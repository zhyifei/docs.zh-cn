---
title: "SendParameters 和 ReceiveParameters 活动的基本用法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a45e04c4368406255736312503e19de95ed12150
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="basic-usage-of-sendparameters-and-receiveparameters-activities"></a><span data-ttu-id="f945f-102">SendParameters 和 ReceiveParameters 活动的基本用法</span><span class="sxs-lookup"><span data-stu-id="f945f-102">Basic Usage of SendParameters and ReceiveParameters Activities</span></span>
<span data-ttu-id="f945f-103">此示例演示如何使用 <xref:System.ServiceModel.Activities.SendParametersContent> 和 <xref:System.ServiceModel.Activities.ReceiveParametersContent> 活动。</span><span class="sxs-lookup"><span data-stu-id="f945f-103">This sample shows the use of <xref:System.ServiceModel.Activities.SendParametersContent> and <xref:System.ServiceModel.Activities.ReceiveParametersContent> activities.</span></span> <span data-ttu-id="f945f-104">此服务公开了一个操作，该操作获取一个字符串参数并将输入回显到客户端。</span><span class="sxs-lookup"><span data-stu-id="f945f-104">The service exposes one operation that takes a string argument and echoes the input back to the client.</span></span> <span data-ttu-id="f945f-105">此示例演示如何设置这些消息传递活动的参数。</span><span class="sxs-lookup"><span data-stu-id="f945f-105">The sample shows how to set up the parameters for these messaging activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f945f-106">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="f945f-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f945f-107">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="f945f-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f945f-108">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="f945f-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f945f-109">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="f945f-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### <a name="using-this-sample"></a><span data-ttu-id="f945f-110">使用此示例</span><span class="sxs-lookup"><span data-stu-id="f945f-110">Using this sample</span></span>  
  
1.  <span data-ttu-id="f945f-111">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中加载项目解决方案，然后生成项目。</span><span class="sxs-lookup"><span data-stu-id="f945f-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="f945f-112">首先运行 [解决方案基目录]\EchoWorkflowService\bin\debug 中生成的 EchoWorkflowService 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f945f-112">First run the EchoWorkflowService application generated in [solution base directory]\EchoWorkflowService\bin\debug.</span></span>  
  
3.  <span data-ttu-id="f945f-113">然后运行 [解决方案基目录]\EchoWorkflowClient\bin\debug 中生成的 EchoWorkflowClient 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f945f-113">Second, run the EchoWorkflowClient application generated in [solution base directory]\EchoWorkflowClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="f945f-114">客户端对服务调用 Echo 操作，并输出结果。</span><span class="sxs-lookup"><span data-stu-id="f945f-114">The client calls Echo operation on the service and prints the results.</span></span> <span data-ttu-id="f945f-115">完成后，请按 Enter 退出客户端，然后退出服务。</span><span class="sxs-lookup"><span data-stu-id="f945f-115">When complete, press ENTER to exit the client and then the service.</span></span>