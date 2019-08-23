---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 68de255b9f11dc4377159d1cc3efa575633db316
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918897"
---
# <a name="filter"></a><span data-ttu-id="00457-101">\<filter></span><span class="sxs-lookup"><span data-stu-id="00457-101">\<filter></span></span>

<span data-ttu-id="00457-102">定义一个路由筛选器, 该筛选器确定要在评估传入<xref:System.ServiceModel.Dispatcher.MessageFilter>消息时使用的 Windows Communication Foundation (WCF) 的类型, 以及筛选器所需的任何支持数据或参数。</span><span class="sxs-lookup"><span data-stu-id="00457-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="00457-103">\<system.serviceModel> \<routing> \<filters> \<filter></span><span class="sxs-lookup"><span data-stu-id="00457-103">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>
  
## <a name="syntax"></a><span data-ttu-id="00457-104">语法</span><span class="sxs-lookup"><span data-stu-id="00457-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00457-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="00457-105">Attributes and elements</span></span>

<span data-ttu-id="00457-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="00457-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="00457-107">特性</span><span class="sxs-lookup"><span data-stu-id="00457-107">Attributes</span></span>

| <span data-ttu-id="00457-108">特性</span><span class="sxs-lookup"><span data-stu-id="00457-108">Attribute</span></span>  | <span data-ttu-id="00457-109">描述</span><span class="sxs-lookup"><span data-stu-id="00457-109">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="00457-110">customType</span><span class="sxs-lookup"><span data-stu-id="00457-110">customType</span></span> | <span data-ttu-id="00457-111">一个字符串，包含要用作筛选器的自定义类型的完全限定类型名称。</span><span class="sxs-lookup"><span data-stu-id="00457-111">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="00457-112">如果`filterType`设置为`custom`, 则此特性包含要创建的类的完全限定类型名称。</span><span class="sxs-lookup"><span data-stu-id="00457-112">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="00457-113">`filterData`还可以包含在计算自定义类型筛选器的过程中要使用的值。</span><span class="sxs-lookup"><span data-stu-id="00457-113">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="00457-114">filterData</span><span class="sxs-lookup"><span data-stu-id="00457-114">filterData</span></span> | <span data-ttu-id="00457-115">一个包含筛选器数据的字符串。</span><span class="sxs-lookup"><span data-stu-id="00457-115">A string containing the filter data.</span></span> <span data-ttu-id="00457-116">有关如何指定此特性的更多信息，请参见 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>。</span><span class="sxs-lookup"><span data-stu-id="00457-116">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="00457-117">filterType</span><span class="sxs-lookup"><span data-stu-id="00457-117">filterType</span></span> | <span data-ttu-id="00457-118">一个包含筛选器类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="00457-118">A string containing the filter type.</span></span> <span data-ttu-id="00457-119">此特性的类型为 <xref:System.ServiceModel.Routing.Configuration.FilterType>。</span><span class="sxs-lookup"><span data-stu-id="00457-119">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="00457-120">有关如何使用此 `filterData` 特性的更多信息，请参见 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>。</span><span class="sxs-lookup"><span data-stu-id="00457-120">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="00457-121">NAME</span><span class="sxs-lookup"><span data-stu-id="00457-121">name</span></span>       | <span data-ttu-id="00457-122">一个字符串，包含此筛选器元素的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="00457-122">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="00457-123">子元素</span><span class="sxs-lookup"><span data-stu-id="00457-123">Child elements</span></span>

<span data-ttu-id="00457-124">无。</span><span class="sxs-lookup"><span data-stu-id="00457-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="00457-125">父元素</span><span class="sxs-lookup"><span data-stu-id="00457-125">Parent elements</span></span>

| <span data-ttu-id="00457-126">元素</span><span class="sxs-lookup"><span data-stu-id="00457-126">Element</span></span> | <span data-ttu-id="00457-127">描述</span><span class="sxs-lookup"><span data-stu-id="00457-127">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="00457-128">\<routing></span><span class="sxs-lookup"><span data-stu-id="00457-128">\<routing></span></span>](routing.md) | <span data-ttu-id="00457-129">用于定义一组路由筛选器的配置节, 这些筛选器确定计算传入消息时使用<xref:System.ServiceModel.Dispatcher.MessageFilter>的 Windows Communication Foundation (WCF) 的类型。</span><span class="sxs-lookup"><span data-stu-id="00457-129">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="00457-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="00457-130">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
