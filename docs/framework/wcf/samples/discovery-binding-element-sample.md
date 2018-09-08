---
title: 发现绑定元素示例
ms.date: 03/30/2017
ms.assetid: af513015-85bf-417b-8729-1bdff77ff6d6
ms.openlocfilehash: d906d9a389c50095f2af5d52e3874c3e43199e68
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44177531"
---
# <a name="discovery-binding-element-sample"></a><span data-ttu-id="a6227-102">发现绑定元素示例</span><span class="sxs-lookup"><span data-stu-id="a6227-102">Discovery Binding Element Sample</span></span>
<span data-ttu-id="a6227-103">本示例演示如何使用发现客户端绑定元素发现服务。</span><span class="sxs-lookup"><span data-stu-id="a6227-103">This sample demonstrates how to use the discovery client binding element to discover a service.</span></span> <span data-ttu-id="a6227-104">开发人员使用此功能可以向其现有客户端通道堆栈添加发现客户端通道，从而使编程模型非常直观。</span><span class="sxs-lookup"><span data-stu-id="a6227-104">This feature enables developers to add a discovery client channel to their existing client channel stack, making the programming model very intuitive.</span></span> <span data-ttu-id="a6227-105">当关联通道打开时，会使用发现解析服务地址。</span><span class="sxs-lookup"><span data-stu-id="a6227-105">When the associated channel is opened, the address of the service is resolved using discovery.</span></span> <span data-ttu-id="a6227-106">本示例包含以下项目：</span><span class="sxs-lookup"><span data-stu-id="a6227-106">This sample consists of the following projects:</span></span>  
  
-   <span data-ttu-id="a6227-107">**CalculatorService**： 可发现的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="a6227-107">**CalculatorService**: A discoverable WCF service.</span></span>  
  
-   <span data-ttu-id="a6227-108">**CalculatorClient**： 使用 discovery 客户端通道搜索并调用 CalculatorService 的 WCF 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="a6227-108">**CalculatorClient**: A WCF client application that uses the discovery client channel to search for and call the CalculatorService.</span></span>  
  
