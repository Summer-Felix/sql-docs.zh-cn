---
title: "&gt;=（大于或等于）（SSIS 表达式） | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "<=（小于或等于运算符）"
  - "大于或等于 (>=)"
ms.assetid: 52ad504d-2f54-44de-b5e2-620577c0e289
caps.latest.revision: 50
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 50
---
# &gt;=（大于或等于）（SSIS 表达式）
  执行比较来确定第一个表达式是否大于或等于第二个表达式。 在执行比较前表达式计算器会自动转换多种数据类型。  
  
> [!NOTE]  
>  该运算符不支持对使用 DT_TEXT、DT_NTEXT 或 DT_IMAGE 数据类型的表达式进行比较。  
  
 但是，某些数据类型要求表达式包括显式转换，才能成功进行计算。 有关数据类型之间的合法转换的详细信息，请参阅[转换（SSIS 表达式）](../../integration-services/expressions/cast-ssis-expression.md)。  
  
> [!NOTE]  
>  此运算符的两个字符之间没有空格。  
  
## 语法  
  
```  
  
expression1 >= expression2  
  
```  
  
## 参数  
 *expression1、expression2*  
 为任意有效的表达式。  
  
## 结果类型  
 DT_BOOL  
  
## 注释  
 如果比较中的任一表达式为空，则比较结果为空。 如果两个表达式都为空，则结果为空。  
  
 表达式集， *expression1* 和 *expression2*，必须遵守下列规则之一：  
  
-   **Numeric**   *expression1* 和 *expression2* 必须为数值数据类型。 数据类型的交集必须为数值数据类型，该类型在表达式计算器执行隐式数值转换的规则中指定。 两个数值数据类型的交集不能为空。 有关详细信息，请参阅 [Integration Services Data Types in Expressions](../../integration-services/expressions/integration-services-data-types-in-expressions.md)。  
  
-   **Character**：*expression1* 和 *expression2* 的计算结果必须为 DT_STR 或 DT_WSTR 数据类型。 两个表达式的计算结果可以为不同的字符串数据类型。  
  
    > [!NOTE]  
    >  字符串比较区分大小写、重音、假名和全半角。  
  
-   **Date、Time 或 Date/Time** *expression1* 和 *expression2* 的计算结果必须为下列数据类型之一：DT_DBDATE、DT_DATE、DT_DBTIME、DT_DBTIME2、DT_DBTIMESTAMP、DT_DBTIMESTAMP2、DT_DBTIMESTAPMOFFSET 或 DT_FILETIME。  
  
    > [!NOTE]  
    >  系统不支持对计算结果为时间数据类型的表达式和计算结果为日期或日期/时间数据类型的表达式进行比较。 否则系统会生成错误。  
  
     在对表达式进行比较时，系统会按照所列出的顺序应用下面的转换规则：  
  
    -   当两个表达式的计算结果为同一个数据类型时，则会执行该数据类型的比较。  
  
    -   如果一个表达式是 DT_DBTIMESTAMPOFFSET 数据类型，则另一个表达式会隐式转换为 DT_DBTIMESTAMPOFFSET，并执行 DT_DBTIMESTAMPOFFSET 比较。 有关详细信息，请参阅 [Integration Services Data Types in Expressions](../../integration-services/expressions/integration-services-data-types-in-expressions.md)。  
  
    -   如果一个表达式是 DT_DBTIMESTAMP2 数据类型，则另一个表达式会隐式转换为 DT_DBTIMESTAMP2，并执行 DT_DBTIMESTAMP2 比较。  
  
    -   如果一个表达式是 DT_DBTIME2 数据类型，则另一个表达式会隐式转换为 DT_DBTIME2，并执行 DT_DBTIME2 比较。  
  
    -   如果一个表达式是 DT_DBTIMESTAMPOFFSET、DT_DBTIMESTAMP2 或 DT_DBTIME2 以外的类型，那么，在对表达式进行比较之前，会将它们转换为 DT_DBTIMESTAMP 数据类型。  
  
     在对表达式进行比较时，系统会进行如下假设：  
  
    -   如果每个表达式的数据类型都包含小数秒，则系统会假设对于小数秒位数最少的数据类型，用零填充其余位。  
  
    -   如果每个表达式都是日期数据类型，但是只有一个表达式具有时区偏移量，系统会假设没有时区偏移量的日期数据类型采用的是协调世界时 (UTC)。  
  
 有关数据类型的详细信息，请参阅 [Integration Services Data Types](../../integration-services/data-flow/integration-services-data-types.md)。  
  
## 表达式示例  
 如果当前日期为 2003 年 7 月 4 日或更早，则此示例的计算结果为 TRUE。 有关详细信息，请参阅 [GETDATE（SSIS 表达式）](../../integration-services/expressions/getdate-ssis-expression.md)。  
  
```  
"7/4/2003" >= GETDATE()  
```  
  
 如果 **ListPrice** 列中的值大于或等于 500，则示例的计算结果为 TRUE。  
  
```  
ListPrice >= 500  
```  
  
 此示例使用了变量 **LPrice**。 如果 **LPrice** 的值大于或等于 500，则此示例的计算结果为 TRUE。 该变量的数据类型必须为数值以便分析表达式。  
  
```  
@LPrice >= 500  
```  
  
## 另请参阅  
 [>（大于）（SSIS 表达式）](../../integration-services/expressions/greater-than-ssis-expression.md)   
 [>（小于）（SSIS 表达式）](../../integration-services/expressions/less-than-ssis-expression.md)   
 [<=（小于或等于）（SSIS 表达式）](../../integration-services/expressions/less-than-or-equal-to-ssis-expression.md)   
 [运算符优先级和结合性](../../integration-services/expressions/operator-precedence-and-associativity.md)   
 [运算符（SSIS 表达式）](../../integration-services/expressions/operators-ssis-expression.md)  
  
  