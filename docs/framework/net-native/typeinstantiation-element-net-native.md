---
title: "&lt;类型实例化&gt;元素 (.NET Native)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5eada64-075b-4162-9655-ded84e4681f2
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 442970c8253147313a38e1a1518219a96ec41945
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="lttypeinstantiationgt-element-net-native"></a><span data-ttu-id="53d31-102">&lt;类型实例化&gt;元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="53d31-102">&lt;TypeInstantiation&gt; Element (.NET Native)</span></span>
<span data-ttu-id="53d31-103">将运行时反射策略应用到一个构造泛型类型。</span><span class="sxs-lookup"><span data-stu-id="53d31-103">Applies runtime reflection policy to a constructed generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53d31-104">语法</span><span class="sxs-lookup"><span data-stu-id="53d31-104">Syntax</span></span>  
  
```xml  
<TypeInstantiation Name="type_name"  
                   Arguments="type_arguments"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53d31-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="53d31-105">Attributes and Elements</span></span>  
 <span data-ttu-id="53d31-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="53d31-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53d31-107">特性</span><span class="sxs-lookup"><span data-stu-id="53d31-107">Attributes</span></span>  
  
|<span data-ttu-id="53d31-108">特性</span><span class="sxs-lookup"><span data-stu-id="53d31-108">Attribute</span></span>|<span data-ttu-id="53d31-109">特性类型</span><span class="sxs-lookup"><span data-stu-id="53d31-109">Attribute type</span></span>|<span data-ttu-id="53d31-110">描述</span><span class="sxs-lookup"><span data-stu-id="53d31-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="53d31-111">常规</span><span class="sxs-lookup"><span data-stu-id="53d31-111">General</span></span>|<span data-ttu-id="53d31-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="53d31-112">Required attribute.</span></span> <span data-ttu-id="53d31-113">指定类型名称。</span><span class="sxs-lookup"><span data-stu-id="53d31-113">Specifies the type name.</span></span>|  
|`Arguments`|<span data-ttu-id="53d31-114">常规</span><span class="sxs-lookup"><span data-stu-id="53d31-114">General</span></span>|<span data-ttu-id="53d31-115">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="53d31-115">Required attribute.</span></span> <span data-ttu-id="53d31-116">指定泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="53d31-116">Specifies the generic type arguments.</span></span> <span data-ttu-id="53d31-117">如果存在多个自变量，它们之间用逗号分割。</span><span class="sxs-lookup"><span data-stu-id="53d31-117">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Activate`|<span data-ttu-id="53d31-118">映像</span><span class="sxs-lookup"><span data-stu-id="53d31-118">Reflection</span></span>|<span data-ttu-id="53d31-119">可选特性。</span><span class="sxs-lookup"><span data-stu-id="53d31-119">Optional attribute.</span></span> <span data-ttu-id="53d31-120">控制运行时对构造函数的访问，以启用实例激活。</span><span class="sxs-lookup"><span data-stu-id="53d31-120">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="53d31-121">映像</span><span class="sxs-lookup"><span data-stu-id="53d31-121">Reflection</span></span>|<span data-ttu-id="53d31-122">可选特性。</span><span class="sxs-lookup"><span data-stu-id="53d31-122">Optional attribute.</span></span> <span data-ttu-id="53d31-123">控制对有关程序元素信息的查询，但并不启用任何运行时访问。</span><span class="sxs-lookup"><span data-stu-id="53d31-123">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="53d31-124">映像</span><span class="sxs-lookup"><span data-stu-id="53d31-124">Reflection</span></span>|<span data-ttu-id="53d31-125">可选特性。</span><span class="sxs-lookup"><span data-stu-id="53d31-125">Optional attribute.</span></span> <span data-ttu-id="53d31-126">控制运行时对所有类型成员的访问，包括构造函数、方法、字段、属性和事件，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="53d31-126">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="53d31-127">序列化</span><span class="sxs-lookup"><span data-stu-id="53d31-127">Serialization</span></span>|<span data-ttu-id="53d31-128">可选特性。</span><span class="sxs-lookup"><span data-stu-id="53d31-128">Optional attribute.</span></span> <span data-ttu-id="53d31-129">控制运行时对构造函数、字段和属性的访问，使类型实例得到序列化和反序列化处理，这是通过库进行的，例如 Newtonsoft JSON 序列化程序。</span><span class="sxs-lookup"><span data-stu-id="53d31-129">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="53d31-130">序列化</span><span class="sxs-lookup"><span data-stu-id="53d31-130">Serialization</span></span>|<span data-ttu-id="53d31-131">可选特性。</span><span class="sxs-lookup"><span data-stu-id="53d31-131">Optional attribute.</span></span> <span data-ttu-id="53d31-132">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 类的序列化策略。</span><span class="sxs-lookup"><span data-stu-id="53d31-132">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="53d31-133">序列化</span><span class="sxs-lookup"><span data-stu-id="53d31-133">Serialization</span></span>|<span data-ttu-id="53d31-134">可选特性。</span><span class="sxs-lookup"><span data-stu-id="53d31-134">Optional attribute.</span></span> <span data-ttu-id="53d31-135">控制使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 类的 JSON 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="53d31-135">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="53d31-136">序列化</span><span class="sxs-lookup"><span data-stu-id="53d31-136">Serialization</span></span>|<span data-ttu-id="53d31-137">可选特性。</span><span class="sxs-lookup"><span data-stu-id="53d31-137">Optional attribute.</span></span> <span data-ttu-id="53d31-138">控制使用 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 类的 XML 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="53d31-138">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="53d31-139">Interop</span><span class="sxs-lookup"><span data-stu-id="53d31-139">Interop</span></span>|<span data-ttu-id="53d31-140">可选特性。</span><span class="sxs-lookup"><span data-stu-id="53d31-140">Optional attribute.</span></span> <span data-ttu-id="53d31-141">控制封送引用类型到 Windows 运行时和 COM 的策略。</span><span class="sxs-lookup"><span data-stu-id="53d31-141">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="53d31-142">Interop</span><span class="sxs-lookup"><span data-stu-id="53d31-142">Interop</span></span>|<span data-ttu-id="53d31-143">可选特性。</span><span class="sxs-lookup"><span data-stu-id="53d31-143">Optional attribute.</span></span> <span data-ttu-id="53d31-144">控制将委托类型作为函数指针封送到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="53d31-144">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="53d31-145">Interop</span><span class="sxs-lookup"><span data-stu-id="53d31-145">Interop</span></span>|<span data-ttu-id="53d31-146">可选特性。</span><span class="sxs-lookup"><span data-stu-id="53d31-146">Optional attribute.</span></span> <span data-ttu-id="53d31-147">控制封送结构到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="53d31-147">Controls policy for marshaling structures to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="53d31-148">Name 特性</span><span class="sxs-lookup"><span data-stu-id="53d31-148">Name attribute</span></span>  
  
