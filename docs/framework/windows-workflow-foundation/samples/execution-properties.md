---
title: 执行属性
ms.date: 03/30/2017
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
ms.openlocfilehash: 4906c2ad11c8b5822764435d2b39a5b51f2673ba
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43748189"
---
# <a name="execution-properties"></a><span data-ttu-id="44c29-102">执行属性</span><span class="sxs-lookup"><span data-stu-id="44c29-102">Execution Properties</span></span>
<span data-ttu-id="44c29-103">此示例演示如何在自定义活动中定义并使用执行属性。</span><span class="sxs-lookup"><span data-stu-id="44c29-103">This sample shows how to define and use an execution property in a custom activity.</span></span> <span data-ttu-id="44c29-104">在此示例中，执行属性可确定控制台的前景色。</span><span class="sxs-lookup"><span data-stu-id="44c29-104">In this example, the execution property determines the console's foreground color.</span></span> <span data-ttu-id="44c29-105">示例工作流演示执行的各个逻辑路径（<xref:System.Activities.Statements.Parallel> 活动的分支）如何保留不同的控制台颜色，而不管活动的交错执行（跨 <xref:System.Activities.Statements.Parallel> 活动的分支）。</span><span class="sxs-lookup"><span data-stu-id="44c29-105">An example workflow shows how different logical paths of execution (branches of a <xref:System.Activities.Statements.Parallel> activity) can maintain different console colors despite interleaved execution of activities (across the branches of the <xref:System.Activities.Statements.Parallel> activity).</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="44c29-106">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="44c29-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="44c29-107">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 ExecutionProperties.sln 示例解决方案。</span><span class="sxs-lookup"><span data-stu-id="44c29-107">Open the ExecutionProperties.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44c29-108">由于必须在生成解决方案的同时生成使用的自定义活动，因此在生成解决方案前查看 ThreeColors.xaml 会显示错误。</span><span class="sxs-lookup"><span data-stu-id="44c29-108">Viewing ThreeColors.xaml before building the solution displays an error, because the custom activities used must be built at the same time as the solution.</span></span>  
  
2.  <span data-ttu-id="44c29-109">生成和运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="44c29-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="44c29-110">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="44c29-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="44c29-111">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="44c29-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="44c29-112">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="44c29-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="44c29-113">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="44c29-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`