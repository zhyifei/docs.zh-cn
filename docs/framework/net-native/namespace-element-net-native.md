---
title: <Namespace>元素 (.NET Native)
ms.date: 03/30/2017
ms.assetid: 57c614e5-18a9-4e87-bfd5-d0fe3396a192
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7be004776d2a2fd3b4c41fb21b3ac244946f2166
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049418"
---
# <a name="namespace-element-net-native"></a><span data-ttu-id="e0dd3-102">\<命名空间 > 元素（.NET Native）</span><span class="sxs-lookup"><span data-stu-id="e0dd3-102">\<Namespace> Element (.NET Native)</span></span>
<span data-ttu-id="e0dd3-103">将运行时反射策略应用到一个指定的命名空间中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-103">Applies runtime reflection policy to all the types in a specified namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0dd3-104">语法</span><span class="sxs-lookup"><span data-stu-id="e0dd3-104">Syntax</span></span>  
  
```xml  
<Namespace Name="namespace_name"   
           Activate="policy_type"   
           Browse="policy_type"  
           Dynamic="policy_setting"  
           Serialize="policy_setting"  
           DataContractSerializer="policy_setting"  
           DataContractJsonSerializer="policy_setting"  
           XmlSerializer="policy_setting"  
           MarshalObject="policy_setting"  
           MarshalDelegate="policy_setting"  
           MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0dd3-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e0dd3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e0dd3-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0dd3-107">特性</span><span class="sxs-lookup"><span data-stu-id="e0dd3-107">Attributes</span></span>  
  
|<span data-ttu-id="e0dd3-108">特性</span><span class="sxs-lookup"><span data-stu-id="e0dd3-108">Attribute</span></span>|<span data-ttu-id="e0dd3-109">特性类型</span><span class="sxs-lookup"><span data-stu-id="e0dd3-109">Attribute type</span></span>|<span data-ttu-id="e0dd3-110">描述</span><span class="sxs-lookup"><span data-stu-id="e0dd3-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="e0dd3-111">常规</span><span class="sxs-lookup"><span data-stu-id="e0dd3-111">General</span></span>|<span data-ttu-id="e0dd3-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-112">Required attribute.</span></span> <span data-ttu-id="e0dd3-113">指定命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-113">Specifies the name of the namespace.</span></span>|  
|`Activate`|<span data-ttu-id="e0dd3-114">映像</span><span class="sxs-lookup"><span data-stu-id="e0dd3-114">Reflection</span></span>|<span data-ttu-id="e0dd3-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-115">Optional attribute.</span></span> <span data-ttu-id="e0dd3-116">控制运行时对构造函数的访问，以启用实例激活。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="e0dd3-117">映像</span><span class="sxs-lookup"><span data-stu-id="e0dd3-117">Reflection</span></span>|<span data-ttu-id="e0dd3-118">可选特性。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-118">Optional attribute.</span></span> <span data-ttu-id="e0dd3-119">控制对有关程序元素信息的查询，但并不启用任何运行时访问。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-119">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="e0dd3-120">映像</span><span class="sxs-lookup"><span data-stu-id="e0dd3-120">Reflection</span></span>|<span data-ttu-id="e0dd3-121">可选特性。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-121">Optional attribute.</span></span> <span data-ttu-id="e0dd3-122">控制运行时对所有类型成员的访问，包括构造函数、方法、字段、属性和事件，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="e0dd3-123">序列化</span><span class="sxs-lookup"><span data-stu-id="e0dd3-123">Serialization</span></span>|<span data-ttu-id="e0dd3-124">可选特性。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-124">Optional attribute.</span></span> <span data-ttu-id="e0dd3-125">控制运行时对构造函数、字段和属性的访问，使类型实例得到序列化和反序列化处理，这是通过库进行的，例如 Newtonsoft JSON 序列化程序。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="e0dd3-126">序列化</span><span class="sxs-lookup"><span data-stu-id="e0dd3-126">Serialization</span></span>|<span data-ttu-id="e0dd3-127">可选特性。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-127">Optional attribute.</span></span> <span data-ttu-id="e0dd3-128">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 类的序列化策略。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="e0dd3-129">序列化</span><span class="sxs-lookup"><span data-stu-id="e0dd3-129">Serialization</span></span>|<span data-ttu-id="e0dd3-130">可选特性。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-130">Optional attribute.</span></span> <span data-ttu-id="e0dd3-131">控制使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 类的 JSON 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="e0dd3-132">序列化</span><span class="sxs-lookup"><span data-stu-id="e0dd3-132">Serialization</span></span>|<span data-ttu-id="e0dd3-133">可选特性。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-133">Optional attribute.</span></span> <span data-ttu-id="e0dd3-134">控制使用 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 类的 XML 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="e0dd3-135">Interop</span><span class="sxs-lookup"><span data-stu-id="e0dd3-135">Interop</span></span>|<span data-ttu-id="e0dd3-136">可选特性。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-136">Optional attribute.</span></span> <span data-ttu-id="e0dd3-137">控制封送引用类型到 Windows 运行时和 COM 的策略。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="e0dd3-138">Interop</span><span class="sxs-lookup"><span data-stu-id="e0dd3-138">Interop</span></span>|<span data-ttu-id="e0dd3-139">可选特性。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-139">Optional attribute.</span></span> <span data-ttu-id="e0dd3-140">控制将委托类型作为函数指针封送到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="e0dd3-141">Interop</span><span class="sxs-lookup"><span data-stu-id="e0dd3-141">Interop</span></span>|<span data-ttu-id="e0dd3-142">可选特性。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-142">Optional attribute.</span></span> <span data-ttu-id="e0dd3-143">控制封送结构到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-143">Controls policy for marshaling structures to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="e0dd3-144">Name 特性</span><span class="sxs-lookup"><span data-stu-id="e0dd3-144">Name attribute</span></span>  
  
|<span data-ttu-id="e0dd3-145">值</span><span class="sxs-lookup"><span data-stu-id="e0dd3-145">Value</span></span>|<span data-ttu-id="e0dd3-146">描述</span><span class="sxs-lookup"><span data-stu-id="e0dd3-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e0dd3-147">namespace_name</span><span class="sxs-lookup"><span data-stu-id="e0dd3-147">*namespace_name*</span></span>|<span data-ttu-id="e0dd3-148">命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-148">The namespace name.</span></span> <span data-ttu-id="e0dd3-149">如果 \<Namespace> 元素是 [\<Application>](application-element-net-native.md)、[\<Library>](library-element-net-native.md) 或 [\<Assembly>](assembly-element-net-native.md) 元素的子元素，namespace_name 必须是一个完全限定的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-149">If the \<Namespace> element is a child of an [\<Application>](application-element-net-native.md), [\<Library>](library-element-net-native.md), or [\<Assembly>](assembly-element-net-native.md) element, *namespace_name* must be a fully qualified namespace name.</span></span> <span data-ttu-id="e0dd3-150">如果 \<Namespace> 元素是另一个 \<Namespace> 元素的子元素，则 namespace_name 必须是一个相对的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-150">If the \<Namespace> element is a child of another \<Namespace> element, *namespace_name* must be a relative namespace name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="e0dd3-151">所有其他特性</span><span class="sxs-lookup"><span data-stu-id="e0dd3-151">All other attributes</span></span>  
  
|<span data-ttu-id="e0dd3-152">值</span><span class="sxs-lookup"><span data-stu-id="e0dd3-152">Value</span></span>|<span data-ttu-id="e0dd3-153">描述</span><span class="sxs-lookup"><span data-stu-id="e0dd3-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e0dd3-154">policy_setting</span><span class="sxs-lookup"><span data-stu-id="e0dd3-154">*policy_setting*</span></span>|<span data-ttu-id="e0dd3-155">该设置将应用这个策略类型到该命名空间的所有类型。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-155">The setting to apply to this policy type for all types in the namespace.</span></span> <span data-ttu-id="e0dd3-156">可能值为 `All`、`Auto`、`Excluded`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal` 以及 `Required All`。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-156">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="e0dd3-157">有关详细信息，请参阅[运行时指令策略设置](runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0dd3-158">子元素</span><span class="sxs-lookup"><span data-stu-id="e0dd3-158">Child Elements</span></span>  
  
