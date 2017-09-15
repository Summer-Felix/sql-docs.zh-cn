---
title: "PERCENTILE_CONT (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 10/20/2015
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- PERCENTILE_CONT_TSQL
- PERCENTILE_CONT
dev_langs:
- TSQL
helpviewer_keywords:
- analytic functions, PERCENTILE_CONT
- PERCENTILE_CONT function
ms.assetid: d019419e-5297-4994-97d5-e9c8fc61bbf4
caps.latest.revision: 24
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 424e3ac668bb979a2d30446ff1ecb57346a0e8ac
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="percentilecont-transact-sql"></a>PERCENTILE_CONT (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-all_md](../../includes/tsql-appliesto-ss2012-all-md.md)]

  基于 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 列值的连续分布计算百分位数。 将内插结果，且结果可能不等于列中的任何特定值。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定 &#40;Transact SQL &#41;](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
PERCENTILE_CONT ( numeric_literal )   
    WITHIN GROUP ( ORDER BY order_by_expression [ ASC | DESC ] )  
    OVER ( [ <partition_by_clause> ] )  
```  
  
## <a name="arguments"></a>参数  
 *numeric_literal*  
 要计算的百分位数。 该值必须介于 0.0 和 1.0 之间。  
  
 组内**(** ORDER BY *order_by_expression* [ **ASC** |DESC]**)**  
 指定要排序的数值列表，并计算百分位数。 只有一个*order_by_expression*允许。 表达式的计算结果必须为精确数值类型 (**int**， **bigint**， **smallint**， **tinyint**，**数字**，**位**，**十进制**， **smallmoney**， **money**) 或近似数值类型 (**float**，**实际**)。 不允许其他数据类型。 默认的排序顺序为升序。  
  
 通过**(** \<partition_by_clause > **)**  
 将 FROM 子句生成的结果集划分为数个应用百分位数函数的分区。 有关详细信息，请参阅[OVER 子句 &#40;Transact SQL &#41;](../../t-sql/queries/select-over-clause-transact-sql.md). \<ORDER BY 子句 > 和\<行或 range 子句 > 的转移不在 PERCENTILE_CONT 函数中指定的语法。  
  
## <a name="return-types"></a>返回类型  
 **float(53)**  
  
## <a name="compatibility-support"></a>兼容性支持  
 在兼容级别 110 和更高级别中，WITHIN GROUP 是保留关键字。 有关详细信息，请参阅 [ALTER DATABASE 兼容级别 (Transact-SQL)](../../t-sql/statements/alter-database-transact-sql-compatibility-level.md)。  
  
## <a name="general-remarks"></a>一般备注  
 数据集中的任何 null 都将被忽略。  
  
 PERCENTILE_CONT 具有不确定性。 有关详细信息，请参阅 [Deterministic and Nondeterministic Functions](../../relational-databases/user-defined-functions/deterministic-and-nondeterministic-functions.md)。  
  
## <a name="examples"></a>示例  
  
### <a name="a-basic-syntax-example"></a>A. 基本语法示例  
 下面的示例使用 PERCENTILE_CONT 和 PERCENTILE_DISC 函数找出每个部门内雇员的薪金中值。 请注意，这些函数可能不返回相同的值。 这是因为，PERCENTILE_CONT 内插适当的值，而无论它在数据集中是否存在，而 PERCENTILE_DISC 始终从数据集中返回实际值。  
  
```  
USE AdventureWorks2012;  
  
SELECT DISTINCT Name AS DepartmentName  
      ,PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY ph.Rate)   
                            OVER (PARTITION BY Name) AS MedianCont  
      ,PERCENTILE_DISC(0.5) WITHIN GROUP (ORDER BY ph.Rate)   
                            OVER (PARTITION BY Name) AS MedianDisc  
FROM HumanResources.Department AS d  
INNER JOIN HumanResources.EmployeeDepartmentHistory AS dh   
    ON dh.DepartmentID = d.DepartmentID  
INNER JOIN HumanResources.EmployeePayHistory AS ph  
    ON ph.BusinessEntityID = dh.BusinessEntityID  
WHERE dh.EndDate IS NULL;  
```  
  
 以下为部分结果集。  
  
 `DepartmentName        MedianCont    MedianDisc`  
  
 `--------------------   ----------   ----------`  
  
 `Document Control       16.8269      16.8269`  
  
 `Engineering            34.375       32.6923`  
  
 `Executive              54.32695     48.5577`  
  
 `Human Resources        17.427850    16.5865`  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>示例：[!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]和[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="b-basic-syntax-example"></a>B. 基本语法示例  
 下面的示例使用 PERCENTILE_CONT 和 PERCENTILE_DISC 函数找出每个部门内雇员的薪金中值。 请注意，这些函数可能不返回相同的值。 这是因为，PERCENTILE_CONT 内插适当的值，而无论它在数据集中是否存在，而 PERCENTILE_DISC 始终从数据集中返回实际值。  
  
```  
-- Uses AdventureWorks  
  
SELECT DISTINCT DepartmentName  
,PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY BaseRate)  
    OVER (PARTITION BY DepartmentName) AS MedianCont  
,PERCENTILE_DISC(0.5) WITHIN GROUP (ORDER BY BaseRate)  
    OVER (PARTITION BY DepartmentName) AS MedianDisc  
FROM dbo.DimEmployee;  
  
```  
  
 以下为部分结果集。  
  
 `DepartmentName        MedianCont    MedianDisc`  
  
 `--------------------   ----------   ----------`  
  
 `Document Control       16.826900    16.8269`  
  
 `Engineering            34.375000    32.6923`  
  
 `Human Resources        17.427850    16.5865`  
  
 `Shipping and Receiving 9.250000      9.0000`  
  
## <a name="see-also"></a>另请参阅  
 [PERCENTILE_DISC &#40;Transact SQL &#41;](../../t-sql/functions/percentile-disc-transact-sql.md)  
  
  


