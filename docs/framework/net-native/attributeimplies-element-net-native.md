---
title: "&lt;特性暗示&gt;元素 (.NET Native)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82db7193-a860-418b-84fc-fff2fdf2e025
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2fcb3f476a00f00e00eeea90db75699c2c4cdf76
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="ltattributeimpliesgt-element-net-native"></a><span data-ttu-id="4aca5-102">&lt;特性暗示&gt;元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="4aca5-102">&lt;AttributeImplies&gt; Element (.NET Native)</span></span>
<span data-ttu-id="4aca5-103">为包含特性应用的代码元素定义策略。</span><span class="sxs-lookup"><span data-stu-id="4aca5-103">Defines policy for code elements the containing attribute is applied to.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aca5-104">语法</span><span class="sxs-lookup"><span data-stu-id="4aca5-104">Syntax</span></span>  
  
```xml  
<AttributeImplies Activate="policy_type"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4aca5-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4aca5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4aca5-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4aca5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4aca5-107">特性</span><span class="sxs-lookup"><span data-stu-id="4aca5-107">Attributes</span></span>  
  
|<span data-ttu-id="4aca5-108">特性</span><span class="sxs-lookup"><span data-stu-id="4aca5-108">Attribute</span></span>|<span data-ttu-id="4aca5-109">特性类型</span><span class="sxs-lookup"><span data-stu-id="4aca5-109">Attribute type</span></span>|<span data-ttu-id="4aca5-110">描述</span><span class="sxs-lookup"><span data-stu-id="4aca5-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="4aca5-111">映像</span><span class="sxs-lookup"><span data-stu-id="4aca5-111">Reflection</span></span>|<span data-ttu-id="4aca5-112">可选特性。</span><span class="sxs-lookup"><span data-stu-id="4aca5-112">Optional attribute.</span></span> <span data-ttu-id="4aca5-113">控制运行时对构造函数的访问，以启用实例激活。</span><span class="sxs-lookup"><span data-stu-id="4aca5-113">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="4aca5-114">映像</span><span class="sxs-lookup"><span data-stu-id="4aca5-114">Reflection</span></span>|<span data-ttu-id="4aca5-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="4aca5-115">Optional attribute.</span></span> <span data-ttu-id="4aca5-116">控制对有关程序元素信息的查询，但并不启用任何运行时访问。</span><span class="sxs-lookup"><span data-stu-id="4aca5-116">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="4aca5-117">映像</span><span class="sxs-lookup"><span data-stu-id="4aca5-117">Reflection</span></span>|<span data-ttu-id="4aca5-118">可选特性。</span><span class="sxs-lookup"><span data-stu-id="4aca5-118">Optional attribute.</span></span> <span data-ttu-id="4aca5-119">控制运行时对所有类型成员的访问，包括构造函数、方法、字段、属性和事件，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="4aca5-119">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="4aca5-120">序列化</span><span class="sxs-lookup"><span data-stu-id="4aca5-120">Serialization</span></span>|<span data-ttu-id="4aca5-121">可选特性。</span><span class="sxs-lookup"><span data-stu-id="4aca5-121">Optional attribute.</span></span> <span data-ttu-id="4aca5-122">控制运行时对构造函数、字段和属性的访问，使类型实例得到序列化和反序列化处理，这是通过库进行的，例如 Newtonsoft JSON 序列化程序。</span><span class="sxs-lookup"><span data-stu-id="4aca5-122">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="4aca5-123">序列化</span><span class="sxs-lookup"><span data-stu-id="4aca5-123">Serialization</span></span>|<span data-ttu-id="4aca5-124">可选特性。</span><span class="sxs-lookup"><span data-stu-id="4aca5-124">Optional attribute.</span></span> <span data-ttu-id="4aca5-125">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> 类的序列化策略。</span><span class="sxs-lookup"><span data-stu-id="4aca5-125">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="4aca5-126">序列化</span><span class="sxs-lookup"><span data-stu-id="4aca5-126">Serialization</span></span>|<span data-ttu-id="4aca5-127">可选特性。</span><span class="sxs-lookup"><span data-stu-id="4aca5-127">Optional attribute.</span></span> <span data-ttu-id="4aca5-128">控制使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> 类的 JSON 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="4aca5-128">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="4aca5-129">序列化</span><span class="sxs-lookup"><span data-stu-id="4aca5-129">Serialization</span></span>|<span data-ttu-id="4aca5-130">可选特性。</span><span class="sxs-lookup"><span data-stu-id="4aca5-130">Optional attribute.</span></span> <span data-ttu-id="4aca5-131">控制使用 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> 类的 XML 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="4aca5-131">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="4aca5-132">Interop</span><span class="sxs-lookup"><span data-stu-id="4aca5-132">Interop</span></span>|<span data-ttu-id="4aca5-133">可选特性。</span><span class="sxs-lookup"><span data-stu-id="4aca5-133">Optional attribute.</span></span> <span data-ttu-id="4aca5-134">控制封送引用类型到 Windows 运行时和 COM 的策略。</span><span class="sxs-lookup"><span data-stu-id="4aca5-134">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="4aca5-135">Interop</span><span class="sxs-lookup"><span data-stu-id="4aca5-135">Interop</span></span>|<span data-ttu-id="4aca5-136">可选特性。</span><span class="sxs-lookup"><span data-stu-id="4aca5-136">Optional attribute.</span></span> <span data-ttu-id="4aca5-137">控制将委托类型作为函数指针封送到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="4aca5-137">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="4aca5-138">Interop</span><span class="sxs-lookup"><span data-stu-id="4aca5-138">Interop</span></span>|<span data-ttu-id="4aca5-139">可选特性。</span><span class="sxs-lookup"><span data-stu-id="4aca5-139">Optional attribute.</span></span> <span data-ttu-id="4aca5-140">控制封送处理值类型到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="4aca5-140">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="4aca5-141">所有特性</span><span class="sxs-lookup"><span data-stu-id="4aca5-141">All attributes</span></span>  
  
|<span data-ttu-id="4aca5-142">值</span><span class="sxs-lookup"><span data-stu-id="4aca5-142">Value</span></span>|<span data-ttu-id="4aca5-143">描述</span><span class="sxs-lookup"><span data-stu-id="4aca5-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4aca5-144">policy_setting</span><span class="sxs-lookup"><span data-stu-id="4aca5-144">*policy_setting*</span></span>|<span data-ttu-id="4aca5-145">该设置将应用到这种策略类型。</span><span class="sxs-lookup"><span data-stu-id="4aca5-145">The setting to apply to this policy type.</span></span> <span data-ttu-id="4aca5-146">可能值为 `All`、`Auto`、`Excluded`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal` 以及 `Required All`。</span><span class="sxs-lookup"><span data-stu-id="4aca5-146">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="4aca5-147">有关详细信息，请参阅[运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="4aca5-147">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4aca5-148">子元素</span><span class="sxs-lookup"><span data-stu-id="4aca5-148">Child Elements</span></span>  
 <span data-ttu-id="4aca5-149">无。</span><span class="sxs-lookup"><span data-stu-id="4aca5-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4aca5-150">父元素</span><span class="sxs-lookup"><span data-stu-id="4aca5-150">Parent Elements</span></span>  
  
|<span data-ttu-id="4aca5-151">元素</span><span class="sxs-lookup"><span data-stu-id="4aca5-151">Element</span></span>|<span data-ttu-id="4aca5-152">描述</span><span class="sxs-lookup"><span data-stu-id="4aca5-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4aca5-153">\<Type></span><span class="sxs-lookup"><span data-stu-id="4aca5-153">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="4aca5-154">将反射策略应用到一种类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="4aca5-154">Applies reflection policy to a type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4aca5-155">备注</span><span class="sxs-lookup"><span data-stu-id="4aca5-155">Remarks</span></span>  
 <span data-ttu-id="4aca5-156">如果它的包含类型是一个特性（即，从 `<AttributeImplies>` 中派生出的一个类），则使用 <xref:System.Attribute?displayProperty=fullName> 元素。</span><span class="sxs-lookup"><span data-stu-id="4aca5-156">The `<AttributeImplies>` element is used if its containing type is an attribute (that is, a class derived from <xref:System.Attribute?displayProperty=fullName>).</span></span> <span data-ttu-id="4aca5-157">如果该特性被应用到特定的程序元素，由 `<AttributeImplies>` 元素定义的策略将应用到该程序元素。</span><span class="sxs-lookup"><span data-stu-id="4aca5-157">If the attribute is applied to a particular program element, the policy defined by the `<AttributeImplies>` element applies to that program element.</span></span>  
  
 <span data-ttu-id="4aca5-158">反射、序列化和互操作特性都是可选项，但必须存在至少一项。</span><span class="sxs-lookup"><span data-stu-id="4aca5-158">The reflection, serialization, and interop attributes are all optional, although at least one should be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aca5-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4aca5-159">See Also</span></span>  
 <span data-ttu-id="4aca5-160">[\<Type> 元素](../../../docs/framework/net-native/type-element-net-native.md) </span><span class="sxs-lookup"><span data-stu-id="4aca5-160">[\<Type> Element](../../../docs/framework/net-native/type-element-net-native.md) </span></span>  
 <span data-ttu-id="4aca5-161">[运行时指令 (rd.xml) 配置文件参考](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4aca5-161">[Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) </span></span>  
 <span data-ttu-id="4aca5-162">[运行时指令元素](../../../docs/framework/net-native/runtime-directive-elements.md) </span><span class="sxs-lookup"><span data-stu-id="4aca5-162">[Runtime Directive Elements](../../../docs/framework/net-native/runtime-directive-elements.md) </span></span>  
 [<span data-ttu-id="4aca5-163">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="4aca5-163">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)

