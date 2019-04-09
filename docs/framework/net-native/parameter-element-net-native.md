---
title: <Parameter> 元素 (.NET Native)
ms.date: 03/30/2017
ms.assetid: 22aaa1f3-596f-4733-93db-f4bcabcb5240
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d2dbff544f991712ad26f2cb12d638801b5a3fb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137873"
---
# <a name="parameter-element-net-native"></a><span data-ttu-id="0fd41-102">\<参数 > 元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="0fd41-102">\<Parameter> Element (.NET Native)</span></span>
<span data-ttu-id="0fd41-103">将反射策略应用到传递到方法的自变量类型。</span><span class="sxs-lookup"><span data-stu-id="0fd41-103">Applies reflection policy to the type of the argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fd41-104">语法</span><span class="sxs-lookup"><span data-stu-id="0fd41-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0fd41-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0fd41-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0fd41-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0fd41-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0fd41-107">特性</span><span class="sxs-lookup"><span data-stu-id="0fd41-107">Attributes</span></span>  
  
|<span data-ttu-id="0fd41-108">特性</span><span class="sxs-lookup"><span data-stu-id="0fd41-108">Attribute</span></span>|<span data-ttu-id="0fd41-109">特性类型</span><span class="sxs-lookup"><span data-stu-id="0fd41-109">Attribute type</span></span>|<span data-ttu-id="0fd41-110">描述</span><span class="sxs-lookup"><span data-stu-id="0fd41-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="0fd41-111">常规</span><span class="sxs-lookup"><span data-stu-id="0fd41-111">General</span></span>|<span data-ttu-id="0fd41-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="0fd41-112">Required attribute.</span></span> <span data-ttu-id="0fd41-113">参数名称。</span><span class="sxs-lookup"><span data-stu-id="0fd41-113">The parameter name.</span></span> <span data-ttu-id="0fd41-114">例如，对于方法签名 `String.CompareTo(Object value)`，`Name` 特性的值为“值”。</span><span class="sxs-lookup"><span data-stu-id="0fd41-114">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
|`Activate`|<span data-ttu-id="0fd41-115">映像</span><span class="sxs-lookup"><span data-stu-id="0fd41-115">Reflection</span></span>|<span data-ttu-id="0fd41-116">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0fd41-116">Optional attribute.</span></span> <span data-ttu-id="0fd41-117">控制运行时对构造函数的访问，以启用实例激活。</span><span class="sxs-lookup"><span data-stu-id="0fd41-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="0fd41-118">映像</span><span class="sxs-lookup"><span data-stu-id="0fd41-118">Reflection</span></span>|<span data-ttu-id="0fd41-119">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0fd41-119">Optional attribute.</span></span> <span data-ttu-id="0fd41-120">控制对有关程序元素信息的查询，但并不启用任何运行时访问。</span><span class="sxs-lookup"><span data-stu-id="0fd41-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="0fd41-121">映像</span><span class="sxs-lookup"><span data-stu-id="0fd41-121">Reflection</span></span>|<span data-ttu-id="0fd41-122">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0fd41-122">Optional attribute.</span></span> <span data-ttu-id="0fd41-123">控制运行时对所有类型成员的访问，包括构造函数、方法、字段、属性和事件，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="0fd41-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="0fd41-124">序列化</span><span class="sxs-lookup"><span data-stu-id="0fd41-124">Serialization</span></span>|<span data-ttu-id="0fd41-125">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0fd41-125">Optional attribute.</span></span> <span data-ttu-id="0fd41-126">控制运行时对构造函数、字段和属性的访问，使类型实例得到序列化和反序列化处理，这是通过库进行的，例如 Newtonsoft JSON 序列化程序。</span><span class="sxs-lookup"><span data-stu-id="0fd41-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="0fd41-127">序列化</span><span class="sxs-lookup"><span data-stu-id="0fd41-127">Serialization</span></span>|<span data-ttu-id="0fd41-128">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0fd41-128">Optional attribute.</span></span> <span data-ttu-id="0fd41-129">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 类的序列化策略。</span><span class="sxs-lookup"><span data-stu-id="0fd41-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="0fd41-130">序列化</span><span class="sxs-lookup"><span data-stu-id="0fd41-130">Serialization</span></span>|<span data-ttu-id="0fd41-131">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0fd41-131">Optional attribute.</span></span> <span data-ttu-id="0fd41-132">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 类的 JSON 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="0fd41-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="0fd41-133">序列化</span><span class="sxs-lookup"><span data-stu-id="0fd41-133">Serialization</span></span>|<span data-ttu-id="0fd41-134">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0fd41-134">Optional attribute.</span></span> <span data-ttu-id="0fd41-135">控制使用 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 类的 XML 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="0fd41-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="0fd41-136">Interop</span><span class="sxs-lookup"><span data-stu-id="0fd41-136">Interop</span></span>|<span data-ttu-id="0fd41-137">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0fd41-137">Optional attribute.</span></span> <span data-ttu-id="0fd41-138">控制将引用类型封送到 WinRT 和 COM 的策略。</span><span class="sxs-lookup"><span data-stu-id="0fd41-138">Controls policy for marshaling reference types to WinRT and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="0fd41-139">Interop</span><span class="sxs-lookup"><span data-stu-id="0fd41-139">Interop</span></span>|<span data-ttu-id="0fd41-140">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0fd41-140">Optional attribute.</span></span> <span data-ttu-id="0fd41-141">控制将委托类型作为函数指针封送到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="0fd41-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="0fd41-142">Interop</span><span class="sxs-lookup"><span data-stu-id="0fd41-142">Interop</span></span>|<span data-ttu-id="0fd41-143">可选特性。</span><span class="sxs-lookup"><span data-stu-id="0fd41-143">Optional attribute.</span></span> <span data-ttu-id="0fd41-144">控制封送处理值类型到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="0fd41-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="0fd41-145">Name 特性</span><span class="sxs-lookup"><span data-stu-id="0fd41-145">Name attribute</span></span>  
  
