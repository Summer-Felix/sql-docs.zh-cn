---
title: "维护计划（“设计”选项卡） | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.swb.maint.maintplanproperties.optimizations.f1"
  - "sql13.swb.maint.planeditor.f1"
  - "sql13.swb.maint.subplaneditor.f1"
ms.assetid: 6d20d4d4-5b3f-454a-8a05-f0aac803c5ad
caps.latest.revision: 27
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 27
---
# 维护计划（“设计”选项卡）
  使用**维护计划（“设计”选项卡）**可以指定维护计划及其子计划的属性。 将任务从工具箱拖到计划设计器中。 右键单击任务组以创建分支执行路径。 维护计划将另存为 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 包，它们由 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 代理作业执行。  
  
## 选项  
 **添加子计划**  
 添加可以配置的子计划。  
  
 **子计划属性**  
 显示“子计划属性”对话框。 在网格中选择子计划，单击此图标为该子计划输入名称、说明和计划。 还可以在网格中双击该子计划，以显示“子计划属性”对话框。 子计划的名称限制在 128 个字符以内，子计划的说明限制在 512 个字符以内。  
  
 **删除所选子计划**  
 删除所选子计划。  
  
 **子计划的计划**  
 显示“作业计划属性”对话框。 在网格中选择子计划，单击此图标可配置该子计划的计划。  
  
 **删除计划**  
 从所选子计划中删除计划。  
  
 **管理连接**  
 显示“管理连接”对话框。 用于向维护计划添加其他 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例连接。 子计划编辑器中的每一个维护任务都可以使用其中的任何连接。 在执行时，维护计划会使用连接凭据，建立从维护计划服务器到指定 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 服务器的连接。  
  
 **报告和记录**  
 显示“报告和记录”对话框，用于管理关于维护计划活动的报告，并配置是在本地服务器还是在远程服务器上进行日志记录。  
  
 **服务器**  
 显示“服务器”对话框，用于选择要运行子计划中的任务的服务器。 此选项仅在多服务器环境中的主服务器上启用。 有关详细信息，请参阅[创建多服务器环境](../../ssms/agent/create-a-multiserver-environment.md)。  
  
 **名称**  
 显示维护计划的名称。 对于新建的维护计划，该名称是在打开维护计划设计器之前在一个对话框中指定的。 若要重命名维护计划，请在对象资源管理器中右键单击该计划，再单击“重命名”。  
  
 **说明**  
 查看或指定维护计划的说明。 说明的最大长度为 512 个字符。  
  
 **设计器图面**  
 设计和维护维护计划。 使用设计器图面，可以向计划中添加维护任务、从计划中删除任务、指定任务之间的优先链接以及指示任务分支和并行情况。  
  
 两个任务之间的优先链接会在任务之间建立关系。 只有当第一项任务（前置任务）的执行结果与指定的条件相匹配时，才执行第二项任务（依赖任务）。 通常，指定的执行结果为 **“成功”**、 **“失败”**或 **“完成”**。 维护计划设计器图面基于 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 设计器图面。 有关详细信息，请参阅 [Precedence Constraints](../../integration-services/control-flow/precedence-constraints.md)。  
  
 例如，可以将“索引碎片整理”任务指定为只在上一个“检查数据库完整性”任务成功完成之后才能执行。 使用任务优先关联功能，您还可以在计划中处理错误或失败条件。 例如，如果“检查数据库完整性”任务失败，则“通知操作员”任务可以通知用户或操作员有关失败的消息。  
  
 “任务分支” 示例：指定任务在前置任务失败后执行。  
  
 “任务并行” 示例：指定两项或多项任务在前置任务成功完成后同时开始执行。 没有约束的所有任务将并行开始和运行。 使用约束可以延迟任务，以便让较早的任务首先完成。  
  
 在将维护任务放在设计图面上之后，可以根据需要编辑其属性。 例如，在将“备份数据库”任务添加到计划中之后，可以指定要在该任务中备份的特定数据库。 设计图面上未正确配置的任务包含一个带有白色 x 的红色图标。  
  
 若要将维护任务添加到计划中，请从“维护计划任务”工具箱中将该任务的图标拖到计划设计图面上，或者在该工具箱中双击该任务，从而将该任务添加到当前活动的设计器图面上。 如果 **“维护计划中的任务”** 工具箱不可见，请从 **的** “视图” [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **“工具箱”** 。 在 **“工具箱”** 窗格中展开 **“维护计划中的任务”** 节点。  
  
 若要从计划中删除某项任务，请在设计器图面中选择该任务，按“DELETE”键，或者右键单击该任务，再单击“删除”。  
  
 若要在两项任务之间指定优先链接，请首先将这两项任务拖到设计图面上，然后单击首先出现的任务（前置任务），再将箭头拖到依赖任务。 在建立了优先链接之后，设计器会显示一个链接这两个任务的箭头（从前置任务指向依赖任务）。 默认情况下，在建立链接后，将设置对该链接的约束，以保证只有在前置任务的执行结果为 **“成功”**时才会执行依赖任务。  
  
 若要更改优先链接的属性，请双击该链接以启动“优先约束编辑器”。 此编辑器提供了多种选项，用来指定逻辑条件以确定是否执行依赖任务。 例如，可以将 **“执行结果”** 设置为 **“失败”**，在此情况下，只有当前置任务失败时才会执行依赖任务。 通过右键单击链接，然后从上下文菜单上选择“成功”、“失败”或“完成”，还可以修改该链接的执行结果属性。  
  
 若要指定任务分支，请首先在两个任务之间创建优先链接。 然后，将另外一个依赖任务放到设计图面上，针对与第一个依赖任务不同的结果执行该任务。 单击前置任务，然后将第二个箭头从前置任务拖到该依赖任务。 若要更改触发依赖任务开始执行的执行结果（“成功”、“失败”或“完成”），请双击链接箭头，然后修改“执行结果”字段。 或者，右键单击链接，然后从快捷菜单上选择所需的执行结果值。  
  
 若要指定任务并行，请将两个或多个依赖任务链接到单个前置任务。 修改优先链接的属性，对于指向并行运行的依赖任务的链接，执行结果字段具有相同的值。  
  
## 快捷菜单上可用的其他功能  
 若要查看其他选项，请在设计图面上选择一个或多个任务，再单击右键打开快捷菜单。 除了常用的 **“剪切”**、 **“复制”**、 **“粘贴”**、 **“删除”**和 **“全选”**之外，对于某些任务，还可以使用以下特殊选项：  
  
 **添加批注**  
 向设计图面上添加说明性注释。  
  
 **编辑**  
 打开任务的属性对话框。  
  
 **Disable**  
 使任务暂时不可用。  
  
 **启用**  
 恢复禁用的任务。  
  
 **分组**  
 创建包含一项或多项任务的组。  
  
 **取消分组**  
 从组中删除任务。  
  
 **自动调整大小**  
 将每项任务的大小设置为该任务的最佳大小。  
  
 **折叠**  
 隐藏组中的任务。  
  
 **展开**  
 显示组中以前使用“折叠”隐藏的任务。  
  
 **缩放**  
 更改设计图面上任务的大小。  
  
## 另请参阅  
 [维护计划](../../relational-databases/maintenance-plans/maintenance-plans.md)   
 [创建维护计划](../../relational-databases/maintenance-plans/create-a-maintenance-plan.md)  
  
  