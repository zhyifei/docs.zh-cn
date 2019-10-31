---
title: <TypeParameter>元素 (.NET Native)
ms.date: 03/30/2017
ms.assetid: d37bb1b7-1ddc-4c6d-8ecf-583f804a2479
ms.openlocfilehash: c69b535f3a01c287d30189138130066fc10a77e2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128923"
---
# <a name="typeparameter-element-net-native"></a><span data-ttu-id="41259-102">\<TypeParameter > 元素（.NET Native）</span><span class="sxs-lookup"><span data-stu-id="41259-102">\<TypeParameter> Element (.NET Native)</span></span>
<span data-ttu-id="41259-103">将策略应用到以传递到方法为代表的类型参数类型。</span><span class="sxs-lookup"><span data-stu-id="41259-103">Applies policy to the type represented by a Type argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41259-104">语法</span><span class="sxs-lookup"><span data-stu-id="41259-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41259-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="41259-105">Attributes and Elements</span></span>  
 <span data-ttu-id="41259-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="41259-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41259-107">特性</span><span class="sxs-lookup"><span data-stu-id="41259-107">Attributes</span></span>  
  
|<span data-ttu-id="41259-108">特性</span><span class="sxs-lookup"><span data-stu-id="41259-108">Attribute</span></span>|<span data-ttu-id="41259-109">特性类型</span><span class="sxs-lookup"><span data-stu-id="41259-109">Attribute type</span></span>|<span data-ttu-id="41259-110">描述</span><span class="sxs-lookup"><span data-stu-id="41259-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="41259-111">常规</span><span class="sxs-lookup"><span data-stu-id="41259-111">General</span></span>|<span data-ttu-id="41259-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="41259-112">Required attribute.</span></span> <span data-ttu-id="41259-113">类型 <xref:System.Type> 的参数名称。</span><span class="sxs-lookup"><span data-stu-id="41259-113">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="41259-114">例如，对于方法签名 `Type.GetInterfaceMap(Type interfaceType)`，`Name` 特性的值为“接口类型”。</span><span class="sxs-lookup"><span data-stu-id="41259-114">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
|`Activate`|<span data-ttu-id="41259-115">映像</span><span class="sxs-lookup"><span data-stu-id="41259-115">Reflection</span></span>|<span data-ttu-id="41259-116">可选特性。</span><span class="sxs-lookup"><span data-stu-id="41259-116">Optional attribute.</span></span> <span data-ttu-id="41259-117">控制运行时对构造函数的访问，以启用实例激活。</span><span class="sxs-lookup"><span data-stu-id="41259-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="41259-118">映像</span><span class="sxs-lookup"><span data-stu-id="41259-118">Reflection</span></span>|<span data-ttu-id="41259-119">可选特性。</span><span class="sxs-lookup"><span data-stu-id="41259-119">Optional attribute.</span></span> <span data-ttu-id="41259-120">控制对有关程序元素信息的查询，但并不启用任何运行时访问。</span><span class="sxs-lookup"><span data-stu-id="41259-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="41259-121">映像</span><span class="sxs-lookup"><span data-stu-id="41259-121">Reflection</span></span>|<span data-ttu-id="41259-122">可选特性。</span><span class="sxs-lookup"><span data-stu-id="41259-122">Optional attribute.</span></span> <span data-ttu-id="41259-123">控制运行时对所有类型成员的访问，包括构造函数、方法、字段、属性和事件，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="41259-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="41259-124">序列化</span><span class="sxs-lookup"><span data-stu-id="41259-124">Serialization</span></span>|<span data-ttu-id="41259-125">可选特性。</span><span class="sxs-lookup"><span data-stu-id="41259-125">Optional attribute.</span></span> <span data-ttu-id="41259-126">控制运行时对构造函数、字段和属性的访问，使类型实例得到序列化和反序列化处理，这是通过库进行的，例如 Newtonsoft JSON 序列化程序。</span><span class="sxs-lookup"><span data-stu-id="41259-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="41259-127">序列化</span><span class="sxs-lookup"><span data-stu-id="41259-127">Serialization</span></span>|<span data-ttu-id="41259-128">可选特性。</span><span class="sxs-lookup"><span data-stu-id="41259-128">Optional attribute.</span></span> <span data-ttu-id="41259-129">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 类的序列化策略。</span><span class="sxs-lookup"><span data-stu-id="41259-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="41259-130">序列化</span><span class="sxs-lookup"><span data-stu-id="41259-130">Serialization</span></span>|<span data-ttu-id="41259-131">可选特性。</span><span class="sxs-lookup"><span data-stu-id="41259-131">Optional attribute.</span></span> <span data-ttu-id="41259-132">控制使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 类的 JSON 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="41259-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="41259-133">序列化</span><span class="sxs-lookup"><span data-stu-id="41259-133">Serialization</span></span>|<span data-ttu-id="41259-134">可选特性。</span><span class="sxs-lookup"><span data-stu-id="41259-134">Optional attribute.</span></span> <span data-ttu-id="41259-135">控制使用 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 类的 XML 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="41259-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="41259-136">Interop</span><span class="sxs-lookup"><span data-stu-id="41259-136">Interop</span></span>|<span data-ttu-id="41259-137">可选特性。</span><span class="sxs-lookup"><span data-stu-id="41259-137">Optional attribute.</span></span> <span data-ttu-id="41259-138">控制封送引用类型到 Windows 运行时和 COM 的策略。</span><span class="sxs-lookup"><span data-stu-id="41259-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="41259-139">Interop</span><span class="sxs-lookup"><span data-stu-id="41259-139">Interop</span></span>|<span data-ttu-id="41259-140">可选特性。</span><span class="sxs-lookup"><span data-stu-id="41259-140">Optional attribute.</span></span> <span data-ttu-id="41259-141">控制将委托类型作为函数指针封送到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="41259-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="41259-142">Interop</span><span class="sxs-lookup"><span data-stu-id="41259-142">Interop</span></span>|<span data-ttu-id="41259-143">可选特性。</span><span class="sxs-lookup"><span data-stu-id="41259-143">Optional attribute.</span></span> <span data-ttu-id="41259-144">控制封送处理值类型到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="41259-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="41259-145">Name 特性</span><span class="sxs-lookup"><span data-stu-id="41259-145">Name attribute</span></span>  
  
