---
title: "&lt;类型参数&gt;元素 (.NET Native)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d37bb1b7-1ddc-4c6d-8ecf-583f804a2479
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 94c7b2fe5cf586c0f8a58d1698cdf3870b5b5c96
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="lttypeparametergt-element-net-native"></a><span data-ttu-id="7fd24-102">&lt;类型参数&gt;元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="7fd24-102">&lt;TypeParameter&gt; Element (.NET Native)</span></span>
<span data-ttu-id="7fd24-103">将策略应用到以传递到方法为代表的类型参数类型。</span><span class="sxs-lookup"><span data-stu-id="7fd24-103">Applies policy to the type represented by a Type argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fd24-104">语法</span><span class="sxs-lookup"><span data-stu-id="7fd24-104">Syntax</span></span>  
  
```xml  
<Parameter Name="parameter_name"  
           Activate="policy_type"  
           Browse="policy_type"  
           Dynamic="policy_type"  
           Serialize="policy_type"  
           DataContractSerializer="policy_type"  
           DataContractJsonSerializer="policy_type"  
           XmlSerializer="policy_type"  
           MarshalObject="policy_type"  
           MarshalDelegate="policy_type"  
           MarshalStructure="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7fd24-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7fd24-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7fd24-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7fd24-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7fd24-107">特性</span><span class="sxs-lookup"><span data-stu-id="7fd24-107">Attributes</span></span>  
  
|<span data-ttu-id="7fd24-108">特性</span><span class="sxs-lookup"><span data-stu-id="7fd24-108">Attribute</span></span>|<span data-ttu-id="7fd24-109">特性类型</span><span class="sxs-lookup"><span data-stu-id="7fd24-109">Attribute type</span></span>|<span data-ttu-id="7fd24-110">描述</span><span class="sxs-lookup"><span data-stu-id="7fd24-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="7fd24-111">常规</span><span class="sxs-lookup"><span data-stu-id="7fd24-111">General</span></span>|<span data-ttu-id="7fd24-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="7fd24-112">Required attribute.</span></span> <span data-ttu-id="7fd24-113">类型 <xref:System.Type> 的参数名称。</span><span class="sxs-lookup"><span data-stu-id="7fd24-113">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="7fd24-114">例如，对于方法签名 `Type.GetInterfaceMap(Type interfaceType)`，`Name` 特性的值为“接口类型”。</span><span class="sxs-lookup"><span data-stu-id="7fd24-114">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
|`Activate`|<span data-ttu-id="7fd24-115">映像</span><span class="sxs-lookup"><span data-stu-id="7fd24-115">Reflection</span></span>|<span data-ttu-id="7fd24-116">可选特性。</span><span class="sxs-lookup"><span data-stu-id="7fd24-116">Optional attribute.</span></span> <span data-ttu-id="7fd24-117">控制运行时对构造函数的访问，以启用实例激活。</span><span class="sxs-lookup"><span data-stu-id="7fd24-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="7fd24-118">映像</span><span class="sxs-lookup"><span data-stu-id="7fd24-118">Reflection</span></span>|<span data-ttu-id="7fd24-119">可选特性。</span><span class="sxs-lookup"><span data-stu-id="7fd24-119">Optional attribute.</span></span> <span data-ttu-id="7fd24-120">控制对有关程序元素信息的查询，但并不启用任何运行时访问。</span><span class="sxs-lookup"><span data-stu-id="7fd24-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="7fd24-121">映像</span><span class="sxs-lookup"><span data-stu-id="7fd24-121">Reflection</span></span>|<span data-ttu-id="7fd24-122">可选特性。</span><span class="sxs-lookup"><span data-stu-id="7fd24-122">Optional attribute.</span></span> <span data-ttu-id="7fd24-123">控制运行时对所有类型成员的访问，包括构造函数、方法、字段、属性和事件，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="7fd24-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="7fd24-124">序列化</span><span class="sxs-lookup"><span data-stu-id="7fd24-124">Serialization</span></span>|<span data-ttu-id="7fd24-125">可选特性。</span><span class="sxs-lookup"><span data-stu-id="7fd24-125">Optional attribute.</span></span> <span data-ttu-id="7fd24-126">控制运行时对构造函数、字段和属性的访问，使类型实例得到序列化和反序列化处理，这是通过库进行的，例如 Newtonsoft JSON 序列化程序。</span><span class="sxs-lookup"><span data-stu-id="7fd24-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="7fd24-127">序列化</span><span class="sxs-lookup"><span data-stu-id="7fd24-127">Serialization</span></span>|<span data-ttu-id="7fd24-128">可选特性。</span><span class="sxs-lookup"><span data-stu-id="7fd24-128">Optional attribute.</span></span> <span data-ttu-id="7fd24-129">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 类的序列化策略。</span><span class="sxs-lookup"><span data-stu-id="7fd24-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="7fd24-130">序列化</span><span class="sxs-lookup"><span data-stu-id="7fd24-130">Serialization</span></span>|<span data-ttu-id="7fd24-131">可选特性。</span><span class="sxs-lookup"><span data-stu-id="7fd24-131">Optional attribute.</span></span> <span data-ttu-id="7fd24-132">控制使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 类的 JSON 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="7fd24-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="7fd24-133">序列化</span><span class="sxs-lookup"><span data-stu-id="7fd24-133">Serialization</span></span>|<span data-ttu-id="7fd24-134">可选特性。</span><span class="sxs-lookup"><span data-stu-id="7fd24-134">Optional attribute.</span></span> <span data-ttu-id="7fd24-135">控制使用 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 类的 XML 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="7fd24-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="7fd24-136">Interop</span><span class="sxs-lookup"><span data-stu-id="7fd24-136">Interop</span></span>|<span data-ttu-id="7fd24-137">可选特性。</span><span class="sxs-lookup"><span data-stu-id="7fd24-137">Optional attribute.</span></span> <span data-ttu-id="7fd24-138">控制封送引用类型到 Windows 运行时和 COM 的策略。</span><span class="sxs-lookup"><span data-stu-id="7fd24-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="7fd24-139">Interop</span><span class="sxs-lookup"><span data-stu-id="7fd24-139">Interop</span></span>|<span data-ttu-id="7fd24-140">可选特性。</span><span class="sxs-lookup"><span data-stu-id="7fd24-140">Optional attribute.</span></span> <span data-ttu-id="7fd24-141">控制将委托类型作为函数指针封送到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="7fd24-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="7fd24-142">Interop</span><span class="sxs-lookup"><span data-stu-id="7fd24-142">Interop</span></span>|<span data-ttu-id="7fd24-143">可选特性。</span><span class="sxs-lookup"><span data-stu-id="7fd24-143">Optional attribute.</span></span> <span data-ttu-id="7fd24-144">控制封送处理值类型到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="7fd24-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="7fd24-145">Name 特性</span><span class="sxs-lookup"><span data-stu-id="7fd24-145">Name attribute</span></span>  
  
|<span data-ttu-id="7fd24-146">值</span><span class="sxs-lookup"><span data-stu-id="7fd24-146">Value</span></span>|<span data-ttu-id="7fd24-147">描述</span><span class="sxs-lookup"><span data-stu-id="7fd24-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7fd24-148">parameter_name</span><span class="sxs-lookup"><span data-stu-id="7fd24-148">*parameter_name*</span></span>|<span data-ttu-id="7fd24-149">类型 <xref:System.Type> 的参数名称。</span><span class="sxs-lookup"><span data-stu-id="7fd24-149">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="7fd24-150">例如，对于方法签名 `Type.GetInterfaceMap(Type interfaceType)`，`Name` 特性的值为“接口类型”。</span><span class="sxs-lookup"><span data-stu-id="7fd24-150">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="7fd24-151">所有其他特性</span><span class="sxs-lookup"><span data-stu-id="7fd24-151">All other attributes</span></span>  
  
|<span data-ttu-id="7fd24-152">值</span><span class="sxs-lookup"><span data-stu-id="7fd24-152">Value</span></span>|<span data-ttu-id="7fd24-153">描述</span><span class="sxs-lookup"><span data-stu-id="7fd24-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7fd24-154">policy_setting</span><span class="sxs-lookup"><span data-stu-id="7fd24-154">*policy_setting*</span></span>|<span data-ttu-id="7fd24-155">该设置将应用到这种策略类型。</span><span class="sxs-lookup"><span data-stu-id="7fd24-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="7fd24-156">可能值为 `All`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal` 以及 `Required All`。</span><span class="sxs-lookup"><span data-stu-id="7fd24-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="7fd24-157">有关详细信息，请参阅[运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="7fd24-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7fd24-158">子元素</span><span class="sxs-lookup"><span data-stu-id="7fd24-158">Child Elements</span></span>  
 <span data-ttu-id="7fd24-159">无。</span><span class="sxs-lookup"><span data-stu-id="7fd24-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7fd24-160">父元素</span><span class="sxs-lookup"><span data-stu-id="7fd24-160">Parent Elements</span></span>  
  
