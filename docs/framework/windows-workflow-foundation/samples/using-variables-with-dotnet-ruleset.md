---
title: "将变量用于 .NET Framework 3.5 规则集"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2656cc5d8add0027d6bf038d5de735ebccd2d96d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-variables-with-a-net-framework-35-ruleset"></a><span data-ttu-id="468f5-102">将变量用于 .NET Framework 3.5 规则集</span><span class="sxs-lookup"><span data-stu-id="468f5-102">Using Variables with a .NET Framework 3.5 Ruleset</span></span>
<span data-ttu-id="468f5-103">此示例演示如何创建一个工作流，该工作流使用 <xref:System.Activities.Statements.Interop> 活动来集成在 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 中编写并应用了策略和规则的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="468f5-103">This sample demonstrates how to create a workflow that uses the <xref:System.Activities.Statements.Interop> activity to integrate a custom activity written in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] that uses policy and rules.</span></span> <span data-ttu-id="468f5-104">该工作流将数据传递给此自定义活动，采用的方式是将变量绑定到此自定义活动公开的依赖项属性。</span><span class="sxs-lookup"><span data-stu-id="468f5-104">The workflow passes data to the custom activity by binding variables to the dependency properties exposed by the custom activity.</span></span>  
  
## <a name="sample-walkthrough"></a><span data-ttu-id="468f5-105">示例演练</span><span class="sxs-lookup"><span data-stu-id="468f5-105">Sample walkthrough</span></span>  
  
#### <a name="to-examine-travelrulelibrary"></a><span data-ttu-id="468f5-106">检查 TravelRuleLibrary</span><span class="sxs-lookup"><span data-stu-id="468f5-106">To examine TravelRuleLibrary</span></span>  
  
1.  <span data-ttu-id="468f5-107">使用 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]，打开 InteropWith35RuleSet.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="468f5-107">Using [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="468f5-108">在工作流设计器中打开 TravelRuleSet.cs。</span><span class="sxs-lookup"><span data-stu-id="468f5-108">Open the TravelRuleSet.cs in the workflow designer.</span></span>  
  
     <span data-ttu-id="468f5-109">这将显示包含 <xref:System.Workflow.Activities.PolicyActivity> 的自定义顺序活动。</span><span class="sxs-lookup"><span data-stu-id="468f5-109">A custom sequential activity that contains a <xref:System.Workflow.Activities.PolicyActivity> is displayed.</span></span>  
  
3.  <span data-ttu-id="468f5-110">双击 DiscountPolicy 策略活动以检查规则。</span><span class="sxs-lookup"><span data-stu-id="468f5-110">Double-click the DiscountPolicy policy activity to examine the rules.</span></span>  
  
     <span data-ttu-id="468f5-111">规则编辑器将弹出，其中显示了规则。</span><span class="sxs-lookup"><span data-stu-id="468f5-111">The Rules editor pops up to show the rules.</span></span>  
  
4.  <span data-ttu-id="468f5-112">右键单击`DiscountPolicy`和选择**查看代码**选项以检查活动的 C# 代码旁边的代码。</span><span class="sxs-lookup"><span data-stu-id="468f5-112">Right click the `DiscountPolicy` and select the **View Code** option to examine the code beside C# code for the activity.</span></span>  
  
     <span data-ttu-id="468f5-113">观察 `DiscountLevel` 的依赖项属性设置。</span><span class="sxs-lookup"><span data-stu-id="468f5-113">Observe the dependency property setting for `DiscountLevel`.</span></span> <span data-ttu-id="468f5-114">这等效于 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] 中的参数。</span><span class="sxs-lookup"><span data-stu-id="468f5-114">This is equivalent to arguments in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="468f5-115">自变量，请参阅[变量和自变量](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="468f5-115"> arguments, see [Variables and Arguments](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).</span></span>  
  
## <a name="interopwith35ruleset"></a><span data-ttu-id="468f5-116">InteropWith35RuleSet</span><span class="sxs-lookup"><span data-stu-id="468f5-116">InteropWith35RuleSet</span></span>  
 <span data-ttu-id="468f5-117">这是一个顺序工作流项目，该项目使用 <xref:System.Activities.Statements.Interop> 活动与 `TravelRuleLibrary` 项目中创建的自定义规则集集成。</span><span class="sxs-lookup"><span data-stu-id="468f5-117">This is a sequential workflow project that uses the <xref:System.Activities.Statements.Interop> activity to integrate with the custom Rule set created in the `TravelRuleLibrary` project.</span></span> <span data-ttu-id="468f5-118">变量是在顶级 <xref:System.Activities.Statements.Sequence> 活动上创建的。</span><span class="sxs-lookup"><span data-stu-id="468f5-118">Variables are created on the top level <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="468f5-119"><xref:System.Activities.Statements.Interop> 活动用于与 `TravelRuleSet` 活动进行的集成。</span><span class="sxs-lookup"><span data-stu-id="468f5-119">The <xref:System.Activities.Statements.Interop> activity is used to integrate with the `TravelRuleSet` activity.</span></span> <span data-ttu-id="468f5-120">在 <xref:System.Activities.Statements.Sequence> 上声明的变量用于绑定到依赖项属性。</span><span class="sxs-lookup"><span data-stu-id="468f5-120">The variables that are declared on the <xref:System.Activities.Statements.Sequence> are used to bind to the dependency properties.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="468f5-121">使用此示例</span><span class="sxs-lookup"><span data-stu-id="468f5-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="468f5-122">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]，打开 InteropWith35RuleSet.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="468f5-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="468f5-123">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="468f5-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="468f5-124">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="468f5-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="468f5-125">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="468f5-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="468f5-126">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="468f5-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="468f5-127">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="468f5-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="468f5-128">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="468f5-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`