|<span data-ttu-id="e0dd3-159">元素</span><span class="sxs-lookup"><span data-stu-id="e0dd3-159">Element</span></span>|<span data-ttu-id="e0dd3-160">描述</span><span class="sxs-lookup"><span data-stu-id="e0dd3-160">Description</span></span>|  
|-------------|-----------------|  
|`<Namespace>`|<span data-ttu-id="e0dd3-161">将运行时反射策略应用到一个父命名空间中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-161">Applies runtime reflection policy to all types in a parent namespace.</span></span>|  
|[<span data-ttu-id="e0dd3-162">\<Type></span><span class="sxs-lookup"><span data-stu-id="e0dd3-162">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="e0dd3-163">将反射策略应用到一个类型。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-163">Applies reflection policy to a type.</span></span>|  
|[<span data-ttu-id="e0dd3-164">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="e0dd3-164">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="e0dd3-165">将反射策略应用到一个构造泛型类型。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-165">Applies reflection policy to a constructed generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e0dd3-166">父元素</span><span class="sxs-lookup"><span data-stu-id="e0dd3-166">Parent Elements</span></span>  
  
|<span data-ttu-id="e0dd3-167">元素</span><span class="sxs-lookup"><span data-stu-id="e0dd3-167">Element</span></span>|<span data-ttu-id="e0dd3-168">描述</span><span class="sxs-lookup"><span data-stu-id="e0dd3-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0dd3-169">\<Application></span><span class="sxs-lookup"><span data-stu-id="e0dd3-169">\<Application></span></span>](application-element-net-native.md)|<span data-ttu-id="e0dd3-170">作为应用程序范围内的类型和元数据可以反应在运行时间的类型成员的容器而服务。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-170">Serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="e0dd3-171">[\<Application>](application-element-net-native.md) 元素可包含零个、一个或多个 [\<Assembly>](assembly-element-net-native.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-171">The [\<Application>](application-element-net-native.md) element can have zero, one, or more [\<Assembly>](assembly-element-net-native.md) elements.</span></span>|  
|[<span data-ttu-id="e0dd3-172">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="e0dd3-172">\<Assembly></span></span>](assembly-element-net-native.md)|<span data-ttu-id="e0dd3-173">将运行时反射策略应用到指定程序集中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-173">Applies runtime reflection policy to all the types in a specified assembly.</span></span>|  
|[<span data-ttu-id="e0dd3-174">\<Library></span><span class="sxs-lookup"><span data-stu-id="e0dd3-174">\<Library></span></span>](library-element-net-native.md)|<span data-ttu-id="e0dd3-175">定义包含元数据在运行时间可以用于反射的类型和类型成员的程序集。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-175">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="e0dd3-176">[\<Library>](library-element-net-native.md) 元素可包含零个或一个 [\<Assembly>](assembly-element-net-native.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-176">The [\<Library>](library-element-net-native.md) element can have zero or one [\<Assembly>](assembly-element-net-native.md) element.</span></span>|  
|`<Namespace>`|<span data-ttu-id="e0dd3-177">将反射策略应用到一个父命名空间中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-177">Applies reflection policy to all types in a parent namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0dd3-178">备注</span><span class="sxs-lookup"><span data-stu-id="e0dd3-178">Remarks</span></span>  
 <span data-ttu-id="e0dd3-179">`Activate`、`Browse`、`Dynamic` 和 `Serialize` 特性都是可选项。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-179">The `Activate`, `Browse`, `Dynamic`, and `Serialize` attributes are all optional.</span></span> <span data-ttu-id="e0dd3-180">如果这些都不存在，`<Namespace>` 元素仅会充当子元素的容器。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-180">If none are present, the `<Namespace>` element serves only as a container for child elements.</span></span> <span data-ttu-id="e0dd3-181">如果它们存在，`<Namespace>` 元素会将运行时反射策略应用到一个指定的命名空间中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-181">If they are present, the `<Namespace>` element applies runtime reflection policy to all the types in the specified namespace.</span></span>  
  
 <span data-ttu-id="e0dd3-182">当它是 [\<Assembly>](assembly-element-net-native.md) 元素的子元素时，`<Namespace>` 元素会替代 [\<Assembly>](assembly-element-net-native.md) 元素定义的运行时反射策略。</span><span class="sxs-lookup"><span data-stu-id="e0dd3-182">When it is a child of the [\<Assembly>](assembly-element-net-native.md) element, the `<Namespace>` element overrides the runtime reflection policy defined by the  [\<Assembly>](assembly-element-net-native.md) element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0dd3-183">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0dd3-183">See also</span></span>

- [<span data-ttu-id="e0dd3-184">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="e0dd3-184">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="e0dd3-185">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="e0dd3-185">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="e0dd3-186">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="e0dd3-186">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
