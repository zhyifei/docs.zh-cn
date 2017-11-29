---
title: "等待输入活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d58c344e-9ee8-4ce2-b199-75b3fe45237f
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d4e9df410f5f8e6c95baa5ce5fdc9b2d339a190f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="wait-for-input-activity"></a><span data-ttu-id="7b264-102">等待输入活动</span><span class="sxs-lookup"><span data-stu-id="7b264-102">Wait For Input Activity</span></span>
<span data-ttu-id="7b264-103">此示例演示如何在工作流中创建命名书签。</span><span class="sxs-lookup"><span data-stu-id="7b264-103">This sample demonstrates how to create named bookmarks in a workflow.</span></span> [!INCLUDE[wf](../../../../includes/wf-md.md)]<span data-ttu-id="7b264-104"> 没有提供用于创建声明性书签的活动。</span><span class="sxs-lookup"><span data-stu-id="7b264-104"> does not provide an activity for declarative bookmark creation.</span></span> <span data-ttu-id="7b264-105">因此，当您需要在工作流中创建书签时，必须编写一个创建书签的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="7b264-105">Therefore, when you want to create a bookmark in your workflow, you must write a custom activity that creates it.</span></span> <span data-ttu-id="7b264-106">此示例中定义的 `WaitForInput` 活动提供了此项功能，以便用户可以通过声明方式在工作流内创建书签。</span><span class="sxs-lookup"><span data-stu-id="7b264-106">The `WaitForInput` activity defined in this sample provides this functionality, so that users can create bookmarks declaratively within a workflow.</span></span>  
  
## <a name="projects-in-this-sample"></a><span data-ttu-id="7b264-107">此示例中的项目</span><span class="sxs-lookup"><span data-stu-id="7b264-107">Projects in this sample</span></span>  
  
|<span data-ttu-id="7b264-108">**项目名称**</span><span class="sxs-lookup"><span data-stu-id="7b264-108">**Project Name**</span></span>|<span data-ttu-id="7b264-109">**描述**</span><span class="sxs-lookup"><span data-stu-id="7b264-109">**Description**</span></span>|<span data-ttu-id="7b264-110">**主要文件**</span><span class="sxs-lookup"><span data-stu-id="7b264-110">**Main Files**</span></span>|  
|-|-|-|  
|<span data-ttu-id="7b264-111">WaitForInput</span><span class="sxs-lookup"><span data-stu-id="7b264-111">WaitForInput</span></span>|<span data-ttu-id="7b264-112">包含 `WaitForInput` 活动及其设计器</span><span class="sxs-lookup"><span data-stu-id="7b264-112">Contains `WaitForInput` activity and its designer</span></span>|<span data-ttu-id="7b264-113">WaitForInput.cs</span><span class="sxs-lookup"><span data-stu-id="7b264-113">WaitForInput.cs</span></span><br /><br /> <span data-ttu-id="7b264-114">`WaitForInput` 活动定义。</span><span class="sxs-lookup"><span data-stu-id="7b264-114">`WaitForInput` activity definition.</span></span>|  
|||<span data-ttu-id="7b264-115">WaitForInputDesigner.xaml</span><span class="sxs-lookup"><span data-stu-id="7b264-115">WaitForInputDesigner.xaml</span></span><br /><br /> <span data-ttu-id="7b264-116">`WaitForInput` 活动的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="7b264-116">Custom designer for the `WaitForInput` activity.</span></span>|  
|||<span data-ttu-id="7b264-117">TypeToFirstGenericArgumentConverter.cs</span><span class="sxs-lookup"><span data-stu-id="7b264-117">TypeToFirstGenericArgumentConverter.cs</span></span><br /><br /> <span data-ttu-id="7b264-118">用于更新设计器中活动的泛型类型的 WPF 类型转换器。</span><span class="sxs-lookup"><span data-stu-id="7b264-118">WPF type converter used to update the generic type of the activity in the designer.</span></span>|  
|<span data-ttu-id="7b264-119">WaitForInputTestClient</span><span class="sxs-lookup"><span data-stu-id="7b264-119">WaitForInputTestClient</span></span>|<span data-ttu-id="7b264-120">示例客户端应用程序，它可通过工作流设计器使用一些 WaitForInput 活动来配置和运行工作流。</span><span class="sxs-lookup"><span data-stu-id="7b264-120">Sample client application that configures and runs a workflow using several WaitForInput activities using the workflow designer.</span></span>|<span data-ttu-id="7b264-121">Sequence1.xaml</span><span class="sxs-lookup"><span data-stu-id="7b264-121">Sequence1.xaml</span></span><br /><br /> <span data-ttu-id="7b264-122">使用 `WaitForInput` 活动的顺序工作流。</span><span class="sxs-lookup"><span data-stu-id="7b264-122">A sequential workflow that uses the `WaitForInput` activity.</span></span>|  
|||<span data-ttu-id="7b264-123">Program.cs</span><span class="sxs-lookup"><span data-stu-id="7b264-123">Program.cs</span></span><br /><br /> <span data-ttu-id="7b264-124">运行在 Sequence1.xaml 中定义的工作流的实例。</span><span class="sxs-lookup"><span data-stu-id="7b264-124">Runs an instance of the workflow defined in Sequence1.xaml.</span></span>|  
  
