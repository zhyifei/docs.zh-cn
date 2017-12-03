---
title: "相关计算器"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c365166e-6552-49a4-bf17-9f4e597d4d41
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6296ecb5c708d344624cac6e24247d2163fd66b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="correlated-calculator"></a><span data-ttu-id="dd4ed-102">相关计算器</span><span class="sxs-lookup"><span data-stu-id="dd4ed-102">Correlated Calculator</span></span>
<span data-ttu-id="dd4ed-103">此示例演示如何基于消息中的参数，将设计器中的消息传递活动（<xref:System.ServiceModel.Activities.Receive> 和 <xref:System.ServiceModel.Activities.SendReply>）与基于内容的相关性一起使用。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-103">This sample demonstrates how to use the messaging activities (<xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply>) in the designer with content-based correlation based on a parameter in the message.</span></span> <span data-ttu-id="dd4ed-104">在此方案中，计算器的操作在一个并行的队列中。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-104">In this scenario, the operations of the calculator are in a parallel convoy.</span></span> <span data-ttu-id="dd4ed-105">在将第一条消息发送到工作流时，将创建一个实例和一个相关性（基于 `CalculatorId`），后续的具有相同 `CalculatorId` 的消息将被调度到该实例，直到调用 Reset 操作。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-105">Both an instance and a correlation (based on `CalculatorId`) are created when the first message is sent to the workflow, and subsequent messages with the same `CalculatorId` are dispatched to that instance until the Reset operation is called.</span></span> <span data-ttu-id="dd4ed-106">客户端作为一个 WPF 应用程序实现，它使用基于代码的客户端代理与服务通信。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-106">The client is implemented as a WPF application that uses a code-based client proxy to communicate with the service.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="dd4ed-107">使用此示例</span><span class="sxs-lookup"><span data-stu-id="dd4ed-107">To use this sample</span></span>  
  
1.  <span data-ttu-id="dd4ed-108">使用提升的权限启动 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]，打开 For.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-108">Start [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] in elevated permissions, open the For.sln solution file.</span></span>  
  
    1.  <span data-ttu-id="dd4ed-109">导航到包含 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-109">Navigate to the folder that contains [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    2.  <span data-ttu-id="dd4ed-110">右击 Devenv.exe 并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-110">Right-click Devenv.exe and select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="dd4ed-111">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 CorrelatedCalculator.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-111">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CorrelatedCalculator.sln solution file.</span></span>  
  
3.  <span data-ttu-id="dd4ed-112">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-112">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="dd4ed-113">若要运行服务项目，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-113">To run the service project, press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="dd4ed-114">在服务准备就绪并开始侦听消息之后，在“解决方案资源管理器”中右击“Client”项目，并运行它。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-114">Once the service is ready and listening for messages, in Solution Explorer, right-click the Client project and run it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dd4ed-115">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dd4ed-116">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="dd4ed-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dd4ed-117">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dd4ed-118">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="dd4ed-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\CorellatedCalculator`