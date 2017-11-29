---
title: "限制并行 ForEach"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6c8336060be48f55b974960e67ca1ebc57e76c63
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="throttled-parallel-foreach"></a><span data-ttu-id="f78c8-102">限制并行 ForEach</span><span class="sxs-lookup"><span data-stu-id="f78c8-102">Throttled Parallel ForEach</span></span>
<span data-ttu-id="f78c8-103">`ThrottleParallelForEach`活动是类似于<!--zz <xref:System.Activities.Statements.ParallelForEach>-->`System.Activities.Statements.ParallelForEach`活动有一个例外在于前者允许设置并发系数来限制要执行的并发分支的数目。</span><span class="sxs-lookup"><span data-stu-id="f78c8-103">The `ThrottleParallelForEach` activity is similar to the <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span> <span data-ttu-id="f78c8-104">`ThrottleParallelForEach` 活动派生自 <xref:System.Activities.NativeActivity>，因为该活动需要对其他活动（子活动）进行计划，并且只有通过 <xref:System.Activities.NativeActivityContext> 类才能对此进行访问。</span><span class="sxs-lookup"><span data-stu-id="f78c8-104">The `ThrottleParallelForEach` activity derives from <xref:System.Activities.NativeActivity>, because it needs to schedule other activities (the child activities) and this is only accessible through the <xref:System.Activities.NativeActivityContext> class.</span></span>  
  
## <a name="projects"></a><span data-ttu-id="f78c8-105">项目</span><span class="sxs-lookup"><span data-stu-id="f78c8-105">Projects</span></span>  
  
|<span data-ttu-id="f78c8-106">**ProjectName**</span><span class="sxs-lookup"><span data-stu-id="f78c8-106">**ProjectName**</span></span>|<span data-ttu-id="f78c8-107">**描述**</span><span class="sxs-lookup"><span data-stu-id="f78c8-107">**Description**</span></span>|<span data-ttu-id="f78c8-108">**主要文件**</span><span class="sxs-lookup"><span data-stu-id="f78c8-108">**Main Files**</span></span>|  
|-|-|-|  
|<span data-ttu-id="f78c8-109">ThrottledParallelForEach</span><span class="sxs-lookup"><span data-stu-id="f78c8-109">ThrottledParallelForEach</span></span>|<span data-ttu-id="f78c8-110">包含 `ThrottledParallelForEach` 活动及其设计器。</span><span class="sxs-lookup"><span data-stu-id="f78c8-110">Contains `ThrottledParallelForEach` activity and its designer.</span></span>|<span data-ttu-id="f78c8-111">ThrottledParallelForEach.cs</span><span class="sxs-lookup"><span data-stu-id="f78c8-111">ThrottledParallelForEach.cs</span></span><br /><br /> <span data-ttu-id="f78c8-112">`ThrottledParallelForEach` 活动定义。</span><span class="sxs-lookup"><span data-stu-id="f78c8-112">The `ThrottledParallelForEach` activity definition.</span></span>|  
|<span data-ttu-id="f78c8-113">CodeTestClient</span><span class="sxs-lookup"><span data-stu-id="f78c8-113">CodeTestClient</span></span>|<span data-ttu-id="f78c8-114">示例客户端应用程序，通过使用命令性代码的 `ThrottledParallelForEach` 来配置和运行工作流。</span><span class="sxs-lookup"><span data-stu-id="f78c8-114">Sample client application that configures and runs a workflow with a `ThrottledParallelForEach` using imperative code.</span></span>|<span data-ttu-id="f78c8-115">Program.cs</span><span class="sxs-lookup"><span data-stu-id="f78c8-115">Program.cs</span></span><br /><br /> <span data-ttu-id="f78c8-116">定义和运行示例工作流的实例。</span><span class="sxs-lookup"><span data-stu-id="f78c8-116">Defines and runs an instance of the sample workflow.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="f78c8-117">使用此示例</span><span class="sxs-lookup"><span data-stu-id="f78c8-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="f78c8-118">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 ThrottledParallelForEach.sln 文件。</span><span class="sxs-lookup"><span data-stu-id="f78c8-118">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ThrottledParallelForEach.sln file.</span></span>  
  
2.  <span data-ttu-id="f78c8-119">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="f78c8-119">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="f78c8-120">若要运行解决方案，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="f78c8-120">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f78c8-121">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="f78c8-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f78c8-122">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="f78c8-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f78c8-123">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="f78c8-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f78c8-124">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="f78c8-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`  
  
## <a name="see-also"></a><span data-ttu-id="f78c8-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f78c8-125">See Also</span></span>
