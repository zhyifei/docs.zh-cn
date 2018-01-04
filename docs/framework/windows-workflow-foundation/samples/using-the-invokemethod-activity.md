---
title: "使用 InvokeMethod 活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6643550-d043-4ac7-8069-9c55ebbb4233
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c5d3f6734f9d6a3b0e2279b2bb6cca71141c8f5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-invokemethod-activity"></a><span data-ttu-id="123d6-102">使用 InvokeMethod 活动</span><span class="sxs-lookup"><span data-stu-id="123d6-102">Using the InvokeMethod Activity</span></span>
<span data-ttu-id="123d6-103">此示例演示如何使用<!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx)活动调用公共类中的公共方法。</span><span class="sxs-lookup"><span data-stu-id="123d6-103">This sample demonstrates how to use the <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity to invoke public methods in public classes.</span></span> <span data-ttu-id="123d6-104"><!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx)活动允许工作流针对对象调用方法、 传入参数、 获取返回值、 指定泛型方法的类型和指定的方法是同步或异步。</span><span class="sxs-lookup"><span data-stu-id="123d6-104">The <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity allows a workflow to call methods against objects, pass in parameters, get the return value, specify types for generic methods, and specify whether the method is synchronous or asynchronous.</span></span> 
  
<span data-ttu-id="123d6-105">没有一个非泛型版本<xref:System.Activities.Statements.InvokeMethod>其中的返回值设置为活动<xref:System.Activities.Statements.InvokeMethod.Result%2A>属性和一个泛型版本<!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx)其中返回的返回值的活动通过<!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> --> [ <code>System.Activities.Statements.InvokeMethod\`1.Result</code> ](https://msdn.microsoft.com/library/dd987724.aspx)类型的属性`TResult`。</span><span class="sxs-lookup"><span data-stu-id="123d6-105">There is a non-generic version of the <xref:System.Activities.Statements.InvokeMethod> activity where the return value is set to the <xref:System.Activities.Statements.InvokeMethod.Result%2A> property and a generic version of the <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity where the return value is returned through the <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> -->[<code>System.Activities.Statements.InvokeMethod\`1.Result</code>](https://msdn.microsoft.com/library/dd987724.aspx) property of type `TResult`.</span></span> 
  
 <span data-ttu-id="123d6-106">此示例演示如何调用各种不同的方法类型。</span><span class="sxs-lookup"><span data-stu-id="123d6-106">This sample demonstrates how to call various method types.</span></span> <span data-ttu-id="123d6-107">下面的列表详细介绍了此示例中演示的方法类型：</span><span class="sxs-lookup"><span data-stu-id="123d6-107">The following list details the method types demonstrated in this sample:</span></span>  
  
-   <span data-ttu-id="123d6-108">调用不含参数的实例方法。</span><span class="sxs-lookup"><span data-stu-id="123d6-108">Invoke an instance method without parameters.</span></span>  
  
-   <span data-ttu-id="123d6-109">调用含有两个参数（System.String 和 System.Int32）的实例方法。</span><span class="sxs-lookup"><span data-stu-id="123d6-109">Invoke an instance method with two parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="123d6-110">调用含有两个参数（System.String 和 System.Int32）和一个 System.String[] 类型的参数数组的实例方法。</span><span class="sxs-lookup"><span data-stu-id="123d6-110">Invoke an instance method with two parameters (System.String and System.Int32) and a parameter array of type System.String[].</span></span>  
  
-   <span data-ttu-id="123d6-111">调用含有两个参数（两个 System.Int32 数）和一个 System.Int32 类型的结果的实例方法。</span><span class="sxs-lookup"><span data-stu-id="123d6-111">Invoke an instance method with two parameters (two System.Int32 numbers) and a result of type System.Int32.</span></span>  
  
     <span data-ttu-id="123d6-112">使用 <xref:System.Activities.Statements.WriteLine> 活动将返回值绑定到一个变量，并输出到控制台。</span><span class="sxs-lookup"><span data-stu-id="123d6-112">The return value is bound to a variable and printed to the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
-   <span data-ttu-id="123d6-113">调用含有两个参数（System.String 和 System.Int32）的静态方法。</span><span class="sxs-lookup"><span data-stu-id="123d6-113">Invoke a static method with two parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="123d6-114">调用含有一个泛型参数 (System.String) 的实例方法。</span><span class="sxs-lookup"><span data-stu-id="123d6-114">Invoke an instance method with one generic parameter (System.String).</span></span>  
  
-   <span data-ttu-id="123d6-115">调用含有两个泛型参数（System.String 和 System.Int32）的静态方法。</span><span class="sxs-lookup"><span data-stu-id="123d6-115">Invoke a static method with two generic parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="123d6-116">调用包含一个按引用传递的参数的 (System.String) 实例方法。</span><span class="sxs-lookup"><span data-stu-id="123d6-116">Invoke an instance method that has one parameter passed by reference (System.String).</span></span>  
  
     <span data-ttu-id="123d6-117">使用 <xref:System.Activities.Statements.WriteLine> 活动将引用的参数绑定到一个变量，并输出到控制台。</span><span class="sxs-lookup"><span data-stu-id="123d6-117">The referenced parameter is bound to a variable and printed to the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
-   <span data-ttu-id="123d6-118">调用异步的实例方法。</span><span class="sxs-lookup"><span data-stu-id="123d6-118">Invoke an asynchronous instance method.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="123d6-119">使用此示例</span><span class="sxs-lookup"><span data-stu-id="123d6-119">To use this sample</span></span>  
  
1.  <span data-ttu-id="123d6-120">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 InvokeMethodUsage.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="123d6-120">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file.</span></span>  
  
2.  <span data-ttu-id="123d6-121">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="123d6-121">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="123d6-122">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="123d6-122">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="123d6-123">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="123d6-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="123d6-124">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="123d6-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="123d6-125">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="123d6-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="123d6-126">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="123d6-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`