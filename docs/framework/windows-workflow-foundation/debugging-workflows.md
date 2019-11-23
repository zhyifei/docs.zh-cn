---
title: 调试工作流
ms.date: 03/30/2017
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
ms.openlocfilehash: 3947e61161b0e2108fa48fbc7e33fb7601645a1b
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291486"
---
# <a name="debugging-workflows"></a><span data-ttu-id="48b5b-102">调试工作流</span><span class="sxs-lookup"><span data-stu-id="48b5b-102">Debugging Workflows</span></span>

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] <span data-ttu-id="48b5b-103">提供了用于从开发环境调试正在运行的工作流的多个选项。</span><span class="sxs-lookup"><span data-stu-id="48b5b-103">offers several options for debugging running workflows from the development environment.</span></span> <span data-ttu-id="48b5b-104">可以在设计器、XAML 和代码中调试工作流。</span><span class="sxs-lookup"><span data-stu-id="48b5b-104">Workflows can be debugged in the designer, in XAML, and in code.</span></span>

## <a name="debugging-in-the-workflow-designer"></a><span data-ttu-id="48b5b-105">在工作流设计器中调试</span><span class="sxs-lookup"><span data-stu-id="48b5b-105">Debugging in the Workflow Designer</span></span>

<span data-ttu-id="48b5b-106">可以在工作流设计器中对活动设置断点，方法是突出显示活动，按<kbd>F9</kbd> ，或使用活动的上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="48b5b-106">Breakpoints can be set on activities in the workflow designer by either highlighting the activity and pressing <kbd>F9</kbd> or by using the activity’s context menu.</span></span> <span data-ttu-id="48b5b-107">然后，当工作流宿主在调试模式下运行时将中断工作流的执行。</span><span class="sxs-lookup"><span data-stu-id="48b5b-107">Execution of the workflow then breaks when the workflow host is run in debug mode.</span></span> <span data-ttu-id="48b5b-108">在下面的屏幕快照中，工作流执行在断点处暂停。</span><span class="sxs-lookup"><span data-stu-id="48b5b-108">In the following screenshot, workflow execution is paused at a breakpoint.</span></span> <span data-ttu-id="48b5b-109">有关详细信息，请参阅[用工作流设计器调试工作流](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer)。</span><span class="sxs-lookup"><span data-stu-id="48b5b-109">For more information, see [Debugging Workflows with the Workflow Designer](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer).</span></span>

## <a name="debugging-in-xaml"></a><span data-ttu-id="48b5b-110">在 XAML 中调试</span><span class="sxs-lookup"><span data-stu-id="48b5b-110">Debugging in XAML</span></span>

<span data-ttu-id="48b5b-111">如果在设计器中某个工作流已在断点处暂停，则还可以在 XAML 中调试该工作流。</span><span class="sxs-lookup"><span data-stu-id="48b5b-111">If a workflow has paused at a breakpoint in the designer, the workflow can also be debugged in XAML.</span></span> <span data-ttu-id="48b5b-112">若要在 XAML 中查看执行点，请在工作流执行暂停时在工作流设计器中选择 " **XAML 视图**"。</span><span class="sxs-lookup"><span data-stu-id="48b5b-112">To view the point of execution in XAML, select **XAML View** in the workflow designer when workflow execution is paused.</span></span> <span data-ttu-id="48b5b-113">通过从解决方案资源管理器重新打开工作流可以将调试切换回设计器。</span><span class="sxs-lookup"><span data-stu-id="48b5b-113">Debugging can be switched back to the designer by re-opening the workflow in the designer from the solution explorer.</span></span> <span data-ttu-id="48b5b-114">有关详细信息，请参阅[如何：用工作流设计器调试 XAML](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer)。</span><span class="sxs-lookup"><span data-stu-id="48b5b-114">For more information, see [How to: Debug XAML with the Workflow Designer](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer).</span></span>

