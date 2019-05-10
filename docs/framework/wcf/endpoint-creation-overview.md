---
title: 终结点创建概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- endpoints [WCF], overview
ms.assetid: f4dce0fb-6f54-47e6-8054-86d7f574b91c
ms.openlocfilehash: fa6486db483c004430e0e8ed75c75a6b25c05d6b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64613592"
---
# <a name="endpoint-creation-overview"></a><span data-ttu-id="cbc16-102">终结点创建概述</span><span class="sxs-lookup"><span data-stu-id="cbc16-102">Endpoint Creation Overview</span></span>
<span data-ttu-id="cbc16-103">与 Windows Communication Foundation (WCF) 服务的所有通信都是通过*终结点*的服务。</span><span class="sxs-lookup"><span data-stu-id="cbc16-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="cbc16-104">终结点向客户端访问 WCF 服务提供的功能。</span><span class="sxs-lookup"><span data-stu-id="cbc16-104">Endpoints provide the clients access to the functionality that a WCF service offers.</span></span> <span data-ttu-id="cbc16-105">本节描述终结点的结构，并概述如何在配置和代码中定义终结点。</span><span class="sxs-lookup"><span data-stu-id="cbc16-105">This section describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code.</span></span>  
  
## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="cbc16-106">终结点的结构</span><span class="sxs-lookup"><span data-stu-id="cbc16-106">The Structure of an Endpoint</span></span>  
 <span data-ttu-id="cbc16-107">每个终结点包含一个指示可在何处找到此终结点的地址、一个指定客户端如何与此终结点进行通信的绑定和一个标识可用方法的协定。</span><span class="sxs-lookup"><span data-stu-id="cbc16-107">Each endpoint contains an address that indicates where to find the endpoint, a binding that specifies how a client can communicate with the endpoint, and a contract that identifies the methods available.</span></span>  
  
