---
title: "使用具有显式架构的 OPENJSON (SQL Server) | Microsoft Docs"
ms.custom: 
  - "SQL2016_New_Updated"
ms.date: "06/02/2016"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-json"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "OPENJSON，具有显式架构"
ms.assetid: 9c1c3bfb-e1ad-4659-b94f-722b0848d5a2
caps.latest.revision: 13
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 12
---
# 使用具有显式架构的 OPENJSON (SQL Server)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  使用具有显式架构的 **OPENJSON** 可返回一个按你在 WITH 子句中指定的格式进行设置的表。  
  
 下面的一些示例展示了如何使用具有显式架构的 **OPENJSON** 。 有关详细信息和更多示例，请参阅 [OPENJSON (Transact-SQL)](../../t-sql/functions/openjson-transact-sql.md)。  
  
## 示例 - 使用 WITH 子句设置输出格式  
 以下查询返回下表中显示的结果。 请注意 AS JSON 子句是如何让值作为 JSON 对象（而不是标量值）在 col5 和 array_element 中返回的。  
  
```tsql  
DECLARE @json NVARCHAR(MAX) =
N'{"someObject":   
   {"someArray":  
     [  
         {"k1": 11, "k2": null, "k3": "text"},  
         {"k1": 21, "k2": "text2", "k4": { "data": "text4" }},  
         {"k1": 31, "k2": 32},  
         {"k1": 41, "k2": null, "k4": { "data": false }}     
      ]  
   }  
}'  
  
SELECT * FROM  
OPENJSON(@json, N'lax $.someObject.someArray')  
WITH ( k1 int,   
       k2 varchar(100),  
       col3 varchar(6) N'$.k3',  
       col4 varchar(10) N'lax $.k4.data',  
       col5 nvarchar(MAX) N'lax $.k4' AS JSON, 
       array_element nvarchar(MAX) N'$' AS JSON  
)  
```  
  
 **结果**  
  
|k1|k2|col3|col4|col5|array_element|  
|--------|--------|----------|----------|----------|--------------------|  
|11|*NULL*|"text"|*NULL*|*NULL*|{"k1": 11, "k2": null, "k3": "text"}|  
|21|"text2"|*NULL*|"text4"|{ "data": "text4" }|{"k1": true, "k2": "text2", "k4": { "data": "text4" } }|  
|31|"32"|*NULL*|*NULL*|*NULL*|{"k1": 31, "k2": 32 }|  
|41|*NULL*|*NULL*|false|{ "data": false }|{"k1": 41, "k2": null,       "k4": { "data": false }    }|  
  
## 示例 - 将 JSON 加载到 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 表中。  
 下面的示例展示了将整个 JSON 对象加载到 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 表中。  
  
```tsql  
declare @json nvarchar(max) = '{  
 "id" : 2,  
 "firstName": "John",  
 "lastName": "Smith",  
 "isAlive": true,  
 "age": 25,  
 "dateOfBirth": "2015-03-25T12:00:00",  
 "spouse": null  
 }';  
  
 INSERT INTO Person  
 SELECT *   
 FROM OPENJSON(@json)  
 WITH (id int,  
       firstName nvarchar(50), lastName nvarchar(50),   
       isAlive bit, age int,  
       dateOfBirth datetime2, spouse nvarchar(50))  
  
```  
  
## 另请参阅  
 [OPENJSON (Transact-SQL)](../../t-sql/functions/openjson-transact-sql.md)  
  
  