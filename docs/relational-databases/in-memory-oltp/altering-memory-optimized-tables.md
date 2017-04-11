---
title: "更改内存优化表 | Microsoft Docs"
ms.custom: 
  - "SQL2016_New_Updated"
ms.date: "10/04/2016"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine-imoltp"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 690b70b7-5be1-4014-af97-54e531997839
caps.latest.revision: 20
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
caps.handback.revision: 20
---
# 更改内存优化表
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  可以使用 ALTER TABLE 语句来更改内存优化表的架构和索引。 数据库应用程序可以继续运行，并且访问该表的任何操作都将被阻止，直到更改过程完成。  
  
## ALTER TABLE  
 
使用 ALTER TABLE 语法更改表架构，以及添加、删除和重新生成索引。 索引被视为表定义的一部分：  
  
-   语法 ALTER TABLE... 内存优化表仅支持 ADD/DROP/ALTER INDEX。  
  
-   如果不使用 ALTER TABLE 语句，内存优化表上的索引将不支持 CREATE INDEX、DROP INDEX 和 ALTER INDEX 语句。  
  
 以下是 ALTER TABLE 语句上 ADD、DROP 和 ALTER INDEX 字句的语法。  
  
```
| ADD   
     {   
        <column_definition>  
      | <table_constraint>  
      | <table_index>    
     } [ ,...n ]  
  
| DROP   
     {  
         [ CONSTRAINT ]   
         {   
              constraint_name   
         } [ ,...n ]  
         | COLUMN   
         {  
              column_name   
         } [ ,...n ]  
         | INDEX   
         {  
              index_name   
         } [ ,...n ]  
     } [ ,...n ]  
  
| ALTER INDEX index_name  
     {   
         REBUILD WITH ( <rebuild_index_option> )     
     }  
}  
```  
  
 支持下列更改类型。  
  
-   更改桶计数  
  
-   添加和删除索引  
  
-   更改、添加和删除列  
  
-   添加和删除约束  
  
 有关 ALTER TABLE 功能和完整语法的详细信息，请参阅 [ALTER TABLE (Transact-SQL)](../../t-sql/statements/alter-table-transact-sql.md)  
  
## 架构绑定依赖关系  
 本机编译的存储过程都需要绑定到架构，即是说它们对所访问的内存优化表和所引用的列有一种绑定到架构的依赖关系。 架构绑定依赖关系是一种两个实体之间的关系，只要引用实体存在，这种关系就可以防止对被引用的实体进行删除或不兼容地更改。  
  
 例如，如果绑定到架构的本机编译存储过程从表 *mytable* 中引用了 *c1* 列，则*c1* 列不能被删除。 同样，如果一个过程包含一个没有列列表的 INSERT 语句（如 `INSERT INTO dbo.mytable VALUES (...)`），那么表中没有可被删除的列。  
  
## 示例  
 下面的示例将更改现有哈希索引的桶计数。 此操作将重新生成具有新的桶计数的哈希索引，并且哈希索引的其他属性保持不变。  
  
```tsql
ALTER TABLE Sales.SalesOrderDetail_inmem   
       ALTER INDEX imPK_SalesOrderDetail_SalesOrderID_SalesOrderDetailID  
              REBUILD WITH (BUCKET_COUNT=67108864);  
GO
```
  
 下面的示例将添加一个带有 NOT NULL 约束和 DEFAULT 定义的列，并使用 WITH VALUES 为表中的各个现有行提供值。 如果没有使用 WITH VALUES，那么每一行的新列中都将包含 NULL 值。  
  
```tsql  
ALTER TABLE Sales.SalesOrderDetail_inmem  
       ADD Comment NVARCHAR(100) NOT NULL DEFAULT N'' WITH VALUES;  
GO
```  
  
 下面的示例将在现有列中添加一个主键约束。  
  
```tsql
CREATE TABLE dbo.UserSession (   
   SessionId int not null,   
   UserId int not null,   
   CreatedDate datetime2 not null,   
   ShoppingCartId int,   
   index ix_UserId nonclustered hash (UserId) with (bucket_count=400000)   
)   
WITH (MEMORY_OPTIMIZED=ON, DURABILITY=SCHEMA_ONLY) ;  
GO  
  
ALTER TABLE dbo.UserSession  
       ADD CONSTRAINT PK_UserSession PRIMARY KEY NONCLUSTERED (SessionId);  
GO
```  
  
 下面的示例将删除一个索引。  
  
```tsql
ALTER TABLE Sales.SalesOrderDetail_inmem  
       DROP INDEX ix_ModifiedDate;  
GO
```  
  
 下面的示例将添加一个索引。  
  
```tsql  
ALTER TABLE Sales.SalesOrderDetail_inmem  
       ADD INDEX ix_ModifiedDate (ModifiedDate);  
GO  
```  
  
 下面的示例将添加多个包含索引和约束的列。  
  
```tsql
ALTER TABLE Sales.SalesOrderDetail_inmem  
       ADD    CustomerID int NOT NULL DEFAULT -1 WITH VALUES,  
              ShipMethodID int NOT NULL DEFAULT -1 WITH VALUES,  
              INDEX ix_Customer (CustomerID);  
GO  
```


<a name="logging-of-alter-table-on-memory-optimized-tables-124"></a>

## 记录内存优化表上的 ALTER TABLE


在一个内存优化表中，大多数 ALTER TABLE 方案可同时运行，从而优化了向事务日志的写入。 这种优化体现在只将元数据更改写入事务日志。 但是，以下 ALTER TABLE 操作将以单线程运行，而未经过日志优化。

单线程操作要求将更改后的表的全部内容写入日志。 单线程操作的列表如下：

- 更改或添加列以使用大型对象 (LOB) 类型：nvarchar(max)、varchar(max) 或 varbinary(max)。

- 添加或删除列存储索引。

- 几乎所有内容都将影响[行外列](../../relational-databases/in-memory-oltp/supported-data-types-for-in-memory-oltp.md)。

    - 导致行上列移动行外列。

    - 导致行外列移动行上列。

    - 创建新的行外列。

    - *异常：*已使用优化方式记录了延长行外列。


## 另请参阅  

[内存优化表](../../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  