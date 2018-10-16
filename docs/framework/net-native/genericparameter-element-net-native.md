---
title: '&lt;泛型参数&gt;元素 (.NET Native)'
ms.date: 03/30/2017
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd0d9851f62381a16f628607c326c6690492628b
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347846"
---
# <a name="ltgenericparametergt-element-net-native"></a><span data-ttu-id="694e0-102">&lt;泛型参数&gt;元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="694e0-102">&lt;GenericParameter&gt; Element (.NET Native)</span></span>
<span data-ttu-id="694e0-103">将策略应用到一个泛型类型或方法的参数类型。</span><span class="sxs-lookup"><span data-stu-id="694e0-103">Applies policy to the parameter type of a generic type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="694e0-104">语法</span><span class="sxs-lookup"><span data-stu-id="694e0-104">Syntax</span></span>  
  
```xml  
<GenericParameter Name="generic_parameter_name"  
                  Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type" />  
                  DataContractSerializer="policy_type"  
                  DataContractJsonSerializer="policy_type"  
                  XmlSerializer="policy_type"  
                  MarshalObject="policy_type"  
                  MarshalDelegate="policy_type"  
                  MarshalStructure="policy_type"  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="694e0-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="694e0-105">Attributes and Elements</span></span>  
 <span data-ttu-id="694e0-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="694e0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="694e0-107">特性</span><span class="sxs-lookup"><span data-stu-id="694e0-107">Attributes</span></span>  
  
|<span data-ttu-id="694e0-108">特性</span><span class="sxs-lookup"><span data-stu-id="694e0-108">Attribute</span></span>|<span data-ttu-id="694e0-109">特性类型</span><span class="sxs-lookup"><span data-stu-id="694e0-109">Attribute type</span></span>|<span data-ttu-id="694e0-110">描述</span><span class="sxs-lookup"><span data-stu-id="694e0-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="694e0-111">常规</span><span class="sxs-lookup"><span data-stu-id="694e0-111">General</span></span>|<span data-ttu-id="694e0-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="694e0-112">Required attribute.</span></span> <span data-ttu-id="694e0-113">泛型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="694e0-113">The name of the generic parameter.</span></span> <span data-ttu-id="694e0-114">例如，对于泛型委托 <xref:System.Func%603>，`Name` 特性的值为“TResult”，从而将运行时策略应用到该委托的返回值。</span><span class="sxs-lookup"><span data-stu-id="694e0-114">For example, for the generic delegate <xref:System.Func%603>, the value of the `Name` attribute is "TResult" to apply runtime policy to the delegate's return value.</span></span>|  
|`Activate`|<span data-ttu-id="694e0-115">映像</span><span class="sxs-lookup"><span data-stu-id="694e0-115">Reflection</span></span>|<span data-ttu-id="694e0-116">可选特性。</span><span class="sxs-lookup"><span data-stu-id="694e0-116">Optional attribute.</span></span> <span data-ttu-id="694e0-117">控制运行时对构造函数的访问，以启用实例激活。</span><span class="sxs-lookup"><span data-stu-id="694e0-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="694e0-118">映像</span><span class="sxs-lookup"><span data-stu-id="694e0-118">Reflection</span></span>|<span data-ttu-id="694e0-119">可选特性。</span><span class="sxs-lookup"><span data-stu-id="694e0-119">Optional attribute.</span></span> <span data-ttu-id="694e0-120">控制对有关程序元素信息的查询，但并不启用任何运行时访问。</span><span class="sxs-lookup"><span data-stu-id="694e0-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="694e0-121">映像</span><span class="sxs-lookup"><span data-stu-id="694e0-121">Reflection</span></span>|<span data-ttu-id="694e0-122">可选特性。</span><span class="sxs-lookup"><span data-stu-id="694e0-122">Optional attribute.</span></span> <span data-ttu-id="694e0-123">控制运行时对所有类型成员的访问，包括构造函数、方法、字段、属性和事件，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="694e0-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="694e0-124">序列化</span><span class="sxs-lookup"><span data-stu-id="694e0-124">Serialization</span></span>|<span data-ttu-id="694e0-125">可选特性。</span><span class="sxs-lookup"><span data-stu-id="694e0-125">Optional attribute.</span></span> <span data-ttu-id="694e0-126">控制运行时对构造函数、字段和属性的访问，使类型实例得到序列化和反序列化处理，这是通过库进行的，例如 Newtonsoft JSON 序列化程序。</span><span class="sxs-lookup"><span data-stu-id="694e0-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="694e0-127">序列化</span><span class="sxs-lookup"><span data-stu-id="694e0-127">Serialization</span></span>|<span data-ttu-id="694e0-128">可选特性。</span><span class="sxs-lookup"><span data-stu-id="694e0-128">Optional attribute.</span></span> <span data-ttu-id="694e0-129">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 类的序列化策略。</span><span class="sxs-lookup"><span data-stu-id="694e0-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="694e0-130">序列化</span><span class="sxs-lookup"><span data-stu-id="694e0-130">Serialization</span></span>|<span data-ttu-id="694e0-131">可选特性。</span><span class="sxs-lookup"><span data-stu-id="694e0-131">Optional attribute.</span></span> <span data-ttu-id="694e0-132">控制使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 类的 JSON 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="694e0-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="694e0-133">序列化</span><span class="sxs-lookup"><span data-stu-id="694e0-133">Serialization</span></span>|<span data-ttu-id="694e0-134">可选特性。</span><span class="sxs-lookup"><span data-stu-id="694e0-134">Optional attribute.</span></span> <span data-ttu-id="694e0-135">控制使用 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 类的 XML 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="694e0-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="694e0-136">Interop</span><span class="sxs-lookup"><span data-stu-id="694e0-136">Interop</span></span>|<span data-ttu-id="694e0-137">可选特性。</span><span class="sxs-lookup"><span data-stu-id="694e0-137">Optional attribute.</span></span> <span data-ttu-id="694e0-138">控制封送引用类型到 Windows 运行时和 COM 的策略。</span><span class="sxs-lookup"><span data-stu-id="694e0-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="694e0-139">Interop</span><span class="sxs-lookup"><span data-stu-id="694e0-139">Interop</span></span>|<span data-ttu-id="694e0-140">可选特性。</span><span class="sxs-lookup"><span data-stu-id="694e0-140">Optional attribute.</span></span> <span data-ttu-id="694e0-141">控制将委托类型作为函数指针封送到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="694e0-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="694e0-142">Interop</span><span class="sxs-lookup"><span data-stu-id="694e0-142">Interop</span></span>|<span data-ttu-id="694e0-143">可选特性。</span><span class="sxs-lookup"><span data-stu-id="694e0-143">Optional attribute.</span></span> <span data-ttu-id="694e0-144">控制封送处理值类型到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="694e0-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="694e0-145">Name 特性</span><span class="sxs-lookup"><span data-stu-id="694e0-145">Name attribute</span></span>  
  
|<span data-ttu-id="694e0-146">值</span><span class="sxs-lookup"><span data-stu-id="694e0-146">Value</span></span>|<span data-ttu-id="694e0-147">描述</span><span class="sxs-lookup"><span data-stu-id="694e0-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="694e0-148">generic_parameter_name</span><span class="sxs-lookup"><span data-stu-id="694e0-148">*generic_parameter_name*</span></span>|<span data-ttu-id="694e0-149">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="694e0-149">Required attribute.</span></span> <span data-ttu-id="694e0-150">泛型类型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="694e0-150">The name of the generic type parameter.</span></span> <span data-ttu-id="694e0-151">例如，对于泛型委托 <xref:System.Func%603>，“TResult”的一个 generic_parameter_name 值将运行时策略应用到该委托的返回值。</span><span class="sxs-lookup"><span data-stu-id="694e0-151">For example, for the generic delegate <xref:System.Func%603>, a *generic_parameter_name* value of "TResult" applies runtime policy to the delegate's return value.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="694e0-152">所有其他特性</span><span class="sxs-lookup"><span data-stu-id="694e0-152">All other attributes</span></span>  
  
|<span data-ttu-id="694e0-153">值</span><span class="sxs-lookup"><span data-stu-id="694e0-153">Value</span></span>|<span data-ttu-id="694e0-154">描述</span><span class="sxs-lookup"><span data-stu-id="694e0-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="694e0-155">policy_setting</span><span class="sxs-lookup"><span data-stu-id="694e0-155">*policy_setting*</span></span>|<span data-ttu-id="694e0-156">该设置将应用到这种策略类型。</span><span class="sxs-lookup"><span data-stu-id="694e0-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="694e0-157">可能值为 `All`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal` 以及 `Required All`。</span><span class="sxs-lookup"><span data-stu-id="694e0-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="694e0-158">有关详细信息，请参阅[运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="694e0-158">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="694e0-159">子元素</span><span class="sxs-lookup"><span data-stu-id="694e0-159">Child Elements</span></span>  
 <span data-ttu-id="694e0-160">无。</span><span class="sxs-lookup"><span data-stu-id="694e0-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="694e0-161">父元素</span><span class="sxs-lookup"><span data-stu-id="694e0-161">Parent Elements</span></span>  
  
