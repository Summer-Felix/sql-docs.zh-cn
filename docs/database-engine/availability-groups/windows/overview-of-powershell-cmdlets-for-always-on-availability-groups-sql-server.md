---
title: "AlwaysOn 可用性组的 PowerShell Cmdlet 概述 (SQL Server) | Microsoft Docs"
ms.custom: 
ms.date: 08/30/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: availability-groups
ms.reviewer: 
ms.suite: sql
ms.technology: dbe-high-availability
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Availability Groups [SQL Server], PowerShell cmdlets
- Availability Groups [SQL Server], about
- PowerShell [SQL Server], cmdlets
ms.assetid: b3fef0d5-b6d7-4386-a0f0-d06c165ad4de
caps.latest.revision: "36"
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 1a6b9e19ea916963acf28a222d5bd463bc5662d4
ms.sourcegitcommit: dcac30038f2223990cc21775c84cbd4e7bacdc73
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2018
---
# <a name="overview-of-powershell-cmdlets-for-always-on-availability-groups-sql-server"></a>Always On 可用性组的 PowerShell Cmdlet 概述 (SQL Server)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[msCoName](../../../includes/msconame-md.md)] PowerShell 是专门设计用于系统管理的基于任务的命令行 Shell 和脚本语言。 [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] 在 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] 中提供一组 PowerShell cmdlet，支持您部署、管理和监视可用性组、可用性副本和可用性数据库。  
  
> [!NOTE]  
>  一旦成功启动某操作，PowerShell cmdlet 即告完成。 这并不表示要执行的工作（例如可用性组的故障转移）已经完成。 对一系列操作编写脚本时，您可能必须检查这些操作的状态，并等待这些操作完成。  
  
 本主题介绍了用于执行下列各组任务的 cmdlet：  
  
