---
title: 客户端配置
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: 2e178f8b08fbadbb5549fa10631d3a57f71a7e0d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503217"
---
# <a name="client-configuration"></a><span data-ttu-id="14577-102">客户端配置</span><span class="sxs-lookup"><span data-stu-id="14577-102">Client Configuration</span></span>
<span data-ttu-id="14577-103">Windows Communication Foundation (WCF) 客户端配置可用于指定地址、 绑定、 行为和协定，客户端终结点，哪些客户端用于连接到服务终结点的"ABC"属性。</span><span class="sxs-lookup"><span data-stu-id="14577-103">You can use the Windows Communication Foundation (WCF) client configuration to specify the address, binding, behavior, and contract, the "ABC" properties of the client endpoint, which clients use to connect to service endpoints.</span></span> <span data-ttu-id="14577-104">[\<客户端 >](../../../../docs/framework/configure-apps/file-schema/wcf/client.md)元素具有[\<终结点 >](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017)元素，其属性用于配置终结点的 abc 属性。</span><span class="sxs-lookup"><span data-stu-id="14577-104">The [\<client>](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) element has an [\<endpoint>](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element whose attributes are used to configure the endpoint ABCs.</span></span> <span data-ttu-id="14577-105">这些属性将在本主题的“配置终结点”一节中讨论。</span><span class="sxs-lookup"><span data-stu-id="14577-105">These attributes are discussed in the "Configuring Endpoints" section of this topic.</span></span>  
  
 <span data-ttu-id="14577-106">[\<终结点 >](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017)元素还包含[\<元数据 >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)元素用于指定导入和导出元数据，用于设置[ \<标头 >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)包含一个自定义地址标头集合的元素和一个[\<标识 >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)启用的其他终结点的终结点的身份验证的元素交换与它的消息。</span><span class="sxs-lookup"><span data-stu-id="14577-106">The [\<endpoint>](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element also contains a [\<metadata>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) element that is used to specify settings for importing and exporting metadata , a [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) element that contains a collection of custom address headers, and an [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) element that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span> <span data-ttu-id="14577-107">[\<标头 >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)并[\<标识 >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)元素属于<xref:System.ServiceModel.EndpointAddress>进行的讨论会在[地址](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)主题。</span><span class="sxs-lookup"><span data-stu-id="14577-107">The [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are discussed in the [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) topic.</span></span> <span data-ttu-id="14577-108">本主题的“配置元数据”子节中提供了一些主题链接，这些主题对元数据扩展的使用进行说明。</span><span class="sxs-lookup"><span data-stu-id="14577-108">Links to topics that explain the use of metadata extensions are provided in the Configuring Metadata sub-section of this topic.</span></span>  
  
## <a name="configuring-endpoints"></a><span data-ttu-id="14577-109">配置终结点</span><span class="sxs-lookup"><span data-stu-id="14577-109">Configuring Endpoints</span></span>  
 <span data-ttu-id="14577-110">设计客户端配置为允许客户端可以指定一个或多个终结点，每个都有其自己的名称、 地址和协定，并且每个引用[\<绑定 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)并[ \<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)要用来配置该终结点的客户端配置中的元素。</span><span class="sxs-lookup"><span data-stu-id="14577-110">The client configuration is designed to allow the client to specify one or more endpoints, each with its own name, address, and contract, with each referencing the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) and [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elements in the client configuration to be used to configure that endpoint.</span></span> <span data-ttu-id="14577-111">客户端配置文件应命名为"App.config"因为这是 WCF 运行时需要的名称。</span><span class="sxs-lookup"><span data-stu-id="14577-111">The client configuration file should be named "App.config" because this is the name that the WCF runtime expects.</span></span> <span data-ttu-id="14577-112">下面的示例演示一个客户端配置文件。</span><span class="sxs-lookup"><span data-stu-id="14577-112">The following example shows a client configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
        <client>  
          <endpoint  
            name="endpoint1"  
            address="http://localhost/ServiceModelSamples/service.svc"  
            binding="wsHttpBinding"  
            bindingConfiguration="WSHttpBinding_IHello"  
            behaviorConfiguration="IHello_Behavior"  
            contract="IHello" >  
  
            <metadata>  
              <wsdlImporters>  
                <extension  
                  type="Microsoft.ServiceModel.Samples.WsdlDocumentationImporter, WsdlDocumentation"/>  
              </wsdlImporters>  
            </metadata>  
  
            <identity>  
              <servicePrincipalName value="host/localhost" />  
            </identity>  
          </endpoint>  
// Add another endpoint by adding another <endpoint> element.  
          <endpoint  
            name="endpoint2">  
           //Configure another endpoint here.  
          </endpoint>  
        </client>  
  
//The bindings section references by the bindingConfiguration endpoint attribute.  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_IHello"   
                 bypassProxyOnLocal="false"   
                 hostNameComparisonMode="StrongWildcard">  
          <readerQuotas maxDepth="32"/>  
          <reliableSession ordered="true"   
                           enabled="false" />  
          <security mode="Message">  
           //Security settings go here.  
          </security>  
        </binding>  
        <binding name="Another Binding"  
        //Configure this binding here.  
        </binding>  
          </wsHttpBinding>  
        </bindings>  
  
//The behavior section references by the behaviorConfiguration endpoint attribute.  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name=" IHello_Behavior ">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="14577-113">可选的 `name` 属性唯一地标识了给定协定的终结点。</span><span class="sxs-lookup"><span data-stu-id="14577-113">The optional `name` attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="14577-114">它由 <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> 或 <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> 用于指定客户端配置中的哪个终结点是目标终结点，必须在创建到服务的通道时加载。</span><span class="sxs-lookup"><span data-stu-id="14577-114">It is used by the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> or by the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> to specify which endpoint in the client configuration is being targeted and must be loaded when a channel is created to service.</span></span> <span data-ttu-id="14577-115">通配符终结点配置名称“\*”可用，并且指示 <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> 方法，如果文件中正好有一个终结点配置，就应加载该终结点配置，否则引发异常。</span><span class="sxs-lookup"><span data-stu-id="14577-115">A wildcard endpoint configuration name "\*" is available and indicates to the <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> method that it should load any endpoint configuration in the file, provided there is precisely one available, and otherwise throws an exception.</span></span> <span data-ttu-id="14577-116">如果省略此属性，则将对应的终结点用作与指定协定类型相关联的默认终结点。</span><span class="sxs-lookup"><span data-stu-id="14577-116">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified contract type.</span></span> <span data-ttu-id="14577-117">`name` 属性的默认值是一个空字符串，它与任何其他名称一样进行匹配。</span><span class="sxs-lookup"><span data-stu-id="14577-117">The default value for the `name` attribute is an empty string which is matched like any other name.</span></span>  
  
 <span data-ttu-id="14577-118">每个终结点都必须具有一个与之关联的地址，用于查找和标识终结点。</span><span class="sxs-lookup"><span data-stu-id="14577-118">Every endpoint must have an address associated with it to locate and identify the endpoint.</span></span> <span data-ttu-id="14577-119">`address` 属性可用来指定提供终结点位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="14577-119">The `address` attribute can be used to specify the URL that provides the location of the endpoint.</span></span> <span data-ttu-id="14577-120">但是，通过创建统一资源标识符 (URI)，也可以在代码中指定服务终结点的地址，使用 <xref:System.ServiceModel.ServiceHost> 方法之一可以将该地址添加到 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>。</span><span class="sxs-lookup"><span data-stu-id="14577-120">But the address for a service endpoint can also be specified in code by creating a Uniform Resource Identifier (URI) and is added to the <xref:System.ServiceModel.ServiceHost> using one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods.</span></span> <span data-ttu-id="14577-121">有关详细信息，请参阅[地址](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)。</span><span class="sxs-lookup"><span data-stu-id="14577-121">For more information, see [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).</span></span> <span data-ttu-id="14577-122">正如简介， [\<标头 >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)并[\<标识 >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)元素属于<xref:System.ServiceModel.EndpointAddress>和中还讨论了[地址](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)主题。</span><span class="sxs-lookup"><span data-stu-id="14577-122">As the introduction indicates, the [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are also discussed in the [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) topic.</span></span>  
  
 <span data-ttu-id="14577-123">`binding` 属性指示终结点在连接到服务时期望使用的绑定类型。</span><span class="sxs-lookup"><span data-stu-id="14577-123">The `binding` attribute indicates the type of binding the endpoint expects to use when connecting to a service.</span></span> <span data-ttu-id="14577-124">该类型必须具有一个已注册的配置节，才能加以引用。</span><span class="sxs-lookup"><span data-stu-id="14577-124">The type must have a registered configuration section if it is to be referenced.</span></span> <span data-ttu-id="14577-125">在上一示例中，这是[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)部分中，它指示终结点使用<xref:System.ServiceModel.WSHttpBinding>。</span><span class="sxs-lookup"><span data-stu-id="14577-125">In the previous example, this is the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) section, which indicates that the endpoint uses a <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="14577-126">实际上，终结点可以使用某个给定类型的多个绑定。</span><span class="sxs-lookup"><span data-stu-id="14577-126">But there may be more than one binding of a given type that the endpoint can use.</span></span> <span data-ttu-id="14577-127">每个具有其自己[\<绑定 >](../../../../docs/framework/misc/binding.md) (binding) 类型元素中的元素。</span><span class="sxs-lookup"><span data-stu-id="14577-127">Each of these has its own [\<binding>](../../../../docs/framework/misc/binding.md) element within the (binding) type element.</span></span> <span data-ttu-id="14577-128">`bindingconfiguration` 属性用于区分相同类型的绑定。</span><span class="sxs-lookup"><span data-stu-id="14577-128">The `bindingconfiguration` attribute is used to distinguish between bindings of the same type.</span></span> <span data-ttu-id="14577-129">其值符合`name`的属性[\<绑定 >](../../../../docs/framework/misc/binding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="14577-129">Its value is matched with the `name` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) element.</span></span> <span data-ttu-id="14577-130">有关如何配置客户端绑定使用的配置，请参阅[如何：在配置中指定客户端绑定](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="14577-130">For more information about how to configure a client binding using configuration, see [How to: Specify a Client Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).</span></span>  
  
 <span data-ttu-id="14577-131">`behaviorConfiguration`属性用于指定哪些[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)的[ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)终结点应使用。</span><span class="sxs-lookup"><span data-stu-id="14577-131">The `behaviorConfiguration` attribute is used to specify which [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) of the [\<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) the endpoint should use.</span></span> <span data-ttu-id="14577-132">其值符合`name`的属性[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)元素。</span><span class="sxs-lookup"><span data-stu-id="14577-132">Its value is matched with the `name` attribute of the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element.</span></span> <span data-ttu-id="14577-133">有关使用配置来指定客户端行为的示例，请参阅[配置客户端行为](../../../../docs/framework/wcf/configuring-client-behaviors.md)。</span><span class="sxs-lookup"><span data-stu-id="14577-133">For an example of using configuration to specify client behaviors, see [Configuring Client Behaviors](../../../../docs/framework/wcf/configuring-client-behaviors.md).</span></span>  
  
 <span data-ttu-id="14577-134">`contract` 属性指定终结点公开哪个协定。</span><span class="sxs-lookup"><span data-stu-id="14577-134">The `contract` attribute specifies which contract the endpoint is exposing.</span></span> <span data-ttu-id="14577-135">此值对应于 <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> 的 <xref:System.ServiceModel.ServiceContractAttribute>。</span><span class="sxs-lookup"><span data-stu-id="14577-135">This value maps to the <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> of the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="14577-136">默认值为实现相应服务的类的完整类型名。</span><span class="sxs-lookup"><span data-stu-id="14577-136">The default value is the full type name of the class that implements the service.</span></span>  
  
### <a name="configuring-metadata"></a><span data-ttu-id="14577-137">配置元数据</span><span class="sxs-lookup"><span data-stu-id="14577-137">Configuring Metadata</span></span>  
 <span data-ttu-id="14577-138">[\<元数据 >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)元素用于指定导入扩展的设置用于注册元数据。</span><span class="sxs-lookup"><span data-stu-id="14577-138">The [\<metadata>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) element is used to specify settings used to register metadata import extensions.</span></span> <span data-ttu-id="14577-139">有关扩展元数据系统的详细信息，请参阅[扩展元数据系统](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)。</span><span class="sxs-lookup"><span data-stu-id="14577-139">For more information about extending the metadata system, see [Extending the Metadata System](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14577-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="14577-140">See also</span></span>
- [<span data-ttu-id="14577-141">终结点：地址、 绑定和协定</span><span class="sxs-lookup"><span data-stu-id="14577-141">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="14577-142">配置客户端行为</span><span class="sxs-lookup"><span data-stu-id="14577-142">Configuring Client Behaviors</span></span>](../../../../docs/framework/wcf/configuring-client-behaviors.md)
