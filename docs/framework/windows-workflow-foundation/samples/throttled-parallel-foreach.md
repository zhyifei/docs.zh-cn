---
title: 限制并行 ForEach
ms.date: 03/30/2017
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
ms.openlocfilehash: fd30a1ac587359a054a273b3deca2e9bb8bc2798
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261811"
---
# <a name="throttled-parallel-foreach"></a><span data-ttu-id="19bb7-102">限制并行 ForEach</span><span class="sxs-lookup"><span data-stu-id="19bb7-102">Throttled Parallel ForEach</span></span>

<span data-ttu-id="19bb7-103">`ThrottleParallelForEach` 活动类似于 <xref:System.Activities.Statements.ParallelForEach%601> 活动，不同之处在于前者允许设置并发系数来限制要执行的并发分支的数目。</span><span class="sxs-lookup"><span data-stu-id="19bb7-103">The `ThrottleParallelForEach` activity is similar to the <xref:System.Activities.Statements.ParallelForEach%601> activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span> <span data-ttu-id="19bb7-104">`ThrottleParallelForEach` 活动派生自 <xref:System.Activities.NativeActivity>，因为该活动需要对其他活动（子活动）进行计划，并且只有通过 <xref:System.Activities.NativeActivityContext> 类才能对此进行访问。</span><span class="sxs-lookup"><span data-stu-id="19bb7-104">The `ThrottleParallelForEach` activity derives from <xref:System.Activities.NativeActivity>, because it needs to schedule other activities (the child activities) and this is only accessible through the <xref:System.Activities.NativeActivityContext> class.</span></span>

## <a name="projects"></a><span data-ttu-id="19bb7-105">项目</span><span class="sxs-lookup"><span data-stu-id="19bb7-105">Projects</span></span>

|<span data-ttu-id="19bb7-106">**ProjectName**</span><span class="sxs-lookup"><span data-stu-id="19bb7-106">**ProjectName**</span></span>|<span data-ttu-id="19bb7-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="19bb7-107">**Description**</span></span>|<span data-ttu-id="19bb7-108">**主要文件**</span><span class="sxs-lookup"><span data-stu-id="19bb7-108">**Main Files**</span></span>|
|-|-|-|
|<span data-ttu-id="19bb7-109">ThrottledParallelForEach</span><span class="sxs-lookup"><span data-stu-id="19bb7-109">ThrottledParallelForEach</span></span>|<span data-ttu-id="19bb7-110">包含 `ThrottledParallelForEach` 活动及其设计器。</span><span class="sxs-lookup"><span data-stu-id="19bb7-110">Contains `ThrottledParallelForEach` activity and its designer.</span></span>|<span data-ttu-id="19bb7-111">ThrottledParallelForEach.cs</span><span class="sxs-lookup"><span data-stu-id="19bb7-111">ThrottledParallelForEach.cs</span></span><br /><br /> <span data-ttu-id="19bb7-112">`ThrottledParallelForEach` 活动定义。</span><span class="sxs-lookup"><span data-stu-id="19bb7-112">The `ThrottledParallelForEach` activity definition.</span></span>|
|<span data-ttu-id="19bb7-113">CodeTestClient</span><span class="sxs-lookup"><span data-stu-id="19bb7-113">CodeTestClient</span></span>|<span data-ttu-id="19bb7-114">示例客户端应用程序，通过使用命令性代码的 `ThrottledParallelForEach` 来配置和运行工作流。</span><span class="sxs-lookup"><span data-stu-id="19bb7-114">Sample client application that configures and runs a workflow with a `ThrottledParallelForEach` using imperative code.</span></span>|<span data-ttu-id="19bb7-115">Program.cs</span><span class="sxs-lookup"><span data-stu-id="19bb7-115">Program.cs</span></span><br /><br /> <span data-ttu-id="19bb7-116">定义和运行示例工作流的实例。</span><span class="sxs-lookup"><span data-stu-id="19bb7-116">Defines and runs an instance of the sample workflow.</span></span>|

## <a name="to-use-this-sample"></a><span data-ttu-id="19bb7-117">使用此示例</span><span class="sxs-lookup"><span data-stu-id="19bb7-117">To use this sample</span></span>

1. <span data-ttu-id="19bb7-118">使用 Visual Studio 2010 打开 ThrottledParallelForEach.sln 文件。</span><span class="sxs-lookup"><span data-stu-id="19bb7-118">Using Visual Studio 2010, open the ThrottledParallelForEach.sln file.</span></span>

2. <span data-ttu-id="19bb7-119">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="19bb7-119">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="19bb7-120">若要运行解决方案，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="19bb7-120">To run the solution, press F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19bb7-121">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="19bb7-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="19bb7-122">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="19bb7-122">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="19bb7-123">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="19bb7-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="19bb7-124">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="19bb7-124">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`