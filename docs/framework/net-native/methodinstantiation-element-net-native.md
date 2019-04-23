---
title: <MethodInstantiation>元素 (.NET Native)
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae15e6d61267feb0388170ee27dcd939035329b0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121688"
---
# <a name="methodinstantiation-element-net-native"></a><span data-ttu-id="46652-102">\<方法实例化 > 元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="46652-102">\<MethodInstantiation> Element (.NET Native)</span></span>
<span data-ttu-id="46652-103">将运行时反射策略应用到一个构造泛型方法。</span><span class="sxs-lookup"><span data-stu-id="46652-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46652-104">语法</span><span class="sxs-lookup"><span data-stu-id="46652-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46652-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="46652-105">Attributes and Elements</span></span>  
 <span data-ttu-id="46652-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="46652-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46652-107">特性</span><span class="sxs-lookup"><span data-stu-id="46652-107">Attributes</span></span>  
  
|<span data-ttu-id="46652-108">特性</span><span class="sxs-lookup"><span data-stu-id="46652-108">Attribute</span></span>|<span data-ttu-id="46652-109">特性类型</span><span class="sxs-lookup"><span data-stu-id="46652-109">Attribute type</span></span>|<span data-ttu-id="46652-110">描述</span><span class="sxs-lookup"><span data-stu-id="46652-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="46652-111">常规</span><span class="sxs-lookup"><span data-stu-id="46652-111">General</span></span>|<span data-ttu-id="46652-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="46652-112">Required attribute.</span></span> <span data-ttu-id="46652-113">指定方法名称。</span><span class="sxs-lookup"><span data-stu-id="46652-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="46652-114">常规</span><span class="sxs-lookup"><span data-stu-id="46652-114">General</span></span>|<span data-ttu-id="46652-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="46652-115">Optional attribute.</span></span> <span data-ttu-id="46652-116">指定该类型的命名参数。</span><span class="sxs-lookup"><span data-stu-id="46652-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="46652-117">多个命名参数由逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="46652-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="46652-118">`Signature` 特性用于区分重载方法。</span><span class="sxs-lookup"><span data-stu-id="46652-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="46652-119">常规</span><span class="sxs-lookup"><span data-stu-id="46652-119">General</span></span>|<span data-ttu-id="46652-120">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="46652-120">Required attribute.</span></span> <span data-ttu-id="46652-121">指定泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="46652-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="46652-122">如果存在多个自变量，它们之间用逗号分割。</span><span class="sxs-lookup"><span data-stu-id="46652-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="46652-123">映像</span><span class="sxs-lookup"><span data-stu-id="46652-123">Reflection</span></span>|<span data-ttu-id="46652-124">可选特性。</span><span class="sxs-lookup"><span data-stu-id="46652-124">Optional attribute.</span></span> <span data-ttu-id="46652-125">控制对该方法信息的查询或列举该方法，但并不在运行时间启用任何动态调用。</span><span class="sxs-lookup"><span data-stu-id="46652-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="46652-126">映像</span><span class="sxs-lookup"><span data-stu-id="46652-126">Reflection</span></span>|<span data-ttu-id="46652-127">可选特性。</span><span class="sxs-lookup"><span data-stu-id="46652-127">Optional attribute.</span></span> <span data-ttu-id="46652-128">控制运行时对构造函数或方法的访问，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="46652-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="46652-129">该策略确保一个成员可在运行时间内得到调用。</span><span class="sxs-lookup"><span data-stu-id="46652-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="46652-130">Name 特性</span><span class="sxs-lookup"><span data-stu-id="46652-130">Name attribute</span></span>  
  
|<span data-ttu-id="46652-131">“值”</span><span class="sxs-lookup"><span data-stu-id="46652-131">Value</span></span>|<span data-ttu-id="46652-132">描述</span><span class="sxs-lookup"><span data-stu-id="46652-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="46652-133">method_name</span><span class="sxs-lookup"><span data-stu-id="46652-133">*method_name*</span></span>|<span data-ttu-id="46652-134">方法名。</span><span class="sxs-lookup"><span data-stu-id="46652-134">The method name.</span></span> <span data-ttu-id="46652-135">该方法的类型是由 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 或 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 父元素定义的。</span><span class="sxs-lookup"><span data-stu-id="46652-135">The type of the method is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="46652-136">签名特性</span><span class="sxs-lookup"><span data-stu-id="46652-136">Signature attribute</span></span>  
  
