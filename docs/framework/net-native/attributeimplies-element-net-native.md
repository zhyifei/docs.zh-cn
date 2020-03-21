---
title: <AttributeImplies>元素 (.NET Native)
ms.date: 03/30/2017
ms.assetid: 82db7193-a860-418b-84fc-fff2fdf2e025
ms.openlocfilehash: 2ab1fdc71bc43f61f69a0d9b7bea7acb35e14ea5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181063"
---
# <a name="attributeimplies-element-net-native"></a><span data-ttu-id="1e7ee-102">\<属性>元素（.NET 本机）</span><span class="sxs-lookup"><span data-stu-id="1e7ee-102">\<AttributeImplies> Element (.NET Native)</span></span>
<span data-ttu-id="1e7ee-103">为包含特性应用的代码元素定义策略。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-103">Defines policy for code elements the containing attribute is applied to.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e7ee-104">语法</span><span class="sxs-lookup"><span data-stu-id="1e7ee-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e7ee-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1e7ee-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1e7ee-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e7ee-107">属性</span><span class="sxs-lookup"><span data-stu-id="1e7ee-107">Attributes</span></span>  
  
|<span data-ttu-id="1e7ee-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="1e7ee-108">Attribute</span></span>|<span data-ttu-id="1e7ee-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="1e7ee-109">Attribute type</span></span>|<span data-ttu-id="1e7ee-110">说明</span><span class="sxs-lookup"><span data-stu-id="1e7ee-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="1e7ee-111">反射</span><span class="sxs-lookup"><span data-stu-id="1e7ee-111">Reflection</span></span>|<span data-ttu-id="1e7ee-112">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-112">Optional attribute.</span></span> <span data-ttu-id="1e7ee-113">控制运行时对构造函数的访问，以启用实例激活。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-113">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="1e7ee-114">反射</span><span class="sxs-lookup"><span data-stu-id="1e7ee-114">Reflection</span></span>|<span data-ttu-id="1e7ee-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-115">Optional attribute.</span></span> <span data-ttu-id="1e7ee-116">控制对有关程序元素信息的查询，但并不启用任何运行时访问。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-116">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="1e7ee-117">反射</span><span class="sxs-lookup"><span data-stu-id="1e7ee-117">Reflection</span></span>|<span data-ttu-id="1e7ee-118">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-118">Optional attribute.</span></span> <span data-ttu-id="1e7ee-119">控制运行时对所有类型成员的访问，包括构造函数、方法、字段、属性和事件，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-119">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="1e7ee-120">序列化</span><span class="sxs-lookup"><span data-stu-id="1e7ee-120">Serialization</span></span>|<span data-ttu-id="1e7ee-121">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-121">Optional attribute.</span></span> <span data-ttu-id="1e7ee-122">控制运行时对构造函数、字段和属性的访问，使类型实例得到序列化和反序列化处理，这是通过库进行的，例如 Newtonsoft JSON 序列化程序。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-122">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="1e7ee-123">序列化</span><span class="sxs-lookup"><span data-stu-id="1e7ee-123">Serialization</span></span>|<span data-ttu-id="1e7ee-124">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-124">Optional attribute.</span></span> <span data-ttu-id="1e7ee-125">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 类的序列化策略。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-125">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="1e7ee-126">序列化</span><span class="sxs-lookup"><span data-stu-id="1e7ee-126">Serialization</span></span>|<span data-ttu-id="1e7ee-127">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-127">Optional attribute.</span></span> <span data-ttu-id="1e7ee-128">控制使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 类的 JSON 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-128">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="1e7ee-129">序列化</span><span class="sxs-lookup"><span data-stu-id="1e7ee-129">Serialization</span></span>|<span data-ttu-id="1e7ee-130">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-130">Optional attribute.</span></span> <span data-ttu-id="1e7ee-131">控制使用 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 类的 XML 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-131">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="1e7ee-132">Interop</span><span class="sxs-lookup"><span data-stu-id="1e7ee-132">Interop</span></span>|<span data-ttu-id="1e7ee-133">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-133">Optional attribute.</span></span> <span data-ttu-id="1e7ee-134">控制封送引用类型到 Windows 运行时和 COM 的策略。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-134">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="1e7ee-135">Interop</span><span class="sxs-lookup"><span data-stu-id="1e7ee-135">Interop</span></span>|<span data-ttu-id="1e7ee-136">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-136">Optional attribute.</span></span> <span data-ttu-id="1e7ee-137">控制将委托类型作为函数指针封送到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-137">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="1e7ee-138">Interop</span><span class="sxs-lookup"><span data-stu-id="1e7ee-138">Interop</span></span>|<span data-ttu-id="1e7ee-139">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-139">Optional attribute.</span></span> <span data-ttu-id="1e7ee-140">控制封送处理值类型到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-140">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="1e7ee-141">所有特性</span><span class="sxs-lookup"><span data-stu-id="1e7ee-141">All attributes</span></span>  
  
