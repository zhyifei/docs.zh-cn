---
title: "&lt;Field&gt; 元素 (.NET Native)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ef073004b213ee03ce9655096f612acb5750684
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltfieldgt-element-net-native"></a><span data-ttu-id="796e1-102">&lt;Field&gt; 元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="796e1-102">&lt;Field&gt; Element (.NET Native)</span></span>
<span data-ttu-id="796e1-103">将运行时反射策略应用到一个字段。</span><span class="sxs-lookup"><span data-stu-id="796e1-103">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="796e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="796e1-104">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="796e1-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="796e1-105">Attributes and Elements</span></span>  
 <span data-ttu-id="796e1-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="796e1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="796e1-107">特性</span><span class="sxs-lookup"><span data-stu-id="796e1-107">Attributes</span></span>  
  
|<span data-ttu-id="796e1-108">特性</span><span class="sxs-lookup"><span data-stu-id="796e1-108">Attribute</span></span>|<span data-ttu-id="796e1-109">特性类型</span><span class="sxs-lookup"><span data-stu-id="796e1-109">Attribute type</span></span>|<span data-ttu-id="796e1-110">描述</span><span class="sxs-lookup"><span data-stu-id="796e1-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="796e1-111">常规</span><span class="sxs-lookup"><span data-stu-id="796e1-111">General</span></span>|<span data-ttu-id="796e1-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="796e1-112">Required attribute.</span></span> <span data-ttu-id="796e1-113">指定字段名称。</span><span class="sxs-lookup"><span data-stu-id="796e1-113">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="796e1-114">映像</span><span class="sxs-lookup"><span data-stu-id="796e1-114">Reflection</span></span>|<span data-ttu-id="796e1-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="796e1-115">Optional attribute.</span></span> <span data-ttu-id="796e1-116">控制对该字段信息的查询或列举该字段，但并不在运行时间启用任何动态访问。</span><span class="sxs-lookup"><span data-stu-id="796e1-116">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="796e1-117">映像</span><span class="sxs-lookup"><span data-stu-id="796e1-117">Reflection</span></span>|<span data-ttu-id="796e1-118">可选特性。</span><span class="sxs-lookup"><span data-stu-id="796e1-118">Optional attribute.</span></span> <span data-ttu-id="796e1-119">控制运行时对该字段的访问，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="796e1-119">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="796e1-120">该策略确保一个字段可在运行时间内得到设置或动态检索。</span><span class="sxs-lookup"><span data-stu-id="796e1-120">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="796e1-121">序列化</span><span class="sxs-lookup"><span data-stu-id="796e1-121">Serialization</span></span>|<span data-ttu-id="796e1-122">可选特性。</span><span class="sxs-lookup"><span data-stu-id="796e1-122">Optional attribute.</span></span> <span data-ttu-id="796e1-123">控制运行时对一个字段的访问以启用类型实例，使其通过程序库得到序列化，例如通过 Newtonsoft JSON 序列化程序，或被用于绑定数据。</span><span class="sxs-lookup"><span data-stu-id="796e1-123">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="796e1-124">Name 特性</span><span class="sxs-lookup"><span data-stu-id="796e1-124">Name attribute</span></span>  
  
|<span data-ttu-id="796e1-125">值</span><span class="sxs-lookup"><span data-stu-id="796e1-125">Value</span></span>|<span data-ttu-id="796e1-126">描述</span><span class="sxs-lookup"><span data-stu-id="796e1-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="796e1-127">method_name</span><span class="sxs-lookup"><span data-stu-id="796e1-127">*method_name*</span></span>|<span data-ttu-id="796e1-128">字段名。</span><span class="sxs-lookup"><span data-stu-id="796e1-128">The field name.</span></span> <span data-ttu-id="796e1-129">该字段的类型是由 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 或 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 父元素定义的。</span><span class="sxs-lookup"><span data-stu-id="796e1-129">The type of the field is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="796e1-130">所有其他特性</span><span class="sxs-lookup"><span data-stu-id="796e1-130">All other attributes</span></span>  
  
|<span data-ttu-id="796e1-131">值</span><span class="sxs-lookup"><span data-stu-id="796e1-131">Value</span></span>|<span data-ttu-id="796e1-132">描述</span><span class="sxs-lookup"><span data-stu-id="796e1-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="796e1-133">policy_setting</span><span class="sxs-lookup"><span data-stu-id="796e1-133">*policy_setting*</span></span>|<span data-ttu-id="796e1-134">该设置将应用到这个字段的策略类型。</span><span class="sxs-lookup"><span data-stu-id="796e1-134">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="796e1-135">可能值为 `Auto`、`Excluded`、`Included` 和 `Required`。</span><span class="sxs-lookup"><span data-stu-id="796e1-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="796e1-136">有关详细信息，请参阅[运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="796e1-136">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="796e1-137">子元素</span><span class="sxs-lookup"><span data-stu-id="796e1-137">Child Elements</span></span>  
 <span data-ttu-id="796e1-138">无。</span><span class="sxs-lookup"><span data-stu-id="796e1-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="796e1-139">父元素</span><span class="sxs-lookup"><span data-stu-id="796e1-139">Parent Elements</span></span>  
  
|<span data-ttu-id="796e1-140">元素</span><span class="sxs-lookup"><span data-stu-id="796e1-140">Element</span></span>|<span data-ttu-id="796e1-141">描述</span><span class="sxs-lookup"><span data-stu-id="796e1-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="796e1-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="796e1-142">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="796e1-143">将反射策略应用到一种类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="796e1-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="796e1-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="796e1-144">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="796e1-145">将反射策略应用到一种构造泛型类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="796e1-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="796e1-146">备注</span><span class="sxs-lookup"><span data-stu-id="796e1-146">Remarks</span></span>  
 <span data-ttu-id="796e1-147">如果一个字段的策略没有得到显式定义，它将继承其父元素的运行时策略。</span><span class="sxs-lookup"><span data-stu-id="796e1-147">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="796e1-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="796e1-148">See Also</span></span>  
 [<span data-ttu-id="796e1-149">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="796e1-149">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="796e1-150">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="796e1-150">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="796e1-151">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="796e1-151">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
