---
title: "指定轴 (SQLXML 4.0) |Microsoft 文档"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: sqlxml
ms.reviewer: 
ms.suite: sql
ms.technology:
- dbe-xml
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], axes
- XPath queries [SQLXML], location paths
- self axis
- attribute axis [SQLXML]
- axis [SQLXML]
- child axis
- parent axis
- location path for XPath query
- axes [SQLXML]
ms.assetid: 65631795-3389-40cf-90ea-85e9438956c5
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: d70d1868f676eba9e3d7365d1fada29f550a9a3a
ms.sourcegitcommit: 37f0b59e648251be673389fa486b0a984ce22c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2018
---
# <a name="specifying-an-axis-sqlxml-40"></a>指定轴 (SQLXML 4.0)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
    
-   轴指定根据位置步骤和上下文节点选择的节点之间的树关系。 支持以下轴：**子**  
  
     包含上下文节点的子级。  
  
     下面的 XPath 表达式 （位置路径） 选择从当前上下文节点所有**\<客户 >**子级：  
  
    ```  
    child::Customer  
    ```  
  
     在下面的 XPath 查询中，`child` 为轴。 `Customer` 是节点测试。  
  
-   **parent**  
  
     包含上下文节点的父级。  
  
     下面的 XPath 表达式选择所有**\<客户 >**的父级**\<顺序 >**子级：  
  
    ```  
    child::Customer/child::Order[parent::Customer/@customerID="ALFKI"]  
    ```  
  
     这与指定 `child::Customer` 的作用相同。 在此 XPath 查询中，`child` 和 `parent` 为轴。 `Customer` 和 `Order` 是节点测试。  
  
-   **attribute**  
  
     包含上下文节点的属性。  
  
     下面的 XPath 表达式选择**CustomerID**的上下文节点的属性：  
  
    ```  
    attribute::CustomerID  
    ```  
  
-   **self**  
  
     包含上下文节点本身。  
  
     下面的 XPath 表达式选择当前节点是否**\<顺序 >**节点：  
  
    ```  
    self::Order  
    ```  
  
     在此 XPath 查询中，`self` 为轴，`Order` 为节点测试。  
  
  
