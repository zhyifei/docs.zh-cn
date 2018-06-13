---
title: 自定义绑定
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, endpoints
- Windows Communication Foundation, configuration
ms.assetid: 58532b6d-4eea-4a4f-854f-a1c8c842564d
ms.openlocfilehash: 6880b04a3f8a82c1e109c32674804c5241913a8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487067"
---
# <a name="custom-bindings"></a><span data-ttu-id="93e4b-102">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="93e4b-102">Custom Bindings</span></span>
<span data-ttu-id="93e4b-103">当系统提供的某个绑定不符合服务的要求时，可使用 <xref:System.ServiceModel.Channels.CustomBinding> 类。</span><span class="sxs-lookup"><span data-stu-id="93e4b-103">You can use the <xref:System.ServiceModel.Channels.CustomBinding> class when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="93e4b-104">所有绑定都是从绑定元素的有序集构造而来的。</span><span class="sxs-lookup"><span data-stu-id="93e4b-104">All bindings are constructed from an ordered set of binding elements.</span></span> <span data-ttu-id="93e4b-105">自定义绑定可以从一组系统提供的绑定元素生成，也可以包含用户定义的自定义绑定元素。</span><span class="sxs-lookup"><span data-stu-id="93e4b-105">Custom bindings can be built from a set of system-provided binding elements or can include user-defined custom binding elements.</span></span> <span data-ttu-id="93e4b-106">例如，可以使用自定义绑定元素在服务终结点使用新的传输或编码器。</span><span class="sxs-lookup"><span data-stu-id="93e4b-106">You can use custom binding elements, for example, to enable the use of new transports or encoders at a service endpoint.</span></span> <span data-ttu-id="93e4b-107">有关工作示例，请参阅[自定义绑定示例](http://msdn.microsoft.com/library/657e8143-beb0-472d-9cfe-ed1a19c2ab08)。</span><span class="sxs-lookup"><span data-stu-id="93e4b-107">For working examples, see [Custom Binding Samples](http://msdn.microsoft.com/library/657e8143-beb0-472d-9cfe-ed1a19c2ab08).</span></span> <span data-ttu-id="93e4b-108">有关详细信息，请参阅[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)。</span><span class="sxs-lookup"><span data-stu-id="93e4b-108">For more information, see [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
## <a name="construction-of-a-custom-binding"></a><span data-ttu-id="93e4b-109">自定义绑定的构造</span><span class="sxs-lookup"><span data-stu-id="93e4b-109">Construction of a Custom Binding</span></span>  
 <span data-ttu-id="93e4b-110">自定义绑定是使用 <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> 构造函数并通过“堆叠”在一起的绑定元素的集合构造的，这些元素的特定顺序如下：</span><span class="sxs-lookup"><span data-stu-id="93e4b-110">A custom binding is constructed using the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> constructor from a collection of binding elements that are "stacked" in a specific order:</span></span>  
  
-   <span data-ttu-id="93e4b-111">最顶层是一个允许流事务的可选 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> 类。</span><span class="sxs-lookup"><span data-stu-id="93e4b-111">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> class that allows flowing transactions.</span></span>  
  
-   <span data-ttu-id="93e4b-112">接下来是一个可选的 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> 类，它提供了 WS-ReliableMessaging 规范中定义的会话和排序机制。</span><span class="sxs-lookup"><span data-stu-id="93e4b-112">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> class that provides a session and ordering mechanisms as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="93e4b-113">会话可通过 SOAP 和传输中介。</span><span class="sxs-lookup"><span data-stu-id="93e4b-113">A session can cross SOAP and transport intermediaries.</span></span>  
  
-   <span data-ttu-id="93e4b-114">接下来是一个可选的 <xref:System.ServiceModel.Channels.SecurityBindingElement> 类，它提供了授权、身份验证、保护和机密性等安全功能。</span><span class="sxs-lookup"><span data-stu-id="93e4b-114">Next is an optional <xref:System.ServiceModel.Channels.SecurityBindingElement> class that provides security features such as authorization, authentication, protection, and confidentiality.</span></span>  
  
-   <span data-ttu-id="93e4b-115">接下来是一个可选的 <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> 类，它提供了通过本身不支持双工通信的传输协议（例如 HTTP）进行双向双工通信的功能。</span><span class="sxs-lookup"><span data-stu-id="93e4b-115">Next is an optional <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> class that provides the ability to have two way duplex communication with a transport protocol that does not support duplex communication natively, such as HTTP.</span></span>  
  
-   <span data-ttu-id="93e4b-116">接下来是一个可选的 <xref:System.ServiceModel.Channels.OneWayBindingElement> 类，它提供了单向通信。</span><span class="sxs-lookup"><span data-stu-id="93e4b-116">Next is an optional <xref:System.ServiceModel.Channels.OneWayBindingElement>) class that provides one-way communication.</span></span>  
  
-   <span data-ttu-id="93e4b-117">接下来是一个可选的流安全绑定元素，它可以是以下元素之一。</span><span class="sxs-lookup"><span data-stu-id="93e4b-117">Next is an optional stream security binding element which can be one of the following.</span></span>  
  
    -   <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
