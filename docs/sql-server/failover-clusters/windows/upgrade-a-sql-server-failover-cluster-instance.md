---
title: "升级 SQL Server 故障转移群集实例 | Microsoft Docs"
ms.custom: ""
ms.date: "02/01/2016"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-high-availability"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "升级故障转移群集"
  - "群集 [SQL Server], 升级"
  - "故障转移群集 [SQL Server], 升级"
ms.assetid: daac41fe-7d0b-4f14-84c2-62952ad8cbfa
caps.latest.revision: 47
author: "MikeRayMSFT"
ms.author: "mikeray"
manager: "jhubbard"
caps.handback.revision: 47
---
# 升级 SQL Server 故障转移群集实例
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 支持将 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 故障转移群集升级到 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 的新版本、新的 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 服务包或积累更新，或在所有故障转移节点上分别将其安装到新的 Windows 服务包或积累更新时进行升级，故障时间限制为一次手动故障转移（或者如果无法故障转移回原始的主要副本，则限制为两次手动故障转移）。  
  
 Windows Server 2012 R2 之前的操作系统不支持升级故障转移群集的 Windows 操作系统。 若要升级在 Windows Server 2012 R2 上运行的群集节点，请参阅 [Cluster Operating System Rolling Upgrade](https://technet.microsoft.com/en-us/library/dn850430.aspx)（群集操作系统滚动升级）  
  
 支持详细信息如下所示：  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]升级，也支持从命令提示符处进行升级。 可以从每个故障转移群集节点上的命令提示符处运行升级，也可以使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 安装程序 UI 来升级每个群集节点。  有关详细信息，请参阅[升级 SQL Server 故障转移群集实例（安装程序）](../../../sql-server/failover-clusters/windows/upgrade-a-sql-server-failover-cluster-instance-setup.md) 和 [从命令提示符安装 SQL Server 2016](../../../database-engine/install-windows/install-sql-server-2016-from-the-command-prompt.md)。  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 升级不支持以下方案：  
  
    -   不能从独立的 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 实例升级到故障转移群集。  
  
    -   不能向故障转移群集中添加功能。 例如，不能向现在仅 [!INCLUDE[ssDE](../../../includes/ssde-md.md)] 的故障转移群集中添加[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]。  
  
    -   不能将故障转移群集节点降级为独立的实例。  
  
    -   仅允许在某些方案中更改故障转移群集的版本。 有关详细信息，请参阅[支持的版本升级](../../../database-engine/install-windows/supported-version-and-edition-upgrades.md)。  
  
-   在故障转移群集升级过程中，停机时间限制为故障转移时间和运行升级脚本所需的时间。 在开始进行升级过程之前，如果遵循下方的故障转移群集滚动升级过程并满足所有节点的所有先决条件，则故障时间将最短。 在内存优化表处于使用中时升级 SQL Server 2014 会耗费一些额外时间。 有关详细信息，请参阅 [Plan and Test the Database Engine Upgrade Plan](../../../database-engine/install-windows/plan-and-test-the-database-engine-upgrade-plan.md)。  
  
## 先决条件  
 开始之前，请仔细阅读以下重要信息：  
  
-   [Supported Version and Edition Upgrades](../../../database-engine/install-windows/supported-version-and-edition-upgrades.md)：验证是否可以从你的 Windows 操作系统版本和 SQL Server 版本升级到 SQL Server 2016。 例如，不能直接从 SQL Server 2005 故障转移群集实例升级到 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] 或升级在 Windows Server 2003 上运行的故障转移群集。  
  
-   [Choose a Database Engine Upgrade Method](../../../database-engine/install-windows/choose-a-database-engine-upgrade-method.md)︰检查支持的版本和版本升级以及环境中安装的其他组件，并据此选择适当的升级方法和步骤，按正确顺序升级组件。  
  
-   [计划并测试数据库引擎升级计划](../../../database-engine/install-windows/plan-and-test-the-database-engine-upgrade-plan.md)：查看发行说明和已知升级问题、预升级清单，并制定和测试升级计划。  
  
-   [安装 SQL Server 2016 的硬件和软件要求](../../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server-2016.md)：查看安装 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] 的软件要求。 如果需要其他软件，则应在升级过程开始之前在每个节点上安装该软件，从而最大程度减少故障时间。  
  
## 执行滚动升级或更新  
 若要将 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 故障转移群集升级到 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]，请使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 安装程序，从被动节点开始逐个升级每个故障转移群集节点。 升级每个节点时，节点被放在故障转移群集的可能所有者之外。 如果发生意外故障转移，已升级的节点将不参与故障转移，直到 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 安装程序将群集资源组的所有权转移给已升级的节点。  
  
 默认情况下， [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 安装程序自动确定何时将故障转移到已升级的节点。 这取决于故障转移群集实例中节点的总数和已经升级的节点数。 如果有一半或更多节点已经升级，则当你在下一个节点上执行升级时， [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 安装程序会导致故障转移到已升级的节点。 在故障转移到已升级的节点后，群集组将移至已升级的节点。 所有已升级的节点都放在可能的所有者列表中，所有尚未升级的节点都将从可能的所有者列表中删除。 升级剩余的每个节点时，节点被添加到故障转移群集的可能所有者那里。  
  
 此过程使停机时间限制为整个故障转移群集升级过程中的一次故障转移时间和数据库升级脚本执行时间。  
  
 若要控制升级过程中群集节点的故障转移行为，请从命令提示符运行升级操作，并使用 /FAILOVERCLUSTERROLLOWNERSHIP 参数。 有关详细信息，请参阅[从命令提示符安装 SQL Server 2016](../../../database-engine/install-windows/install-sql-server-2016-from-the-command-prompt.md)。  
  
## 另请参阅  
 [使用安装向导（安装程序）升级到 SQL Server 2016](../../../database-engine/install-windows/upgrade-to-sql-server-2016-using-the-installation-wizard-setup.md)   
 [从命令提示符安装 SQL Server 2016](../../../database-engine/install-windows/install-sql-server-2016-from-the-command-prompt.md)   
 [升级 SQL Server 故障转移群集实例（安装程序）](../../../sql-server/failover-clusters/windows/upgrade-a-sql-server-failover-cluster-instance-setup.md)  
  
  