---
title: APPLOCK_TEST (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- APPLOCK_TEST_TSQL
- APPLOCK_TEST
dev_langs:
- TSQL
helpviewer_keywords:
- locking [SQL Server], applications
- APPLOCK_TEST function
- applications [SQL Server], locks
- sessions [SQL Server], application locks
- testing application locks
ms.assetid: 4ea33d04-f8e9-46ff-ae61-985bd3eaca2c
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: f4009a151873bf989a39bc4fb91ec3a9963af9f2
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="applocktest-transact-sql"></a>APPLOCK_TEST (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

返回信息指示是否可以为指定锁所有者授予对某种资源的锁而不必获取锁。 APPLOCK_TEST 是应用程序锁函数，它对当前数据库执行操作。 应用程序锁的作用域是数据库。
  
![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>语法  
  
```sql
APPLOCK_TEST ( 'database_principal' , 'resource_name' , 'lock_mode' , 'lock_owner' )  
```  
  
## <a name="arguments"></a>参数  
' database_principal '  
可将对数据库中对象的权限授予它们的用户、角色或应用程序角色。 该函数的调用方必须是 database_principal、dbo 或 db_owner 固定数据库角色的成员，才可成功调用该函数。
  
**'** resource_name **'**  
由客户端应用程序指定的锁资源名称。 应用程序必须确保该资源是唯一的。 指定的名称经过内部哈希运算后成为可以存储在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 锁管理器中的值。 resource_name 为 nvarchar(255)，无默认值。 resource_name 使用二进制比较并区分大小写，无论当前数据库的排序规则设置为何。
  
**'** lock_mode **'**  
要为特定资源获取的锁模式。 lock_mode 是 nvarchar(32)，且无默认值。 该值可以是下列值之一：Shared、Update、IntentShared、IntentExclusive、Exclusive。
  
**'** lock_owner **'**  
锁的所有者，它是请求锁时所指定的 lock_owner 值。 lock_owner 是 nvarchar(32)。 该值可以是 Transaction（默认值）或 Session。 如果显式指定默认值或 Transaction，则必须从事务中执行 APPLOCK_TEST。
  
## <a name="return-types"></a>返回类型
**int**
  
## <a name="return-value"></a>返回值
如果无法将锁授予指定的所有者，则返回 0；如果可以授予锁，则返回 1。
  
## <a name="function-properties"></a>函数属性
**Nondeterministic**
  
**Nonindexable**
  
**Nonparallelizable**
  
## <a name="examples"></a>示例  
在下面的示例中，具有不同会话的两个用户（用户 A 和用户 B）按以下顺序运行 [!INCLUDE[tsql](../../includes/tsql-md.md)] 语句。
  
用户 A 运行：
  
```sql
USE AdventureWorks2012;  
GO  
BEGIN TRAN;  
DECLARE @result int;  
EXEC @result=sp_getapplock  
    @DbPrincipal='public',  
    @Resource='Form1',  
    @LockMode='Shared',  
    @LockOwner='Transaction';  
SELECT APPLOCK_MODE('public', 'Form1', 'Transaction');  
GO  
```  
  
然后用户 B 运行：
  
```sql
Use AdventureWorks2012;  
GO  
BEGIN TRAN;  
SELECT APPLOCK_MODE('public', 'Form1', 'Transaction');  
--Result set: NoLock  
  
SELECT APPLOCK_TEST('public', 'Form1', 'Shared', 'Transaction');  
--Result set: 1 (Lock is grantable.)  
  
SELECT APPLOCK_TEST('public', 'Form1', 'Exclusive', 'Transaction');  
--Result set: 0 (Lock is not grantable.)  
GO  
```  
  
然后用户 A 运行：
  
```sql
EXEC sp_releaseapplock @Resource='Form1', @DbPrincipal='public';  
GO  
```  
  
然后用户 B 运行：
  
```sql
SELECT APPLOCK_TEST('public', 'Form1', 'Exclusive', 'Transaction');  
--Result set: '1' (The lock is grantable.)  
GO  
```  
  
然后用户 A 和用户 B 同时运行：
  
```sql
COMMIT TRAN;  
GO  
```  
  
## <a name="see-also"></a>另请参阅
[APPLOCK_MODE (Transact-SQL)](../../t-sql/functions/applock-mode-transact-sql.md)  
[sp_getapplock (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-getapplock-transact-sql.md)  
[sp_releaseapplock (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-releaseapplock-transact-sql.md)
  
  
