---
title: "打开活动监视器 (SQL Server Management Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "08/05/2016"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "活动监视器 [SQL Server], 设置刷新间隔"
  - "活动监视器的刷新间隔"
  - "活动监视器 [SQL Server], 打开"
  - "opening Activity Monitor"
ms.assetid: 0a6eeb16-f02b-479d-9a60-543e40ebf46b
caps.latest.revision: 38
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 38
---
# 打开活动监视器 (SQL Server Management Studio)

   
 活动监视器将在被监视的实例上运行查询以获取有关活动监视器显示窗格的信息。 当刷新间隔设置为小于 10 秒时，运行这些查询所用的时间可能会对服务器性能产生影响。  
  
  
##  <a name="Permissions"></a> 检查你的权限！  
 若要查看实际的活动，必须拥有 VIEW SERVER STATE 权限。 若要查看活动监视器的“数据文件 I/O”部分，除了 VIEW SERVER STATE 之外，您还必须具有 CREATE DATABASE、ALTER ANY DATABASE 或 VIEW ANY DEFINITION 权限。  
  
 若要终止进程，用户必须是 sysadmin 或 processadmin 固定服务器角色的成员。  
  
  
## 打开活动监视器  

### 键盘快捷键  
 - 键入“Ctrl+Alt+A”可随时打开活动监视器。

 >**提示！** 将鼠标悬停在 SSMS 中的任何图标上方可了解该图标是什么，以及哪个键盘快捷键可激活它！

### 工具栏

在标准工具栏上，单击“活动监视器”图标。 该图标位于中间，就在“撤消/重做”按钮的右边。
![Activity_Monitor_icon](../../relational-databases/performance-monitor/media/activity-monitor-icon.png)  
  
如果尚未连接到想要监视的 SQL Server 的实例，请完成“连接到服务器”对话框。
  
## 在启动时启动活动监视器和对象资源管理器
  
1.  从 **“工具”** 菜单中，单击 **“选项”**。  
  
2.  在“选项”对话框中，展开“环境”，再选择“启动”。  
  
3.  在“启动时”下拉列表中，选择“打开对象资源管理器和活动监视器”。  

4.  单击 **“确定”**。
  
![open_object_explorer](../../relational-databases/performance-monitor/media/open-object-explorer.png)
  
  
## 设置活动监视器刷新间隔  
  
1.   打开活动监视器。  
  
2.   右键单击“概述”，选择“刷新间隔”，然后选择活动监视器获取新实例信息所用的间隔。  
  
  