|<span data-ttu-id="41259-146">“值”</span><span class="sxs-lookup"><span data-stu-id="41259-146">Value</span></span>|<span data-ttu-id="41259-147">描述</span><span class="sxs-lookup"><span data-stu-id="41259-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="41259-148">parameter_name</span><span class="sxs-lookup"><span data-stu-id="41259-148">*parameter_name*</span></span>|<span data-ttu-id="41259-149">类型 <xref:System.Type> 的参数名称。</span><span class="sxs-lookup"><span data-stu-id="41259-149">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="41259-150">例如，对于方法签名 `Type.GetInterfaceMap(Type interfaceType)`，`Name` 特性的值为“接口类型”。</span><span class="sxs-lookup"><span data-stu-id="41259-150">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="41259-151">所有其他特性</span><span class="sxs-lookup"><span data-stu-id="41259-151">All other attributes</span></span>  
  
|<span data-ttu-id="41259-152">“值”</span><span class="sxs-lookup"><span data-stu-id="41259-152">Value</span></span>|<span data-ttu-id="41259-153">描述</span><span class="sxs-lookup"><span data-stu-id="41259-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="41259-154">policy_setting</span><span class="sxs-lookup"><span data-stu-id="41259-154">*policy_setting*</span></span>|<span data-ttu-id="41259-155">该设置将应用到这种策略类型。</span><span class="sxs-lookup"><span data-stu-id="41259-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="41259-156">可能值为 `All`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal` 以及 `Required All`。</span><span class="sxs-lookup"><span data-stu-id="41259-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="41259-157">有关详细信息，请参阅[运行时指令策略设置](runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="41259-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41259-158">子元素</span><span class="sxs-lookup"><span data-stu-id="41259-158">Child Elements</span></span>  
 <span data-ttu-id="41259-159">无。</span><span class="sxs-lookup"><span data-stu-id="41259-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41259-160">父元素</span><span class="sxs-lookup"><span data-stu-id="41259-160">Parent Elements</span></span>  
  
|<span data-ttu-id="41259-161">元素</span><span class="sxs-lookup"><span data-stu-id="41259-161">Element</span></span>|<span data-ttu-id="41259-162">描述</span><span class="sxs-lookup"><span data-stu-id="41259-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41259-163">\<Method></span><span class="sxs-lookup"><span data-stu-id="41259-163">\<Method></span></span>](method-element-net-native.md)|<span data-ttu-id="41259-164">将运行时反射策略应用到一个构造函数或方法。</span><span class="sxs-lookup"><span data-stu-id="41259-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41259-165">备注</span><span class="sxs-lookup"><span data-stu-id="41259-165">Remarks</span></span>  
 <span data-ttu-id="41259-166">`<TypeParameter>` 元素与 [\<Parameter>](parameter-element-net-native.md) 元素相似，不同之处在于前者只能应用于类型 <xref:System.Type> 的参数。</span><span class="sxs-lookup"><span data-stu-id="41259-166">The `<TypeParameter>` element is similar to the [\<Parameter>](parameter-element-net-native.md) element, except that it can be applied only to parameters of type <xref:System.Type>.</span></span> <span data-ttu-id="41259-167">它将策略应用到任何在运行时间由 `Name` 特性指定的以类型参数为代表的类型。</span><span class="sxs-lookup"><span data-stu-id="41259-167">It applies policy to whatever type is represented at run time by the type argument specified by the `Name` attribute.</span></span>  
  
 <span data-ttu-id="41259-168">例如，NewtonSoft JSON 序列化程序包含一个静态 `JsonConvert.DeserializeObject(String value, Type type)` 方法。</span><span class="sxs-lookup"><span data-stu-id="41259-168">For example, the NewtonSoft JSON serializer includes a static `JsonConvert.DeserializeObject(String value, Type type)` method.</span></span> <span data-ttu-id="41259-169">以下是反射指令：</span><span class="sxs-lookup"><span data-stu-id="41259-169">The following reflection directives:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject">  
         <GenericParameter Name="type" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
 <span data-ttu-id="41259-170">指定 `type` 参数所代表的运行时类型的元数据应可用于序列化。</span><span class="sxs-lookup"><span data-stu-id="41259-170">specify that metadata for the runtime type represented by the `type` argument should be made available for serialization.</span></span> <span data-ttu-id="41259-171">如果这些运行时指令适用于一个包含以下源代码的项目：</span><span class="sxs-lookup"><span data-stu-id="41259-171">If these runtime directives apply to a project that includes the following source code:</span></span>  
  
```csharp  
Type t = typeof(StockQuote);  
Object obj = JsonConvert.DeserializeObject(data, t);  
```  
  
 <span data-ttu-id="41259-172">反射指令使 `StockQuote` 类型的元数据在运行时间可由 NewtonSoft JSON 序列化程序使用。</span><span class="sxs-lookup"><span data-stu-id="41259-172">the reflection directives make metadata for the `StockQuote` type available for the NewtonSoft JSON serializer at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41259-173">请参阅</span><span class="sxs-lookup"><span data-stu-id="41259-173">See also</span></span>

- [<span data-ttu-id="41259-174">\<Method> 元素</span><span class="sxs-lookup"><span data-stu-id="41259-174">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="41259-175">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="41259-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="41259-176">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="41259-176">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="41259-177">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="41259-177">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
