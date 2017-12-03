---
title: "自定义绑定命令"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e13bf96-5de0-4476-b646-5f150774418d
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 556f38ac6cbc3f4f279d238c592da2c72d84264f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="custom-binding-imperative"></a><span data-ttu-id="9bfe2-102">自定义绑定命令</span><span class="sxs-lookup"><span data-stu-id="9bfe2-102">Custom Binding Imperative</span></span>
<span data-ttu-id="9bfe2-103">本示例演示如何在不使用配置文件或 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 生成的客户端的情况下，编写命令性代码来定义和使用自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="9bfe2-103">The sample demonstrates how to write imperative code to define and use custom bindings without using a configuration file or a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] generated client.</span></span> <span data-ttu-id="9bfe2-104">本示例将 HTTP 传输提供的功能与可靠会话通道结合在一起，用于创建基于 HTTP 的可靠绑定。</span><span class="sxs-lookup"><span data-stu-id="9bfe2-104">This sample combines the features provided by the HTTP transport and the reliable session channel to create a reliable HTTP-based binding.</span></span> <span data-ttu-id="9bfe2-105">此示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)实现计算器服务。</span><span class="sxs-lookup"><span data-stu-id="9bfe2-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9bfe2-106">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="9bfe2-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="9bfe2-107">在客户端和服务上，创建包含两个绑定元素（可靠会话和 HTTP）的自定义绑定：</span><span class="sxs-lookup"><span data-stu-id="9bfe2-107">On both the client and the service, a custom binding is created that contains two binding elements (Reliable Session and HTTP):</span></span>  
  
```  
ReliableSessionBindingElement reliableSession = new ReliableSessionBindingElement();  
reliableSession.Ordered = true;  
  
HttpTransportBindingElement httpTransport = new HttpTransportBindingElement();  
httpTransport.AuthenticationScheme = System.Net.AuthenticationSchemes.Anonymous;  
httpTransport.HostNameComparisonMode = HostNameComparisonMode.StrongWildcard;  
  
CustomBinding binding = new CustomBinding(reliableSession, httpTransport);  
```  
  
 <span data-ttu-id="9bfe2-108">在服务上，通过将终结点添加到 ServiceHost 来使用绑定：</span><span class="sxs-lookup"><span data-stu-id="9bfe2-108">On the service, the binding is used by adding an endpoint to the ServiceHost:</span></span>  
  
```  
serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, "");  
```  
  
 <span data-ttu-id="9bfe2-109">在客户端上，<xref:System.ServiceModel.ChannelFactory> 使用绑定来创建服务通道：</span><span class="sxs-lookup"><span data-stu-id="9bfe2-109">On the client, the binding is used by a <xref:System.ServiceModel.ChannelFactory> to create a channel to the service:</span></span>  
  
```  
EndpointAddress address = new EndpointAddress("http://localhost:8000/servicemodelsamples/service");  
ChannelFactory<ICalculator> channelFactory = new ChannelFactory<ICalculator>(binding, address);  
ICalculator channel = channelFactory.CreateChannel();  
```  
  
 <span data-ttu-id="9bfe2-110">然后将此通道用于与服务进行交互：</span><span class="sxs-lookup"><span data-stu-id="9bfe2-110">This channel is then used to interact with the service:</span></span>  
  
```  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = channel.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
```  
  
 <span data-ttu-id="9bfe2-111">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="9bfe2-111">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="9bfe2-112">在客户端窗口中按 Enter 可以关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="9bfe2-112">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9bfe2-113">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="9bfe2-113">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="9bfe2-114">请确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="9bfe2-114">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="9bfe2-115">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="9bfe2-115">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="9bfe2-116">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="9bfe2-116">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9bfe2-117">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="9bfe2-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9bfe2-118">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="9bfe2-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9bfe2-119">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="9bfe2-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9bfe2-120">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="9bfe2-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\Custom\Imperative`  
  
## <a name="see-also"></a><span data-ttu-id="9bfe2-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9bfe2-121">See Also</span></span>  
 [<span data-ttu-id="9bfe2-122">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="9bfe2-122">Custom Binding</span></span>](http://msdn.microsoft.com/en-us/657e8143-beb0-472d-9cfe-ed1a19c2ab08)
