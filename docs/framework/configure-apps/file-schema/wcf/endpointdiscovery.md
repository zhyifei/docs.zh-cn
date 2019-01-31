---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: effceee30abdaa1725b8c8718df22632961871e8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266411"
---
# <a name="endpointdiscovery"></a><span data-ttu-id="ba5fb-101">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="ba5fb-101">\<endpointDiscovery></span></span>
<span data-ttu-id="ba5fb-102">指定终结点的各种发现设置，例如终结点的可发现性、范围以及对终结点元数据的任何自定义扩展。</span><span class="sxs-lookup"><span data-stu-id="ba5fb-102">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="ba5fb-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ba5fb-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ba5fb-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ba5fb-104">\<behaviors></span></span>  
<span data-ttu-id="ba5fb-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="ba5fb-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="ba5fb-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ba5fb-106">\<behavior></span></span>  
<span data-ttu-id="ba5fb-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="ba5fb-107">\<endpointDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba5fb-108">语法</span><span class="sxs-lookup"><span data-stu-id="ba5fb-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba5fb-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ba5fb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ba5fb-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ba5fb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba5fb-111">特性</span><span class="sxs-lookup"><span data-stu-id="ba5fb-111">Attributes</span></span>  
  
|<span data-ttu-id="ba5fb-112">特性</span><span class="sxs-lookup"><span data-stu-id="ba5fb-112">Attribute</span></span>|<span data-ttu-id="ba5fb-113">描述</span><span class="sxs-lookup"><span data-stu-id="ba5fb-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba5fb-114">enabled</span><span class="sxs-lookup"><span data-stu-id="ba5fb-114">enabled</span></span>|<span data-ttu-id="ba5fb-115">一个布尔值，该值指定是否在此终结点上启用可发现性。</span><span class="sxs-lookup"><span data-stu-id="ba5fb-115">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="ba5fb-116">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="ba5fb-116">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba5fb-117">子元素</span><span class="sxs-lookup"><span data-stu-id="ba5fb-117">Child Elements</span></span>  
  
|<span data-ttu-id="ba5fb-118">元素</span><span class="sxs-lookup"><span data-stu-id="ba5fb-118">Element</span></span>|<span data-ttu-id="ba5fb-119">描述</span><span class="sxs-lookup"><span data-stu-id="ba5fb-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba5fb-120">\<scopes></span><span class="sxs-lookup"><span data-stu-id="ba5fb-120">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="ba5fb-121">终结点的范围 URI 集合。</span><span class="sxs-lookup"><span data-stu-id="ba5fb-121">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="ba5fb-122">一个终结点可以与多个范围 URI 关联。</span><span class="sxs-lookup"><span data-stu-id="ba5fb-122">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="ba5fb-123">[\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [of \<endpointDiscovery>]</span><span class="sxs-lookup"><span data-stu-id="ba5fb-123">[\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="ba5fb-124">一个 XML 元素集合，用于指定要对终结点发布的自定义元数据。</span><span class="sxs-lookup"><span data-stu-id="ba5fb-124">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="ba5fb-125">\<types></span><span class="sxs-lookup"><span data-stu-id="ba5fb-125">\<types></span></span>|<span data-ttu-id="ba5fb-126">要搜索的接口集合。</span><span class="sxs-lookup"><span data-stu-id="ba5fb-126">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba5fb-127">父元素</span><span class="sxs-lookup"><span data-stu-id="ba5fb-127">Parent Elements</span></span>  
  
|<span data-ttu-id="ba5fb-128">元素</span><span class="sxs-lookup"><span data-stu-id="ba5fb-128">Element</span></span>|<span data-ttu-id="ba5fb-129">描述</span><span class="sxs-lookup"><span data-stu-id="ba5fb-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba5fb-130">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ba5fb-130">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="ba5fb-131">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="ba5fb-131">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="ba5fb-132">备注</span><span class="sxs-lookup"><span data-stu-id="ba5fb-132">Remarks</span></span>  
 <span data-ttu-id="ba5fb-133">如果将此配置元素添加到终结点的行为配置，并将 `enabled` 特性设置为 `true`，此配置元素将启用该终结点的可发现性。</span><span class="sxs-lookup"><span data-stu-id="ba5fb-133">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="ba5fb-134">此外，还可以使用[\<作用域 >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)子元素指定自定义范围可用于在查询期间筛选服务终结点的 Uri 并将[\<扩展 >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md)子元素指定应随标准可发现元数据 （EPR、 ContractTypeName、 BindingName、 范围和 ListenURI） 一起发布的自定义元数据。</span><span class="sxs-lookup"><span data-stu-id="ba5fb-134">In addition, you can use the [\<scopes>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="ba5fb-135">此配置元素是依赖于[ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)元素，它提供服务级别控制的可发现性。</span><span class="sxs-lookup"><span data-stu-id="ba5fb-135">This configuration element is dependent on the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="ba5fb-136">这意味着，如果将忽略此元素的设置[ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)配置中不存在。</span><span class="sxs-lookup"><span data-stu-id="ba5fb-136">This means that this element’s settings are ignored if [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba5fb-137">示例</span><span class="sxs-lookup"><span data-stu-id="ba5fb-137">Example</span></span>  
 <span data-ttu-id="ba5fb-138">下面的配置示例指定要对终结点发布的筛选范围和扩展元数据。</span><span class="sxs-lookup"><span data-stu-id="ba5fb-138">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService"
              behaviorConfiguration="calculatorEndpointBehavior" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery />
    </behavior>
  </serviceBehaviors>
  <endpointBehaviors>
    <behavior name="calculatorEndpointBehavior">
      <endpointDiscovery enabled="true">
        <scopes>
          <add scope="http://contoso/test1" />
          <add scope="http://contoso/test2" />
        </scopes>
        <extensions>
          <e:Publisher xmlns:e="http://example.org">
            <e:Name>The Example Organization</e:Name>
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>
            <e:Contact>support@example.org</e:Contact>
          </e:Publisher>
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>
        </extensions>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="ba5fb-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba5fb-139">See also</span></span>
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
