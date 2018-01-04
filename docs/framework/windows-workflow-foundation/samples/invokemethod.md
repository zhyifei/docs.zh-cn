---
title: InvokeMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04988eb3-65f8-456d-b1bd-509f5d05a57c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b90ebec929b310442cde2be8d96386e016a9bbb4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="invokemethod"></a><span data-ttu-id="7845e-102">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="7845e-102">InvokeMethod</span></span>
<span data-ttu-id="7845e-103">本示例演示使用 <xref:System.Activities.Statements.InvokeMethod> 活动调用类的方法的不同方式。</span><span class="sxs-lookup"><span data-stu-id="7845e-103">This sample shows the different ways of using the <xref:System.Activities.Statements.InvokeMethod> activity to invoke methods of a class.</span></span>  
  
 <span data-ttu-id="7845e-104">方法属于一个类，并表示所包含的操作集。</span><span class="sxs-lookup"><span data-stu-id="7845e-104">A method belongs to a class and represents a contained set of operations.</span></span> <span data-ttu-id="7845e-105"><xref:System.Activities.Statements.InvokeMethod> 活动使您能够针对对象或类型调用方法，传入参数，并获取返回值。</span><span class="sxs-lookup"><span data-stu-id="7845e-105">The <xref:System.Activities.Statements.InvokeMethod> activity gives you the ability to call methods against objects or types, pass in parameters, and get the return value.</span></span> <span data-ttu-id="7845e-106">可以同步或异步调用方法。</span><span class="sxs-lookup"><span data-stu-id="7845e-106">Methods can be invoked synchronously or asynchronously.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="7845e-107">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="7845e-107">Sample Details</span></span>  
 <span data-ttu-id="7845e-108">本示例使用 <xref:System.Activities.Statements.InvokeMethod> 活动执行以下方案：</span><span class="sxs-lookup"><span data-stu-id="7845e-108">This sample uses the <xref:System.Activities.Statements.InvokeMethod> activity to perform the following scenarios:</span></span>  
  
1.  <span data-ttu-id="7845e-109">调用不含参数的实例方法。</span><span class="sxs-lookup"><span data-stu-id="7845e-109">Invoke an instance method without parameters.</span></span>  
  
2.  <span data-ttu-id="7845e-110">调用含有两个参数（<xref:System.String> 和 <xref:System.Int32>）的实例方法。</span><span class="sxs-lookup"><span data-stu-id="7845e-110">Invoke an instance method with two parameters (<xref:System.String> and <xref:System.Int32>).</span></span>  
  
3.  <span data-ttu-id="7845e-111">调用含有两个参数（<xref:System.String> 和 <xref:System.Int32>）和一个 <xref:System.String>[] 类型的参数数组的实例方法。</span><span class="sxs-lookup"><span data-stu-id="7845e-111">Invoke an instance method with two parameters (<xref:System.String> and <xref:System.Int32>) and a parameter array of type <xref:System.String>[].</span></span>  
  
4.  <span data-ttu-id="7845e-112">调用含有 <xref:System.Int32> 类型的两个参数和一个 <xref:System.Int32> 类型的结果的实例方法。</span><span class="sxs-lookup"><span data-stu-id="7845e-112">Invoke an instance method with two parameters of type <xref:System.Int32> and a result of type <xref:System.Int32>.</span></span> <span data-ttu-id="7845e-113">在本方案中，结果值绑定到一个变量，并在另一个活动中使用。</span><span class="sxs-lookup"><span data-stu-id="7845e-113">In this scenario, the result value is bound to a variable and used in another activity.</span></span> <span data-ttu-id="7845e-114">使用 <xref:System.Activities.Statements.WriteLine> 活动在控制台中显示该结果值。</span><span class="sxs-lookup"><span data-stu-id="7845e-114">It is displayed in the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
5.  <span data-ttu-id="7845e-115">调用含有 <xref:System.String> 类型和 <xref:System.Int32> 类型的两个参数的静态方法。</span><span class="sxs-lookup"><span data-stu-id="7845e-115">Invoke a static method with two parameters of type <xref:System.String> and <xref:System.Int32>.</span></span>  
  
6.  <span data-ttu-id="7845e-116">调用含有一个 <xref:System.String> 类型的泛型参数的实例方法。</span><span class="sxs-lookup"><span data-stu-id="7845e-116">Invoke an instance method with one generic parameter of type <xref:System.String>.</span></span>  
  
7.  <span data-ttu-id="7845e-117">调用含有 <xref:System.String> 类型和 <xref:System.Int32> 类型的两个泛型参数的静态方法。</span><span class="sxs-lookup"><span data-stu-id="7845e-117">Invoke a static method with two generic parameters of type <xref:System.String> and <xref:System.Int32>.</span></span>  
  
