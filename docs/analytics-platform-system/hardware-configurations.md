---
title: "硬件配置 (Analytics Platform System)"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.prod: analytics-platform-system
ms.prod_service: mpp-data-warehouse
ms.service: 
ms.component: 
ms.suite: sql
ms.custom: 
ms.technology: mpp-data-warehouse
description: "分析平台系统 (AP) 硬件的架构使用可缩放单位，以便根据你的业务要求购买合适的处理和存储量。"
ms.date: 01/05/2017
ms.topic: article
ms.assetid: f95945b7-97ae-4ab9-bae5-c792a516acea
caps.latest.revision: "9"
ms.openlocfilehash: 6762775fdec3cd3a01a372ed5c16fbc4a93c1426
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="hardware-configurations"></a>硬件配置
分析平台系统 (AP) 硬件的架构使用可缩放单位，以便根据你的业务要求购买合适的处理和存储量。 设备缩放存储的 SQL Server 并行数据仓库 (PDW) 从几兆兆字节到超过 6 的千万亿字节数据。  
  
## <a name="contents"></a>目录  
  
-   [一个机架配置](#section1)  
  
-   [多机架配置](#section2)  

  
## <a name="section1"></a>一个机架配置  
在设备中的第一个机架包含运行 PDW 所需的组件。 最低设备配置是机架和网络加上基本缩放单位。 这些图显示方式，可以配置第一个设备的机架。 你可以有 2 和 9 中第一个机架，具体取决于硬件供应商的计算节点。  
  
### <a name="first-rack-configurations---dell"></a>第一次机架配置-DELL  
DELL 设备的最低配置具有 3 个计算节点。 可以将最多为 2 的数据扩展单元添加到 9 的计算节点的总计的第一个机架中。  
  
![Dell first 机架配置](media/first-rack-configurations-dell.png "Dell first 机架配置")  
  
### <a name="first-rack-configurations---hpe"></a>第一次机架配置-HPE  
HPE 设备的最低配置具有 2 个计算节点。 可以将最多 3 的数据扩展单元添加到第一个机架总共 8 个计算节点。  
  
![HPE 首先机架配置 HPE](media/first-rack-configurations-hpe.png "HPE 首先机架配置")  
  
## <a name="section2"></a>多机架配置  
若要将容量添加到 PDW 可以添加数据缩放单位，根据需要提供正确的电源，其他机架和网络组件以及网络、，机架基础结构。 每个其他机架与网络都需要一个被动宿主。  
  
每个硬件供应商指定数据缩放指定的单位数可以添加你的设备的容量。 我们建议添加足够的数据缩放单位，以查看至少 20%提升性能。 例如，添加一种数据比例到设备已 20 数据缩放单位单元可能会导致较可以忽略不计的性能提升。 净的性能收益不是值得的成本和工作量。  
  
### <a name="scale-out-example---hpe"></a>横向扩展示例-HPE  
下图显示一个包含 20 个计算节点的 3 机架 HP 设备。  
  
![HPE 设备，但有 20 个计算节点](media/scale-out-hpe.png "HPE 设备，但有 20 个计算节点")  
  
### <a name="scale-out-example--dell-quanta"></a>横向扩展示例-DELL，量程  
下图显示包含 21 的计算节点是 3 机架 DELL 或量程装置。  
  
![Dell 设备，但有 21 的计算节点](media/scale-out-dell.png "Dell 设备，但有 21 的计算节点")  
 
