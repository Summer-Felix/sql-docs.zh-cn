---
title: "FTP 任务编辑器（“文件传输”页） | Microsoft Docs"
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
  - "sql13.dts.designer.ftptask.filetransfer.f1"
helpviewer_keywords: 
  - "文件传输协议任务编辑器"
ms.assetid: 37e52220-feb2-474c-ad88-fa1b1059acd4
caps.latest.revision: 26
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 26
---
# FTP 任务编辑器（“文件传输”页）
  可以使用 **“FTP 任务编辑器”** 对话框的 **“文件传输”** 页配置任务执行的 FTP 操作。  
  
 若要了解此任务，请参阅 [FTP 任务](../../integration-services/control-flow/ftp-task.md)。  
  
## 选项  
 **IsRemotePathVariable**  
 指示远程路径是否存储在变量中。 此属性具有下表所列的选项。  
  
|“值”|Description|  
|-----------|-----------------|  
|**True**|目标路径存储在变量中。 选择该值将显示动态选项 **RemoteVariable**。|  
|**False**|目标路径在文件连接管理器中指定。 选择该值将显示动态选项 **RemotePath**。|  
  
 **OverwriteFileAtDestination**  
 指定是否可以覆盖目标位置中的文件。  
  
 **IsLocalPathVariable**  
 指示本地路径是否存储在变量中。 此属性具有下表所列的选项。  
  
|“值”|Description|  
|-----------|-----------------|  
|**True**|目标路径存储在变量中。 选择该值将显示动态选项 **LocalVariable**。|  
|**False**|目标路径在文件连接管理器中指定。 选择该值将显示动态选项 **LocalPath**。|  
  
 **运算**  
 选择要执行的 FTP 操作。 此属性具有下表所列的选项。  
  
|“值”|Description|  
|-----------|-----------------|  
|**发送文件**|发送文件。 选择此值将显示动态选项 **LocalVariable**、**LocalPathRemoteVariable** 和 **RemotePath**。|  
|**接收文件**|接收文件。 选择此值将显示动态选项 **LocalVariable**、**LocalPathRemoteVariable** 和 **RemotePath**。|  
|**创建本地目录**|创建本地目录。 选择此值将显示动态选项 **LocalVariable** 和 **LocalPath**。|  
|**创建远程目录**|创建远程目录。 选择此值将显示动态选项 **RemoteVariable** 和 **RemotelPath**。|  
|**删除本地目录**|删除本地目录。 选择此值将显示动态选项 **LocalVariable** 和 **LocalPath**。|  
|**删除远程目录**|删除远程目录。 选择此值将显示动态选项 **RemoteVariable** 和 **RemotePath**。|  
|**删除本地文件**|删除本地文件。 选择此值将显示动态选项 **LocalVariable** 和 **LocalPath**。|  
|**删除远程文件**|删除远程文件。 选择此值将显示动态选项 **RemoteVariable** 和 **RemotePath**。|  
  
 **IsTransferASCII**  
 指示是否应以 ASCII 模式传输从远程 FTP 服务器传输来的文件和传输到远程 FTP 服务器上的文件。  
  
## IsRemotePathVariable 动态选项  
  
### IsRemotePathVariable = True  
 **RemoteVariable**  
 选择现有的用户定义变量，或单击 \<“新建变量...”> 以创建用户定义变量。  
  
 **相关主题：**[Integration Services (SSIS) 变量](../../integration-services/integration-services-ssis-variables.md)、添加变量  
  
### IsRemotePathVariable = False  
 **RemotePath**  
 选择现有 FTP 连接管理器，或单击“\<新建连接...>”以创建连接管理器。  
  
 **相关主题**：[FTP 连接管理器](../../integration-services/connection-manager/ftp-connection-manager.md)、[FTP 连接管理器编辑器](../../integration-services/connection-manager/ftp-connection-manager-editor.md)  
  
## IsLocalPathVariable 动态选项  
  
### IsLocalPathVariable = True  
 **LocalVariable**  
 选择现有的用户定义变量，或单击 \<“新建变量...”> 以创建变量。  
  
 **相关主题：**[Integration Services (SSIS) 变量](../../integration-services/integration-services-ssis-variables.md)、添加变量  
  
### IsLocalPathVariable = False  
 **LocalPath**  
 选择现有文件连接管理器，或单击 \<“新建连接...”> 以创建连接管理器。  
  
 **相关主题**： [Flat File Connection Manager](../../integration-services/connection-manager/flat-file-connection-manager.md)、 [File Connection Manager Editor](../../integration-services/connection-manager/file-connection-manager-editor.md)  
  
## 另请参阅  
 [Integration Services 错误和消息引用](../../integration-services/integration-services-error-and-message-reference.md)   
 [FTP 任务编辑器（“常规”页）](../../integration-services/control-flow/ftp-task-editor-general-page.md)   
 [“表达式”页](../../integration-services/expressions/expressions-page.md)  
  
  