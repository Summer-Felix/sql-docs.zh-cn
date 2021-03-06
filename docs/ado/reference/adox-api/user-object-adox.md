---
title: "用户对象 (ADOX) |Microsoft 文档"
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- User
helpviewer_keywords:
- User object [ADOX]
ms.assetid: f68e32ce-ef7c-407d-bdb5-d280947ae0e2
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 70271f780557a7ad63df504f50962e88113348b1
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="user-object-adox"></a>用户对象 (ADOX)
表示具有受保护的数据库内的访问权限的用户帐户。  
  
## <a name="remarks"></a>注释  
 [用户](../../../ado/reference/adox-api/users-collection-adox.md)集合[目录](../../../ado/reference/adox-api/catalog-object-adox.md)表示目录的所有用户。 **用户**集合[组](../../../ado/reference/adox-api/group-object-adox.md)表示只有特定组的用户。  
  
 与属性、 集合和方法的**用户**对象，你可以：  
  
-   标识与用户[名称](../../../ado/reference/adox-api/name-property-adox.md)属性。  
  
-   更改具有的用户的密码[ChangePassword](../../../ado/reference/adox-api/changepassword-method-adox.md)方法。  
  
-   确定是否用户具有读取、 写入或删除权限[GetPermissions](../../../ado/reference/adox-api/getpermissions-method-adox.md)和[SetPermissions](../../../ado/reference/adox-api/setpermissions-method-adox.md)方法。  
  
-   访问与用户所属组[组](../../../ado/reference/adox-api/groups-collection-adox.md)集合。  
  
-   访问与提供程序特定属性[属性](../../../ado/reference/ado-api/properties-collection-ado.md)集合。  
  
-   确定[ParentCatalog](../../../ado/reference/adox-api/parentcatalog-property-adox.md)用户。  
  
 本部分包含以下主题。  
  
-   [用户对象属性、方法和事件](../../../ado/reference/adox-api/user-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>另请参阅  
 [GetPermissions 和 SetPermissions 方法示例 (VB)](../../../ado/reference/adox-api/getpermissions-and-setpermissions-methods-example-vb.md)   
 [组集合 (ADOX)](../../../ado/reference/adox-api/groups-collection-adox.md)   
 [用户集合 (ADOX)](../../../ado/reference/adox-api/users-collection-adox.md)
