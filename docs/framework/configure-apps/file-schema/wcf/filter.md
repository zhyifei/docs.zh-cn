---
title: "&lt;筛选器&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: af2095289d5f711733c71238b855c685114d1997
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltfiltergt"></a><span data-ttu-id="ea217-102">&lt;筛选器&gt;</span><span class="sxs-lookup"><span data-stu-id="ea217-102">&lt;filter&gt;</span></span>

<span data-ttu-id="ea217-103">定义路由筛选器，该筛选器确定计算传入消息时使用的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> 的类型，以及该筛选器所需的任何支持数据或参数。</span><span class="sxs-lookup"><span data-stu-id="ea217-103">Defines a routing filter, which determines the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="ea217-104">\<system.serviceModel >\<路由 >\<筛选器 >\<筛选器 ></span><span class="sxs-lookup"><span data-stu-id="ea217-104">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>

## <a name="syntax"></a><span data-ttu-id="ea217-105">语法</span><span class="sxs-lookup"><span data-stu-id="ea217-105">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="ea217-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ea217-106">Attributes and elements</span></span>

<span data-ttu-id="ea217-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ea217-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ea217-108">特性</span><span class="sxs-lookup"><span data-stu-id="ea217-108">Attributes</span></span>

| <span data-ttu-id="ea217-109">特性</span><span class="sxs-lookup"><span data-stu-id="ea217-109">Attribute</span></span>  | <span data-ttu-id="ea217-110">描述</span><span class="sxs-lookup"><span data-stu-id="ea217-110">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="ea217-111">customType</span><span class="sxs-lookup"><span data-stu-id="ea217-111">customType</span></span> | <span data-ttu-id="ea217-112">一个字符串，包含要用作筛选器的自定义类型的完全限定类型名称。</span><span class="sxs-lookup"><span data-stu-id="ea217-112">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="ea217-113">如果`filterType`设置为`custom`，此属性包含要创建的类的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="ea217-113">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="ea217-114">`filterData`可能还包含要自定义类型筛选器求值期间使用的值。</span><span class="sxs-lookup"><span data-stu-id="ea217-114">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="ea217-115">filterData</span><span class="sxs-lookup"><span data-stu-id="ea217-115">filterData</span></span> | <span data-ttu-id="ea217-116">一个包含筛选器数据的字符串。</span><span class="sxs-lookup"><span data-stu-id="ea217-116">A string containing the filter data.</span></span> <span data-ttu-id="ea217-117">有关如何指定此特性的更多信息，请参见 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>。</span><span class="sxs-lookup"><span data-stu-id="ea217-117">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="ea217-118">filterType</span><span class="sxs-lookup"><span data-stu-id="ea217-118">filterType</span></span> | <span data-ttu-id="ea217-119">一个包含筛选器类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="ea217-119">A string containing the filter type.</span></span> <span data-ttu-id="ea217-120">此特性的类型为 <xref:System.ServiceModel.Routing.Configuration.FilterType>。</span><span class="sxs-lookup"><span data-stu-id="ea217-120">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="ea217-121">有关如何使用此 `filterData` 特性的更多信息，请参见 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>。</span><span class="sxs-lookup"><span data-stu-id="ea217-121">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="ea217-122">name</span><span class="sxs-lookup"><span data-stu-id="ea217-122">name</span></span>       | <span data-ttu-id="ea217-123">一个字符串，包含此筛选器元素的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="ea217-123">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="ea217-124">子元素</span><span class="sxs-lookup"><span data-stu-id="ea217-124">Child elements</span></span>

<span data-ttu-id="ea217-125">无。</span><span class="sxs-lookup"><span data-stu-id="ea217-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ea217-126">父元素</span><span class="sxs-lookup"><span data-stu-id="ea217-126">Parent elements</span></span>

| <span data-ttu-id="ea217-127">元素</span><span class="sxs-lookup"><span data-stu-id="ea217-127">Element</span></span> | <span data-ttu-id="ea217-128">描述</span><span class="sxs-lookup"><span data-stu-id="ea217-128">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="ea217-129">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="ea217-129">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="ea217-130">一个配置节，用于定义一组路由筛选器，这些筛选器确定计算传入消息时使用的 [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> 的类型。</span><span class="sxs-lookup"><span data-stu-id="ea217-130">A configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="ea217-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea217-131">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
