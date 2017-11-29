---
title: "使用 Discovery 客户端通道"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1494242a-1d64-4035-8ecd-eb4f06c8d2ba
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9d0aede489c6b5db029a9df37f84d0a067bbf836
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-discovery-client-channel"></a><span data-ttu-id="1567b-102">使用 Discovery 客户端通道</span><span class="sxs-lookup"><span data-stu-id="1567b-102">Using the Discovery Client Channel</span></span>
<span data-ttu-id="1567b-103">编写 WCF 客户端应用程序时，需要了解所调用服务的终结点地址。</span><span class="sxs-lookup"><span data-stu-id="1567b-103">When writing a WCF client application you need to know the endpoint address of the service you are calling.</span></span> <span data-ttu-id="1567b-104">在许多情况下，事先并不知晓服务的终结点地址，或者服务地址会随时间变化。</span><span class="sxs-lookup"><span data-stu-id="1567b-104">In many situations the endpoint address of a service is not known in advance or the address of the service changes over time.</span></span> <span data-ttu-id="1567b-105">Discovery 客户端通道可用于编写 WCF 客户端应用程序，描述您要调用的服务，并且自动发送探测请求。</span><span class="sxs-lookup"><span data-stu-id="1567b-105">The Discovery Client Channel allows you to write a WCF client application, describe the service you want to call, and the client channel automatically sends a probe request.</span></span> <span data-ttu-id="1567b-106">如果有服务做出响应，Discovery 客户端通道会从探测响应中检索该服务的终结点地址，并使用该地址调用服务。</span><span class="sxs-lookup"><span data-stu-id="1567b-106">When a service responds, the discovery client channel retrieves the endpoint address for the service from the probe response and uses it to call the service.</span></span>  
  
## <a name="using-the-discovery-client-channel"></a><span data-ttu-id="1567b-107">使用 Discovery 客户端通道</span><span class="sxs-lookup"><span data-stu-id="1567b-107">Using the Discovery Client Channel</span></span>  
 <span data-ttu-id="1567b-108">若要使用 Discovery 客户端通道，请将 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> 实例添加到客户端通道堆栈。</span><span class="sxs-lookup"><span data-stu-id="1567b-108">To use the Discovery Client Channel, add an instance of the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> to your client channel stack.</span></span> <span data-ttu-id="1567b-109">此外，也可以使用 <xref:System.ServiceModel.Discovery.DynamicEndpoint>。如果尚不存在 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>，则会自动将该绑定元素添加到绑定。</span><span class="sxs-lookup"><span data-stu-id="1567b-109">Alternatively you can use the <xref:System.ServiceModel.Discovery.DynamicEndpoint> and a <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> is automatically added to your binding if not already present.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="1567b-110">建议将 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> 作为客户端通道堆栈的最顶层元素。</span><span class="sxs-lookup"><span data-stu-id="1567b-110">It is recommended that the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> is the top-most element on your client channel stack.</span></span> <span data-ttu-id="1567b-111">在 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> 之上添加的任何绑定元素都必须确保 <xref:System.ServiceModel.ChannelFactory> 或自己创建的通道不使用终结点地址或 `Via` 地址（传递到 `CreateChannel` 方法），因为它们包含的地址可能不正确。</span><span class="sxs-lookup"><span data-stu-id="1567b-111">Any binding element that is added on top of the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> must make sure that the <xref:System.ServiceModel.ChannelFactory> or channel it creates does not use the endpoint address or `Via` address (passed to the `CreateChannel` method) because they may not contain the correct address.</span></span>  
  
 <span data-ttu-id="1567b-112"><xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> 类包含两个公共属性：</span><span class="sxs-lookup"><span data-stu-id="1567b-112">The <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> class contains two public properties:</span></span>  
  
1.  <span data-ttu-id="1567b-113"><xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement.FindCriteria%2A>，用于描述您要调用的服务。</span><span class="sxs-lookup"><span data-stu-id="1567b-113"><xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement.FindCriteria%2A>, which is used to describe the service you want to call.</span></span>  
  
