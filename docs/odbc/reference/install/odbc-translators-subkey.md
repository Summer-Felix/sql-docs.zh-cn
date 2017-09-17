---
title: "ODBC 转换器子项 |Microsoft 文档"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- translator subkey [ODBC]
- subkeys [ODBC], translator subkey
- registry entries for components [ODBC], translator subkey
ms.assetid: 6b170f1f-e263-4aac-9d49-8d0ca0470ca2
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: dfc34daa6236fa7187c27a204ee16cc47a0de7b0
ms.contentlocale: zh-cn
ms.lasthandoff: 09/09/2017

---
# <a name="odbc-translators-subkey"></a>ODBC 转换器子项
ODBC 转换器子项下的值列表的已安装的转换器。 下表中显示这些值的格式。  
  
|Name|数据类型|data|  
|----------|---------------|----------|  
|*转换器 desc*|REG_SZ|**安装**|  
  
 *转换器 desc*由转换器开发人员定义名称。  
  
 例如，假设用户已经安装了 Microsoft® 代码页转换器和自定义 ASCII 到 EBCDIC 转换器。 ODBC 转换器子项下的值可能如下所示：  
  
```  
MS Code Page Translator: REG_SZ : Installed  
ASCII to EBCDIC: REG_SZ : Installed.  
```