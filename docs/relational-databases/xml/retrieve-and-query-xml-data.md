---
title: "检索和查询 XML 数据 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-xml"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "XML 数据 [SQL Server], 检索"
  - "XML 实例检索"
ms.assetid: 24a28760-1225-42b3-9c89-c9c0332d9c51
caps.latest.revision: 15
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 14
---
# 检索和查询 XML 数据
  本主题说明查询 XML 数据必须指定的查询选项。 它还说明了当 XML 实例存储在数据库中时未保留的部分。  
  
##  <a name="features"></a> 未保留的 XML 实例的功能  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 可保留 XML 实例的内容，但不会保留 XML 数据模型中认为是不重要的 XML 实例的某些方面。 这意味着检索到的 XML 实例可能与服务器中存储的实例不相同，但将包含同样的信息。  
  
### XML 声明  
 当将某个实例存储在数据库中时，不会保留该实例中的 XML 声明。 例如：  
  
```  
CREATE TABLE T1 (Col1 int primary key, Col2 xml)  
GO  
INSERT INTO T1 values (1, '<?xml version="1.0" encoding="windows-1252" ?><doc></doc>')  
GO  
SELECT Col2  
FROM T1  
```  
  
 结果为 `<doc/>`。  
  
 当在 `<?xml version='1.0'?>`数据类型实例中存储 XML 数据时，不会保留 XML 声明（如 **xml** ）。 这是设计的结果。 XML 声明 () 及其属性 (version/encoding/stand-alone) 在数据被转换为 **xml** 类型后将丢失。 XML 声明被视为对 XML 分析器的指令。 XML 数据在内部存储为 ucs-2。 XML 实例中所有其他 PI 均被保留。  
  
 [本主题内容](#top)  
  
### 属性的顺序  
 不保留 XML 实例中的属性顺序。 查询存储在 **xml** 类型列中的 XML 实例时，所得 XML 中的属性顺序可能与原 XML 实例中的顺序不同。  
  
 [本主题内容](#top)  
  
### 属性值前后的引号  
 不保留属性值前后的单引号和双引号。 属性值作为名称和值对存储在数据库中。 不存储引号。 对 XML 实例执行 XQuery 时，将用属性值前后的双引号对所得 XML 进行序列化。  
  
```  
DECLARE @x xml  
-- Use double quotation marks.  
SET @x = '<root a="1" />'  
SELECT @x  
GO  
DECLARE @x xml  
-- Use single quotation marks.  
SET @x = '<root a=''1'' />'  
SELECT @x  
GO  
```  
  
 两个查询都返回 `<root a="1" />`。  
  
 [本主题内容](#top)  
  
### 命名空间前缀  
 不保留命名空间前缀。 对 **xml** 类型列指定 XQuery 时，序列化的 XML 结果可能会返回不同的命名空间前缀。  
  
```  
DECLARE @x xml  
SET @x = '<ns1:root xmlns:ns1="abc" xmlns:ns2="abc">  
            <ns2:SomeElement/>  
          </ns1:root>'  
SELECT @x  
SELECT @x.query('/*')  
GO  
```  
  
 结果中的命名空间前缀可能会有所不同。 例如：  
  
```  
<p1:root xmlns:p1="abc"><p1:SomeElement/></p1:root>  
```  
  
 [本主题内容](#top)  
  
##  <a name="query"></a> 设置所需的查询选项  
 当使用 **xml** 数据类型方法查询 **xml** 类型列或变量时，以下选项必须按照所显示的内容进行设置。  
  
|SET 选项|所需值|  
|-----------------|---------------------|  
|ANSI_NULLS|ON|  
|ANSI_PADDING|ON|  
|ANSI_WARNINGS|ON|  
|ARITHABORT|ON|  
|CONCAT_NULL_YIELDS_NULL|ON|  
|NUMERIC_ROUNDABORT|OFF|  
|QUOTED_IDENTIFIER|ON|  
  
 如果这些选项未按照此处所示进行设置，则对 **xml** 数据类型方法的查询和修改将失败。  
  
 [本主题内容](#top)  
  
## 另请参阅  
 [创建 XML 数据的实例](../../relational-databases/xml/create-instances-of-xml-data.md)  
  
  