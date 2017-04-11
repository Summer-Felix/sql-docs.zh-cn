---
title: "PolyBase 受版本控制的功能摘要 | Microsoft Docs"
ms.custom: ""
ms.date: "04/13/2016"
ms.prod: "sql-non-specified"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6591994d-6109-4285-9c5b-ecb355f8a111
caps.latest.revision: 10
author: "barbkess"
ms.author: "barbkess"
manager: "jhubbard"
caps.handback.revision: 8
---
# PolyBase 受版本控制的功能摘要
[!INCLUDE[tsql-appliesto-ss2016-xxxx-asdw-pdw_md](../../includes/tsql-appliesto-ss2016-xxxx-asdw-pdw-md.md)]

  可用于 SQL Server 产品和服务的 PolyBase 功能的摘要。  
  
## 产品版本的功能摘要  
 此表概述了 PolyBase 的主要功能以及提供这些功能的产品。  
  
### [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)]  
 这些功能适用于在本地运行或在 Azure 虚拟机中运行的 [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)]。  PolyBase 在 SQL Server 2014 和更早版本中不可用。  
  
|||  
|-|-|  
|**功能**|**可用性**|  
|查询 Hadoop 数据和 [!INCLUDE[tsql](../../includes/tsql-md.md)]|是|  
|查询 Azure blob 存储 [!INCLUDE[tsql](../../includes/tsql-md.md)]|是|  
|从 Hadoop 导入数据|是|  
|从 Azure blob 存储导入数据|是|  
|导出数据到 Hadoop|是|  
|导出数据到 Azure blob 存储|是|  
|从 Microsoft 的 BI 工具运行 PolyBase Queries|是|  
|将查询计算下推到 Hadoop|是|  
  
### [!INCLUDE[ssSDW](../../includes/sssdw-md.md)]  
 这些功能适用于 [!INCLUDE[ssSDW](../../includes/sssdw-md.md)]。  
  
|||  
|-|-|  
|**功能**|**可用性**|  
|查询 Hadoop 数据和 [!INCLUDE[tsql](../../includes/tsql-md.md)]|否|  
|查询 Azure blob 存储 [!INCLUDE[tsql](../../includes/tsql-md.md)]|是|  
|从 Hadoop 导入数据|否|  
|从 Azure blob 存储导入数据|是|  
|导出数据到 Hadoop|否|  
|导出数据到 Azure blob 存储|是|  
|从 Microsoft 的 BI 工具运行 PolyBase Queries|是|  
|将查询计算下推到 Hadoop|否|  
  
### [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 这些功能适用于 [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]。  
  
|||  
|-|-|  
|**功能**|**可用性**|  
|查询 Hadoop 数据和 [!INCLUDE[tsql](../../includes/tsql-md.md)]|是|  
|查询 Azure blob 存储 [!INCLUDE[tsql](../../includes/tsql-md.md)]|是|  
|从 Hadoop 导入数据|是|  
|从 Azure blob 存储导入数据|是|  
|导出数据到 Hadoop|是|  
|导出数据到 Azure blob 存储|是|  
|从 Microsoft 的 BI 工具运行 PolyBase Queries|是|  
|将查询计算下推到 Hadoop|是|  
  
## 另请参阅  
 [PolyBase 指南](../../relational-databases/polybase/polybase-guide.md)  
  
  