---
title: 入门 Tutorial2
ms.date: 03/30/2017
helpviewer_keywords:
- WF [WF], getting started
- Windows Workflow Foundation [WF], getting started
ms.assetid: c2d3585f-6b1a-4d4f-9865-bd7cd31c5d42
ms.openlocfilehash: 540765c09dceef583798ceaf1abf9f191f444697
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217427"
---
# <a name="getting-started-tutorial"></a><span data-ttu-id="c6331-102">入门教程</span><span class="sxs-lookup"><span data-stu-id="c6331-102">Getting Started Tutorial</span></span>
<span data-ttu-id="c6331-103">本部分包含一的组向您介绍 Windows Workflow Foundation (WF) 应用程序编程的演练主题。</span><span class="sxs-lookup"><span data-stu-id="c6331-103">This section contains a set of walkthrough topics that introduce you to programming Windows Workflow Foundation (WF) applications.</span></span> <span data-ttu-id="c6331-104">按照这些主题中的过程操作，将生成一个猜数游戏应用程序。</span><span class="sxs-lookup"><span data-stu-id="c6331-104">By following the procedures in these topics, you will build an application that is a number guessing game.</span></span> <span data-ttu-id="c6331-105">本教程中的第一个主题将逐步引导您创建工作流所需的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="c6331-105">The first topic in the tutorial leads you through the steps to create the custom activities required for the workflow.</span></span> <span data-ttu-id="c6331-106">在第二个主题中，将这些活动与内置的工作流活动组合成一个流程图工作流。</span><span class="sxs-lookup"><span data-stu-id="c6331-106">In the second topic, these activities are assembled along with built-in workflow activities into a flowchart workflow.</span></span> <span data-ttu-id="c6331-107">在第三个主题中，配置主机应用程序以运行工作流，并在最后的主题中介绍持久性。</span><span class="sxs-lookup"><span data-stu-id="c6331-107">In the third topic, the host application is configured to run the workflow, and in the final topic persistence is introduced.</span></span> <span data-ttu-id="c6331-108">此过程的每一步骤都依赖于前面的步骤，因此建议您按顺序完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="c6331-108">Each step in this process depends on the previous steps, so we recommend that you complete them in order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c6331-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="c6331-109">In This Section</span></span>  
 [<span data-ttu-id="c6331-110">如何：创建活动</span><span class="sxs-lookup"><span data-stu-id="c6331-110">How to: Create an Activity</span></span>](how-to-create-an-activity.md)  
 <span data-ttu-id="c6331-111">介绍如何创建从 <xref:System.Activities.NativeActivity%601> 派生的自定义活动，以及如何使用活动设计器将此活动与内置的活动组合成一个复合活动。</span><span class="sxs-lookup"><span data-stu-id="c6331-111">Describes how to create a custom activity that derives from <xref:System.Activities.NativeActivity%601>, and how to compose this activity along with a built-in activity into a composite activity using the activity designer.</span></span>  
  
 [<span data-ttu-id="c6331-112">如何：创建工作流</span><span class="sxs-lookup"><span data-stu-id="c6331-112">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)  
 <span data-ttu-id="c6331-113">通过使用内置的活动和前面教程中的自定义活动，介绍如何创建流程图、顺序工作流和状态机工作流。</span><span class="sxs-lookup"><span data-stu-id="c6331-113">Describes how to create flowchart, sequential, and state machine workflows by using built-in activities and the custom activities from the preceding tutorial.</span></span>  
  
 [<span data-ttu-id="c6331-114">如何：运行工作流</span><span class="sxs-lookup"><span data-stu-id="c6331-114">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)  
 <span data-ttu-id="c6331-115">介绍如何从宿主环境调用工作流、如何将数据传入和传出工作流以及如何继续书签。</span><span class="sxs-lookup"><span data-stu-id="c6331-115">Describes how to invoke a workflow from a host environment, pass data into and out of a workflow, and how to resume bookmarks.</span></span>  
  
 [<span data-ttu-id="c6331-116">如何：创建和运行长时间运行工作流</span><span class="sxs-lookup"><span data-stu-id="c6331-116">How to: Create and Run a Long Running Workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md)  
 <span data-ttu-id="c6331-117">介绍如何向工作流应用程序添加持久性。</span><span class="sxs-lookup"><span data-stu-id="c6331-117">Describes how to add persistence to a workflow application.</span></span>  
  
 [<span data-ttu-id="c6331-118">如何：创建自定义跟踪参与者</span><span class="sxs-lookup"><span data-stu-id="c6331-118">How to: Create a Custom Tracking Participant</span></span>](how-to-create-a-custom-tracking-participant.md)  
 <span data-ttu-id="c6331-119">介绍如何创建自定义跟踪参与者和跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="c6331-119">Describes how to create a custom tracking participant and tracking profile.</span></span>  
  
 [<span data-ttu-id="c6331-120">如何：承载多个版本的工作流的并排方案</span><span class="sxs-lookup"><span data-stu-id="c6331-120">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)  
 <span data-ttu-id="c6331-121">介绍如何使用 `WorkflowIdentity` 并行承载工作流的多个版本。</span><span class="sxs-lookup"><span data-stu-id="c6331-121">Describes how to use `WorkflowIdentity` to host multiple versions of a workflow side-by-side.</span></span>  
  
 [<span data-ttu-id="c6331-122">如何：更新正在运行的工作流实例的定义</span><span class="sxs-lookup"><span data-stu-id="c6331-122">How to: Update the Definition of a Running Workflow Instance</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md)  
 <span data-ttu-id="c6331-123">介绍如何使用动态更新来修改运行的工作流实例。</span><span class="sxs-lookup"><span data-stu-id="c6331-123">Describes how to use dynamic update to modify running workflow instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6331-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6331-124">See also</span></span>

- [<span data-ttu-id="c6331-125">Windows Workflow Foundation 编程</span><span class="sxs-lookup"><span data-stu-id="c6331-125">Windows Workflow Foundation Programming</span></span>](programming.md)
