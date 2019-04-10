---
title: <Event> 元素 (.NET Native)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89e8ddf9ea72db63c72bfb5393709b4c20de2a14
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162990"
---
# <a name="event-element-net-native"></a><span data-ttu-id="bd11d-102">\<事件 > 元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="bd11d-102">\<Event> Element (.NET Native)</span></span>
<span data-ttu-id="bd11d-103">将运行时反射策略应用到一个事件。</span><span class="sxs-lookup"><span data-stu-id="bd11d-103">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd11d-104">语法</span><span class="sxs-lookup"><span data-stu-id="bd11d-104">Syntax</span></span>  
  
```xml  
<Event Name="event_name"   
       Browse="policy_type"   
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd11d-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bd11d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="bd11d-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="bd11d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd11d-107">特性</span><span class="sxs-lookup"><span data-stu-id="bd11d-107">Attributes</span></span>  
  
|<span data-ttu-id="bd11d-108">特性</span><span class="sxs-lookup"><span data-stu-id="bd11d-108">Attribute</span></span>|<span data-ttu-id="bd11d-109">特性类型</span><span class="sxs-lookup"><span data-stu-id="bd11d-109">Attribute type</span></span>|<span data-ttu-id="bd11d-110">描述</span><span class="sxs-lookup"><span data-stu-id="bd11d-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="bd11d-111">常规</span><span class="sxs-lookup"><span data-stu-id="bd11d-111">General</span></span>|<span data-ttu-id="bd11d-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="bd11d-112">Required attribute.</span></span> <span data-ttu-id="bd11d-113">指定事件名称。</span><span class="sxs-lookup"><span data-stu-id="bd11d-113">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="bd11d-114">映像</span><span class="sxs-lookup"><span data-stu-id="bd11d-114">Reflection</span></span>|<span data-ttu-id="bd11d-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="bd11d-115">Optional attribute.</span></span> <span data-ttu-id="bd11d-116">控制对该事件信息的查询或列举该事件，但并不在运行时间启用任何动态访问。</span><span class="sxs-lookup"><span data-stu-id="bd11d-116">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="bd11d-117">映像</span><span class="sxs-lookup"><span data-stu-id="bd11d-117">Reflection</span></span>|<span data-ttu-id="bd11d-118">可选特性。</span><span class="sxs-lookup"><span data-stu-id="bd11d-118">Optional attribute.</span></span> <span data-ttu-id="bd11d-119">控制运行时对该事件的访问，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="bd11d-119">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="bd11d-120">该策略确保一个事件可在运行时间内得到处理。</span><span class="sxs-lookup"><span data-stu-id="bd11d-120">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="bd11d-121">Name 特性</span><span class="sxs-lookup"><span data-stu-id="bd11d-121">Name attribute</span></span>  
  
|<span data-ttu-id="bd11d-122">“值”</span><span class="sxs-lookup"><span data-stu-id="bd11d-122">Value</span></span>|<span data-ttu-id="bd11d-123">描述</span><span class="sxs-lookup"><span data-stu-id="bd11d-123">Description</span></span>|  
|-----------|-----------------|  
|*<span data-ttu-id="bd11d-124">方法_名称</span><span class="sxs-lookup"><span data-stu-id="bd11d-124">method_name</span></span>*|<span data-ttu-id="bd11d-125">事件名称。</span><span class="sxs-lookup"><span data-stu-id="bd11d-125">The event name.</span></span> <span data-ttu-id="bd11d-126">该事件的类型是由 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 或 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 父元素定义的。</span><span class="sxs-lookup"><span data-stu-id="bd11d-126">The type of the event is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="bd11d-127">所有其他特性</span><span class="sxs-lookup"><span data-stu-id="bd11d-127">All other attributes</span></span>  
  
|<span data-ttu-id="bd11d-128">“值”</span><span class="sxs-lookup"><span data-stu-id="bd11d-128">Value</span></span>|<span data-ttu-id="bd11d-129">描述</span><span class="sxs-lookup"><span data-stu-id="bd11d-129">Description</span></span>|  
|-----------|-----------------|  
|*<span data-ttu-id="bd11d-130">策略_设置</span><span class="sxs-lookup"><span data-stu-id="bd11d-130">policy_setting</span></span>*|<span data-ttu-id="bd11d-131">该设置将应用到这个事件的策略类型。</span><span class="sxs-lookup"><span data-stu-id="bd11d-131">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="bd11d-132">可能值为 `Auto`、`Excluded`、`Included` 和 `Required`。</span><span class="sxs-lookup"><span data-stu-id="bd11d-132">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="bd11d-133">有关详细信息，请参阅[运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="bd11d-133">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bd11d-134">子元素</span><span class="sxs-lookup"><span data-stu-id="bd11d-134">Child Elements</span></span>  
 <span data-ttu-id="bd11d-135">无。</span><span class="sxs-lookup"><span data-stu-id="bd11d-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bd11d-136">父元素</span><span class="sxs-lookup"><span data-stu-id="bd11d-136">Parent Elements</span></span>  
  
|<span data-ttu-id="bd11d-137">元素</span><span class="sxs-lookup"><span data-stu-id="bd11d-137">Element</span></span>|<span data-ttu-id="bd11d-138">描述</span><span class="sxs-lookup"><span data-stu-id="bd11d-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd11d-139">\<Type></span><span class="sxs-lookup"><span data-stu-id="bd11d-139">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="bd11d-140">将反射策略应用到一种类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="bd11d-140">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="bd11d-141">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="bd11d-141">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="bd11d-142">将反射策略应用到一种构造泛型类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="bd11d-142">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd11d-143">备注</span><span class="sxs-lookup"><span data-stu-id="bd11d-143">Remarks</span></span>  
 <span data-ttu-id="bd11d-144">如果一个事件的策略没有得到显式定义，它将继承其父元素的运行时策略。</span><span class="sxs-lookup"><span data-stu-id="bd11d-144">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd11d-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd11d-145">See also</span></span>

- [<span data-ttu-id="bd11d-146">运行时指令 (rd.xml) 配置文件引用</span><span class="sxs-lookup"><span data-stu-id="bd11d-146">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="bd11d-147">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="bd11d-147">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="bd11d-148">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="bd11d-148">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
