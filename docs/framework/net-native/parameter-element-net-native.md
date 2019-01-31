---
title: <Parameter>元素 (.NET Native)
ms.date: 03/30/2017
ms.assetid: 22aaa1f3-596f-4733-93db-f4bcabcb5240
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c18919a6c48c251138a3d5e88079d3383979ef1a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266398"
---
# <a name="parameter-element-net-native"></a><span data-ttu-id="790e7-102">\<参数 > 元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="790e7-102">\<Parameter> Element (.NET Native)</span></span>
<span data-ttu-id="790e7-103">将反射策略应用到传递到方法的自变量类型。</span><span class="sxs-lookup"><span data-stu-id="790e7-103">Applies reflection policy to the type of the argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="790e7-104">语法</span><span class="sxs-lookup"><span data-stu-id="790e7-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="790e7-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="790e7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="790e7-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="790e7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="790e7-107">特性</span><span class="sxs-lookup"><span data-stu-id="790e7-107">Attributes</span></span>  
  
|<span data-ttu-id="790e7-108">特性</span><span class="sxs-lookup"><span data-stu-id="790e7-108">Attribute</span></span>|<span data-ttu-id="790e7-109">特性类型</span><span class="sxs-lookup"><span data-stu-id="790e7-109">Attribute type</span></span>|<span data-ttu-id="790e7-110">描述</span><span class="sxs-lookup"><span data-stu-id="790e7-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="790e7-111">常规</span><span class="sxs-lookup"><span data-stu-id="790e7-111">General</span></span>|<span data-ttu-id="790e7-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="790e7-112">Required attribute.</span></span> <span data-ttu-id="790e7-113">参数名称。</span><span class="sxs-lookup"><span data-stu-id="790e7-113">The parameter name.</span></span> <span data-ttu-id="790e7-114">例如，对于方法签名 `String.CompareTo(Object value)`，`Name` 特性的值为“值”。</span><span class="sxs-lookup"><span data-stu-id="790e7-114">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
|`Activate`|<span data-ttu-id="790e7-115">映像</span><span class="sxs-lookup"><span data-stu-id="790e7-115">Reflection</span></span>|<span data-ttu-id="790e7-116">可选特性。</span><span class="sxs-lookup"><span data-stu-id="790e7-116">Optional attribute.</span></span> <span data-ttu-id="790e7-117">控制运行时对构造函数的访问，以启用实例激活。</span><span class="sxs-lookup"><span data-stu-id="790e7-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="790e7-118">映像</span><span class="sxs-lookup"><span data-stu-id="790e7-118">Reflection</span></span>|<span data-ttu-id="790e7-119">可选特性。</span><span class="sxs-lookup"><span data-stu-id="790e7-119">Optional attribute.</span></span> <span data-ttu-id="790e7-120">控制对有关程序元素信息的查询，但并不启用任何运行时访问。</span><span class="sxs-lookup"><span data-stu-id="790e7-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="790e7-121">映像</span><span class="sxs-lookup"><span data-stu-id="790e7-121">Reflection</span></span>|<span data-ttu-id="790e7-122">可选特性。</span><span class="sxs-lookup"><span data-stu-id="790e7-122">Optional attribute.</span></span> <span data-ttu-id="790e7-123">控制运行时对所有类型成员的访问，包括构造函数、方法、字段、属性和事件，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="790e7-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="790e7-124">序列化</span><span class="sxs-lookup"><span data-stu-id="790e7-124">Serialization</span></span>|<span data-ttu-id="790e7-125">可选特性。</span><span class="sxs-lookup"><span data-stu-id="790e7-125">Optional attribute.</span></span> <span data-ttu-id="790e7-126">控制运行时对构造函数、字段和属性的访问，使类型实例得到序列化和反序列化处理，这是通过库进行的，例如 Newtonsoft JSON 序列化程序。</span><span class="sxs-lookup"><span data-stu-id="790e7-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="790e7-127">序列化</span><span class="sxs-lookup"><span data-stu-id="790e7-127">Serialization</span></span>|<span data-ttu-id="790e7-128">可选特性。</span><span class="sxs-lookup"><span data-stu-id="790e7-128">Optional attribute.</span></span> <span data-ttu-id="790e7-129">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 类的序列化策略。</span><span class="sxs-lookup"><span data-stu-id="790e7-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="790e7-130">序列化</span><span class="sxs-lookup"><span data-stu-id="790e7-130">Serialization</span></span>|<span data-ttu-id="790e7-131">可选特性。</span><span class="sxs-lookup"><span data-stu-id="790e7-131">Optional attribute.</span></span> <span data-ttu-id="790e7-132">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 类的 JSON 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="790e7-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="790e7-133">序列化</span><span class="sxs-lookup"><span data-stu-id="790e7-133">Serialization</span></span>|<span data-ttu-id="790e7-134">可选特性。</span><span class="sxs-lookup"><span data-stu-id="790e7-134">Optional attribute.</span></span> <span data-ttu-id="790e7-135">控制使用 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 类的 XML 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="790e7-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="790e7-136">Interop</span><span class="sxs-lookup"><span data-stu-id="790e7-136">Interop</span></span>|<span data-ttu-id="790e7-137">可选特性。</span><span class="sxs-lookup"><span data-stu-id="790e7-137">Optional attribute.</span></span> <span data-ttu-id="790e7-138">控制将引用类型封送到 WinRT 和 COM 的策略。</span><span class="sxs-lookup"><span data-stu-id="790e7-138">Controls policy for marshaling reference types to WinRT and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="790e7-139">Interop</span><span class="sxs-lookup"><span data-stu-id="790e7-139">Interop</span></span>|<span data-ttu-id="790e7-140">可选特性。</span><span class="sxs-lookup"><span data-stu-id="790e7-140">Optional attribute.</span></span> <span data-ttu-id="790e7-141">控制将委托类型作为函数指针封送到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="790e7-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="790e7-142">Interop</span><span class="sxs-lookup"><span data-stu-id="790e7-142">Interop</span></span>|<span data-ttu-id="790e7-143">可选特性。</span><span class="sxs-lookup"><span data-stu-id="790e7-143">Optional attribute.</span></span> <span data-ttu-id="790e7-144">控制封送处理值类型到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="790e7-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="790e7-145">Name 特性</span><span class="sxs-lookup"><span data-stu-id="790e7-145">Name attribute</span></span>  
  
