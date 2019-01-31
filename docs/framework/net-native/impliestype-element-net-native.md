---
title: <ImpliesType>元素 (.NET Native)
ms.date: 03/30/2017
ms.assetid: 3abd2071-0f28-40ba-b9a0-d52bd94cd2f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1739c2a5e15d4c120d487c849819b6439afabade
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288010"
---
# <a name="impliestype-element-net-native"></a><span data-ttu-id="85d17-102">\<暗示类型 > 元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="85d17-102">\<ImpliesType> Element (.NET Native)</span></span>
<span data-ttu-id="85d17-103">如果该策略已应用到该包含类型或方法，将该策略应用到一个类型。</span><span class="sxs-lookup"><span data-stu-id="85d17-103">Applies policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85d17-104">语法</span><span class="sxs-lookup"><span data-stu-id="85d17-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85d17-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="85d17-105">Attributes and Elements</span></span>  
 <span data-ttu-id="85d17-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="85d17-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85d17-107">特性</span><span class="sxs-lookup"><span data-stu-id="85d17-107">Attributes</span></span>  
  
|<span data-ttu-id="85d17-108">特性</span><span class="sxs-lookup"><span data-stu-id="85d17-108">Attribute</span></span>|<span data-ttu-id="85d17-109">特性类型</span><span class="sxs-lookup"><span data-stu-id="85d17-109">Attribute type</span></span>|<span data-ttu-id="85d17-110">描述</span><span class="sxs-lookup"><span data-stu-id="85d17-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="85d17-111">常规</span><span class="sxs-lookup"><span data-stu-id="85d17-111">General</span></span>|<span data-ttu-id="85d17-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="85d17-112">Required attribute.</span></span> <span data-ttu-id="85d17-113">指定类型名称。</span><span class="sxs-lookup"><span data-stu-id="85d17-113">Specifies the type name.</span></span>|  
|`Activate`|<span data-ttu-id="85d17-114">映像</span><span class="sxs-lookup"><span data-stu-id="85d17-114">Reflection</span></span>|<span data-ttu-id="85d17-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="85d17-115">Optional attribute.</span></span> <span data-ttu-id="85d17-116">控制运行时对构造函数的访问，以启用实例激活。</span><span class="sxs-lookup"><span data-stu-id="85d17-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="85d17-117">映像</span><span class="sxs-lookup"><span data-stu-id="85d17-117">Reflection</span></span>|<span data-ttu-id="85d17-118">可选特性。</span><span class="sxs-lookup"><span data-stu-id="85d17-118">Optional attribute.</span></span> <span data-ttu-id="85d17-119">控制对有关程序元素信息的查询，但并不启用任何运行时访问。</span><span class="sxs-lookup"><span data-stu-id="85d17-119">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="85d17-120">映像</span><span class="sxs-lookup"><span data-stu-id="85d17-120">Reflection</span></span>|<span data-ttu-id="85d17-121">可选特性。</span><span class="sxs-lookup"><span data-stu-id="85d17-121">Optional attribute.</span></span> <span data-ttu-id="85d17-122">控制运行时对所有类型成员的访问，包括构造函数、方法、字段、属性和事件，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="85d17-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="85d17-123">序列化</span><span class="sxs-lookup"><span data-stu-id="85d17-123">Serialization</span></span>|<span data-ttu-id="85d17-124">可选特性。</span><span class="sxs-lookup"><span data-stu-id="85d17-124">Optional attribute.</span></span> <span data-ttu-id="85d17-125">控制运行时对构造函数、字段和属性的访问，使类型实例得到序列化和反序列化处理，这是通过库进行的，例如 Newtonsoft JSON 序列化程序。</span><span class="sxs-lookup"><span data-stu-id="85d17-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="85d17-126">序列化</span><span class="sxs-lookup"><span data-stu-id="85d17-126">Serialization</span></span>|<span data-ttu-id="85d17-127">可选特性。</span><span class="sxs-lookup"><span data-stu-id="85d17-127">Optional attribute.</span></span> <span data-ttu-id="85d17-128">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 类的序列化策略。</span><span class="sxs-lookup"><span data-stu-id="85d17-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="85d17-129">序列化</span><span class="sxs-lookup"><span data-stu-id="85d17-129">Serialization</span></span>|<span data-ttu-id="85d17-130">可选特性。</span><span class="sxs-lookup"><span data-stu-id="85d17-130">Optional attribute.</span></span> <span data-ttu-id="85d17-131">控制使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 类的 JSON 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="85d17-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="85d17-132">序列化</span><span class="sxs-lookup"><span data-stu-id="85d17-132">Serialization</span></span>|<span data-ttu-id="85d17-133">可选特性。</span><span class="sxs-lookup"><span data-stu-id="85d17-133">Optional attribute.</span></span> <span data-ttu-id="85d17-134">控制使用 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 类的 XML 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="85d17-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="85d17-135">Interop</span><span class="sxs-lookup"><span data-stu-id="85d17-135">Interop</span></span>|<span data-ttu-id="85d17-136">可选特性。</span><span class="sxs-lookup"><span data-stu-id="85d17-136">Optional attribute.</span></span> <span data-ttu-id="85d17-137">控制封送引用类型到 Windows 运行时和 COM 的策略。</span><span class="sxs-lookup"><span data-stu-id="85d17-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="85d17-138">Interop</span><span class="sxs-lookup"><span data-stu-id="85d17-138">Interop</span></span>|<span data-ttu-id="85d17-139">可选特性。</span><span class="sxs-lookup"><span data-stu-id="85d17-139">Optional attribute.</span></span> <span data-ttu-id="85d17-140">控制将委托类型作为函数指针封送到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="85d17-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="85d17-141">Interop</span><span class="sxs-lookup"><span data-stu-id="85d17-141">Interop</span></span>|<span data-ttu-id="85d17-142">可选特性。</span><span class="sxs-lookup"><span data-stu-id="85d17-142">Optional attribute.</span></span> <span data-ttu-id="85d17-143">控制封送处理值类型到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="85d17-143">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="85d17-144">Name 特性</span><span class="sxs-lookup"><span data-stu-id="85d17-144">Name attribute</span></span>  
  
