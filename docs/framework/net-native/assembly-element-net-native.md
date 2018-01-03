---
title: "&lt;程序集&gt;元素 (.NET Native)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfe629eb-1106-4113-86e1-052f402d8d8b
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a34e49e4d11f442f15db2f06b330b8b84a165a08
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltassemblygt-element-net-native"></a><span data-ttu-id="1cfe0-102">&lt;程序集&gt;元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="1cfe0-102">&lt;Assembly&gt; Element (.NET Native)</span></span>
<span data-ttu-id="1cfe0-103">将运行时反射策略应用到指定程序集中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-103">Applies runtime reflection policy to all the types in a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cfe0-104">语法</span><span class="sxs-lookup"><span data-stu-id="1cfe0-104">Syntax</span></span>  
  
```xml  
<Assembly Name="assembly_name"   
          Activate="policy_setting"  
          Browse="policy_setting"  
          Dynamic="policy_setting"  
          Serialize="policy_setting" />  
          DataContractSerializer="policy_setting"  
          DataContractJsonSerializer="policy_setting"  
          XmlSerializer="policy_setting"  
          MarshalObject="policy_setting"  
          MarshalDelegate="policy_setting"  
          MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1cfe0-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1cfe0-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1cfe0-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1cfe0-107">特性</span><span class="sxs-lookup"><span data-stu-id="1cfe0-107">Attributes</span></span>  
  
|<span data-ttu-id="1cfe0-108">特性</span><span class="sxs-lookup"><span data-stu-id="1cfe0-108">Attribute</span></span>|<span data-ttu-id="1cfe0-109">特性类型</span><span class="sxs-lookup"><span data-stu-id="1cfe0-109">Attribute type</span></span>|<span data-ttu-id="1cfe0-110">描述</span><span class="sxs-lookup"><span data-stu-id="1cfe0-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="1cfe0-111">常规</span><span class="sxs-lookup"><span data-stu-id="1cfe0-111">General</span></span>|<span data-ttu-id="1cfe0-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-112">Required attribute.</span></span> <span data-ttu-id="1cfe0-113">指定一个程序集的简单名称。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-113">Specifies the simple name of an assembly.</span></span>|  
|`Activate`|<span data-ttu-id="1cfe0-114">映像</span><span class="sxs-lookup"><span data-stu-id="1cfe0-114">Reflection</span></span>|<span data-ttu-id="1cfe0-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-115">Optional attribute.</span></span> <span data-ttu-id="1cfe0-116">控制运行时对构造函数的访问，以启用实例激活。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="1cfe0-117">映像</span><span class="sxs-lookup"><span data-stu-id="1cfe0-117">Reflection</span></span>|<span data-ttu-id="1cfe0-118">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-118">Optional attribute.</span></span> <span data-ttu-id="1cfe0-119">控制查询或列举程序集中的类型的信息，但并不在运行时间启用任何动态访问。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-119">Controls querying for information about or enumerating the types in the assembly, but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="1cfe0-120">映像</span><span class="sxs-lookup"><span data-stu-id="1cfe0-120">Reflection</span></span>|<span data-ttu-id="1cfe0-121">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-121">Optional attribute.</span></span> <span data-ttu-id="1cfe0-122">控制运行时对所有类型成员的访问，包括构造函数、方法、字段、属性和事件，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="1cfe0-123">序列化</span><span class="sxs-lookup"><span data-stu-id="1cfe0-123">Serialization</span></span>|<span data-ttu-id="1cfe0-124">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-124">Optional attribute.</span></span> <span data-ttu-id="1cfe0-125">控制运行时对构造函数、字段和属性的访问，使类型实例得到序列化和反序列化处理，这是通过库进行的，例如 Newtonsoft JSON 序列化程序。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="1cfe0-126">序列化</span><span class="sxs-lookup"><span data-stu-id="1cfe0-126">Serialization</span></span>|<span data-ttu-id="1cfe0-127">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-127">Optional attribute.</span></span> <span data-ttu-id="1cfe0-128">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 类的序列化策略。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="1cfe0-129">序列化</span><span class="sxs-lookup"><span data-stu-id="1cfe0-129">Serialization</span></span>|<span data-ttu-id="1cfe0-130">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-130">Optional attribute.</span></span> <span data-ttu-id="1cfe0-131">控制使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 类的 JSON 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="1cfe0-132">序列化</span><span class="sxs-lookup"><span data-stu-id="1cfe0-132">Serialization</span></span>|<span data-ttu-id="1cfe0-133">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-133">Optional attribute.</span></span> <span data-ttu-id="1cfe0-134">控制使用 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 类的 XML 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="1cfe0-135">Interop</span><span class="sxs-lookup"><span data-stu-id="1cfe0-135">Interop</span></span>|<span data-ttu-id="1cfe0-136">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-136">Optional attribute.</span></span> <span data-ttu-id="1cfe0-137">控制封送引用类型到 Windows 运行时和 COM 的策略。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="1cfe0-138">Interop</span><span class="sxs-lookup"><span data-stu-id="1cfe0-138">Interop</span></span>|<span data-ttu-id="1cfe0-139">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-139">Optional attribute.</span></span> <span data-ttu-id="1cfe0-140">控制将委托类型作为函数指针封送到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="1cfe0-141">Interop</span><span class="sxs-lookup"><span data-stu-id="1cfe0-141">Interop</span></span>|<span data-ttu-id="1cfe0-142">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-142">Optional attribute.</span></span> <span data-ttu-id="1cfe0-143">控制封送结构到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-143">Controls policy for marshaling structures to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="1cfe0-144">Name 特性</span><span class="sxs-lookup"><span data-stu-id="1cfe0-144">Name attribute</span></span>  
  
|<span data-ttu-id="1cfe0-145">值</span><span class="sxs-lookup"><span data-stu-id="1cfe0-145">Value</span></span>|<span data-ttu-id="1cfe0-146">描述</span><span class="sxs-lookup"><span data-stu-id="1cfe0-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1cfe0-147">assembly_name</span><span class="sxs-lookup"><span data-stu-id="1cfe0-147">*assembly_name*</span></span>|<span data-ttu-id="1cfe0-148">程序集的简单名称，不要包含文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-148">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="1cfe0-149">此特性对应 <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-149">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="1cfe0-150">例如，一个名为 Extensions.dll 的程序集的名称为“Extensions”。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-150">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span><br /><br /> <span data-ttu-id="1cfe0-151">你也可以指定文本字符串 `*Application*`，从而将策略应用到你的程序包中的所有程序集，而不管这些程序集是否已加载。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-151">You can also specify the literal string `*Application*` to apply policy to all assemblies in your app package, whether those assemblies are loaded or not.</span></span> <span data-ttu-id="1cfe0-152">`*Application*` 从不会将策略应用到 .NET Framework 程序集。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-152">`*Application*` never applies policy to .NET Framework assemblies.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="1cfe0-153">所有其他特性</span><span class="sxs-lookup"><span data-stu-id="1cfe0-153">All other attributes</span></span>  
  
|<span data-ttu-id="1cfe0-154">值</span><span class="sxs-lookup"><span data-stu-id="1cfe0-154">Value</span></span>|<span data-ttu-id="1cfe0-155">描述</span><span class="sxs-lookup"><span data-stu-id="1cfe0-155">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1cfe0-156">policy_setting</span><span class="sxs-lookup"><span data-stu-id="1cfe0-156">*policy_setting*</span></span>|<span data-ttu-id="1cfe0-157">该设置将应用这个策略类型到该程序集中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-157">The setting to apply to this policy type for all types in the assembly.</span></span> <span data-ttu-id="1cfe0-158">可能值为 `All`、`Auto`、`Excluded`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal` 以及 `Required All`。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-158">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="1cfe0-159">有关详细信息，请参阅[运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-159">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1cfe0-160">子元素</span><span class="sxs-lookup"><span data-stu-id="1cfe0-160">Child Elements</span></span>  
  