|<span data-ttu-id="694e0-162">元素</span><span class="sxs-lookup"><span data-stu-id="694e0-162">Element</span></span>|<span data-ttu-id="694e0-163">描述</span><span class="sxs-lookup"><span data-stu-id="694e0-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="694e0-164">\<Method></span><span class="sxs-lookup"><span data-stu-id="694e0-164">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="694e0-165">将运行时反射策略应用到一个构造函数或方法。</span><span class="sxs-lookup"><span data-stu-id="694e0-165">Applies runtime reflection policy to a constructor or method.</span></span>|  
|[<span data-ttu-id="694e0-166">\<Type></span><span class="sxs-lookup"><span data-stu-id="694e0-166">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="694e0-167">将运行时反射策略应用到一个特定类型，例如一个类或结构。</span><span class="sxs-lookup"><span data-stu-id="694e0-167">Applies runtime reflection policy to a particular type, such as a class or structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="694e0-168">备注</span><span class="sxs-lookup"><span data-stu-id="694e0-168">Remarks</span></span>  
 <span data-ttu-id="694e0-169">`<GenericParameter>` 元素是 [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) 或 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 元素的子元素，用于将策略应用到一个特定的泛型类型参数，该参数由其在泛型类型或方法签名中的名称指定。</span><span class="sxs-lookup"><span data-stu-id="694e0-169">The `<GenericParameter>` element is a child of either the [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) or [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element and is used to apply policy to a particular generic type parameter, which is specified by its name in the generic type or method signature.</span></span>  
  
 <span data-ttu-id="694e0-170">`<GenericParameter>` 元素在同序列化程序一起使用时非常有用。</span><span class="sxs-lookup"><span data-stu-id="694e0-170">The `<GenericParameter>` element is most useful when used with serializers.</span></span> <span data-ttu-id="694e0-171">以下示例使用 `<GenericParameter>` 元素在对 NewtonSoft JSON 序列化程序的 [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) 方法重载的调用中，将策略应用到类型 `T`。</span><span class="sxs-lookup"><span data-stu-id="694e0-171">The following example uses the `<GenericParameter>` element to apply policy to the type `T` in calls to the NewtonSoft JSON serializer's [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) method overloads.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="694e0-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="694e0-172">See Also</span></span>  
 [<span data-ttu-id="694e0-173">\<Method> 元素</span><span class="sxs-lookup"><span data-stu-id="694e0-173">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 [<span data-ttu-id="694e0-174">\<类型 > 元素</span><span class="sxs-lookup"><span data-stu-id="694e0-174">\<Type> Element</span></span>](../../../docs/framework/net-native/type-element-net-native.md)  
 [<span data-ttu-id="694e0-175">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="694e0-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="694e0-176">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="694e0-176">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="694e0-177">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="694e0-177">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