|<span data-ttu-id="85d17-145">值</span><span class="sxs-lookup"><span data-stu-id="85d17-145">Value</span></span>|<span data-ttu-id="85d17-146">描述</span><span class="sxs-lookup"><span data-stu-id="85d17-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="85d17-147">type_name</span><span class="sxs-lookup"><span data-stu-id="85d17-147">*type_name*</span></span>|<span data-ttu-id="85d17-148">类型名称。</span><span class="sxs-lookup"><span data-stu-id="85d17-148">The type name.</span></span> <span data-ttu-id="85d17-149">如果此 `<ImpliesType>` 元素代表的类型同其包含的 `<Type>` 元素位于相同的命名空间，type_name 可能会包括类型名称而不包括其命名空间。</span><span class="sxs-lookup"><span data-stu-id="85d17-149">If the type represented by this `<ImpliesType>` element is located in the same namespace as its containing `<Type>` element, *type_name* can include the name of the type without its namespace.</span></span> <span data-ttu-id="85d17-150">否则，type_name 必须包含完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="85d17-150">Otherwise, *type_name* must include the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="85d17-151">所有其他特性</span><span class="sxs-lookup"><span data-stu-id="85d17-151">All other attributes</span></span>  
  
|<span data-ttu-id="85d17-152">值</span><span class="sxs-lookup"><span data-stu-id="85d17-152">Value</span></span>|<span data-ttu-id="85d17-153">描述</span><span class="sxs-lookup"><span data-stu-id="85d17-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="85d17-154">policy_setting</span><span class="sxs-lookup"><span data-stu-id="85d17-154">*policy_setting*</span></span>|<span data-ttu-id="85d17-155">该设置将应用到这种策略类型。</span><span class="sxs-lookup"><span data-stu-id="85d17-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="85d17-156">可能值为 `All`、`Auto`、`Excluded`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal` 以及 `Required All`。</span><span class="sxs-lookup"><span data-stu-id="85d17-156">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="85d17-157">有关详细信息，请参阅[运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="85d17-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85d17-158">子元素</span><span class="sxs-lookup"><span data-stu-id="85d17-158">Child Elements</span></span>  
 <span data-ttu-id="85d17-159">无。</span><span class="sxs-lookup"><span data-stu-id="85d17-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85d17-160">父元素</span><span class="sxs-lookup"><span data-stu-id="85d17-160">Parent Elements</span></span>  
  
|<span data-ttu-id="85d17-161">元素</span><span class="sxs-lookup"><span data-stu-id="85d17-161">Element</span></span>|<span data-ttu-id="85d17-162">描述</span><span class="sxs-lookup"><span data-stu-id="85d17-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85d17-163">\<Type></span><span class="sxs-lookup"><span data-stu-id="85d17-163">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="85d17-164">将反射策略应用到一种类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="85d17-164">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="85d17-165">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="85d17-165">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="85d17-166">将反射策略应用到一种构造泛型类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="85d17-166">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
|[<span data-ttu-id="85d17-167">\<Method></span><span class="sxs-lookup"><span data-stu-id="85d17-167">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="85d17-168">将反射策略应用到一个方法。</span><span class="sxs-lookup"><span data-stu-id="85d17-168">Applies reflection policy to a method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85d17-169">备注</span><span class="sxs-lookup"><span data-stu-id="85d17-169">Remarks</span></span>  
 <span data-ttu-id="85d17-170">该 `<ImpliesType>` 元素主要是供库使用的。</span><span class="sxs-lookup"><span data-stu-id="85d17-170">The `<ImpliesType>` element is primarily intended for use by libraries.</span></span> <span data-ttu-id="85d17-171">它讨论的是以下情景：</span><span class="sxs-lookup"><span data-stu-id="85d17-171">It addresses the following scenario:</span></span>  
  
-   <span data-ttu-id="85d17-172">如果一个例程需要反射到一个类型，它必然也要反射到另一种类型。</span><span class="sxs-lookup"><span data-stu-id="85d17-172">If a routine needs to reflect on one type, it necessarily needs to reflect on a second type.</span></span>  
  
-   <span data-ttu-id="85d17-173">否则，第二种类型的暗示的实例化元数据就不可用，因为静态分析没有指示这一步骤是必须的。</span><span class="sxs-lookup"><span data-stu-id="85d17-173">The metadata for the implied instantiation of the second type is otherwise unavailable, because static analysis doesn't indicate that it's necessary.</span></span>  
  
 <span data-ttu-id="85d17-174">最常见的两种类型是附带共享类型参数的泛型实例化。</span><span class="sxs-lookup"><span data-stu-id="85d17-174">Most commonly, the two types are generic instantiations with shared type arguments.</span></span>  
  
 <span data-ttu-id="85d17-175">对 `<ImpliesType>` 元素的定义是以一个假设为基础的，即如果需要反射到父元素指定的类型上暗示着也需要反射到 `<ImpliesType>` 元素指定的类型上。</span><span class="sxs-lookup"><span data-stu-id="85d17-175">The `<ImpliesType>` element was defined with the assumption that a need for reflection on the type specified by its parent element implies a need for reflection on the type specified by the `<ImpliesType>` element.</span></span> <span data-ttu-id="85d17-176">例如，以下反射指令应用到两种类型，`Explicit<T>` 和 `Implicit<T>`。</span><span class="sxs-lookup"><span data-stu-id="85d17-176">For example, the following reflection directives apply to two types, `Explicit<T>` and `Implicit<T>`.</span></span>  
  
```xml  
<Type Name="Explicit{ET}">  
    <ImpliesType Name="Implicit{ET}" Dynamic="Required Public" />  
