---
title: 使用 Send 的通道缓存
ms.date: 03/30/2017
ms.assetid: e69a2502-25cb-43bf-b8d2-95fbdecb41cb
ms.openlocfilehash: 619088def1f5e443a31244516655d75d1e25c9cb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43475850"
---
# <a name="channel-caching-with-send"></a><span data-ttu-id="e6008-102">使用 Send 的通道缓存</span><span class="sxs-lookup"><span data-stu-id="e6008-102">Channel Caching with Send</span></span>
<span data-ttu-id="e6008-103"><xref:System.ServiceModel.Activities.SendMessageChannelCache> 使用户能够对 <xref:System.ServiceModel.Activities.Send> 和 <xref:System.ServiceModel.Activities.SendParametersContent> 活动使用不同级别的通道缓存。</span><span class="sxs-lookup"><span data-stu-id="e6008-103">The <xref:System.ServiceModel.Activities.SendMessageChannelCache> enables users to have different levels of channel caching with <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.SendParametersContent> activities.</span></span> <span data-ttu-id="e6008-104">默认情况下将启用实例级别的缓存，此示例将演示以下功能：</span><span class="sxs-lookup"><span data-stu-id="e6008-104">Instance-level caching is enabled by default and this sample demonstrates the following features:</span></span>  
  
1.  <span data-ttu-id="e6008-105">跨应用程序域共享 <xref:System.ServiceModel.Activities.SendMessageChannelCache>。</span><span class="sxs-lookup"><span data-stu-id="e6008-105">Share a <xref:System.ServiceModel.Activities.SendMessageChannelCache> across an application domain.</span></span>  
  
2.  <span data-ttu-id="e6008-106">禁用通道缓存。</span><span class="sxs-lookup"><span data-stu-id="e6008-106">Disable channel caching.</span></span>  
  
3.  <span data-ttu-id="e6008-107">在 <xref:System.ServiceModel.Activities.SendMessageChannelCache> 中的工作流实例之间共享 <xref:System.ServiceModel.Activities.WorkflowServiceHost>。</span><span class="sxs-lookup"><span data-stu-id="e6008-107">Share a <xref:System.ServiceModel.Activities.SendMessageChannelCache> among workflow instances in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="e6008-108">演示</span><span class="sxs-lookup"><span data-stu-id="e6008-108">Demonstrates</span></span>  
 <span data-ttu-id="e6008-109"><xref:System.ServiceModel.Activities.SendMessageChannelCache> 扩展、<xref:System.ServiceModel.Activities.Send>、<xref:System.ServiceModel.Activities.Receive>、<xref:System.ServiceModel.Activities.ReceiveContent> 和 <xref:System.ServiceModel.Activities.SendReply> 活动。</span><span class="sxs-lookup"><span data-stu-id="e6008-109"><xref:System.ServiceModel.Activities.SendMessageChannelCache> extension, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.ReceiveContent> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e6008-110">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="e6008-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e6008-111">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中加载项目解决方案，然后生成项目。</span><span class="sxs-lookup"><span data-stu-id="e6008-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="e6008-112">运行在 \EchoWorkflowService\bin\debug 中生成的 EchoWorkflowService 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e6008-112">Run the EchoWorkflowService application generated in \EchoWorkflowService\bin\debug.</span></span>  
  
3.  <span data-ttu-id="e6008-113">运行在 \EchoWorkflowService\bin\debug 中生成的 EchoWorkflowClient 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e6008-113">Run the EchoWorkflowClient application generated in .\EchoWorkflowClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="e6008-114">客户端对服务调用 Echo 操作，并输出结果。</span><span class="sxs-lookup"><span data-stu-id="e6008-114">The client calls the Echo operation on the service and prints the results.</span></span> <span data-ttu-id="e6008-115">输出结果后，按 Enter 退出客户端和服务。</span><span class="sxs-lookup"><span data-stu-id="e6008-115">When the results have been printed, press ENTER to exit the client and the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e6008-116">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="e6008-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e6008-117">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="e6008-117">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e6008-118">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="e6008-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e6008-119">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="e6008-119">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ChannelCache`
