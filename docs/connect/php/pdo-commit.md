---
title: "Pdo:: commit |Microsoft 文档"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: php
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0db4a00-9700-4f49-ab16-6522dd1101d3
caps.latest.revision: "8"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 52958b4f08a244982d1871d4f2ad5dfe6a1d8ea5
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="pdocommit"></a>PDO::commit
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

将命令发送到调用 [PDO::beginTransaction](../../connect/php/pdo-begintransaction.md) 后发布的数据库，并将连接返回到自动提交模式。  
  
## <a name="syntax"></a>语法  
  
```  
  
bool PDO::commit();  
```  
  
## <a name="return-value"></a>返回值  
如果方法调用成功，则为 True，否则为 False。  
  
## <a name="remarks"></a>注释  
PDO::commit 不受 PDO::ATTR_AUTOCOMMIT 的值影响（也不影响该值）。  
  
有关使用 PDO::commit 的示例，请参阅 [PDO::beginTransaction](../../connect/php/pdo-begintransaction.md) 。  
  
已在 [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]的版本 2.0 中添加了对 PDO 的支持。  
  
## <a name="see-also"></a>另请参阅  
[PDO 类](../../connect/php/pdo-class.md)  
[PDO](http://go.microsoft.com/fwlink/?LinkID=187441)  
  
