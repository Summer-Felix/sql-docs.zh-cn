---
title: "导出和导入数据挖掘对象 | Microsoft Docs"
ms.custom: ""
ms.date: "03/06/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
  - "analysis-services/data-mining"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "备份数据库 [Analysis Services]"
  - "导出挖掘模型"
  - "导出挖掘结构"
  - "挖掘结构 [Analysis Services], 创建"
  - "挖掘结构 [DMX], 导出"
  - "挖掘模型 [Analysis Services], 迁移"
ms.assetid: 10a83b13-2640-4ff5-80c8-a35e1d692908
caps.latest.revision: 23
author: "Minewiskan"
ms.author: "owend"
manager: "jhubbard"
caps.handback.revision: 23
---
# 导出和导入数据挖掘对象
  除了 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 中提供的用于备份、还原和迁移解决方案的功能外，SQL Server 数据挖掘还提供了可通过使用数据挖掘扩展插件 (DMX)，在不同的服务器之间快速传输数据挖掘结构和模型的功能。  
  
 如果您的数据挖掘解决方案使用的是关系数据而不是多维数据库时，与使用数据还原或部署整个解决方案相比，使用 **EXPORT** 和 **IMPORT** 来传输模型更加快捷。  
  
 本节简要说明如何使用 DMX 语句来传输数据挖掘结构和模型。 有关语法的详细信息以及相应的示例，请参阅 [EXPORT (DMX)](../../dmx/export-dmx.md) 和 [IMPORT (DMX)](../../dmx/import-dmx.md)。  
  
> [!NOTE]  
>  只有数据库或服务器管理员才能从 Microsoft SQL Server Analysis Services 数据库导出对象或向其中导入对象。  
  
## 导出数据挖掘结构  
 导出挖掘结构时，EXPORT 语句将自动导出所有关联的模型。 若要控制导出的对象，则必须按名称逐个指定每个对象。  
  
 如果挖掘结构已经过处理且已缓存结果（这是默认行为），则在您导出挖掘结构时，定义中将包含该结构所基于的数据的摘要。 若要删除此摘要，则必须通过执行 **Process Clear Structure** 操作来清除与挖掘结构相关联的缓存。 有关详细信息，请参阅 [Process a Mining Structure](../../analysis-services/data-mining/process-a-mining-structure.md)。  
  
### 导出数据挖掘模型  
 您可以使用 **WITH DEPENDENCIES** 关键字导出数据源、数据源视图定义以及挖掘模型及其结构。  
  
 如果导出挖掘模型，但却不导出其依赖项，则 EXPORT 语句将导出挖掘模型的定义及其挖掘结构，而不导出数据源的定义。 因此，导入了模型后您将能够立即浏览该模型，但是，如果您想要在目标服务器上重新处理挖掘模型，或对基础数据运行查询，则必须在目标服务器上创建相应的数据源。  
  
## 导入数据挖掘结构和模型  
 导入数据挖掘对象时，对象将被导入到您在执行 IMPORT 语句时所连接到的服务器和数据库。 如果导入文件包含服务器中不存在的数据库，则系统将创建该数据库。  
  
 您还可以使用 **Restore** 命令来导入挖掘结构或挖掘模型。 您的模型或结构将被还原到与其所导出的数据库同名的数据库中。 有关详细信息，请参阅 [Restore Options](../../analysis-services/multidimensional-models/restore-options.md)。  
  
## 注释  
 如果服务器中已存在同名模型或结构，则不能将模型或结构导入该服务器。 同样，也不能先导出数据挖掘对象，然后在导出文件中修改对象的名称。 因此，如果预计会出现命名冲突，请删除目标服务器上的数据挖掘对象，或在导出定义前重新命名该数据挖掘对象。  
  
## 另请参阅  
 [管理数据挖掘解决方案和对象](../../analysis-services/data-mining/management-of-data-mining-solutions-and-objects.md)  
  
  