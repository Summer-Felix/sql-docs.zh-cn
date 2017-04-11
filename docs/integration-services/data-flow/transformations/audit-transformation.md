---
title: "审核转换 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dts.designer.audittrans.f1"
helpviewer_keywords: 
  - "包中的环境数据 [Integration Services]"
  - "审核转换"
ms.assetid: 8c143682-9c81-4150-83d6-1d9678151d37
caps.latest.revision: 46
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 46
---
# 审核转换
  通过进行审核转换，包中的数据流可以包含有关运行包的环境的数据。 例如，包、计算机和操作员的名称可添加到数据流中。 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] 中包含了提供这些信息的系统变量。  
  
## 系统变量  
 下表介绍了审核转换可以使用的系统变量。  
  
|系统变量|索引|Description|  
|---------------------|-----------|-----------------|  
|**ExecutionInstanceGUID**|0|标识包的执行实例的 GUID。|  
|**PackageID**|1|包的唯一标识符。|  
|**PackageName**|2|包名称。|  
|**VersionID**|3|包的版本。|  
|**ExecutionStartTime**|4|包开始运行的时间。|  
|**MachineName**|5|计算机名称。|  
|**UserName**|6|启动包的人员的登录名。|  
|**TaskName**|7|与审核转换相关联的数据流任务的名称。|  
|**TaskId**|8|数据流任务的唯一标识符。|  
  
## 审核转换的配置  
 您可以通过提供要添加到转换输出的新输出列的名称，然后将系统变量映射到该输出列，来配置审核转换。 可以将单个系统变量映射到多个列。  
  
 此转换有一个输入和一个输出。 它不支持错误输出。  
  
 可以通过 [!INCLUDE[ssIS](../../../includes/ssis-md.md)] 设计器或以编程方式来设置属性。  
  
 有关可在 **“审核转换编辑器”** 对话框中设置的属性的详细信息，请参阅 [Audit Transformation Editor](../../../integration-services/data-flow/transformations/audit-transformation-editor.md)。  
  
 **“高级编辑器”** 对话框反映了可以通过编程方式进行设置的属性。 有关可以在 **“高级编辑器”** 对话框中或以编程方式设置的属性的详细信息，请单击下列主题之一：  
  
-   [通用属性](../Topic/Common%20Properties.md)  
  
-   [转换自定义属性](../../../integration-services/data-flow/transformations/transformation-custom-properties.md)  
  
 有关如何设置属性的详细信息，请参阅[设置数据流组件的属性](../../../integration-services/data-flow/set-the-properties-of-a-data-flow-component.md)。  
  
  