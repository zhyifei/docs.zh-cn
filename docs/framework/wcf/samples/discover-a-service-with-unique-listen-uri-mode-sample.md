---
title: 使用唯一侦听 Uri 模式示例发现服务
ms.date: 03/30/2017
ms.assetid: 9a6d35b2-0469-43c8-a0c9-63623e3d2733
ms.openlocfilehash: 7e1c5ae0cb1a44c72a27566035b4bc20acbf1614
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43882819"
---
# <a name="discover-a-service-with-unique-listen-uri-mode-sample"></a><span data-ttu-id="a896a-102">使用唯一侦听 Uri 模式示例发现服务</span><span class="sxs-lookup"><span data-stu-id="a896a-102">Discover a Service with Unique Listen Uri Mode Sample</span></span>
<span data-ttu-id="a896a-103">此示例演示如何发现 <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> 属性设置为 <xref:System.ServiceModel.Description.ListenUriMode.Unique> 的服务。</span><span class="sxs-lookup"><span data-stu-id="a896a-103">This sample demonstrates how to discover a service that has the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>.</span></span> <span data-ttu-id="a896a-104">当 <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> 属性设置为 <xref:System.ServiceModel.Description.ListenUriMode.Unique> 时，通过将端口设置为唯一或追加 GUID 使其对路径唯一来确保 ListenUri 唯一。</span><span class="sxs-lookup"><span data-stu-id="a896a-104">When the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>, the ListenUri is ensured to be unique by either setting the port to be unique or for the path to be unique by appending a GUID.</span></span>  
  
### <a name="features-on-the-service"></a><span data-ttu-id="a896a-105">服务上的功能</span><span class="sxs-lookup"><span data-stu-id="a896a-105">Features on the Service</span></span>  
 <span data-ttu-id="a896a-106">对于 TCP 终结点，<xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> 属性设置为 <xref:System.ServiceModel.Description.ListenUriMode.Unique>。</span><span class="sxs-lookup"><span data-stu-id="a896a-106">The <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique> for the TCP endpoint.</span></span> <span data-ttu-id="a896a-107">随后可在 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> 上发现服务。</span><span class="sxs-lookup"><span data-stu-id="a896a-107">The service is then made discoverable over a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint.</span></span>  
  
### <a name="features-on-the-client"></a><span data-ttu-id="a896a-108">客户端上的功能</span><span class="sxs-lookup"><span data-stu-id="a896a-108">Features on the Client</span></span>  
 <span data-ttu-id="a896a-109">此客户端使用 `Via.Uri` 方法通过正确的 <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> 连接到服务。</span><span class="sxs-lookup"><span data-stu-id="a896a-109">This client connects to the service using the correct `Via.Uri` by using the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method.</span></span> <span data-ttu-id="a896a-110">随后查询从该方法返回的 <xref:System.ServiceModel.Discovery.FindResponse>，以了解其是否包含有效的 <xref:System.ServiceModel.Endpoint.ListenUri%2A> 以及是否与 `Address.Uri` 不同。</span><span class="sxs-lookup"><span data-stu-id="a896a-110">The <xref:System.ServiceModel.Discovery.FindResponse> that is returned from the method is then queried for whether it contains a valid <xref:System.ServiceModel.Endpoint.ListenUri%2A> and whether it is different than `Address.Uri`.</span></span> <span data-ttu-id="a896a-111">随后会将合适的信息传递给 `InvokeCalculatorService` 方法。</span><span class="sxs-lookup"><span data-stu-id="a896a-111">The appropriate information is then passed to the `InvokeCalculatorService` method.</span></span> <span data-ttu-id="a896a-112">在 `InvokeCalculatorService` 方法中，调用方传入 <xref:System.ServiceModel.Endpoint.ListenUri%2A>，随后具有正确 `ClientViaBehavior` 的 `Via.Uri` 会添加到客户端的终结点。</span><span class="sxs-lookup"><span data-stu-id="a896a-112">In the `InvokeCalculatorService` method, the <xref:System.ServiceModel.Endpoint.ListenUri%2A> was passed in by the caller, then a `ClientViaBehavior` with the correct `Via.Uri` is added to the client’s endpoint.</span></span>  
  
##### <a name="to-use-this-sample"></a><span data-ttu-id="a896a-113">使用此示例</span><span class="sxs-lookup"><span data-stu-id="a896a-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="a896a-114">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 UniqueListenUriMode.sln。</span><span class="sxs-lookup"><span data-stu-id="a896a-114">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open UniqueListenUriMode.sln.</span></span>  
  
2.  <span data-ttu-id="a896a-115">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="a896a-115">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="a896a-116">运行在 [解决方案基目录]\service\bin\debug 文件夹中生成的服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="a896a-116">Run the service application, which is generated in the [solution base directory]\service\bin\debug folder.</span></span>  
  
4.  <span data-ttu-id="a896a-117">运行在 [解决方案基目录]\Client\bin\debug 文件夹中生成的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="a896a-117">Run the client application, which is generated in the [solution base directory]\Client\bin\debug folder.</span></span>  
  
     <span data-ttu-id="a896a-118">客户端定位正在运行的服务并向控制台写入服务终结点发布的元数据。</span><span class="sxs-lookup"><span data-stu-id="a896a-118">The client locates the running service and writes to the console the metadata published by the service’s endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a896a-119">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="a896a-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a896a-120">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="a896a-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a896a-121">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="a896a-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a896a-122">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="a896a-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\UniqueListenUriMode`  
  
## <a name="see-also"></a><span data-ttu-id="a896a-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="a896a-123">See Also</span></span>
