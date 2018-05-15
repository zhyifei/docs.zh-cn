---
title: '&lt;筛选器&gt;'
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 93d47fc6b25a75eedae43cd70582abc863a74e6c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltfiltergt"></a><span data-ttu-id="736a0-102">&lt;筛选器&gt;</span><span class="sxs-lookup"><span data-stu-id="736a0-102">&lt;filter&gt;</span></span>

<span data-ttu-id="736a0-103">定义路由筛选器，确定类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>以作为也任何支持的数据或筛选器所需参数计算传入消息时使用。</span><span class="sxs-lookup"><span data-stu-id="736a0-103">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="736a0-104">\<system.serviceModel >\<路由 >\<筛选器 >\<筛选器 ></span><span class="sxs-lookup"><span data-stu-id="736a0-104">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>

## <a name="syntax"></a><span data-ttu-id="736a0-105">语法</span><span class="sxs-lookup"><span data-stu-id="736a0-105">Syntax</span></span>

```xml
<routing>
  <filters>
    <filter customType="String" 
            filterData="String" 
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
            name="String" />
  </filters>
</routing>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="736a0-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="736a0-106">Attributes and elements</span></span>

<span data-ttu-id="736a0-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="736a0-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="736a0-108">特性</span><span class="sxs-lookup"><span data-stu-id="736a0-108">Attributes</span></span>

| <span data-ttu-id="736a0-109">特性</span><span class="sxs-lookup"><span data-stu-id="736a0-109">Attribute</span></span>  | <span data-ttu-id="736a0-110">描述</span><span class="sxs-lookup"><span data-stu-id="736a0-110">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="736a0-111">customType</span><span class="sxs-lookup"><span data-stu-id="736a0-111">customType</span></span> | <span data-ttu-id="736a0-112">一个字符串，包含要用作筛选器的自定义类型的完全限定类型名称。</span><span class="sxs-lookup"><span data-stu-id="736a0-112">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="736a0-113">如果`filterType`设置为`custom`，此属性包含要创建的类的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="736a0-113">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="736a0-114">`filterData` 可能还包含要自定义类型筛选器求值期间使用的值。</span><span class="sxs-lookup"><span data-stu-id="736a0-114">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="736a0-115">filterData</span><span class="sxs-lookup"><span data-stu-id="736a0-115">filterData</span></span> | <span data-ttu-id="736a0-116">一个包含筛选器数据的字符串。</span><span class="sxs-lookup"><span data-stu-id="736a0-116">A string containing the filter data.</span></span> <span data-ttu-id="736a0-117">有关如何指定此特性的更多信息，请参见 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>。</span><span class="sxs-lookup"><span data-stu-id="736a0-117">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="736a0-118">filterType</span><span class="sxs-lookup"><span data-stu-id="736a0-118">filterType</span></span> | <span data-ttu-id="736a0-119">一个包含筛选器类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="736a0-119">A string containing the filter type.</span></span> <span data-ttu-id="736a0-120">此特性的类型为 <xref:System.ServiceModel.Routing.Configuration.FilterType>。</span><span class="sxs-lookup"><span data-stu-id="736a0-120">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="736a0-121">有关如何使用此 `filterData` 特性的更多信息，请参见 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>。</span><span class="sxs-lookup"><span data-stu-id="736a0-121">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="736a0-122">name</span><span class="sxs-lookup"><span data-stu-id="736a0-122">name</span></span>       | <span data-ttu-id="736a0-123">一个字符串，包含此筛选器元素的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="736a0-123">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="736a0-124">子元素</span><span class="sxs-lookup"><span data-stu-id="736a0-124">Child elements</span></span>

<span data-ttu-id="736a0-125">无。</span><span class="sxs-lookup"><span data-stu-id="736a0-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="736a0-126">父元素</span><span class="sxs-lookup"><span data-stu-id="736a0-126">Parent elements</span></span>

| <span data-ttu-id="736a0-127">元素</span><span class="sxs-lookup"><span data-stu-id="736a0-127">Element</span></span> | <span data-ttu-id="736a0-128">描述</span><span class="sxs-lookup"><span data-stu-id="736a0-128">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="736a0-129">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="736a0-129">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="736a0-130">用于定义一组路由筛选器，这些扩展名决定了类型的 Windows Communication Foundation (WCF) 的配置节<xref:System.ServiceModel.Dispatcher.MessageFilter>计算传入消息时使用。</span><span class="sxs-lookup"><span data-stu-id="736a0-130">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="736a0-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="736a0-131">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
