---
title: 使用 FlowChart 与 Pick 的组合的 StateMachine 方案
ms.date: 03/30/2017
ms.assetid: 88d81395-f7a3-41d8-8439-20a425c538a6
ms.openlocfilehash: b0f8e884a8a6c62c4e7edaf5cc9727bf7bfe8603
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485506"
---
# <a name="statemachine-scenario-using-a-combination-of-flowchart-and-pick"></a><span data-ttu-id="4ca90-102">使用 FlowChart 与 Pick 的组合的 StateMachine 方案</span><span class="sxs-lookup"><span data-stu-id="4ca90-102">StateMachine Scenario Using a Combination of FlowChart and Pick</span></span>
<span data-ttu-id="4ca90-103">此示例演示如何使用 <xref:System.Activities.Statements.Flowchart> 和 <xref:System.Activities.Statements.Pick> 活动的组合实现一个简单的秒表方案。</span><span class="sxs-lookup"><span data-stu-id="4ca90-103">This sample demonstrates how to implement a simple stopwatch scenario using a combination of the <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Pick> activities.</span></span> <span data-ttu-id="4ca90-104">它使用 Pick 活动中的 Receive 和 Send 来侦听秒表事件。</span><span class="sxs-lookup"><span data-stu-id="4ca90-104">It uses Receive and Send within the Pick activity to listen for stopwatch events.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4ca90-105">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="4ca90-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4ca90-106">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="4ca90-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4ca90-107">如果此目录不存在，请转到 （下载页） 以下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="4ca90-107">If this directory does not exist, go to (download page) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4ca90-108">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="4ca90-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## <a name="sample-details"></a><span data-ttu-id="4ca90-109">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="4ca90-109">Sample Details</span></span>  
 <span data-ttu-id="4ca90-110">下表列出了此示例中的项目。</span><span class="sxs-lookup"><span data-stu-id="4ca90-110">The following table lists the projects in this sample.</span></span>  
  
|<span data-ttu-id="4ca90-111">项目名称</span><span class="sxs-lookup"><span data-stu-id="4ca90-111">Project Name</span></span>|<span data-ttu-id="4ca90-112">描述</span><span class="sxs-lookup"><span data-stu-id="4ca90-112">Description</span></span>|  
|-|-|  
|<span data-ttu-id="4ca90-113">StopWatchService</span><span class="sxs-lookup"><span data-stu-id="4ca90-113">StopWatchService</span></span>|<span data-ttu-id="4ca90-114">此项目包含秒表示例的状态计算机的实现，其中使用了 <xref:System.Activities.Statements.Flowchart> 和 <xref:System.Activities.Statements.Pick> 活动的组合。</span><span class="sxs-lookup"><span data-stu-id="4ca90-114">This project contains the implementation of a state machine for the stopwatch sample using a combination of the <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Pick> activities.</span></span><br /><br /> <span data-ttu-id="4ca90-115"><xref:System.Activities.Statements.Pick> 活动在 <xref:System.Activities.Statements.PickBranch> 属性中具有 3 条 <xref:System.Activities.Statements.Pick.Branches%2A> 语句，分别用于侦听 `GetStart`、`GetStop` 和 `GetOff` 事件。</span><span class="sxs-lookup"><span data-stu-id="4ca90-115">The <xref:System.Activities.Statements.Pick> activity has 3 <xref:System.Activities.Statements.PickBranch> statements within the <xref:System.Activities.Statements.Pick.Branches%2A> property that listen for `GetStart`, `GetStop` and `GetOff` events.</span></span> <span data-ttu-id="4ca90-116">根据传入的事件，这三个分支中的一个分支的触发器将会激活并触发对应的 <xref:System.Activities.Statements.PickBranch.Action%2A>。</span><span class="sxs-lookup"><span data-stu-id="4ca90-116">Based on the incoming event, the triggers for one of the branches activate and the corresponding <xref:System.Activities.Statements.PickBranch.Action%2A> is triggered.</span></span> <span data-ttu-id="4ca90-117">在 <xref:System.Activities.Statements.PickBranch.Action%2A> 属性中，有一条用于计算转换是否为合法转换的 <xref:System.Activities.Statements.Switch%601> 语句，如果它是合法的转换，则将 `currentState` 属性更新为正在转换状态并将其发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="4ca90-117">In the <xref:System.Activities.Statements.PickBranch.Action%2A> property, there is a <xref:System.Activities.Statements.Switch%601> statement that evaluates whether the transition is a legitimate transition and if it is, the `currentState` property is updated to the transitioning state and sent to the client.</span></span><br /><br /> <span data-ttu-id="4ca90-118"><xref:System.Activities.Statements.FlowDecision> 末尾的 <xref:System.Activities.Statements.Flowchart> 活动计算 `currentState` 属性来确定此状态是否为最终状态。</span><span class="sxs-lookup"><span data-stu-id="4ca90-118">The <xref:System.Activities.Statements.FlowDecision> activity at the end of the <xref:System.Activities.Statements.Flowchart> evaluates the `currentState` property to determine whether the state is terminal.</span></span> <span data-ttu-id="4ca90-119">如果它是最终状态，则工作流结束；否则，将控制权回送到 <xref:System.Activities.Statements.Pick> 活动的开始位置，工作流在此处等待更多秒表事件。</span><span class="sxs-lookup"><span data-stu-id="4ca90-119">If it is, the workflow ends; otherwise control loops back to the start of the <xref:System.Activities.Statements.Pick> activity where the workflow waits for more stopwatch events.</span></span>|  
|<span data-ttu-id="4ca90-120">StopWatchClient</span><span class="sxs-lookup"><span data-stu-id="4ca90-120">StopWatchClient</span></span>|<span data-ttu-id="4ca90-121">这是一个简单的顺序工作流控制台应用程序，它用简单的 Send 或 Receive 活动组合发送各种秒表事件。</span><span class="sxs-lookup"><span data-stu-id="4ca90-121">This is a simple sequential workflow console application that sends various stopwatch events with simple Send or Receive activity combinations.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="4ca90-122">使用此示例</span><span class="sxs-lookup"><span data-stu-id="4ca90-122">To use this sample</span></span>  
  
