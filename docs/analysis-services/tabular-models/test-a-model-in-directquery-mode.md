---
title: "在 DirectQuery 模式下测试模型 |Microsoft 文档"
ms.custom: 
ms.date: 07/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11260792-ff8b-4d0e-b845-ca210dd3fced
caps.latest.revision: "11"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: ad389541ba4bb964df0c3a0ca7cb08277d1bd1d9
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="test-a-model-in-directquery-mode"></a>在 DirectQuery 模式下测试模型
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]查看用于在每个开发，从设计阶段测试 DirectQuery 模式下的表格模型的选项。  
  
## <a name="test-in-excel"></a>在 Excel 中测试 
  
 在 SSDT 中设计模型时，可使用“在 Excel 中分析”功能来测试针对内存中示例数据集或针对关系数据库的建模决策。  单击“在 Excel 中分析”时，会打开一个对话框，你可在该对话框中指定选项。
 
 ![“在 Excel 中分析”DirectQuery 选项](../../analysis-services/tabular-models/media/analyze-in-excel-directquery-options.png)
 
 如果已打开模型的 DirectQuery 模式，可指定 DirectQuery 连接模式，此时你有两个选择：
 - **示例数据视图** - 此选项下，Excel 的所有查询都将导向至包含一个内存中示例数据集的示例分区。 在你希望确保正确执行度量值、计算列或行级别安全性中的所有 DAX 公式时，此选项非常有用。
 
 - **完整数据视图** - 此选项下，Excel 的所有查询都将发送至 Analysis Services，随后再发送至关系数据库中。 此选项实际上是完全运作的 DirecQuery 模式。
 
 ### <a name="other-clients"></a>其他客户端
 使用“在 Excel 中分析”时，会创建一个 .doc 连接文件。 可使用此文件中的连接字符串信息从其他客户端应用程序连接到模型。 已添加附加参数 DataView=Sample 来指定应连接到示例数据分区的客户端。  
  
## <a name="monitor-query-execution-on-backend-systems-using-xevents-or-sql-profiler"></a>使用 xEvents 或 SQL 事件探查器监视后端系统上的查询执行情况 
 启动连接到 SQL Server 关系数据库的会话跟踪以监视来自表格模型的连接：  
  
-   [使用 SQL Server 扩展事件监视 Analysis Services](../../analysis-services/instances/monitor-analysis-services-with-sql-server-extended-events.md)  
  
-   [使用 SQL Server Profiler 监视 Analysis Services](../../analysis-services/instances/use-sql-server-profiler-to-monitor-analysis-services.md)  
  
 如果使用 Oracle 或 Teradata，请将跟踪监视工具用于这些系统。  
  
  
