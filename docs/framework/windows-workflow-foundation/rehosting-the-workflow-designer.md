---
title: 重新承载工作流设计器
description: 在 Visual Studio 之外的环境中，可以重新承载 Windows 工作流设计器来创建、修改和监视工作流。
ms.date: 03/30/2017
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
ms.openlocfilehash: 34709b84d445b2bb07e32bfd3f34d06072f125bf
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421418"
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="ba5b7-103">重新承载工作流设计器</span><span class="sxs-lookup"><span data-stu-id="ba5b7-103">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="ba5b7-104">可在 Visual Studio 2012 之外的环境中重新承载 Windows 工作流设计器，以创建、修改和监视工作流。</span><span class="sxs-lookup"><span data-stu-id="ba5b7-104">The Windows Workflow Designer can be rehosted in environments outside of Visual Studio 2012 for the purposes of creating, modifying, and monitoring workflows.</span></span>

 <span data-ttu-id="ba5b7-105"><xref:System.Activities.Presentation.WorkflowDesigner> 类型是画布、属性网格和其他元素的包装，它公开一个基本的编程模型，用于处理大多数设计器重新承载方案。</span><span class="sxs-lookup"><span data-stu-id="ba5b7-105">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="ba5b7-106">在 <xref:System.Activities.Presentation.WorkflowDesigner> Windows Presentation Foundation （WPF）应用程序内部承载是工作流设计器的常见重新承载方案。</span><span class="sxs-lookup"><span data-stu-id="ba5b7-106">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a Windows Presentation Foundation (WPF) application is a common rehosting scenario for Workflow Designer.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ba5b7-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="ba5b7-107">In This Section</span></span>
 [<span data-ttu-id="ba5b7-108">任务 1：创建一个新的 Windows Presentation Foundation 应用程序</span><span class="sxs-lookup"><span data-stu-id="ba5b7-108">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)

 [<span data-ttu-id="ba5b7-109">任务 2：承载工作流设计器</span><span class="sxs-lookup"><span data-stu-id="ba5b7-109">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)

 [<span data-ttu-id="ba5b7-110">任务 3：创建工具箱窗格和属性网格窗格</span><span class="sxs-lookup"><span data-stu-id="ba5b7-110">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)

 [<span data-ttu-id="ba5b7-111">重新承载的工作流设计器中新 Workflow Foundation 4.5 功能的支持</span><span class="sxs-lookup"><span data-stu-id="ba5b7-111">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](wf-features-in-the-rehosted-workflow-designer.md)

## <a name="see-also"></a><span data-ttu-id="ba5b7-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba5b7-112">See also</span></span>

- [<span data-ttu-id="ba5b7-113">自定义工作流设计体验</span><span class="sxs-lookup"><span data-stu-id="ba5b7-113">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
