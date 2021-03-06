---
title: "设置光标 |Microsoft 文档"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: odbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scrollable cursors [ODBC]
- cursors [ODBC], scrollable
- cursors [ODBC], creating
ms.assetid: b80afb0e-ef2f-408f-86f5-a392edd99a56
caps.latest.revision: "6"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: b442a732eb16b4047eabe9c507eb5cd5d2887a99
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="setting-up-the-cursor"></a>设置光标
执行语句，以创建结果设置之前，应用程序可以指定游标类型。 具有 SQL_ATTR_CURSOR_TYPE 语句属性做到这一点。 如果应用程序未显式指定类型，则将使用只进游标。 若要获取混合的光标，应用程序指定的键集驱动游标，但声明键集大小小于结果集大小。  
  
 对于游标键集驱动的和混合游标，该应用程序还可以指定的键集大小。 具有 SQL_ATTR_KEYSET_SIZE 语句属性做到这一点。 如果键集大小设置为 0，这是默认设置，键集大小设置为结果集大小，并且使用键集驱动游标。 在打开游标后，可以更改由键集大小。  
  
 应用程序还可以设置大小与行集不同。有关详细信息，请参阅[使用块状游标](../../../odbc/reference/develop-app/using-block-cursors.md)，本部分前面的。