## <a name="waitforinput-activity"></a><span data-ttu-id="7b264-125">WaitForInput 活动</span><span class="sxs-lookup"><span data-stu-id="7b264-125">WaitForInput Activity</span></span>  
 <span data-ttu-id="7b264-126">`WaitForInput` 活动在工作流中创建一个命名书签。</span><span class="sxs-lookup"><span data-stu-id="7b264-126">The `WaitForInput` activity creates a named bookmark in a workflow.</span></span> <span data-ttu-id="7b264-127">该书签等待一个信号，然后接收它的所配置的类型的数据。</span><span class="sxs-lookup"><span data-stu-id="7b264-127">The bookmark waits for a signal and receives data of its configured type.</span></span> <span data-ttu-id="7b264-128">当书签恢复之后，将可以通过 `Result` 属性使用传入到工作流中的数据。</span><span class="sxs-lookup"><span data-stu-id="7b264-128">After the bookmark is resumed the data passed into the workflow is available through the `Result` property.</span></span>  
  
 <span data-ttu-id="7b264-129">`WaitForInput` 活动派生自 <xref:System.Activities.NativeActivity> 类，因为它必须创建只能通过 <xref:System.Activities.NativeActivityContext> 类访问的书签。</span><span class="sxs-lookup"><span data-stu-id="7b264-129">The `WaitForInput` activity derives from the <xref:System.Activities.NativeActivity> class because it must create bookmarks, which are only accessible through the <xref:System.Activities.NativeActivityContext> class.</span></span>  
  
 <span data-ttu-id="7b264-130">该活动应用了三个特性，分别用于绑定设计器、添加可更新的泛型参数功能以及将默认泛型类型设置为 string。</span><span class="sxs-lookup"><span data-stu-id="7b264-130">The activity has three attributes applied to it for binding a designer, adding the generic argument feature that can be updated, and setting the default generic type to string.</span></span> <span data-ttu-id="7b264-131">该活动还具有下表中列出的自变量。</span><span class="sxs-lookup"><span data-stu-id="7b264-131">The activity also has the arguments  listed in the following table.</span></span>  
  
|<span data-ttu-id="7b264-132">**Name**</span><span class="sxs-lookup"><span data-stu-id="7b264-132">**Name**</span></span>|<span data-ttu-id="7b264-133">**类型**</span><span class="sxs-lookup"><span data-stu-id="7b264-133">**Type**</span></span>|<span data-ttu-id="7b264-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="7b264-134">**Description**</span></span>|  
|-|-|-|  
|<span data-ttu-id="7b264-135">TResult</span><span class="sxs-lookup"><span data-stu-id="7b264-135">TResult</span></span>|<span data-ttu-id="7b264-136">泛型参数 (TResult)</span><span class="sxs-lookup"><span data-stu-id="7b264-136">Generic argument (TResult)</span></span>|<span data-ttu-id="7b264-137">书签的类型。</span><span class="sxs-lookup"><span data-stu-id="7b264-137">Type of the bookmark.</span></span> <span data-ttu-id="7b264-138">这是在书签恢复时要传给书签的数据的类型。</span><span class="sxs-lookup"><span data-stu-id="7b264-138">This is the type of the data to be passed to the bookmark when resumed.</span></span>|  
|<span data-ttu-id="7b264-139">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="7b264-139">BookmarkName</span></span>|<span data-ttu-id="7b264-140">InArgument\<字符串 ></span><span class="sxs-lookup"><span data-stu-id="7b264-140">InArgument\<string></span></span>|<span data-ttu-id="7b264-141">书签的名称。</span><span class="sxs-lookup"><span data-stu-id="7b264-141">Name of the bookmark.</span></span>|  
|<span data-ttu-id="7b264-142">结果</span><span class="sxs-lookup"><span data-stu-id="7b264-142">Result</span></span>|<span data-ttu-id="7b264-143">InArgument\<TResult ></span><span class="sxs-lookup"><span data-stu-id="7b264-143">InArgument\<TResult></span></span>|<span data-ttu-id="7b264-144">书签恢复时要传递到活动的数据。</span><span class="sxs-lookup"><span data-stu-id="7b264-144">Data passed to the activity when the bookmark is resumed.</span></span>|  
  