|<span data-ttu-id="7fd24-161">元素</span><span class="sxs-lookup"><span data-stu-id="7fd24-161">Element</span></span>|<span data-ttu-id="7fd24-162">描述</span><span class="sxs-lookup"><span data-stu-id="7fd24-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7fd24-163">\<Method></span><span class="sxs-lookup"><span data-stu-id="7fd24-163">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="7fd24-164">将运行时反射策略应用到一个构造函数或方法。</span><span class="sxs-lookup"><span data-stu-id="7fd24-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fd24-165">备注</span><span class="sxs-lookup"><span data-stu-id="7fd24-165">Remarks</span></span>  
 <span data-ttu-id="7fd24-166">`<TypeParameter>` 元素与 [\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md) 元素相似，不同之处在于前者只能应用于类型 <xref:System.Type> 的参数。</span><span class="sxs-lookup"><span data-stu-id="7fd24-166">The `<TypeParameter>` element is similar to the [\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md) element, except that it can be applied only to parameters of type <xref:System.Type>.</span></span> <span data-ttu-id="7fd24-167">它将策略应用到任何在运行时间由 `Name` 特性指定的以类型参数为代表的类型。</span><span class="sxs-lookup"><span data-stu-id="7fd24-167">It applies policy to whatever type is represented at run time by the type argument specified by the `Name` attribute.</span></span>  
  
 <span data-ttu-id="7fd24-168">例如，NewtonSoft JSON 序列化程序包含一个静态 `JsonConvert.DeserializeObject(String value, Type type)` 方法。</span><span class="sxs-lookup"><span data-stu-id="7fd24-168">For example, the NewtonSoft JSON serializer includes a static `JsonConvert.DeserializeObject(String value, Type type)` method.</span></span> <span data-ttu-id="7fd24-169">以下是反射指令：</span><span class="sxs-lookup"><span data-stu-id="7fd24-169">The following reflection directives:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject">  
         <GenericParameter Name="type" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
 <span data-ttu-id="7fd24-170">指定 `type` 参数所代表的运行时类型的元数据应可用于序列化。</span><span class="sxs-lookup"><span data-stu-id="7fd24-170">specify that metadata for the runtime type represented by the `type` argument should be made available for serialization.</span></span> <span data-ttu-id="7fd24-171">如果这些运行时指令适用于一个包含以下源代码的项目：</span><span class="sxs-lookup"><span data-stu-id="7fd24-171">If these runtime directives apply to a project that includes the following source code:</span></span>  
  
```csharp  
Type t = typeof(StockQuote);  
Object obj = JsonConvert.DeserializeObject(data, t);  
```  
  
 <span data-ttu-id="7fd24-172">反射指令使 `StockQuote` 类型的元数据在运行时间可由 NewtonSoft JSON 序列化程序使用。</span><span class="sxs-lookup"><span data-stu-id="7fd24-172">the reflection directives make metadata for the `StockQuote` type available for the NewtonSoft JSON serializer at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fd24-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7fd24-173">See Also</span></span>  
 [<span data-ttu-id="7fd24-174">\<Method> 元素</span><span class="sxs-lookup"><span data-stu-id="7fd24-174">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 [<span data-ttu-id="7fd24-175">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="7fd24-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="7fd24-176">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="7fd24-176">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="7fd24-177">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="7fd24-177">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