## <a name="debugging-in-code"></a><span data-ttu-id="48b5b-115">在代码中调试</span><span class="sxs-lookup"><span data-stu-id="48b5b-115">Debugging in Code</span></span>

<span data-ttu-id="48b5b-116">若要设置断点，请单击 "代码" 窗格的左边距，或在要设置该断点的行上按 " <kbd>F9</kbd> "。</span><span class="sxs-lookup"><span data-stu-id="48b5b-116">To set a breakpoint, click the left margin of the code pane, or press <kbd>F9</kbd> with the cursor at the line where you want to set it.</span></span>

## <a name="attaching-to-a-workflow-process"></a><span data-ttu-id="48b5b-117">附加到工作流过程</span><span class="sxs-lookup"><span data-stu-id="48b5b-117">Attaching to a Workflow Process</span></span>

<span data-ttu-id="48b5b-118">工作流调试还支持使用 Visual Studio 的基础结构附加到某个过程。</span><span class="sxs-lookup"><span data-stu-id="48b5b-118">Workflow debugging also supports using Visual Studio’s infrastructure to attach to a process.</span></span> <span data-ttu-id="48b5b-119">这使工作流创作者能够调试在另一个主机环境（如 Internet 信息服务 (IIS) 7.0）中运行的工作流。</span><span class="sxs-lookup"><span data-stu-id="48b5b-119">This enables the workflow author to debug a workflow running in a different host environment such as Internet Information Services (IIS) 7.0.</span></span>

## <a name="remote-debugging"></a><span data-ttu-id="48b5b-120">远程调试</span><span class="sxs-lookup"><span data-stu-id="48b5b-120">Remote Debugging</span></span>

<span data-ttu-id="48b5b-121">Windows Workflow Foundation （WF）远程调试与其他 Visual Studio 组件进行远程调试的功能相同。</span><span class="sxs-lookup"><span data-stu-id="48b5b-121">Windows Workflow Foundation (WF) remote debugging functions the same as remote debugging for other Visual Studio components.</span></span> <span data-ttu-id="48b5b-122">有关使用远程调试的信息，请参阅[如何：启用远程调试](https://go.microsoft.com/fwlink/?LinkId=196257)。</span><span class="sxs-lookup"><span data-stu-id="48b5b-122">For information on using remote debugging, see [How to: Enable Remote Debugging](https://go.microsoft.com/fwlink/?LinkId=196257).</span></span>

> [!NOTE]
> <span data-ttu-id="48b5b-123">如果工作流应用程序针对 x86 体系结构并托管在运行64位操作系统的计算机上，则远程调试将无法工作，除非在远程计算机上安装了 Visual Studio，或者工作流应用程序的目标更改为 "**任意 CPU**"。</span><span class="sxs-lookup"><span data-stu-id="48b5b-123">If the workflow application targets the x86 architecture and is hosted on a computer running a 64 bit operating system, then remote debugging will not work unless Visual Studio is installed on the remote computer or the target for the workflow application is changed to **Any CPU**.</span></span>

## <a name="extending-the-workflow-debugging-service"></a><span data-ttu-id="48b5b-124">扩展工作流调试服务</span><span class="sxs-lookup"><span data-stu-id="48b5b-124">Extending the Workflow Debugging Service</span></span>

<span data-ttu-id="48b5b-125">工作流调试器服务现在以公共方式使用，可以使用该服务创建自定义应用程序，如在重新承载的设计器中进行监视、模拟和调试。</span><span class="sxs-lookup"><span data-stu-id="48b5b-125">The workflow debugger service is now public and can be used to create custom applications such as monitoring, simulation, and debugging in a re-hosted designer.</span></span> <span data-ttu-id="48b5b-126">有关详细信息，请参阅<xref:System.Activities.Presentation.Debug.DebuggerService>一文。</span><span class="sxs-lookup"><span data-stu-id="48b5b-126">For more information, see the <xref:System.Activities.Presentation.Debug.DebuggerService> article.</span></span>
