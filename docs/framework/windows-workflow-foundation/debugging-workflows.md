---
title: 调试工作流
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 788cc6b25e4faa8a680f5ec23d88a5d18d0a7c87
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="debugging-workflows"></a><span data-ttu-id="179a1-102">调试工作流</span><span class="sxs-lookup"><span data-stu-id="179a1-102">Debugging Workflows</span></span>
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="179a1-103">提供多个用于从开发环境调试运行的工作流的选项。</span><span class="sxs-lookup"><span data-stu-id="179a1-103"> offers several options for debugging running workflows from the development environment.</span></span> <span data-ttu-id="179a1-104">可以在设计器、XAML 和代码中调试工作流。</span><span class="sxs-lookup"><span data-stu-id="179a1-104">Workflows can be debugged in the designer, in XAML, and in code.</span></span>  
  
## <a name="debugging-in-the-workflow-designer"></a><span data-ttu-id="179a1-105">在工作流设计器中调试</span><span class="sxs-lookup"><span data-stu-id="179a1-105">Debugging in the Workflow Designer</span></span>  
 <span data-ttu-id="179a1-106">可以通过突出显示活动并按工作流设计器中的活动上设置断点**F9**或通过使用活动的上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="179a1-106">Breakpoints can be set on activities in the workflow designer by either highlighting the activity and pressing **F9** or by using the activity’s context menu.</span></span> <span data-ttu-id="179a1-107">然后，当工作流宿主在调试模式下运行时将中断工作流的执行。</span><span class="sxs-lookup"><span data-stu-id="179a1-107">Execution of the workflow then breaks when the workflow host is run in debug mode.</span></span> <span data-ttu-id="179a1-108">在下面的屏幕快照中，工作流执行在断点处暂停。</span><span class="sxs-lookup"><span data-stu-id="179a1-108">In the following screenshot, workflow execution is paused at a breakpoint.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="179a1-109"> [使用工作流设计器调试工作流](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer)。</span><span class="sxs-lookup"><span data-stu-id="179a1-109"> [Debugging Workflows with the Workflow Designer](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer).</span></span>  
  
## <a name="debugging-in-xaml"></a><span data-ttu-id="179a1-110">在 XAML 中调试</span><span class="sxs-lookup"><span data-stu-id="179a1-110">Debugging in XAML</span></span>  
 <span data-ttu-id="179a1-111">如果在设计器中某个工作流已在断点处暂停，则还可以在 XAML 中调试该工作流。</span><span class="sxs-lookup"><span data-stu-id="179a1-111">If a workflow has paused at a breakpoint in the designer, the workflow can also be debugged in XAML.</span></span> <span data-ttu-id="179a1-112">若要在 XAML 中查看执行点，请选择**XAML 视图**在工作流设计器中工作流执行暂停时。</span><span class="sxs-lookup"><span data-stu-id="179a1-112">To view the point of execution in XAML, select **XAML View** in the workflow designer when workflow execution is paused.</span></span> <span data-ttu-id="179a1-113">通过从解决方案资源管理器重新打开工作流可以将调试切换回设计器。</span><span class="sxs-lookup"><span data-stu-id="179a1-113">Debugging can be switched back to the designer by re-opening the workflow in the designer from the solution explorer.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="179a1-114"> [如何： 使用工作流设计器调试 XAML](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer)。</span><span class="sxs-lookup"><span data-stu-id="179a1-114"> [How to: Debug XAML with the Workflow Designer](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer).</span></span>  
  
## <a name="debugging-in-code"></a><span data-ttu-id="179a1-115">在代码中调试</span><span class="sxs-lookup"><span data-stu-id="179a1-115">Debugging in Code</span></span>  
 <span data-ttu-id="179a1-116">也可以在 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 中使用代码断点，其使用方式与在其他命令性应用程序中相同。</span><span class="sxs-lookup"><span data-stu-id="179a1-116">Code breakpoints can be used in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] in the same way that they can be used in other imperative applications.</span></span> <span data-ttu-id="179a1-117">单击左边的距的代码窗格，以创建一个代码断点，或按**F9**光标位置处放置一个断点。</span><span class="sxs-lookup"><span data-stu-id="179a1-117">Click the left margin of the code pane to create a code breakpoint, or press **F9** to place a breakpoint at the cursor location.</span></span>  
  
## <a name="attaching-to-a-workflow-process"></a><span data-ttu-id="179a1-118">附加到工作流过程</span><span class="sxs-lookup"><span data-stu-id="179a1-118">Attaching to a Workflow Process</span></span>  
 <span data-ttu-id="179a1-119">工作流调试还支持使用 Visual Studio 的基础结构附加到某个过程。</span><span class="sxs-lookup"><span data-stu-id="179a1-119">Workflow debugging also supports using Visual Studio’s infrastructure to attach to a process.</span></span> <span data-ttu-id="179a1-120">这使工作流创作者能够调试在另一个宿主环境（如 Internet 信息服务 (IIS) 7.0）中运行的工作流。</span><span class="sxs-lookup"><span data-stu-id="179a1-120">This enables the workflow author to debug a workflow running in a different host environment such as Internet Information Services (IIS) 7.0.</span></span>  
  
## <a name="remote-debugging"></a><span data-ttu-id="179a1-121">Remote Debugging</span><span class="sxs-lookup"><span data-stu-id="179a1-121">Remote Debugging</span></span>  
 [!INCLUDE[wf](../../../includes/wf-md.md)]<span data-ttu-id="179a1-122"> 远程调试的函数与其他 Visual Studio 组件的远程调试相同。</span><span class="sxs-lookup"><span data-stu-id="179a1-122"> remote debugging functions the same as remote debugging for other Visual Studio components.</span></span> <span data-ttu-id="179a1-123">有关使用远程调试的信息，请参阅[如何： 启用远程调试](http://go.microsoft.com/fwlink/?LinkId=196257)。</span><span class="sxs-lookup"><span data-stu-id="179a1-123">For information on using remote debugging, see [How to: Enable Remote Debugging](http://go.microsoft.com/fwlink/?LinkId=196257).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="179a1-124">如果工作流应用程序针对 x86 体系结构并位于运行 64 位操作系统的计算机上远程调试将不工作，除非在远程计算机上安装 Visual Studio 或工作流应用程序的目标更改为**任何 CPU**。</span><span class="sxs-lookup"><span data-stu-id="179a1-124">If the workflow application targets the x86 architecture and is hosted on a computer running a 64 bit operating system, then remote debugging will not work unless Visual Studio is installed on the remote computer or the target for the workflow application is changed to **Any CPU**.</span></span>  
  
## <a name="extending-the-workflow-debugging-service"></a><span data-ttu-id="179a1-125">扩展工作流调试服务</span><span class="sxs-lookup"><span data-stu-id="179a1-125">Extending the Workflow Debugging Service</span></span>  
 <span data-ttu-id="179a1-126">工作流调试器服务现在以公共方式使用，可以使用该服务创建自定义应用程序，如在重新承载的设计器中进行监视、模拟和调试。</span><span class="sxs-lookup"><span data-stu-id="179a1-126">The workflow debugger service is now public and can be used to create custom applications such as monitoring, simulation, and debugging in a re-hosted designer.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="179a1-127"> <xref:System.Activities.Presentation.Debug.DebuggerService> 主题。</span><span class="sxs-lookup"><span data-stu-id="179a1-127"> the <xref:System.Activities.Presentation.Debug.DebuggerService> topic.</span></span>
