---
title: "MakeValid (geography 数据类型) |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- MakeValid method (geography)
ms.assetid: f67038e3-4f62-4465-994e-e95ac27d8ada
caps.latest.revision: 14
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: ca7928d73b20bfa024466cc580b1958c250c9d8e
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="makevalid-geography-data-type"></a>MakeValid（geography 数据类型）
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

  将转换**geography**实例化为有效无效**geography**与有效的开放地理空间联盟 (OGC) 类型的实例。  
  
 如果输入的对象 STIsValid()，返回 False`MakeValid()`将转换到有效实例无效的实例。  
  
 此 geography 数据类型方法支持**FullGlobe**实例或大于半球的空间实例。  
  
## <a name="syntax"></a>语法  
  
```  
  
.MakeValid ()  
```  
  
## <a name="return-types"></a>返回类型  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]返回类型：**地理位置**  
  
 CLR 返回类型： **SqlGeography**  
  
## <a name="remarks"></a>注释  
 此方法可能会更改的一种**geography**实例。 此外的点**geography**实例可能会稍有变化。 在某些方法，如 NumPoint() 结果可能会更改。  
  
 在情况下，无效的空间实例相交赤道，必须 EnvelopeAngle() = 180， **FullGlobe**将返回实例。 `MakeValid()` **Geography**数据类型方法将使在返回有效的实例的最佳尝试但不是保证结果都是准确或精确。  
  
> [!NOTE]  
>  无效的对象可以存储在数据库中。 可以在无效的实例执行的方法 （哪些 STIsValid() 这些实例返回 False） 是检查有效性或允许导出的方法： STIsValid()、 MakeValid()、 stastext （）、 STAsBinary()、 tostring （）、 AsTextZM() 和 AsGml()。  
  
 此方法不精确。  
  
## <a name="examples"></a>示例  
 第一个示例创建一个与其自身重叠的无效 `LineString` 实例，并使用 `STIsValid()` 来确认该实例是无效实例。 `STIsValid()` 针对无效实例返回值 0。  
  
```  
DECLARE @g geography;  
SET @g = geography::STGeomFromText('LINESTRING(0 2, 1 1, 1 0, 1 1, 2 2)', 4326);  
SELECT @g.STIsValid();  
```  
  
 第二个示例使用 `MakeValid()` 使该实例有效并测试该实例是否的确有效。 `STIsValid()` 针对有效实例返回值 1。  
  
```  
SET @g = @g.MakeValid();  
SELECT @g.STIsValid();  
```  
  
 第三个示例验证是否已将该实例更改为有效实例。  
  
```  
SELECT @g.ToString();  
```  
  
 在此示例中，在选择 `LineString` 实例时，值将作为有效的 `MultiLineString` 实例返回。  
  
```  
MULTILINESTRING ((0 2, 1 1, 2 2), (1 1, 1 0))  
```  
  
## <a name="see-also"></a>另请参阅  
 [STIsValid（geometry 数据类型）](../../t-sql/spatial-geometry/stisvalid-geometry-data-type.md)   
 [地域实例的扩展的方法](../../t-sql/spatial-geography/extended-methods-on-geography-instances.md)  
  
  