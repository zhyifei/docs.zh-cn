---
title: '&lt;filter&gt;'
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 9fae9a599299fdd8cf1e996593514fc0ef38b6ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645504"
---
# <a name="ltfiltergt"></a><span data-ttu-id="3bbed-102">&lt;filter&gt;</span><span class="sxs-lookup"><span data-stu-id="3bbed-102">&lt;filter&gt;</span></span>

<span data-ttu-id="3bbed-103">定义路由筛选器，确定类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>若要在评估传入消息，以及任何支持的数据和所需的筛选器参数时使用。</span><span class="sxs-lookup"><span data-stu-id="3bbed-103">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="3bbed-104">\<system.serviceModel> \<routing> \<filters> \<filter></span><span class="sxs-lookup"><span data-stu-id="3bbed-104">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>
  
## <a name="syntax"></a><span data-ttu-id="3bbed-105">语法</span><span class="sxs-lookup"><span data-stu-id="3bbed-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3bbed-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3bbed-106">Attributes and elements</span></span>

<span data-ttu-id="3bbed-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3bbed-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3bbed-108">特性</span><span class="sxs-lookup"><span data-stu-id="3bbed-108">Attributes</span></span>

| <span data-ttu-id="3bbed-109">特性</span><span class="sxs-lookup"><span data-stu-id="3bbed-109">Attribute</span></span>  | <span data-ttu-id="3bbed-110">描述</span><span class="sxs-lookup"><span data-stu-id="3bbed-110">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="3bbed-111">customType</span><span class="sxs-lookup"><span data-stu-id="3bbed-111">customType</span></span> | <span data-ttu-id="3bbed-112">一个字符串，包含要用作筛选器的自定义类型的完全限定类型名称。</span><span class="sxs-lookup"><span data-stu-id="3bbed-112">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="3bbed-113">如果`filterType`设置为`custom`，该属性包含要创建的类的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="3bbed-113">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="3bbed-114">`filterData` 此外可能包含对自定义类型筛选器求值期间使用的值。</span><span class="sxs-lookup"><span data-stu-id="3bbed-114">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="3bbed-115">filterData</span><span class="sxs-lookup"><span data-stu-id="3bbed-115">filterData</span></span> | <span data-ttu-id="3bbed-116">一个包含筛选器数据的字符串。</span><span class="sxs-lookup"><span data-stu-id="3bbed-116">A string containing the filter data.</span></span> <span data-ttu-id="3bbed-117">有关如何指定此特性的更多信息，请参见 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>。</span><span class="sxs-lookup"><span data-stu-id="3bbed-117">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="3bbed-118">filterType</span><span class="sxs-lookup"><span data-stu-id="3bbed-118">filterType</span></span> | <span data-ttu-id="3bbed-119">一个包含筛选器类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="3bbed-119">A string containing the filter type.</span></span> <span data-ttu-id="3bbed-120">此特性的类型为 <xref:System.ServiceModel.Routing.Configuration.FilterType>。</span><span class="sxs-lookup"><span data-stu-id="3bbed-120">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="3bbed-121">有关如何使用此 `filterData` 特性的更多信息，请参见 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>。</span><span class="sxs-lookup"><span data-stu-id="3bbed-121">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="3bbed-122">name</span><span class="sxs-lookup"><span data-stu-id="3bbed-122">name</span></span>       | <span data-ttu-id="3bbed-123">一个字符串，包含此筛选器元素的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="3bbed-123">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="3bbed-124">子元素</span><span class="sxs-lookup"><span data-stu-id="3bbed-124">Child elements</span></span>

<span data-ttu-id="3bbed-125">无。</span><span class="sxs-lookup"><span data-stu-id="3bbed-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3bbed-126">父元素</span><span class="sxs-lookup"><span data-stu-id="3bbed-126">Parent elements</span></span>

| <span data-ttu-id="3bbed-127">元素</span><span class="sxs-lookup"><span data-stu-id="3bbed-127">Element</span></span> | <span data-ttu-id="3bbed-128">描述</span><span class="sxs-lookup"><span data-stu-id="3bbed-128">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="3bbed-129">\<routing></span><span class="sxs-lookup"><span data-stu-id="3bbed-129">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="3bbed-130">用于定义一组路由筛选器，确定类型的 Windows Communication Foundation (WCF) 的配置节<xref:System.ServiceModel.Dispatcher.MessageFilter>要评估传入消息时使用。</span><span class="sxs-lookup"><span data-stu-id="3bbed-130">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3bbed-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bbed-131">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