- <span data-ttu-id="cbc16-108">**地址**。</span><span class="sxs-lookup"><span data-stu-id="cbc16-108">**Address**.</span></span> <span data-ttu-id="cbc16-109">地址唯一标识终结点并告知潜在客户服务的所在位置。</span><span class="sxs-lookup"><span data-stu-id="cbc16-109">The address uniquely identifies the endpoint and tells potential consumers where the service is located.</span></span> <span data-ttu-id="cbc16-110">通过在 WCF 对象模型中表示<xref:System.ServiceModel.EndpointAddress>地址，其中包含统一资源标识符 (URI) 和地址属性，包括标识、 一些 Web 服务描述语言 (WSDL) 元素，以及一系列可选标头。</span><span class="sxs-lookup"><span data-stu-id="cbc16-110">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> address, which contains a Uniform Resource Identifier (URI) and address properties that include an identity, some Web Services Description Language (WSDL) elements, and a collection of optional headers.</span></span> <span data-ttu-id="cbc16-111">可选标头提供用于标识终结点或与终结点交互的其他详细寻址信息。</span><span class="sxs-lookup"><span data-stu-id="cbc16-111">The optional headers provide additional detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="cbc16-112">有关详细信息，请参阅[指定一个终结点地址](../../../docs/framework/wcf/specifying-an-endpoint-address.md)。</span><span class="sxs-lookup"><span data-stu-id="cbc16-112">For more information, see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
- <span data-ttu-id="cbc16-113">**绑定**。</span><span class="sxs-lookup"><span data-stu-id="cbc16-113">**Binding**.</span></span> <span data-ttu-id="cbc16-114">绑定指定如何与终结点进行通信。</span><span class="sxs-lookup"><span data-stu-id="cbc16-114">The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="cbc16-115">绑定指定终结点如何与世界通信，包括使用哪种传输协议（例如，TCP 或 HTTP）、对消息使用何种编码（例如，文本或二进制），以及需要何种安全要求（例如，安全套接字层 [SSL] 或 SOAP 消息安全）。</span><span class="sxs-lookup"><span data-stu-id="cbc16-115">The binding specifies how the endpoint communicates with the world, including which transport protocol to use (for example, TCP or HTTP), which encoding to use for the messages (for example, text or binary), and which security requirements are necessary (for example, Secure Sockets Layer [SSL] or SOAP message security).</span></span> <span data-ttu-id="cbc16-116">有关详细信息，请参阅[到配置服务和客户端使用的绑定](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="cbc16-116">For more information, see [Using Bindings to Configure Services and Clients](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span></span>  
  
- <span data-ttu-id="cbc16-117">**服务协定**。</span><span class="sxs-lookup"><span data-stu-id="cbc16-117">**Service contract**.</span></span> <span data-ttu-id="cbc16-118">服务协定概述了终结点向客户端公开的功能。</span><span class="sxs-lookup"><span data-stu-id="cbc16-118">The service contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="cbc16-119">协定指定客户端可以调用的操作、消息的形式、输入参数的类型或调用操作所需的数据，以及客户端应收到的处理消息或响应消息的种类。</span><span class="sxs-lookup"><span data-stu-id="cbc16-119">A contract specifies the operations that a client can call, the form of the message and the type of input parameters or data required to call the operation, and the kind of processing or response message the client can expect.</span></span> <span data-ttu-id="cbc16-120">三种基本的协定类型与基本消息交换模式 (MEP) 相对应：数据报（单向）、请求/答复和双工（双向）。</span><span class="sxs-lookup"><span data-stu-id="cbc16-120">Three basic types of contracts correspond to basic message exchange patterns (MEPs): datagram (one-way), request/reply, and duplex (bidirectional).</span></span> <span data-ttu-id="cbc16-121">当访问服务协定时，服务协定也可以采用数据和消息协定要求特定的数据类型和消息格式。</span><span class="sxs-lookup"><span data-stu-id="cbc16-121">The service contract can also employ data and message contracts to require specific data types and message formats when being accessed.</span></span> <span data-ttu-id="cbc16-122">有关如何定义服务协定的详细信息，请参阅[Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="cbc16-122">For more information about how to define a service contract, see [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span></span> <span data-ttu-id="cbc16-123">请注意，也可以要求客户端实现服务定义的协定（称为回调协定），以便在双工 MEP 下接收服务的消息。</span><span class="sxs-lookup"><span data-stu-id="cbc16-123">Note that a client may also be required to implement a service-defined contract, called a callback contract, to receive messages from the service in a duplex MEP.</span></span> <span data-ttu-id="cbc16-124">有关详细信息，请参阅[双工服务](../../../docs/framework/wcf/feature-details/duplex-services.md)。</span><span class="sxs-lookup"><span data-stu-id="cbc16-124">For more information, see [Duplex Services](../../../docs/framework/wcf/feature-details/duplex-services.md).</span></span>  
  
 <span data-ttu-id="cbc16-125">指定服务的终结点有两种方式，通过使用代码的强制方式或通过配置的声明方式。</span><span class="sxs-lookup"><span data-stu-id="cbc16-125">The endpoint for a service can be specified either imperatively by using code or declaratively through configuration.</span></span> <span data-ttu-id="cbc16-126">如果未指定任何终结点，则运行时通过为该服务实现的每个服务协定的每个基地址添加一个默认终结点，来提供默认终结点。</span><span class="sxs-lookup"><span data-stu-id="cbc16-126">If no endpoints are specified then the runtime provides default endpoints by adding one default endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="cbc16-127">在代码中定义终结点通常是不可行的，因为已部署服务的绑定和地址通常与在部署服务时所用的绑定和地址不同。</span><span class="sxs-lookup"><span data-stu-id="cbc16-127">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="cbc16-128">一般而言，使用配置定义服务终结点比使用代码更为可行。</span><span class="sxs-lookup"><span data-stu-id="cbc16-128">Generally, it is more practical to define service endpoints using configuration rather than code.</span></span> <span data-ttu-id="cbc16-129">通过将绑定和寻址信息放置在代码之外，可以在更改这些信息之后不必重新编译和重新部署应用程序。</span><span class="sxs-lookup"><span data-stu-id="cbc16-129">Keeping the binding and addressing information out of the code allows them to change without having to recompile and redeploy the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cbc16-130">添加执行模拟的服务终结点时，必须使用 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> 方法之一或 <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29> 方法来将协定正确加载到新的 <xref:System.ServiceModel.Description.ServiceDescription> 对象。</span><span class="sxs-lookup"><span data-stu-id="cbc16-130">When adding a service endpoint that performs impersonation, you must either use one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods or the <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29> method to properly load the contract into a new <xref:System.ServiceModel.Description.ServiceDescription> object.</span></span>  
  
## <a name="defining-endpoints-in-code"></a><span data-ttu-id="cbc16-131">在代码中定义终结点</span><span class="sxs-lookup"><span data-stu-id="cbc16-131">Defining Endpoints in Code</span></span>  
 <span data-ttu-id="cbc16-132">下面的示例说明如何在代码中指定终结点，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cbc16-132">The following example illustrates how to specify an endpoint in code with the following:</span></span>  
  
- <span data-ttu-id="cbc16-133">为定义协定`IEcho`类型的服务接受某人的名字并做出响应"Hello\<名称 > ！"。</span><span class="sxs-lookup"><span data-stu-id="cbc16-133">Define a contract for an `IEcho` type of service that accepts someone's name and echo with the response "Hello \<name>!".</span></span>  
  
- <span data-ttu-id="cbc16-134">实现由 `Echo` 协定定义的该类型的 `IEcho` 服务。</span><span class="sxs-lookup"><span data-stu-id="cbc16-134">Implement an `Echo` service of the type defined by the `IEcho` contract.</span></span>  
  
- <span data-ttu-id="cbc16-135">指定的终结点地址`http://localhost:8000/Echo`服务。</span><span class="sxs-lookup"><span data-stu-id="cbc16-135">Specify an endpoint address of `http://localhost:8000/Echo` for the service.</span></span>  
  
- <span data-ttu-id="cbc16-136">使用 `Echo` 绑定配置 <xref:System.ServiceModel.WSHttpBinding> 服务。</span><span class="sxs-lookup"><span data-stu-id="cbc16-136">Configure the `Echo` service using a <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
```csharp  
Namespace Echo  
{  
   // Define the contract for the IEcho service   
   [ServiceContract]  
   public interface IEcho  
   {  
       [OperationContract]  
       String Hello(string name)  
   }  
  
   // Create an Echo service that implements IEcho contract  
   class Echo : IEcho  
   {  
      public string Hello(string name)  
      {  
         return "Hello" + name + "!";  
      }  
      public static void Main ()  
      {  
          //Specify the base address for Echo service.  
          Uri echoUri = new Uri("http://localhost:8000/");  
  
          //Create a ServiceHost for the Echo service.  
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);  
  
          // Use a predefined WSHttpBinding to configure the service.  
          WSHttpBinding binding = new WSHttpBinding();  
  
          // Add the endpoint for this service to the service host.  
          serviceHost.AddServiceEndpoint(  
             typeof(IEcho),   
             binding,   
             echoUri  
           );  
  
          // Open the service host to run it.  
          serviceHost.Open();  
     }  
  }  
}  
```  
  
```vb  
' Define the contract for the IEcho service  
    <ServiceContract()> _  
    Public Interface IEcho  
        <OperationContract()> _  
        Function Hello(ByVal name As String) As String  
    End Interface  
  
' Create an Echo service that implements IEcho contract  
    Public Class Echo   
        Implements IEcho  
        Public Function Hello(ByVal name As String) As String _  
 Implements ICalculator.Hello  
            Dim result As String = "Hello" + name + "!"  
            Return result  
        End Function  
  
' Specify the base address for Echo service.  
Dim echoUri As Uri = New Uri("http://localhost:8000/")  
  
' Create a ServiceHost for the Echo service.  
Dim svcHost As ServiceHost = New ServiceHost(GetType(HelloWorld), echoUri)  
  
' Use a predefined WSHttpBinding to configure the service.  
Dim binding As New WSHttpBinding()  
  
' Add the endpoint for this service to the service host.  
serviceHost.AddServiceEndpoint(GetType(IEcho), binding, echoUri)  
  
' Open the service host to run it.  
serviceHost.Open()  
```  
  
> [!NOTE]
>  <span data-ttu-id="cbc16-137">使用基址创建服务主机，然后将与基址相关的其余地址指定为终结点的一部分。</span><span class="sxs-lookup"><span data-stu-id="cbc16-137">The service host is created with a base address and then the rest of the address, relative to the base address, is specified as part of an endpoint.</span></span> <span data-ttu-id="cbc16-138">这样划分地址可以更加方便地为主机上的服务定义多个终结点。</span><span class="sxs-lookup"><span data-stu-id="cbc16-138">This partitioning of the address allows multiple endpoints to be defined more conveniently for services at a host.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cbc16-139">不能在 <xref:System.ServiceModel.Description.ServiceDescription> 上的 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> 方法之后修改服务应用程序中的 <xref:System.ServiceModel.ServiceHostBase> 的属性。</span><span class="sxs-lookup"><span data-stu-id="cbc16-139">Properties of <xref:System.ServiceModel.Description.ServiceDescription> in the service application must not be modified subsequent to the <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> method on <xref:System.ServiceModel.ServiceHostBase>.</span></span> <span data-ttu-id="cbc16-140">如果修改通过该点的某些成员（如 <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> 属性以及 `AddServiceEndpoint` 和 <xref:System.ServiceModel.ServiceHostBase> 上的 <xref:System.ServiceModel.ServiceHost> 方法），则将引发异常。</span><span class="sxs-lookup"><span data-stu-id="cbc16-140">Some members, such as the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property and the `AddServiceEndpoint` methods on <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.ServiceHost>, throw an exception if modified past that point.</span></span> <span data-ttu-id="cbc16-141">允许修改其他成员，但结果不可确定。</span><span class="sxs-lookup"><span data-stu-id="cbc16-141">Others permit you to modify them, but the result is undefined.</span></span>  
>   
>  <span data-ttu-id="cbc16-142">同样，在调用 <xref:System.ServiceModel.Description.ServiceEndpoint> 上的 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> 之后不能在客户端上修改 <xref:System.ServiceModel.ChannelFactory> 值。</span><span class="sxs-lookup"><span data-stu-id="cbc16-142">Similarly, on the client the <xref:System.ServiceModel.Description.ServiceEndpoint> values must not be modified after the call to <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> on the <xref:System.ServiceModel.ChannelFactory>.</span></span> <span data-ttu-id="cbc16-143">如果修改通过该点的 <xref:System.ServiceModel.ChannelFactory.Credentials%2A> 属性，则此属性将引发异常。</span><span class="sxs-lookup"><span data-stu-id="cbc16-143">The <xref:System.ServiceModel.ChannelFactory.Credentials%2A> property throws an exception if modified past that point.</span></span> <span data-ttu-id="cbc16-144">可以对其他客户端说明值进行修改而不会出现错误，但结果不可确定。</span><span class="sxs-lookup"><span data-stu-id="cbc16-144">The other client description values can be modified without error, but the result is undefined.</span></span>  
>   
>  <span data-ttu-id="cbc16-145">无论是对于服务还是客户端，建议您在调用 <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> 之前修改说明。</span><span class="sxs-lookup"><span data-stu-id="cbc16-145">Whether for the service or client, it is recommended that you modify the description prior to calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span>  
  
## <a name="defining-endpoints-in-configuration"></a><span data-ttu-id="cbc16-146">在配置中定义终结点</span><span class="sxs-lookup"><span data-stu-id="cbc16-146">Defining Endpoints in Configuration</span></span>  
 <span data-ttu-id="cbc16-147">创建应用程序时，经常需要将一些决策交给部署该应用程序的管理员。</span><span class="sxs-lookup"><span data-stu-id="cbc16-147">When creating an application, you often want to defer decisions to the administrator who is deploying the application.</span></span> <span data-ttu-id="cbc16-148">例如，通常没有办法预先知道将使用什么服务地址（一个 URI）。</span><span class="sxs-lookup"><span data-stu-id="cbc16-148">For example, there is often no way of knowing in advance what a service address (a URI) will be.</span></span> <span data-ttu-id="cbc16-149">最好允许管理员在创建服务后指定地址，而不是对地址进行硬编码。</span><span class="sxs-lookup"><span data-stu-id="cbc16-149">Instead of hard-coding an address, it is preferable to allow an administrator to do so after creating a service.</span></span> <span data-ttu-id="cbc16-150">这种灵活性是通过配置实现的。</span><span class="sxs-lookup"><span data-stu-id="cbc16-150">This flexibility is accomplished through configuration.</span></span> <span data-ttu-id="cbc16-151">有关详细信息，请参阅[配置服务](../../../docs/framework/wcf/configuring-services.md)。</span><span class="sxs-lookup"><span data-stu-id="cbc16-151">For details, see [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cbc16-152">使用[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)与`/config:` *filename*`[,`*文件名*`]`切换到快速创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="cbc16-152">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) with the `/config:`*filename*`[,`*filename*`]` switch to quickly create configuration files.</span></span>  
  
## <a name="using-default-endpoints"></a><span data-ttu-id="cbc16-153">使用默认终结点</span><span class="sxs-lookup"><span data-stu-id="cbc16-153">Using Default Endpoints</span></span>  
 <span data-ttu-id="cbc16-154">如果在代码或配置中未指定任何终结点，则运行时通过为该服务实现的每个服务协定的每个基地址添加一个默认终结点，来提供默认终结点。</span><span class="sxs-lookup"><span data-stu-id="cbc16-154">If no endpoints are specified in code or in configuration then the runtime provides default endpoints by adding one default endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="cbc16-155">可以在代码或配置中指定基地址，默认终结点是在 <xref:System.ServiceModel.ICommunicationObject.Open> 上调用 <xref:System.ServiceModel.ServiceHost> 时添加的。</span><span class="sxs-lookup"><span data-stu-id="cbc16-155">The base address can be specified in code or in configuration, and the default endpoints are added when <xref:System.ServiceModel.ICommunicationObject.Open> is called on the <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="cbc16-156">此示例是上一节中的同一示例，但由于未指定任何终结点，因此添加了默认终结点。</span><span class="sxs-lookup"><span data-stu-id="cbc16-156">This example is the same example from the previous section, but since no endpoints are specified, the default endpoints are added.</span></span>  
  
```csharp  
Namespace Echo  
{  
   // Define the contract for the IEcho service   
   [ServiceContract]  
   Interface IEcho  
   {  
       [OperationContract]  
       String Hello(string name)  
   }  
  
   // Create an Echo service that implements IEcho contract  
   Class Echo : IEcho  
   {  
      Public string Hello(string name)  
      {  
         return "Hello" + name + "!";  
      }  
      static void Main ()  
      {  
          //Specify the base address for Echo service.  
          Uri echoUri = new Uri("http://localhost:8000/");  
  
          //Create a ServiceHost for the Echo service.  
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);  
  
          // Open the service host to run it. Default endpoints  
          // are added when the service is opened.  
          serviceHost.Open();  
     }  
  }  
}  
```  
  
```vb  
' Define the contract for the IEcho service  
    <ServiceContract()> _  
    Public Interface IEcho  
        <OperationContract()> _  
        Function Hello(ByVal name As String) As String  
    End Interface  
  
' Create an Echo service that implements IEcho contract  
    Public Class Echo   
        Implements IEcho  
        Public Function Hello(ByVal name As String) As String _  
 Implements ICalculator.Hello  
            Dim result As String = "Hello" + name + "!"  
            Return result  
        End Function  
  
' Specify the base address for Echo service.  
Dim echoUri As Uri = New Uri("http://localhost:8000/")  
  
' Open the service host to run it. Default endpoints  
' are added when the service is opened.  
serviceHost.Open()  
```  
  
 <span data-ttu-id="cbc16-157">如果显式提供了终结点，则仍可以添加默认终结点，方法是先在 <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> 上调用 <xref:System.ServiceModel.ServiceHost>，然后调用 <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>。</span><span class="sxs-lookup"><span data-stu-id="cbc16-157">If endpoints are explicitly provided, the default endpoints can still be added by calling <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> on the <xref:System.ServiceModel.ServiceHost> before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span> <span data-ttu-id="cbc16-158">有关默认终结点的详细信息，请参阅[Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md)并[WCF 服务的简化配置](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="cbc16-158">For more information about default endpoints, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc16-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="cbc16-159">See also</span></span>

- [<span data-ttu-id="cbc16-160">实现服务协定</span><span class="sxs-lookup"><span data-stu-id="cbc16-160">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
