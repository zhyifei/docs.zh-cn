---
title: '&lt;endpointDiscovery&gt;'
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: c5971ce79ac2f03fbdc91653d5d282804e98cf8a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltendpointdiscoverygt"></a><span data-ttu-id="71a76-102">&lt;endpointDiscovery&gt;</span><span class="sxs-lookup"><span data-stu-id="71a76-102">&lt;endpointDiscovery&gt;</span></span>
<span data-ttu-id="71a76-103">指定终结点的各种发现设置，例如终结点的可发现性、范围以及对终结点元数据的任何自定义扩展。</span><span class="sxs-lookup"><span data-stu-id="71a76-103">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="71a76-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="71a76-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="71a76-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="71a76-105">\<behaviors></span></span>  
<span data-ttu-id="71a76-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="71a76-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="71a76-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="71a76-107">\<behavior></span></span>  
<span data-ttu-id="71a76-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="71a76-108">\<endpointDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71a76-109">语法</span><span class="sxs-lookup"><span data-stu-id="71a76-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71a76-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="71a76-110">Attributes and Elements</span></span>  
 <span data-ttu-id="71a76-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="71a76-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71a76-112">特性</span><span class="sxs-lookup"><span data-stu-id="71a76-112">Attributes</span></span>  
  
|<span data-ttu-id="71a76-113">特性</span><span class="sxs-lookup"><span data-stu-id="71a76-113">Attribute</span></span>|<span data-ttu-id="71a76-114">描述</span><span class="sxs-lookup"><span data-stu-id="71a76-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71a76-115">enabled</span><span class="sxs-lookup"><span data-stu-id="71a76-115">enabled</span></span>|<span data-ttu-id="71a76-116">一个布尔值，指定是否对此终结点启用可发现性。</span><span class="sxs-lookup"><span data-stu-id="71a76-116">A Boolean value that that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="71a76-117">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="71a76-117">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71a76-118">子元素</span><span class="sxs-lookup"><span data-stu-id="71a76-118">Child Elements</span></span>  
  
|<span data-ttu-id="71a76-119">元素</span><span class="sxs-lookup"><span data-stu-id="71a76-119">Element</span></span>|<span data-ttu-id="71a76-120">描述</span><span class="sxs-lookup"><span data-stu-id="71a76-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71a76-121">\<作用域 ></span><span class="sxs-lookup"><span data-stu-id="71a76-121">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="71a76-122">终结点的范围 URI 集合。</span><span class="sxs-lookup"><span data-stu-id="71a76-122">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="71a76-123">一个终结点可以与多个范围 URI 关联。</span><span class="sxs-lookup"><span data-stu-id="71a76-123">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="71a76-124">[\<扩展 >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [的\<endpointDiscovery >]</span><span class="sxs-lookup"><span data-stu-id="71a76-124">[\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="71a76-125">一个 XML 元素集合，用于指定要对终结点发布的自定义元数据。</span><span class="sxs-lookup"><span data-stu-id="71a76-125">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="71a76-126">\<类型 ></span><span class="sxs-lookup"><span data-stu-id="71a76-126">\<types></span></span>|<span data-ttu-id="71a76-127">要搜索的接口集合。</span><span class="sxs-lookup"><span data-stu-id="71a76-127">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="71a76-128">父元素</span><span class="sxs-lookup"><span data-stu-id="71a76-128">Parent Elements</span></span>  
  
|<span data-ttu-id="71a76-129">元素</span><span class="sxs-lookup"><span data-stu-id="71a76-129">Element</span></span>|<span data-ttu-id="71a76-130">描述</span><span class="sxs-lookup"><span data-stu-id="71a76-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71a76-131">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="71a76-131">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="71a76-132">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="71a76-132">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="71a76-133">备注</span><span class="sxs-lookup"><span data-stu-id="71a76-133">Remarks</span></span>  
 <span data-ttu-id="71a76-134">如果将此配置元素添加到终结点的行为配置，并将 `enabled` 特性设置为 `true`，此配置元素将启用该终结点的可发现性。</span><span class="sxs-lookup"><span data-stu-id="71a76-134">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="71a76-135">此外，你可以使用[\<作用域 >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)与指定自定义范围 Uri 可以用于在查询时筛选服务终结点的子元素以及[\<扩展 >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md)子元素可指定应随标准可发现元数据 （EPR、 ContractTypeName、 BindingName、 作用域和 ListenURI） 一起发布的自定义元数据。</span><span class="sxs-lookup"><span data-stu-id="71a76-135">In addition, you can use the [\<scopes>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="71a76-136">此配置元素是依赖于[ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)提供可发现性服务级别控制的元素。</span><span class="sxs-lookup"><span data-stu-id="71a76-136">This configuration element is dependent on the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="71a76-137">这意味着如果将忽略此元素的设置[ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)不是配置中存在。</span><span class="sxs-lookup"><span data-stu-id="71a76-137">This means that this element’s settings are ignored if [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71a76-138">示例</span><span class="sxs-lookup"><span data-stu-id="71a76-138">Example</span></span>  
 <span data-ttu-id="71a76-139">下面的配置示例指定要对终结点发布的筛选范围和扩展元数据。</span><span class="sxs-lookup"><span data-stu-id="71a76-139">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
          <add scope="http://contoso/test1"/>  
          <add scope="http://contoso/test2"/>  
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
  
## <a name="see-also"></a><span data-ttu-id="71a76-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="71a76-140">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
