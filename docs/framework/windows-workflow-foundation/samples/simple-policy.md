---
title: "简单策略"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6a2798c753e1fc526b2f95801d49108a2aba9e8a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="simple-policy"></a><span data-ttu-id="8dead-102">简单策略</span><span class="sxs-lookup"><span data-stu-id="8dead-102">Simple Policy</span></span>
<span data-ttu-id="8dead-103">此示例演示如何在工作流中使用 <xref:System.Workflow.Activities.PolicyActivity> 活动。</span><span class="sxs-lookup"><span data-stu-id="8dead-103">This sample shows how to use a <xref:System.Workflow.Activities.PolicyActivity> activity in a workflow.</span></span>  
  
 <span data-ttu-id="8dead-104">此示例中的顺序工作流是通过使用 <xref:System.Workflow.Activities.PolicyActivity> 活动创建的。</span><span class="sxs-lookup"><span data-stu-id="8dead-104">The sequential workflow in this sample is created by using a <xref:System.Workflow.Activities.PolicyActivity> activity.</span></span> <span data-ttu-id="8dead-105">工作流定义 `orderValue`, `customerType`，以及用于定义产品折扣工作流的 `discount` 字段。</span><span class="sxs-lookup"><span data-stu-id="8dead-105">The workflow defines `orderValue`, `customerType`, and `discount` fields that are used to define a product discount workflow.</span></span> <span data-ttu-id="8dead-106">规则文件中定义的规则设置基于 `orderValue` 和 `customerType` 的折扣值。</span><span class="sxs-lookup"><span data-stu-id="8dead-106">The rules defined in the rules file set a discount value that is based on the `orderValue` and `customerType`.</span></span> <span data-ttu-id="8dead-107">`orderValue` 和 `customerType` 在 `SimplePolicyWorkflow` 类定义中设置，并且可加以更改以改变行为。</span><span class="sxs-lookup"><span data-stu-id="8dead-107">The `orderValue` and `customerType` are set in the `SimplePolicyWorkflow` class definition and can be changed to alter the behavior.</span></span> <span data-ttu-id="8dead-108">生成的折扣将写入 <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> 事件处理程序中的控制台，该事件处理程序是在 `SimplePolicyWorkflow` 类中定义的。</span><span class="sxs-lookup"><span data-stu-id="8dead-108">The resulting discount is written to the console in the <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> event handler that is defined in the `SimplePolicyWorkflow` class.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="8dead-109">生成示例</span><span class="sxs-lookup"><span data-stu-id="8dead-109">To build the sample</span></span>  
  
1.  <span data-ttu-id="8dead-110">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开解决方案。</span><span class="sxs-lookup"><span data-stu-id="8dead-110">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="8dead-111">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="8dead-111">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="8dead-112">按 Ctrl+F5 运行解决方案而不进行调试。</span><span class="sxs-lookup"><span data-stu-id="8dead-112">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="8dead-113">运行示例</span><span class="sxs-lookup"><span data-stu-id="8dead-113">To run the sample</span></span>  
  
-   <span data-ttu-id="8dead-114">在 SDK 命令提示窗口中，运行 SimplePolicy\bin\debug 文件夹（对于该示例的 Visual Basic 版本为 SimplePolicy\bin 文件夹）中的 .exe 文件，该文件夹位于该示例的主文件夹下。</span><span class="sxs-lookup"><span data-stu-id="8dead-114">In the SDK Command Prompt window, run the .exe file in the SimplePolicy\bin\debug folder (or the SimplePolicy\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8dead-115">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="8dead-115">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8dead-116">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="8dead-116">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8dead-117">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="8dead-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8dead-118">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="8dead-118">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## <a name="see-also"></a><span data-ttu-id="8dead-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8dead-119">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="8dead-120">高级的策略</span><span class="sxs-lookup"><span data-stu-id="8dead-120">Advanced Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)
