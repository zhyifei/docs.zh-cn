---
title: "公开和调用 ActivityActions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4285718ef1829e9432957278d5ca7959e32e4511
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="exposing-and-invoking-activityactions"></a><span data-ttu-id="3daed-102">公开和调用 ActivityActions</span><span class="sxs-lookup"><span data-stu-id="3daed-102">Exposing and Invoking ActivityActions</span></span>
<span data-ttu-id="3daed-103">此示例演示如何开发具有 <xref:System.Activities.ActivityAction> 的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="3daed-103">This sample demonstrates how to develop a custom activity that has an <xref:System.Activities.ActivityAction>.</span></span> <span data-ttu-id="3daed-104">它还演示如何通过提供 <xref:System.Activities.ActivityAction> 的实现来使用此活动。</span><span class="sxs-lookup"><span data-stu-id="3daed-104">It also demonstrates how to use this activity by providing an implementation of the <xref:System.Activities.ActivityAction>.</span></span>  
  
 <span data-ttu-id="3daed-105"><xref:System.Activities.ActivityAction>允许活动作者公开的"漏洞"具有特定签名活动用户可以在其中插入自定义行为。</span><span class="sxs-lookup"><span data-stu-id="3daed-105">An <xref:System.Activities.ActivityAction> allows an activity author to expose "holes" with specific signatures where the activity user can plug in a custom behavior.</span></span> <span data-ttu-id="3daed-106">例如， <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach`活动，（针对进行操作的项的集合），具有<xref:System.Activities.ActivityAction>，它允许活动用户插入针对当前迭代项进行操作的行为。</span><span class="sxs-lookup"><span data-stu-id="3daed-106">For example, the <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` activity, (which operates over a collection of items), has an <xref:System.Activities.ActivityAction> that allows the activity user to plug in behavior that operates on the current iteration item.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3daed-107">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="3daed-107">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="3daed-108">打开**ActivityAction.sln**示例中的解决方案[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3daed-108">Open the **ActivityAction.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="3daed-109">生成和运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="3daed-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3daed-110">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="3daed-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3daed-111">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="3daed-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3daed-112">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="3daed-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3daed-113">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="3daed-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`