|<span data-ttu-id="0fd41-146">“值”</span><span class="sxs-lookup"><span data-stu-id="0fd41-146">Value</span></span>|<span data-ttu-id="0fd41-147">描述</span><span class="sxs-lookup"><span data-stu-id="0fd41-147">Description</span></span>|  
|-----------|-----------------|  
|*<span data-ttu-id="0fd41-148">parameter_name</span><span class="sxs-lookup"><span data-stu-id="0fd41-148">parameter_name</span></span>*|<span data-ttu-id="0fd41-149">策略应用到的方法参数的名称。</span><span class="sxs-lookup"><span data-stu-id="0fd41-149">The name of the method parameter to which policy is applied.</span></span> <span data-ttu-id="0fd41-150">例如，对于方法签名 `String.CompareTo(Object value)`，`Name` 特性的值为“值”。</span><span class="sxs-lookup"><span data-stu-id="0fd41-150">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="0fd41-151">所有其他特性</span><span class="sxs-lookup"><span data-stu-id="0fd41-151">All other attributes</span></span>  
  
|<span data-ttu-id="0fd41-152">“值”</span><span class="sxs-lookup"><span data-stu-id="0fd41-152">Value</span></span>|<span data-ttu-id="0fd41-153">描述</span><span class="sxs-lookup"><span data-stu-id="0fd41-153">Description</span></span>|  
|-----------|-----------------|  
|*<span data-ttu-id="0fd41-154">策略_设置</span><span class="sxs-lookup"><span data-stu-id="0fd41-154">policy_setting</span></span>*|<span data-ttu-id="0fd41-155">该设置将应用到这种策略类型。</span><span class="sxs-lookup"><span data-stu-id="0fd41-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="0fd41-156">可能值为 `All`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal` 以及 `Required All`。</span><span class="sxs-lookup"><span data-stu-id="0fd41-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="0fd41-157">有关详细信息，请参阅[运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="0fd41-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0fd41-158">子元素</span><span class="sxs-lookup"><span data-stu-id="0fd41-158">Child Elements</span></span>  
 <span data-ttu-id="0fd41-159">无。</span><span class="sxs-lookup"><span data-stu-id="0fd41-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0fd41-160">父元素</span><span class="sxs-lookup"><span data-stu-id="0fd41-160">Parent Elements</span></span>  
  
|<span data-ttu-id="0fd41-161">元素</span><span class="sxs-lookup"><span data-stu-id="0fd41-161">Element</span></span>|<span data-ttu-id="0fd41-162">描述</span><span class="sxs-lookup"><span data-stu-id="0fd41-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0fd41-163">\<方法 ></span><span class="sxs-lookup"><span data-stu-id="0fd41-163">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="0fd41-164">将运行时反射策略应用到一个构造函数或方法。</span><span class="sxs-lookup"><span data-stu-id="0fd41-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fd41-165">备注</span><span class="sxs-lookup"><span data-stu-id="0fd41-165">Remarks</span></span>  
 <span data-ttu-id="0fd41-166">`<Parameter>` 元素是 [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) 元素的子元素，用于将策略应用于特定方法参数。</span><span class="sxs-lookup"><span data-stu-id="0fd41-166">The `<Parameter>` element is a child of the [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) element and is used to apply policy to a particular method parameter.</span></span> <span data-ttu-id="0fd41-167">特定的方法参数由名称而不是由类型指定。</span><span class="sxs-lookup"><span data-stu-id="0fd41-167">The specific method parameter is specified by name rather than by type.</span></span> <span data-ttu-id="0fd41-168">表示策略类型，比如 `Activate` 或 `Dynamic`，的至少一个特性必须存在。</span><span class="sxs-lookup"><span data-stu-id="0fd41-168">At least one attribute that represents a policy type, such as `Activate` or `Dynamic`, must be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fd41-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fd41-169">See also</span></span>

- [<span data-ttu-id="0fd41-170">\<方法 > 元素</span><span class="sxs-lookup"><span data-stu-id="0fd41-170">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)
- [<span data-ttu-id="0fd41-171">运行时指令 (rd.xml) 配置文件引用</span><span class="sxs-lookup"><span data-stu-id="0fd41-171">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="0fd41-172">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="0fd41-172">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
- [<span data-ttu-id="0fd41-173">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="0fd41-173">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