|<span data-ttu-id="1e7ee-142">值</span><span class="sxs-lookup"><span data-stu-id="1e7ee-142">Value</span></span>|<span data-ttu-id="1e7ee-143">说明</span><span class="sxs-lookup"><span data-stu-id="1e7ee-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1e7ee-144">*策略_设置*</span><span class="sxs-lookup"><span data-stu-id="1e7ee-144">*policy_setting*</span></span>|<span data-ttu-id="1e7ee-145">该设置将应用到这种策略类型。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-145">The setting to apply to this policy type.</span></span> <span data-ttu-id="1e7ee-146">可能值为 `All`、`Auto`、`Excluded`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal` 以及 `Required All`。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-146">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="1e7ee-147">有关详细信息，请参阅[运行时指令策略设置](runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-147">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e7ee-148">子元素</span><span class="sxs-lookup"><span data-stu-id="1e7ee-148">Child Elements</span></span>  
 <span data-ttu-id="1e7ee-149">无。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e7ee-150">父元素</span><span class="sxs-lookup"><span data-stu-id="1e7ee-150">Parent Elements</span></span>  
  
|<span data-ttu-id="1e7ee-151">元素</span><span class="sxs-lookup"><span data-stu-id="1e7ee-151">Element</span></span>|<span data-ttu-id="1e7ee-152">说明</span><span class="sxs-lookup"><span data-stu-id="1e7ee-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e7ee-153">\<键入></span><span class="sxs-lookup"><span data-stu-id="1e7ee-153">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="1e7ee-154">将反射策略应用到一种类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-154">Applies reflection policy to a type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e7ee-155">备注</span><span class="sxs-lookup"><span data-stu-id="1e7ee-155">Remarks</span></span>  
 <span data-ttu-id="1e7ee-156">如果它的包含类型是一个特性（即，从 `<AttributeImplies>` 中派生出的一个类），则使用 <xref:System.Attribute?displayProperty=nameWithType> 元素。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-156">The `<AttributeImplies>` element is used if its containing type is an attribute (that is, a class derived from <xref:System.Attribute?displayProperty=nameWithType>).</span></span> <span data-ttu-id="1e7ee-157">如果该特性被应用到特定的程序元素，由 `<AttributeImplies>` 元素定义的策略将应用到该程序元素。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-157">If the attribute is applied to a particular program element, the policy defined by the `<AttributeImplies>` element applies to that program element.</span></span>  
  
 <span data-ttu-id="1e7ee-158">反射、序列化和互操作特性都是可选项，但必须存在至少一项。</span><span class="sxs-lookup"><span data-stu-id="1e7ee-158">The reflection, serialization, and interop attributes are all optional, although at least one should be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e7ee-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e7ee-159">See also</span></span>

- [<span data-ttu-id="1e7ee-160">\<类型>元素</span><span class="sxs-lookup"><span data-stu-id="1e7ee-160">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="1e7ee-161">运行时指令 (rd.xml) 配置文件引用</span><span class="sxs-lookup"><span data-stu-id="1e7ee-161">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="1e7ee-162">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="1e7ee-162">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="1e7ee-163">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="1e7ee-163">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