-   <span data-ttu-id="a6227-109">**DynamicCalculatorClient**： 使用动态终结点搜索并调用 CalculatorService 的 WCF 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="a6227-109">**DynamicCalculatorClient**: A WCF client application that uses a dynamic endpoint to search for and call the CalculatorService.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a6227-110">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="a6227-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a6227-111">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="a6227-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a6227-112">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="a6227-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a6227-113">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="a6227-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryBindingElement`  
  
## <a name="calculatorservice"></a><span data-ttu-id="a6227-114">CalculatorService</span><span class="sxs-lookup"><span data-stu-id="a6227-114">CalculatorService</span></span>  
 <span data-ttu-id="a6227-115">此项目包含一个实现 `ICalculatorService` 协定的简单计算器服务。</span><span class="sxs-lookup"><span data-stu-id="a6227-115">This project contains a simple calculator service that implements the `ICalculatorService` contract.</span></span>  
  
 <span data-ttu-id="a6227-116">下面的 App.config 文件用于在服务行为和发现终结点中添加 `<serviceDiscovery>` 行为。</span><span class="sxs-lookup"><span data-stu-id="a6227-116">The following App.config file is used to add a `<serviceDiscovery>` behavior in the service behaviors as well as the discovery endpoint.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service behaviorConfiguration="CalculatorBehavior" name="Microsoft.Samples.Discovery.CalculatorService">  
        <endpoint name="udpDiscoveryEpt" kind="udpDiscoveryEndpoint" />  
      </service>  
    </services>  
    <behaviors>  
      <!--Enable discovery through configuration.-->  
      <serviceBehaviors>  
        <behavior name="CalculatorBehavior">  
          <serviceDiscovery>  
          </serviceDiscovery>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="a6227-117">这使得服务及其终结点可发现。</span><span class="sxs-lookup"><span data-stu-id="a6227-117">This makes the service and its endpoints discoverable.</span></span> <span data-ttu-id="a6227-118">CalculatorService 是使用 NetTcpBinding 绑定添加一个终结点的自承载服务。</span><span class="sxs-lookup"><span data-stu-id="a6227-118">The CalculatorService is a self-hosted service that adds one endpoint using the NetTcpBinding binding.</span></span> <span data-ttu-id="a6227-119">它还向终结点添加 `EndpointDiscoveryBehavior` 并指定范围，如下面的节点中所示。</span><span class="sxs-lookup"><span data-stu-id="a6227-119">It also adds an `EndpointDiscoveryBehavior` to the endpoint and specifies a scope as shown in the following code.</span></span>  
  
```  
// Add a NET.TCP endpoint and add a scope to that endpoint.  
ServiceEndpoint netTcpEndpoint = serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new NetTcpBinding(), netTcpAddress);  
EndpointDiscoveryBehavior netTctEndpointBehavior = new EndpointDiscoveryBehavior();  
netTctEndpointBehavior.Scopes.Add(new Uri("ldap:///ou=engineering,o=exampleorg,c=us"));  
netTcpEndpoint.Behaviors.Add(netTctEndpointBehavior);  
serviceHost.Open();  
```  
  
## <a name="calculatorclient"></a><span data-ttu-id="a6227-120">CalculatorClient</span><span class="sxs-lookup"><span data-stu-id="a6227-120">CalculatorClient</span></span>  
 <span data-ttu-id="a6227-121">此项目包含一个向 CalculatorService 发送消息的客户端实现。</span><span class="sxs-lookup"><span data-stu-id="a6227-121">This project contains a client implementation that sends messages to the CalculatorService.</span></span> <span data-ttu-id="a6227-122">此程序使用 `CreateCustomBindingWithDiscoveryElement()` 方法创建一个使用 Discovery 客户端通道的自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="a6227-122">This program uses the `CreateCustomBindingWithDiscoveryElement()` method to create a custom binding that uses the Discovery Client Channel.</span></span>  
  
```  
static CustomBinding CreateCustomBindingWithDiscoveryElement()  
 {  
      DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
            // Provide the search criteria and the endpoint over which the probe is sent  
            discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
            discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
            CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
            // Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
            // An exception is thrown if this binding element is not at the top  
            customBinding.Elements.Insert(0, discoveryBindingElement);  
  
            return customBinding; }  
```  
  
 <span data-ttu-id="a6227-123"><xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> 实例化后，开发人员指定搜索服务时要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="a6227-123">After the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> is instantiated, the developer specifies the criteria to use when searching for a service.</span></span> <span data-ttu-id="a6227-124">在本例中，发现查找条件是 `ICalculatorService` 类型。</span><span class="sxs-lookup"><span data-stu-id="a6227-124">In this case, the discovery find criterion is the `ICalculatorService` type.</span></span> <span data-ttu-id="a6227-125">此外，开发人员还指定一个 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>，它返回指定要在何处查找服务的 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>。</span><span class="sxs-lookup"><span data-stu-id="a6227-125">Additionally, the developer specifies a <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> which returns a <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> that specifies where to look for the services.</span></span> <span data-ttu-id="a6227-126"><xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> 返回新的 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> 实例。</span><span class="sxs-lookup"><span data-stu-id="a6227-126">The <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> returns a new <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instance.</span></span> <span data-ttu-id="a6227-127">有关详细信息，请参阅[Discovery 客户端通道使用一个自定义绑定](../../../../docs/framework/wcf/feature-details/using-a-custom-binding-with-the-discovery-client-channel.md)。</span><span class="sxs-lookup"><span data-stu-id="a6227-127">For more information, see [Using a Custom Binding with the Discovery Client Channel](../../../../docs/framework/wcf/feature-details/using-a-custom-binding-with-the-discovery-client-channel.md).</span></span>  
  
```  
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
    // to the DiscoveryClientBindingElement. The Discovery ClientChannel   
    // uses this endpoint to send Probe message.  
    public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
    {  
        public override DiscoveryEndpoint GetDiscoveryEndpoint()  
        {  
            return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
        }  
    }  
