---
title: "交互式搜索文档 | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "交互搜索 [SQL Server Management Studio]"
  - "搜索 [SQL Server Management Studio], 交互"
  - "查询编辑器 [SQL Server Management Studio], 交互式搜索"
ms.assetid: dae65ac5-67af-45c6-a6e0-952fea26d680
caps.latest.revision: 22
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 22
---
# 交互式搜索文档
  使用 **“查找和替换”** 对话框，可以搜索一个或多个打开的文件或窗口，并逐个移动到每个搜索匹配项。 该技术允许您在匹配项周围的文本上下文中检查每个单独的搜索匹配项。 **“查找和替换”** 对话框还提供了执行大容量查找操作和在报表格式中检查搜索匹配项的选项。  
  
### 搜索所有打开的文档  
  
1.  打开想要搜索的项。  
  
2.  在“编辑”菜单上，指向“查找和替换”，再单击“快速查找”。  
  
3.  在 **“查找和替换”** 文本框中，输入要搜索的文本。  
  
4.  在 **“查找范围”** 列表中，选择 **“所有打开的文档”**。  
  
    > [!NOTE]  
    >  如果选择 **“所有打开的文档”** ，则可能不搜索某些打开的文件。 只有当前在文本视图（如代码视图）中打开的文件才会包括在搜索中。 设计器视图中的文件不包括在搜索中。  
  
5.  选择其他搜索选项可以提高搜索准确性。  
  
6.  单击 **“查找下一个”** 可以启动搜索，连续单击 **“查找下一个”** 直到搜索了最后一个文件。  
  
 在搜索通过文档的开始或末尾时，将在状态栏中显示消息。 如果搜索到达搜索的起点，则出现消息框。  
  
#### 在所有活动文件中交互式替换  
  
1.  在“编辑”菜单上，指向“查找和替换”，再单击“快速替换”。  
  
2.  在 **“查找内容”** 框中，输入要搜索的文本。  
  
3.  在 **“替换为”** 框中，输入用来替换搜索文本的文本。  
  
4.  在 **“查找范围”** 列表中，选择 **“所有打开的文档”**。  
  
5.  单击 **“替换”**，并连续单击 **“替换”** ，直到替换了最后一个文件中的最后一个匹配项。 单击 **“查找下一个”** 可以跳过不想替换的匹配项。  
  
     - 或 -  
  
     选择 **“全部替换”** 以替换所有匹配项。 然后将出现消息框，列出替换的总数。  
  
 **“全部替换”** 命令将替换所有搜索匹配项，包括那些已经用 **“查找下一个”** 按钮跳过的匹配项。 若要取消 **“全部替换”**，请在关闭任何文件之前从 **“编辑”** 菜单中单击 **“撤消”** 。  
  
## 另请参阅  
 [增量搜索活动文档](../../relational-databases/scripting/search-an-active-document-incrementally.md)   
 [搜索和替换](../../relational-databases/scripting/search-and-replace.md)   
 [使用结果列表搜索文档](../../relational-databases/scripting/search-documents-using-results-lists.md)   
 [使用通配符搜索文本](../../relational-databases/scripting/search-text-with-wildcards.md)   
 [使用正则表达式搜索文本](../../relational-databases/scripting/search-text-with-regular-expressions.md)  
  
  