-   <span data-ttu-id="93e4b-118">再接下来是一个必需的消息编码绑定元素。</span><span class="sxs-lookup"><span data-stu-id="93e4b-118">Next is a required message encoding binding element.</span></span> <span data-ttu-id="93e4b-119">可以使用自己的消息编码器或者以下三种消息编码绑定之一：</span><span class="sxs-lookup"><span data-stu-id="93e4b-119">You can use your own message encoder or one of the three message encoding bindings:</span></span>  
  
    -   <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>  
  
 <span data-ttu-id="93e4b-120">底层是一个必需的传输元素。</span><span class="sxs-lookup"><span data-stu-id="93e4b-120">At the bottom is a required transport element.</span></span> <span data-ttu-id="93e4b-121">你可以使用自己的传输或 Windows Communication Foundation (WCF) 提供的以下传输绑定元素之一：</span><span class="sxs-lookup"><span data-stu-id="93e4b-121">You can use your own transport or one of the following transport binding elements Windows Communication Foundation (WCF) provides:</span></span>  
  
-   <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.PeerTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>  
  
-   <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>  
  
-   <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>  
  
 <span data-ttu-id="93e4b-122">下表总结了每层的选项。</span><span class="sxs-lookup"><span data-stu-id="93e4b-122">The following table summarizes the options for each layer.</span></span>  
  
|<span data-ttu-id="93e4b-123">层</span><span class="sxs-lookup"><span data-stu-id="93e4b-123">Layer</span></span>|<span data-ttu-id="93e4b-124">选项</span><span class="sxs-lookup"><span data-stu-id="93e4b-124">Options</span></span>|<span data-ttu-id="93e4b-125">必需</span><span class="sxs-lookup"><span data-stu-id="93e4b-125">Required</span></span>|  
|-----------|-------------|--------------|  
|<span data-ttu-id="93e4b-126">事务</span><span class="sxs-lookup"><span data-stu-id="93e4b-126">Transactions</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="93e4b-127">否</span><span class="sxs-lookup"><span data-stu-id="93e4b-127">No</span></span>|  
|<span data-ttu-id="93e4b-128">可靠性</span><span class="sxs-lookup"><span data-stu-id="93e4b-128">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="93e4b-129">No</span><span class="sxs-lookup"><span data-stu-id="93e4b-129">No</span></span>|  
|<span data-ttu-id="93e4b-130">安全性</span><span class="sxs-lookup"><span data-stu-id="93e4b-130">Security</span></span>|<xref:System.ServiceModel.Channels.SecurityBindingElement>|<span data-ttu-id="93e4b-131">否</span><span class="sxs-lookup"><span data-stu-id="93e4b-131">No</span></span>|  
|<span data-ttu-id="93e4b-132">编码</span><span class="sxs-lookup"><span data-stu-id="93e4b-132">Encoding</span></span>|<span data-ttu-id="93e4b-133">文本、二进制、消息传输优化机制 (MTOM)、自定义</span><span class="sxs-lookup"><span data-stu-id="93e4b-133">Text, binary, Message Transmission Optimization Mechanism (MTOM), custom</span></span>|<span data-ttu-id="93e4b-134">是</span><span class="sxs-lookup"><span data-stu-id="93e4b-134">Yes</span></span>|  
|<span data-ttu-id="93e4b-135">传输</span><span class="sxs-lookup"><span data-stu-id="93e4b-135">Transport</span></span>|<span data-ttu-id="93e4b-136">TCP、HTTP、HTTPS、命名管道（也称为 IPC）、对等 (P2P)、消息队列（也称为 MSMQ）、自定义</span><span class="sxs-lookup"><span data-stu-id="93e4b-136">TCP, HTTP, HTTPS, named pipes (also known as IPC), Peer-to-Peer (P2P), Message Queuing (also known as MSMQ), Custom</span></span>|<span data-ttu-id="93e4b-137">是</span><span class="sxs-lookup"><span data-stu-id="93e4b-137">Yes</span></span>|  
  
 <span data-ttu-id="93e4b-138">此外，可以定义自己的绑定元素，并将它们插在前面定义的任何层之间。</span><span class="sxs-lookup"><span data-stu-id="93e4b-138">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93e4b-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="93e4b-139">See Also</span></span>  
 [<span data-ttu-id="93e4b-140">终结点创建概述</span><span class="sxs-lookup"><span data-stu-id="93e4b-140">Endpoint Creation Overview</span></span>](../../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [<span data-ttu-id="93e4b-141">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="93e4b-141">Using Bindings to Configure Services and Clients</span></span>](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="93e4b-142">系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="93e4b-142">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [<span data-ttu-id="93e4b-143">如何：自定义系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="93e4b-143">How to: Customize a System-Provided Binding</span></span>](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)  
 [<span data-ttu-id="93e4b-144">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="93e4b-144">\<customBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="93e4b-145">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="93e4b-145">Custom Binding</span></span>](../../../../docs/framework/wcf/samples/custom-binding.md)
