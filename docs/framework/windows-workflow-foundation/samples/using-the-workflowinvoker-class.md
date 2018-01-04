---
title: "使用 WorkflowInvoker 类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 553367916ff249118a8fcdd8273382402b90cfcc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-workflowinvoker-class"></a><span data-ttu-id="6c2bd-102">使用 WorkflowInvoker 类</span><span class="sxs-lookup"><span data-stu-id="6c2bd-102">Using the WorkflowInvoker Class</span></span>
<span data-ttu-id="6c2bd-103">此示例演示如何使用 <xref:System.Activities.WorkflowInvoker> 类将活动作为方法进行调用。</span><span class="sxs-lookup"><span data-stu-id="6c2bd-103">This sample demonstrates how to use the <xref:System.Activities.WorkflowInvoker> class to invoke an activity as if it were a method.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="6c2bd-104">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="6c2bd-104">Sample Details</span></span>  
 <span data-ttu-id="6c2bd-105">执行活动的最简单方式是使用 <xref:System.Activities.WorkflowInvoker> 类。</span><span class="sxs-lookup"><span data-stu-id="6c2bd-105">Using the <xref:System.Activities.WorkflowInvoker> class is the simplest way to execute an activity.</span></span> <span data-ttu-id="6c2bd-106">该类是为直接将活动作为方法调用运行而设计的。</span><span class="sxs-lookup"><span data-stu-id="6c2bd-106">It is designed for directly running an activity as if it were a method call.</span></span> <span data-ttu-id="6c2bd-107">它是一种性能极佳且易于使用的轻量 API，当执行活动不需要其他宿主变体提供的控件基础结构时使用此 API。</span><span class="sxs-lookup"><span data-stu-id="6c2bd-107">It is a lightweight, high-performing, easy to use API for use in scenarios where an activity’s execution does not require the control infrastructure provided by other hosting variations.</span></span>  
  
 <span data-ttu-id="6c2bd-108">此示例使用自定义活动派生自<xref:System.Activities.CodeActivity%601>< Int32\>名为`Add`后者添加两个<xref:System.Activities.InArgument%601>，`X`和`Y`，并返回`Result` <xref:System.Activities.OutArgument%601>。</span><span class="sxs-lookup"><span data-stu-id="6c2bd-108">The sample uses a custom activity that derives from <xref:System.Activities.CodeActivity%601><Int32\> named `Add` that adds two <xref:System.Activities.InArgument%601>, `X` and `Y`, and returns a `Result`<xref:System.Activities.OutArgument%601>.</span></span> <span data-ttu-id="6c2bd-109">(<xref:System.Activities.CodeActivity%601>\<T > 派生自<xref:System.Activities.Activity%601>< T\>，它具有<xref:System.Activities.OutArgument%601> \<T > 名为`Result`。)A `Dictionary`\<字符串、 对象 > 用于将自变量传递到通过调用的活动<xref:System.Activities.WorkflowInvoker>。</span><span class="sxs-lookup"><span data-stu-id="6c2bd-109">(<xref:System.Activities.CodeActivity%601>\<T> derives from <xref:System.Activities.Activity%601><T\>, which has an <xref:System.Activities.OutArgument%601>\<T> named `Result`.) A `Dictionary`\<string, object> is used to pass arguments into an activity being invoked through <xref:System.Activities.WorkflowInvoker>.</span></span> <span data-ttu-id="6c2bd-110">字典的键与调用的活动上的自变量名相对应。</span><span class="sxs-lookup"><span data-stu-id="6c2bd-110">The key of the dictionary corresponds to the name of an argument on the invoked activity.</span></span> <span data-ttu-id="6c2bd-111">与特定键关联的值将绑定到键所标识的参数。</span><span class="sxs-lookup"><span data-stu-id="6c2bd-111">The value associated with a particular key is bound to the argument identified by the key.</span></span>  
  
 <span data-ttu-id="6c2bd-112">此示例调用 <xref:System.Activities.WorkflowInvoker.Invoke%2A> 并传递一个字典，其中包含 `X` 和 `Y` 的值。</span><span class="sxs-lookup"><span data-stu-id="6c2bd-112">The sample calls <xref:System.Activities.WorkflowInvoker.Invoke%2A> and passes a dictionary that contains values for `X` and `Y`.</span></span> <span data-ttu-id="6c2bd-113"><xref:System.Activities.WorkflowInvoker> 类将这些值绑定到 `Add` 活动的参数，执行活动并返回结果。</span><span class="sxs-lookup"><span data-stu-id="6c2bd-113">The <xref:System.Activities.WorkflowInvoker> class binds these values to the `Add` activity’s arguments, executes the activity, and returns the result.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="6c2bd-114">使用此示例</span><span class="sxs-lookup"><span data-stu-id="6c2bd-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="6c2bd-115">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]，打开 Invoker.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="6c2bd-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Invoker.sln solution file.</span></span>  
  
2.  <span data-ttu-id="6c2bd-116">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="6c2bd-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="6c2bd-117">若要运行解决方案，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="6c2bd-117">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6c2bd-118">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="6c2bd-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6c2bd-119">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="6c2bd-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6c2bd-120">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="6c2bd-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6c2bd-121">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="6c2bd-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`