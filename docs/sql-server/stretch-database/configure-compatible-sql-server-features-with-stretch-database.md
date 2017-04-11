---
title: "配置与 Stretch Database 兼容的 SQL Server 功能 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.service: "sql-server-stretch-database"
ms.suite: ""
ms.technology: 
  - "dbe-stretch"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c8121ede-1aec-459b-b7b0-1408bb3e62fb
caps.latest.revision: 4
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 4
---
# 配置与 Stretch Database 兼容的 SQL Server 功能
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

执行简单步骤来配置以下 SQL Server 功能，以使用 Stretch Database。
-   AlwaysOn
-   始终加密
-   透明数据加密 (TDE)
-   临时表

## 对 Stretch Database 配置 AlwaysOn
如果将 AlwaysOn 与 Stretch Database 一起使用，则必须确保数据库主密钥在次要副本上可用。 Stretch Database 使用数据库主密钥保护用于连接到远程 Azure 数据库的凭据。

设置了 AlwaysOn 可用性组之后，对每个次要副本运行存储过程 **sp_control_dbmasterkey_password**，并为已启用延伸的数据库提供密码。 有关详细信息和示例，请参阅 [sp_control_dbmasterkey_password](../../relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql.md)。 

## 对 Stretch Database 配置始终加密
如果要一起使用始终加密和 Stretch Database，则必须在对表启用 Stretch Database 之前，对所选列配置加密。

如果已对表启用了 Stretch Database，并且要使用始终加密列，则必须执行以下操作。
1.   对表禁用 Stretch Database 并从 Azure 返回远程数据。 有关详细信息，请参阅[禁用 Stretch Database 并恢复远程数据](../../sql-server/stretch-database/disable-stretch-database-and-bring-back-remote-data.md)。
2.   对所选列配置始终加密。
3. 对表重新启用 Stretch Database。 有关详细信息，请参阅 [Enable Stretch Database for a database](../../sql-server/stretch-database/enable-stretch-database-for-a-table.md)。

## 对 Stretch Database 配置透明数据加密 (TDE)

如果在本地数据库上启用了 TDE，则不会在 Stretch database 远程终结点上自动启用它。 必须记住在对数据库启用拉伸之后，对远程终结点启用 TDE。

## 对 Stretch Database 配置临时表
如果使用临时表，则可以对历史记录表（但不能对当前表）启用 Stretch Database。
-   有关将临时表与 Stretch Database 结合使用的指南，请参阅[管理版本由系统控制的临时表中历史数据的保留期](../../relational-databases/tables/manage-retention-of-historical-data-in-system-versioned-temporal-tables.md)。
-   若要使用滑动窗口筛选要从历史记录表迁移的行，请参阅[使用筛选器函数选择要迁移的行](../../sql-server/stretch-database/select-rows-to-migrate-by-using-a-filter-function-stretch-database.md)。