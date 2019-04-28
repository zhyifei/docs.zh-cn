---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: bff19f106d86c73dea80b8b57bb73442eaa2cf9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704032"
---
# <a name="filter"></a><span data-ttu-id="31c9d-101">\<filter></span><span class="sxs-lookup"><span data-stu-id="31c9d-101">\<filter></span></span>

<span data-ttu-id="31c9d-102">定义路由筛选器，确定类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>若要在评估传入消息，以及任何支持的数据和所需的筛选器参数时使用。</span><span class="sxs-lookup"><span data-stu-id="31c9d-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="31c9d-103">\<system.serviceModel> \<routing> \<filters> \<filter></span><span class="sxs-lookup"><span data-stu-id="31c9d-103">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>
  
## <a name="syntax"></a><span data-ttu-id="31c9d-104">语法</span><span class="sxs-lookup"><span data-stu-id="31c9d-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31c9d-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="31c9d-105">Attributes and elements</span></span>

<span data-ttu-id="31c9d-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="31c9d-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="31c9d-107">特性</span><span class="sxs-lookup"><span data-stu-id="31c9d-107">Attributes</span></span>

| <span data-ttu-id="31c9d-108">特性</span><span class="sxs-lookup"><span data-stu-id="31c9d-108">Attribute</span></span>  | <span data-ttu-id="31c9d-109">描述</span><span class="sxs-lookup"><span data-stu-id="31c9d-109">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="31c9d-110">customType</span><span class="sxs-lookup"><span data-stu-id="31c9d-110">customType</span></span> | <span data-ttu-id="31c9d-111">一个字符串，包含要用作筛选器的自定义类型的完全限定类型名称。</span><span class="sxs-lookup"><span data-stu-id="31c9d-111">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="31c9d-112">如果`filterType`设置为`custom`，该属性包含要创建的类的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="31c9d-112">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="31c9d-113">`filterData` 此外可能包含对自定义类型筛选器求值期间使用的值。</span><span class="sxs-lookup"><span data-stu-id="31c9d-113">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="31c9d-114">filterData</span><span class="sxs-lookup"><span data-stu-id="31c9d-114">filterData</span></span> | <span data-ttu-id="31c9d-115">一个包含筛选器数据的字符串。</span><span class="sxs-lookup"><span data-stu-id="31c9d-115">A string containing the filter data.</span></span> <span data-ttu-id="31c9d-116">有关如何指定此特性的更多信息，请参见 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>。</span><span class="sxs-lookup"><span data-stu-id="31c9d-116">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="31c9d-117">filterType</span><span class="sxs-lookup"><span data-stu-id="31c9d-117">filterType</span></span> | <span data-ttu-id="31c9d-118">一个包含筛选器类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="31c9d-118">A string containing the filter type.</span></span> <span data-ttu-id="31c9d-119">此特性的类型为 <xref:System.ServiceModel.Routing.Configuration.FilterType>。</span><span class="sxs-lookup"><span data-stu-id="31c9d-119">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="31c9d-120">有关如何使用此 `filterData` 特性的更多信息，请参见 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>。</span><span class="sxs-lookup"><span data-stu-id="31c9d-120">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="31c9d-121">name</span><span class="sxs-lookup"><span data-stu-id="31c9d-121">name</span></span>       | <span data-ttu-id="31c9d-122">一个字符串，包含此筛选器元素的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="31c9d-122">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="31c9d-123">子元素</span><span class="sxs-lookup"><span data-stu-id="31c9d-123">Child elements</span></span>

<span data-ttu-id="31c9d-124">无。</span><span class="sxs-lookup"><span data-stu-id="31c9d-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="31c9d-125">父元素</span><span class="sxs-lookup"><span data-stu-id="31c9d-125">Parent elements</span></span>

| <span data-ttu-id="31c9d-126">元素</span><span class="sxs-lookup"><span data-stu-id="31c9d-126">Element</span></span> | <span data-ttu-id="31c9d-127">描述</span><span class="sxs-lookup"><span data-stu-id="31c9d-127">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="31c9d-128">\<routing></span><span class="sxs-lookup"><span data-stu-id="31c9d-128">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="31c9d-129">用于定义一组路由筛选器，确定类型的 Windows Communication Foundation (WCF) 的配置节<xref:System.ServiceModel.Dispatcher.MessageFilter>要评估传入消息时使用。</span><span class="sxs-lookup"><span data-stu-id="31c9d-129">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="31c9d-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="31c9d-130">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
