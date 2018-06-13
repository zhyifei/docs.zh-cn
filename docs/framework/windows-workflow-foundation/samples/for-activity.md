---
title: For 活动
ms.date: 03/30/2017
ms.assetid: 2ea751b4-36f0-48aa-a115-70a2ab89f6d8
ms.openlocfilehash: c79f295e7880f845c606a55f9c56ad65350f9c52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515440"
---
# <a name="for-activity"></a><span data-ttu-id="327d4-102">For 活动</span><span class="sxs-lookup"><span data-stu-id="327d4-102">For Activity</span></span>
<span data-ttu-id="327d4-103">For 示例演示如何生成一个继承自 <xref:System.Activities.NativeActivity> 的自定义活动，以及如何在工作流中使用此活动来执行实际示例。</span><span class="sxs-lookup"><span data-stu-id="327d4-103">The For sample demonstrates how to build a custom activity that inherits from <xref:System.Activities.NativeActivity>, and use it in a workflow to execute a real world example.</span></span> <span data-ttu-id="327d4-104">该示例中包含的自定义活动的功能与 C# `for` 语句的功能类似</span><span class="sxs-lookup"><span data-stu-id="327d4-104">The custom activity included in this sample functions like the C# `for` statement.</span></span> <span data-ttu-id="327d4-105">T</span><span class="sxs-lookup"><span data-stu-id="327d4-105">T</span></span>  
  
 <span data-ttu-id="327d4-106">`For` 自定义活动具有名为 `InitAction`、`IterationAction`、`Condition` 和 `Body` 的属性，这些属性分别对应于标准 C# `For` 语句中包含的初始化语句、交互式语句、继续条件和正文语句。</span><span class="sxs-lookup"><span data-stu-id="327d4-106">The `For` custom activity has properties named `InitAction`, `IterationAction`, `Condition`, and `Body` that correspond to the initialization statement, iterative statement, continuation condition, and body statement respectively found in the standard C# `For` statement.</span></span>  
  
 <span data-ttu-id="327d4-107">下表说明示例中的主要文件。</span><span class="sxs-lookup"><span data-stu-id="327d4-107">The following table describes the key files in the sample.</span></span>  
  
|<span data-ttu-id="327d4-108">文件</span><span class="sxs-lookup"><span data-stu-id="327d4-108">File</span></span>|<span data-ttu-id="327d4-109">描述</span><span class="sxs-lookup"><span data-stu-id="327d4-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="327d4-110">For.cs</span><span class="sxs-lookup"><span data-stu-id="327d4-110">For.cs</span></span>|<span data-ttu-id="327d4-111">`For` 自定义活动的类定义，它扩展 <xref:System.Activities.NativeActivity> 类以提供 C# `For` 语句的功能。</span><span class="sxs-lookup"><span data-stu-id="327d4-111">Class definition for the `For` custom activity, which extends the <xref:System.Activities.NativeActivity> class to provide the functionality of the C# `For` statement.</span></span>|  
|<span data-ttu-id="327d4-112">Program.cs</span><span class="sxs-lookup"><span data-stu-id="327d4-112">Program.cs</span></span>|<span data-ttu-id="327d4-113">一个客户端应用程序，它使用自定义 `For` 活动对集合执行基本交互式工作。</span><span class="sxs-lookup"><span data-stu-id="327d4-113">A client application that performs basic iterative work on a collection using the custom `For` activity.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="327d4-114">在使用 `For` 自定义活动时，请确保设置了 `Condition` 属性；否则，将出现无限循环。</span><span class="sxs-lookup"><span data-stu-id="327d4-114">When using the `For` custom activity, ensure that the `Condition` property is set; otherwise an infinite loop could occur.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="327d4-115">演示</span><span class="sxs-lookup"><span data-stu-id="327d4-115">Demonstrates</span></span>  
 <span data-ttu-id="327d4-116">创建从 <xref:System.Activities.NativeActivity> 继承的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="327d4-116">Create a custom activity that inherits from <xref:System.Activities.NativeActivity>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="327d4-117">讨论</span><span class="sxs-lookup"><span data-stu-id="327d4-117">Discussion</span></span>  
 <span data-ttu-id="327d4-118">下表介绍了此示例中包含的活动的属性。</span><span class="sxs-lookup"><span data-stu-id="327d4-118">The following table describes the properties of the activity included in this sample.</span></span>  
  
 <span data-ttu-id="327d4-119">InitAction</span><span class="sxs-lookup"><span data-stu-id="327d4-119">InitAction</span></span>  
 <span data-ttu-id="327d4-120">初始化语句</span><span class="sxs-lookup"><span data-stu-id="327d4-120">Initialization statement</span></span>  
  
 <span data-ttu-id="327d4-121">IterationAction</span><span class="sxs-lookup"><span data-stu-id="327d4-121">IterationAction</span></span>  
 <span data-ttu-id="327d4-122">交互式语句</span><span class="sxs-lookup"><span data-stu-id="327d4-122">Iterative statement</span></span>  
  
 <span data-ttu-id="327d4-123">条件</span><span class="sxs-lookup"><span data-stu-id="327d4-123">Condition</span></span>  
 <span data-ttu-id="327d4-124">继续语句</span><span class="sxs-lookup"><span data-stu-id="327d4-124">Continuation statement</span></span>  
  
 <span data-ttu-id="327d4-125">Body</span><span class="sxs-lookup"><span data-stu-id="327d4-125">Body</span></span>  
 <span data-ttu-id="327d4-126">正文语句</span><span class="sxs-lookup"><span data-stu-id="327d4-126">Body statement</span></span>  
  
 <span data-ttu-id="327d4-127">此活动从 <xref:System.Activities.NativeActivity> 继承，以通过使用 `ScheduleActivity` 的 <xref:System.Activities.NativeActivityContext> 方法之一来获取对运行时功能（如计划要运行的其他活动）的访问权。</span><span class="sxs-lookup"><span data-stu-id="327d4-127">The activity inherits from <xref:System.Activities.NativeActivity> to gain access to runtime features such as scheduling additional activities to run, using one of the `ScheduleActivity` methods of <xref:System.Activities.NativeActivityContext>.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="327d4-128">使用此示例</span><span class="sxs-lookup"><span data-stu-id="327d4-128">To use this sample</span></span>  
  
1.  <span data-ttu-id="327d4-129">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]，打开 For.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="327d4-129">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the For.sln solution file.</span></span>  
  
2.  <span data-ttu-id="327d4-130">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="327d4-130">Build the solution, by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="327d4-131">按 F5 运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="327d4-131">Run the solution, by pressing F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="327d4-132">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="327d4-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="327d4-133">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="327d4-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="327d4-134">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="327d4-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="327d4-135">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="327d4-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\For`