```  
  
 <span data-ttu-id="a6227-128">在本例中，客户端使用 Discovery 协议定义的 UDP 多播机制在本地子网上搜索服务。</span><span class="sxs-lookup"><span data-stu-id="a6227-128">In this case, the client uses the UDP multicast mechanism defined by the Discovery protocol to search for services on the local subnet.</span></span> <span data-ttu-id="a6227-129">方法的其余部分创建自定义绑定并将 Discovery 绑定元素插入堆栈顶部。</span><span class="sxs-lookup"><span data-stu-id="a6227-129">The remainder of the method creates a custom binding and inserts the Discovery binding element at the top of the stack.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6227-130"><xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> 必须放置在绑定堆栈顶部。</span><span class="sxs-lookup"><span data-stu-id="a6227-130">The <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> must be placed on the top of the binding stack.</span></span> <span data-ttu-id="a6227-131"><xref:System.ServiceModel.Channels.BindingElement> 之上的任何 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> 都必须确保其创建的通道工厂或通道不使用 `EndpointAddress` 或 `Via` 属性，因为实际地址只能在 Discovery 客户端通道上发现。</span><span class="sxs-lookup"><span data-stu-id="a6227-131">Any <xref:System.ServiceModel.Channels.BindingElement> on top of <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> must make sure that the channel factory or channel it creates does not use the `EndpointAddress` or `Via` properties, because the actual address is found only at the Discovery client channel.</span></span>  
  
 <span data-ttu-id="a6227-132">接下来，可以通过传入此自定义绑定和终结点地址来实例化 `CalculatorClient`。</span><span class="sxs-lookup"><span data-stu-id="a6227-132">Next, the `CalculatorClient` can be instantiated by passing in this custom binding as well as an endpoint address.</span></span>  
  
```  
CalculatorServiceClient client = new CalculatorServiceClient(CreateCustomBindingWithDiscoveryElement(), DiscoveryClientBindingElement.DiscoveryEndpointAddress);  
```  
  
 <span data-ttu-id="a6227-133">在使用发现客户端通道时，将传入先前指定的恒定终结点地址。</span><span class="sxs-lookup"><span data-stu-id="a6227-133">When using the Discovery Client Channel, the constant endpoint address specified previously is passed in.</span></span> <span data-ttu-id="a6227-134">现在，在运行时，发现客户端通道查找通过查找条件指定的服务，并与其连接。</span><span class="sxs-lookup"><span data-stu-id="a6227-134">Now at runtime, the Discovery Client Channel finds the service specified by the find criteria and connects to it.</span></span> <span data-ttu-id="a6227-135">若要使服务和客户端建立连接，它们必须具有相同的基础绑定堆栈。</span><span class="sxs-lookup"><span data-stu-id="a6227-135">For the service and the client to establish a connection, they must also have the same underlying binding stack.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="a6227-136">使用此示例</span><span class="sxs-lookup"><span data-stu-id="a6227-136">To use this sample</span></span>  
  
1.  <span data-ttu-id="a6227-137">在 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 中打开解决方案。</span><span class="sxs-lookup"><span data-stu-id="a6227-137">Open the solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="a6227-138">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="a6227-138">Build the solution.</span></span>  
  
3.  <span data-ttu-id="a6227-139">运行服务应用程序和每个客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="a6227-139">Run the service application and each of the client applications.</span></span>  
  
4.  <span data-ttu-id="a6227-140">观察客户端是否能够在不知道服务地址的情况下找到服务。</span><span class="sxs-lookup"><span data-stu-id="a6227-140">Observe that the client was able to find the service without knowing its address.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6227-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6227-141">See Also</span></span>