## <a name="waitforinput-activity-designer"></a><span data-ttu-id="7b264-145">WaitForInput 活动设计器</span><span class="sxs-lookup"><span data-stu-id="7b264-145">WaitForInput activity designer</span></span>  
 <span data-ttu-id="7b264-146">`WaitForInput` 活动设计器在 WaitForInputDesigner.xaml 文件中实现。</span><span class="sxs-lookup"><span data-stu-id="7b264-146">The `WaitForInput` activity designer is implemented in the WaitForInputDesigner.xaml file.</span></span> <span data-ttu-id="7b264-147">`WaitForInput` 活动及其设计器包含在同一个程序集中。</span><span class="sxs-lookup"><span data-stu-id="7b264-147">The `WaitForInput` activity and its designer are included in the same assembly.</span></span> <span data-ttu-id="7b264-148">下图显示了工具箱中与程序集具有相同名称的类别中的 `WaitForInput` 活动。</span><span class="sxs-lookup"><span data-stu-id="7b264-148">The following graphic shows the `WaitForInput` activity in the toolbox within a category that has the same name as the assembly.</span></span>  
  
 <span data-ttu-id="7b264-149">![WaitForInput 工具箱屏幕快照](../../../../docs/framework/windows-workflow-foundation/samples/media/waitforinputtoolbox.jpg "WaitForInputToolbox")</span><span class="sxs-lookup"><span data-stu-id="7b264-149">![WaitForInput toolbox screenshot](../../../../docs/framework/windows-workflow-foundation/samples/media/waitforinputtoolbox.jpg "WaitForInputToolbox")</span></span>  
  
 <span data-ttu-id="7b264-150">下图显示了 `WaitForInput` 设计器。</span><span class="sxs-lookup"><span data-stu-id="7b264-150">The following graphic shows the `WaitForInput` designer.</span></span> <span data-ttu-id="7b264-151">因为 `WaitForInput` 活动是最基本的，所以设计器允许在设计器图面上直接设置它的所有参数。</span><span class="sxs-lookup"><span data-stu-id="7b264-151">Because, the `WaitForInput` activity is very basic, the designer allows setting all its arguments directly in the designer surface.</span></span>  
  
 <span data-ttu-id="7b264-152">![WaitForInput 活动设计器](../../../../docs/framework/windows-workflow-foundation/samples/media/waitforinputdesigner.jpg "WaitForInputDesigner")</span><span class="sxs-lookup"><span data-stu-id="7b264-152">![WaitForInput Activity Designer](../../../../docs/framework/windows-workflow-foundation/samples/media/waitforinputdesigner.jpg "WaitForInputDesigner")</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="7b264-153">使用此示例</span><span class="sxs-lookup"><span data-stu-id="7b264-153">To use this sample</span></span>  
  
1.  <span data-ttu-id="7b264-154">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 WaitForInput.sln 文件。</span><span class="sxs-lookup"><span data-stu-id="7b264-154">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WaitForInput.sln file.</span></span>  
  
2.  <span data-ttu-id="7b264-155">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="7b264-155">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="7b264-156">若要启用示例而不进行调试，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="7b264-156">To start the sample without debugging, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7b264-157">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="7b264-157">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7b264-158">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="7b264-158">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7b264-159">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="7b264-159">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7b264-160">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="7b264-160">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\WaitForInput`  
  
## <a name="see-also"></a><span data-ttu-id="7b264-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b264-161">See Also</span></span>