|<span data-ttu-id="53d31-149">值</span><span class="sxs-lookup"><span data-stu-id="53d31-149">Value</span></span>|<span data-ttu-id="53d31-150">描述</span><span class="sxs-lookup"><span data-stu-id="53d31-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="53d31-151">type_name</span><span class="sxs-lookup"><span data-stu-id="53d31-151">*type_name*</span></span>|<span data-ttu-id="53d31-152">类型名称。</span><span class="sxs-lookup"><span data-stu-id="53d31-152">The type name.</span></span> <span data-ttu-id="53d31-153">如果该 `<TypeInstantiation>` 元素是 [\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md) 元素、[\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 元素或另一个 `<TypeInstantiation>` 元素的子元素，type_name 可以指定类型名称而不包括其命名空间。</span><span class="sxs-lookup"><span data-stu-id="53d31-153">If this `<TypeInstantiation>` element is the child of a [\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md) element, a [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element, or another `<TypeInstantiation>` element, *type_name* can specify the name of the type without its namespace.</span></span> <span data-ttu-id="53d31-154">否则，type_name 必须包含完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="53d31-154">Otherwise, *type_name* must include the fully qualified type name.</span></span> <span data-ttu-id="53d31-155">该类型名称没有经过修饰。</span><span class="sxs-lookup"><span data-stu-id="53d31-155">The type name isn't decorated.</span></span> <span data-ttu-id="53d31-156">例如，对于一个 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> 对象，`<TypeInstantiation>` 元素可能显示如下：</span><span class="sxs-lookup"><span data-stu-id="53d31-156">For example, for a <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> object, the `<TypeInstantiation>` element might appear as follows:</span></span><br /><br /> `\<TypeInstantiation Name=System.Collections.Generic.List Dynamic="Required Public" />`|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="53d31-157">参数特性</span><span class="sxs-lookup"><span data-stu-id="53d31-157">Arguments attribute</span></span>  
  
