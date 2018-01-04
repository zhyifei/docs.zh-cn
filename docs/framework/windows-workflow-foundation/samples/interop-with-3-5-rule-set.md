---
title: "与 3.5 规则集交互"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 969f3295-d874-428c-a9c6-623e3d578e51
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 854aeac936d3f911f2613c6e315ab81347f64a25
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="interop-with-35-rule-set"></a><span data-ttu-id="47c9c-102">与 3.5 规则集交互</span><span class="sxs-lookup"><span data-stu-id="47c9c-102">Interop with 3.5 Rule Set</span></span>
<span data-ttu-id="47c9c-103">此示例演示如何使用<xref:System.Activities.Statements.Interop>活动中的自定义活动与集成[!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]使用<!--zz <xref:System.Workflow.Activities.Policy> -->`System.Workflow.Activities.Policy`和规则。</span><span class="sxs-lookup"><span data-stu-id="47c9c-103">This sample demonstrates the use of the <xref:System.Activities.Statements.Interop> activity to integrate with a custom activity in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] using <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` and rules.</span></span> <span data-ttu-id="47c9c-104">此示例通过将 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] 变量绑定到由自定义活动公开的依赖项属性，将数据传递给自定义活动。</span><span class="sxs-lookup"><span data-stu-id="47c9c-104">It passes data to the custom activity by binding [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] variables to the dependency properties exposed by the custom activity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47c9c-105">惠?</span><span class="sxs-lookup"><span data-stu-id="47c9c-105">Requirements</span></span>  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]  
  
2.  [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]  
  
3.  [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]  
  
## <a name="demonstrates"></a><span data-ttu-id="47c9c-106">演示</span><span class="sxs-lookup"><span data-stu-id="47c9c-106">Demonstrates</span></span>  
 <span data-ttu-id="47c9c-107"><xref:System.Activities.Statements.Interop>活动， <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy`中的活动[!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]具有依赖项属性</span><span class="sxs-lookup"><span data-stu-id="47c9c-107"><xref:System.Activities.Statements.Interop> activity, <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` activity in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] with dependency properties</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="47c9c-108">讨论</span><span class="sxs-lookup"><span data-stu-id="47c9c-108">Discussion</span></span>  
 <span data-ttu-id="47c9c-109">此示例演示与 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 活动集成的集成方案之一。</span><span class="sxs-lookup"><span data-stu-id="47c9c-109">The sample demonstrates one of the integration scenarios for integrating with a [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] activity.</span></span> <span data-ttu-id="47c9c-110">此示例包括[!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]时，将调用的自定义活动<!--zz <xref:System.Workflow.Activities.Policy> -->`System.Workflow.Activities.Policy`活动。</span><span class="sxs-lookup"><span data-stu-id="47c9c-110">This sample includes a [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] custom activity that invokes a <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` activity.</span></span>  
  
## <a name="travelrulelibrary"></a><span data-ttu-id="47c9c-111">TravelRuleLibrary</span><span class="sxs-lookup"><span data-stu-id="47c9c-111">TravelRuleLibrary</span></span>  
 <span data-ttu-id="47c9c-112">在设计器中打开 TravelRuleSet.cs 将会显示一个包含 Policy 活动的自定义顺序活动，如下所示。</span><span class="sxs-lookup"><span data-stu-id="47c9c-112">Opening TravelRuleSet.cs in the designer shows a custom sequential activity that contains a Policy activity as follows</span></span>  
  
 <span data-ttu-id="47c9c-113">![Interop 活动](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulespolicy.jpg "InteropRulesPolicy")</span><span class="sxs-lookup"><span data-stu-id="47c9c-113">![Interop Activity](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulespolicy.jpg "InteropRulesPolicy")</span></span>  
  
 <span data-ttu-id="47c9c-114">双击**DiscountPolicy**策略活动以检查规则。</span><span class="sxs-lookup"><span data-stu-id="47c9c-114">Double-click the **DiscountPolicy** policy activity to examine the rules.</span></span> <span data-ttu-id="47c9c-115">规则编辑器将会出现并显示规则。</span><span class="sxs-lookup"><span data-stu-id="47c9c-115">The Rules editor appears to show the rules.</span></span>  
  
 <span data-ttu-id="47c9c-116">![规则集编辑器](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesruleseteditor.jpg "InteropRulesRuleSetEditor")</span><span class="sxs-lookup"><span data-stu-id="47c9c-116">![Rule Set Editor](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesruleseteditor.jpg "InteropRulesRuleSetEditor")</span></span>  
  
 <span data-ttu-id="47c9c-117">右键单击**DiscountPolicy**活动，并选择**查看代码**选项以检查的代码旁置 C# 代码，用此活动。</span><span class="sxs-lookup"><span data-stu-id="47c9c-117">Right-click the **DiscountPolicy** activity and select the **View Code** option to examine the code-beside C# code that goes with this activity.</span></span> <span data-ttu-id="47c9c-118">观察 `DiscountLevel` 的依赖项属性设置。</span><span class="sxs-lookup"><span data-stu-id="47c9c-118">Observe the dependency property setting for `DiscountLevel`.</span></span> <span data-ttu-id="47c9c-119">这等效于 <xref:System.Activities.Argument> 中的 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="47c9c-119">This is equivalent to an <xref:System.Activities.Argument> in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span></span>  
  
