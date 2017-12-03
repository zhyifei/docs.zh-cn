---
title: "使用策略的订单处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66833724-dc36-4fad-86b0-59ffeaa3ba6a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4aaab8fca4693f6b253d48f066e644cc76637241
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="order-processing-with-policy"></a><span data-ttu-id="e6c2f-102">使用策略的订单处理</span><span class="sxs-lookup"><span data-stu-id="e6c2f-102">Order Processing with Policy</span></span>
<span data-ttu-id="e6c2f-103">订单处理策略示例演示了 Windows Workflow Foundation (WF) 的 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] 中引入的一些主要功能。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-103">The Order Processing Policy sample demonstrates some of the key features introduced in the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] of the Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="e6c2f-104">以下功能对 WF 规则引擎而言是新功能：</span><span class="sxs-lookup"><span data-stu-id="e6c2f-104">The following functionality is new for the WF rules engine:</span></span>  
  
-   <span data-ttu-id="e6c2f-105">支持运算符重载。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-105">Support for operator overloading.</span></span>  
  
-   <span data-ttu-id="e6c2f-106">支持 `new` 运算符，允许用户从 WF 规则创建新的对象和数组。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-106">Support for the `new` operator, allowing users to create new objects and arrays from WF rules.</span></span>  
  
-   <span data-ttu-id="e6c2f-107">支持扩展方法，使用户能够从与 C# 编码样式兼容的 WF 规则中调用扩展方法。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-107">Support for extension methods to make the user experience in calling extension methods from WF rules compatible with C# coding styles.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6c2f-108">此示例需要安装 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]才能生成和运行。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-108">This sample requires that [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] is installed to build and run.</span></span> <span data-ttu-id="e6c2f-109">若要打开项目和解决方案文件，需要使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-109">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] is required to open the project and solution files.</span></span>  
  
 <span data-ttu-id="e6c2f-110">此示例演示了一个 `OrderProcessingPolicy` 项目，在该项目中输入客户订单和邮政编码，订单包括一份可用项的编号列表。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-110">The sample demonstrates an `OrderProcessingPolicy` project in which a customer order, which consists of a numbered list of available items and a zip code, is entered.</span></span> <span data-ttu-id="e6c2f-111">如果两项输入均正确，则订单将成功处理；否则，策略会创建错误对象，并利用重载 `+` 运算符和预定义的扩展方法将该错误通知给用户。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-111">The order is processed successfully if both entries are correct; otherwise, the policy creates error objects, utilizing an overloaded `+` operator and a predefined extension method to inform the user of the errors.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e6c2f-112">扩展方法，请参阅[C# 3.0 版规范](http://go.microsoft.com/fwlink/?LinkId=95402)。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-112"> extension methods, see [C# Version 3.0 Specification](http://go.microsoft.com/fwlink/?LinkId=95402).</span></span>  
  
 <span data-ttu-id="e6c2f-113">该示例由下列项目组成：</span><span class="sxs-lookup"><span data-stu-id="e6c2f-113">The sample is comprised of the following projects:</span></span>  
  
-   `OrderErrorLibrary`  
  
     <span data-ttu-id="e6c2f-114">`OrderErrorLibrary` 是一个类库，定义了 `OrderError` 和 `OrderErrorCollection` 类。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-114">The `OrderErrorLibrary` is a class library that defines `OrderError` and `OrderErrorCollection` classes.</span></span> <span data-ttu-id="e6c2f-115">输入无效时，将创建一个 `OrderError` 实例。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-115">An `OrderError` instance is created when an invalid input is entered.</span></span> <span data-ttu-id="e6c2f-116">此库也在 `OrderErrorCollection` 类上提供扩展方法，该方法输出 `ErrorText` 中所有 `OrderError` 对象上的 `OrderErrorCollection` 属性。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-116">The library also provides an extension method on the `OrderErrorCollection` class that outputs the `ErrorText` property on all `OrderError` objects in the `OrderErrorCollection`.</span></span>  
  
-   `OrderProcessingPolicy`  
  
     <span data-ttu-id="e6c2f-117">`OrderProcessingPolicy` 项目是一个 WF 控制台应用程序，定义单个 `PolicyFromFile` 活动。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-117">The `OrderProcessingPolicy` project is a WF console application that defines a single `PolicyFromFile` activity.</span></span> <span data-ttu-id="e6c2f-118">该活动包含下列规则：</span><span class="sxs-lookup"><span data-stu-id="e6c2f-118">The activity has the following rules:</span></span>  
  
    -   `invalidItemNum`  
  
         <span data-ttu-id="e6c2f-119">此规则验证项编号是否介于 1 和 6（包含 1 和 6）之间。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-119">This rule validates that the item number is between 1 and 6, inclusive.</span></span> <span data-ttu-id="e6c2f-120">如果项编号在有效范围内，则该规则不会进行任何操作（除了输出到控制台）。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-120">If the item number is within the valid range, the rule does nothing (other than printing to the console).</span></span> <span data-ttu-id="e6c2f-121">如果项编号未介于 1 和 6 之间，则 `invalidItemNum` 规则将进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e6c2f-121">If the item number is not between 1 and 6, the `invalidItemNum` rule does the following:</span></span>  
  
        1.  <span data-ttu-id="e6c2f-122">创建一个新的 `OrderError` 对象，将输入的项编号传递给该对象，并在对象上设置 `ErrorText` 和 `CustomerName` 属性。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-122">Creates a new `OrderError` object, passing it the item number entered, and sets the `ErrorText` and `CustomerName` properties on the object.</span></span>  
  
        2.  <span data-ttu-id="e6c2f-123">创建一个 `invalidItemNumErrorCollection` 对象。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-123">Creates an `invalidItemNumErrorCollection` object.</span></span>  
  
        3.  <span data-ttu-id="e6c2f-124">将新创建的 `OrderError` 实例添加到 `invalidItemNumErrorCollection`。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-124">Adds the newly-created `OrderError` instance to the `invalidItemNumErrorCollection`.</span></span>  
  
         <span data-ttu-id="e6c2f-125">这表明支持 `new` 运算符，您可以使用该运算符在规则内进行对象的实例化。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-125">This demonstrates support for the `new` operator, with which you can instantiate objects inside rules.</span></span>  
  
    -   `invalidZip`  
  
         <span data-ttu-id="e6c2f-126">此规则验证邮政编码是否有 5 个数字，并且是否在 600 到 99998 的范围内。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-126">This rule validates that the zip code has 5 digits, and is within the range 600 to 99998.</span></span> <span data-ttu-id="e6c2f-127">如果邮政编码在有效范围内，则该规则不会进行任何操作（除了输出到控制台）。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-127">If the zip code is within the valid range, the rule does nothing (other than printing to the console).</span></span> <span data-ttu-id="e6c2f-128">如果邮政编码的长度小于 5 或不在 00600 和 99998 之间，则 `invalidZip` 规则将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e6c2f-128">If the length of the zip code is less than 5, or the zip code is not between 00600 and 99998, the `invalidZip` rule does the following:</span></span>  
  
        1.  <span data-ttu-id="e6c2f-129">创建一个 `OrderError` 对象，将输入的邮政编码传递给该对象，并在该对象上设置 `ErrorText` 和 `CustomerName` 属性。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-129">Creates an `OrderError` object, passing it the zip code entered, and sets the `ErrorText` and `CustomerName` properties on the object.</span></span>  
  
        2.  <span data-ttu-id="e6c2f-130">创建一个 `invalidZipCodeErrorCollection` 对象。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-130">Creates an `invalidZipCodeErrorCollection` object.</span></span>  
  
        3.  <span data-ttu-id="e6c2f-131">将新创建的 `OrderError` 实例添加到新创建的 `invalidZipCodeErrorCollection`。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-131">Adds the newly-created `OrderError` instance to the newly-created `invalidZipCodeErrorCollection`.</span></span>  
  
         <span data-ttu-id="e6c2f-132">此规则再次表明支持 `new` 运算符，因此您可以在规则内进行对象的实例化。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-132">This rule again demonstrates support for the `new` operator, which allows you to instantiate objects inside rules.</span></span>  
  
    -   `displayErrors`  
  
         <span data-ttu-id="e6c2f-133">此规则检查前两个规则是否将任何错误添加到了两个 `OrderErrorCollection` 对象 `invalidItemNumErrorCollection` 和 `invalidIZipCodeErrorCollection` 中。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-133">This rule checks to see if there were any errors added by the previous two rules in the two `OrderErrorCollection` objects `invalidItemNumErrorCollection` and `invalidIZipCodeErrorCollection`.</span></span> <span data-ttu-id="e6c2f-134">如果存在错误（`invalidItemNumErrorCollection` 或 `invalidZipCodeErrorCollection` 不为 `null`），则规则将进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e6c2f-134">If there were errors (either `invalidItemNumErrorCollection` or `invalidZipCodeErrorCollection` is not `null`), the rule does the following:</span></span>  
  
        1.  <span data-ttu-id="e6c2f-135">调用重载`+`运算符的内容复制`invalidItemNumErrorCollection`和`invalidZipCodeErrorCollection`到`invalidOrdersCollection``OrderErrorCollection`实例。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-135">Calls the overloaded `+` operator to copy the contents of `invalidItemNumErrorCollection` and `invalidZipCodeErrorCollection` to an `invalidOrdersCollection``OrderErrorCollection` instance.</span></span>  
  
        2.  <span data-ttu-id="e6c2f-136">调用 `PrintOrderErrors` 上的 `invalidOrdersCollection` 扩展方法，并输出 `ErrorText` 中所有 `orderError` 对象上的 `invalidOrdersCollection` 属性。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-136">Calls the `PrintOrderErrors` extension method on `invalidOrdersCollection` and outputs the `ErrorText` property on all `orderError` objects in `invalidOrdersCollection`.</span></span>  
  
 <span data-ttu-id="e6c2f-137">`+` 上的重载运算符 `OrderErrorCollection` 在 `OrderErrorCollection` 项目的 `OrderErrorLibrary` 类中进行定义。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-137">The overloaded operator `+` on the `OrderErrorCollection` is defined in the `OrderErrorCollection` class, in the `OrderErrorLibrary` project.</span></span> <span data-ttu-id="e6c2f-138">它将使用两个 `OrderErrorCollection` 对象，并将这两个对象合并到一个 `OrderErrorCollection` 对象中。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-138">It takes two `OrderErrorCollection` objects and combines them into one `OrderErrorCollection` object.</span></span>  
  
 <span data-ttu-id="e6c2f-139">`PrintOrderErrors` 扩展方法也在 `OrderErrorLibrary` 项目中进行定义。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-139">The `PrintOrderErrors` extension method is also defined in the `OrderErrorLibrary` project.</span></span> <span data-ttu-id="e6c2f-140">扩展方法是一项全新的 C# 功能，它使开发人员能够将新方法添加到现有 CLR 类型的公共协定中，而不必再从它派生子类或重新编译原始类型。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-140">Extension methods are a new C# feature that enables developers to add new methods to the public contract of an existing CLR type, without having to derive a class from it or recompile the original type.</span></span>  
  
 <span data-ttu-id="e6c2f-141">当您运行示例时，系统将提示您输入名称、要采购项目的项编号和邮政编码。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-141">When you run the sample you are prompted to enter a name, the item number of the item to be purchased, and a zip code.</span></span> <span data-ttu-id="e6c2f-142">此信息随后将由在策略活动中定义的规则进行验证。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-142">This information is then verified by the rules defined in the policy activity.</span></span> <span data-ttu-id="e6c2f-143">下面是来自程序的示例输出。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-143">The following is sample output from the program.</span></span>  
  
```  
Please enter your name: John  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 1  
  
Please enter your 5-Digit zip code: 98102  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Thank you for your order, it has been processed.  
  
Workflow Completed  
Another Order? (Y/N): y  
  
Please enter your name: Joel  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 8  
  
Please enter your 5-Digit zip code: 0000  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Your order contains the following error(s)  
  
Error: No item number found. Please choose an available item.  
Error: Invalid zip code. Please choose a zip code between 00600 and 99998.  
  
Workflow Completed  
Another Order? (Y/N): n  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e6c2f-144">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="e6c2f-144">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e6c2f-145">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 OrderProcessingPolicy.sln 项目文件。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-145">Open the OrderProcessingPolicy.sln project file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="e6c2f-146">解决方案中有两个不同的项目：`OrderErrorLibrary` 和 `OrderProcessingPolicy`。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-146">There are two different projects in the solution: `OrderErrorLibrary` and `OrderProcessingPolicy`.</span></span> <span data-ttu-id="e6c2f-147">`OrderProcessingPolicy` 项目使用在 `OrderErrorLibrary` 中定义的类和方法。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-147">The `OrderProcessingPolicy` project uses classes and methods defined in the `OrderErrorLibrary`.</span></span>  
  
3.  <span data-ttu-id="e6c2f-148">生成所有项目。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-148">Build all projects.</span></span>  
  
4.  <span data-ttu-id="e6c2f-149">单击“运行” 。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-149">Click **Run**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e6c2f-150">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-150">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e6c2f-151">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="e6c2f-151">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e6c2f-152">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="e6c2f-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e6c2f-153">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="e6c2f-153">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\OrderProcessingPolicy`