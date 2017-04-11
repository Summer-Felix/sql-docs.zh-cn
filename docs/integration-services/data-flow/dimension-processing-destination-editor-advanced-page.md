---
title: "维度处理目标编辑器（“高级”页） | Microsoft Docs"
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
  - "sql13.dts.designer.dimprocessingtransformation.advanced.f1"
helpviewer_keywords: 
  - "维度处理目标编辑器"
ms.assetid: 2b30835a-2680-4d98-89a4-4f17e29e3818
caps.latest.revision: 27
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 27
---
# 维度处理目标编辑器（“高级”页）
  可以使用 **“维度处理目标编辑器”** 对话框中的 **“高级”** 页配置错误处理方式。  
  
 若要了解有关维度处理目标的详细信息，请参阅 [Dimension Processing Destination](../../integration-services/data-flow/dimension-processing-destination.md)。  
  
## 选项  
 **使用默认错误配置**  
 指定是否使用 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 的默认错误处理方式。 默认情况下，此值为 **True**。  
  
 **键错误操作**  
 指定如何处理包含不可接受的键值的记录。  
  
|“值”|Description|  
|-----------|-----------------|  
|**ConvertToUnknown**|将不适用的键值转换为 **UnknownMember** 值。|  
|**DiscardRecord**|放弃记录。|  
  
 **忽略错误**  
 指定将忽略错误。  
  
 **出错时停止**  
 指定在出现错误时应停止处理。  
  
 **错误数**  
 指定应停止处理的错误阈值（如果选择了“出错时停止”）。  
  
 **出错时要执行的操作**  
 指定在达到错误阈值时执行的操作（如果选择了“出错时停止”）。  
  
|“值”|Description|  
|-----------|-----------------|  
|**StopProcessing**|停止处理。|  
|**StopLogging**|停止记录错误。|  
  
 **找不到键**  
 指定在出现“找不到键”错误时执行的操作。 默认情况下，此值为 **ReportAndContinue**。  
  
|“值”|Description|  
|-----------|-----------------|  
|**IgnoreError**|忽略错误并继续处理。|  
|**ReportAndContinue**|报告错误并继续处理。|  
|**ReportAndStop**|报告错误并停止处理。|  
  
 **重复键**  
 指定在出现“重复键”错误时执行的操作。 默认情况下，此值为 **IgnoreError**。  
  
|“值”|Description|  
|-----------|-----------------|  
|**IgnoreError**|忽略错误并继续处理。|  
|**ReportAndContinue**|报告错误并继续处理。|  
|**ReportAndStop**|报告错误并停止处理。|  
  
 **空键转换为未知键**  
 指定在将空键转换为 **UnknownMember** 值后所采取的操作。 默认情况下，此值为 **IgnoreError**。  
  
|“值”|Description|  
|-----------|-----------------|  
|**IgnoreError**|忽略错误并继续处理。|  
|**ReportAndContinue**|报告错误并继续处理。|  
|**ReportAndStop**|报告错误并停止处理。|  
  
 **不允许空键**  
 指定在不允许空键而又遇到空键时执行的操作。 默认情况下，此值为 **ReportAndContinue**。  
  
|“值”|Description|  
|-----------|-----------------|  
|**IgnoreError**|忽略错误并继续处理。|  
|**ReportAndContinue**|报告错误并继续处理。|  
|**ReportAndStop**|报告错误并停止处理。|  
  
 **错误日志路径**  
 键入错误日志的路径，或单击“浏览 (...)”按钮以选择目标。  
  
 **浏览(...)**  
 选择错误日志的路径。  
  
## 另请参阅  
 [Integration Services 错误和消息引用](../../integration-services/integration-services-error-and-message-reference.md)   
 [维度处理目标编辑器（“连接管理器”页）](../../integration-services/data-flow/dimension-processing-destination-editor-connection-manager-page.md)   
 [维度处理目标编辑器（“映射”页）](../../integration-services/data-flow/dimension-processing-destination-editor-mappings-page.md)  
  
  