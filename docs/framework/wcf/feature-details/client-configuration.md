---
title: 客户端配置
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: 6a5cbf5d536af8649b0b8bb93600e94a48c507c1
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141768"
---
# <a name="client-configuration"></a><span data-ttu-id="06113-102">客户端配置</span><span class="sxs-lookup"><span data-stu-id="06113-102">Client Configuration</span></span>
<span data-ttu-id="06113-103">您可以使用 Windows Communication Foundation （WCF）客户端配置来指定客户端终结点的地址、绑定、行为和协定，客户端终结点的 "ABC" 属性用于连接到服务终结点。</span><span class="sxs-lookup"><span data-stu-id="06113-103">You can use the Windows Communication Foundation (WCF) client configuration to specify the address, binding, behavior, and contract, the "ABC" properties of the client endpoint, which clients use to connect to service endpoints.</span></span> <span data-ttu-id="06113-104">[\<客户端 >](../../configure-apps/file-schema/wcf/client.md)元素具有一个[\<终结点 >](../../configure-apps/file-schema/wcf/endpoint-of-client.md)元素，其属性用于配置终结点 abc。</span><span class="sxs-lookup"><span data-stu-id="06113-104">The [\<client>](../../configure-apps/file-schema/wcf/client.md) element has an [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element whose attributes are used to configure the endpoint ABCs.</span></span> <span data-ttu-id="06113-105">这些属性在[配置终结点](#configuring-endpoints)部分中进行了讨论。</span><span class="sxs-lookup"><span data-stu-id="06113-105">These attributes are discussed in the [Configuring Endpoints](#configuring-endpoints) section.</span></span>  
  
 <span data-ttu-id="06113-106">[\<终结点 >](../../configure-apps/file-schema/wcf/endpoint-of-client.md)元素还包含一个[\<元数据 >](../../configure-apps/file-schema/wcf/metadata.md)元素，该元素用于指定导入和导出元数据的设置、一个包含自定义地址标头集合的[\<标头 >](../../configure-apps/file-schema/wcf/headers.md)元素，以及一个[\<标识 >](../../configure-apps/file-schema/wcf/identity.md)元素，通过该元素，可通过与该终结点交换消息的其他终结点对该终结点进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="06113-106">The [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element also contains a [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) element that is used to specify settings for importing and exporting metadata, a [\<headers>](../../configure-apps/file-schema/wcf/headers.md) element that contains a collection of custom address headers, and an [\<identity>](../../configure-apps/file-schema/wcf/identity.md) element that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span> <span data-ttu-id="06113-107">[\<标头 >](../../configure-apps/file-schema/wcf/headers.md)和[\<标识 >](../../configure-apps/file-schema/wcf/identity.md)元素是 <xref:System.ServiceModel.EndpointAddress> 的一部分，并在 "[地址](../../wcf/feature-details/endpoint-addresses.md)" 一文中进行讨论。</span><span class="sxs-lookup"><span data-stu-id="06113-107">The [\<headers>](../../configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are discussed in the [Addresses](../../wcf/feature-details/endpoint-addresses.md) article.</span></span> <span data-ttu-id="06113-108">在[配置元数据](#configuring-metadata)部分中提供了指向说明元数据扩展使用的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="06113-108">Links to topics that explain the use of metadata extensions are provided in the [Configuring Metadata](#configuring-metadata) section.</span></span>  
  
## <a name="configuring-endpoints"></a><span data-ttu-id="06113-109">配置终结点</span><span class="sxs-lookup"><span data-stu-id="06113-109">Configuring Endpoints</span></span>  
 <span data-ttu-id="06113-110">客户端配置旨在允许客户端指定一个或多个终结点，每个终结点都有自己的名称、地址和协定，每个终结点都引用[\<绑定 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)并[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)要用于配置该终结点的客户端配置中的元素。</span><span class="sxs-lookup"><span data-stu-id="06113-110">The client configuration is designed to allow the client to specify one or more endpoints, each with its own name, address, and contract, with each referencing the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) and [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elements in the client configuration to be used to configure that endpoint.</span></span> <span data-ttu-id="06113-111">应将客户端配置文件命名为 "App.config"，因为这是 WCF 运行时需要的名称。</span><span class="sxs-lookup"><span data-stu-id="06113-111">The client configuration file should be named "App.config" because this is the name that the WCF runtime expects.</span></span> <span data-ttu-id="06113-112">下面的示例演示一个客户端配置文件。</span><span class="sxs-lookup"><span data-stu-id="06113-112">The following example shows a client configuration file.</span></span>  
  
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
  
 <span data-ttu-id="06113-113">可选的 `name` 属性唯一地标识了给定协定的终结点。</span><span class="sxs-lookup"><span data-stu-id="06113-113">The optional `name` attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="06113-114">它由 <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> 或 <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> 用于指定客户端配置中的哪个终结点是目标终结点，必须在创建到服务的通道时加载。</span><span class="sxs-lookup"><span data-stu-id="06113-114">It is used by the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> or by the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> to specify which endpoint in the client configuration is being targeted and must be loaded when a channel is created to service.</span></span> <span data-ttu-id="06113-115">通配符终结点配置名称 "\*" 可用，并向 <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> 方法指示它应将任何终结点配置加载到文件中（只要有精确可用），否则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="06113-115">A wildcard endpoint configuration name "\*" is available and indicates to the <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> method that it should load any endpoint configuration in the file, provided there is precisely one available, and otherwise throws an exception.</span></span> <span data-ttu-id="06113-116">如果省略此属性，则将对应的终结点用作与指定协定类型相关联的默认终结点。</span><span class="sxs-lookup"><span data-stu-id="06113-116">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified contract type.</span></span> <span data-ttu-id="06113-117">`name` 属性的默认值是一个空字符串，它与任何其他名称一样进行匹配。</span><span class="sxs-lookup"><span data-stu-id="06113-117">The default value for the `name` attribute is an empty string which is matched like any other name.</span></span>  
  
 <span data-ttu-id="06113-118">每个终结点都必须具有一个与之关联的地址，用于查找和标识终结点。</span><span class="sxs-lookup"><span data-stu-id="06113-118">Every endpoint must have an address associated with it to locate and identify the endpoint.</span></span> <span data-ttu-id="06113-119">`address` 属性可用来指定提供终结点位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="06113-119">The `address` attribute can be used to specify the URL that provides the location of the endpoint.</span></span> <span data-ttu-id="06113-120">但是，通过创建统一资源标识符 (URI)，也可以在代码中指定服务终结点的地址，使用 <xref:System.ServiceModel.ServiceHost> 方法之一可以将该地址添加到 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>。</span><span class="sxs-lookup"><span data-stu-id="06113-120">But the address for a service endpoint can also be specified in code by creating a Uniform Resource Identifier (URI) and is added to the <xref:System.ServiceModel.ServiceHost> using one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods.</span></span> <span data-ttu-id="06113-121">有关详细信息，请参阅[地址](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)。</span><span class="sxs-lookup"><span data-stu-id="06113-121">For more information, see [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).</span></span> <span data-ttu-id="06113-122">正如简介中所述， [\<标头 >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)和[\<标识 >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)元素都是 <xref:System.ServiceModel.EndpointAddress> 的一部分，并且还会在 "[地址](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)" 主题中讨论。</span><span class="sxs-lookup"><span data-stu-id="06113-122">As the introduction indicates, the [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are also discussed in the [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) topic.</span></span>  
  
 <span data-ttu-id="06113-123">`binding` 属性指示终结点在连接到服务时期望使用的绑定类型。</span><span class="sxs-lookup"><span data-stu-id="06113-123">The `binding` attribute indicates the type of binding the endpoint expects to use when connecting to a service.</span></span> <span data-ttu-id="06113-124">该类型必须具有一个已注册的配置节，才能加以引用。</span><span class="sxs-lookup"><span data-stu-id="06113-124">The type must have a registered configuration section if it is to be referenced.</span></span> <span data-ttu-id="06113-125">在前面的示例中，这是[\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)部分，指示终结点使用 <xref:System.ServiceModel.WSHttpBinding>。</span><span class="sxs-lookup"><span data-stu-id="06113-125">In the previous example, this is the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) section, which indicates that the endpoint uses a <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="06113-126">实际上，终结点可以使用某个给定类型的多个绑定。</span><span class="sxs-lookup"><span data-stu-id="06113-126">But there may be more than one binding of a given type that the endpoint can use.</span></span> <span data-ttu-id="06113-127">其中每个元素都有其自己的[\<绑定](../../configure-apps/file-schema/wcf/bindings.md)（绑定）类型元素中的 > 元素。</span><span class="sxs-lookup"><span data-stu-id="06113-127">Each of these has its own [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element within the (binding) type element.</span></span> <span data-ttu-id="06113-128">`bindingconfiguration` 属性用于区分相同类型的绑定。</span><span class="sxs-lookup"><span data-stu-id="06113-128">The `bindingconfiguration` attribute is used to distinguish between bindings of the same type.</span></span> <span data-ttu-id="06113-129">它的值与[\<绑定 >](../../configure-apps/file-schema/wcf/bindings.md)元素的 `name` 特性相匹配。</span><span class="sxs-lookup"><span data-stu-id="06113-129">Its value is matched with the `name` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span> <span data-ttu-id="06113-130">有关如何使用配置来配置客户端绑定的详细信息，请参阅[如何：在配置中指定客户端绑定](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="06113-130">For more information about how to configure a client binding using configuration, see [How to: Specify a Client Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).</span></span>  
  
 <span data-ttu-id="06113-131">`behaviorConfiguration` 特性用于指定终结点应使用的[\<> endpointBehaviors](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)的[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 。</span><span class="sxs-lookup"><span data-stu-id="06113-131">The `behaviorConfiguration` attribute is used to specify which [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) of the [\<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) the endpoint should use.</span></span> <span data-ttu-id="06113-132">它的值与 > 元素的[\<行为](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)的 `name` 特性相匹配。</span><span class="sxs-lookup"><span data-stu-id="06113-132">Its value is matched with the `name` attribute of the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element.</span></span> <span data-ttu-id="06113-133">有关使用配置来指定客户端行为的示例，请参阅[配置客户端行为](../../../../docs/framework/wcf/configuring-client-behaviors.md)。</span><span class="sxs-lookup"><span data-stu-id="06113-133">For an example of using configuration to specify client behaviors, see [Configuring Client Behaviors](../../../../docs/framework/wcf/configuring-client-behaviors.md).</span></span>  
  
 <span data-ttu-id="06113-134">`contract` 属性指定终结点公开哪个协定。</span><span class="sxs-lookup"><span data-stu-id="06113-134">The `contract` attribute specifies which contract the endpoint is exposing.</span></span> <span data-ttu-id="06113-135">此值对应于 <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> 的 <xref:System.ServiceModel.ServiceContractAttribute>。</span><span class="sxs-lookup"><span data-stu-id="06113-135">This value maps to the <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> of the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="06113-136">默认值为实现相应服务的类的完整类型名。</span><span class="sxs-lookup"><span data-stu-id="06113-136">The default value is the full type name of the class that implements the service.</span></span>  
  
### <a name="configuring-metadata"></a><span data-ttu-id="06113-137">配置元数据</span><span class="sxs-lookup"><span data-stu-id="06113-137">Configuring Metadata</span></span>  
 <span data-ttu-id="06113-138">[\<metadata >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)元素用于指定用于注册元数据导入扩展的设置。</span><span class="sxs-lookup"><span data-stu-id="06113-138">The [\<metadata>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) element is used to specify settings used to register metadata import extensions.</span></span> <span data-ttu-id="06113-139">有关扩展元数据系统的详细信息，请参阅[扩展元数据系统](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)。</span><span class="sxs-lookup"><span data-stu-id="06113-139">For more information about extending the metadata system, see [Extending the Metadata System](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06113-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="06113-140">See also</span></span>

- [<span data-ttu-id="06113-141">终结点：地址、绑定和协定</span><span class="sxs-lookup"><span data-stu-id="06113-141">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="06113-142">配置客户端行为</span><span class="sxs-lookup"><span data-stu-id="06113-142">Configuring Client Behaviors</span></span>](../../../../docs/framework/wcf/configuring-client-behaviors.md)
