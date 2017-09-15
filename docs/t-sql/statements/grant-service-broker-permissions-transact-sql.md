---
title: "授予 Service Broker 权限 (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 06/10/2016
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
- granting permissions [SQL Server], Service Broker
- routes [Service Broker], permissions
- Service Broker, permissions
- GRANT statement, Service Broker
- remote service bindings [Service Broker], permissions
- message types [Service Broker], permissions
- contracts [Service Broker], permissions
ms.assetid: c5579976-97c4-4123-be0c-d0b98a9e38fb
caps.latest.revision: 17
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 185950b1872ca5f11663f3d5051d1a2303cce090
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="grant-service-broker-permissions-transact-sql"></a>GRANT Service Broker 权限 (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  授予对 Service Broker 约定、消息类型、远程绑定、路由或服务的权限。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
GRANT permission  [ ,...n ] ON  
    {    
              [ CONTRACT :: contract_name ]   
       | [ MESSAGE TYPE :: message_type_name ]    
       | [ REMOTE SERVICE BINDING :: remote_binding_name ]    
       | [ ROUTE :: route_name ]   
       | [ SERVICE :: service_name ]      
    }  
    TO database_principal [ ,...n ]   
    [ WITH GRANT OPTION ]  
        [ AS granting_principal ]  
```  
  
## <a name="arguments"></a>参数  
 *权限*  
 指定可对 Service Broker 安全对象授予的权限。  如下所列。  
  
 协定**::***contract_name*  
 指定将对其授予权限的约定。 作用域限定符"::"是必需的。  
  
 消息类型**::***message_type_name*  
 指定将对其授予权限的消息类型。 需要使用作用域限定符“::”。  
  
 远程服务绑定**::***remote_binding_name*  
 指定将对其授予权限的远程服务绑定。 需要使用作用域限定符“::”。  
  
 路由**::***route_name*  
 指定将对其授予权限的路由。 需要使用作用域限定符“::”。  
  
 服务**::***service_name*  
 指定将对其授予权限的服务。 需要使用作用域限定符“::”。  
  
 *database_principal*  
 指定要向其授予权限的主体。 可以是以下类型之一：  
  
-   数据库用户  
  
-   数据库角色  
  
-   应用程序角色  
  
-   映射到 Windows 登录名的数据库用户  
  
-   映射到 Windows 组的数据库用户  
  
-   映射到证书的数据库用户  
  
-   映射到非对称密钥的数据库用户  
  
-   未映射到服务器主体的数据库用户。  
  
 GRANT OPTION  
 指示该主体还可以向其他主体授予所指定的权限。  
  
 *granting_principal*  
 指定一个主体，执行该查询的主体从该主体获得授予该权限的权利。 可以是以下类型之一：  
  
-   数据库用户  
  
-   数据库角色  
  
-   应用程序角色  
  
-   映射到 Windows 登录名的数据库用户  
  
-   映射到 Windows 组的数据库用户  
  
-   映射到证书的数据库用户  
  
-   映射到非对称密钥的数据库用户  
  
-   未映射到服务器主体的数据库用户。  
  
## <a name="remarks"></a>注释  
  
## <a name="service-broker-contracts"></a>Service Broker 约定  
 Service Broker 约定是一个数据库级的安全对象，包含于权限层次结构中作为其父级的数据库中。 下面列出了可对 Service Broker 约定授予的最特定、最有限的权限，以及暗含这些权限的更一般的权限。  
  
|Service Broker 约定权限|Service Broker 约定权限隐含的权限|数据库权限隐含的权限|  
|----------------------------------------|---------------------------------------------------|------------------------------------|  
|CONTROL|CONTROL|CONTROL|  
|TAKE OWNERSHIP|CONTROL|CONTROL|  
|ALTER|CONTROL|ALTER ANY CONTRACT|  
|REFERENCES|CONTROL|REFERENCES|  
|VIEW DEFINITION|CONTROL|VIEW DEFINITION|  
  
## <a name="service-broker-message-types"></a>Service Broker 消息类型  
 Service Broker 消息类型是一个数据库级的安全对象，包含于权限层次结构中作为其父级的数据库中。 下面列出了可对 Service Broker 消息类型授予的最特定、最有限的权限，以及暗含这些权限的更一般的权限。  
  
|Service Broker 消息类型权限|Service Broker 消息类型权限隐含的权限|数据库权限隐含的权限|  
|--------------------------------------------|-------------------------------------------------------|------------------------------------|  
|CONTROL|CONTROL|CONTROL|  
|TAKE OWNERSHIP|CONTROL|CONTROL|  
|ALTER|CONTROL|ALTER ANY MESSAGE TYPE|  
|REFERENCES|CONTROL|REFERENCES|  
|VIEW DEFINITION|CONTROL|VIEW DEFINITION|  
  
## <a name="service-broker-remote-service-bindings"></a>Service Broker 远程服务绑定  
 Service Broker 远程服务绑定是一个数据库级的安全对象，包含于权限层次结构中作为其父级的数据库中。 下面列出了可对 Service Broker 远程服务绑定授予的最特定、最有限的权限，以及暗含这些权限的更一般的权限。  
  
|Service Broker 远程服务绑定权限|Service Broker 远程服务绑定权限隐含的权限|数据库权限隐含的权限|  
|------------------------------------------------------|-----------------------------------------------------------------|------------------------------------|  
|CONTROL|CONTROL|CONTROL|  
|TAKE OWNERSHIP|CONTROL|CONTROL|  
|ALTER|CONTROL|ALTER ANY REMOTE SERVICE BINDING|  
|VIEW DEFINITION|CONTROL|VIEW DEFINITION|  
  
## <a name="service-broker-routes"></a>Service Broker 路由  
 Service Broker 路由是一个数据库级的安全对象，包含于权限层次结构中作为其父级的数据库中。 下面列出了可对 Service Broker 路由授予的最特定、最有限的权限，以及暗含这些权限的更一般的权限。  
  
|Service Broker 路由权限|Service Broker 路由权限隐含的权限|数据库权限隐含的权限|  
|-------------------------------------|------------------------------------------------|------------------------------------|  
|CONTROL|CONTROL|CONTROL|  
|TAKE OWNERSHIP|CONTROL|CONTROL|  
|ALTER|CONTROL|ALTER ANY ROUTE|  
|VIEW DEFINITION|CONTROL|VIEW DEFINITION|  
  
### <a name="service-broker-services"></a>Service Broker 服务  
 Service Broker 服务是一个数据库级的安全对象，包含于权限层次结构中作为其父级的数据库中。 下面列出了可对 Service Broker 服务授予的最特定、最有限的权限，以及暗含这些权限的更一般的权限。  
  
|Service Broker 服务权限|Service Broker 服务权限隐含的权限|数据库权限隐含的权限|  
|---------------------------------------|--------------------------------------------------|------------------------------------|  
|CONTROL|CONTROL|CONTROL|  
|TAKE OWNERSHIP|CONTROL|CONTROL|  
|SEND|CONTROL|CONTROL|  
|ALTER|CONTROL|ALTER ANY SERVICE|  
|VIEW DEFINITION|CONTROL|VIEW DEFINITION|  
  
## <a name="permissions"></a>Permissions  
 授权者（或用 AS 选项指定的主体）必须具有带 GRANT OPTION 的相同权限，或具有隐含所授予权限的更高权限。  
  
 如果使用 AS 选项，还必须满足以下附加要求：  
  
|AS *granting_principal*|所需的其他权限|  
|------------------------------|------------------------------------|  
|数据库用户|针对用户、 中的成员身份的 IMPERSONATE 权限**db_securityadmin**固定的数据库角色、 中的成员身份**db_owner**固定数据库角色或中的成员身份**sysadmin**固定的服务器角色。|  
|映射到 Windows 登录名的数据库用户|针对用户、 中的成员身份的 IMPERSONATE 权限**db_securityadmin**固定的数据库角色、 中的成员身份**db_owner**固定数据库角色或中的成员身份**sysadmin**固定的服务器角色。|  
|映射到 Windows 组的数据库用户|中的 Windows 组中中的成员身份的成员身份**db_securityadmin**固定的数据库角色、 中的成员身份**db_owner**固定数据库角色或中的成员身份**sysadmin**固定的服务器角色。|  
|映射到证书的数据库用户|中的成员身份**db_securityadmin**固定的数据库角色、 中的成员身份**db_owner**固定数据库角色或中的成员身份**sysadmin**固定的服务器角色。|  
|映射到非对称密钥的数据库用户|中的成员身份**db_securityadmin**固定的数据库角色、 中的成员身份**db_owner**固定数据库角色或中的成员身份**sysadmin**固定的服务器角色。|  
|未映射到任何服务器主体的数据库用户|针对用户、 中的成员身份的 IMPERSONATE 权限**db_securityadmin**固定的数据库角色、 中的成员身份**db_owner**固定数据库角色或中的成员身份**sysadmin**固定的服务器角色。|  
|数据库角色|在角色中的成员身份的 ALTER 权限**db_securityadmin**固定的数据库角色、 中的成员身份**db_owner**固定数据库角色或中的成员身份**sysadmin**固定的服务器角色。|  
|应用程序角色|在角色中的成员身份的 ALTER 权限**db_securityadmin**固定的数据库角色、 中的成员身份**db_owner**固定数据库角色或中的成员身份**sysadmin**固定的服务器角色。|  
  
 对象所有者可以授予对其所拥有的对象的权限。 对某安全对象具有 CONTROL 权限的主体可以授予对该安全对象的权限。  
  
 被授权者的 CONTROL SERVER 权限，例如成员**sysadmin**固定的服务器角色，可以授予任何权限上任何服务器中安全对象。 数据库，如的成员拥有 CONTROL 权限的被授权者**db_owner**固定的数据库角色，可以授予任何权限对任何数据库中安全对象。 被授权 CONTROL 权限的用户可以授予对相应架构中任一个对象的任意权限。  
  
## <a name="see-also"></a>另请参阅  
 [SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md)   
 [GRANT (Transact-SQL)](../../t-sql/statements/grant-transact-sql.md)   
 [权限（数据库引擎）](../../relational-databases/security/permissions-database-engine.md)   
 [主体（数据库引擎）](../../relational-databases/security/authentication-access/principals-database-engine.md)  
  
  