2.  <!--zz <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement.DiscoveryEndpoint%2A>  --> `DiscoveryEndpoint`, which specifies the discovery endpoint to send discovery messages to.  
  
 <span data-ttu-id="1567b-114"><xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement.FindCriteria%2A> 属性可用于指定要搜索的服务协定、任何必需的范围 URI 以及打开通道的最大尝试次数。</span><span class="sxs-lookup"><span data-stu-id="1567b-114">The <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement.FindCriteria%2A> property allows you to specify the service contract you are searching for, any required scope URIs, and the maximum number of time to attempt to open the channel.</span></span> <span data-ttu-id="1567b-115">协定类型由调用的构造函数指定 <<!--zz <xref:System.ServiceModel.Discovery.FindCriteria%2A>  --> `FindCriteria`>。</span><span class="sxs-lookup"><span data-stu-id="1567b-115">The contract type is specified by calling the constructor <<!--zz <xref:System.ServiceModel.Discovery.FindCriteria%2A>  --> `FindCriteria`> .</span></span> <span data-ttu-id="1567b-116">可以将范围 URI 添加到 <xref:System.ServiceModel.Discovery.FindCriteria.Scopes%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="1567b-116">Scope URIs can be added to the <xref:System.ServiceModel.Discovery.FindCriteria.Scopes%2A> property.</span></span> <span data-ttu-id="1567b-117"><xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> 属性可用于指定客户端尝试连接的最大结果数。</span><span class="sxs-lookup"><span data-stu-id="1567b-117">The <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> property allows you to specify the maximum number of results to which the client tries to connect to.</span></span> <span data-ttu-id="1567b-118">客户端收到探测响应时，会尝试使用探测响应提供的终结点地址打开通道。</span><span class="sxs-lookup"><span data-stu-id="1567b-118">When a probe response is received the client attempts to open the channel using the endpoint address from the probe response.</span></span> <span data-ttu-id="1567b-119">如果出现异常，客户端会转到下一个探测响应，如有必要，会等待接收更多响应。</span><span class="sxs-lookup"><span data-stu-id="1567b-119">If an exception occurs the client moves on to the next probe response, waiting for more responses to be received if necessary.</span></span> <span data-ttu-id="1567b-120">客户端将继续执行此操作，直至成功打开通道或者达到最大结果数。</span><span class="sxs-lookup"><span data-stu-id="1567b-120">It continues to do this until the channel is successfully opened or the maximum number of results is reached.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="1567b-121">这些设置，请参阅 <<!--zz <xref:System.ServiceModel.Discovery.FindCriteria%2A>  --> `FindCriteria`>。</span><span class="sxs-lookup"><span data-stu-id="1567b-121"> these settings, see <<!--zz <xref:System.ServiceModel.Discovery.FindCriteria%2A>  --> `FindCriteria`>.</span></span>  
  
 <span data-ttu-id="1567b-122"><!--zz <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement.DiscoveryEndpoint%2A>  --> `DiscoveryEndpoint%2A>`属性允许你指定要使用的发现终结点。</span><span class="sxs-lookup"><span data-stu-id="1567b-122">The <!--zz <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement.DiscoveryEndpoint%2A>  --> `DiscoveryEndpoint%2A>` property allows you to specify the discovery endpoint to use.</span></span> <span data-ttu-id="1567b-123">该终结点通常是 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>，但也可能是任何有效的终结点。</span><span class="sxs-lookup"><span data-stu-id="1567b-123">Normally this is a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, but it can be any valid endpoint.</span></span>  
  
 <span data-ttu-id="1567b-124">创建用于与服务通信的绑定时，必须注意使用与服务完全相同的绑定。</span><span class="sxs-lookup"><span data-stu-id="1567b-124">When you are creating the binding to use to communicate with the service, you must be careful to use the exact same binding as the service.</span></span> <span data-ttu-id="1567b-125">唯一的区别是客户端绑定在堆栈顶层有一个 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="1567b-125">The only difference is the client binding has a <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> on the top of the stack.</span></span> <span data-ttu-id="1567b-126">如果服务使用系统提供的绑定之一，则创建新 <xref:System.ServiceModel.Channels.CustomBinding>，并在系统提供的绑定中将新绑定传递到 <!--zz <xref:System.ServiceModel.CustomBinding.CustomBinding%2A> `CustomBinding` --> 构造函数。</span><span class="sxs-lookup"><span data-stu-id="1567b-126">If service is using one of the system-provided bindings, create a new <xref:System.ServiceModel.Channels.CustomBinding> and pass in the system-provided binding to the <!--zz <xref:System.ServiceModel.CustomBinding.CustomBinding%2A> `CustomBinding` --> constructor.</span></span> <span data-ttu-id="1567b-127">然后，可以添加<xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>通过调用`Insert`上<!--zz <xref:System.ServiceModel.Channels.Binding.Elements%2A> -->`Elements`属性。</span><span class="sxs-lookup"><span data-stu-id="1567b-127">Then you can add the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> by calling `Insert` on the <!--zz <xref:System.ServiceModel.Channels.Binding.Elements%2A> --> `Elements` property.</span></span>  
  
 <span data-ttu-id="1567b-128">将 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> 添加到绑定并进行配置之后，即可创建 WCF 客户端类的实例、打开该实例以及调用该实例的方法。</span><span class="sxs-lookup"><span data-stu-id="1567b-128">Once you have added the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> to your binding and configured it, you can create an instance of the WCF client class, open it, and call its methods.</span></span> <span data-ttu-id="1567b-129">下面的示例使用 Discovery 客户端通道发现某个 WCF 服务，该服务实现 `ICalculator` 类（在“WCF 入门教程”中使用该类）并调用该类的 `Add` 方法。</span><span class="sxs-lookup"><span data-stu-id="1567b-129">The following example uses the Discovery Client Channel to discover a WCF service that implements the `ICalculator` class (used in the Getting Started WCF tutorial) and calls its `Add` method.</span></span>  
  
