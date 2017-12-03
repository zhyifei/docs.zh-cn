---
title: "编写自定义活动入门"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3902f5fa-8a43-4048-8a6a-6b15472f90f0
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0cf8bd0368977b665f2ea412e4debbc1f681e5f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="getting-started-writing-a-custom-activity"></a><span data-ttu-id="2a115-102">编写自定义活动入门</span><span class="sxs-lookup"><span data-stu-id="2a115-102">Getting Started Writing a Custom Activity</span></span>
<span data-ttu-id="2a115-103">此示例演示如何在 XAML 中定义简单自定义活动。</span><span class="sxs-lookup"><span data-stu-id="2a115-103">This sample demonstrates how to define a simple custom activity in XAML.</span></span> <span data-ttu-id="2a115-104">该活动获得的名称为 `Rhyme`，其逻辑是一个包含三个 <xref:System.Activities.Statements.WriteLine> 活动的序列。</span><span class="sxs-lookup"><span data-stu-id="2a115-104">The activity is given the name `Rhyme`, and its logic is a sequence of three <xref:System.Activities.Statements.WriteLine> activities.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2a115-105">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="2a115-105">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2a115-106">打开**Simple.sln**示例中的解决方案[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2a115-106">Open the **Simple.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="2a115-107">生成和运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="2a115-107">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2a115-108">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="2a115-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2a115-109">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="2a115-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2a115-110">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="2a115-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2a115-111">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="2a115-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\GettingStarted`