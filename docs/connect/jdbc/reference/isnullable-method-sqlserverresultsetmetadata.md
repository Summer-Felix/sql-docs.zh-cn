---
title: "isNullable 方法 (SQLServerResultSetMetaData) |Microsoft 文档"
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
apiname: SQLServerResultSetMetaData.isNullable
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: c0fce3fe-5b16-4f60-9b0e-e9b30a90525e
caps.latest.revision: "7"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 8211d689c93997139f97fe7c76bcab78f2518c3c
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="isnullable-method-sqlserverresultsetmetadata"></a>isNullable 方法 (SQLServerResultSetMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  指示指定列中的值的为 Null 性。  
  
## <a name="syntax"></a>语法  
  
```  
  
public int isNullable(int column)  
```  
  
#### <a name="parameters"></a>Parameters  
 *列*  
  
 **Int** ，该值指示的列索引。  
  
## <a name="return-value"></a>返回值  
 **true**如果列可以为 null。 否则为 **false**。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.ResultSetMetaData 接口中的 isNullable 方法指定此 isNullable 方法。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerResultSetMetaData 方法](../../../connect/jdbc/reference/sqlserverresultsetmetadata-methods.md)   
 [SQLServerResultSetMetaData 成员](../../../connect/jdbc/reference/sqlserverresultsetmetadata-members.md)   
 [SQLServerResultSetMetaData 类](../../../connect/jdbc/reference/sqlserverresultsetmetadata-class.md)  
  
  
