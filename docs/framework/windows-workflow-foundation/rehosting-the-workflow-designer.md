---
title: "重新承载工作流设计器"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c01b39a8f21011bb45a1d73fcf44df76d5bf6fb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="34514-102">重新承载工作流设计器</span><span class="sxs-lookup"><span data-stu-id="34514-102">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="34514-103">为了创建、修改和监视工作流，可以将 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] 重新承载于 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 之外的环境中。</span><span class="sxs-lookup"><span data-stu-id="34514-103">The [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] can be rehosted in environments outside of [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] for the purposes of creating, modifying, and monitoring workflows.</span></span>  
  
 <span data-ttu-id="34514-104"><xref:System.Activities.Presentation.WorkflowDesigner> 类型是画布、属性网格和其他元素的包装，它公开一个基本的编程模型，用于处理大多数设计器重新承载方案。</span><span class="sxs-lookup"><span data-stu-id="34514-104">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="34514-105">在 <xref:System.Activities.Presentation.WorkflowDesigner> 应用程序内承载 [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] 是 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] 的一种常见重新承载方案。</span><span class="sxs-lookup"><span data-stu-id="34514-105">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] application is a common rehosting scenario for [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="34514-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="34514-106">In This Section</span></span>  
 [<span data-ttu-id="34514-107">任务 1：新建 Windows Presentation Foundation 应用程序</span><span class="sxs-lookup"><span data-stu-id="34514-107">Task 1: Create a New Windows Presentation Foundation Application</span></span>](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)  
  
 [<span data-ttu-id="34514-108">任务 2：托管工作流设计器</span><span class="sxs-lookup"><span data-stu-id="34514-108">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)  
  
 [<span data-ttu-id="34514-109">任务 3：创建“工具箱”和“属性网格”窗格</span><span class="sxs-lookup"><span data-stu-id="34514-109">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md)  
  
 [<span data-ttu-id="34514-110">重新托管的工作流设计器支持的新 Workflow Foundation 4.5 功能</span><span class="sxs-lookup"><span data-stu-id="34514-110">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/wf-features-in-the-rehosted-workflow-designer.md)  
  
## <a name="see-also"></a><span data-ttu-id="34514-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34514-111">See Also</span></span>  
 [<span data-ttu-id="34514-112">自定义工作流设计体验</span><span class="sxs-lookup"><span data-stu-id="34514-112">Customizing the Workflow Design Experience</span></span>](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)
