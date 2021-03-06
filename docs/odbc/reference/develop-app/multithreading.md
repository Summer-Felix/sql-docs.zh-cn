---
title: "多线程处理 |Microsoft 文档"
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
- ODBC drivers [ODBC], thread-safe
- thread-safe drivers [ODBC]
- multithreaded applications [ODBC]
ms.assetid: cdfebdf5-12ff-4e28-8055-41f49b77f664
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 72cc8fd918c8ba69a0eb52f9739abeb3728c425d
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading"></a>多线程处理
多线程在操作系统上，驱动程序必须是线程安全的。 也就是说，它必须能够为应用程序在多个线程上使用相同的句柄。 这如何实现是特定于驱动程序，以及有可能驱动程序将进行序列化任何尝试同时在两个不同的线程使用相同的句柄。  
  
 应用程序通常使用多个线程，而不是异步处理。 应用程序创建一个单独的线程、 调用 ODBC 函数时，然后在主线程上继续处理。 而不是无需频繁地轮询异步函数中，使用 SQL_ATTR_ASYNC_ENABLE 语句特性时的情况一样，应用程序可以只需让新创建的线程完成。  
  
 接受语句句柄并在一个线程上运行的函数可以取消通过调用**SQLCancel**使用相同的语句从另一个线程处理。 尽管驱动程序不应序列化的使用**SQLCancel**这种方式，就不能保证调用**SQLCancel**实际上将取消另一个线程上运行的函数。
