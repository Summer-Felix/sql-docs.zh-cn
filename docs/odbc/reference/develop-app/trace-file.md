---
title: "跟踪文件 |Microsoft 文档"
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
- trace files [ODBC]
- tracing options [ODBC], trace files
ms.assetid: ec97f949-126f-40a2-b67e-e74520a524cb
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: f14ddeafa35a91dc73a9540a63de805a2e16242f
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="trace-file"></a>跟踪文件
应用程序指定的跟踪文件通过设置**TraceFile**关键字在 Odbc.ini 注册表项中或通过调用**SQLSetConnectAttr**与 SQL_ATTR_TRACEFILE 连接属性。 如果启用跟踪时，该文件不存在，则驱动程序管理器将创建文件。 每个应用程序应具有其自己的专用的跟踪文件，若要避免争用。 应用程序可以使用多个跟踪文件;应用程序的安装程序可以向用户提供一种跟踪文件。 如果动态启用了跟踪，应用程序还可以显示跟踪结果，而不是日志记录到跟踪文件。  
  
 跟踪文件提供的数据类型与每个 ODBC 函数调用的日志和所有参数的值。 它将记录所有输入的函数，并使用返回代码和错误状态记录所有返回的函数。  
  
 ODBC 3 中*.x*，对连接函数的参数不会提供给跟踪 DLL。