1.  <span data-ttu-id="4ca90-123">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 StateMachineWithPick.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="4ca90-123">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open StateMachineWithPick.sln solution file.</span></span>  
  
2.  <span data-ttu-id="4ca90-124">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="4ca90-124">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="4ca90-125">启动从 StopWatchService.exe[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]以管理员身份通过右键单击.exe 文件并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="4ca90-125">Start the StopWatchService.exe from [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] as an administrator by right clicking the .exe file and selecting **Run as administrator**.</span></span>  
  
    1.  <span data-ttu-id="4ca90-126">导航到 StateMachineWithPick\CS\StopWatchService\bin\Debug 文件夹。</span><span class="sxs-lookup"><span data-stu-id="4ca90-126">Navigate to the StateMachineWithPick\CS\StopWatchService\bin\Debug folder.</span></span>  
  
    2.  <span data-ttu-id="4ca90-127">右击 StopWatchService.exe 文件，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="4ca90-127">Right-click the StopWatchService.exe file and select **Run as administrator**.</span></span>  
  
4.  <span data-ttu-id="4ca90-128">从 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中启动 StopWatchClient 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ca90-128">Start the StopWatchClient client application from within [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    1.  <span data-ttu-id="4ca90-129">在中**解决方案资源管理器**，选择**StopWatchClient**项目，然后右键单击**设为启动项目**。</span><span class="sxs-lookup"><span data-stu-id="4ca90-129">In **Solution Explorer**, select the **StopWatchClient** project and right-click **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="4ca90-130">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="4ca90-130">To run the solution, press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="4ca90-131">切换回 StopWatchService.exe 的控制台窗口以查看状态转换。</span><span class="sxs-lookup"><span data-stu-id="4ca90-131">Switch back to the console window for the StopWatchService.exe to view the state transitions.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4ca90-132">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="4ca90-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4ca90-133">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="4ca90-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4ca90-134">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="4ca90-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4ca90-135">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="4ca90-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`