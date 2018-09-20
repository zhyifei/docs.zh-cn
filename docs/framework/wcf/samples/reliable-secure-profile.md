---
title: 可靠安全配置文件
ms.date: 03/30/2017
ms.assetid: 921edc41-e91b-40f9-bde9-b6148b633e61
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: dfdafbcdc461c80192e310a86d5bff50f0885283
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2018
ms.locfileid: "46471166"
---
# <a name="reliable-secure-profile"></a><span data-ttu-id="f869c-102">可靠安全配置文件</span><span class="sxs-lookup"><span data-stu-id="f869c-102">Reliable Secure Profile</span></span>
<span data-ttu-id="f869c-103">此示例演示如何编写 WCF 并[可靠安全配置文件](https://go.microsoft.com/fwlink/?LinkId=178140)(RSP)。</span><span class="sxs-lookup"><span data-stu-id="f869c-103">This sample demonstrates how to compose WCF and [Reliable Secure Profile](https://go.microsoft.com/fwlink/?LinkId=178140) (RSP).</span></span> <span data-ttu-id="f869c-104">此示例演示如何实现[建立连接](https://go.microsoft.com/fwlink/?LinkId=178141)通道以及可靠的消息传送和 （可选） 可以编写基于 RSP 规范的创建的可靠安全绑定的安全通道。</span><span class="sxs-lookup"><span data-stu-id="f869c-104">This sample demonstrates the implementation of a [Make Connection](https://go.microsoft.com/fwlink/?LinkId=178141) channel which can be composed together with Reliable Messaging and optionally a secure channel to create a Reliable Secure Binding based on the RSP specification.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f869c-105">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="f869c-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f869c-106">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="f869c-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f869c-107">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="f869c-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f869c-108">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="f869c-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ReliableSecureProfile`  
  
## <a name="discussion"></a><span data-ttu-id="f869c-109">讨论</span><span class="sxs-lookup"><span data-stu-id="f869c-109">Discussion</span></span>  
 <span data-ttu-id="f869c-110">此示例演示可靠的异步双向消息交换方案。</span><span class="sxs-lookup"><span data-stu-id="f869c-110">This sample demonstrates a reliable asynchronous two-way message exchange scenario.</span></span> <span data-ttu-id="f869c-111">该服务有双工协定，客户端实现双工回调协定。</span><span class="sxs-lookup"><span data-stu-id="f869c-111">The service has a duplex contract and the client implements the duplex callback contract.</span></span> <span data-ttu-id="f869c-112">客户端向服务发出请求，应在单独的连接上响应该请求。</span><span class="sxs-lookup"><span data-stu-id="f869c-112">The client initiates a request to a service, for which a response is expected on a separate connection.</span></span> <span data-ttu-id="f869c-113">会以可靠方式发送请求消息。</span><span class="sxs-lookup"><span data-stu-id="f869c-113">The request message is sent reliably.</span></span> <span data-ttu-id="f869c-114">客户端不希望在其关闭时打开侦听终结点。</span><span class="sxs-lookup"><span data-stu-id="f869c-114">The client does not want to open a listening endpoint at its end.</span></span> <span data-ttu-id="f869c-115">因此，它将轮询具有“建立连接”请求的服务，以使服务在此“建立连接”请求的反向通道上发送回响应。</span><span class="sxs-lookup"><span data-stu-id="f869c-115">Thus, it polls the service with ‘Make Connection’ requests for the service to send back the response on the back channel of this ‘Make Connection’ request.</span></span> <span data-ttu-id="f869c-116">此示例演示如何通过 HTTP 进行安全可靠的双工通信，而无需客户端公开侦听终结点（并创建防火墙例外）。</span><span class="sxs-lookup"><span data-stu-id="f869c-116">This sample demonstrates how to have secure reliable duplex communication over HTTP without the client exposing a listening endpoint (and creating a firewall exception).</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f869c-117">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="f869c-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f869c-118">打开**reliablesecureprofile**解决方案。</span><span class="sxs-lookup"><span data-stu-id="f869c-118">Open the **ReliableSecureProfile** solution.</span></span>  
  
2.  <span data-ttu-id="f869c-119">右键单击**服务**项目中**解决方案资源管理器**，选择**调试**，**启动新实例**从上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="f869c-119">Right click the **Service** project in **Solution Explorer**, select **Debug**, **Start new instance** from the context menu.</span></span> <span data-ttu-id="f869c-120">这会启动服务主机。</span><span class="sxs-lookup"><span data-stu-id="f869c-120">This starts up the service host.</span></span>  
  
3.  <span data-ttu-id="f869c-121">右键单击**客户端**项目中**解决方案资源管理器**，选择**调试**，**启动新实例**从上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="f869c-121">Right click the **Client** project in **Solution Explorer**, select **Debug**, **Start new instance** from the context menu.</span></span> <span data-ttu-id="f869c-122">这会启动客户端。</span><span class="sxs-lookup"><span data-stu-id="f869c-122">This starts up the client.</span></span>  
  
4.  <span data-ttu-id="f869c-123">在客户端控制台窗口中出现提示时键入任意字符串，然后单击 ENTER。这会将输入字符串发送到计算此字符串的哈希的服务。</span><span class="sxs-lookup"><span data-stu-id="f869c-123">Type in any string in the prompt on the client console window and click ENTER.This sends the input string to the service, which computes a hash of this string.</span></span>  
  
5.  <span data-ttu-id="f869c-124">服务回调双工回调协定操作以在客户端控制台窗口中显示结果时，可在客户端窗口中查看结果。</span><span class="sxs-lookup"><span data-stu-id="f869c-124">View the result on the client windows when the service calls back the duplex callback contract operation to display the result on the client console window.</span></span> <span data-ttu-id="f869c-125">服务中会进行有意的延迟，以模拟长时间运行的处理数据操作。</span><span class="sxs-lookup"><span data-stu-id="f869c-125">There is an intentional delay on the service to simulate a long running operation of processing the data.</span></span>  
  
6.  <span data-ttu-id="f869c-126">监视 HTTP 通信（通过任何联机网络监视工具，如网络监视器和 Fiddler 等）会显示按照可靠安全配置文件在客户端和服务之间建立通信序列，以及客户端如何轮询具有“建立连接”请求的服务。</span><span class="sxs-lookup"><span data-stu-id="f869c-126">Monitoring the HTTP traffic (by any of the online network monitoring tools like Network Monitor, Fiddler and so on) shows that a sequence for communication is established between the client and the service as laid down by the Reliable Secure Profile, and how the client polls the service with ‘Make Connection’ requests.</span></span> <span data-ttu-id="f869c-127">服务准备好发送回经过处理的响应时，会使用上一个“建立连接”请求的反向通道来发送回结果。</span><span class="sxs-lookup"><span data-stu-id="f869c-127">When the service gets ready to send back the processed response, it uses the back channel of the last ‘Make Connection’ request to send back the results.</span></span>  
  
7.  <span data-ttu-id="f869c-128">在服务控制台窗口中按 ENTER 关闭服务。</span><span class="sxs-lookup"><span data-stu-id="f869c-128">Press ENTER on the service console window to close the service.</span></span> <span data-ttu-id="f869c-129">在客户端控制台窗口中按 ENTER 关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="f869c-129">Press ENTER on the client console window to close the client.</span></span>
