---
title: 终结点：地址、绑定和协定
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: 3e78e7cf0c5acde53d7ee23294fd52134414e860
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207521"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a><span data-ttu-id="c263f-102">终结点：地址、绑定和协定</span><span class="sxs-lookup"><span data-stu-id="c263f-102">Endpoints: Addresses, Bindings, and Contracts</span></span>
<span data-ttu-id="c263f-103">与 Windows Communication Foundation (WCF) 服务的所有通信都是通过*终结点*的服务。</span><span class="sxs-lookup"><span data-stu-id="c263f-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="c263f-104">终结点向客户端访问 WCF 服务提供的功能。</span><span class="sxs-lookup"><span data-stu-id="c263f-104">Endpoints provide clients access to the functionality offered by a WCF service.</span></span>  
  
 <span data-ttu-id="c263f-105">每个终结点包含四个属性：</span><span class="sxs-lookup"><span data-stu-id="c263f-105">Each endpoint consists of four properties:</span></span>  
  
-   <span data-ttu-id="c263f-106">一个指示可以查找终结点的位置的地址。</span><span class="sxs-lookup"><span data-stu-id="c263f-106">An address that indicates where the endpoint can be found.</span></span>  
  
-   <span data-ttu-id="c263f-107">一个指定客户端如何与终结点进行通信的绑定。</span><span class="sxs-lookup"><span data-stu-id="c263f-107">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
-   <span data-ttu-id="c263f-108">一个标识可用操作的协定。</span><span class="sxs-lookup"><span data-stu-id="c263f-108">A contract that identifies the operations available.</span></span>  
  
-   <span data-ttu-id="c263f-109">一组指定终结点的本地实现细节的行为。</span><span class="sxs-lookup"><span data-stu-id="c263f-109">A set of behaviors that specify local implementation details of the endpoint.</span></span>  
  
 <span data-ttu-id="c263f-110">本主题讨论此终结点结构并说明如何在 WCF 对象模型中表示。</span><span class="sxs-lookup"><span data-stu-id="c263f-110">This topic discusses this endpoint structure and explains how it is represented in the WCF object model.</span></span>  
  
## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="c263f-111">终结点的结构</span><span class="sxs-lookup"><span data-stu-id="c263f-111">The Structure of an Endpoint</span></span>  
 <span data-ttu-id="c263f-112">每个终结点由以下内容组成：</span><span class="sxs-lookup"><span data-stu-id="c263f-112">Each endpoint consists of the following:</span></span>  
  
