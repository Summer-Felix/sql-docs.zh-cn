---
title: "NativeError 属性 (ADO) |Microsoft 文档"
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
- Error::GetNativeError
- Error::get_NativeError
- Error::NativeError
helpviewer_keywords:
- NativeError property [ADO]
ms.assetid: b9b47e57-18a4-4186-aef5-5bd18d7b1d74
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 3a21c2f5fb6e4432ecfd5d98156fa8e856243886
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="nativeerror-property-ado"></a>NativeError 属性 (ADO)
表示的提供程序特定的错误代码给定[错误](../../../ado/reference/ado-api/error-object.md)对象。  
  
## <a name="return-value"></a>返回值  
 返回**长**值，该值指示错误代码。  
  
## <a name="remarks"></a>注释  
 使用**NativeError**属性，以检索特定的数据库特定错误信息**错误**对象。 例如，当对于 OLE DB 使用 Microsoft SQL Server 数据库的 Microsoft ODBC 提供程序，来源于 SQL Server 的本机错误代码将传递通过 ODBC 和 ODBC 提供程序给 ADO **NativeError**属性。  
  
## <a name="applies-to"></a>适用范围  
 [错误对象](../../../ado/reference/ado-api/error-object.md)  
  
## <a name="see-also"></a>另请参阅  
 [描述、 HelpContext、 HelpFile、 NativeError、 数量、 源和 SQLState 属性示例 (VB)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vb.md)   
 [描述、 HelpContext、 HelpFile、 NativeError、 数量、 源和 SQLState 属性示例 （VC + +）](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vc.md)   
