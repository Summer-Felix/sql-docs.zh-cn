---
title: "创建版本标志 (Master Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "master-data-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "创建版本标志 [Master Data Services]"
  - "版本标志 [Master Data Services], 创建"
  - "版本 [Master Data Services], 创建标志"
ms.assetid: 3067e1e3-05b7-4f11-9206-c612ef4e7e42
caps.latest.revision: 7
author: "sabotta"
ms.author: "carlasab"
manager: "jhubbard"
caps.handback.revision: 7
---
# 创建版本标志 (Master Data Services)
  在 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]中，创建要分配给某一版本的标志。 该标志可以指示用户或订阅系统应使用的版本。  
  
## 先决条件  
 若要执行此过程：  
  
-   您必须有权访问 **“版本管理”** 功能区域。  
  
-   您必须是模型管理员。 有关详细信息，请参阅[管理员 (Master Data Services)](../master-data-services/administrators-master-data-services.md)。  
  
-   你必须有权访问“版本管理”功能区域。 有关详细信息，请参阅[功能区域权限 (Master Data Services)](../master-data-services/functional-area-permissions-master-data-services.md)。  
  
### 创建版本标志  
  
1.  在 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]中，单击 **“版本管理”**。  
  
2.  在 **“管理版本”** 页上，从菜单栏中，指向 **“管理”** ，然后单击 **“标志”**。  
  
3.  在 **“管理版本标志”** 页上，从 **“模型”** 字段中，选择要为其创建标志的模型。  
  
4.  单击 **“添加”**。  
  
5.  在 **“名称”** 框中，键入名称。  
  
6.  在 **“说明”** 框中，键入说明。  
  
7.  在 **“仅提交的版本”** 字段中，选择 **True** 以便指示只能将标志分配给状态为 **“已提交”** 的版本。 选择 **False** 以便指示可以将标志分配给具有任何状态的版本。  
  
8.  单击 **“保存”**。  
  
## 后续步骤  
  
-   [向版本分配标志 (Master Data Services)](../master-data-services/assign-a-flag-to-a-version-master-data-services.md)  
  
## 另请参阅  
 [版本 (Master Data Services)](../master-data-services/versions-master-data-services.md)   
 [更改版本标志名称 (Master Data Services)](../master-data-services/change-a-version-flag-name-master-data-services.md)  
  
  