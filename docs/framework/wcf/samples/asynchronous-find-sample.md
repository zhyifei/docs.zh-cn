---
title: 异步查找示例
ms.date: 03/30/2017
ms.assetid: 7a713a25-c1f4-42e1-8c4a-93d64ca45a3b
ms.openlocfilehash: ed900ba3cd1b55f4e35ec0d2b92ef6b7283b498e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33500260"
---
# <a name="asynchronous-find-sample"></a><span data-ttu-id="f1ef7-102">异步查找示例</span><span class="sxs-lookup"><span data-stu-id="f1ef7-102">Asynchronous Find Sample</span></span>
<span data-ttu-id="f1ef7-103">此示例演示如何使用客户端应用程序中的异步查找操作。</span><span class="sxs-lookup"><span data-stu-id="f1ef7-103">This sample shows how to use the asynchronous find operation from a client application.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="f1ef7-104">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="f1ef7-104">Sample Details</span></span>  
 <span data-ttu-id="f1ef7-105">此设计模式的优点是以异步方式将作为查找请求的结果而找到的终结点通知客户端。</span><span class="sxs-lookup"><span data-stu-id="f1ef7-105">The benefit of following this design pattern is that the client is notified asynchronously of the endpoints located as a result of the find request.</span></span> <span data-ttu-id="f1ef7-106">若要查看其工作原理，请打开 Client.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="f1ef7-106">To see how this works, open the Client.cs file.</span></span> <span data-ttu-id="f1ef7-107">请注意，<xref:System.ServiceModel.Discovery.DiscoveryClient> 对象已将两个委托附加到它的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="f1ef7-107">Note the <xref:System.ServiceModel.Discovery.DiscoveryClient> object has two delegates attached to its event handlers.</span></span> <span data-ttu-id="f1ef7-108">引发 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> 事件时调用一个委托，每次引发 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> 事件时调用另一个委托。</span><span class="sxs-lookup"><span data-stu-id="f1ef7-108">One delegate is called when a <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> event is raised and another is called each time a <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> event is raised.</span></span> <span data-ttu-id="f1ef7-109">此示例演示如何在应用程序中使用此模式。</span><span class="sxs-lookup"><span data-stu-id="f1ef7-109">The sample shows how you can utilize this pattern in your application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1ef7-110">此示例使用 HTTP 终结点，若要运行此示例，必须添加正确的 URL ACL。</span><span class="sxs-lookup"><span data-stu-id="f1ef7-110">This sample uses HTTP endpoints and to run, proper URL ACLs must be added.</span></span> <span data-ttu-id="f1ef7-111">有关详细信息，请参阅[配置 HTTP 和 HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)。</span><span class="sxs-lookup"><span data-stu-id="f1ef7-111">For more information, see [Configuring HTTP and HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="f1ef7-112">使用提升的特权执行下面的命令应添加相应的 ACL。</span><span class="sxs-lookup"><span data-stu-id="f1ef7-112">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="f1ef7-113">如果该命令无效，则可能需要使用你的域和用户名替换以下自变量。</span><span class="sxs-lookup"><span data-stu-id="f1ef7-113">You may want to substitute your domain and username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f1ef7-114">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="f1ef7-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f1ef7-115">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 AsyncFind.sln。</span><span class="sxs-lookup"><span data-stu-id="f1ef7-115">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the AsyncFind.sln.</span></span>  
  
2.  <span data-ttu-id="f1ef7-116">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="f1ef7-116">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="f1ef7-117">打开 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 命令提示，导航到 \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug 或 \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug 目录，然后运行 Service.exe。</span><span class="sxs-lookup"><span data-stu-id="f1ef7-117">Open a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt and navigate to the \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug or \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug directory and run Service.exe.</span></span>  
  
4.  <span data-ttu-id="f1ef7-118">该服务启动后，导航到 \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug 或 WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug 目录，然后运行 Client.exe。</span><span class="sxs-lookup"><span data-stu-id="f1ef7-118">After the service has started, navigate to the \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug or WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug directory and run Client.exe.</span></span>  
  
5.  <span data-ttu-id="f1ef7-119">您将看到，客户端能够查找和调用该服务。</span><span class="sxs-lookup"><span data-stu-id="f1ef7-119">Observe the client is able to locate and call the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f1ef7-120">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="f1ef7-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f1ef7-121">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="f1ef7-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f1ef7-122">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="f1ef7-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f1ef7-123">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="f1ef7-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\AsyncFind`  
  
## <a name="see-also"></a><span data-ttu-id="f1ef7-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1ef7-124">See Also</span></span>