|<span data-ttu-id="46652-137">“值”</span><span class="sxs-lookup"><span data-stu-id="46652-137">Value</span></span>|<span data-ttu-id="46652-138">描述</span><span class="sxs-lookup"><span data-stu-id="46652-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="46652-139">method_signature</span><span class="sxs-lookup"><span data-stu-id="46652-139">*method_signature*</span></span>|<span data-ttu-id="46652-140">指定该类型的命名参数。</span><span class="sxs-lookup"><span data-stu-id="46652-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="46652-141">如果存在多个参数，它们之间用逗号分割。</span><span class="sxs-lookup"><span data-stu-id="46652-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="46652-142">自变量特性</span><span class="sxs-lookup"><span data-stu-id="46652-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="46652-143">“值”</span><span class="sxs-lookup"><span data-stu-id="46652-143">Value</span></span>|<span data-ttu-id="46652-144">描述</span><span class="sxs-lookup"><span data-stu-id="46652-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="46652-145">method_arguments</span><span class="sxs-lookup"><span data-stu-id="46652-145">*method_arguments*</span></span>|<span data-ttu-id="46652-146">指定泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="46652-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="46652-147">如果存在多个自变量，它们之间用逗号分割。</span><span class="sxs-lookup"><span data-stu-id="46652-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="46652-148">每个自变量必须包含一个完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="46652-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="46652-149">所有其他特性</span><span class="sxs-lookup"><span data-stu-id="46652-149">All other attributes</span></span>  
  
|<span data-ttu-id="46652-150">“值”</span><span class="sxs-lookup"><span data-stu-id="46652-150">Value</span></span>|<span data-ttu-id="46652-151">描述</span><span class="sxs-lookup"><span data-stu-id="46652-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="46652-152">policy_setting</span><span class="sxs-lookup"><span data-stu-id="46652-152">*policy_setting*</span></span>|<span data-ttu-id="46652-153">该设置将应用到这个方法的策略类型。</span><span class="sxs-lookup"><span data-stu-id="46652-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="46652-154">可能值为 `Auto`、`Excluded`、`Included` 和 `Required`。</span><span class="sxs-lookup"><span data-stu-id="46652-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="46652-155">有关详细信息，请参阅[运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="46652-155">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46652-156">子元素</span><span class="sxs-lookup"><span data-stu-id="46652-156">Child Elements</span></span>  
 <span data-ttu-id="46652-157">无。</span><span class="sxs-lookup"><span data-stu-id="46652-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="46652-158">父元素</span><span class="sxs-lookup"><span data-stu-id="46652-158">Parent Elements</span></span>  
  
|<span data-ttu-id="46652-159">元素</span><span class="sxs-lookup"><span data-stu-id="46652-159">Element</span></span>|<span data-ttu-id="46652-160">描述</span><span class="sxs-lookup"><span data-stu-id="46652-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46652-161">\<Type></span><span class="sxs-lookup"><span data-stu-id="46652-161">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="46652-162">将反射策略应用到一种类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="46652-162">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="46652-163">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="46652-163">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="46652-164">将反射策略应用到一种构造泛型类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="46652-164">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46652-165">备注</span><span class="sxs-lookup"><span data-stu-id="46652-165">Remarks</span></span>  
 <span data-ttu-id="46652-166">`<MethodInstantiation>` 元素替代其相应的开发泛型方法的运行时反射策略。</span><span class="sxs-lookup"><span data-stu-id="46652-166">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46652-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="46652-167">See also</span></span>

- [<span data-ttu-id="46652-168">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="46652-168">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="46652-169">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="46652-169">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="46652-170">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="46652-170">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
- [<span data-ttu-id="46652-171">\<Method> 元素</span><span class="sxs-lookup"><span data-stu-id="46652-171">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)
