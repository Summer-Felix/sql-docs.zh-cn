---
title: "getShort 方法 (java.lang.String) |Microsoft 文档"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: jdbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname: SQLServerCallableStatement.getShort (java.lang.String)
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: cd39ed03-b3e8-443d-9c7a-e8cf2581e581
caps.latest.revision: "10"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 4055b0cb4e925579a6a3416099d027f2d6ad5159
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="getshort-method-javalangstring"></a>getShort 方法 (java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  检索与指定参数的值**短**java 编程语言提供的参数名称。  
  
## <a name="syntax"></a>语法  
  
```  
  
public short getShort(java.lang.String sCol)  
```  
  
#### <a name="parameters"></a>Parameters  
 *sCol*  
  
 A**字符串**，其中包含参数名称。  
  
## <a name="return-value"></a>返回值  
 A**短**值。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.CallableStatement 接口中的 getShort 方法指定此 getShort 方法。  
  
 此方法仅支持在[!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]可以安全地返回如 smallint、 tinyint 和位的整数值的数据类型。 在任何其他数据类型上使用此方法会引发异常。  
  
## <a name="see-also"></a>另请参阅  
 [getShort 方法 &#40;SQLServerCallableStatement &#41;](../../../connect/jdbc/reference/getshort-method-sqlservercallablestatement.md)   
 [SQLServerCallableStatement 成员](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [SQLServerCallableStatement 类](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  
