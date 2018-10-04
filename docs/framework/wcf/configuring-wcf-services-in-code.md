---
title: 在代码中配置 WCF 服务
ms.date: 03/30/2017
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
ms.openlocfilehash: abd75e514d698e73c2297a5dc2e511f89f0534b1
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48582432"
---
# <a name="configuring-wcf-services-in-code"></a><span data-ttu-id="0fedf-102">在代码中配置 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="0fedf-102">Configuring WCF Services in Code</span></span>
<span data-ttu-id="0fedf-103">Windows Communication Foundation (WCF) 允许开发人员使用代码或配置文件配置服务。</span><span class="sxs-lookup"><span data-stu-id="0fedf-103">Windows Communication Foundation (WCF) allows developers to configure services using configuration files or code.</span></span>  <span data-ttu-id="0fedf-104">当部署之后需要对服务进行配置时，配置文件十分有用。</span><span class="sxs-lookup"><span data-stu-id="0fedf-104">Configuration files are useful when a service needs to be configured after being deployed.</span></span> <span data-ttu-id="0fedf-105">在使用配置文件时，IT 专业人员只需要更新配置文件，无需重新编译。</span><span class="sxs-lookup"><span data-stu-id="0fedf-105">When using configuration files, an IT professional only needs to update the configuration file, no recompilation is required.</span></span> <span data-ttu-id="0fedf-106">不过，配置文件可能十分复杂，难以维护。</span><span class="sxs-lookup"><span data-stu-id="0fedf-106">Configuration files, however, can be complex and difficult to maintain.</span></span> <span data-ttu-id="0fedf-107">不支持对配置文件进行调试，并且将按名称来引用配置元素，这使得配置文件的创作易于出错且较为困难。</span><span class="sxs-lookup"><span data-stu-id="0fedf-107">There is no support for debugging configuration files and configuration elements are referenced by names which makes authoring configuration files error-prone and difficult.</span></span> <span data-ttu-id="0fedf-108">WCF 还允许您在代码中配置服务。</span><span class="sxs-lookup"><span data-stu-id="0fedf-108">WCF also allows you to configure services in code.</span></span> <span data-ttu-id="0fedf-109">在早期版本的代码中的 WCF （4.0 及更早版本） 配置服务很容易在自承载方案中，<xref:System.ServiceModel.ServiceHost>类允许您配置终结点和调用 ServiceHost.Open 之前的行为。</span><span class="sxs-lookup"><span data-stu-id="0fedf-109">In earlier versions of WCF (4.0 and earlier) configuring services in code was easy in self-hosted scenarios, the <xref:System.ServiceModel.ServiceHost> class allowed you to configure endpoints and behaviors prior to calling ServiceHost.Open.</span></span> <span data-ttu-id="0fedf-110">但是，在 Web 承载方案中，您不具备针对 <xref:System.ServiceModel.ServiceHost> 类的直接访问权限。</span><span class="sxs-lookup"><span data-stu-id="0fedf-110">In web hosted scenarios, however, you don’t have direct access to the <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="0fedf-111">若要配置 Web 承载的服务，您需要创建 `System.ServiceModel.ServiceHostFactory`，后者会创建 <xref:System.ServiceModel.Activation.ServiceHostFactory> 并执行任何所需的配置。</span><span class="sxs-lookup"><span data-stu-id="0fedf-111">To configure a web hosted service you were required to create a `System.ServiceModel.ServiceHostFactory` that created the <xref:System.ServiceModel.Activation.ServiceHostFactory> and performed any needed configuration.</span></span> <span data-ttu-id="0fedf-112">从.NET 4.5 开始，WCF 提供了更简单的方法同时配置两者自托管，web 托管代码中的服务。</span><span class="sxs-lookup"><span data-stu-id="0fedf-112">Starting with .NET 4.5, WCF provides an easier way to configure both self-hosted and web hosted services in code.</span></span>  
  