8.  <span data-ttu-id="7845e-118">调用具有一个由 <xref:System.String> 类型的引用传递的参数的实例方法。</span><span class="sxs-lookup"><span data-stu-id="7845e-118">Invoke an instance method that has one parameter passed by reference of type <xref:System.String>.</span></span> <span data-ttu-id="7845e-119">在本方案中，引用参数绑定到一个变量 (`outParam`)，并在另一个活动中使用。</span><span class="sxs-lookup"><span data-stu-id="7845e-119">In this scenario, the reference parameter is bound to a variable (`outParam`) and used in another activity.</span></span> <span data-ttu-id="7845e-120">使用 <xref:System.Activities.Statements.WriteLine> 活动在控制台上显示该引用参数。</span><span class="sxs-lookup"><span data-stu-id="7845e-120">It is displayed on the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
9. <span data-ttu-id="7845e-121">调用异步的实例方法。</span><span class="sxs-lookup"><span data-stu-id="7845e-121">Invoke an asynchronous instance method.</span></span>  
  
10. <span data-ttu-id="7845e-122">使用两个 <xref:System.Activities.Statements.InvokeMethod> 活动对一个对象的同一个实例调用两个不同的方法。</span><span class="sxs-lookup"><span data-stu-id="7845e-122">Invoke two different methods on the same instance of an object using two <xref:System.Activities.Statements.InvokeMethod> activities.</span></span>  
  
11. <span data-ttu-id="7845e-123">在对象的实例中存储一个值。</span><span class="sxs-lookup"><span data-stu-id="7845e-123">Store a value in an instance of an object.</span></span>  
  
12. <span data-ttu-id="7845e-124">从对象的实例检索一个值。</span><span class="sxs-lookup"><span data-stu-id="7845e-124">Retrieve a value from an instance of an object.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="7845e-125">使用此示例</span><span class="sxs-lookup"><span data-stu-id="7845e-125">To use this sample</span></span>  
 <span data-ttu-id="7845e-126">此示例分为两个版本。</span><span class="sxs-lookup"><span data-stu-id="7845e-126">This sample is provided in two versions.</span></span> <span data-ttu-id="7845e-127">此示例的第一个版本通过 C# 代码使用 <xref:System.Activities.Statements.InvokeMethod> 编程模型演示 [!INCLUDE[wf](../../../../includes/wf-md.md)] 的用法，它可以在 CodedWorkflow\CS 文件夹下找到。</span><span class="sxs-lookup"><span data-stu-id="7845e-127">The first version of this sample demonstrates the usage of <xref:System.Activities.Statements.InvokeMethod> through C# code using the [!INCLUDE[wf](../../../../includes/wf-md.md)] programming model and can be found under the CodedWorkflow\CS folder.</span></span> <span data-ttu-id="7845e-128">此示例的第二个版本使用 XAML 演示 <xref:System.Activities.Statements.InvokeMethod> 的用法，它可以在 DesignerWorkflow\CS 文件夹下找到。</span><span class="sxs-lookup"><span data-stu-id="7845e-128">The second version demonstrates the usage of <xref:System.Activities.Statements.InvokeMethod> using XAML and can be found under the DesignerWorkflow\CS folder.</span></span>  
  
#### <a name="to-run-the-coded-workflow-sample"></a><span data-ttu-id="7845e-129">运行编码的工作流示例</span><span class="sxs-lookup"><span data-stu-id="7845e-129">To run the coded workflow sample</span></span>  
  
1.  <span data-ttu-id="7845e-130">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 CodedWorkflow\CS 文件夹中的 InvokeMethodUsage.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="7845e-130">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file in the CodedWorkflow\CS folder.</span></span>  
  
2.  <span data-ttu-id="7845e-131">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="7845e-131">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="7845e-132">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="7845e-132">To run the solution, press CTRL+F5.</span></span>  
  
#### <a name="to-run-the-designer-workflow-sample"></a><span data-ttu-id="7845e-133">运行设计器工作流示例</span><span class="sxs-lookup"><span data-stu-id="7845e-133">To run the designer workflow sample</span></span>  
  
1.  <span data-ttu-id="7845e-134">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 DesignerWorkflow\CS 文件夹中的 InvokeMethodUsage.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="7845e-134">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file in the DesignerWorkflow\CS folder.</span></span>  
  
2.  <span data-ttu-id="7845e-135">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="7845e-135">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="7845e-136">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="7845e-136">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7845e-137">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="7845e-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7845e-138">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="7845e-138">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7845e-139">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="7845e-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7845e-140">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="7845e-140">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`