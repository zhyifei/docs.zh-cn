---
title: 简化配置
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: 13cf8bd46ef3aabb011cb2ddd207963235468662
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184049"
---
# <a name="simplified-configuration"></a><span data-ttu-id="0343d-102">简化配置</span><span class="sxs-lookup"><span data-stu-id="0343d-102">Simplified Configuration</span></span>
<span data-ttu-id="0343d-103">配置 Windows Communication Foundation (WCF) 服务可能相当复杂的任务。</span><span class="sxs-lookup"><span data-stu-id="0343d-103">Configuring Windows Communication Foundation (WCF) services can be a complex task.</span></span> <span data-ttu-id="0343d-104">该任务涉及多个不同选项，并且有时会很难确定需要哪些设置。</span><span class="sxs-lookup"><span data-stu-id="0343d-104">There are many different options and it is not always easy to determine what settings are required.</span></span> <span data-ttu-id="0343d-105">虽然配置文件提高灵活性的 WCF 服务，它们也是带来了许多难以发现的问题。</span><span class="sxs-lookup"><span data-stu-id="0343d-105">While configuration files increase the flexibility of WCF services, they also are the source for many hard to find problems.</span></span> [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="0343d-106">解决了这些问题，并向用户提供了一种减小服务配置大小和降低复杂性的方法。</span><span class="sxs-lookup"><span data-stu-id="0343d-106">addresses these problems and provides a way to reduce the size and complexity of service configuration.</span></span>  
  
## <a name="simplified-configuration"></a><span data-ttu-id="0343d-107">简化配置</span><span class="sxs-lookup"><span data-stu-id="0343d-107">Simplified Configuration</span></span>  
 <span data-ttu-id="0343d-108">在 WCF 服务配置文件，<`system.serviceModel`> 部分包含 <`service`> 托管每个服务的元素。</span><span class="sxs-lookup"><span data-stu-id="0343d-108">In WCF service configuration files, the <`system.serviceModel`> section contains a <`service`> element for each service hosted.</span></span> <span data-ttu-id="0343d-109"><`service`> 元素包含一系列 <`endpoint`> 指定的每个服务和一组服务行为 （可选） 公开的终结点元素。</span><span class="sxs-lookup"><span data-stu-id="0343d-109">The <`service`> element contains a collection of <`endpoint`> elements that specify the endpoints exposed for each service and optionally a set of service behaviors.</span></span> <span data-ttu-id="0343d-110"><`endpoint`> 元素指定地址、 绑定和协定公开终结点，也可以选择绑定配置和终结点行为。</span><span class="sxs-lookup"><span data-stu-id="0343d-110">The <`endpoint`> elements specify the address, binding, and contract exposed by the endpoint, and optionally binding configuration and endpoint behaviors.</span></span> <span data-ttu-id="0343d-111"><`system.serviceModel`> 部分还包含 <`behaviors`> 元素，它允许您指定服务或终结点行为。</span><span class="sxs-lookup"><span data-stu-id="0343d-111">The <`system.serviceModel`> section also contains a <`behaviors`> element that allows you to specify service or endpoint behaviors.</span></span> <span data-ttu-id="0343d-112">下面的示例演示 <`system.serviceModel`> 配置文件的部分。</span><span class="sxs-lookup"><span data-stu-id="0343d-112">The following example shows the <`system.serviceModel`> section of a configuration file.</span></span>  
  
```  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true">  
        <serviceDebug includeExceptionDetailInFaults="false">  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <bindings>  
   <basicHttpBinding>  
      <binding name=MyBindingConfig"  
               maxBufferSize="100"  
               maxReceiveBufferSize="100" />  
   </basicHttpBinding>  
   </bindings>   <services>  
    <service behaviorConfiguration="MyServiceBehavior"  
             name="MyService">  
      <endpoint address=""  
                binding="basicHttpBinding"  
                contract="ICalculator"  
                bindingConfiguration="MyBindingConfig" />  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange"/>  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] <span data-ttu-id="0343d-113">可以通过删除的要求来配置 WCF 服务更加容易 <`service`> 元素。</span><span class="sxs-lookup"><span data-stu-id="0343d-113">makes configuring a WCF service easier by removing the requirement for the <`service`> element.</span></span> <span data-ttu-id="0343d-114">如果未添加 <`service`> 部分，或添加任何终结点在 <`service`> 部分，并且你的服务未以编程方式定义任何终结点，则一组默认终结点会自动添加到你的服务，每个服务基址和服务实现的每个协定。</span><span class="sxs-lookup"><span data-stu-id="0343d-114">If you do not add a <`service`>  section or add any endpoints in a <`service`> section and your service does not programmatically define any endpoints, then a set of default endpoints are automatically added to your service, one for each service base address and for each contract implemented by your service.</span></span> <span data-ttu-id="0343d-115">在上述每个终结点中，终结点地址与基址相对应，绑定由基址方案确定，协定即为服务实现的协定。</span><span class="sxs-lookup"><span data-stu-id="0343d-115">In each of these endpoints, the endpoint address corresponds to the base address, the binding is determined by the base address scheme and the contract is the one implemented by your service.</span></span> <span data-ttu-id="0343d-116">如果你不需要指定任何终结点或服务行为，或者不需要更改任何绑定设置，则完全不必指定服务配置文件。</span><span class="sxs-lookup"><span data-stu-id="0343d-116">If you do not need to specify any endpoints or service behaviors or make any binding setting changes, you do not need to specify a service configuration file at all.</span></span> <span data-ttu-id="0343d-117">如果服务实现了两个协定，并且主机同时启用了 HTTP 和 TCP 传输，服务主机将创建四个默认终结点，使用每个传输的每一协定各对应一个终结点。</span><span class="sxs-lookup"><span data-stu-id="0343d-117">If a service implements two contracts and the host enables both HTTP and TCP transports the service host creates four default endpoints, one for each contract using each transport.</span></span> <span data-ttu-id="0343d-118">若要创建默认终结点，服务主机必须了解要使用的绑定。</span><span class="sxs-lookup"><span data-stu-id="0343d-118">To create default endpoints the service host must know what bindings to use.</span></span> <span data-ttu-id="0343d-119">这些设置指定在 <`protocolMappings`> 节中 <`system.serviceModel`> 部分。</span><span class="sxs-lookup"><span data-stu-id="0343d-119">These settings are specified in a <`protocolMappings`> section within the <`system.serviceModel`> section.</span></span> <span data-ttu-id="0343d-120"><`protocolMappings`> 部分包含映射到绑定类型的传输协议方案的列表。</span><span class="sxs-lookup"><span data-stu-id="0343d-120">The <`protocolMappings`> section contains a list of transport protocol schemes mapped to binding types.</span></span> <span data-ttu-id="0343d-121">服务主机使用传递到它的基址来确定要使用的绑定。</span><span class="sxs-lookup"><span data-stu-id="0343d-121">The service host uses the base addresses passed to it to determine which binding to use.</span></span> <span data-ttu-id="0343d-122">下面的示例使用 <`protocolMappings`> 元素。</span><span class="sxs-lookup"><span data-stu-id="0343d-122">The following example uses the <`protocolMappings`> element.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="0343d-123">更改默认配置元素（如绑定或行为）可能会影响在配置层次结构的较低级别中定义的服务，因为这些服务可能使用这些默认绑定和行为。</span><span class="sxs-lookup"><span data-stu-id="0343d-123">Changing default configuration elements, such as bindings or behaviors, might affect services defined in lower levels of the configuration hierarchy, since they might be using these default bindings and behaviors.</span></span> <span data-ttu-id="0343d-124">因而，更改默认绑定和行为的任何人员都需要注意，这些更改可能会影响层次结构中的其他服务。</span><span class="sxs-lookup"><span data-stu-id="0343d-124">Thus, whoever changes default bindings and behaviors needs to be aware that these changes might affect other services in the hierarchy.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0343d-125">承载于 Internet 信息服务 (IIS) 或 Windows 进程激活服务 (WAS) 下的服务使用虚拟目录作为其基址。</span><span class="sxs-lookup"><span data-stu-id="0343d-125">Services hosted under Internet Information Services (IIS) or Windows Process Activation Service (WAS) use the virtual directory as their base address.</span></span>  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 <span data-ttu-id="0343d-126">在上一示例中，基址以“http”方案开头的终结点使用 <xref:System.ServiceModel.BasicHttpBinding>。</span><span class="sxs-lookup"><span data-stu-id="0343d-126">In the previous example, an endpoint with a base address that starts with the "http" scheme uses the <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="0343d-127">基址以“net.tcp”方案开头的终结点使用 <xref:System.ServiceModel.NetTcpBinding>。</span><span class="sxs-lookup"><span data-stu-id="0343d-127">An endpoint with a base address that starts with the "net.tcp" scheme uses the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="0343d-128">你可以在本地 App.config 或 Web.config 文件中重写相应设置。</span><span class="sxs-lookup"><span data-stu-id="0343d-128">You can override settings in a local App.config or Web.config file.</span></span>  
  
 <span data-ttu-id="0343d-129">中的每个元素 <`protocolMappings`> 部分必须指定方案和绑定。</span><span class="sxs-lookup"><span data-stu-id="0343d-129">Each element within the <`protocolMappings`> section must specify a scheme and a binding.</span></span> <span data-ttu-id="0343d-130">或者可以指定`bindingConfiguration`绑定中指定配置的属性 <`bindings`> 配置文件的部分。</span><span class="sxs-lookup"><span data-stu-id="0343d-130">Optionally it can specify a `bindingConfiguration` attribute that specifies a binding configuration within the <`bindings`> section of the configuration file.</span></span> <span data-ttu-id="0343d-131">如果未指定 `bindingConfiguration`，则使用相应绑定类型的匿名绑定配置。</span><span class="sxs-lookup"><span data-stu-id="0343d-131">If no `bindingConfiguration` is specified, the anonymous binding configuration of the appropriate binding type is used.</span></span>  
  
 <span data-ttu-id="0343d-132">为默认终结点配置服务行为，应使用匿名 <`behavior`> 部分中 <`serviceBehaviors`> 部分。</span><span class="sxs-lookup"><span data-stu-id="0343d-132">Service behaviors are configured for the default endpoints by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span> <span data-ttu-id="0343d-133">任何未命名 <`behavior`> 中的元素 <`serviceBehaviors`> 用于配置服务行为。</span><span class="sxs-lookup"><span data-stu-id="0343d-133">Any unnamed <`behavior`> elements within <`serviceBehaviors`> are used to configure service behaviors.</span></span> <span data-ttu-id="0343d-134">例如，下面的配置文件对主机中的所有服务启用服务元数据发布。</span><span class="sxs-lookup"><span data-stu-id="0343d-134">For example, the following configuration file enables service metadata publishing for all services within the host.</span></span>  
  
```xml  
<system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>    <!-- No <service> tag is necessary. Default endpoints are added to the service -->  
    <!-- The service behavior with name="" is picked up by the service -->  
 </system.serviceModel>  
```  
  
 <span data-ttu-id="0343d-135">终结点行为配置通过使用匿名 <`behavior`> 部分中 <`serviceBehaviors`> 部分。</span><span class="sxs-lookup"><span data-stu-id="0343d-135">Endpoint behaviors are configured by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span>  
  
 <span data-ttu-id="0343d-136">下面示例中的配置文件使用简化配置模型，它等效于本主题开头的配置文件。</span><span class="sxs-lookup"><span data-stu-id="0343d-136">The following example is a configuration file equivalent to the one at the beginning of this topic that uses the simplified configuration model.</span></span>  
  
```xml  
<system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="true" />
          <serviceDebug includeExceptionDetailInFaults="false" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <bindings>
       <basicHttpBinding>
          <binding maxBufferSize="100"
                   maxReceiveBufferSize="100" />
       </basicHttpBinding>
    </bindings>
    <!-- No <service> tag is necessary. Default endpoints will be added to the service -->
    <!-- The service behavior with name="" will be picked up by the service -->
    <protocolMapping>
      <add scheme="http" binding="basicHttpBinding" />
  </protocolMapping>
  </system.serviceModel>
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="0343d-137">此功能只与 WCF 服务配置相关，与客户端配置无关。</span><span class="sxs-lookup"><span data-stu-id="0343d-137">This feature relates only to WCF service configuration, not client configuration.</span></span> <span data-ttu-id="0343d-138">大多数时候，使用 svcutil.exe 之类的工具或从 Visual Studio 添加服务引用将生成 WCF 客户端配置。</span><span class="sxs-lookup"><span data-stu-id="0343d-138">Most times, WCF client configuration will be generated by a tool such as svcutil.exe or adding a service reference from Visual Studio.</span></span> <span data-ttu-id="0343d-139">如果您在手动配置 WCF 客户端将需要添加\<客户端 > 配置元素，并指定你想要调用任何终结点。</span><span class="sxs-lookup"><span data-stu-id="0343d-139">If you are manually configuring a WCF client you will need to add a \<client> element to the configuration and specify any endpoints you wish to call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0343d-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="0343d-140">See also</span></span>

- [<span data-ttu-id="0343d-141">使用配置文件配置服务</span><span class="sxs-lookup"><span data-stu-id="0343d-141">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)
- [<span data-ttu-id="0343d-142">配置服务绑定</span><span class="sxs-lookup"><span data-stu-id="0343d-142">Configuring Bindings for Services</span></span>](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)
- [<span data-ttu-id="0343d-143">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="0343d-143">Configuring System-Provided Bindings</span></span>](../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0343d-144">配置服务</span><span class="sxs-lookup"><span data-stu-id="0343d-144">Configuring Services</span></span>](../../../docs/framework/wcf/configuring-services.md)
- [<span data-ttu-id="0343d-145">配置 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="0343d-145">Configuring WCF services</span></span>](configuring-services.md)
- [<span data-ttu-id="0343d-146">在代码中配置 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="0343d-146">Configuring WCF Services in Code</span></span>](../../../docs/framework/wcf/configuring-wcf-services-in-code.md)