## <a name="the-configure-method"></a><span data-ttu-id="0fedf-113">Configure 方法</span><span class="sxs-lookup"><span data-stu-id="0fedf-113">The Configure method</span></span>  
 <span data-ttu-id="0fedf-114">只需在您的服务实现类中使用以下签名定义名为 `Configure` 的公共静态方法：</span><span class="sxs-lookup"><span data-stu-id="0fedf-114">Simply define a public static method called `Configure` with the following signature in your service implementation class:</span></span>  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 <span data-ttu-id="0fedf-115">Configure 方法采用 <xref:System.ServiceModel.ServiceConfiguration> 实例，使开发者可以添加终结点和行为。</span><span class="sxs-lookup"><span data-stu-id="0fedf-115">The Configure method takes a <xref:System.ServiceModel.ServiceConfiguration> instance that enables the developer to add endpoints and behaviors.</span></span> <span data-ttu-id="0fedf-116">打开服务主机之前，将由 WCF 调用此方法。</span><span class="sxs-lookup"><span data-stu-id="0fedf-116">This method is called by WCF before the service host is opened.</span></span> <span data-ttu-id="0fedf-117">定义后，将忽略 app.config 或 web.config 文件中指定的任何服务配置设置。</span><span class="sxs-lookup"><span data-stu-id="0fedf-117">When defined, any service configuration settings specified in an app.config or web.config file will be ignored.</span></span>  
  
 <span data-ttu-id="0fedf-118">下面的代码段阐释如何定义 `Configure` 方法和添加服务终结点、终结点行为以及服务行为：</span><span class="sxs-lookup"><span data-stu-id="0fedf-118">The following code snippet illustrates how to define the `Configure` method and add a service endpoint, an endpoint behavior and service behaviors:</span></span>  
  
```csharp  
public class Service1 : IService1  
    {  
        public static void Configure(ServiceConfiguration config)  
        {  
            ServiceEndpoint se = new ServiceEndpoint(new ContractDescription("IService1"), new BasicHttpBinding(), new EndpointAddress("basic"));  
            se.Behaviors.Add(new MyEndpointBehavior());  
            config.AddServiceEndpoint(se);  
  
            config.Description.Behaviors.Add(new ServiceMetadataBehavior { HttpGetEnabled = true });  
            config.Description.Behaviors.Add(new ServiceDebugBehavior { IncludeExceptionDetailInFaults = true });  
        }  
  
        public string GetData(int value)  
        {  
            return string.Format("You entered: {0}", value);  
        }  
  
        public CompositeType GetDataUsingDataContract(CompositeType composite)  
        {  
            if (composite == null)  
            {  
                throw new ArgumentNullException("composite");  
            }  
            if (composite.BoolValue)  
            {  
                composite.StringValue += "Suffix";  
            }  
            return composite;  
        }  
    }  
```  
  
 <span data-ttu-id="0fedf-119">要为服务启用协议（如 https），可以显式添加使用协议的终结点，也可以通过调用 ServiceConfiguration.EnableProtocol(Binding) 自动添加终结点，这样可为与协议兼容的每个基址和定义的每个服务协定添加终结点。</span><span class="sxs-lookup"><span data-stu-id="0fedf-119">To enable a protocol such as https for a service, you can either explicitly add an endpoint that uses the protocol or you can automatically add endpoints by calling ServiceConfiguration.EnableProtocol(Binding) which adds an endpoint for each base address compatible with the protocol and each service contract defined.</span></span> <span data-ttu-id="0fedf-120">下面的代码演示如何使用 ServiceConfiguration.EnableProtocol 方法：</span><span class="sxs-lookup"><span data-stu-id="0fedf-120">The following code illustrates how to use the ServiceConfiguration.EnableProtocol method:</span></span>  
  
```csharp  
public class Service1 : IService1   
{   
    public string GetData(int value);   
    public static void Configure(ServiceConfiguration config)   
    {   
        // Enable "Add Service Reference" support   
       config.Description.Behaviors.Add( new ServiceMetadataBehavior { HttpGetEnabled = true });   
       // set up support for http, https, net.tcp, net.pipe   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new NetTcpBinding());   
       config.EnableProtocol(new NetNamedPipeBinding());   
       // add an extra BasicHttpBinding endpoint at http:///basic   
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");   
    }   
}   
```  
  
 <span data-ttu-id="0fedf-121">中的设置 <`protocolMappings`> 部分才使用任何应用程序终结点添加到<xref:System.ServiceModel.ServiceConfiguration>以编程方式。您可以根据需要加载服务配置从默认应用程序配置文件通过调用<xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A>然后更改设置。</span><span class="sxs-lookup"><span data-stu-id="0fedf-121">The settings in the <`protocolMappings`> section are only used if no application endpoints are added to the <xref:System.ServiceModel.ServiceConfiguration> programmatically.You can optionally load the service configuration from the default application configuration file by calling <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> and then change the settings.</span></span> <span data-ttu-id="0fedf-122"><xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> 类还允许您从集中式配置加载配置。</span><span class="sxs-lookup"><span data-stu-id="0fedf-122">The <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> class also allows you to load configuration from a centralized configuration.</span></span> <span data-ttu-id="0fedf-123">下面的代码演示如何实现这一点：</span><span class="sxs-lookup"><span data-stu-id="0fedf-123">The following code illustrates how to implement this:</span></span>  
  
