---
title: "Hello World 自定义活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72b1dd0a-9aad-47d5-95a9-a1024ee1d0a1
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b717a5448a32eea3957e1e7e45c4dfc2f8801775
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="hello-world-custom-activity"></a><span data-ttu-id="2d5a7-102">Hello World 自定义活动</span><span class="sxs-lookup"><span data-stu-id="2d5a7-102">Hello World Custom Activity</span></span>
<span data-ttu-id="2d5a7-103">此示例演示几个 [!INCLUDE[wf](../../../../includes/wf-md.md)] 的主要功能，包括如何创建一个简单的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-103">This sample demonstrates several key features of [!INCLUDE[wf](../../../../includes/wf-md.md)], including how to create a simple custom activity.</span></span> <span data-ttu-id="2d5a7-104">此示例中演示的一些功能使用 C# 创建自定义活动并使用 `in` 和 `out` 参数（<xref:System.Activities.InArgument> 和 <xref:System.Activities.OutArgument>）。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-104">Some of the features demonstrated in this sample are creating a custom activity in C# and using `in` and `out` arguments (<xref:System.Activities.InArgument> and <xref:System.Activities.OutArgument>).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2d5a7-105">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-105">The samples may already be installed on your computer.</span></span> <span data-ttu-id="2d5a7-106">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="2d5a7-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2d5a7-107">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2d5a7-108">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="2d5a7-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\HelloWorld`  
  
## <a name="creating-a-workflow-in-code"></a><span data-ttu-id="2d5a7-109">使用代码创建工作流</span><span class="sxs-lookup"><span data-stu-id="2d5a7-109">Creating a Workflow in Code</span></span>  
 <span data-ttu-id="2d5a7-110">在此示例中，使用 C# 代码创建两个自定义活动。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-110">In this sample, two custom activities are created using C# code.</span></span> <span data-ttu-id="2d5a7-111">这两个自定义活动直接或间接继承自 <xref:System.Activities.Activity%601> 以返回单个值。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-111">Both custom activities inherit directly or indirectly from <xref:System.Activities.Activity%601> to return a single value.</span></span> <span data-ttu-id="2d5a7-112">使用泛型返回值（而不是继承自非泛型 <xref:System.Activities.Activity> 类）的好处是：一些活动（例如，<xref:System.Activities.Statements.Assign>）在用作组合活动的一部分时能够访问返回值。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-112">The advantage of using the generic return value, instead of inheriting from the non-generic <xref:System.Activities.Activity> class, is that some activities (such as <xref:System.Activities.Statements.Assign>) are able to access the return value when used as part of a composed activity.</span></span>  
  
 <span data-ttu-id="2d5a7-113">AppendString</span><span class="sxs-lookup"><span data-stu-id="2d5a7-113">AppendString</span></span>  
 <span data-ttu-id="2d5a7-114">此活动继承自 <xref:System.Activities.Activity%601>，并使用一个可将两个字符串连接在一起的 <xref:System.Activities.Statements.Assign> 活动。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-114">This activity inherits from <xref:System.Activities.Activity%601>, and uses an <xref:System.Activities.Statements.Assign> activity that concatenates two strings together.</span></span>  
  
 <span data-ttu-id="2d5a7-115">Prepend String</span><span class="sxs-lookup"><span data-stu-id="2d5a7-115">Prepend String</span></span>  
 <span data-ttu-id="2d5a7-116">此活动直接继承自 <xref:System.Activities.CodeActivity%601>，并且创建与 `AppendString` 活动类似的功能。 活动使用通过代码实现的而不是由预先存在的活动构成的逻辑。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-116">This activity inherits directly from <xref:System.Activities.CodeActivity%601>, and creates similar functionality to the `AppendString` activity, which uses logic implemented in code rather than being composed of a pre-existing activity.</span></span>  
  
 <span data-ttu-id="2d5a7-117">此项目中包括以下文件。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-117">The following files are included in this project.</span></span>  
  
 <span data-ttu-id="2d5a7-118">AppendString.cs</span><span class="sxs-lookup"><span data-stu-id="2d5a7-118">AppendString.cs</span></span>  
 <span data-ttu-id="2d5a7-119">将字符串追加在一起的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-119">The custom activity that appends strings together.</span></span> <span data-ttu-id="2d5a7-120">它接收一个字符串，并将它组合与文字文本字符串"says 你好 world"，向窗体输出完整的消息。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-120">It takes in a string and combines it with a literal text string " says hello world" to form a complete message as output.</span></span>  
  
 <span data-ttu-id="2d5a7-121">PrependString.cs</span><span class="sxs-lookup"><span data-stu-id="2d5a7-121">PrependString.cs</span></span>  
 <span data-ttu-id="2d5a7-122">此活动将一个预定义字符串添加到一个输入字符串的前面。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-122">This activity prefixes a predefined string to an input string.</span></span>  
  
 <span data-ttu-id="2d5a7-123">Sequence1.xaml</span><span class="sxs-lookup"><span data-stu-id="2d5a7-123">Sequence1.xaml</span></span>  
 <span data-ttu-id="2d5a7-124">一个使用 `AppendString` 和 `PrependString` 自定义活动的工作流。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-124">A workflow that uses the `AppendString` and `PrependString` custom activities.</span></span>  
  
 <span data-ttu-id="2d5a7-125">Program.cs</span><span class="sxs-lookup"><span data-stu-id="2d5a7-125">Program.cs</span></span>  
 <span data-ttu-id="2d5a7-126">一个运行工作流的程序。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-126">A program that runs the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="2d5a7-127">使用此示例</span><span class="sxs-lookup"><span data-stu-id="2d5a7-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="2d5a7-128">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 HelloWorld.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the HelloWorld.sln solution file.</span></span>  
  
2.  <span data-ttu-id="2d5a7-129">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="2d5a7-130">若要运行解决方案，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="2d5a7-130">To run the solution, press F5.</span></span>