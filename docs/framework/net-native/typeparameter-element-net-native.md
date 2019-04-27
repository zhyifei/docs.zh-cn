---
title: <TypeParameter>元素 (.NET Native)
ms.date: 03/30/2017
ms.assetid: d37bb1b7-1ddc-4c6d-8ecf-583f804a2479
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b03c87c70fa1bfcd331f468d369632f4164300bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982457"
---
# <a name="typeparameter-element-net-native"></a><span data-ttu-id="0cfe2-102">\<类型参数 > 元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="0cfe2-102">\<TypeParameter> Element (.NET Native)</span></span>
<span data-ttu-id="0cfe2-103">将策略应用到以传递到方法为代表的类型参数类型。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-103">Applies policy to the type represented by a Type argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cfe2-104">语法</span><span class="sxs-lookup"><span data-stu-id="0cfe2-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0cfe2-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0cfe2-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0cfe2-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0cfe2-107">特性</span><span class="sxs-lookup"><span data-stu-id="0cfe2-107">Attributes</span></span>  
  
|<span data-ttu-id="0cfe2-108">特性</span><span class="sxs-lookup"><span data-stu-id="0cfe2-108">Attribute</span></span>|<span data-ttu-id="0cfe2-109">特性类型</span><span class="sxs-lookup"><span data-stu-id="0cfe2-109">Attribute type</span></span>|<span data-ttu-id="0cfe2-110">描述</span><span class="sxs-lookup"><span data-stu-id="0cfe2-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="0cfe2-111">常规</span><span class="sxs-lookup"><span data-stu-id="0cfe2-111">General</span></span>|<span data-ttu-id="0cfe2-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-112">Required attribute.</span></span> <span data-ttu-id="0cfe2-113">类型 <xref:System.Type> 的参数名称。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-113">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="0cfe2-114">例如，对于方法签名 `Type.GetInterfaceMap(Type interfaceType)`，`Name` 特性的值为“接口类型”。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-114">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
|`Activate`|<span data-ttu-id="0cfe2-115">映像</span><span class="sxs-lookup"><span data-stu-id="0cfe2-115">Reflection</span></span>|<span data-ttu-id="0cfe2-116">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-116">Optional attribute.</span></span> <span data-ttu-id="0cfe2-117">控制运行时对构造函数的访问，以启用实例激活。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="0cfe2-118">映像</span><span class="sxs-lookup"><span data-stu-id="0cfe2-118">Reflection</span></span>|<span data-ttu-id="0cfe2-119">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-119">Optional attribute.</span></span> <span data-ttu-id="0cfe2-120">控制对有关程序元素信息的查询，但并不启用任何运行时访问。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="0cfe2-121">映像</span><span class="sxs-lookup"><span data-stu-id="0cfe2-121">Reflection</span></span>|<span data-ttu-id="0cfe2-122">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-122">Optional attribute.</span></span> <span data-ttu-id="0cfe2-123">控制运行时对所有类型成员的访问，包括构造函数、方法、字段、属性和事件，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="0cfe2-124">序列化</span><span class="sxs-lookup"><span data-stu-id="0cfe2-124">Serialization</span></span>|<span data-ttu-id="0cfe2-125">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-125">Optional attribute.</span></span> <span data-ttu-id="0cfe2-126">控制运行时对构造函数、字段和属性的访问，使类型实例得到序列化和反序列化处理，这是通过库进行的，例如 Newtonsoft JSON 序列化程序。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="0cfe2-127">序列化</span><span class="sxs-lookup"><span data-stu-id="0cfe2-127">Serialization</span></span>|<span data-ttu-id="0cfe2-128">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-128">Optional attribute.</span></span> <span data-ttu-id="0cfe2-129">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 类的序列化策略。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="0cfe2-130">序列化</span><span class="sxs-lookup"><span data-stu-id="0cfe2-130">Serialization</span></span>|<span data-ttu-id="0cfe2-131">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-131">Optional attribute.</span></span> <span data-ttu-id="0cfe2-132">控制使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 类的 JSON 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="0cfe2-133">序列化</span><span class="sxs-lookup"><span data-stu-id="0cfe2-133">Serialization</span></span>|<span data-ttu-id="0cfe2-134">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-134">Optional attribute.</span></span> <span data-ttu-id="0cfe2-135">控制使用 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 类的 XML 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="0cfe2-136">Interop</span><span class="sxs-lookup"><span data-stu-id="0cfe2-136">Interop</span></span>|<span data-ttu-id="0cfe2-137">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-137">Optional attribute.</span></span> <span data-ttu-id="0cfe2-138">控制封送引用类型到 Windows 运行时和 COM 的策略。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="0cfe2-139">Interop</span><span class="sxs-lookup"><span data-stu-id="0cfe2-139">Interop</span></span>|<span data-ttu-id="0cfe2-140">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-140">Optional attribute.</span></span> <span data-ttu-id="0cfe2-141">控制将委托类型作为函数指针封送到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="0cfe2-142">Interop</span><span class="sxs-lookup"><span data-stu-id="0cfe2-142">Interop</span></span>|<span data-ttu-id="0cfe2-143">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-143">Optional attribute.</span></span> <span data-ttu-id="0cfe2-144">控制封送处理值类型到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="0cfe2-145">Name 特性</span><span class="sxs-lookup"><span data-stu-id="0cfe2-145">Name attribute</span></span>  
  
