---
title: "维护计划（“报告和记录”页）| Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: maintenance-plans
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.swb.maint.reportinglogging.f1
ms.assetid: 3a30b17a-3deb-446f-900a-62f88934a90f
caps.latest.revision: 
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 05d9eac7b81f5a17d5f2b9de71cc0a7027896354
ms.sourcegitcommit: dcac30038f2223990cc21775c84cbd4e7bacdc73
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2018
---
# <a name="maintenance-plan-reporting-and-logging-page"></a>维护计划（“报告和记录”页）
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]使用“报告和记录”对话框可以配置在执行维护计划时生成的报告和日志。  
  
## <a name="options"></a>“常规”  
 **生成文本文件报告**  
 指定是否希望 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 写入文本文件报告。  
  
 **创建新文件**  
 在每次执行维护计划时创建新的报告文件。 默认情况下，报告文件写入到承载包含此维护计划的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例的计算机，具体位置为在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 安装过程中建立的默认日志文件夹。 若要指定其它文件夹，请在“文件夹”文本框中输入该文件夹的完整路径，或单击“浏览”按钮 (**...**) 并导航到所需的文件夹。  
  
 **追加到文件**  
 将每次执行计划所生成的报告追加到在“文件名”文本框中指定的文件。 还可以通过单击浏览按钮并从对话框中选择文件来指定文件。  
  
 **将报告发送给电子邮件收件人**  
 通过电子邮件传输维护计划执行的结果。 只有启用了数据库邮件并进行适当配置后，此选项才可用。  
  
 **代理操作员**  
 从电子邮件收件人列表中选择代理操作员。 只有启用了邮件并进行了正确配置，此选项才可用。  
  
 **记录扩展信息**  
 在日志中包括详细信息。 包括此选项将增大存储的维护计划历史记录的大小。  
  
 **在远程服务器上进行日志记录**  
 将维护计划历史记录记录到远程服务器。  
  
 **“连接”**  
 指定在远程服务器上进行日志记录时使用的连接信息。  
  
 **新建**  
 显示“连接属性”对话框。 用于配置在远程服务器上进行日志记录时使用的新连接信息。  
  
## <a name="see-also"></a>另请参阅  
 [维护计划](../../relational-databases/maintenance-plans/maintenance-plans.md)   
 [数据库邮件](../../relational-databases/database-mail/database-mail.md)  
  
  
