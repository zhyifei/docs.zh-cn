---
title: 使用绑定配置服务和客户端
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings [WCF], using
ms.assetid: c39479c3-0766-4a17-ba4c-97a74607f392
caps.latest.revision: 33
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 68c8c2c93ce29147247c332848025fd931bf7854
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="using-bindings-to-configure-services-and-clients"></a><span data-ttu-id="760e5-102">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="760e5-102">Using Bindings to Configure Services and Clients</span></span>
<span data-ttu-id="760e5-103">绑定是指定连接到终结点所需的通信详细信息的对象。</span><span class="sxs-lookup"><span data-stu-id="760e5-103">Bindings are objects that specify the communication details required to connect to an endpoint.</span></span> <span data-ttu-id="760e5-104">更具体地说，绑定包含用于创建客户端或服务运行时的配置信息，创建方法是定义用于各个终结点或客户端通道的传输、连网格式（消息编码）和协议的具体内容。</span><span class="sxs-lookup"><span data-stu-id="760e5-104">More specifically, bindings contain configuration information that is used to create the client or service runtime by defining the specifics of transports, wire-formats (message encoding), and protocols to use for the respective endpoint or client channel.</span></span> <span data-ttu-id="760e5-105">若要创建运行的 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 服务，服务中的每个终结点都需要一个绑定。</span><span class="sxs-lookup"><span data-stu-id="760e5-105">To create a functioning [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service, each endpoint in the service requires a binding.</span></span> <span data-ttu-id="760e5-106">本主题解释什么是绑定、如何定义绑定以及如何为终结点指定特定的绑定。</span><span class="sxs-lookup"><span data-stu-id="760e5-106">This topic explains what bindings are, how they are defined, and how a particular binding is specified for an endpoint.</span></span>  
  
## <a name="what-a-binding-defines"></a><span data-ttu-id="760e5-107">绑定所定义的内容</span><span class="sxs-lookup"><span data-stu-id="760e5-107">What a Binding Defines</span></span>  
 <span data-ttu-id="760e5-108">绑定中的信息可能非常基本，也可能非常复杂。</span><span class="sxs-lookup"><span data-stu-id="760e5-108">The information in a binding can be very basic or very complex.</span></span> <span data-ttu-id="760e5-109">最基本的绑定仅指定连接终结点所必需的传输协议（如 HTTP）。</span><span class="sxs-lookup"><span data-stu-id="760e5-109">The most basic binding specifies only the transport protocol (such as HTTP) that must be used to connect to the endpoint.</span></span> <span data-ttu-id="760e5-110">一般来说，绑定包含的有关如何连接到终结点的信息属于下表中的某一类别。</span><span class="sxs-lookup"><span data-stu-id="760e5-110">More generally, the information a binding contains about how to connect to an endpoint falls into one of the categories in the following table.</span></span>  
  
 <span data-ttu-id="760e5-111">协议</span><span class="sxs-lookup"><span data-stu-id="760e5-111">Protocols</span></span>  
 <span data-ttu-id="760e5-112">确定要使用的安全机制（可靠消息传递功能或事务上下文流设置）。</span><span class="sxs-lookup"><span data-stu-id="760e5-112">Determines the security mechanism being used, either reliable messaging capability or transaction context flow settings.</span></span>  
  
 <span data-ttu-id="760e5-113">传输</span><span class="sxs-lookup"><span data-stu-id="760e5-113">Transport</span></span>  
 <span data-ttu-id="760e5-114">确定要使用的基础传输协议（例如，TCP 或 HTTP）。</span><span class="sxs-lookup"><span data-stu-id="760e5-114">Determines the underlying transport protocol to use (for example, TCP or HTTP).</span></span>  
  
 <span data-ttu-id="760e5-115">编码</span><span class="sxs-lookup"><span data-stu-id="760e5-115">Encoding</span></span>  
 <span data-ttu-id="760e5-116">确定消息编码（例如，文本/XML、二进制或消息传输优化机制），该编码确定消息如何在网络上表示为字节流。</span><span class="sxs-lookup"><span data-stu-id="760e5-116">Determines the message encoding, for example, text/XML, binary, or Message Transmission Optimization Mechanism (MTOM), which determines how messages are represented as byte streams on the wire.</span></span>  
  
## <a name="system-provided-bindings"></a><span data-ttu-id="760e5-117">系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="760e5-117">System-Provided Bindings</span></span>  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="760e5-118"> 包含一组系统提供的绑定，这些绑定旨在满足大多数应用程序要求和方案。</span><span class="sxs-lookup"><span data-stu-id="760e5-118"> includes a set of system-provided bindings that are designed to cover most application requirements and scenarios.</span></span> <span data-ttu-id="760e5-119">下面的类表示系统提供的绑定的一些示例：</span><span class="sxs-lookup"><span data-stu-id="760e5-119">The following classes represent some examples of system-provided bindings:</span></span>  
  
-   <span data-ttu-id="760e5-120"><xref:System.ServiceModel.BasicHttpBinding>：一个适于连接到符合 WS-I 基本配置文件 1.1 规范的 Web 服务（例如，ASP.NET Web 服务和基于 [ASMX] 的服务）的 HTTP 协议绑定。</span><span class="sxs-lookup"><span data-stu-id="760e5-120"><xref:System.ServiceModel.BasicHttpBinding>: An HTTP protocol binding suitable for connecting to Web services that conforms to the WS-I Basic Profile 1.1 specification (for example, ASP.NET Web services [ASMX]-based services).</span></span>  
  
-   <span data-ttu-id="760e5-121"><xref:System.ServiceModel.WSHttpBinding>：一个适于连接到符合 Web 服务规范协议的终结点的 HTTP 协议绑定。</span><span class="sxs-lookup"><span data-stu-id="760e5-121"><xref:System.ServiceModel.WSHttpBinding>: An HTTP protocol binding suitable for connecting to endpoints that conform to the Web services specifications protocols.</span></span>  
  
-   <span data-ttu-id="760e5-122"><xref:System.ServiceModel.NetNamedPipeBinding>：将 .NET 二进制编码和组帧技术与 Windows 命名管道传输一起使用，以连接到同一计算机上的其他 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 终结点。</span><span class="sxs-lookup"><span data-stu-id="760e5-122"><xref:System.ServiceModel.NetNamedPipeBinding>: Uses the .NET binary encoding and framing technologies in conjunction with the Windows named pipe transport to connect to other [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] endpoints on the same machine.</span></span>  
  
-   <span data-ttu-id="760e5-123"><xref:System.ServiceModel.NetMsmqBinding>：将 .NET 二进制编码和组帧技术与消息队列（也称为 MSMQ）一起使用，以创建与其他 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 终结点的排队消息连接。</span><span class="sxs-lookup"><span data-stu-id="760e5-123"><xref:System.ServiceModel.NetMsmqBinding>: Uses the .NET binary encoding and framing technologies in conjunction with the Message Queuing (also known as MSMQ) to create queued message connections with other [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] endpoints.</span></span>  
  
 <span data-ttu-id="760e5-124">有关说明，使用系统提供的绑定的完整列表请参阅[系统提供的绑定](../../../docs/framework/wcf/system-provided-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="760e5-124">For a complete list of system-provided bindings, with descriptions, see [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
## <a name="custom-bindings"></a><span data-ttu-id="760e5-125">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="760e5-125">Custom Bindings</span></span>  
 <span data-ttu-id="760e5-126">如果系统提供的绑定集合不具有某一服务应用程序所需的正确功能组合，则可以创建 <xref:System.ServiceModel.Channels.CustomBinding> 绑定。</span><span class="sxs-lookup"><span data-stu-id="760e5-126">If the system-provided binding collection does not have the correct combination of features that a service application requires, you can create a <xref:System.ServiceModel.Channels.CustomBinding> binding.</span></span> <span data-ttu-id="760e5-127">有关详细信息，有关元素的<xref:System.ServiceModel.Channels.CustomBinding>绑定，请参阅[ \<customBinding >](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)和[自定义绑定](../../../docs/framework/wcf/extending/custom-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="760e5-127">For more information about the elements of a <xref:System.ServiceModel.Channels.CustomBinding> binding, see [\<customBinding>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) and [Custom Bindings](../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="using-bindings"></a><span data-ttu-id="760e5-128">使用绑定</span><span class="sxs-lookup"><span data-stu-id="760e5-128">Using Bindings</span></span>  
 <span data-ttu-id="760e5-129">使用绑定需要执行两个基本步骤：</span><span class="sxs-lookup"><span data-stu-id="760e5-129">Using bindings entails two basic steps:</span></span>  
  
1.  <span data-ttu-id="760e5-130">选择或定义绑定。</span><span class="sxs-lookup"><span data-stu-id="760e5-130">Select or define a binding.</span></span> <span data-ttu-id="760e5-131">最简单的方法就是选择一个系统提供的绑定并使用它的默认设置。</span><span class="sxs-lookup"><span data-stu-id="760e5-131">The easiest method is to choose one of the system-provided bindings and use its default settings.</span></span> <span data-ttu-id="760e5-132">您还可以选择一个系统提供的绑定，然后根据您的要求重新设置它的属性值。</span><span class="sxs-lookup"><span data-stu-id="760e5-132">You can also choose a system-provided binding and reset its property values to suit your requirements.</span></span> <span data-ttu-id="760e5-133">或者，您可以创建一个自定义绑定并根据需要设置每一个属性。</span><span class="sxs-lookup"><span data-stu-id="760e5-133">Alternatively, you can create a custom binding and set every property as required.</span></span>  
  
2.  <span data-ttu-id="760e5-134">创建使用此绑定的终结点。</span><span class="sxs-lookup"><span data-stu-id="760e5-134">Create an endpoint that uses this binding.</span></span>  
  
## <a name="code-and-configuration"></a><span data-ttu-id="760e5-135">代码和配置</span><span class="sxs-lookup"><span data-stu-id="760e5-135">Code and Configuration</span></span>  
 <span data-ttu-id="760e5-136">您可以通过代码或配置来定义或配置绑定。</span><span class="sxs-lookup"><span data-stu-id="760e5-136">You can define or configure bindings through code or configuration.</span></span> <span data-ttu-id="760e5-137">例如，这两种方法不受所用绑定的类型的影响，无论您是使用系统提供的绑定还是使用 <xref:System.ServiceModel.Channels.CustomBinding> 绑定。</span><span class="sxs-lookup"><span data-stu-id="760e5-137">These two approaches are independent of the type of binding used, for example, whether you are using a system-provided or a <xref:System.ServiceModel.Channels.CustomBinding> binding.</span></span> <span data-ttu-id="760e5-138">通常，使用代码可使您在编译时对绑定的定义拥有完全的控制权。</span><span class="sxs-lookup"><span data-stu-id="760e5-138">In general, using code gives you complete control over the definition of a binding when you compile.</span></span> <span data-ttu-id="760e5-139">另一方面，使用配置允许系统管理员或 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务或客户端的用户更改绑定的参数。</span><span class="sxs-lookup"><span data-stu-id="760e5-139">Using configuration, on the other hand, allows a system administrator or the user of a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service or client to change the parameters of bindings.</span></span> <span data-ttu-id="760e5-140">由于无法预测部署 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 应用程序的特定的计算机要求和网络状况，因而通常需要这种灵活性。</span><span class="sxs-lookup"><span data-stu-id="760e5-140">This flexibility is often desirable because there is no way to predict the specific machine requirements and network conditions into which a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] application is to be deployed.</span></span> <span data-ttu-id="760e5-141">从代码分隔绑定（和寻址）信息允许管理员无需重新编译或重新部署应用程序就可以更改绑定详细信息。</span><span class="sxs-lookup"><span data-stu-id="760e5-141">Separating the binding (and addressing) information from the code allows administrators to change the binding details without having to recompile or redeploy the application.</span></span> <span data-ttu-id="760e5-142">请注意，如果在代码中定义绑定，该绑定将覆盖配置文件中所指定的任何基于配置的定义。</span><span class="sxs-lookup"><span data-stu-id="760e5-142">Note that if the binding is defined in code, it overwrites any configuration-based definitions made in the configuration file.</span></span> <span data-ttu-id="760e5-143">有关这些方法的示例，请参见下面的主题：</span><span class="sxs-lookup"><span data-stu-id="760e5-143">For examples of these approaches, see the following topics:</span></span>  
  
-   <span data-ttu-id="760e5-144">[如何： 承载 WCF 服务中托管的应用程序](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)提供了在代码中创建绑定的示例。</span><span class="sxs-lookup"><span data-stu-id="760e5-144">[How to: Host a WCF Service in a Managed Application](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md) provides an example of creating a binding in code.</span></span>  
  
-   <span data-ttu-id="760e5-145">[如何： 配置客户端](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)提供创建客户端使用配置的示例。</span><span class="sxs-lookup"><span data-stu-id="760e5-145">[How to: Configure a Client](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md) provides an example of creating a client using configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="760e5-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="760e5-146">See Also</span></span>  
 [<span data-ttu-id="760e5-147">终结点创建概述</span><span class="sxs-lookup"><span data-stu-id="760e5-147">Endpoint Creation Overview</span></span>](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [<span data-ttu-id="760e5-148">如何：在配置中指定服务绑定</span><span class="sxs-lookup"><span data-stu-id="760e5-148">How to: Specify a Service Binding in Configuration</span></span>](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [<span data-ttu-id="760e5-149">如何：在代码中指定服务绑定</span><span class="sxs-lookup"><span data-stu-id="760e5-149">How to: Specify a Service Binding in Code</span></span>](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md)  
 [<span data-ttu-id="760e5-150">如何：在配置中指定客户端绑定</span><span class="sxs-lookup"><span data-stu-id="760e5-150">How to: Specify a Client Binding in Configuration</span></span>](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)  
 [<span data-ttu-id="760e5-151">如何：在代码中指定客户端绑定</span><span class="sxs-lookup"><span data-stu-id="760e5-151">How to: Specify a Client Binding in Code</span></span>](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-code.md)
