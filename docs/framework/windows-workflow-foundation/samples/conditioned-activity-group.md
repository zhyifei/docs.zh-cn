---
title: "条件活动组"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f76ef924-34ce-48ae-8c8d-48faf9697754
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e0df4ddc6f2cc5404c8153b30df66cda41487691
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="conditioned-activity-group"></a><span data-ttu-id="2dac3-102">条件活动组</span><span class="sxs-lookup"><span data-stu-id="2dac3-102">Conditioned Activity Group</span></span>
<span data-ttu-id="2dac3-103">此示例演示一个旅行预订应用程序。</span><span class="sxs-lookup"><span data-stu-id="2dac3-103">The sample demonstrates a travel booking application.</span></span> <span data-ttu-id="2dac3-104"><xref:System.Workflow.Activities.ConditionedActivityGroup> (CAG) 有两个代码活动：Car 活动和 Airline 活动。</span><span class="sxs-lookup"><span data-stu-id="2dac3-104">The <xref:System.Workflow.Activities.ConditionedActivityGroup> (CAG) has two code activities: a Car activity and an Airline activity.</span></span> <span data-ttu-id="2dac3-105">在 `SimpleCAGWorkflow` 构造函数中，已用所需旅行预订的类型填充了“travelNeedType”ArrayList 对象。</span><span class="sxs-lookup"><span data-stu-id="2dac3-105">In the `SimpleCAGWorkflow` constructor, a "travelNeedType" ArrayList object is populated with the types of travel bookings that are required.</span></span> <span data-ttu-id="2dac3-106">通过注释掉其中一个或全部两个 `travelNeeds.Add` 语句，将会相应地修改 CAG 行为。</span><span class="sxs-lookup"><span data-stu-id="2dac3-106">By commenting out one or both of the `travelNeeds.Add` statements, you modify the CAG behavior accordingly.</span></span> <span data-ttu-id="2dac3-107">Car 和 Airline 活动在它们的 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> 条件中都填充有 <xref:System.Workflow.Activities.CodeCondition>。</span><span class="sxs-lookup"><span data-stu-id="2dac3-107">Both the Car and Airline activities have their <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> condition populated with a <xref:System.Workflow.Activities.CodeCondition>.</span></span> <span data-ttu-id="2dac3-108">只有当 `travelNeeds` 集合具有 `TravelNeeds.Car` 项时，Car 活动才会执行，并且，只有当 `travelNeeds` 集合具有 `TravelNeeds.Airline` 项时，Airline 活动才会执行。</span><span class="sxs-lookup"><span data-stu-id="2dac3-108">The Car activity executes only if the `travelNeeds` collection has a `TravelNeeds.Car` entry, and the Airline activity executes only if the `travelNeeds` collection has a `TravelNeeds.Airline` entry.</span></span>  
  
 <span data-ttu-id="2dac3-109">每个活动执行时都会从集合中移除对应的项。</span><span class="sxs-lookup"><span data-stu-id="2dac3-109">The execution of each activity removes the corresponding entry from the collection.</span></span> <span data-ttu-id="2dac3-110">默认的 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> 条件指定：当没有子项在执行或者准备好执行时（根据其 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> 条件），CAG 应退出。</span><span class="sxs-lookup"><span data-stu-id="2dac3-110">The default <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> condition specifies that the CAG should exit when no children are executing or are ready for execution (based on their <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> conditions).</span></span> <span data-ttu-id="2dac3-111">在此示例中，这意味着 CAG 在 `travelNeeds` 集合为空时会退出。</span><span class="sxs-lookup"><span data-stu-id="2dac3-111">In this sample, this means that the CAG exits when the `travelNeeds` collection is empty.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="2dac3-112">生成示例</span><span class="sxs-lookup"><span data-stu-id="2dac3-112">To build the sample</span></span>  
  
1.  <span data-ttu-id="2dac3-113">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开解决方案。</span><span class="sxs-lookup"><span data-stu-id="2dac3-113">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="2dac3-114">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="2dac3-114">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="2dac3-115">按 Ctrl+F5 运行解决方案而不进行调试。</span><span class="sxs-lookup"><span data-stu-id="2dac3-115">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="2dac3-116">运行示例</span><span class="sxs-lookup"><span data-stu-id="2dac3-116">To run the sample</span></span>  
  
-   <span data-ttu-id="2dac3-117">在 SDK 命令提示窗口中，运行 SimpleCAG\bin\debug 文件夹（对于该示例的 Visual Basic 版本为 SimpleCAG\bin 文件夹）中的 .exe 文件，该文件夹位于该示例的主文件夹下。</span><span class="sxs-lookup"><span data-stu-id="2dac3-117">In the SDK Command Prompt window, run the .exe file in the SimpleCAG\bin\debug folder (or the SimpleCAG\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2dac3-118">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="2dac3-118">The samples may already be installed on your computer.</span></span> <span data-ttu-id="2dac3-119">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="2dac3-119">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2dac3-120">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="2dac3-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2dac3-121">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="2dac3-121">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\SimpleCAG`  
  
## <a name="see-also"></a><span data-ttu-id="2dac3-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2dac3-122">See Also</span></span>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>  
 <xref:System.Workflow.Activities.CodeCondition>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A>
