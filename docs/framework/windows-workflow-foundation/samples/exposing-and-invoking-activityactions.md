---
title: 公开和调用 ActivityActions
ms.date: 03/30/2017
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
ms.openlocfilehash: 99207c33d82ec9028da2355cc792c366dc5e0cc6
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "47398558"
---
# <a name="exposing-and-invoking-activityactions"></a><span data-ttu-id="ae9b5-102">公开和调用 ActivityActions</span><span class="sxs-lookup"><span data-stu-id="ae9b5-102">Exposing and Invoking ActivityActions</span></span>
<span data-ttu-id="ae9b5-103">此示例演示如何开发具有 <xref:System.Activities.ActivityAction> 的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="ae9b5-103">This sample demonstrates how to develop a custom activity that has an <xref:System.Activities.ActivityAction>.</span></span> <span data-ttu-id="ae9b5-104">它还演示如何通过提供 <xref:System.Activities.ActivityAction> 的实现来使用此活动。</span><span class="sxs-lookup"><span data-stu-id="ae9b5-104">It also demonstrates how to use this activity by providing an implementation of the <xref:System.Activities.ActivityAction>.</span></span>  
  
 <span data-ttu-id="ae9b5-105"><xref:System.Activities.ActivityAction>允许活动作者公开"漏洞"具有特定签名的活动用户可在其中插入自定义行为。</span><span class="sxs-lookup"><span data-stu-id="ae9b5-105">An <xref:System.Activities.ActivityAction> allows an activity author to expose "holes" with specific signatures where the activity user can plug in a custom behavior.</span></span> <span data-ttu-id="ae9b5-106">例如，<xref:System.Activities.Statements.ForEach%601> 活动（针对项集合进行操作）具有一个 <xref:System.Activities.ActivityAction>，它允许活动用户插入针对当前迭代项进行操作的行为。</span><span class="sxs-lookup"><span data-stu-id="ae9b5-106">For example, the <xref:System.Activities.Statements.ForEach%601> activity, (which operates over a collection of items), has an <xref:System.Activities.ActivityAction> that allows the activity user to plug in behavior that operates on the current iteration item.</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ae9b5-107">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="ae9b5-107">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ae9b5-108">打开**ActivityAction.sln**示例解决方案中的[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ae9b5-108">Open the **ActivityAction.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="ae9b5-109">生成和运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="ae9b5-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ae9b5-110">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="ae9b5-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ae9b5-111">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="ae9b5-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ae9b5-112">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="ae9b5-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ae9b5-113">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="ae9b5-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`