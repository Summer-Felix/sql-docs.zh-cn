---
title: "使用嵌套表数据作为准确性图表的输入 | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
  - "analysis-services/data-mining"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "挖掘准确性图表 [Analysis Services], 嵌套表"
  - "挖掘准确性图表 [Analysis Services], 输入表"
  - "嵌套表"
  - "添加嵌套表"
ms.assetid: 162e0686-ada3-4dd3-9151-9589926e6613
caps.latest.revision: 24
author: "Minewiskan"
ms.author: "owend"
manager: "jhubbard"
caps.handback.revision: 24
---
# 使用嵌套表数据作为准确性图表的输入
  在使用外部数据测试挖掘模型的准确性时，如果挖掘模型包含嵌套表，则外部数据也必须包含一个事例表和一个关联的嵌套表。  
  
 本主题说明如何处理用于模型测试的嵌套表、如何在模型和外部数据中映射嵌套表和事例表，以及如何将筛选器应用到嵌套表。  
  
 使用嵌套表时，请记住以下技巧：  
  
-   如果选择 **“使用挖掘模型测试事例”** 或 **“使用挖掘结构测试事例”**选项，则无需指定事例表或嵌套表。 使用这些选项可将测试数据的定义存储在挖掘结构中，且可实现在您创建准确性图表时自动选择测试数据。  
  
-   如果数据源中事例表和嵌套表之间的关系已存在，则挖掘结构中的列将自动映射到输入表中的同名列。  
  
-   只有指定了事例表，才可选择嵌套表。 此外，只有在挖掘模型也使用事例表和嵌套表结构时，才可以指定嵌套表作为输入。  
  
### 使用嵌套表作为准确性图表的输入  
  
1.  双击挖掘结构以在数据挖掘设计器中将其打开。  
  
2.  选择“挖掘准确性图表”  选项卡，然后选择“输入选择”  选项卡。  
  
3.  在 **“选择要用于准确性图表的数据集”**中，选择 **“指定其他数据集”**选项。  
  
4.  单击浏览按钮 **(…)**，从当前服务器上的数据源视图列表中选择外部数据集。  
  
5.  单击“选择事例表” 。 在 **“选择表”** 对话框中，从包含事例数据的数据源视图中选择事例表，然后单击 **“确定”**。  
  
6.  单击 **“选择嵌套表”**。 在 **“选择表”** 对话框中，选择包含嵌套数据的表，然后单击 **“确定”**。  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     如果需要修改嵌套表与事例表之间的关系，请单击 **“修改联接”** 以打开 **“创建关系”** 对话框。  
  
## 另请参阅  
 [选择和映射模型测试数据](../../analysis-services/data-mining/choose-and-map-model-testing-data.md)   
 [将筛选器应用于模型测试数据](../../analysis-services/data-mining/apply-filters-to-model-testing-data.md)  
  
  