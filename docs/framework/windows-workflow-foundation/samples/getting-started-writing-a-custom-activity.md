---
title: 编写自定义活动入门
ms.date: 03/30/2017
ms.assetid: 3902f5fa-8a43-4048-8a6a-6b15472f90f0
ms.openlocfilehash: 4d9c140ca230750ca1119b33252b1edb8796d458
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43405223"
---
# <a name="getting-started-writing-a-custom-activity"></a><span data-ttu-id="70bac-102">编写自定义活动入门</span><span class="sxs-lookup"><span data-stu-id="70bac-102">Getting Started Writing a Custom Activity</span></span>
<span data-ttu-id="70bac-103">此示例演示如何在 XAML 中定义简单自定义活动。</span><span class="sxs-lookup"><span data-stu-id="70bac-103">This sample demonstrates how to define a simple custom activity in XAML.</span></span> <span data-ttu-id="70bac-104">该活动获得的名称为 `Rhyme`，其逻辑是一个包含三个 <xref:System.Activities.Statements.WriteLine> 活动的序列。</span><span class="sxs-lookup"><span data-stu-id="70bac-104">The activity is given the name `Rhyme`, and its logic is a sequence of three <xref:System.Activities.Statements.WriteLine> activities.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="70bac-105">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="70bac-105">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="70bac-106">打开**Simple.sln**示例解决方案中的[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="70bac-106">Open the **Simple.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="70bac-107">生成和运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="70bac-107">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="70bac-108">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="70bac-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="70bac-109">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="70bac-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="70bac-110">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="70bac-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="70bac-111">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="70bac-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\GettingStarted`