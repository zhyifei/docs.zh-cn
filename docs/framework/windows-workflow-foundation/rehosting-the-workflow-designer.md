---
title: 重新承载工作流设计器
ms.date: 03/30/2017
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
ms.openlocfilehash: 98048ca58bf635f4e87241befa083dc240deaecf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61968176"
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="1ca3e-102">重新承载工作流设计器</span><span class="sxs-lookup"><span data-stu-id="1ca3e-102">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="1ca3e-103">[!INCLUDE[wfd1](../../../includes/wfd1-md.md)]可以重新承载在 Visual Studio 2012 以外的环境中用于创建、 修改和监视工作流。</span><span class="sxs-lookup"><span data-stu-id="1ca3e-103">The [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] can be rehosted in environments outside of Visual Studio 2012 for the purposes of creating, modifying, and monitoring workflows.</span></span>

 <span data-ttu-id="1ca3e-104"><xref:System.Activities.Presentation.WorkflowDesigner> 类型是画布、属性网格和其他元素的包装，它公开一个基本的编程模型，用于处理大多数设计器重新承载方案。</span><span class="sxs-lookup"><span data-stu-id="1ca3e-104">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="1ca3e-105">承载<xref:System.Activities.Presentation.WorkflowDesigner>在 Windows Presentation Foundation (WPF) 应用程序是一种常见重新承载方案为[!INCLUDE[wfd2](../../../includes/wfd2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1ca3e-105">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a Windows Presentation Foundation (WPF) application is a common rehosting scenario for [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1ca3e-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="1ca3e-106">In This Section</span></span>
 [<span data-ttu-id="1ca3e-107">任务 1:创建新的 Windows Presentation Foundation 应用程序</span><span class="sxs-lookup"><span data-stu-id="1ca3e-107">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)

 [<span data-ttu-id="1ca3e-108">任务 2:承载工作流设计器</span><span class="sxs-lookup"><span data-stu-id="1ca3e-108">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)

 [<span data-ttu-id="1ca3e-109">任务 3:创建工具箱和属性网格窗格</span><span class="sxs-lookup"><span data-stu-id="1ca3e-109">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)

 [<span data-ttu-id="1ca3e-110">重新托管的工作流设计器支持的新 Workflow Foundation 4.5 功能</span><span class="sxs-lookup"><span data-stu-id="1ca3e-110">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](wf-features-in-the-rehosted-workflow-designer.md)

## <a name="see-also"></a><span data-ttu-id="1ca3e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ca3e-111">See also</span></span>

- [<span data-ttu-id="1ca3e-112">自定义工作流设计体验</span><span class="sxs-lookup"><span data-stu-id="1ca3e-112">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
