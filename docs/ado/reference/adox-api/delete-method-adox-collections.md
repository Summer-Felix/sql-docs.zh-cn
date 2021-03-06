---
title: "Delete 方法 （ADOX 集合） |Microsoft 文档"
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
- Views::Delete
- Groups::Delete
- Indexes::raw_Delete
- Columns::raw_Delete
- Tables::Delete
- Keys::Delete
- Users::Delete
- Users::raw_Delete
- Keys::raw_Delete
- Procedures::raw_Delete
- Views::raw_Delete
- Indexes::Delete
- Procedures::Delete
- Groups::raw_Delete
- Tables::raw_Delete
- Columns::Delete
helpviewer_keywords:
- delete method [ADOX]
ms.assetid: e6b6e3a4-8952-4d79-81f4-51019c338374
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 4efe8d4528d0085d2bef7f97bf9b1958be208547
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="delete-method-adox-collections"></a>Delete 方法 （ADOX 集合）
从集合中移除一个对象。  
  
## <a name="syntax"></a>语法  
  
```  
  
Collection.Delete Name  
```  
  
#### <a name="parameters"></a>Parameters  
 *名称*  
 A **Variant**指定的名称或序号位置 （索引） 的要删除的对象。  
  
## <a name="remarks"></a>注释  
 如果出现错误，将*名称*集合中不存在。  
  
 有关[表](../../../ado/reference/adox-api/tables-collection-adox.md)和[用户](../../../ado/reference/adox-api/users-collection-adox.md)集合，如果将发生错误的提供程序不支持删除表或多个用户分别。 有关[过程](../../../ado/reference/adox-api/procedures-collection-adox.md)和[视图](../../../ado/reference/adox-api/views-collection-adox.md)集合，**删除**如果提供程序不支持保留命令将失败。  
  
## <a name="applies-to"></a>适用范围  
  
||||  
|-|-|-|  
|[列集合 (ADOX)](../../../ado/reference/adox-api/columns-collection-adox.md)|[组集合 (ADOX)](../../../ado/reference/adox-api/groups-collection-adox.md)|[索引集合 (ADOX)](../../../ado/reference/adox-api/indexes-collection-adox.md)|  
|[项集合 (ADOX)](../../../ado/reference/adox-api/keys-collection-adox.md)|[过程集合 (ADOX)](../../../ado/reference/adox-api/procedures-collection-adox.md)|[表集合 (ADOX)](../../../ado/reference/adox-api/tables-collection-adox.md)|  
|[用户集合 (ADOX)](../../../ado/reference/adox-api/users-collection-adox.md)|[视图集合 (ADOX)](../../../ado/reference/adox-api/views-collection-adox.md)||  
  
## <a name="see-also"></a>另请参阅  
 [过程删除方法示例 (VB)](../../../ado/reference/adox-api/procedures-delete-method-example-vb.md)   
 [视图 Delete 方法示例 (VB)](../../../ado/reference/adox-api/views-delete-method-example-vb.md)