|<span data-ttu-id="53d31-158">值</span><span class="sxs-lookup"><span data-stu-id="53d31-158">Value</span></span>|<span data-ttu-id="53d31-159">描述</span><span class="sxs-lookup"><span data-stu-id="53d31-159">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="53d31-160">type_argument</span><span class="sxs-lookup"><span data-stu-id="53d31-160">*type_argument*</span></span>|<span data-ttu-id="53d31-161">指定泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="53d31-161">Specifies the generic type arguments.</span></span> <span data-ttu-id="53d31-162">如果存在多个参数，它们之间用逗号分割。</span><span class="sxs-lookup"><span data-stu-id="53d31-162">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="53d31-163">每个参数必须包含一个完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="53d31-163">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="53d31-164">所有其他特性</span><span class="sxs-lookup"><span data-stu-id="53d31-164">All other attributes</span></span>  
  
|<span data-ttu-id="53d31-165">值</span><span class="sxs-lookup"><span data-stu-id="53d31-165">Value</span></span>|<span data-ttu-id="53d31-166">描述</span><span class="sxs-lookup"><span data-stu-id="53d31-166">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="53d31-167">policy_setting</span><span class="sxs-lookup"><span data-stu-id="53d31-167">*policy_setting*</span></span>|<span data-ttu-id="53d31-168">该设置将应用到这个构造泛型类型的策略类型。</span><span class="sxs-lookup"><span data-stu-id="53d31-168">The setting to apply to this policy type for the constructed generic type.</span></span> <span data-ttu-id="53d31-169">可能值为 `All`、`Auto`、`Excluded`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal` 以及 `Required All`。</span><span class="sxs-lookup"><span data-stu-id="53d31-169">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="53d31-170">有关详细信息，请参阅[运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="53d31-170">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53d31-171">子元素</span><span class="sxs-lookup"><span data-stu-id="53d31-171">Child Elements</span></span>  
  
|<span data-ttu-id="53d31-172">元素</span><span class="sxs-lookup"><span data-stu-id="53d31-172">Element</span></span>|<span data-ttu-id="53d31-173">描述</span><span class="sxs-lookup"><span data-stu-id="53d31-173">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53d31-174">\<Event></span><span class="sxs-lookup"><span data-stu-id="53d31-174">\<Event></span></span>](../../../docs/framework/net-native/event-element-net-native.md)|<span data-ttu-id="53d31-175">将反射策略应用到属于这种类型的一个事件。</span><span class="sxs-lookup"><span data-stu-id="53d31-175">Applies reflection policy to an event belonging to this type.</span></span>|  
|[<span data-ttu-id="53d31-176">\<Field></span><span class="sxs-lookup"><span data-stu-id="53d31-176">\<Field></span></span>](../../../docs/framework/net-native/field-element-net-native.md)|<span data-ttu-id="53d31-177">将反射策略应用到属于这种类型的一个字段。</span><span class="sxs-lookup"><span data-stu-id="53d31-177">Applies reflection policy to a field belonging to this type.</span></span>|  
|[<span data-ttu-id="53d31-178">\<ImpliesType></span><span class="sxs-lookup"><span data-stu-id="53d31-178">\<ImpliesType></span></span>](../../../docs/framework/net-native/impliestype-element-net-native.md)|<span data-ttu-id="53d31-179">如果该策略已应用到以包含 `<TypeInstantiation>` 元素为代表的类型，将该策略应用到一个类型。</span><span class="sxs-lookup"><span data-stu-id="53d31-179">Applies policy to a type, if that policy has been applied to the type represented by the containing `<TypeInstantiation>` element.</span></span>|  
|[<span data-ttu-id="53d31-180">\<Method></span><span class="sxs-lookup"><span data-stu-id="53d31-180">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="53d31-181">将反射策略应用到属于这种类型的一个方法。</span><span class="sxs-lookup"><span data-stu-id="53d31-181">Applies reflection policy to a method belonging to this type.</span></span>|  
|[<span data-ttu-id="53d31-182">\<MethodInstantiation></span><span class="sxs-lookup"><span data-stu-id="53d31-182">\<MethodInstantiation></span></span>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)|<span data-ttu-id="53d31-183">将反射策略应用到属于这种类型的一个构造泛型方法。</span><span class="sxs-lookup"><span data-stu-id="53d31-183">Applies reflection policy to a constructed generic method belonging to this type.</span></span>|  
|[<span data-ttu-id="53d31-184">\<Property></span><span class="sxs-lookup"><span data-stu-id="53d31-184">\<Property></span></span>](../../../docs/framework/net-native/property-element-net-native.md)|<span data-ttu-id="53d31-185">将反射策略应用到属于这种类型的一个属性。</span><span class="sxs-lookup"><span data-stu-id="53d31-185">Applies reflection policy to a property belonging to this type.</span></span>|  
|[<span data-ttu-id="53d31-186">\<Type></span><span class="sxs-lookup"><span data-stu-id="53d31-186">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="53d31-187">将反射策略应用到一个嵌套类型。</span><span class="sxs-lookup"><span data-stu-id="53d31-187">Applies reflection policy to a nested type.</span></span>|  
|`<TypeInstantiation>`|<span data-ttu-id="53d31-188">将反射策略应用到一个嵌套的构造泛型类型。</span><span class="sxs-lookup"><span data-stu-id="53d31-188">Applies reflection policy to a nested constructed generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="53d31-189">父元素</span><span class="sxs-lookup"><span data-stu-id="53d31-189">Parent Elements</span></span>  
  
|<span data-ttu-id="53d31-190">元素</span><span class="sxs-lookup"><span data-stu-id="53d31-190">Element</span></span>|<span data-ttu-id="53d31-191">描述</span><span class="sxs-lookup"><span data-stu-id="53d31-191">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53d31-192">\<Application></span><span class="sxs-lookup"><span data-stu-id="53d31-192">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="53d31-193">作为应用程序范围内的类型和元数据可以反应在运行时间的类型成员的容器而服务。</span><span class="sxs-lookup"><span data-stu-id="53d31-193">Serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span>|  
|[<span data-ttu-id="53d31-194">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="53d31-194">\<Assembly></span></span>](../../../docs/framework/net-native/assembly-element-net-native.md)|<span data-ttu-id="53d31-195">将反射策略应用到指定程序集中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="53d31-195">Applies reflection policy to all the types in a specified assembly.</span></span>|  
|[<span data-ttu-id="53d31-196">\<Library></span><span class="sxs-lookup"><span data-stu-id="53d31-196">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="53d31-197">定义包含元数据在运行时间可以用于反射的类型和类型成员的程序集。</span><span class="sxs-lookup"><span data-stu-id="53d31-197">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>|  
|[<span data-ttu-id="53d31-198">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="53d31-198">\<Namespace></span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)|<span data-ttu-id="53d31-199">将反射策略应用到命名空间中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="53d31-199">Applies reflection policy to all the types in a namespace.</span></span>|  
|[<span data-ttu-id="53d31-200">\<Type></span><span class="sxs-lookup"><span data-stu-id="53d31-200">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="53d31-201">将反射策略应用到一种类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="53d31-201">Applies reflection policy to a type and all its members.</span></span>|  
|`<TypeInstantiation>`|<span data-ttu-id="53d31-202">将反射策略应用到一种构造泛型类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="53d31-202">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53d31-203">备注</span><span class="sxs-lookup"><span data-stu-id="53d31-203">Remarks</span></span>  
 <span data-ttu-id="53d31-204">反射、序列化和互操作特性都是可选项。</span><span class="sxs-lookup"><span data-stu-id="53d31-204">The reflection, serialization, and interop attributes are all optional.</span></span> <span data-ttu-id="53d31-205">然而，至少一个特性必须存在。</span><span class="sxs-lookup"><span data-stu-id="53d31-205">However, at least one must be present.</span></span>  
  
 <span data-ttu-id="53d31-206">如果 `<TypeInstantiation>` 元素是 [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)、[\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md)、或 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 元素的子元素，它会重写由父元素定义的策略设置。</span><span class="sxs-lookup"><span data-stu-id="53d31-206">If a `<TypeInstantiation>` element is the child of an [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md), [\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md), or [\<Type>](../../../docs/framework/net-native/type-element-net-native.md), element, it overrides the policy settings defined by the parent element.</span></span> <span data-ttu-id="53d31-207">如果 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 元素定义了相应的泛型类型定义，`<TypeInstantiation>` 元素只为指定构造泛型类型的实例化重写运行时反射策略。</span><span class="sxs-lookup"><span data-stu-id="53d31-207">If a [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element defines a corresponding generic type definition, the `<TypeInstantiation>` element overrides runtime reflection policy only for instantiations of the specified constructed generic type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53d31-208">示例</span><span class="sxs-lookup"><span data-stu-id="53d31-208">Example</span></span>  
 <span data-ttu-id="53d31-209">以下实例使用反射从一个构造的 <xref:System.Collections.Generic.Dictionary%602> 对象取回了泛型类型定义。</span><span class="sxs-lookup"><span data-stu-id="53d31-209">The following example uses reflection to retrieve the generic type definition from a constructed <xref:System.Collections.Generic.Dictionary%602> object.</span></span> <span data-ttu-id="53d31-210">它还使用反射显示了代表构造泛型类型和构造类型定义的有关 <xref:System.Type> 对象的信息。</span><span class="sxs-lookup"><span data-stu-id="53d31-210">It also uses reflection to display information about <xref:System.Type> objects that represent constructed generic types and generic type definitions.</span></span> <span data-ttu-id="53d31-211">示例中的变量 `b` 是 [TextBlock](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx) 控件。</span><span class="sxs-lookup"><span data-stu-id="53d31-211">The variable `b` in the example is a [TextBlock](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx) control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/makegenerictype1.cs#2)]  
  
 <span data-ttu-id="53d31-212">在同 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 工具链进行编译后，该示例在调用 <xref:System.Type.GetGenericTypeDefinition%2A?displayProperty=nameWithType> 方法的行中引发 [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) 异常。</span><span class="sxs-lookup"><span data-stu-id="53d31-212">After compilation with the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain, the example throws a [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) exception on the line that calls the <xref:System.Type.GetGenericTypeDefinition%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="53d31-213">你可通过将以下 `<TypeInstantiation>` 元素添加到运行时指令文件来消除异常并提供必需的元数据：</span><span class="sxs-lookup"><span data-stu-id="53d31-213">You can eliminate the exception and provide the necessary metadata by adding the following `<TypeInstantiation>` element to the runtime directives file:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
    <Assembly Name="*Application*" Dynamic="Required All" />  
     <TypeInstantiation Name="System.Collections.Generic.Dictionary"  
                        Arguments="System.String,GenericType.Example"  
                        Dynamic="Required Public" />  
  </Application>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="53d31-214">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53d31-214">See Also</span></span>  
 [<span data-ttu-id="53d31-215">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="53d31-215">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="53d31-216">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="53d31-216">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="53d31-217">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="53d31-217">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
