---
title: 使用 Pick 活动
ms.date: 03/30/2017
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
ms.openlocfilehash: b0997254615ca962fd386dea70c67a8edb36c90a
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715530"
---
# <a name="using-the-pick-activity"></a><span data-ttu-id="babc5-102">使用 Pick 活动</span><span class="sxs-lookup"><span data-stu-id="babc5-102">Using the Pick Activity</span></span>
<span data-ttu-id="babc5-103">此示例演示如何使用 <xref:System.Activities.Statements.Pick> 活动。</span><span class="sxs-lookup"><span data-stu-id="babc5-103">This sample demonstrates how to use the <xref:System.Activities.Statements.Pick> activity.</span></span>

 <span data-ttu-id="babc5-104"><xref:System.Activities.Statements.Pick> 活动提供基于事件的控制建模。</span><span class="sxs-lookup"><span data-stu-id="babc5-104">The <xref:System.Activities.Statements.Pick> activity provides event-based control modeling.</span></span> <span data-ttu-id="babc5-105">其行为与 C# `switch` 语句相似, 也就是只在 `switch` 语句中执行一个分支。</span><span class="sxs-lookup"><span data-stu-id="babc5-105">It behaves similar to the C# `switch` statement, which executes only one of the branches in the `switch` statement.</span></span> <span data-ttu-id="babc5-106">与 `switch` 语句中基于某个值执行一个分支不同的是，<xref:System.Activities.Statements.Pick> 活动基于一个活动的完成情况来执行一个分支。</span><span class="sxs-lookup"><span data-stu-id="babc5-106">Unlike the `switch` statement in which a branch is executed based upon on a value, the <xref:System.Activities.Statements.Pick> activity executes a branch based upon how an activity completes.</span></span>

 <span data-ttu-id="babc5-107">此示例提示用户在给定的时间期限内在控制台中键入自己的用户名。</span><span class="sxs-lookup"><span data-stu-id="babc5-107">This sample prompts a user to type in their name on the console within a given time period.</span></span> <span data-ttu-id="babc5-108">此示例中的 <xref:System.Activities.Statements.Pick> 活动有两个分支，这两个分支的执行将取决于用户是否在五秒钟之内键入了其用户名。</span><span class="sxs-lookup"><span data-stu-id="babc5-108">The <xref:System.Activities.Statements.Pick> activity in the sample has two branches that are executed based upon whether the user types in their name within 5 seconds or not.</span></span> <span data-ttu-id="babc5-109">如果用户在五秒钟之内键入了其用户名，则将执行第一个包含一个自定义 `ReadLine` 活动的分支；否则将执行另外一个包含一个 <xref:System.Activities.Statements.Delay> 活动的分支。</span><span class="sxs-lookup"><span data-stu-id="babc5-109">If the user types in their name within 5 seconds, the first branch is executed, which contains a custom `ReadLine` activity; otherwise the other branch is executed, which contains a <xref:System.Activities.Statements.Delay> activity.</span></span> <span data-ttu-id="babc5-110">当用户在控制台中键入其用户名之后，此用户名将会在控制台中输出。</span><span class="sxs-lookup"><span data-stu-id="babc5-110">Once a user’s name is typed in on the console, the user’s name is printed on the console.</span></span> <span data-ttu-id="babc5-111">如果在五秒之内未完成输入，则操作超时。</span><span class="sxs-lookup"><span data-stu-id="babc5-111">If an input is not entered within 5 seconds, the operation is timed out.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="babc5-112">演示文本</span><span class="sxs-lookup"><span data-stu-id="babc5-112">Demonstrates</span></span>
 <span data-ttu-id="babc5-113"><xref:System.Activities.Statements.Pick> 活动。</span><span class="sxs-lookup"><span data-stu-id="babc5-113"><xref:System.Activities.Statements.Pick> activity.</span></span>

## <a name="discussion"></a><span data-ttu-id="babc5-114">讨论</span><span class="sxs-lookup"><span data-stu-id="babc5-114">Discussion</span></span>
 <span data-ttu-id="babc5-115">此示例包含一个设计器工作流和一个编码工作流。</span><span class="sxs-lookup"><span data-stu-id="babc5-115">The sample includes a Designer workflow and coded workflow.</span></span>

 <span data-ttu-id="babc5-116">设计器工作流示例的设计器版本演示如何在设计器中创建工作流。</span><span class="sxs-lookup"><span data-stu-id="babc5-116">Designer Workflow The Designer version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="babc5-117">包含以下文件：</span><span class="sxs-lookup"><span data-stu-id="babc5-117">The following files are included:</span></span>

- <span data-ttu-id="babc5-118">Program.cs：包含执行示例工作流的 `Main` 函数。</span><span class="sxs-lookup"><span data-stu-id="babc5-118">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>

- <span data-ttu-id="babc5-119">ReadString.cs：一个从控制台读取一些输入的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="babc5-119">ReadString.cs: A custom activity that reads some input from the console.</span></span>

- <span data-ttu-id="babc5-120">Sequence1.xaml：一个通过使用 Pick 的设计器创建的工作流。</span><span class="sxs-lookup"><span data-stu-id="babc5-120">Sequence1.xaml: A workflow created using the designer that uses Pick.</span></span>

 <span data-ttu-id="babc5-121">编码的工作流示例的编码版本演示如何在设计器中创建工作流。</span><span class="sxs-lookup"><span data-stu-id="babc5-121">Coded Workflow The coded version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="babc5-122">包含以下文件：</span><span class="sxs-lookup"><span data-stu-id="babc5-122">The following files are included:</span></span>

- <span data-ttu-id="babc5-123">Program.cs：包含执行示例工作流的 `Main` 函数。</span><span class="sxs-lookup"><span data-stu-id="babc5-123">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>

- <span data-ttu-id="babc5-124">ReadString.cs：一个从控制台读取一些输入的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="babc5-124">ReadString.cs: A custom activity that reads some input from the console.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="babc5-125">使用此示例</span><span class="sxs-lookup"><span data-stu-id="babc5-125">To use this sample</span></span>

1. <span data-ttu-id="babc5-126">使用 Visual Studio 2010，打开 "选择 .sln" 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="babc5-126">Using Visual Studio 2010, open the Pick.sln solution file.</span></span>

2. <span data-ttu-id="babc5-127">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="babc5-127">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="babc5-128">若要运行解决方案，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="babc5-128">To run the solution, press F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="babc5-129">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="babc5-129">The samples may already be installed on your machine.</span></span> <span data-ttu-id="babc5-130">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="babc5-130">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="babc5-131">如果此目录不存在，请参阅[.NET Framework 4 的 Windows Communication Foundation （wcf）和 Windows Workflow Foundation （WF）示例](https://www.microsoft.com/download/details.aspx?id=21459)以下载所有 WINDOWS COMMUNICATION FOUNDATION （wcf）和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="babc5-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="babc5-132">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="babc5-132">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`
