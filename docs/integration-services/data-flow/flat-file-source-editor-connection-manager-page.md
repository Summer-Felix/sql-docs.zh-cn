---
title: "平面文件源编辑器（“连接管理器”页） | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dts.designer.flatfilesourceadapter.connection.f1"
helpviewer_keywords: 
  - "平面文件源编辑器"
ms.assetid: 2efd6baa-ed75-4f3f-b667-514024cebdb8
caps.latest.revision: 29
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 29
---
# 平面文件源编辑器（“连接管理器”页）
  可以使用 **“平面文件源编辑器”** 对话框的 **“连接管理器”** 页，选择平面文件源将使用的连接管理器。 平面文件源从文本文件中读取数据，文本文件可以采用分隔符分隔、固定宽度或混合格式。  
  
 平面文件源可以使用下列类型的连接管理器之一：  
  
-   如果源是单个平面文件，则使用平面文件连接管理器。 有关详细信息，请参阅 [Flat File Connection Manager](../../integration-services/connection-manager/flat-file-connection-manager.md)。  
  
-   如果源是多平面文件并且数据流任务在循环容器（例如 For 循环容器）内，则使用多平面文件连接管理器。 在容器的每个循环中，平面文件源从多平面文件连接管理器提供的下一个文件名加载数据。 有关详细信息，请参阅 [Multiple Flat Files Connection Manager](../../integration-services/connection-manager/multiple-flat-files-connection-manager.md)。  
  
 若要了解有关平面文件源的详细信息，请参阅 [Flat File Source](../../integration-services/data-flow/flat-file-source.md)。  
  
## 选项  
 **平面文件连接管理器**  
 从列表中选择现有的连接管理器，或单击“新建”创建新的连接管理器。  
  
 **新建**  
 通过使用“平面文件连接管理器编辑器”对话框创建新的连接管理器。  
  
 **在数据流中保留源中的空值**  
 指定提取数据时是否保留空值。 此属性的默认值为 **false**。 当此值为 F**alse**时，平面文件源使用每列的相应默认值替换源数据中的空值，例如，对于字符串列使用空字符串，对于数值列使用零。  
  
 **预览**  
 通过使用“数据视图”对话框预览结果。 预览最多可以显示 200 行。  
  
## 另请参阅  
 [Integration Services 错误和消息引用](../../integration-services/integration-services-error-and-message-reference.md)   
 [平面文件源编辑器（“列”页）](../../integration-services/data-flow/flat-file-source-editor-columns-page.md)   
 [平面文件源编辑器（“错误输出”页）](../../integration-services/data-flow/flat-file-source-editor-error-output-page.md)   
 [平面文件连接管理器](../../integration-services/connection-manager/flat-file-connection-manager.md)  
  
  