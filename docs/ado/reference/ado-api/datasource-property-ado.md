---
title: "数据源属性 (ADO) |Microsoft 文档"
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
- Recordset20::DataSource
helpviewer_keywords:
- DataSource property [ADO]
ms.assetid: 300a702a-3544-48c5-b759-83b511fe97e0
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: ecdaaeab8b09f392e5f21f365b082872e20efbfc
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="datasource-property-ado"></a>数据源属性 (ADO)
表示包含数据表示为对象[记录集](../../../ado/reference/ado-api/recordset-object-ado.md)对象。  
  
## <a name="remarks"></a>注释  
 此属性用于与数据环境中创建数据绑定控件。 数据环境负责维护的包含的数据 （数据源） 的集合命名对象 （数据成员） 将表示为**记录集**对象*。*  
  
 [DataMember](../../../ado/reference/ado-api/datamember-property.md)和**数据源**属性必须结合使用。  
  
 所引用的对象必须实现**IDataSource**接口，并在必须包含**IRowset**接口。  
  
## <a name="usage"></a>用法  
  
```  
Dim rs as New ADODB.Recordset  
rs.DataMember = "Command"     'Name of the rowset to bind to.  
Set rs.DataSource = myDE      'Name of the object containing an IRowset.  
```  
  
## <a name="applies-to"></a>适用范围  
 [记录集对象 (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>另请参阅  
 [DataMember 属性](../../../ado/reference/ado-api/datamember-property.md)