-   [为 Always On 可用性组配置服务器实例](#ConfiguringServerInstance)  
  
-   [备份和还原数据库和事务日志](#BnRcmdlets)  
  
-   [创建和管理可用性组](#DeployManageAGs)  
  
-   [创建和管理可用性组侦听器](#AGlisteners)  
  
-   [创建和管理可用性副本](#DeployManageARs)  
  
-   [添加和管理可用性数据库](#DeployManageDbs)  
  
-   [监视可用性组的运行状况](#MonitorTblshtAGs)  
  
> [!NOTE]  
>  有关描述如何使用 cmdlet 来执行 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] 任务的 [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] 联机丛书中的主题列表，请参阅 [AlwaysOn 可用性组概述 (SQL Server)](../../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)的“相关任务”一节。  
  
##  <a name="ConfiguringServerInstance"></a> Configuring a Server Instance for Always On Availability Groups  
  
|Cmdlet|Description|支持平台|  
|-------------|-----------------|------------------|  
|“Disable-SqlAlwaysOn”|禁用服务器实例上的 [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] 功能。|由 **Path**、 **InputObject**或 **Name** 参数指定的服务器实例。 （必须为支持 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 的 [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]版本。)|  
|“Enable-SqlAlwaysOn”|在支持 [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] 功能的 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] 实例上启用 [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] 。 有关针对 [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] 的支持的信息，请参阅[针对 AlwaysOn 可用性组的先决条件、限制和建议 (SQL Server)](../../../database-engine/availability-groups/windows/prereqs-restrictions-recommendations-always-on-availability.md)。|任何支持 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 的 [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]版本。|  
|**New-SqlHadrEndPoint**|在服务器实例上创建新的数据库镜像端点。 在主数据库和辅数据库之间移动数据时需要此端点。|任何 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]|  
|**Set-SqlHadrEndpoint**|更改现有数据库镜像端点的属性，如名称、状态或身份验证属性。|支持 [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] 并缺少数据库镜像端点的服务器实例|  
  
##  <a name="BnRcmdlets"></a> Backing Up and Restoring Databases and Transaction Logs  
  
|Cmdlet|Description|支持平台|  
|-------------|-----------------|------------------|  
|**Backup-SqlDatabase**|创建数据或日志备份。|任何联机数据库（对于 [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]，则为承载主副本的服务器实例上的数据库）|  
|**Restore-SqlDatabase**|还原备份。|任何 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 实例（对于 [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]，则为承载辅助副本的服务器实例）<br /><br /> **\*\* 重要说明 \*\*** 当准备辅助数据库时，必须在每个 **Restore-SqlDatabase** 命令中使用 **-NoRecovery** 参数。|  
  
 有关使用这些 cmdlet 来准备辅助数据库的信息，请参阅[为可用性组手动准备辅助数据库 (SQL Server)](../../../database-engine/availability-groups/windows/manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)。  
  
##  <a name="DeployManageAGs"></a> Creating and Managing an Availability Group  
  
|Cmdlet|Description|支持平台|  
|-------------|-----------------|------------------|  
|**New-SqlAvailabilityGroup**|创建新的可用性组。|承载主副本的服务器实例|  
|**Remove-SqlAvailabilityGroup**|删除可用性组。|启用 HADR 的服务器实例|  
|**Set-SqlAvailabilityGroup**|设置可用性组的属性；使可用性组联机/脱机|承载主副本的服务器实例|  
|**Switch-SqlAvailabilityGroup**|启动下列形式之一的故障转移：<br /><br /> 可用性组的强制故障转移（可能会丢失数据）。<br /><br /> 可用性组的手动故障转移。|承载目标辅助副本的服务器实例|  
  
##  <a name="AGlisteners"></a> Creating and Managing an Availability Group Listener  
  
|Cmdlet|Description|支持平台|  
|------------|-----------------|------------------|  
|**New-SqlAvailabilityGroupListener**|创建一个新的可用性组侦听器，并将其附加到一个现有可用性组。|承载主副本的服务器实例|  
|**Set-SqlAvailabilityGroupListener**|修改现有可用性组侦听器的端口设置。|承载主副本的服务器实例|  
|**Add-SqlAvailabilityGroupListenerStaticIp**|将一个静态 IP 地址添加到现有的可用性组侦听器配置。 此 IP 地址可以是带子网的 IPv4 地址或 IPv6 地址。|承载主副本的服务器实例|  
  
##  <a name="DeployManageARs"></a> Creating and Managing an Availability Replica  
  
|Cmdlet|Description|支持平台|  
|-------------|-----------------|------------------|  
|**New-SqlAvailabilityReplica**|创建新的可用性副本。 你可以使用 **-AsTemplate** 参数为每个新的可用性副本创建内存中的可用性副本对象。|承载主副本的服务器实例|  
|**Join-SqlAvailabilityGroup**|将辅助副本联接到该可用性组。|承载辅助副本的服务器实例|  
|**Remove-SqlAvailabilityReplica**|删除可用性副本。|承载主副本的服务器实例|  
|**Set-SqlAvailabilityReplica**|设置可用性副本的属性。|承载主副本的服务器实例|  
  
##  <a name="DeployManageDbs"></a> Adding and Managing an Availability Database  
  
|Cmdlet|Description|支持平台|  
|-------------|-----------------|------------------|  
|**Add-SqlAvailabilityDatabase**|在主副本上，将数据库添加到可用性组。<br /><br /> 在辅助副本上，将辅助数据库联接到可用性组。|承载可用性副本的任何服务器实例（主副本与辅助副本的行为不同）|  
|**Remove-SqlAvailabilityDatabase**|在主副本上，从可用性组中删除数据库。<br /><br /> 在辅助副本上，从本地辅助副本中删除本地辅助数据库。|承载可用性副本的任何服务器实例（主副本与辅助副本的行为不同）|  
|**Resume-SqlAvailabilityDatabase**|恢复已挂起的可用性数据库的数据移动。|已挂起数据库所在的服务器实例。|  
|**Suspend-SqlAvailabilityDatabase**|挂起可用性数据库的数据移动。|承载可用性副本的任何服务器实例。|  
  
##  <a name="MonitorTblshtAGs"></a> Monitoring Availability Group Health  
 以下 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cmdlet 支持您监视可用性组及其副本和数据库的运行状况。  
  
> [!IMPORTANT]  
>  您必须具有 CONNECT、VIEW SERVER STATE 和 VIEW ANY DEFINITION 权限才能执行这些 cmdlet。  
  
|Cmdlet|Description|支持平台|  
|------------|-----------------|------------------|  
|**Test-SqlAvailabilityGroup**|通过评估 SQL Server 基于策略的管理 (PBM) 策略来评估可用性组的运行状况。|承载可用性副本的任何服务器实例。*|  
|**Test-SqlAvailabilityReplica**|通过评估 SQL Server 基于策略的管理 (PBM) 策略来评估可用性副本的运行状况。|承载可用性副本的任何服务器实例。*|  
|**Test-SqlDatabaseReplicaState**|通过评估 SQL Server 基于策略的管理 (PBM) 策略来评估所有联接的可用性副本的可用性数据库的运行状况。|承载可用性副本的任何服务器实例。*|  
  
 *若要查看有关可用性组中所有可用性副本的信息，请使用承载主副本的服务器实例。  
  
 有关详细信息，请参阅[使用 AlwaysOn 策略查看可用性组的运行状况 (SQL Server)](../../../database-engine/availability-groups/windows/use-always-on-policies-to-view-the-health-of-an-availability-group-sql-server.md)。  
  
## <a name="see-also"></a>另请参阅  
 [AlwaysOn 可用性组概述 (SQL Server)](../../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 [获取 SQL Server PowerShell 帮助](../../../relational-databases/scripting/get-help-sql-server-powershell.md)  
  
  