|<span data-ttu-id="790e7-146">值</span><span class="sxs-lookup"><span data-stu-id="790e7-146">Value</span></span>|<span data-ttu-id="790e7-147">描述</span><span class="sxs-lookup"><span data-stu-id="790e7-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="790e7-148">parameter_name</span><span class="sxs-lookup"><span data-stu-id="790e7-148">*parameter_name*</span></span>|<span data-ttu-id="790e7-149">策略应用到的方法参数的名称。</span><span class="sxs-lookup"><span data-stu-id="790e7-149">The name of the method parameter to which policy is applied.</span></span> <span data-ttu-id="790e7-150">例如，对于方法签名 `String.CompareTo(Object value)`，`Name` 特性的值为“值”。</span><span class="sxs-lookup"><span data-stu-id="790e7-150">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="790e7-151">所有其他特性</span><span class="sxs-lookup"><span data-stu-id="790e7-151">All other attributes</span></span>  
  
|<span data-ttu-id="790e7-152">值</span><span class="sxs-lookup"><span data-stu-id="790e7-152">Value</span></span>|<span data-ttu-id="790e7-153">描述</span><span class="sxs-lookup"><span data-stu-id="790e7-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="790e7-154">policy_setting</span><span class="sxs-lookup"><span data-stu-id="790e7-154">*policy_setting*</span></span>|<span data-ttu-id="790e7-155">该设置将应用到这种策略类型。</span><span class="sxs-lookup"><span data-stu-id="790e7-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="790e7-156">可能值为 `All`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal` 以及 `Required All`。</span><span class="sxs-lookup"><span data-stu-id="790e7-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="790e7-157">有关详细信息，请参阅[运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="790e7-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="790e7-158">子元素</span><span class="sxs-lookup"><span data-stu-id="790e7-158">Child Elements</span></span>  
 <span data-ttu-id="790e7-159">无。</span><span class="sxs-lookup"><span data-stu-id="790e7-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="790e7-160">父元素</span><span class="sxs-lookup"><span data-stu-id="790e7-160">Parent Elements</span></span>  
  
|<span data-ttu-id="790e7-161">元素</span><span class="sxs-lookup"><span data-stu-id="790e7-161">Element</span></span>|<span data-ttu-id="790e7-162">描述</span><span class="sxs-lookup"><span data-stu-id="790e7-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="790e7-163">\<Method></span><span class="sxs-lookup"><span data-stu-id="790e7-163">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="790e7-164">将运行时反射策略应用到一个构造函数或方法。</span><span class="sxs-lookup"><span data-stu-id="790e7-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="790e7-165">备注</span><span class="sxs-lookup"><span data-stu-id="790e7-165">Remarks</span></span>  
 <span data-ttu-id="790e7-166">`<Parameter>` 元素是 [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) 元素的子元素，用于将策略应用于特定方法参数。</span><span class="sxs-lookup"><span data-stu-id="790e7-166">The `<Parameter>` element is a child of the [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) element and is used to apply policy to a particular method parameter.</span></span> <span data-ttu-id="790e7-167">特定的方法参数由名称而不是由类型指定。</span><span class="sxs-lookup"><span data-stu-id="790e7-167">The specific method parameter is specified by name rather than by type.</span></span> <span data-ttu-id="790e7-168">表示策略类型，比如 `Activate` 或 `Dynamic`，的至少一个特性必须存在。</span><span class="sxs-lookup"><span data-stu-id="790e7-168">At least one attribute that represents a policy type, such as `Activate` or `Dynamic`, must be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="790e7-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="790e7-169">See also</span></span>
- [<span data-ttu-id="790e7-170">\<Method> 元素</span><span class="sxs-lookup"><span data-stu-id="790e7-170">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)
- [<span data-ttu-id="790e7-171">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="790e7-171">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="790e7-172">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="790e7-172">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
- [<span data-ttu-id="790e7-173">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="790e7-173">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