</Type>  
```  
  
 <span data-ttu-id="85d17-177">这个指令是不起作用的，除非 `Explicit` 的一个实例化具有一个已定义的 `Dynamic` 策略设置。</span><span class="sxs-lookup"><span data-stu-id="85d17-177">This directive has no effect unless an instantiation of `Explicit` has a defined `Dynamic` policy setting.</span></span> <span data-ttu-id="85d17-178">例如，如果对于 `Explicit<Int32>` 情况如此，`Implicit<Int32>` 会同其根公共成员一起被实例化，并且它们的元数据就能由动态编程访问。</span><span class="sxs-lookup"><span data-stu-id="85d17-178">For example, if that's the case for `Explicit<Int32>`, `Implicit<Int32>` is instantiated with its public members rooted, and their metadata is made accessible for dynamic programming.</span></span>  
  
 <span data-ttu-id="85d17-179">以下是一个至少可以应用到序列化程序的实际实例。</span><span class="sxs-lookup"><span data-stu-id="85d17-179">The following is a real-world example that applies to at least one serializer.</span></span> <span data-ttu-id="85d17-180">指令获得到的需求是，反射到 something 的 `IList<`*something*`>` 类型也需要反射到相应的 `List<`*something*`>` 类型，而不需要任何应用程序注释。</span><span class="sxs-lookup"><span data-stu-id="85d17-180">The directives capture the requirement that reflecting on something typed as `IList<`*something*`>` also involves reflecting on the corresponding `List<`*something*`>` type without requiring any per-application annotation.</span></span>  
  
```xml  
<Type Name="System.Collections.Generic.IList{T}">  
   <ImpliesType Name="System.Collections.Generic.List{T}" Serialize="Public" />  
</Type>  
```  
  
 <span data-ttu-id="85d17-181">`<ImpliesType>` 元素也可能出现在 `<Method>` 元素内部，因为在某些情况下泛型方法暗示着反射到了一个类型实例化上。</span><span class="sxs-lookup"><span data-stu-id="85d17-181">The `<ImpliesType>` element can also appear within a `<Method>` element, because in some cases instantiating a generic method implies reflecting on a type instantiation.</span></span> <span data-ttu-id="85d17-182">例如，假设一个泛型方法`IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)`的给定的库可以动态访问以及相关<xref:System.Collections.Generic.List%601>和<xref:System.Array>类型。</span><span class="sxs-lookup"><span data-stu-id="85d17-182">For example, imagine a generic method `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` that a given library will access dynamically along with the associated <xref:System.Collections.Generic.List%601> and <xref:System.Array> types.</span></span> <span data-ttu-id="85d17-183">这可以表示为：</span><span class="sxs-lookup"><span data-stu-id="85d17-183">This can be expressed as:</span></span>  
  
```xml  
<Type Name="MyType">  
    <Method Name="MakeEnumerable{T}" Signature="(System.String, T)" Dynamic="Included">  
        <ImpliesType Name="T[]" Dynamic="Public" />  
        <ImpliesType Name="System.Collections.Generic.List{T}" Dynamic="Public">  
    </Method>  
</Type>  
```  
  
## <a name="see-also"></a><span data-ttu-id="85d17-184">请参阅</span><span class="sxs-lookup"><span data-stu-id="85d17-184">See also</span></span>
- [<span data-ttu-id="85d17-185">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="85d17-185">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="85d17-186">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="85d17-186">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="85d17-187">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="85d17-187">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
