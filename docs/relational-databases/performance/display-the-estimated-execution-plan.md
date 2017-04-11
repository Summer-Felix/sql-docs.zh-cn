---
title: "显示估计的执行计划 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "显示比例 [SQL Server]"
  - "估计的执行计划 [SQL Server]"
  - "显示执行计划"
  - "查看执行计划"
  - "执行计划 [SQL Server], 显示"
  - "自定义执行计划的显示方式 [SQL Server]"
  - "修改执行计划的显示方式"
  - "自定义显示比例 [SQL Server]"
ms.assetid: e94aa576-4c0c-4c54-ad05-6c3432cc615b
caps.latest.revision: 26
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 26
---
# 显示估计的执行计划
  本主题介绍了如何使用 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]生成图形化的估计的执行计划。 生成估计的执行计划时， [!INCLUDE[tsql](../../includes/tsql-md.md)] 查询或批处理并不执行。 生成的执行计划显示的是如果实际执行查询 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] 最有可能使用的查询执行计划。  
  
 为了使用此功能，用户必须具有执行 [!INCLUDE[tsql](../../includes/tsql-md.md)] 查询（为其生成图形执行计划）的相应权限，并且用户必须获得了对查询引用的所有数据库的 SHOWPLAN 权限。  
  
### 显示查询的估计的执行计划  
  
1.  在工具栏上，单击 **“数据库引擎查询”**。 通过单击 **“打开文件”** 工具栏按钮，再定位到该现有查询，也可以打开一个现有查询并显示估计的执行计划。  
  
2.  输入您希望为其显示估计的执行计划的查询。  
  
3.  在 **“查询”** 菜单上，单击 **“显示估计的执行计划”** ，或单击 **“显示估计的执行计划”** 工具栏按钮。 估计的执行计划在结果窗格中的 **“执行计划”** 选项卡上显示。 若要查看其他信息，请将鼠标暂停在逻辑和物理运算符图标上，并查看显示的工具提示中有关运算符的说明和属性。 另外，还可以在“属性”窗口中查看运算符属性。 如果属性不可见，请右键单击一个运算符并单击“属性”。 选择要查看其属性的运算符。  
  
4.  若要更改执行计划的显示，请右键单击“执行计划”并选择“放大”、“缩小”、“自定义显示比例”或“缩放到合适大小”。 “放大”和“缩小”允许你按固定量扩大或减小执行计划。 “自定义缩放” 允许你定义自己的显示放大倍数，例如缩放到 80%。 **“缩放到合适大小”** 会放大执行计划以适应结果窗格。  
  
  