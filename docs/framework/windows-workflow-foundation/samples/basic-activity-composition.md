---
title: "基本活动组合"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8eb909ce50c5faebf48339b07e8565fcd7afc718
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="basic-activity-composition"></a><span data-ttu-id="1e6c8-102">基本活动组合</span><span class="sxs-lookup"><span data-stu-id="1e6c8-102">Basic Activity Composition</span></span>
<span data-ttu-id="1e6c8-103">此示例演示如何编写自定义活动和系统提供的活动来生成更多自定义活动。</span><span class="sxs-lookup"><span data-stu-id="1e6c8-103">This sample demonstrates how to compose custom activities and system-provided activities to build more custom activities.</span></span>  
  
 <span data-ttu-id="1e6c8-104">使用 Survey 活动的工作流安排包含一系列问题的调查，然后输出接收到的响应。</span><span class="sxs-lookup"><span data-stu-id="1e6c8-104">The workflow using the Survey activity schedules the Survey with a list of questions, and then outputs the responses received.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="1e6c8-105">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="1e6c8-105">Sample Details</span></span>  
 <span data-ttu-id="1e6c8-106">此示例使用三个自定义活动。</span><span class="sxs-lookup"><span data-stu-id="1e6c8-106">This sample uses three custom activities.</span></span> <span data-ttu-id="1e6c8-107">`ReadLine`是一个简单<xref:System.Activities.NativeActivity>\<字符串 > 创建<xref:System.Activities.Bookmark>时计划，并将`Return`<xref:System.Activities.OutArgument%601>为与其值<xref:System.Activities.Bookmark>恢复。</span><span class="sxs-lookup"><span data-stu-id="1e6c8-107">`ReadLine` is a simple <xref:System.Activities.NativeActivity>\<string> that creates a <xref:System.Activities.Bookmark> when scheduled, and then sets the `Return`<xref:System.Activities.OutArgument%601> to the value with which the <xref:System.Activities.Bookmark> is resumed.</span></span> <span data-ttu-id="1e6c8-108">`Prompt`是<xref:System.Activities.Activity%601>\<字符串 > 采用<xref:System.Activities.InArgument%601>< 字符串\>名为`Text`，并返回响应中的用户`Result` <xref:System.Activities.OutArgument%601>\<字符串 >。</span><span class="sxs-lookup"><span data-stu-id="1e6c8-108">`Prompt` is an <xref:System.Activities.Activity%601>\<string> that takes an <xref:System.Activities.InArgument%601><string\> named `Text` and returns the users response in the `Result`<xref:System.Activities.OutArgument%601>\<string>.</span></span> <span data-ttu-id="1e6c8-109">`Prompt` 活动使用作为 .NET Framework 的一部分提供的 <xref:System.Activities.Statements.Sequence> 和 <xref:System.Activities.Statements.WriteLine> 活动，并且该活动还集成了自定义 `ReadLine` 活动以获取用户输入。</span><span class="sxs-lookup"><span data-stu-id="1e6c8-109">The `Prompt` activity uses the <xref:System.Activities.Statements.Sequence> and <xref:System.Activities.Statements.WriteLine> activities that ship as part of the .NET Framework, and also incorporates the custom `ReadLine` activity for getting user input.</span></span> <span data-ttu-id="1e6c8-110">最后一个自定义活动为 `Survey` 活动。</span><span class="sxs-lookup"><span data-stu-id="1e6c8-110">The last custom activity is the `Survey` activity.</span></span> <span data-ttu-id="1e6c8-111">它是<xref:System.Activities.Activity>< ICollection\<字符串 >>。</span><span class="sxs-lookup"><span data-stu-id="1e6c8-111">It is an <xref:System.Activities.Activity><ICollection\<string>>.</span></span>  <span data-ttu-id="1e6c8-112">此活动接受<xref:System.Activities.InArgument%601>< IEnumerable < 字符串\>> 名为`Questions`并填充`Result`out 使用响应的自变量。</span><span class="sxs-lookup"><span data-stu-id="1e6c8-112">This activity takes an <xref:System.Activities.InArgument%601><IEnumerable<string\>> named `Questions` and populates the `Result` out argument with the responses.</span></span> <span data-ttu-id="1e6c8-113">`Survey` 活动使用 .NET Framework 中的 <xref:System.Activities.Statements.ForEach%601>、<xref:System.Activities.Statements.Sequence> 和 <xref:System.Activities.Statements.AddToCollection%601>，并使用 `Prompt` 活动询问调查问题并获取响应。</span><span class="sxs-lookup"><span data-stu-id="1e6c8-113">The `Survey` activity uses <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> and <xref:System.Activities.Statements.AddToCollection%601> from the .NET Framework and employs the `Prompt` activity for asking the survey questions and getting responses.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1e6c8-114">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="1e6c8-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="1e6c8-115">打开**BasicActivityComposition.sln**示例中的解决方案[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1e6c8-115">Open the **BasicActivityComposition.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="1e6c8-116">生成和运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="1e6c8-116">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1e6c8-117">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="1e6c8-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1e6c8-118">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="1e6c8-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1e6c8-119">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="1e6c8-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1e6c8-120">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="1e6c8-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`