```  
public class Service1 : IService1   
{   
    public void DoWork();   
    public static void Configure(ServiceConfiguration config)   
    {   
          config.LoadFromConfiguration(ConfigurationManager.OpenMappedExeConfiguration(new ExeConfigurationFileMap { ExeConfigFilename = @"c:\sharedConfig\MyConfig.config" }, ConfigurationUserLevel.None));   
    }   
}  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="0fedf-124">请注意，<xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A>忽略 <`host`> 中的设置 <`service`> 标记 <`system.serviceModel`>。</span><span class="sxs-lookup"><span data-stu-id="0fedf-124">Note that <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> ignores <`host`> settings within the <`service`> tag of <`system.serviceModel`>.</span></span> <span data-ttu-id="0fedf-125">从概念上讲，<`host`> 是有关主机配置、 不服务配置，以及它在 Configure 方法执行之前进行加载。</span><span class="sxs-lookup"><span data-stu-id="0fedf-125">Conceptually, <`host`> is about host configuration, not service configuration, and it gets loaded before the Configure method executes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fedf-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fedf-126">See Also</span></span>  
 [<span data-ttu-id="0fedf-127">使用配置文件配置服务</span><span class="sxs-lookup"><span data-stu-id="0fedf-127">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 [<span data-ttu-id="0fedf-128">配置客户端行为</span><span class="sxs-lookup"><span data-stu-id="0fedf-128">Configuring Client Behaviors</span></span>](../../../docs/framework/wcf/configuring-client-behaviors.md)  
 [<span data-ttu-id="0fedf-129">简化配置</span><span class="sxs-lookup"><span data-stu-id="0fedf-129">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 [<span data-ttu-id="0fedf-130">配置</span><span class="sxs-lookup"><span data-stu-id="0fedf-130">Configuration</span></span>](../../../docs/framework/wcf/samples/configuration-sample.md)  
 [<span data-ttu-id="0fedf-131">IIS 和 WAS 中的基于配置的激活</span><span class="sxs-lookup"><span data-stu-id="0fedf-131">Configuration-Based Activation in IIS and WAS</span></span>](../../../docs/framework/wcf/feature-details/configuration-based-activation-in-iis-and-was.md)  
 [<span data-ttu-id="0fedf-132">配置和元数据支持</span><span class="sxs-lookup"><span data-stu-id="0fedf-132">Configuration and Metadata Support</span></span>](../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)  
 [<span data-ttu-id="0fedf-133">配置</span><span class="sxs-lookup"><span data-stu-id="0fedf-133">Configuration</span></span>](../../../docs/framework/wcf/diagnostics/exceptions-reference/configuration.md)  
 [<span data-ttu-id="0fedf-134">如何：在配置中指定服务绑定</span><span class="sxs-lookup"><span data-stu-id="0fedf-134">How to: Specify a Service Binding in Configuration</span></span>](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [<span data-ttu-id="0fedf-135">如何：在配置中创建服务终结点</span><span class="sxs-lookup"><span data-stu-id="0fedf-135">How to: Create a Service Endpoint in Configuration</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 [<span data-ttu-id="0fedf-136">如何：使用配置文件发布服务的元数据</span><span class="sxs-lookup"><span data-stu-id="0fedf-136">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="0fedf-137">如何：在配置中指定客户端绑定</span><span class="sxs-lookup"><span data-stu-id="0fedf-137">How to: Specify a Client Binding in Configuration</span></span>](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)
