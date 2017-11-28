---
title: "&lt;暗示类型&gt;元素 (.NET Native)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3abd2071-0f28-40ba-b9a0-d52bd94cd2f6
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90e079b593ed124da79f5f87b5189d199bc4572a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltimpliestypegt-element-net-native"></a><span data-ttu-id="ff9e7-102">&lt;暗示类型&gt;元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="ff9e7-102">&lt;ImpliesType&gt; Element (.NET Native)</span></span>
<span data-ttu-id="ff9e7-103">如果该策略已应用到该包含类型或方法，将该策略应用到一个类型。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-103">Applies policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff9e7-104">语法</span><span class="sxs-lookup"><span data-stu-id="ff9e7-104">Syntax</span></span>  
  
```xml
<ImpliesType Name="type_name"  
             Activate="policy_type"  
             Browse="policy_type"  
             Dynamic="policy_type"  
             Serialize="policy_type"   
             DataContractSerializer="policy_setting"  
             DataContractJsonSerializer="policy_setting"  
             XmlSerializer="policy_setting"  
             MarshalObject="policy_setting"  
             MarshalDelegate="policy_setting"  
             MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff9e7-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ff9e7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ff9e7-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff9e7-107">特性</span><span class="sxs-lookup"><span data-stu-id="ff9e7-107">Attributes</span></span>  
  
|<span data-ttu-id="ff9e7-108">特性</span><span class="sxs-lookup"><span data-stu-id="ff9e7-108">Attribute</span></span>|<span data-ttu-id="ff9e7-109">特性类型</span><span class="sxs-lookup"><span data-stu-id="ff9e7-109">Attribute type</span></span>|<span data-ttu-id="ff9e7-110">描述</span><span class="sxs-lookup"><span data-stu-id="ff9e7-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="ff9e7-111">常规</span><span class="sxs-lookup"><span data-stu-id="ff9e7-111">General</span></span>|<span data-ttu-id="ff9e7-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-112">Required attribute.</span></span> <span data-ttu-id="ff9e7-113">指定类型名称。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-113">Specifies the type name.</span></span>|  
|`Activate`|<span data-ttu-id="ff9e7-114">映像</span><span class="sxs-lookup"><span data-stu-id="ff9e7-114">Reflection</span></span>|<span data-ttu-id="ff9e7-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-115">Optional attribute.</span></span> <span data-ttu-id="ff9e7-116">控制运行时对构造函数的访问，以启用实例激活。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="ff9e7-117">映像</span><span class="sxs-lookup"><span data-stu-id="ff9e7-117">Reflection</span></span>|<span data-ttu-id="ff9e7-118">可选特性。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-118">Optional attribute.</span></span> <span data-ttu-id="ff9e7-119">控制对有关程序元素信息的查询，但并不启用任何运行时访问。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-119">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="ff9e7-120">映像</span><span class="sxs-lookup"><span data-stu-id="ff9e7-120">Reflection</span></span>|<span data-ttu-id="ff9e7-121">可选特性。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-121">Optional attribute.</span></span> <span data-ttu-id="ff9e7-122">控制运行时对所有类型成员的访问，包括构造函数、方法、字段、属性和事件，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="ff9e7-123">序列化</span><span class="sxs-lookup"><span data-stu-id="ff9e7-123">Serialization</span></span>|<span data-ttu-id="ff9e7-124">可选特性。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-124">Optional attribute.</span></span> <span data-ttu-id="ff9e7-125">控制运行时对构造函数、字段和属性的访问，使类型实例得到序列化和反序列化处理，这是通过库进行的，例如 Newtonsoft JSON 序列化程序。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="ff9e7-126">序列化</span><span class="sxs-lookup"><span data-stu-id="ff9e7-126">Serialization</span></span>|<span data-ttu-id="ff9e7-127">可选特性。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-127">Optional attribute.</span></span> <span data-ttu-id="ff9e7-128">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 类的序列化策略。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="ff9e7-129">序列化</span><span class="sxs-lookup"><span data-stu-id="ff9e7-129">Serialization</span></span>|<span data-ttu-id="ff9e7-130">可选特性。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-130">Optional attribute.</span></span> <span data-ttu-id="ff9e7-131">控制使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 类的 JSON 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="ff9e7-132">序列化</span><span class="sxs-lookup"><span data-stu-id="ff9e7-132">Serialization</span></span>|<span data-ttu-id="ff9e7-133">可选特性。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-133">Optional attribute.</span></span> <span data-ttu-id="ff9e7-134">控制使用 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 类的 XML 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="ff9e7-135">Interop</span><span class="sxs-lookup"><span data-stu-id="ff9e7-135">Interop</span></span>|<span data-ttu-id="ff9e7-136">可选特性。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-136">Optional attribute.</span></span> <span data-ttu-id="ff9e7-137">控制封送引用类型到 Windows 运行时和 COM 的策略。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="ff9e7-138">Interop</span><span class="sxs-lookup"><span data-stu-id="ff9e7-138">Interop</span></span>|<span data-ttu-id="ff9e7-139">可选特性。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-139">Optional attribute.</span></span> <span data-ttu-id="ff9e7-140">控制将委托类型作为函数指针封送到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="ff9e7-141">Interop</span><span class="sxs-lookup"><span data-stu-id="ff9e7-141">Interop</span></span>|<span data-ttu-id="ff9e7-142">可选特性。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-142">Optional attribute.</span></span> <span data-ttu-id="ff9e7-143">控制封送处理值类型到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-143">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="ff9e7-144">Name 特性</span><span class="sxs-lookup"><span data-stu-id="ff9e7-144">Name attribute</span></span>  
  
|<span data-ttu-id="ff9e7-145">值</span><span class="sxs-lookup"><span data-stu-id="ff9e7-145">Value</span></span>|<span data-ttu-id="ff9e7-146">描述</span><span class="sxs-lookup"><span data-stu-id="ff9e7-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ff9e7-147">type_name</span><span class="sxs-lookup"><span data-stu-id="ff9e7-147">*type_name*</span></span>|<span data-ttu-id="ff9e7-148">类型名称。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-148">The type name.</span></span> <span data-ttu-id="ff9e7-149">如果此 `<ImpliesType>` 元素代表的类型同其包含的 `<Type>` 元素位于相同的命名空间，type_name 可能会包括类型名称而不包括其命名空间。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-149">If the type represented by this `<ImpliesType>` element is located in the same namespace as its containing `<Type>` element, *type_name* can include the name of the type without its namespace.</span></span> <span data-ttu-id="ff9e7-150">否则，type_name 必须包含完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-150">Otherwise, *type_name* must include the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="ff9e7-151">所有其他特性</span><span class="sxs-lookup"><span data-stu-id="ff9e7-151">All other attributes</span></span>  
  
|<span data-ttu-id="ff9e7-152">值</span><span class="sxs-lookup"><span data-stu-id="ff9e7-152">Value</span></span>|<span data-ttu-id="ff9e7-153">描述</span><span class="sxs-lookup"><span data-stu-id="ff9e7-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ff9e7-154">policy_setting</span><span class="sxs-lookup"><span data-stu-id="ff9e7-154">*policy_setting*</span></span>|<span data-ttu-id="ff9e7-155">该设置将应用到这种策略类型。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="ff9e7-156">可能值为 `All`、`Auto`、`Excluded`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal` 以及 `Required All`。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-156">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="ff9e7-157">有关详细信息，请参阅[运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff9e7-158">子元素</span><span class="sxs-lookup"><span data-stu-id="ff9e7-158">Child Elements</span></span>  
 <span data-ttu-id="ff9e7-159">无。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff9e7-160">父元素</span><span class="sxs-lookup"><span data-stu-id="ff9e7-160">Parent Elements</span></span>  
  