```  
// Create the DiscoveryClientBindingElement  
DiscoveryClientBindingElement bindingElement = new DiscoveryClientBindingElement();  
// Search for a service that implements the ICalculator interface, attempting to open  
// the channel a maximum of 2 times  
bindingElement.FindCriteria = new FindCriteria(typeof(ICalculator)) { MaxResults = 2 };  
// Use the UdpDiscoveryEndpoint  
bindingElement.DiscoveryEndpoint = new UdpDiscoveryEndpoint();  
  
// The service uses the BasicHttpBinding, so use that and insert the DiscoveryClientBindingElement at the   
// top of the stack  
CustomBinding binding = new CustomBinding(new BasicHttpBinding());  
binding.Elements.Insert(0,bindingElement);  
  
try  
{  
    // Create the WCF client and call a method  
    CalculatorClient client = new CalculatorClient(binding, new EndpointAddress("http://schemas.microsoft.com/dynamic"));  
    client.Open();  
    client.Add(1, 1);  
}  
catch (EndpointNotFoundException ex)  
{  
    Console.WriteLine("An exception occurred: " + ex.Message);  
}  
```  
  
## <a name="security-and-the-discovery-client-channel"></a><span data-ttu-id="1567b-130">安全性和 Discovery 客户端通道</span><span class="sxs-lookup"><span data-stu-id="1567b-130">Security and the Discovery Client Channel</span></span>  
 <span data-ttu-id="1567b-131">使用 Discovery 客户端通道时，同时指定了两个终结点：</span><span class="sxs-lookup"><span data-stu-id="1567b-131">When using the discovery client channel, two endpoints are being specified.</span></span> <span data-ttu-id="1567b-132">其中一个用于发现消息，通常为 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>；另一个是应用程序终结点。</span><span class="sxs-lookup"><span data-stu-id="1567b-132">One is used for discovery messages, usually <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, and the other is the application endpoint.</span></span> <span data-ttu-id="1567b-133">实现安全服务时，必须谨慎以确保这两个终结点的安全。</span><span class="sxs-lookup"><span data-stu-id="1567b-133">When implementing a secure service, care must be taken to secure both endpoints.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="1567b-134">安全，请参阅[保护服务和客户端](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="1567b-134"> security, see [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span></span>