|<span data-ttu-id="1cfe0-161">元素</span><span class="sxs-lookup"><span data-stu-id="1cfe0-161">Element</span></span>|<span data-ttu-id="1cfe0-162">描述</span><span class="sxs-lookup"><span data-stu-id="1cfe0-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cfe0-163">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="1cfe0-163">\<Namespace></span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)|<span data-ttu-id="1cfe0-164">将反射策略应用到一个子命名空间中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-164">Applies reflection policy to all types in a child namespace.</span></span>|  
|[<span data-ttu-id="1cfe0-165">\<Type></span><span class="sxs-lookup"><span data-stu-id="1cfe0-165">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="1cfe0-166">将反射策略应用到一个类型。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-166">Applies reflection policy to a type.</span></span>|  
|[<span data-ttu-id="1cfe0-167">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="1cfe0-167">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="1cfe0-168">将反射策略应用到一个构造泛型类型。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-168">Applies reflection policy to a constructed generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1cfe0-169">父元素</span><span class="sxs-lookup"><span data-stu-id="1cfe0-169">Parent Elements</span></span>  
  
|<span data-ttu-id="1cfe0-170">元素</span><span class="sxs-lookup"><span data-stu-id="1cfe0-170">Element</span></span>|<span data-ttu-id="1cfe0-171">描述</span><span class="sxs-lookup"><span data-stu-id="1cfe0-171">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cfe0-172">\<Application></span><span class="sxs-lookup"><span data-stu-id="1cfe0-172">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="1cfe0-173">作为应用程序范围内的类型和元数据可以反应在运行时间的类型成员的容器而服务。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-173">Serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="1cfe0-174">[\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 元素可包含零个、一个或多个 `<Assembly>` 元素。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-174">The [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element can have zero, one, or more `<Assembly>` elements.</span></span>|  
|[<span data-ttu-id="1cfe0-175">\<Library></span><span class="sxs-lookup"><span data-stu-id="1cfe0-175">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="1cfe0-176">定义包含元数据在运行时间可以用于反射的类型和类型成员的程序集。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-176">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="1cfe0-177">[\<Library>](../../../docs/framework/net-native/library-element-net-native.md) 元素可包含零个或一个 `<Assembly>` 元素。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-177">The [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) element can have zero or one `<Assembly>` element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cfe0-178">备注</span><span class="sxs-lookup"><span data-stu-id="1cfe0-178">Remarks</span></span>  
 <span data-ttu-id="1cfe0-179">`<Assembly>` 元素为一个程序集中的所有类型定义运行时策略。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-179">The `<Assembly>` element defines runtime policy for all the types in an assembly.</span></span> <span data-ttu-id="1cfe0-180">它不同于 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) 元素，后者指定一个库但依赖其子元素来定义运行时反射策略。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-180">It differs from the [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) element, which specifies a library but depends on its child elements to define runtime reflection policy.</span></span> <span data-ttu-id="1cfe0-181">`<Assembly>` 元素将应用到一个程序集中的所有类型，除非这些类型遭到一个子元素的替代。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-181">The `<Assembly>` element applies to all the types in an assembly unless they are overridden by a child element.</span></span>  
  
 <span data-ttu-id="1cfe0-182">以下示例展示了该如何通过分配给 `Name` 特性一个“*Application\*”值，从而将运行时策略应用到应用包内的程序集中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-182">The following example shows how you can apply runtime policy to all the types in assemblies within your app package by assigning the `Name` attribute a value of "*Application\*".</span></span> <span data-ttu-id="1cfe0-183">`<Assembly>` 元素必须是 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-183">The `<Assembly>` element must be a child of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">   
  <Application>   
     <Assembly Name="*Application*" Dynamic="Required All" />   
  </Application>   
</Directives>  
```  
  
 <span data-ttu-id="1cfe0-184">`Activate`、`Browse`、`Dynamic` 和 `Serialize` 特性都是可选项。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-184">The `Activate`, `Browse`, `Dynamic`, and `Serialize` attributes are all optional.</span></span> <span data-ttu-id="1cfe0-185">然而，`<Assembly>` 元素必须至少包含这些属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="1cfe0-185">However, the `<Assembly>` element must contain at least one of these attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cfe0-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="1cfe0-186">See Also</span></span>  
 [<span data-ttu-id="1cfe0-187">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="1cfe0-187">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="1cfe0-188">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="1cfe0-188">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="1cfe0-189">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="1cfe0-189">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