```  
public static DependencyProperty DiscountLevelProperty = DependencyProperty.Register("DiscountLevel", typeof(int), typeof(TravelRuleSet));  
  
[DescriptionAttribute("DiscountLevel")]  
[CategoryAttribute("DiscountLevel Category")]  
[BrowsableAttribute(true)]  
[DesignerSerializationVisibilityAttribute(DesignerSerializationVisibility.Visible)]  
public int DiscountLevel  
{  
   get  
   {  
return ((int)base.GetValue(TravelRuleSet.DiscountLevelProperty)));  
   }  
   set  
   {  
base.SetValue(TravelRuleSet.DiscountLevelProperty, value);  
   }  
}  
```  
  
## <a name="interopwith35ruleset"></a><span data-ttu-id="47c9c-120">InteropWith35RuleSet</span><span class="sxs-lookup"><span data-stu-id="47c9c-120">InteropWith35RuleSet</span></span>  
 <span data-ttu-id="47c9c-121">这是一个 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] 顺序工作流项目，该项目使用 <xref:System.Activities.Statements.Interop> 活动与在 TravelRuleLibrary 项目中创建的自定义规则集进行集成。</span><span class="sxs-lookup"><span data-stu-id="47c9c-121">This is a [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] sequential workflow project that uses the <xref:System.Activities.Statements.Interop> activity to integrate with the custom rule set created in the TravelRuleLibrary project.</span></span> <span data-ttu-id="47c9c-122">变量是在顶级 <xref:System.Activities.Statements.Sequence> 上创建的，如下所示。</span><span class="sxs-lookup"><span data-stu-id="47c9c-122">Variables are created on the top-level <xref:System.Activities.Statements.Sequence> as follows.</span></span>  
  
 <span data-ttu-id="47c9c-123">![变量](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesvariables.jpg "InteropRulesVariables")</span><span class="sxs-lookup"><span data-stu-id="47c9c-123">![Variables](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesvariables.jpg "InteropRulesVariables")</span></span>  
  
 <span data-ttu-id="47c9c-124">![解决方案资源管理器](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulessolutionexplorer.jpg "InteropRulesSolutionExplorer")</span><span class="sxs-lookup"><span data-stu-id="47c9c-124">![Solution Explorer](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulessolutionexplorer.jpg "InteropRulesSolutionExplorer")</span></span>  
  
 <span data-ttu-id="47c9c-125">最后，<xref:System.Activities.Statements.Interop> 活动用于与 TravelRuleSet 进行集成。</span><span class="sxs-lookup"><span data-stu-id="47c9c-125">Lastly, the <xref:System.Activities.Statements.Interop> activity is used to integrate with the TravelRuleSet.</span></span> <span data-ttu-id="47c9c-126">前面在 <xref:System.Activities.Statements.Sequence> 上声明的变量用于绑定到依赖项属性。</span><span class="sxs-lookup"><span data-stu-id="47c9c-126">The variables that were declared earlier on the <xref:System.Activities.Statements.Sequence> are used to bind to the dependency properties.</span></span>  
  
 <span data-ttu-id="47c9c-127">![活动类型](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprules.jpg "InteropRules")</span><span class="sxs-lookup"><span data-stu-id="47c9c-127">![Activity Type](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprules.jpg "InteropRules")</span></span>  
  
 <span data-ttu-id="47c9c-128">![箭头](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesarrow.jpg "InteropRulesArrow")</span><span class="sxs-lookup"><span data-stu-id="47c9c-128">![Arrow](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesarrow.jpg "InteropRulesArrow")</span></span>  
  
 <span data-ttu-id="47c9c-129">![属性](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesproperties.jpg "InteropRulesProperties")</span><span class="sxs-lookup"><span data-stu-id="47c9c-129">![Properties](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesproperties.jpg "InteropRulesProperties")</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="47c9c-130">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="47c9c-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="47c9c-131">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="47c9c-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="47c9c-132">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="47c9c-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="47c9c-133">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="47c9c-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`