-   <span data-ttu-id="c263f-113">地址:地址唯一标识终结点，并告知潜在所在的服务的使用者。</span><span class="sxs-lookup"><span data-stu-id="c263f-113">Address: The address uniquely identifies the endpoint and tells potential consumers of the service where it is located.</span></span> <span data-ttu-id="c263f-114">通过在 WCF 对象模型中表示<xref:System.ServiceModel.EndpointAddress>类。</span><span class="sxs-lookup"><span data-stu-id="c263f-114">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="c263f-115">一个 <xref:System.ServiceModel.EndpointAddress> 类包含：</span><span class="sxs-lookup"><span data-stu-id="c263f-115">An <xref:System.ServiceModel.EndpointAddress> class contains:</span></span>  
  
    -   <span data-ttu-id="c263f-116">一个表示服务地址的 <xref:System.ServiceModel.EndpointAddress.Uri%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="c263f-116">A <xref:System.ServiceModel.EndpointAddress.Uri%2A> property, which represents the address of the service.</span></span>  
  
    -   <span data-ttu-id="c263f-117">一个表示服务安全标识和可选消息头集合的 <xref:System.ServiceModel.EndpointAddress.Identity%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="c263f-117">An <xref:System.ServiceModel.EndpointAddress.Identity%2A> property, which represents the security identity of the service and a collection of optional message headers.</span></span> <span data-ttu-id="c263f-118">可选消息头用于提供其他更多详细寻址信息来标识终结点或与终结点交互。</span><span class="sxs-lookup"><span data-stu-id="c263f-118">The optional message headers are used to provide additional and more detailed addressing information to identify or interact with the endpoint.</span></span>  
  
     <span data-ttu-id="c263f-119">有关详细信息，请参阅[指定一个终结点地址](../../../../docs/framework/wcf/specifying-an-endpoint-address.md)。</span><span class="sxs-lookup"><span data-stu-id="c263f-119">For more information, see [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
-   <span data-ttu-id="c263f-120">绑定：绑定指定如何与终结点进行通信。</span><span class="sxs-lookup"><span data-stu-id="c263f-120">Binding: The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="c263f-121">这包括：</span><span class="sxs-lookup"><span data-stu-id="c263f-121">This includes:</span></span>  
  
    -   <span data-ttu-id="c263f-122">要使用的传输协议（例如，TCP 或 HTTP）。</span><span class="sxs-lookup"><span data-stu-id="c263f-122">The transport protocol to use (for example, TCP or HTTP).</span></span>  
  
    -   <span data-ttu-id="c263f-123">要用于消息的编码（例如，文本或二进制）。</span><span class="sxs-lookup"><span data-stu-id="c263f-123">The encoding to use for the messages (for example, text or binary).</span></span>  
  
    -   <span data-ttu-id="c263f-124">必需的安全要求（例如，SSL 或 SOAP 消息安全）。</span><span class="sxs-lookup"><span data-stu-id="c263f-124">The necessary security requirements (for example, SSL or SOAP message security).</span></span>  
  
     <span data-ttu-id="c263f-125">有关详细信息，请参阅[WCF 绑定概述](../../../../docs/framework/wcf/bindings-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c263f-125">For more information, see [WCF Bindings Overview](../../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="c263f-126">一个绑定由 WCF 对象模型中的抽象基类<xref:System.ServiceModel.Channels.Binding>。</span><span class="sxs-lookup"><span data-stu-id="c263f-126">A binding is represented in the WCF object model by the abstract base class <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="c263f-127">大多数情况下，用户可以使用系统提供的绑定之一。</span><span class="sxs-lookup"><span data-stu-id="c263f-127">For most scenarios, users can use one of the system-provided bindings.</span></span> <span data-ttu-id="c263f-128">有关详细信息，请参阅[System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="c263f-128">For more information, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
-   <span data-ttu-id="c263f-129">约定：协定概述了终结点公开给客户端的功能。</span><span class="sxs-lookup"><span data-stu-id="c263f-129">Contracts: The contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="c263f-130">协定指定：</span><span class="sxs-lookup"><span data-stu-id="c263f-130">A contract specifies:</span></span>  
  
    -   <span data-ttu-id="c263f-131">客户端可以调用的操作。</span><span class="sxs-lookup"><span data-stu-id="c263f-131">What operations can be called by a client.</span></span>  
  
    -   <span data-ttu-id="c263f-132">消息的窗体。</span><span class="sxs-lookup"><span data-stu-id="c263f-132">The form of the message.</span></span>  
  
    -   <span data-ttu-id="c263f-133">调用操作所需的输入参数或数据的类型。</span><span class="sxs-lookup"><span data-stu-id="c263f-133">The type of input parameters or data required to call the operation.</span></span>  
  
    -   <span data-ttu-id="c263f-134">客户端可以预期的处理或响应消息的类型。</span><span class="sxs-lookup"><span data-stu-id="c263f-134">What type of processing or response message the client can expect.</span></span>  
  
     <span data-ttu-id="c263f-135">有关定义协定的详细信息，请参阅[Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="c263f-135">For more information about defining a contract, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
-   <span data-ttu-id="c263f-136">行为：终结点行为可用于自定义服务终结点的本地行为。</span><span class="sxs-lookup"><span data-stu-id="c263f-136">Behaviors: You can use endpoint behaviors to customize the local behavior of the service endpoint.</span></span> <span data-ttu-id="c263f-137">终结点行为通过参与构建 WCFruntime 的过程中实现此目的。</span><span class="sxs-lookup"><span data-stu-id="c263f-137">Endpoint behaviors achieve this by participating in the process of building a WCFruntime.</span></span> <span data-ttu-id="c263f-138">终结点行为的一个示例是 <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> 属性，可以利用该属性指定与 SOAP 或 Web 服务描述语言 (WSDL) 地址不同的侦听地址。</span><span class="sxs-lookup"><span data-stu-id="c263f-138">An example of an endpoint behavior is the <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> property, which allows you to specify a different listening address than the SOAP or Web Services Description Language (WSDL) address.</span></span> <span data-ttu-id="c263f-139">有关详细信息，请参阅[ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md)。</span><span class="sxs-lookup"><span data-stu-id="c263f-139">For more information, see [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).</span></span>  
  
## <a name="defining-endpoints"></a><span data-ttu-id="c263f-140">定义终结点</span><span class="sxs-lookup"><span data-stu-id="c263f-140">Defining Endpoints</span></span>  
 <span data-ttu-id="c263f-141">可以通过使用代码以强制方式或通过配置以声明方式指定服务的终结点。</span><span class="sxs-lookup"><span data-stu-id="c263f-141">You can specify the endpoint for a service either imperatively using code or declaratively through configuration.</span></span> <span data-ttu-id="c263f-142">有关详细信息，请参阅[如何：在配置中创建的服务终结点](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)和[如何：在代码中创建的服务终结点](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)。</span><span class="sxs-lookup"><span data-stu-id="c263f-142">For more information, see [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) and [How to: Create a Service Endpoint in Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c263f-143">本节内容</span><span class="sxs-lookup"><span data-stu-id="c263f-143">In This Section</span></span>  
 <span data-ttu-id="c263f-144">本节说明了绑定、终结点和地址的用途，演示了如何配置绑定和终结点，并演示了如何使用 `ClientVia` 行为和 `ListenUri` 属性。</span><span class="sxs-lookup"><span data-stu-id="c263f-144">This section explains the purpose of bindings, endpoints, and addresses; shows how to configure a binding and an endpoint; and demonstrates how to use the `ClientVia` behavior and `ListenUri` property.</span></span>  
  
 [<span data-ttu-id="c263f-145">地址</span><span class="sxs-lookup"><span data-stu-id="c263f-145">Addresses</span></span>](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 <span data-ttu-id="c263f-146">介绍如何在 WCF 中寻址终结点。</span><span class="sxs-lookup"><span data-stu-id="c263f-146">Describes how endpoints are addressed in WCF.</span></span>  
  
 [<span data-ttu-id="c263f-147">绑定</span><span class="sxs-lookup"><span data-stu-id="c263f-147">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 <span data-ttu-id="c263f-148">描述如何使用绑定指定客户端与服务相互通信所需的传输、编码和协议详细信息。</span><span class="sxs-lookup"><span data-stu-id="c263f-148">Describes how bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span>  
  
 [<span data-ttu-id="c263f-149">协定</span><span class="sxs-lookup"><span data-stu-id="c263f-149">Contracts</span></span>](../../../../docs/framework/wcf/feature-details/contracts.md)  
 <span data-ttu-id="c263f-150">描述协定如何定义服务的方法。</span><span class="sxs-lookup"><span data-stu-id="c263f-150">Describes how contracts define the methods of a service.</span></span>  
  
 [<span data-ttu-id="c263f-151">如何：在配置中创建服务终结点</span><span class="sxs-lookup"><span data-stu-id="c263f-151">How to: Create a Service Endpoint in Configuration</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="c263f-152">描述如何在配置中创建服务终结点。</span><span class="sxs-lookup"><span data-stu-id="c263f-152">Describes how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="c263f-153">如何：在代码中创建服务终结点</span><span class="sxs-lookup"><span data-stu-id="c263f-153">How to: Create a Service Endpoint in Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="c263f-154">描述如何在代码中创建服务终结点。</span><span class="sxs-lookup"><span data-stu-id="c263f-154">Describes how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="c263f-155">如何：使用 Svcutil.exe 验证已编译的服务代码</span><span class="sxs-lookup"><span data-stu-id="c263f-155">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 <span data-ttu-id="c263f-156">介绍了如何不承载服务使用情况下检测服务实现和配置中的错误[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="c263f-156">Describes how to detect errors in service implementations and configurations without hosting the service using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c263f-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="c263f-157">See also</span></span>

- [<span data-ttu-id="c263f-158">正在配置服务</span><span class="sxs-lookup"><span data-stu-id="c263f-158">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)
- [<span data-ttu-id="c263f-159">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="c263f-159">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