|<span data-ttu-id="ff9e7-161">元素</span><span class="sxs-lookup"><span data-stu-id="ff9e7-161">Element</span></span>|<span data-ttu-id="ff9e7-162">描述</span><span class="sxs-lookup"><span data-stu-id="ff9e7-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff9e7-163">\<Type></span><span class="sxs-lookup"><span data-stu-id="ff9e7-163">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="ff9e7-164">将反射策略应用到一种类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-164">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="ff9e7-165">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="ff9e7-165">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="ff9e7-166">将反射策略应用到一种构造泛型类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-166">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
|[<span data-ttu-id="ff9e7-167">\<Method></span><span class="sxs-lookup"><span data-stu-id="ff9e7-167">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="ff9e7-168">将反射策略应用到一个方法。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-168">Applies reflection policy to a method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff9e7-169">备注</span><span class="sxs-lookup"><span data-stu-id="ff9e7-169">Remarks</span></span>  
 <span data-ttu-id="ff9e7-170">该 `<ImpliesType>` 元素主要是供库使用的。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-170">The `<ImpliesType>` element is primarily intended for use by libraries.</span></span> <span data-ttu-id="ff9e7-171">它讨论的是以下情景：</span><span class="sxs-lookup"><span data-stu-id="ff9e7-171">It addresses the following scenario:</span></span>  
  
-   <span data-ttu-id="ff9e7-172">如果一个例程需要反射到一个类型，它必然也要反射到另一种类型。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-172">If a routine needs to reflect on one type, it necessarily needs to reflect on a second type.</span></span>  
  
-   <span data-ttu-id="ff9e7-173">否则，第二种类型的暗示的实例化元数据就不可用，因为静态分析没有指示这一步骤是必须的。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-173">The metadata for the implied instantiation of the second type is otherwise unavailable, because static analysis doesn't indicate that it's necessary.</span></span>  
  
 <span data-ttu-id="ff9e7-174">最常见的两种类型是附带共享类型参数的泛型实例化。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-174">Most commonly, the two types are generic instantiations with shared type arguments.</span></span>  
  
 <span data-ttu-id="ff9e7-175">对 `<ImpliesType>` 元素的定义是以一个假设为基础的，即如果需要反射到父元素指定的类型上暗示着也需要反射到 `<ImpliesType>` 元素指定的类型上。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-175">The `<ImpliesType>` element was defined with the assumption that a need for reflection on the type specified by its parent element implies a need for reflection on the type specified by the `<ImpliesType>` element.</span></span> <span data-ttu-id="ff9e7-176">例如，以下反射指令应用到两种类型，`Explicit<T>` 和 `Implicit<T>`。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-176">For example, the following reflection directives apply to two types, `Explicit<T>` and `Implicit<T>`.</span></span>  
  
```xml  
<Type Name="Explicit{ET}">  
    <ImpliesType Name="Implicit{ET}" Dynamic="Required Public" />  
</Type>  
```  
  
 <span data-ttu-id="ff9e7-177">这个指令是不起作用的，除非 `Explicit` 的一个实例化具有一个已定义的 `Dynamic` 策略设置。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-177">This directive has no effect unless an instantiation of `Explicit` has a defined `Dynamic` policy setting.</span></span> <span data-ttu-id="ff9e7-178">例如，如果对于 `Explicit<Int32>` 情况如此，`Implicit<Int32>` 会同其根公共成员一起被实例化，并且它们的元数据就能由动态编程访问。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-178">For example, if that's the case for `Explicit<Int32>`, `Implicit<Int32>` is instantiated with its public members rooted, and their metadata is made accessible for dynamic programming.</span></span>  
  
 <span data-ttu-id="ff9e7-179">以下是一个至少可以应用到序列化程序的实际实例。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-179">The following is a real-world example that applies to at least one serializer.</span></span> <span data-ttu-id="ff9e7-180">指令获得到的需求是，反射到 something 的 `IList<`*something*`>` 类型也需要反射到相应的 `List<`*something*`>` 类型，而不需要任何应用程序注释。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-180">The directives capture the requirement that reflecting on something typed as `IList<`*something*`>` also involves reflecting on the corresponding `List<`*something*`>` type without requiring any per-application annotation.</span></span>  
  
```xml  
<Type Name="System.Collections.Generic.IList{T}">  
   <ImpliesType Name="System.Collections.Generic.List{T}" Serialize="Public" />  
</Type>  
```  
  
 <span data-ttu-id="ff9e7-181">`<ImpliesType>` 元素也可能出现在 `<Method>` 元素内部，因为在某些情况下泛型方法暗示着反射到了一个类型实例化上。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-181">The `<ImpliesType>` element can also appear within a `<Method>` element, because in some cases instantiating a generic method implies reflecting on a type instantiation.</span></span> <span data-ttu-id="ff9e7-182">例如，想象一个特定的库可以动态访问的泛型方法 `IEnumerable<T> MakeEnumerable<T>(string` `spelling``, T` `defaultValue``)` 以及相关的 <xref:System.Collections.Generic.List%601> 和 <xref:System.Array> 类型。</span><span class="sxs-lookup"><span data-stu-id="ff9e7-182">For example, imagine a generic method `IEnumerable<T> MakeEnumerable<T>(string` `spelling``, T` `defaultValue``)` that a given library will access dynamically along with the associated <xref:System.Collections.Generic.List%601> and <xref:System.Array> types.</span></span> <span data-ttu-id="ff9e7-183">这可以表示为：</span><span class="sxs-lookup"><span data-stu-id="ff9e7-183">This can be expressed as:</span></span>  
  
```xml  
<Type Name="MyType">  
    <Method Name="MakeEnumerable{T}" Signature="(System.String, T)" Dynamic="Included">  
        <ImpliesType Name="T[]" Dynamic="Public" />  
        <ImpliesType Name="System.Collections.Generic.List{T}" Dynamic="Public">  
    </Method>  
</Type>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff9e7-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff9e7-184">See Also</span></span>  
 [<span data-ttu-id="ff9e7-185">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="ff9e7-185">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="ff9e7-186">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="ff9e7-186">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="ff9e7-187">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="ff9e7-187">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
