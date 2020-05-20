---
title: 入门 Tutorial2
description: 本文将开始一系列教程，其中介绍了如何对 Windows Workflow Foundation 应用程序进行编程。
ms.date: 03/30/2017
helpviewer_keywords:
- WF [WF], getting started
- Windows Workflow Foundation [WF], getting started
ms.assetid: c2d3585f-6b1a-4d4f-9865-bd7cd31c5d42
ms.openlocfilehash: 148ba77231067bf5f8ff1d8b444b83d951ce8761
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419845"
---
# <a name="getting-started-tutorial"></a><span data-ttu-id="aed4b-103">入门教程</span><span class="sxs-lookup"><span data-stu-id="aed4b-103">Getting Started Tutorial</span></span>
<span data-ttu-id="aed4b-104">本部分包含一组演练主题，其中介绍了如何对 Windows Workflow Foundation （WF）应用程序进行编程。</span><span class="sxs-lookup"><span data-stu-id="aed4b-104">This section contains a set of walkthrough topics that introduce you to programming Windows Workflow Foundation (WF) applications.</span></span> <span data-ttu-id="aed4b-105">按照这些主题中的过程操作，将生成一个猜数游戏应用程序。</span><span class="sxs-lookup"><span data-stu-id="aed4b-105">By following the procedures in these topics, you will build an application that is a number guessing game.</span></span> <span data-ttu-id="aed4b-106">本教程中的第一个主题将逐步引导您创建工作流所需的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="aed4b-106">The first topic in the tutorial leads you through the steps to create the custom activities required for the workflow.</span></span> <span data-ttu-id="aed4b-107">在第二个主题中，将这些活动与内置的工作流活动组合成一个流程图工作流。</span><span class="sxs-lookup"><span data-stu-id="aed4b-107">In the second topic, these activities are assembled along with built-in workflow activities into a flowchart workflow.</span></span> <span data-ttu-id="aed4b-108">在第三个主题中，配置主机应用程序以运行工作流，并在最后的主题中介绍持久性。</span><span class="sxs-lookup"><span data-stu-id="aed4b-108">In the third topic, the host application is configured to run the workflow, and in the final topic persistence is introduced.</span></span> <span data-ttu-id="aed4b-109">此过程的每一步骤都依赖于前面的步骤，因此建议您按顺序完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="aed4b-109">Each step in this process depends on the previous steps, so we recommend that you complete them in order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aed4b-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="aed4b-110">In This Section</span></span>  
 [<span data-ttu-id="aed4b-111">如何：创建活动</span><span class="sxs-lookup"><span data-stu-id="aed4b-111">How to: Create an Activity</span></span>](how-to-create-an-activity.md)  
 <span data-ttu-id="aed4b-112">介绍如何创建从 <xref:System.Activities.NativeActivity%601> 派生的自定义活动，以及如何使用活动设计器将此活动与内置的活动组合成一个复合活动。</span><span class="sxs-lookup"><span data-stu-id="aed4b-112">Describes how to create a custom activity that derives from <xref:System.Activities.NativeActivity%601>, and how to compose this activity along with a built-in activity into a composite activity using the activity designer.</span></span>  
  
 [<span data-ttu-id="aed4b-113">如何：创建工作流</span><span class="sxs-lookup"><span data-stu-id="aed4b-113">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)  
 <span data-ttu-id="aed4b-114">通过使用内置的活动和前面教程中的自定义活动，介绍如何创建流程图、顺序工作流和状态机工作流。</span><span class="sxs-lookup"><span data-stu-id="aed4b-114">Describes how to create flowchart, sequential, and state machine workflows by using built-in activities and the custom activities from the preceding tutorial.</span></span>  
  
 [<span data-ttu-id="aed4b-115">如何：运行工作流</span><span class="sxs-lookup"><span data-stu-id="aed4b-115">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)  
 <span data-ttu-id="aed4b-116">介绍如何从宿主环境调用工作流、如何将数据传入和传出工作流以及如何继续书签。</span><span class="sxs-lookup"><span data-stu-id="aed4b-116">Describes how to invoke a workflow from a host environment, pass data into and out of a workflow, and how to resume bookmarks.</span></span>  
  
 [<span data-ttu-id="aed4b-117">如何：创建和运行长期运行的工作流</span><span class="sxs-lookup"><span data-stu-id="aed4b-117">How to: Create and Run a Long Running Workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md)  
 <span data-ttu-id="aed4b-118">介绍如何向工作流应用程序添加持久性。</span><span class="sxs-lookup"><span data-stu-id="aed4b-118">Describes how to add persistence to a workflow application.</span></span>  
  
 [<span data-ttu-id="aed4b-119">如何：创建自定义跟踪参与者</span><span class="sxs-lookup"><span data-stu-id="aed4b-119">How to: Create a Custom Tracking Participant</span></span>](how-to-create-a-custom-tracking-participant.md)  
 <span data-ttu-id="aed4b-120">介绍如何创建自定义跟踪参与者和跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="aed4b-120">Describes how to create a custom tracking participant and tracking profile.</span></span>  
  
 [<span data-ttu-id="aed4b-121">如何：并行承载多个版本的工作流</span><span class="sxs-lookup"><span data-stu-id="aed4b-121">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)  
 <span data-ttu-id="aed4b-122">介绍如何使用 `WorkflowIdentity` 并行承载工作流的多个版本。</span><span class="sxs-lookup"><span data-stu-id="aed4b-122">Describes how to use `WorkflowIdentity` to host multiple versions of a workflow side-by-side.</span></span>  
  
 [<span data-ttu-id="aed4b-123">如何：更新正在运行的工作流实例的定义</span><span class="sxs-lookup"><span data-stu-id="aed4b-123">How to: Update the Definition of a Running Workflow Instance</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md)  
 <span data-ttu-id="aed4b-124">介绍如何使用动态更新来修改运行的工作流实例。</span><span class="sxs-lookup"><span data-stu-id="aed4b-124">Describes how to use dynamic update to modify running workflow instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aed4b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aed4b-125">See also</span></span>

- [<span data-ttu-id="aed4b-126">Windows Workflow Foundation 编程</span><span class="sxs-lookup"><span data-stu-id="aed4b-126">Windows Workflow Foundation Programming</span></span>](programming.md)
