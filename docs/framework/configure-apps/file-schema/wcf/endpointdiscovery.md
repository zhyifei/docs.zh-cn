---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 5cb64c54067ba695f67d86c0026db77ebbe7d5ee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919054"
---
# <a name="endpointdiscovery"></a><span data-ttu-id="53cd7-101">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="53cd7-101">\<endpointDiscovery></span></span>
<span data-ttu-id="53cd7-102">指定终结点的各种发现设置，例如终结点的可发现性、范围以及对终结点元数据的任何自定义扩展。</span><span class="sxs-lookup"><span data-stu-id="53cd7-102">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="53cd7-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="53cd7-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="53cd7-104">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="53cd7-104">\<behaviors></span></span>  
<span data-ttu-id="53cd7-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="53cd7-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="53cd7-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="53cd7-106">\<behavior></span></span>  
<span data-ttu-id="53cd7-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="53cd7-107">\<endpointDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53cd7-108">语法</span><span class="sxs-lookup"><span data-stu-id="53cd7-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53cd7-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="53cd7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="53cd7-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="53cd7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53cd7-111">特性</span><span class="sxs-lookup"><span data-stu-id="53cd7-111">Attributes</span></span>  
  
|<span data-ttu-id="53cd7-112">特性</span><span class="sxs-lookup"><span data-stu-id="53cd7-112">Attribute</span></span>|<span data-ttu-id="53cd7-113">描述</span><span class="sxs-lookup"><span data-stu-id="53cd7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53cd7-114">enabled</span><span class="sxs-lookup"><span data-stu-id="53cd7-114">enabled</span></span>|<span data-ttu-id="53cd7-115">一个布尔值, 指定是否在此终结点上启用可发现性。</span><span class="sxs-lookup"><span data-stu-id="53cd7-115">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="53cd7-116">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="53cd7-116">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53cd7-117">子元素</span><span class="sxs-lookup"><span data-stu-id="53cd7-117">Child Elements</span></span>  
  
|<span data-ttu-id="53cd7-118">元素</span><span class="sxs-lookup"><span data-stu-id="53cd7-118">Element</span></span>|<span data-ttu-id="53cd7-119">描述</span><span class="sxs-lookup"><span data-stu-id="53cd7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53cd7-120">\<scopes></span><span class="sxs-lookup"><span data-stu-id="53cd7-120">\<scopes></span></span>](scopes.md)|<span data-ttu-id="53cd7-121">终结点的范围 URI 集合。</span><span class="sxs-lookup"><span data-stu-id="53cd7-121">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="53cd7-122">一个终结点可以与多个范围 URI 关联。</span><span class="sxs-lookup"><span data-stu-id="53cd7-122">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="53cd7-123">扩展 > [of endpointDiscovery>]\< [ \<](extensions.md)</span><span class="sxs-lookup"><span data-stu-id="53cd7-123">[\<extensions>](extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="53cd7-124">一个 XML 元素集合，用于指定要对终结点发布的自定义元数据。</span><span class="sxs-lookup"><span data-stu-id="53cd7-124">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="53cd7-125">\<types></span><span class="sxs-lookup"><span data-stu-id="53cd7-125">\<types></span></span>|<span data-ttu-id="53cd7-126">要搜索的接口集合。</span><span class="sxs-lookup"><span data-stu-id="53cd7-126">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="53cd7-127">父元素</span><span class="sxs-lookup"><span data-stu-id="53cd7-127">Parent Elements</span></span>  
  
|<span data-ttu-id="53cd7-128">元素</span><span class="sxs-lookup"><span data-stu-id="53cd7-128">Element</span></span>|<span data-ttu-id="53cd7-129">描述</span><span class="sxs-lookup"><span data-stu-id="53cd7-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53cd7-130">\<behavior></span><span class="sxs-lookup"><span data-stu-id="53cd7-130">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="53cd7-131">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="53cd7-131">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="53cd7-132">备注</span><span class="sxs-lookup"><span data-stu-id="53cd7-132">Remarks</span></span>  
 <span data-ttu-id="53cd7-133">如果将此配置元素添加到终结点的行为配置，并将 `enabled` 特性设置为 `true`，此配置元素将启用该终结点的可发现性。</span><span class="sxs-lookup"><span data-stu-id="53cd7-133">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="53cd7-134">此外, 您还可以使用[ \<范围 >](scopes.md)子元素指定可用于在查询期间筛选服务终结点的自定义范围 uri, 以及用于指定自定义的[ \<扩展 >](extensions.md)子元素应与标准可发现元数据 (EPR、ContractTypeName、BindingName、Scope 和 ListenURI) 一起发布的元数据。</span><span class="sxs-lookup"><span data-stu-id="53cd7-134">In addition, you can use the [\<scopes>](scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="53cd7-135">此配置元素依赖[ \<](servicediscovery.md)于提供可发现性服务级别控制的 serviceDiscovery > 元素。</span><span class="sxs-lookup"><span data-stu-id="53cd7-135">This configuration element is dependent on the [\<serviceDiscovery>](servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="53cd7-136">这意味着, 如果[ \<](servicediscovery.md)配置中不存在 serviceDiscovery >, 将忽略此元素的设置。</span><span class="sxs-lookup"><span data-stu-id="53cd7-136">This means that this element’s settings are ignored if [\<serviceDiscovery>](servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53cd7-137">示例</span><span class="sxs-lookup"><span data-stu-id="53cd7-137">Example</span></span>  
 <span data-ttu-id="53cd7-138">下面的配置示例指定要对终结点发布的筛选范围和扩展元数据。</span><span class="sxs-lookup"><span data-stu-id="53cd7-138">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="53cd7-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="53cd7-139">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
