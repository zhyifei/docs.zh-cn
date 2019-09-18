---
title: <Application>元素 (.NET Native)
ms.date: 03/30/2017
ms.assetid: b4e9b37a-059b-4076-8f56-cb3f9cef0cd9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2183a64f4e30a5188940abd5108a7ca1bddfe120
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049935"
---
# <a name="application-element-net-native"></a><span data-ttu-id="c0350-102">\<应用程序 > 元素（.NET Native）</span><span class="sxs-lookup"><span data-stu-id="c0350-102">\<Application> Element (.NET Native)</span></span>
<span data-ttu-id="c0350-103">作为应用程序范围内的类型和元数据可以反应在运行时间的类型成员的容器而服务，并将运行时反射策略应用到一个应用的所有程序元素。</span><span class="sxs-lookup"><span data-stu-id="c0350-103">Serves as a container for application-wide types and type members whose metadata is available for reflection at run time, and applies runtime reflection policy to all the program elements in an app.</span></span>  
  
 <span data-ttu-id="c0350-104">\<Directives> 元素</span><span class="sxs-lookup"><span data-stu-id="c0350-104">\<Directives> Element</span></span>  
<span data-ttu-id="c0350-105">\<Application> 元素 (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="c0350-105">\<Application> Element (rd.xml)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0350-106">语法</span><span class="sxs-lookup"><span data-stu-id="c0350-106">Syntax</span></span>  
  
```xml  
<Application Activate="policy_setting"  
             Browse="policy_setting"  
             Dynamic="policy_setting"  
             Serialize="policy_setting"  
             DataContractSerializer="policy_setting"  
             DataContractJsonSerializer="policy_setting"  
             XmlSerializer="policy_setting"  
             MarshalObject="policy_setting"  
             MarshalDelegate="policy_setting"  
             MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0350-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c0350-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c0350-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c0350-108">The following sections describe attributes, child elements, and parent elements.</span></span> <span data-ttu-id="c0350-109">在子元素表格中，策略指向在运行时间针对特定程序元素可用的一类元数据。</span><span class="sxs-lookup"><span data-stu-id="c0350-109">In the Child Elements table, policy refers to the kind of metadata that is made available for particular program elements at run time.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0350-110">特性</span><span class="sxs-lookup"><span data-stu-id="c0350-110">Attributes</span></span>  
  
|<span data-ttu-id="c0350-111">特性</span><span class="sxs-lookup"><span data-stu-id="c0350-111">Attribute</span></span>|<span data-ttu-id="c0350-112">特性类型</span><span class="sxs-lookup"><span data-stu-id="c0350-112">Attribute type</span></span>|<span data-ttu-id="c0350-113">描述</span><span class="sxs-lookup"><span data-stu-id="c0350-113">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="c0350-114">映像</span><span class="sxs-lookup"><span data-stu-id="c0350-114">Reflection</span></span>|<span data-ttu-id="c0350-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="c0350-115">Optional attribute.</span></span> <span data-ttu-id="c0350-116">控制运行时对构造函数的访问，以启用实例激活。</span><span class="sxs-lookup"><span data-stu-id="c0350-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="c0350-117">映像</span><span class="sxs-lookup"><span data-stu-id="c0350-117">Reflection</span></span>|<span data-ttu-id="c0350-118">可选特性。</span><span class="sxs-lookup"><span data-stu-id="c0350-118">Optional attribute.</span></span> <span data-ttu-id="c0350-119">控制对该类型信息的查询或列举该类型，但并不在运行时间启用任何动态访问。</span><span class="sxs-lookup"><span data-stu-id="c0350-119">Controls querying for information about or enumerating the types, but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="c0350-120">映像</span><span class="sxs-lookup"><span data-stu-id="c0350-120">Reflection</span></span>|<span data-ttu-id="c0350-121">可选特性。</span><span class="sxs-lookup"><span data-stu-id="c0350-121">Optional attribute.</span></span> <span data-ttu-id="c0350-122">控制运行时对所有类型成员的访问，包括构造函数、方法、字段、属性和事件，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="c0350-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="c0350-123">序列化</span><span class="sxs-lookup"><span data-stu-id="c0350-123">Serialization</span></span>|<span data-ttu-id="c0350-124">可选特性。</span><span class="sxs-lookup"><span data-stu-id="c0350-124">Optional attribute.</span></span> <span data-ttu-id="c0350-125">控制运行时对构造函数、字段和属性的访问，使类型实例得到序列化和反序列化处理，这是通过库进行的，例如 Newtonsoft JSON 序列化程序。</span><span class="sxs-lookup"><span data-stu-id="c0350-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="c0350-126">序列化</span><span class="sxs-lookup"><span data-stu-id="c0350-126">Serialization</span></span>|<span data-ttu-id="c0350-127">可选特性。</span><span class="sxs-lookup"><span data-stu-id="c0350-127">Optional Attribute.</span></span> <span data-ttu-id="c0350-128">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 类的序列化策略。</span><span class="sxs-lookup"><span data-stu-id="c0350-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="c0350-129">序列化</span><span class="sxs-lookup"><span data-stu-id="c0350-129">Serialization</span></span>|<span data-ttu-id="c0350-130">可选特性。</span><span class="sxs-lookup"><span data-stu-id="c0350-130">Optional Attribute.</span></span> <span data-ttu-id="c0350-131">控制使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 类的 JSON 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="c0350-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="c0350-132">序列化</span><span class="sxs-lookup"><span data-stu-id="c0350-132">Serialization</span></span>|<span data-ttu-id="c0350-133">可选特性。</span><span class="sxs-lookup"><span data-stu-id="c0350-133">Optional Attribute.</span></span> <span data-ttu-id="c0350-134">控制使用 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 类的 XML 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="c0350-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="c0350-135">Interop</span><span class="sxs-lookup"><span data-stu-id="c0350-135">Interop</span></span>|<span data-ttu-id="c0350-136">可选特性。</span><span class="sxs-lookup"><span data-stu-id="c0350-136">Optional Attribute.</span></span> <span data-ttu-id="c0350-137">控制封送引用类型到 Windows 运行时和 COM 的策略。</span><span class="sxs-lookup"><span data-stu-id="c0350-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="c0350-138">Interop</span><span class="sxs-lookup"><span data-stu-id="c0350-138">Interop</span></span>|<span data-ttu-id="c0350-139">可选特性。</span><span class="sxs-lookup"><span data-stu-id="c0350-139">Optional Attribute.</span></span> <span data-ttu-id="c0350-140">控制将委托类型作为函数指针封送到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="c0350-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="c0350-141">Interop</span><span class="sxs-lookup"><span data-stu-id="c0350-141">Interop</span></span>|<span data-ttu-id="c0350-142">可选特性。</span><span class="sxs-lookup"><span data-stu-id="c0350-142">Optional Attribute.</span></span> <span data-ttu-id="c0350-143">控制封送结构到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="c0350-143">Controls policy for marshaling structures to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="c0350-144">所有特性</span><span class="sxs-lookup"><span data-stu-id="c0350-144">All attributes</span></span>  
  
|<span data-ttu-id="c0350-145">值</span><span class="sxs-lookup"><span data-stu-id="c0350-145">Value</span></span>|<span data-ttu-id="c0350-146">描述</span><span class="sxs-lookup"><span data-stu-id="c0350-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c0350-147">policy_setting</span><span class="sxs-lookup"><span data-stu-id="c0350-147">*policy_setting*</span></span>|<span data-ttu-id="c0350-148">该策略的设置将应用到该应用中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="c0350-148">The setting for this policy to apply to the types in the app.</span></span> <span data-ttu-id="c0350-149">可能值为 `All`、`Auto`、`Excluded`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal` 以及 `Required All`。</span><span class="sxs-lookup"><span data-stu-id="c0350-149">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="c0350-150">有关详细信息，请参阅[运行时指令策略设置](runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="c0350-150">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0350-151">子元素</span><span class="sxs-lookup"><span data-stu-id="c0350-151">Child Elements</span></span>  
  
|<span data-ttu-id="c0350-152">元素</span><span class="sxs-lookup"><span data-stu-id="c0350-152">Element</span></span>|<span data-ttu-id="c0350-153">描述</span><span class="sxs-lookup"><span data-stu-id="c0350-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0350-154">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="c0350-154">\<Assembly></span></span>](assembly-element-net-native.md)|<span data-ttu-id="c0350-155">将策略应用到特定程序集中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="c0350-155">Applies policy to all the types in a particular assembly.</span></span>|  
|[<span data-ttu-id="c0350-156">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="c0350-156">\<Namespace></span></span>](namespace-element-net-native.md)|<span data-ttu-id="c0350-157">将策略应用到特定命名空间中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="c0350-157">Applies policy to all the types in a particular namespace.</span></span>|  
|[<span data-ttu-id="c0350-158">\<Type></span><span class="sxs-lookup"><span data-stu-id="c0350-158">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="c0350-159">将策略应用到一个特定类型，例如一个类或结构。</span><span class="sxs-lookup"><span data-stu-id="c0350-159">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[<span data-ttu-id="c0350-160">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="c0350-160">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="c0350-161">将策略应用到一个构造泛型类型。</span><span class="sxs-lookup"><span data-stu-id="c0350-161">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="c0350-162">例如，一个 [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 元素可用于为一个 `List<String>` 类型定义策略。</span><span class="sxs-lookup"><span data-stu-id="c0350-162">For example, a [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
|[<span data-ttu-id="c0350-163">\<Method></span><span class="sxs-lookup"><span data-stu-id="c0350-163">\<Method></span></span>](method-element-net-native.md)|<span data-ttu-id="c0350-164">将策略应用到一个特定类型上的方法。</span><span class="sxs-lookup"><span data-stu-id="c0350-164">Applies policy to a method on a particular type.</span></span>|  
|[<span data-ttu-id="c0350-165">\<MethodInstantiation></span><span class="sxs-lookup"><span data-stu-id="c0350-165">\<MethodInstantiation></span></span>](methodinstantiation-element-net-native.md)|<span data-ttu-id="c0350-166">将策略应用到一个构造泛型方法。</span><span class="sxs-lookup"><span data-stu-id="c0350-166">Applies policy to a constructed generic method.</span></span>|  
|[<span data-ttu-id="c0350-167">\<Property></span><span class="sxs-lookup"><span data-stu-id="c0350-167">\<Property></span></span>](property-element-net-native.md)|<span data-ttu-id="c0350-168">将策略应用到一个特定类型上的属性。</span><span class="sxs-lookup"><span data-stu-id="c0350-168">Applies policy to a property on a particular type.</span></span>|  
|[<span data-ttu-id="c0350-169">\<Field></span><span class="sxs-lookup"><span data-stu-id="c0350-169">\<Field></span></span>](field-element-net-native.md)|<span data-ttu-id="c0350-170">将策略应用到一个特定类型上的字段。</span><span class="sxs-lookup"><span data-stu-id="c0350-170">Applies policy to a field on a particular type.</span></span>|  
|[<span data-ttu-id="c0350-171">\<Event></span><span class="sxs-lookup"><span data-stu-id="c0350-171">\<Event></span></span>](event-element-net-native.md)|<span data-ttu-id="c0350-172">将策略应用到一个特定类型上的事件。</span><span class="sxs-lookup"><span data-stu-id="c0350-172">Applies policy to an event on a particular type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c0350-173">父元素</span><span class="sxs-lookup"><span data-stu-id="c0350-173">Parent Elements</span></span>  
  
|<span data-ttu-id="c0350-174">元素</span><span class="sxs-lookup"><span data-stu-id="c0350-174">Element</span></span>|<span data-ttu-id="c0350-175">描述</span><span class="sxs-lookup"><span data-stu-id="c0350-175">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0350-176">\<Directives></span><span class="sxs-lookup"><span data-stu-id="c0350-176">\<Directives></span></span>](directives-element-net-native.md)|<span data-ttu-id="c0350-177">运行时指令文件的根元素。</span><span class="sxs-lookup"><span data-stu-id="c0350-177">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0350-178">备注</span><span class="sxs-lookup"><span data-stu-id="c0350-178">Remarks</span></span>  
 <span data-ttu-id="c0350-179">[\<Directives>](directives-element-net-native.md) 元素可以包含零个或一个 `<Application>` 元素。</span><span class="sxs-lookup"><span data-stu-id="c0350-179">The [\<Directives>](directives-element-net-native.md) element can contain zero or one `<Application>` element.</span></span> <span data-ttu-id="c0350-180">单独一个反射指令文件中出现的多个 `<Application>` 元素不受支持。</span><span class="sxs-lookup"><span data-stu-id="c0350-180">Multiple `<Application>` elements in a single reflection directives file are not supported.</span></span>  
  
 <span data-ttu-id="c0350-181">`<Application>` 元素可通过以下方法之一使用：</span><span class="sxs-lookup"><span data-stu-id="c0350-181">The `<Application>` element can be used in one of two ways:</span></span>  
  
- <span data-ttu-id="c0350-182">作为定义在运行时间需要元数据的程序元素的容器。</span><span class="sxs-lookup"><span data-stu-id="c0350-182">As a container to define the program elements whose metadata is needed at run time.</span></span> <span data-ttu-id="c0350-183">在这种情况下，`<Application>` 元素不需要具有任何特性。</span><span class="sxs-lookup"><span data-stu-id="c0350-183">In this case, the `<Application>` element need not have any attributes.</span></span> <span data-ttu-id="c0350-184">在编译时间，编译器工具搜索 .NET Framework 核心库等所有库，以查找由 `<Application>` 元素的子元素识别出的程序元素。</span><span class="sxs-lookup"><span data-stu-id="c0350-184">At compile time, compiler tools search all libraries, including .NET Framework core libraries, for program elements identified by child elements of the `<Application>` element.</span></span> <span data-ttu-id="c0350-185">相比而言，编译器工具仅搜素由 [\<Library>](library-element-net-native.md) 元素指定的库，以查找由 [\<Library>](library-element-net-native.md) 的子元素识别出的程序元素。</span><span class="sxs-lookup"><span data-stu-id="c0350-185">In contrast, compiler tools search only the library designated by the [\<Library>](library-element-net-native.md) element for program elements identified by the child elements of [\<Library>](library-element-net-native.md).</span></span>  
  
- <span data-ttu-id="c0350-186">作为为反射、序列化和互操作设置应用程序范围的策略的元素。</span><span class="sxs-lookup"><span data-stu-id="c0350-186">As an element that sets application-wide policy for reflection, serialization, and interop.</span></span> <span data-ttu-id="c0350-187">`<Application>` 元素的特性定义应用程序范围的策略，它可能会遭到 `<Application>` 或 [\<Library>](library-element-net-native.md) 元素定义的子元素的改写。</span><span class="sxs-lookup"><span data-stu-id="c0350-187">The attributes of the `<Application>` element define application-wide policy, which may be overridden by the child elements defined by the `<Application>` or [\<Library>](library-element-net-native.md) element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0350-188">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0350-188">See also</span></span>

- [<span data-ttu-id="c0350-189">\<库 > 元素</span><span class="sxs-lookup"><span data-stu-id="c0350-189">\<Library> Element</span></span>](library-element-net-native.md)
- [<span data-ttu-id="c0350-190">\<指令 > 元素</span><span class="sxs-lookup"><span data-stu-id="c0350-190">\<Directives> Element</span></span>](directives-element-net-native.md)
- [<span data-ttu-id="c0350-191">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="c0350-191">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="c0350-192">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="c0350-192">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
