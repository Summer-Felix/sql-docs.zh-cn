---
title: "setClob 方法 （java.lang.String，java.io.Reader） |Microsoft 文档"
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
ms.assetid: f7457b8a-df31-4999-883e-8cc386a48ceb
caps.latest.revision: "14"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 537a14751fea85904b731a507894f1fd16793a44
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="setclob-method-javalangstring-javaioreader"></a>setClob 方法 (java.lang.String, java.io.Reader)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  将指定的参数设置为指定的读取器对象。  
  
## <a name="syntax"></a>语法  
  
```  
  
public final void setClob(java.lang.String parameterName,  
            java.io.Reader reader)  
```  
  
#### <a name="parameters"></a>Parameters  
 *参数名称*  
  
 A**字符串**，其中包含参数名称。  
  
 *读取器*  
  
 一个读取器对象。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.CallableStatement 接口中的 setClob 方法指定此 setClob 方法。  
  
## <a name="see-also"></a>另请参阅  
 [setClob 方法 &#40;SQLServerCallableStatement &#41;](../../../connect/jdbc/reference/setclob-method-sqlservercallablestatement.md)   
 [SQLServerCallableStatement 成员](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)  
  
  
