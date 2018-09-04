---
title: 使用 Pick 活动
ms.date: 03/30/2017
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
ms.openlocfilehash: 193b60bff7b08c0de9a0957668483eb73be97274
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43563157"
---
# <a name="using-the-pick-activity"></a><span data-ttu-id="69fb4-102">使用 Pick 活动</span><span class="sxs-lookup"><span data-stu-id="69fb4-102">Using the Pick Activity</span></span>
<span data-ttu-id="69fb4-103">此示例演示如何使用 <xref:System.Activities.Statements.Pick> 活动。</span><span class="sxs-lookup"><span data-stu-id="69fb4-103">This sample demonstrates how to use the <xref:System.Activities.Statements.Pick> activity.</span></span>  
  
 <span data-ttu-id="69fb4-104"><xref:System.Activities.Statements.Pick> 活动提供基于事件的控制建模。</span><span class="sxs-lookup"><span data-stu-id="69fb4-104">The <xref:System.Activities.Statements.Pick> activity provides event-based control modeling.</span></span> <span data-ttu-id="69fb4-105">其行为与 C# `switch` 语句相似, 也就是只在 `switch` 语句中执行一个分支。</span><span class="sxs-lookup"><span data-stu-id="69fb4-105">It behaves similar to the C# `switch` statement, which executes only one of the branches in the `switch` statement.</span></span> <span data-ttu-id="69fb4-106">与 `switch` 语句中基于某个值执行一个分支不同的是，<xref:System.Activities.Statements.Pick> 活动基于一个活动的完成情况来执行一个分支。</span><span class="sxs-lookup"><span data-stu-id="69fb4-106">Unlike the `switch` statement in which a branch is executed based upon on a value, the <xref:System.Activities.Statements.Pick> activity executes a branch based upon how an activity completes.</span></span>  
  
 <span data-ttu-id="69fb4-107">此示例提示用户在给定的时间期限内在控制台中键入自己的用户名。</span><span class="sxs-lookup"><span data-stu-id="69fb4-107">This sample prompts a user to type in their name on the console within a given time period.</span></span> <span data-ttu-id="69fb4-108">此示例中的 <xref:System.Activities.Statements.Pick> 活动有两个分支，这两个分支的执行将取决于用户是否在五秒钟之内键入了其用户名。</span><span class="sxs-lookup"><span data-stu-id="69fb4-108">The <xref:System.Activities.Statements.Pick> activity in the sample has two branches that are executed based upon whether the user types in their name within 5 seconds or not.</span></span> <span data-ttu-id="69fb4-109">如果用户在五秒钟之内键入了其用户名，则将执行第一个包含一个自定义 `ReadLine` 活动的分支；否则将执行另外一个包含一个 <xref:System.Activities.Statements.Delay> 活动的分支。</span><span class="sxs-lookup"><span data-stu-id="69fb4-109">If the user types in their name within 5 seconds, the first branch is executed, which contains a custom `ReadLine` activity; otherwise the other branch is executed, which contains a <xref:System.Activities.Statements.Delay> activity.</span></span> <span data-ttu-id="69fb4-110">当用户在控制台中键入其用户名之后，此用户名将会在控制台中输出。</span><span class="sxs-lookup"><span data-stu-id="69fb4-110">Once a user’s name is typed in on the console, the user’s name is printed on the console.</span></span> <span data-ttu-id="69fb4-111">如果在五秒之内未完成输入，则操作超时。</span><span class="sxs-lookup"><span data-stu-id="69fb4-111">If an input is not entered within 5 seconds, the operation is timed out.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="69fb4-112">演示</span><span class="sxs-lookup"><span data-stu-id="69fb4-112">Demonstrates</span></span>  
 <span data-ttu-id="69fb4-113"><xref:System.Activities.Statements.Pick> 活动。</span><span class="sxs-lookup"><span data-stu-id="69fb4-113"><xref:System.Activities.Statements.Pick> activity.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="69fb4-114">讨论</span><span class="sxs-lookup"><span data-stu-id="69fb4-114">Discussion</span></span>  
 <span data-ttu-id="69fb4-115">此示例包含一个设计器工作流和一个编码工作流。</span><span class="sxs-lookup"><span data-stu-id="69fb4-115">The sample includes a Designer workflow and coded workflow.</span></span>  
  
 <span data-ttu-id="69fb4-116">设计器工作流</span><span class="sxs-lookup"><span data-stu-id="69fb4-116">Designer Workflow</span></span>  
 <span data-ttu-id="69fb4-117">此示例的设计器版本演示如何在设计器中创建一个工作流。</span><span class="sxs-lookup"><span data-stu-id="69fb4-117">The Designer version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="69fb4-118">包含以下文件：</span><span class="sxs-lookup"><span data-stu-id="69fb4-118">The following files are included:</span></span>  
  
-   <span data-ttu-id="69fb4-119">Program.cs：包含执行示例工作流的 `Main` 函数。</span><span class="sxs-lookup"><span data-stu-id="69fb4-119">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>  
  
-   <span data-ttu-id="69fb4-120">ReadString.cs：一个从控制台读取一些输入的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="69fb4-120">ReadString.cs: A custom activity that reads some input from the console.</span></span>  
  
-   <span data-ttu-id="69fb4-121">Sequence1.xaml：一个通过使用 Pick 的设计器创建的工作流。</span><span class="sxs-lookup"><span data-stu-id="69fb4-121">Sequence1.xaml: A workflow created using the designer that uses Pick.</span></span>  
  
 <span data-ttu-id="69fb4-122">编码工作流</span><span class="sxs-lookup"><span data-stu-id="69fb4-122">Coded Workflow</span></span>  
 <span data-ttu-id="69fb4-123">此示例的编码版本演示如何在设计器中创建一个工作流。</span><span class="sxs-lookup"><span data-stu-id="69fb4-123">The coded version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="69fb4-124">包含以下文件：</span><span class="sxs-lookup"><span data-stu-id="69fb4-124">The following files are included:</span></span>  
  
-   <span data-ttu-id="69fb4-125">Program.cs：包含执行示例工作流的 `Main` 函数。</span><span class="sxs-lookup"><span data-stu-id="69fb4-125">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>  
  
-   <span data-ttu-id="69fb4-126">ReadString.cs：一个从控制台读取一些输入的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="69fb4-126">ReadString.cs: A custom activity that reads some input from the console.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="69fb4-127">使用此示例</span><span class="sxs-lookup"><span data-stu-id="69fb4-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="69fb4-128">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 Pick.sln 文件。</span><span class="sxs-lookup"><span data-stu-id="69fb4-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Pick.sln solution file.</span></span>  
  
2.  <span data-ttu-id="69fb4-129">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="69fb4-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="69fb4-130">若要运行解决方案，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="69fb4-130">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="69fb4-131">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="69fb4-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="69fb4-132">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="69fb4-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="69fb4-133">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="69fb4-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="69fb4-134">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="69fb4-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`