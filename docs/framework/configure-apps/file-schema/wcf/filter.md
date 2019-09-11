---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 6e78275aaeb202405e327302455d56fa431d7f27
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855258"
---
# <a name="filter"></a><span data-ttu-id="36b0c-101">\<filter></span><span class="sxs-lookup"><span data-stu-id="36b0c-101">\<filter></span></span>

<span data-ttu-id="36b0c-102">定义一个路由筛选器，该筛选器确定要在评估传入<xref:System.ServiceModel.Dispatcher.MessageFilter>消息时使用的 Windows Communication Foundation （WCF）的类型，以及筛选器所需的任何支持数据或参数。</span><span class="sxs-lookup"><span data-stu-id="36b0c-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="36b0c-103">[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="36b0c-103">[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="36b0c-104">&nbsp;&nbsp;[ **\<routing>** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="36b0c-104">&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="36b0c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<筛选器 >** ](filters-of-routing.md)</span><span class="sxs-lookup"><span data-stu-id="36b0c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters-of-routing.md)</span></span>\
<span data-ttu-id="36b0c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<筛选 >**</span><span class="sxs-lookup"><span data-stu-id="36b0c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36b0c-107">语法</span><span class="sxs-lookup"><span data-stu-id="36b0c-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36b0c-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="36b0c-108">Attributes and elements</span></span>

<span data-ttu-id="36b0c-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="36b0c-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="36b0c-110">特性</span><span class="sxs-lookup"><span data-stu-id="36b0c-110">Attributes</span></span>

| <span data-ttu-id="36b0c-111">特性</span><span class="sxs-lookup"><span data-stu-id="36b0c-111">Attribute</span></span>  | <span data-ttu-id="36b0c-112">描述</span><span class="sxs-lookup"><span data-stu-id="36b0c-112">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="36b0c-113">customType</span><span class="sxs-lookup"><span data-stu-id="36b0c-113">customType</span></span> | <span data-ttu-id="36b0c-114">一个字符串，包含要用作筛选器的自定义类型的完全限定类型名称。</span><span class="sxs-lookup"><span data-stu-id="36b0c-114">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="36b0c-115">如果`filterType`设置为`custom`，则此特性包含要创建的类的完全限定类型名称。</span><span class="sxs-lookup"><span data-stu-id="36b0c-115">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="36b0c-116">`filterData`还可以包含在计算自定义类型筛选器的过程中要使用的值。</span><span class="sxs-lookup"><span data-stu-id="36b0c-116">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="36b0c-117">filterData</span><span class="sxs-lookup"><span data-stu-id="36b0c-117">filterData</span></span> | <span data-ttu-id="36b0c-118">一个包含筛选器数据的字符串。</span><span class="sxs-lookup"><span data-stu-id="36b0c-118">A string containing the filter data.</span></span> <span data-ttu-id="36b0c-119">有关如何指定此特性的更多信息，请参见 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>。</span><span class="sxs-lookup"><span data-stu-id="36b0c-119">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="36b0c-120">filterType</span><span class="sxs-lookup"><span data-stu-id="36b0c-120">filterType</span></span> | <span data-ttu-id="36b0c-121">一个包含筛选器类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="36b0c-121">A string containing the filter type.</span></span> <span data-ttu-id="36b0c-122">此特性的类型为 <xref:System.ServiceModel.Routing.Configuration.FilterType>。</span><span class="sxs-lookup"><span data-stu-id="36b0c-122">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="36b0c-123">有关如何使用此 `filterData` 特性的更多信息，请参见 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>。</span><span class="sxs-lookup"><span data-stu-id="36b0c-123">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="36b0c-124">NAME</span><span class="sxs-lookup"><span data-stu-id="36b0c-124">name</span></span>       | <span data-ttu-id="36b0c-125">一个字符串，包含此筛选器元素的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="36b0c-125">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="36b0c-126">子元素</span><span class="sxs-lookup"><span data-stu-id="36b0c-126">Child elements</span></span>

<span data-ttu-id="36b0c-127">无。</span><span class="sxs-lookup"><span data-stu-id="36b0c-127">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="36b0c-128">父元素</span><span class="sxs-lookup"><span data-stu-id="36b0c-128">Parent elements</span></span>

| <span data-ttu-id="36b0c-129">元素</span><span class="sxs-lookup"><span data-stu-id="36b0c-129">Element</span></span> | <span data-ttu-id="36b0c-130">描述</span><span class="sxs-lookup"><span data-stu-id="36b0c-130">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="36b0c-131">\<routing></span><span class="sxs-lookup"><span data-stu-id="36b0c-131">\<routing></span></span>](routing.md) | <span data-ttu-id="36b0c-132">用于定义一组路由筛选器的配置节，这些筛选器确定计算传入消息时使用<xref:System.ServiceModel.Dispatcher.MessageFilter>的 Windows Communication Foundation （WCF）的类型。</span><span class="sxs-lookup"><span data-stu-id="36b0c-132">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="36b0c-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="36b0c-133">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
