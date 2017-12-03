---
title: "自动确认模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 668aec65-78d3-4636-9c7b-deed643a18f9
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aaf4d72396438178d807f28ba8cb0ac5c5cb368e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="auto-confirm-pattern"></a><span data-ttu-id="380fb-102">自动确认模式</span><span class="sxs-lookup"><span data-stu-id="380fb-102">Auto-Confirm Pattern</span></span>
<span data-ttu-id="380fb-103">此示例包含三个用来说明自定义 `AutoConfirmScope` 活动的方案。</span><span class="sxs-lookup"><span data-stu-id="380fb-103">This sample consists of three scenarios that run illustrating a custom `AutoConfirmScope` activity.</span></span> <span data-ttu-id="380fb-104">第一个示例演示一个由四个可补偿活动组成的序列的成功执行，其中的第二个和第三个可补偿活动嵌套到 `AutoConfirmScope` 中。</span><span class="sxs-lookup"><span data-stu-id="380fb-104">The first sample shows the successful execution of a sequence of four compensable activities where the second and third are nested in an `AutoConfirmScope`.</span></span> <span data-ttu-id="380fb-105">第二个示例演示相同的序列，但在执行第四个 <xref:System.Activities.Statements.CompensableActivity> 之后会发生异常。</span><span class="sxs-lookup"><span data-stu-id="380fb-105">The second sample shows the same sequence with an exception occurring after the execution of the fourth <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="380fb-106">第三个方案演示相同的序列，但在第二个 `AutoConfirmScope` 完成后 <xref:System.Activities.Statements.CompensableActivity> 中会发生异常。</span><span class="sxs-lookup"><span data-stu-id="380fb-106">The third scenario shows the same sequence with an exception occurring in the `AutoConfirmScope` after the second <xref:System.Activities.Statements.CompensableActivity> completes.</span></span>  
  
 <span data-ttu-id="380fb-107">此示例演示自动确认模式，在此模式中，在成功完成范围之后立即确认所有的子级可补偿活动。</span><span class="sxs-lookup"><span data-stu-id="380fb-107">The sample demonstrates the auto-confirm pattern where all child compensable activities are confirmed upon successful completion of the scope.</span></span> <span data-ttu-id="380fb-108">此模式定义所有子级可补偿活动的生存期，在生存期过后，再也无法补偿或确认这些活动。</span><span class="sxs-lookup"><span data-stu-id="380fb-108">This pattern defines the lifetime of all child compensable activities, as they can no longer be compensated or confirmed.</span></span>  
  
 <span data-ttu-id="380fb-109">此范围包含一个 <xref:System.Activities.Statements.TryCatch>，其中的 <xref:System.Activities.Statements.TryCatch.Try%2A> 是一个内部 <xref:System.Activities.Statements.CompensableActivity>。</span><span class="sxs-lookup"><span data-stu-id="380fb-109">The scope consists of a <xref:System.Activities.Statements.TryCatch> where the <xref:System.Activities.Statements.TryCatch.Try%2A> is an internal <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="380fb-110">`AutoConfirmScope` 的用户指定主体是内部 <xref:System.Activities.Statements.CompensableActivity> 的主体。</span><span class="sxs-lookup"><span data-stu-id="380fb-110">The user-specified body of the `AutoConfirmScope` is the body of the inner <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="380fb-111">当此内部 <xref:System.Activities.Statements.CompensableActivity> 完成时，它会生成一个 <xref:System.Activities.Statements.CompensationToken> 作为 out 参数。</span><span class="sxs-lookup"><span data-stu-id="380fb-111">When this internal <xref:System.Activities.Statements.CompensableActivity> completes, it produces a <xref:System.Activities.Statements.CompensationToken> as an out-argument.</span></span> <span data-ttu-id="380fb-112">`AutoConfirmScope` 使用 <xref:System.Activities.Statements.TryCatch.Finally%2A> 检查是否已生成此令牌，如果已生成此令牌，则确认内部 <xref:System.Activities.Statements.CompensableActivity>。</span><span class="sxs-lookup"><span data-stu-id="380fb-112">The `AutoConfirmScope` uses a <xref:System.Activities.Statements.TryCatch.Finally%2A> to check whether the token has been produced and if it has then it confirms the inner <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="380fb-113">内部 <xref:System.Activities.Statements.CompensableActivity> 为可能存在于其主体中的任何可补偿活动调用默认补偿。</span><span class="sxs-lookup"><span data-stu-id="380fb-113">The inner <xref:System.Activities.Statements.CompensableActivity> invokes the default compensation for any compensable activities that may exist in its body.</span></span>  
  
 <span data-ttu-id="380fb-114">第一个方案演示成功执行工作流，并演示在工作流完成并确认第一个和第四个可补偿活动时，已确认第二个和第三个可补偿活动。</span><span class="sxs-lookup"><span data-stu-id="380fb-114">The first scenario shows successful execution of the workflow and demonstrates that the second and third compensable activities are already confirmed when the workflow completes and the first and fourth are confirmed.</span></span> <span data-ttu-id="380fb-115">这将产生 3、2、4 和 1 的确认顺序。</span><span class="sxs-lookup"><span data-stu-id="380fb-115">This produces a confirmation order of three, two, four, and one.</span></span>  
  
 <span data-ttu-id="380fb-116">第二个方案演示完成第四个可补偿活动之后的异常。</span><span class="sxs-lookup"><span data-stu-id="380fb-116">The second scenario shows an exception after the four compensable activities have completed.</span></span> <span data-ttu-id="380fb-117">因为可补偿活动 2 和 3 已经得到确认，所以不影响它们，但要补偿可补偿活动 1 和 4。</span><span class="sxs-lookup"><span data-stu-id="380fb-117">Because compensable activities two and three are already confirmed they are unaffected but one and four are compensated.</span></span> <span data-ttu-id="380fb-118">这将产生确认 3、确认 2、补偿 4 和补偿 1。</span><span class="sxs-lookup"><span data-stu-id="380fb-118">This produces confirm three, confirm two, compensate four and compensate one.</span></span>  
  
 <span data-ttu-id="380fb-119">最后一个方案演示未成功执行 `AutoConfirmScope`。</span><span class="sxs-lookup"><span data-stu-id="380fb-119">The final scenario shows unsuccessful execution of the `AutoConfirmScope`.</span></span> <span data-ttu-id="380fb-120">在此方案中，在完成第二个 <xref:System.Activities.Statements.CompensableActivity> 之后发生异常。</span><span class="sxs-lookup"><span data-stu-id="380fb-120">In this scenario, an exception occurs after the completion of the second <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="380fb-121">因为未执行第三个和第四个可补偿活动，所以不影响它们。</span><span class="sxs-lookup"><span data-stu-id="380fb-121">Because the third and fourth compensable activities have not executed, they are unaffected.</span></span> <span data-ttu-id="380fb-122">因为此范围未成功完成，所以第二个 <xref:System.Activities.Statements.CompensableActivity> 未得到确认。</span><span class="sxs-lookup"><span data-stu-id="380fb-122">Because the scope did not complete successfully, the second <xref:System.Activities.Statements.CompensableActivity> does not get confirmed.</span></span> <span data-ttu-id="380fb-123">这将产生先 2 后 1 的补偿顺序。</span><span class="sxs-lookup"><span data-stu-id="380fb-123">This produces and compensation order of two then one.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="380fb-124">使用此示例</span><span class="sxs-lookup"><span data-stu-id="380fb-124">To use this sample</span></span>  
  
1.  <span data-ttu-id="380fb-125">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 AutoConfirmSample.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="380fb-125">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the AutoConfirmSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="380fb-126">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="380fb-126">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="380fb-127">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="380fb-127">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="380fb-128">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="380fb-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="380fb-129">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="380fb-129">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="380fb-130">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="380fb-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="380fb-131">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="380fb-131">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Compensation\AutoConfirm`