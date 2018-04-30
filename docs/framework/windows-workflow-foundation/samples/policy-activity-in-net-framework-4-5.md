---
title: .NET Framework 4.5 中的策略活动
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e375e0c-d7c1-4d69-88ab-36d52db0aa7e
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5ff750942a2d05310669361e83a10a5acefbcbd4
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="policy-activity-in-net-framework-45"></a><span data-ttu-id="1006c-102">.NET Framework 4.5 中的策略活动</span><span class="sxs-lookup"><span data-stu-id="1006c-102">Policy Activity in .NET Framework 4.5</span></span>
<span data-ttu-id="1006c-103">Policy4 活动允许 Windows Workflow Foundation 中[!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)](WF 3.5)<xref:System.Workflow.Activities.Rules.RuleSet>对象用于在 Windows Workflow Foundation 中[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)](WF 4.5) 直接通过 WF 3.5 中附带的规则引擎。</span><span class="sxs-lookup"><span data-stu-id="1006c-103">The Policy4 activity allows Windows Workflow Foundation in [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> objects to be used in Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) directly by using the rules engine that is shipped in WF 3.5.</span></span> <span data-ttu-id="1006c-104">通过使用此活动，可以创建和执行 WF 3.5 <xref:System.Workflow.Activities.Rules.RuleSet>。</span><span class="sxs-lookup"><span data-stu-id="1006c-104">By using this activity, you can create and execute a WF 3.5 <xref:System.Workflow.Activities.Rules.RuleSet>.</span></span> <span data-ttu-id="1006c-105">有关 Windows Workflow Foundation 的一部分包含的 WF 3.5 规则引擎的详细信息，请阅读 Windows Workflow Foundation 规则引擎简介。</span><span class="sxs-lookup"><span data-stu-id="1006c-105">For more information about WF 3.5 Rules Engine included as part of Windows Workflow Foundation, please read Introduction to the Windows Workflow Foundation Rules Engine.</span></span> <span data-ttu-id="1006c-106">有关迁移的详细信息中的 WF 规则[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]，请阅读[迁移指南](../../../../docs/framework/windows-workflow-foundation/migration-guidance.md)。</span><span class="sxs-lookup"><span data-stu-id="1006c-106">For more information about migrating rules to WF in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)], please read [Migration Guidance](../../../../docs/framework/windows-workflow-foundation/migration-guidance.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1006c-107">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="1006c-107">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1006c-108">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="1006c-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1006c-109">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="1006c-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1006c-110">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="1006c-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-Policy4`  
  
## <a name="projects-in-this-sample"></a><span data-ttu-id="1006c-111">此示例中的项目</span><span class="sxs-lookup"><span data-stu-id="1006c-111">Projects in this Sample</span></span>  
  
|<span data-ttu-id="1006c-112">项目名称</span><span class="sxs-lookup"><span data-stu-id="1006c-112">Project Name</span></span>|<span data-ttu-id="1006c-113">描述</span><span class="sxs-lookup"><span data-stu-id="1006c-113">Description</span></span>|<span data-ttu-id="1006c-114">主要文件</span><span class="sxs-lookup"><span data-stu-id="1006c-114">Main Files</span></span>|  
|------------------|-----------------|----------------|  
|<span data-ttu-id="1006c-115">Policy4</span><span class="sxs-lookup"><span data-stu-id="1006c-115">Policy4</span></span>|<span data-ttu-id="1006c-116">包含 Policy4 活动及其 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 设计器。</span><span class="sxs-lookup"><span data-stu-id="1006c-116">Contains the Policy4 activity and its [!INCLUDE[wf1](../../../../includes/wf1-md.md)] designer.</span></span>|<span data-ttu-id="1006c-117">**Policy4.cs**: Policy4 活动定义。</span><span class="sxs-lookup"><span data-stu-id="1006c-117">**Policy4.cs**: Policy4 activity definition.</span></span><br /><br /> <span data-ttu-id="1006c-118">**PolicyDesigner.xaml**: Policy4 活动的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="1006c-118">**PolicyDesigner.xaml**: Custom designer for Policy4 activity.</span></span> <span data-ttu-id="1006c-119">它使用的规则编辑器 ([RuleSetDialog 类](http://go.microsoft.com/fwlink/?LinkId=150378)) 从[!INCLUDE[wf1](../../../../includes/wf1-md.md)]规则引擎。</span><span class="sxs-lookup"><span data-stu-id="1006c-119">It uses the rules editor ([RuleSetDialog Class](http://go.microsoft.com/fwlink/?LinkId=150378)) from [!INCLUDE[wf1](../../../../includes/wf1-md.md)] rules engine.</span></span>|  
|<span data-ttu-id="1006c-120">ImperativeCodeClientSample</span><span class="sxs-lookup"><span data-stu-id="1006c-120">ImperativeCodeClientSample</span></span>|<span data-ttu-id="1006c-121">一个示例客户端应用程序，此应用程序使用命令性 C# 代码（未使用任何 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 设计器）来配置和运行使用 Policy4 应用程序的工作流。</span><span class="sxs-lookup"><span data-stu-id="1006c-121">Sample client application that configures and runs a workflow using a Policy4 application using imperative C# code (no [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Designer used).</span></span>|<span data-ttu-id="1006c-122">**ApplyDiscount.rules**： 使用文件[!INCLUDE[wf1](../../../../includes/wf1-md.md)]规则定义。</span><span class="sxs-lookup"><span data-stu-id="1006c-122">**ApplyDiscount.rules**: File with [!INCLUDE[wf1](../../../../includes/wf1-md.md)] rule definitions.</span></span><br /><br /> <span data-ttu-id="1006c-123">**Order.cs**： 表示客户订单的类型。</span><span class="sxs-lookup"><span data-stu-id="1006c-123">**Order.cs**: Type that represents a customer order.</span></span> <span data-ttu-id="1006c-124">规则适用于此类型的对象。</span><span class="sxs-lookup"><span data-stu-id="1006c-124">Rules are applied to objects of this type.</span></span><br /><br /> <span data-ttu-id="1006c-125">**Program.cs**： 配置和运行具有 Policy4 活动要应用于 Order 对象的实例的 ApplyDiscount.rules 中定义的规则的工作流。</span><span class="sxs-lookup"><span data-stu-id="1006c-125">**Program.cs**: Configures and runs a workflow that has a Policy4 activity to apply rules defined in ApplyDiscount.rules to instances of Order objects.</span></span><br /><br /> <span data-ttu-id="1006c-126">**App.config**： 带有规则文件的路径的配置文件。</span><span class="sxs-lookup"><span data-stu-id="1006c-126">**App.config**: Configuration file with the path of the rules file.</span></span>|  
|<span data-ttu-id="1006c-127">DesignerClientSample</span><span class="sxs-lookup"><span data-stu-id="1006c-127">DesignerClientSample</span></span>|<span data-ttu-id="1006c-128">一个示例客户端应用程序，此应用程序在 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 设计器中配置和运行使用 Policy4 应用程序的工作流。</span><span class="sxs-lookup"><span data-stu-id="1006c-128">Sample client application that configures and runs a workflow using a Policy4 application in the [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Designer.</span></span>|<span data-ttu-id="1006c-129">**Sequence1.xaml**： 使用 Policy4 活动执行规则计算的顺序工作流。</span><span class="sxs-lookup"><span data-stu-id="1006c-129">**Sequence1.xaml**: Sequential workflow that uses a Policy4 activity to perform rule evaluations.</span></span><br /><br /> <span data-ttu-id="1006c-130">`Program.cs`：运行 Sequence1.xaml 中定义的工作流的实例。</span><span class="sxs-lookup"><span data-stu-id="1006c-130">`Program.cs`: Runs an instance of the workflow defined in Sequence1.xaml.</span></span>|  
  
## <a name="the-policy4-activity"></a><span data-ttu-id="1006c-131">Policy4 活动</span><span class="sxs-lookup"><span data-stu-id="1006c-131">The Policy4 Activity</span></span>  
 <span data-ttu-id="1006c-132">Policy4 活动是一个从 <xref:System.Activities.NativeActivity%601> 派生的类，它允许工作流执行 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] RuleSets。</span><span class="sxs-lookup"><span data-stu-id="1006c-132">The Policy4 activity is a class that derives from <xref:System.Activities.NativeActivity%601> that allows workflows to execute [!INCLUDE[wf1](../../../../includes/wf1-md.md)] RuleSets.</span></span> <span data-ttu-id="1006c-133">下面的代码示例是活动的公共 OM 的简化定义。</span><span class="sxs-lookup"><span data-stu-id="1006c-133">The following code example is a simplified definition of the public OM of the activity.</span></span>  
  
```csharp  
public class Policy4Activity<TResult>: NativeActivity<TResult>  
{  
    public RuleSet RuleSet  
  
    [IsRequired]  
    public InArgument Input  
  
    public OutArgument<ValidationErrorCollection> ValidationErrors  
}  
```  
  
|<span data-ttu-id="1006c-134">属性</span><span class="sxs-lookup"><span data-stu-id="1006c-134">Property</span></span>|<span data-ttu-id="1006c-135">描述</span><span class="sxs-lookup"><span data-stu-id="1006c-135">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="1006c-136">RuleSet</span><span class="sxs-lookup"><span data-stu-id="1006c-136">RuleSet</span></span>|<span data-ttu-id="1006c-137">WF [RuleSet 类](http://go.microsoft.com/fwlink/?LinkId=150379)执行活动时要计算的.NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="1006c-137">The WF [RuleSet Class](http://go.microsoft.com/fwlink/?LinkId=150379) for .NET Framework 3.5 to be evaluated when the activity is executed.</span></span>|  
|<span data-ttu-id="1006c-138">TargetObject</span><span class="sxs-lookup"><span data-stu-id="1006c-138">TargetObject</span></span>|<span data-ttu-id="1006c-139">依据对象中的规则[RuleSet 类](http://go.microsoft.com/fwlink/?LinkId=150379)进行评估。</span><span class="sxs-lookup"><span data-stu-id="1006c-139">The object against which the Rules in the [RuleSet Class](http://go.microsoft.com/fwlink/?LinkId=150379) are evaluated.</span></span>|  
|<span data-ttu-id="1006c-140">ValidationError</span><span class="sxs-lookup"><span data-stu-id="1006c-140">ValidationError</span></span>|<span data-ttu-id="1006c-141">返回的验证错误的列表[!INCLUDE[wf1](../../../../includes/wf1-md.md)]验证时的.NET Framework 3.5 规则引擎[RuleSet 类](http://go.microsoft.com/fwlink/?LinkId=150379)对目标对象之前执行。</span><span class="sxs-lookup"><span data-stu-id="1006c-141">The list of validation errors returned by the [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Rule Engine for .NET Framework 3.5 when validating the [RuleSet Class](http://go.microsoft.com/fwlink/?LinkId=150379) against the target object before execution.</span></span>|  
  
## <a name="policy4-activity-designer"></a><span data-ttu-id="1006c-142">Policy4 活动设计器</span><span class="sxs-lookup"><span data-stu-id="1006c-142">Policy4 Activity Designer</span></span>  
 <span data-ttu-id="1006c-143">Policy4 设计器增加了一项功能，利用此功能，无需编写代码即可配置 Policy4 活动。</span><span class="sxs-lookup"><span data-stu-id="1006c-143">The Policy4 designer adds the capability to configure a Policy4 activity without the need to write code.</span></span> <span data-ttu-id="1006c-144">生成解决方案之后, 它可在工具箱的部分中**Microsoft.Samples.Activities.Rules**。</span><span class="sxs-lookup"><span data-stu-id="1006c-144">After building the solution, it can be found in the toolbox in the section **Microsoft.Samples.Activities.Rules**.</span></span>  
  
 <span data-ttu-id="1006c-145">利用 WF 设计器可配置目标对象和 RuleSet。</span><span class="sxs-lookup"><span data-stu-id="1006c-145">The WF Designer allows you to configure a target object and a RuleSet.</span></span> <span data-ttu-id="1006c-146">当**编辑 RuleSet**单击按钮时，WF [RuleSetDialog 类](http://go.microsoft.com/fwlink/?LinkId=150378)为[!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]显示。</span><span class="sxs-lookup"><span data-stu-id="1006c-146">When the **Edit RuleSet** button is clicked, the WF [RuleSetDialog Class](http://go.microsoft.com/fwlink/?LinkId=150378) for [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] is displayed.</span></span> <span data-ttu-id="1006c-147">此对话框是重新承载的 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 规则编辑器。</span><span class="sxs-lookup"><span data-stu-id="1006c-147">This dialog is the re-hosted [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] Rules Editor.</span></span> <span data-ttu-id="1006c-148">使用该编辑器可创建和编辑 Policy4 活动执行的规则。</span><span class="sxs-lookup"><span data-stu-id="1006c-148">Use the editor to create and edit the rules that the Policy4 activity executes.</span></span>  
  
## <a name="using-this-sample"></a><span data-ttu-id="1006c-149">使用此示例</span><span class="sxs-lookup"><span data-stu-id="1006c-149">Using this Sample</span></span>  
 <span data-ttu-id="1006c-150">无需进行特殊设置即可运行此示例。</span><span class="sxs-lookup"><span data-stu-id="1006c-150">No special set up is required to run this sample.</span></span> <span data-ttu-id="1006c-151">只需在 Visual Studio 中打开解决方案，然后按 F5 即可运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="1006c-151">Just open the solution in Visual Studio, and press F5 to run the application.</span></span>  
  
 <span data-ttu-id="1006c-152">此示例包含两个客户端应用程序，即 ImperativeCodeClientSample 和 DesignerClientSample。</span><span class="sxs-lookup"><span data-stu-id="1006c-152">This sample contains two client applications: ImperativeCodeClientSample and DesignerClientSample.</span></span> <span data-ttu-id="1006c-153">ImperativeCodeClientSample 客户端演示如何使用 C# 命令性代码来配置和运行 Policy4 活动。</span><span class="sxs-lookup"><span data-stu-id="1006c-153">The ImperativeCodeClientSample client shows how to configure and run the Policy40 activity using C# imperative code.</span></span> <span data-ttu-id="1006c-154">DesignerClientSample 演示如何使用设计器配置和运行 Policy4 活动。</span><span class="sxs-lookup"><span data-stu-id="1006c-154">The DesignerClientSample shows how to configure and run the Policy4 activity using the designer.</span></span>  
  
#### <a name="to-run-the-imperativecodeclientsample-client-application"></a><span data-ttu-id="1006c-155">运行 ImperativeCodeClientSample 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="1006c-155">To run the ImperativeCodeClientSample client application</span></span>  
  
1.  <span data-ttu-id="1006c-156">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 Policy4Sample.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="1006c-156">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the Policy4Sample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="1006c-157">在**解决方案资源管理器**，右键单击**ImperativeCodeClientSample**项目，然后选择**设为启动项目**。</span><span class="sxs-lookup"><span data-stu-id="1006c-157">In **Solution Explorer**, right-click the **ImperativeCodeClientSample** project and then select **Set as startup project**.</span></span>  
  
3.  <span data-ttu-id="1006c-158">若要运行项目，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="1006c-158">To run the project, press CTRL+F5.</span></span>  
  
#### <a name="to-run-the-imperativecodeclientsample-client-application"></a><span data-ttu-id="1006c-159">运行 ImperativeCodeClientSample 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="1006c-159">To run the ImperativeCodeClientSample client application</span></span>  
  
1.  <span data-ttu-id="1006c-160">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 Policy4Sample.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="1006c-160">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the Policy4Sample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="1006c-161">在**解决方案资源管理器**，右键单击**DesignerClientSample**项目。</span><span class="sxs-lookup"><span data-stu-id="1006c-161">In **Solution Explorer**, right-click the **DesignerClientSample** project.</span></span>  
  
    -   <span data-ttu-id="1006c-162">选择**设为启动项目**。</span><span class="sxs-lookup"><span data-stu-id="1006c-162">Select **Set as startup project**.</span></span>  
  
3.  <span data-ttu-id="1006c-163">若要编译项目，请按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="1006c-163">To compile the project, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="1006c-164">若要运行项目，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="1006c-164">To run the project, press CTRL+F5.</span></span>