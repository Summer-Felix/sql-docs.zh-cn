---
title: "使用调色板定义图表上的颜色（报表生成器和 SSRS） | Microsoft Docs"
ms.custom: ""
ms.date: "03/03/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "reporting-services-sharepoint"
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d95efc22-5a32-43d4-9bd2-12753e7fd395
caps.latest.revision: 6
author: "maggiesMSFT"
ms.author: "maggies"
manager: "erikre"
caps.handback.revision: 6
---
# 使用调色板定义图表上的颜色（报表生成器和 SSRS）
  您可以通过选择预定义调色板或定义自定义调色板来更改图表的调色板。 自定义调色板是针对具体报表而言。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### 使用内置调色板更改图表的颜色  
  
1.  打开“属性”窗格。  
  
2.  在设计图面上，单击该图表。 图表对象的属性将显示在“属性”窗格中。  
  
     对象名称（默认为 **Chart1**）将显示在“属性”窗格顶部的下拉列表中。  
  
3.  在“图表”部分，从下拉列表中为 Palette 属性选择新的调色板。  
  
    > [!NOTE]  
    >  您无法更改预定义调色板中的颜色或顺序。  
  
### 使用自定义调色板定义自己的图表颜色  
  
1.  打开“属性”窗格。  
  
2.  在设计图面上，单击该图表。 图表对象的属性将显示在“属性”窗格中。  
  
3.  在 **“图表”** 部分，为 **“调色板”** 属性选择 **“自定义”**。  
  
4.  在 CustomPaletteColors 属性中，单击“编辑集合”(**…**) 按钮。 将打开 **“ReportColorExpression 集合编辑器”** 。  
  
5.  单击 **“添加”** 以添加颜色。 从下拉列表中选择颜色或选择“表达式”并为特定颜色指定十六进制值，例如“橙色”为 ff6600。  
  
     有关十六进制值的更多信息，请参阅 MSDN 上的 [Color Table](http://go.microsoft.com/fwlink/?linkid=9258) （颜色表）。  
  
6.  单击 **“添加”** 以向调色板添加更多颜色。  
  
7.  完成后，单击 **“确定”**。  
  
 如果使用自定义调色板，可更改颜色顺序以调整图表中不同序列的颜色。  
  
## 另请参阅  
 [设置图表上序列颜色的格式（报表生成器和 SSRS）](../../reporting-services/report-design/formatting-series-colors-on-a-chart-report-builder-and-ssrs.md)   
 [图表（报表生成器和 SSRS）](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)   
 [对多个形状图指定一致的颜色（报表生成器和 SSRS）](../../reporting-services/report-design/specify-consistent-colors-across-multiple-shape-charts-report-builder-and-ssrs.md)  
  
  