|<span data-ttu-id="0cfe2-146">“值”</span><span class="sxs-lookup"><span data-stu-id="0cfe2-146">Value</span></span>|<span data-ttu-id="0cfe2-147">描述</span><span class="sxs-lookup"><span data-stu-id="0cfe2-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0cfe2-148">parameter_name</span><span class="sxs-lookup"><span data-stu-id="0cfe2-148">*parameter_name*</span></span>|<span data-ttu-id="0cfe2-149">类型 <xref:System.Type> 的参数名称。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-149">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="0cfe2-150">例如，对于方法签名 `Type.GetInterfaceMap(Type interfaceType)`，`Name` 特性的值为“接口类型”。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-150">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="0cfe2-151">所有其他特性</span><span class="sxs-lookup"><span data-stu-id="0cfe2-151">All other attributes</span></span>  
  
|<span data-ttu-id="0cfe2-152">“值”</span><span class="sxs-lookup"><span data-stu-id="0cfe2-152">Value</span></span>|<span data-ttu-id="0cfe2-153">描述</span><span class="sxs-lookup"><span data-stu-id="0cfe2-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0cfe2-154">policy_setting</span><span class="sxs-lookup"><span data-stu-id="0cfe2-154">*policy_setting*</span></span>|<span data-ttu-id="0cfe2-155">该设置将应用到这种策略类型。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="0cfe2-156">可能值为 `All`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal` 以及 `Required All`。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="0cfe2-157">有关详细信息，请参阅[运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0cfe2-158">子元素</span><span class="sxs-lookup"><span data-stu-id="0cfe2-158">Child Elements</span></span>  
 <span data-ttu-id="0cfe2-159">无。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0cfe2-160">父元素</span><span class="sxs-lookup"><span data-stu-id="0cfe2-160">Parent Elements</span></span>  
  
|<span data-ttu-id="0cfe2-161">元素</span><span class="sxs-lookup"><span data-stu-id="0cfe2-161">Element</span></span>|<span data-ttu-id="0cfe2-162">描述</span><span class="sxs-lookup"><span data-stu-id="0cfe2-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0cfe2-163">\<Method></span><span class="sxs-lookup"><span data-stu-id="0cfe2-163">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="0cfe2-164">将运行时反射策略应用到一个构造函数或方法。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cfe2-165">备注</span><span class="sxs-lookup"><span data-stu-id="0cfe2-165">Remarks</span></span>  
 <span data-ttu-id="0cfe2-166">`<TypeParameter>` 元素与 [\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md) 元素相似，不同之处在于前者只能应用于类型 <xref:System.Type> 的参数。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-166">The `<TypeParameter>` element is similar to the [\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md) element, except that it can be applied only to parameters of type <xref:System.Type>.</span></span> <span data-ttu-id="0cfe2-167">它将策略应用到任何在运行时间由 `Name` 特性指定的以类型参数为代表的类型。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-167">It applies policy to whatever type is represented at run time by the type argument specified by the `Name` attribute.</span></span>  
  
 <span data-ttu-id="0cfe2-168">例如，NewtonSoft JSON 序列化程序包含一个静态 `JsonConvert.DeserializeObject(String value, Type type)` 方法。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-168">For example, the NewtonSoft JSON serializer includes a static `JsonConvert.DeserializeObject(String value, Type type)` method.</span></span> <span data-ttu-id="0cfe2-169">以下是反射指令：</span><span class="sxs-lookup"><span data-stu-id="0cfe2-169">The following reflection directives:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject">  
         <GenericParameter Name="type" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
 <span data-ttu-id="0cfe2-170">指定 `type` 参数所代表的运行时类型的元数据应可用于序列化。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-170">specify that metadata for the runtime type represented by the `type` argument should be made available for serialization.</span></span> <span data-ttu-id="0cfe2-171">如果这些运行时指令适用于一个包含以下源代码的项目：</span><span class="sxs-lookup"><span data-stu-id="0cfe2-171">If these runtime directives apply to a project that includes the following source code:</span></span>  
  
```csharp  
Type t = typeof(StockQuote);  
Object obj = JsonConvert.DeserializeObject(data, t);  
```  
  
 <span data-ttu-id="0cfe2-172">反射指令使 `StockQuote` 类型的元数据在运行时间可由 NewtonSoft JSON 序列化程序使用。</span><span class="sxs-lookup"><span data-stu-id="0cfe2-172">the reflection directives make metadata for the `StockQuote` type available for the NewtonSoft JSON serializer at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cfe2-173">请参阅</span><span class="sxs-lookup"><span data-stu-id="0cfe2-173">See also</span></span>

- [<span data-ttu-id="0cfe2-174">\<Method> 元素</span><span class="sxs-lookup"><span data-stu-id="0cfe2-174">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)
- [<span data-ttu-id="0cfe2-175">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="0cfe2-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="0cfe2-176">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="0cfe2-176">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
- [<span data-ttu-id="0cfe2-177">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="0cfe2-177">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
