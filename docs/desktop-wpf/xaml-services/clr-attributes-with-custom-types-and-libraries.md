---
title: 自定义类型和库的 XAML 相关 CLR 特性
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: 5481d02e4d393312fa0f0dd13b45c54acc567e13
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432982"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a><span data-ttu-id="1819c-102">用于自定义类型和库的与 XAML 相关的 CLR 属性</span><span class="sxs-lookup"><span data-stu-id="1819c-102">XAML-related CLR attributes for custom types and libraries</span></span>

<span data-ttu-id="1819c-103">本主题介绍由 .NET XAML 服务定义的通用语言运行时 （CLR） 属性。</span><span class="sxs-lookup"><span data-stu-id="1819c-103">This topic describes the common language runtime (CLR) attributes that are defined by .NET XAML Services.</span></span> <span data-ttu-id="1819c-104">它还描述了在 .NET 中定义的其他 CLR 属性，这些属性具有与 XAML 相关的方案，用于应用程序到程序集或类型。</span><span class="sxs-lookup"><span data-stu-id="1819c-104">It also describes other CLR attributes that are defined in .NET that have a XAML-related scenario for application to assemblies or types.</span></span> <span data-ttu-id="1819c-105">将这些 CLR 属性的程序集、类型或成员归为具有 XAML 类型系统信息，这些信息与您的类型相关。</span><span class="sxs-lookup"><span data-stu-id="1819c-105">Attributing assemblies, types, or members with these CLR attributes provides XAML type system information related to your types.</span></span> <span data-ttu-id="1819c-106">信息提供给使用 .NET XAML 服务直接或通过专用 XAML 读取器和 XAML 编写器处理 XAML 节点流的任何 XAML 使用者。</span><span class="sxs-lookup"><span data-stu-id="1819c-106">Information is provided to any XAML consumer that uses .NET XAML Services for processing the XAML node stream directly or through the dedicated XAML readers and XAML writers.</span></span>

## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a><span data-ttu-id="1819c-107">用于自定义类型和自定义成员的 XAML 相关 CLR 属性</span><span class="sxs-lookup"><span data-stu-id="1819c-107">XAML-Related CLR Attributes for Custom Types and Custom Members</span></span>

<span data-ttu-id="1819c-108">使用 CLR 属性意味着您使用整个 CLR 来定义类型，否则此类属性不可用。</span><span class="sxs-lookup"><span data-stu-id="1819c-108">Using CLR attributes entails that you are using the overall CLR to define your types, otherwise such attributes are not available.</span></span> <span data-ttu-id="1819c-109">如果使用 CLR 定义类型备份，则 .NET XAML 服务 XAML 编写器使用的默认 XAML 架构上下文可以通过反射来读取 CLR 归因。</span><span class="sxs-lookup"><span data-stu-id="1819c-109">If you use the CLR to define type backing, then the default XAML schema context used by .NET XAML Services XAML writers can read CLR attribution through reflection against backing assemblies.</span></span>

<span data-ttu-id="1819c-110">以下各节介绍可应用于自定义类型或自定义成员的与 XAML 相关的属性。</span><span class="sxs-lookup"><span data-stu-id="1819c-110">The following sections describe the XAML-related attributes that you can apply to custom types or custom members.</span></span> <span data-ttu-id="1819c-111">每个 CLR 属性都传达与 XAML 类型系统相关的信息。</span><span class="sxs-lookup"><span data-stu-id="1819c-111">Each CLR attribute communicates information that is relevant to a XAML type system.</span></span> <span data-ttu-id="1819c-112">在加载路径中，属性化信息要么帮助 XAML 读取器形成有效的 XAML 节点流，要么帮助 XAML 编写器生成有效的对象图。</span><span class="sxs-lookup"><span data-stu-id="1819c-112">In the load path, the attributed information either helps the XAML reader form a valid XAML node stream, or it helps the XAML writer produce a valid object graph.</span></span> <span data-ttu-id="1819c-113">在保存路径中，属性化信息要么帮助 XAML 读取器形成有效的 XAML 节点流，从而重新构成 XAML 类型系统信息;或者声明 XAML 编写器或其他 XAML 使用者的序列化提示或要求。</span><span class="sxs-lookup"><span data-stu-id="1819c-113">In the save path, the attributed information either helps the XAML reader form a valid XAML node stream that reconstitutes XAML type system information; or it declares serialization hints or requirements for the XAML writer or other XAML consumers.</span></span>

### <a name="ambientattribute"></a><span data-ttu-id="1819c-114">环境属性</span><span class="sxs-lookup"><span data-stu-id="1819c-114">AmbientAttribute</span></span>

<span data-ttu-id="1819c-115">**参考文档：**<xref:System.Windows.Markup.AmbientAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-115">**Reference Documentation:** <xref:System.Windows.Markup.AmbientAttribute></span></span>

<span data-ttu-id="1819c-116">**适用于：** 支持可附加属性的`get`类、属性或访问器成员。</span><span class="sxs-lookup"><span data-stu-id="1819c-116">**Applies to:** Class, property, or `get` accessor members that support attachable properties.</span></span>

<span data-ttu-id="1819c-117">**参数：** 没有</span><span class="sxs-lookup"><span data-stu-id="1819c-117">**Arguments:** None</span></span>

<span data-ttu-id="1819c-118"><xref:System.Windows.Markup.AmbientAttribute>指示属性或采用属性类型的所有属性应在 XAML 中的环境属性概念下解释。</span><span class="sxs-lookup"><span data-stu-id="1819c-118"><xref:System.Windows.Markup.AmbientAttribute> indicates that the property, or all properties that take the attributed type, should be interpreted under the ambient property concept in XAML.</span></span> <span data-ttu-id="1819c-119">环境概念涉及 XAML 处理器如何确定成员的类型所有者。</span><span class="sxs-lookup"><span data-stu-id="1819c-119">The ambient concept relates to how XAML processors determine type owners of members.</span></span> <span data-ttu-id="1819c-120">环境属性是一个属性，在创建对象图时，该值在解析器上下文中可用，但在创建的直接 XAML 节点集时暂停典型的类型成员查找的属性。</span><span class="sxs-lookup"><span data-stu-id="1819c-120">An ambient property is a property where the value is expected to be available in the parser context when creating an object graph, but where typical type-member lookup is suspended for the immediate XAML node set being created.</span></span>

<span data-ttu-id="1819c-121">环境概念可以应用于可附加成员，这些成员在 CLR 属性定义方面不表示为属性<xref:System.AttributeTargets>。</span><span class="sxs-lookup"><span data-stu-id="1819c-121">The ambient concept can be applied to attachable members, which are not represented as properties in terms of how CLR attribution defines <xref:System.AttributeTargets>.</span></span> <span data-ttu-id="1819c-122">方法归因用应仅适用于支持 XAML 可附加用法的`get`访问者。</span><span class="sxs-lookup"><span data-stu-id="1819c-122">The method attribution usage should be applied only for a `get` accessor that supports attachable usage for XAML.</span></span>

### <a name="constructorargumentattribute"></a><span data-ttu-id="1819c-123">构造函数参数属性</span><span class="sxs-lookup"><span data-stu-id="1819c-123">ConstructorArgumentAttribute</span></span>

<span data-ttu-id="1819c-124">**参考文档：**  <xref:System.Windows.Markup.ConstructorArgumentAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-124">**Reference Documentation:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute></span></span>

<span data-ttu-id="1819c-125">**适用于：** 类</span><span class="sxs-lookup"><span data-stu-id="1819c-125">**Applies to:** Class</span></span>

<span data-ttu-id="1819c-126">**参数：** 指定与单个构造函数参数匹配的属性名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="1819c-126">**Arguments:** A string that specifies the name of the property that matches a single constructor argument.</span></span>

<span data-ttu-id="1819c-127"><xref:System.Windows.Markup.ConstructorArgumentAttribute>指定可以使用非参数构造函数语法初始化对象，并且指定名称的属性提供构造信息。</span><span class="sxs-lookup"><span data-stu-id="1819c-127"><xref:System.Windows.Markup.ConstructorArgumentAttribute> specifies that an object can be initialized by using a non-parameterless constructor syntax, and that a property of the specified name supplies construction information.</span></span> <span data-ttu-id="1819c-128">此信息主要用于 XAML 序列化。</span><span class="sxs-lookup"><span data-stu-id="1819c-128">This information is primarily for XAML serialization.</span></span> <span data-ttu-id="1819c-129">有关详细信息，请参阅 <xref:System.Windows.Markup.ConstructorArgumentAttribute>。</span><span class="sxs-lookup"><span data-stu-id="1819c-129">For more information, see <xref:System.Windows.Markup.ConstructorArgumentAttribute>.</span></span>

### <a name="contentpropertyattribute"></a><span data-ttu-id="1819c-130">内容属性属性</span><span class="sxs-lookup"><span data-stu-id="1819c-130">ContentPropertyAttribute</span></span>

<span data-ttu-id="1819c-131">**参考文档：**  <xref:System.Windows.Markup.ContentPropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-131">**Reference Documentation:**  <xref:System.Windows.Markup.ContentPropertyAttribute></span></span>

<span data-ttu-id="1819c-132">**适用于：** 类</span><span class="sxs-lookup"><span data-stu-id="1819c-132">**Applies to:** Class</span></span>

<span data-ttu-id="1819c-133">**参数：** 指定属性类型成员名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="1819c-133">**Arguments:** A string that specifies the name of a member of the attributed type.</span></span>

<span data-ttu-id="1819c-134"><xref:System.Windows.Markup.ContentPropertyAttribute>指示参数命名的属性应用作该类型的 XAML 内容属性。</span><span class="sxs-lookup"><span data-stu-id="1819c-134"><xref:System.Windows.Markup.ContentPropertyAttribute> indicates that the property as named by the argument should serve as the XAML content property for that type.</span></span> <span data-ttu-id="1819c-135">XAML 内容属性定义将继承到可分配给定义类型的所有派生类型。</span><span class="sxs-lookup"><span data-stu-id="1819c-135">The XAML content property definition inherits to all derived types that are assignable to the defining type.</span></span> <span data-ttu-id="1819c-136">可以通过应用于<xref:System.Windows.Markup.ContentPropertyAttribute>特定派生类型来覆盖特定派生类型上的定义。</span><span class="sxs-lookup"><span data-stu-id="1819c-136">You can override the definition on a specific derived type by applying <xref:System.Windows.Markup.ContentPropertyAttribute> on the specific derived type.</span></span>

<span data-ttu-id="1819c-137">对于用作 XAML 内容属性的属性，可以在 XAML 用法中省略该属性的属性元素标记。</span><span class="sxs-lookup"><span data-stu-id="1819c-137">For the property that serves as the XAML content property, property element tagging for the property can be omitted in the XAML usage.</span></span> <span data-ttu-id="1819c-138">通常，您指定 XAML 内容属性，这些属性可为您的内容和包含模型推广简化的 XAML 标记。</span><span class="sxs-lookup"><span data-stu-id="1819c-138">Typically, you designate XAML content properties that promote a streamlined XAML markup for your content and containment models.</span></span> <span data-ttu-id="1819c-139">由于只能将一个成员指定为 XAML 内容属性，因此您有时可以选择将某种类型的多个容器属性中的哪一个指定为 XAML 内容属性。</span><span class="sxs-lookup"><span data-stu-id="1819c-139">Because only one member can be designated as the XAML content property, you sometimes have design choices to make regarding which of several container properties of a type should be designated as the XAML content property.</span></span> <span data-ttu-id="1819c-140">其他容器属性必须与显式属性元素一起使用。</span><span class="sxs-lookup"><span data-stu-id="1819c-140">The other container properties must be used with explicit property elements.</span></span>

<span data-ttu-id="1819c-141">在 XAML 节点流中，XAML 内容`StartMember`属性`EndMember`仍使用 的属性的名称生成和节点<xref:System.Xaml.XamlMember>。</span><span class="sxs-lookup"><span data-stu-id="1819c-141">In the XAML node stream, XAML content properties still produce `StartMember` and `EndMember` nodes, using the name of the property for the <xref:System.Xaml.XamlMember>.</span></span> <span data-ttu-id="1819c-142">要确定成员是否为 XAML 内容属性，请从<xref:System.Xaml.XamlType>`StartObject`位置检查值并获取 的值<xref:System.Xaml.XamlType.ContentProperty%2A>。</span><span class="sxs-lookup"><span data-stu-id="1819c-142">To determine whether a member is the XAML content property, examine the <xref:System.Xaml.XamlType> value from the `StartObject` position and obtain the value of <xref:System.Xaml.XamlType.ContentProperty%2A>.</span></span>

### <a name="contentwrapperattribute"></a><span data-ttu-id="1819c-143">内容包装属性</span><span class="sxs-lookup"><span data-stu-id="1819c-143">ContentWrapperAttribute</span></span>

<span data-ttu-id="1819c-144">**参考文档：**  <xref:System.Windows.Markup.ContentWrapperAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-144">**Reference Documentation:**  <xref:System.Windows.Markup.ContentWrapperAttribute></span></span>

<span data-ttu-id="1819c-145">**适用于：** 类，特别是集合类型。</span><span class="sxs-lookup"><span data-stu-id="1819c-145">**Applies to:** Class, specifically collection types.</span></span>

<span data-ttu-id="1819c-146">**参数：** 指定<xref:System.Type>用作外国内容内容包装类型的类型的类型。</span><span class="sxs-lookup"><span data-stu-id="1819c-146">**Arguments:** A <xref:System.Type> that specifies the type to use as the content wrapper type for foreign content.</span></span>

<span data-ttu-id="1819c-147"><xref:System.Windows.Markup.ContentWrapperAttribute>指定将用于包装外来内容的关联集合类型的一个或多个类型。</span><span class="sxs-lookup"><span data-stu-id="1819c-147"><xref:System.Windows.Markup.ContentWrapperAttribute> specifies one or more types on the associated collection type that will be used to wrap foreign content.</span></span> <span data-ttu-id="1819c-148">外国内容是指内容属性类型的类型系统约束未捕获拥有类型的 XAML 使用的所有可能内容情形的情况。</span><span class="sxs-lookup"><span data-stu-id="1819c-148">Foreign content refers to cases where the type system constraints on the type of the content property do not capture all of the possible content cases that XAML usage for the owning type would support.</span></span> <span data-ttu-id="1819c-149">例如，对特定类型内容的 XAML 支持可能支持强类型泛型<xref:System.Collections.ObjectModel.Collection%601>中的字符串。</span><span class="sxs-lookup"><span data-stu-id="1819c-149">For example, XAML support for content of a particular type might support strings in a strongly typed generic <xref:System.Collections.ObjectModel.Collection%601>.</span></span> <span data-ttu-id="1819c-150">内容包装器可用于将预先存在的标记约定迁移到 XAML 的集合可分配值的概念中，例如迁移与文本相关的内容模型。</span><span class="sxs-lookup"><span data-stu-id="1819c-150">Content wrappers are useful for migrating pre-existing markup conventions into XAML's conception of assignable values for collections, such as migrating text-related content models.</span></span>

<span data-ttu-id="1819c-151">要指定多个内容包装类型，请多次应用该属性。</span><span class="sxs-lookup"><span data-stu-id="1819c-151">To specify more than one content wrapper type, apply the attribute multiple times.</span></span>

### <a name="dependsonattribute"></a><span data-ttu-id="1819c-152">依赖属性</span><span class="sxs-lookup"><span data-stu-id="1819c-152">DependsOnAttribute</span></span>

<span data-ttu-id="1819c-153">**参考文档：**  <xref:System.Windows.Markup.DependsOnAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-153">**Reference Documentation:**  <xref:System.Windows.Markup.DependsOnAttribute></span></span>

<span data-ttu-id="1819c-154">**适用于：** 财产</span><span class="sxs-lookup"><span data-stu-id="1819c-154">**Applies to:** Property</span></span>

<span data-ttu-id="1819c-155">**参数：** 指定属性类型另一个成员名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="1819c-155">**Arguments:** A string that specifies the name of another member of the attributed type.</span></span>

<span data-ttu-id="1819c-156"><xref:System.Windows.Markup.DependsOnAttribute>指示属性属性取决于另一个属性的值。</span><span class="sxs-lookup"><span data-stu-id="1819c-156"><xref:System.Windows.Markup.DependsOnAttribute> indicates that the attributed property depends on the value of another property.</span></span> <span data-ttu-id="1819c-157">将此属性应用于属性定义可确保在 XAML 对象写入中首先处理从属属性。</span><span class="sxs-lookup"><span data-stu-id="1819c-157">Applying this attribute to a property definition ensures that the dependent properties are processed first in XAML object writing.</span></span> <span data-ttu-id="1819c-158">的<xref:System.Windows.Markup.DependsOnAttribute>用法指定属性的特殊情况，这些类型对于有效对象创建必须遵循特定的分析顺序。</span><span class="sxs-lookup"><span data-stu-id="1819c-158">Usages of <xref:System.Windows.Markup.DependsOnAttribute> specify the exceptional cases of properties on types where a specific order of parsing must be followed for valid object creation.</span></span>

<span data-ttu-id="1819c-159">您可以将多个<xref:System.Windows.Markup.DependsOnAttribute>案例应用于属性定义。</span><span class="sxs-lookup"><span data-stu-id="1819c-159">You can apply multiple <xref:System.Windows.Markup.DependsOnAttribute> cases to a property definition.</span></span>

### <a name="markupextensionreturntypeattribute"></a><span data-ttu-id="1819c-160">标记扩展返回类型属性</span><span class="sxs-lookup"><span data-stu-id="1819c-160">MarkupExtensionReturnTypeAttribute</span></span>

<span data-ttu-id="1819c-161">**参考文档：**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-161">**Reference Documentation:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute></span></span>

<span data-ttu-id="1819c-162">**适用于：** 类，应为<xref:System.Windows.Markup.MarkupExtension>派生类型。</span><span class="sxs-lookup"><span data-stu-id="1819c-162">**Applies to:** Class, which is expected to be a <xref:System.Windows.Markup.MarkupExtension> derived type.</span></span>

<span data-ttu-id="1819c-163">**参数：**<xref:System.Type>指定作为`ProvideValue`属性<xref:System.Windows.Markup.MarkupExtension>的结果预期的最精确类型。</span><span class="sxs-lookup"><span data-stu-id="1819c-163">**Arguments:** A <xref:System.Type> that specifies the most precise type to expect as the `ProvideValue` result of the attributed <xref:System.Windows.Markup.MarkupExtension>.</span></span>

<span data-ttu-id="1819c-164">有关详细信息，请参阅[XAML 概述的标记扩展](markup-extensions-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1819c-164">For more information, see [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span></span>

### <a name="namescopepropertyattribute"></a><span data-ttu-id="1819c-165">名称范围属性</span><span class="sxs-lookup"><span data-stu-id="1819c-165">NameScopePropertyAttribute</span></span>

<span data-ttu-id="1819c-166">**参考文档：**  <xref:System.Windows.Markup.NameScopePropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-166">**Reference Documentation:**  <xref:System.Windows.Markup.NameScopePropertyAttribute></span></span>

<span data-ttu-id="1819c-167">**适用于：** 类</span><span class="sxs-lookup"><span data-stu-id="1819c-167">**Applies to:** Class</span></span>

<span data-ttu-id="1819c-168">**参数：** 支持两种归因形式：</span><span class="sxs-lookup"><span data-stu-id="1819c-168">**Arguments:** Supports two forms of attribution:</span></span>

- <span data-ttu-id="1819c-169">指定属性类型上属性名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="1819c-169">A string that specifies the name of a property on the attributed type.</span></span>

- <span data-ttu-id="1819c-170">指定属性名称的字符串，以及定义命名属性的类型的<xref:System.Type>的 字符串。</span><span class="sxs-lookup"><span data-stu-id="1819c-170">A string that specifies the name of a property, and a <xref:System.Type> for the type that defines the named property.</span></span> <span data-ttu-id="1819c-171">此窗体用于将可附加成员指定为 XAML 命名范围属性。</span><span class="sxs-lookup"><span data-stu-id="1819c-171">This form is for specifying an attachable member as the XAML namescope property.</span></span>

<span data-ttu-id="1819c-172"><xref:System.Windows.Markup.NameScopePropertyAttribute>指定为属性类提供 XAML 命名范围值的属性。</span><span class="sxs-lookup"><span data-stu-id="1819c-172"><xref:System.Windows.Markup.NameScopePropertyAttribute> specifies a property that provides the XAML namescope value for the attributed class.</span></span> <span data-ttu-id="1819c-173">XAML 命名范围属性应引用实现<xref:System.Windows.Markup.INameScope>并保存实际 XAML 名称范围、其存储及其行为的对象。</span><span class="sxs-lookup"><span data-stu-id="1819c-173">The XAML namescope property is expected to reference an object that implements <xref:System.Windows.Markup.INameScope> and holds the actual XAML namescope, its store, and its behavior.</span></span>

### <a name="runtimenamepropertyattribute"></a><span data-ttu-id="1819c-174">运行时名称属性属性</span><span class="sxs-lookup"><span data-stu-id="1819c-174">RuntimeNamePropertyAttribute</span></span>

<span data-ttu-id="1819c-175">**参考文档：**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-175">**Reference Documentation:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute></span></span>

<span data-ttu-id="1819c-176">**适用于：** 类</span><span class="sxs-lookup"><span data-stu-id="1819c-176">**Applies to:** Class</span></span>

<span data-ttu-id="1819c-177">**参数：** 指定属性化类型上的运行时名称属性名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="1819c-177">**Arguments:** A string that specifies the name of the run-time name property on the attributed type.</span></span>

<span data-ttu-id="1819c-178"><xref:System.Windows.Markup.RuntimeNamePropertyAttribute>报告映射到 XAML [x：Name 指令](xname-directive.md)的属性类型。</span><span class="sxs-lookup"><span data-stu-id="1819c-178"><xref:System.Windows.Markup.RuntimeNamePropertyAttribute> reports a property of the attributed type that maps to the XAML [x:Name Directive](xname-directive.md).</span></span> <span data-ttu-id="1819c-179">属性必须为类型<xref:System.String>，并且必须读取/写入。</span><span class="sxs-lookup"><span data-stu-id="1819c-179">The property must be of type <xref:System.String> and must be read/write.</span></span>

<span data-ttu-id="1819c-180">定义将继承到可分配给定义类型的所有派生类型。</span><span class="sxs-lookup"><span data-stu-id="1819c-180">The definition inherits to all derived types that are assignable to the defining type.</span></span> <span data-ttu-id="1819c-181">可以通过应用于<xref:System.Windows.Markup.RuntimeNamePropertyAttribute>特定派生类型来覆盖特定派生类型上的定义。</span><span class="sxs-lookup"><span data-stu-id="1819c-181">You can override the definition on a specific derived type by applying <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> on the specific derived type.</span></span>

### <a name="trimsurroundingwhitespaceattribute"></a><span data-ttu-id="1819c-182">修剪包围空白属性</span><span class="sxs-lookup"><span data-stu-id="1819c-182">TrimSurroundingWhitespaceAttribute</span></span>

<span data-ttu-id="1819c-183">**参考文档：**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-183">**Reference Documentation:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute></span></span>

<span data-ttu-id="1819c-184">**适用于：** 类型</span><span class="sxs-lookup"><span data-stu-id="1819c-184">**Applies to:** Types</span></span>

<span data-ttu-id="1819c-185">**参数：** 没有。</span><span class="sxs-lookup"><span data-stu-id="1819c-185">**Arguments:** None.</span></span>

<span data-ttu-id="1819c-186"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>应用于可能显示为空白重要内容中的子元素的特定类型（由 具有<xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>的集合持有的内容）。</span><span class="sxs-lookup"><span data-stu-id="1819c-186"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> is applied to specific types that might appear as child elements within white-space significant content (content held by a collection that has <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>).</span></span> <span data-ttu-id="1819c-187"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>主要与保存路径相关，但通过检查<xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>在负载路径中的 XAML 类型系统中可用。</span><span class="sxs-lookup"><span data-stu-id="1819c-187"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> is mainly relevant to the save path, but is available in the XAML type system in the load path by examining <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1819c-188">有关详细信息，请参阅[XAML 中的空白处理](white-space-processing.md)。</span><span class="sxs-lookup"><span data-stu-id="1819c-188">For more information, see [White-space processing in XAML](white-space-processing.md).</span></span>

### <a name="typeconverterattribute"></a><span data-ttu-id="1819c-189">TypeConverterAttribute</span><span class="sxs-lookup"><span data-stu-id="1819c-189">TypeConverterAttribute</span></span>

<span data-ttu-id="1819c-190">**参考文档：**  <xref:System.ComponentModel.TypeConverterAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-190">**Reference Documentation:**  <xref:System.ComponentModel.TypeConverterAttribute></span></span>

<span data-ttu-id="1819c-191">**适用于：** 类、属性、方法（唯一`get`的 XAML 有效方法大小写是支持可连接成员的访问器）。</span><span class="sxs-lookup"><span data-stu-id="1819c-191">**Applies to:** Class, property, method (the only XAML-valid method case is a `get` accessor that supports an attachable member).</span></span>

<span data-ttu-id="1819c-192">**参数：** 的<xref:System.Type> <xref:System.ComponentModel.TypeConverter>。</span><span class="sxs-lookup"><span data-stu-id="1819c-192">**Arguments:** The <xref:System.Type> of the <xref:System.ComponentModel.TypeConverter>.</span></span>

<span data-ttu-id="1819c-193"><xref:System.ComponentModel.TypeConverterAttribute>在 XAML 上下文中引用自定义<xref:System.ComponentModel.TypeConverter>。</span><span class="sxs-lookup"><span data-stu-id="1819c-193"><xref:System.ComponentModel.TypeConverterAttribute> in a XAML context references a custom <xref:System.ComponentModel.TypeConverter>.</span></span> <span data-ttu-id="1819c-194">这为<xref:System.ComponentModel.TypeConverter>自定义类型或该类型的成员提供类型转换行为。</span><span class="sxs-lookup"><span data-stu-id="1819c-194">This <xref:System.ComponentModel.TypeConverter> provides type conversion behavior for custom types, or members of that type.</span></span>

<span data-ttu-id="1819c-195">将<xref:System.ComponentModel.TypeConverterAttribute>该属性应用于类型，引用类型转换器实现。</span><span class="sxs-lookup"><span data-stu-id="1819c-195">Apply the <xref:System.ComponentModel.TypeConverterAttribute> attribute to your type, referencing your type converter implementation.</span></span> <span data-ttu-id="1819c-196">您可以在类、结构或接口上为 XAML 定义类型转换器。</span><span class="sxs-lookup"><span data-stu-id="1819c-196">You can define type converters for XAML on classes, structures, or interfaces.</span></span> <span data-ttu-id="1819c-197">您无需为枚举提供类型转换，该转换是本机启用的。</span><span class="sxs-lookup"><span data-stu-id="1819c-197">You do not need to provide type conversion for enumerations, that conversion is enabled natively.</span></span>

<span data-ttu-id="1819c-198">类型转换器应该能够从用于标记中的属性或初始化文本的字符串转换为预期的目标类型。</span><span class="sxs-lookup"><span data-stu-id="1819c-198">Your type converter should be able to convert from a string that is used for attributes or initialization text in markup, into your intended destination type.</span></span> <span data-ttu-id="1819c-199">有关详细信息，请参阅[类型转换器和 XAML](../../framework/wpf/advanced/typeconverters-and-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="1819c-199">For more information, see [TypeConverters and XAML](../../framework/wpf/advanced/typeconverters-and-xaml.md).</span></span>

<span data-ttu-id="1819c-200">也可以在特定属性上建立 XAML 的类型转换器行为，而不是应用于类型的所有值。</span><span class="sxs-lookup"><span data-stu-id="1819c-200">Rather than applying to all values of a type, a type converter behavior for XAML can also be established on a specific property.</span></span> <span data-ttu-id="1819c-201">在这种情况下，您将应用于<xref:System.ComponentModel.TypeConverterAttribute>属性定义（外部定义，而不是特定`get`定义和`set`定义）。</span><span class="sxs-lookup"><span data-stu-id="1819c-201">In this case, you apply <xref:System.ComponentModel.TypeConverterAttribute> to the property definition (the outer definition, not the specific `get` and `set` definitions).</span></span>

<span data-ttu-id="1819c-202">可以通过应用于<xref:System.ComponentModel.TypeConverterAttribute>支持 XAML 用法`get`的方法访问器来分配自定义可连接成员的 XAML 使用的类型转换器行为。</span><span class="sxs-lookup"><span data-stu-id="1819c-202">A type converter behavior for XAML usage of a custom attachable member can be assigned by applying <xref:System.ComponentModel.TypeConverterAttribute> to the `get` method accessor that supports the XAML usage.</span></span>

<span data-ttu-id="1819c-203">与<xref:System.ComponentModel.TypeConverter>类似<xref:System.ComponentModel.TypeConverterAttribute>，在 XAML 存在之前存在于 .NET 中，类型转换器模型具有其他用途。</span><span class="sxs-lookup"><span data-stu-id="1819c-203">Similar to <xref:System.ComponentModel.TypeConverter>, <xref:System.ComponentModel.TypeConverterAttribute> existed in .NET prior to the existence of XAML, and the type converter model served other purposes.</span></span> <span data-ttu-id="1819c-204">为了引用和使用<xref:System.ComponentModel.TypeConverterAttribute>，您必须完全限定它或提供`using`语句。 <xref:System.ComponentModel></span><span class="sxs-lookup"><span data-stu-id="1819c-204">In order to reference and use <xref:System.ComponentModel.TypeConverterAttribute>, you must fully qualify it or provide a `using` statement for <xref:System.ComponentModel>.</span></span> <span data-ttu-id="1819c-205">还在项目中包括系统程序集。</span><span class="sxs-lookup"><span data-stu-id="1819c-205">Also include the System assembly in your project.</span></span>

### <a name="uidpropertyattribute"></a><span data-ttu-id="1819c-206">乌德属性</span><span class="sxs-lookup"><span data-stu-id="1819c-206">UidPropertyAttribute</span></span>

<span data-ttu-id="1819c-207">**参考文档：**  <xref:System.Windows.Markup.UidPropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-207">**Reference Documentation:**  <xref:System.Windows.Markup.UidPropertyAttribute></span></span>

<span data-ttu-id="1819c-208">**适用于：** 类</span><span class="sxs-lookup"><span data-stu-id="1819c-208">**Applies to:** Class</span></span>

<span data-ttu-id="1819c-209">**参数：** 按名称引用相关属性的字符串。</span><span class="sxs-lookup"><span data-stu-id="1819c-209">**Arguments:** A string that references the relevant property by name.</span></span>

<span data-ttu-id="1819c-210">指示别名[x：Uid 指令](xuid-directive.md)的类的 CLR 属性。</span><span class="sxs-lookup"><span data-stu-id="1819c-210">Indicates the CLR property of a class that aliases the [x:Uid Directive](xuid-directive.md).</span></span>

### <a name="usableduringinitializationattribute"></a><span data-ttu-id="1819c-211">初始化期间可用属性</span><span class="sxs-lookup"><span data-stu-id="1819c-211">UsableDuringInitializationAttribute</span></span>

<span data-ttu-id="1819c-212">**参考文档：**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-212">**Reference Documentation:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute></span></span>

<span data-ttu-id="1819c-213">**适用于：** 类</span><span class="sxs-lookup"><span data-stu-id="1819c-213">**Applies to:** Class</span></span>

<span data-ttu-id="1819c-214">**参数：** 一个布尔。</span><span class="sxs-lookup"><span data-stu-id="1819c-214">**Arguments:** A Boolean.</span></span> <span data-ttu-id="1819c-215">如果用于属性的预期用途，则该值应设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="1819c-215">If used for the attribute's intended purpose, the value should be set to `true`.</span></span>

<span data-ttu-id="1819c-216">指示类型在 XAML 对象图形创建期间是否自上而下生成。</span><span class="sxs-lookup"><span data-stu-id="1819c-216">Indicates whether the type is built top-down during XAML object graph creation.</span></span> <span data-ttu-id="1819c-217">这是一个高级概念，可能与编程模型的定义密切相关。</span><span class="sxs-lookup"><span data-stu-id="1819c-217">This is an advanced concept, which is probably closely related to the definition of your programming model.</span></span> <span data-ttu-id="1819c-218">有关详细信息，请参阅 <xref:System.Windows.Markup.UsableDuringInitializationAttribute>。</span><span class="sxs-lookup"><span data-stu-id="1819c-218">For more information, see <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.</span></span>

### <a name="valueserializerattribute"></a><span data-ttu-id="1819c-219">值序列器属性</span><span class="sxs-lookup"><span data-stu-id="1819c-219">ValueSerializerAttribute</span></span>

<span data-ttu-id="1819c-220">**参考文档：**  <xref:System.Windows.Markup.ValueSerializerAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-220">**Reference Documentation:**  <xref:System.Windows.Markup.ValueSerializerAttribute></span></span>

<span data-ttu-id="1819c-221">**适用于：** 类、属性、方法（唯一`get`的 XAML 有效方法大小写是支持可连接成员的访问器）。</span><span class="sxs-lookup"><span data-stu-id="1819c-221">**Applies to:** Class, property, method (the only XAML-valid method case is a `get` accessor that supports an attachable member).</span></span>

<span data-ttu-id="1819c-222">**参数：** 指定<xref:System.Type>在序列化属性类型或特定属性属性的所有属性时要使用的值序列化器支持类。</span><span class="sxs-lookup"><span data-stu-id="1819c-222">**Arguments:** A <xref:System.Type> that specifies the value serializer support class to use when serializing all properties of the attributed type, or the specific attributed property.</span></span>

<span data-ttu-id="1819c-223"><xref:System.Windows.Markup.ValueSerializer>指定一个值序列化类，该类需要比 更多的<xref:System.ComponentModel.TypeConverter>状态和上下文。</span><span class="sxs-lookup"><span data-stu-id="1819c-223"><xref:System.Windows.Markup.ValueSerializer> specifies a value serialization class that requires more state and context than a <xref:System.ComponentModel.TypeConverter> does.</span></span> <span data-ttu-id="1819c-224"><xref:System.Windows.Markup.ValueSerializer>通过将属性应用于可附加成员的静态<xref:System.Windows.Markup.ValueSerializerAttribute>`get`访问器方法，可以与可连接成员关联。</span><span class="sxs-lookup"><span data-stu-id="1819c-224"><xref:System.Windows.Markup.ValueSerializer> can be associated with an attachable member by applying the <xref:System.Windows.Markup.ValueSerializerAttribute> attribute on the static `get` accessor method for the attachable member.</span></span> <span data-ttu-id="1819c-225">值序列化也适用于枚举、接口和结构，但不适用于委托。</span><span class="sxs-lookup"><span data-stu-id="1819c-225">Value serialization is also applicable for enumerations, interfaces, and structures, but not for delegates.</span></span>

### <a name="whitespacesignificantcollectionattribute"></a><span data-ttu-id="1819c-226">空白显著集合属性</span><span class="sxs-lookup"><span data-stu-id="1819c-226">WhitespaceSignificantCollectionAttribute</span></span>

<span data-ttu-id="1819c-227">**参考文档：**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-227">**Reference Documentation:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute></span></span>

<span data-ttu-id="1819c-228">**适用于：** 类，特别是预期承载混合内容的集合类型，其中对象元素周围的空白对于 UI 表示可能很重要。</span><span class="sxs-lookup"><span data-stu-id="1819c-228">**Applies to:** Class, specifically collection types that are expected to host mixed content, where white space around object elements might be significant for UI representation.</span></span>

<span data-ttu-id="1819c-229">**参数：** 没有。</span><span class="sxs-lookup"><span data-stu-id="1819c-229">**Arguments:** None.</span></span>

<span data-ttu-id="1819c-230"><xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>指示集合类型应被 XAML 处理器处理为具有显著意义的空格，这会影响集合中 XAML 节点流的值节点的构造。</span><span class="sxs-lookup"><span data-stu-id="1819c-230"><xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> indicates that a collection type should be processed as white-space significant by a XAML processor, which influences the construction of the XAML node stream's value nodes within the collection.</span></span> <span data-ttu-id="1819c-231">有关详细信息，请参阅[XAML 中的空白处理](white-space-processing.md)。</span><span class="sxs-lookup"><span data-stu-id="1819c-231">For more information, see [White-space processing in XAML](white-space-processing.md).</span></span>

### <a name="xamldeferloadattribute"></a><span data-ttu-id="1819c-232">XamlDeferLoad 属性</span><span class="sxs-lookup"><span data-stu-id="1819c-232">XamlDeferLoadAttribute</span></span>

<span data-ttu-id="1819c-233">**参考文档：**  <xref:System.Windows.Markup.XamlDeferLoadAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-233">**Reference Documentation:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute></span></span>

<span data-ttu-id="1819c-234">**适用于：** 类，属性。</span><span class="sxs-lookup"><span data-stu-id="1819c-234">**Applies to:** Class, property.</span></span>

<span data-ttu-id="1819c-235">**参数：** 支持两个归因窗体类型作为字符串，或<xref:System.Type>类型为 。</span><span class="sxs-lookup"><span data-stu-id="1819c-235">**Arguments:** Supports two attribution forms types as strings, or types as <xref:System.Type>.</span></span> <span data-ttu-id="1819c-236">请参阅 <xref:System.Windows.Markup.XamlDeferLoadAttribute>。</span><span class="sxs-lookup"><span data-stu-id="1819c-236">See <xref:System.Windows.Markup.XamlDeferLoadAttribute>.</span></span>

<span data-ttu-id="1819c-237">指示类或属性具有 XAML 的延迟加载用途（如模板行为），并报告启用延迟行为及其目标/内容类型的类。</span><span class="sxs-lookup"><span data-stu-id="1819c-237">Indicates that a class or property has a deferred load usage for XAML (such as a template behavior), and reports the class that enables the deferring behavior and its destination/content type.</span></span>

### <a name="xamlsetmarkupextensionattribute"></a><span data-ttu-id="1819c-238">XamlSetMarkup 扩展属性</span><span class="sxs-lookup"><span data-stu-id="1819c-238">XamlSetMarkupExtensionAttribute</span></span>

<span data-ttu-id="1819c-239">**参考文档：**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-239">**Reference Documentation:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute></span></span>

<span data-ttu-id="1819c-240">**适用于：** 类</span><span class="sxs-lookup"><span data-stu-id="1819c-240">**Applies to:** Class</span></span>

<span data-ttu-id="1819c-241">**参数：** 命名回调。</span><span class="sxs-lookup"><span data-stu-id="1819c-241">**Arguments:** Names the callback.</span></span>

<span data-ttu-id="1819c-242">指示类可以使用标记扩展为一个或多个属性提供值，并引用 XAML 编写器在对类的任何属性执行标记扩展集操作之前应调用的处理程序。</span><span class="sxs-lookup"><span data-stu-id="1819c-242">Indicates that a class can use a markup extension to provide a value for one or more of its properties, and references a handler that a XAML writer should call before performing a markup extension set operation on any property of the class.</span></span>

### <a name="xamlsettypeconverterattribute"></a><span data-ttu-id="1819c-243">XamlSet 类型转换器属性</span><span class="sxs-lookup"><span data-stu-id="1819c-243">XamlSetTypeConverterAttribute</span></span>

<span data-ttu-id="1819c-244">**参考文档：**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-244">**Reference Documentation:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute></span></span>

<span data-ttu-id="1819c-245">**适用于：** 类</span><span class="sxs-lookup"><span data-stu-id="1819c-245">**Applies to:** Class</span></span>

<span data-ttu-id="1819c-246">**参数：** 命名回调。</span><span class="sxs-lookup"><span data-stu-id="1819c-246">**Arguments:** Names the callback.</span></span>

<span data-ttu-id="1819c-247">指示类可以使用类型转换器为其一个或多个属性提供值，并引用 XAML 编写器在对类的任何属性执行类型转换器集操作之前应调用的处理程序。</span><span class="sxs-lookup"><span data-stu-id="1819c-247">Indicates that a class can use a type converter to provide a value for one or more of its properties, and references a handler that a XAML writer should call before performing a type converter set operation on any property of the class.</span></span>

### <a name="xmllangpropertyattribute"></a><span data-ttu-id="1819c-248">XmlLang属性</span><span class="sxs-lookup"><span data-stu-id="1819c-248">XmlLangPropertyAttribute</span></span>

<span data-ttu-id="1819c-249">**参考文档：**  <xref:System.Windows.Markup.XmlLangPropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-249">**Reference Documentation:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute></span></span>

<span data-ttu-id="1819c-250">**适用于：** 类</span><span class="sxs-lookup"><span data-stu-id="1819c-250">**Applies to:** Class</span></span>

<span data-ttu-id="1819c-251">**参数：** 一个字符串，用于在属性类型上指定属性的名称`xml:lang`到别名。</span><span class="sxs-lookup"><span data-stu-id="1819c-251">**Arguments:** A string that specifies the name of the property to alias to `xml:lang` on the attributed type.</span></span>

<span data-ttu-id="1819c-252"><xref:System.Windows.Markup.XmlLangPropertyAttribute>报告映射到 XML`lang`指令的属性类型的属性。</span><span class="sxs-lookup"><span data-stu-id="1819c-252"><xref:System.Windows.Markup.XmlLangPropertyAttribute> reports a property of the attributed type that maps to the XML `lang` directive.</span></span> <span data-ttu-id="1819c-253">属性不一定是类型<xref:System.String>，但必须从字符串中分配（可以通过将类型转换器与属性的类型或特定属性相关联来实现）。</span><span class="sxs-lookup"><span data-stu-id="1819c-253">The property is not necessarily of type <xref:System.String> but must be assignable from a string (assignment could be accomplished by associating a type converter with the property's type or with the specific property).</span></span> <span data-ttu-id="1819c-254">属性必须读/写。</span><span class="sxs-lookup"><span data-stu-id="1819c-254">The property must be read/write.</span></span>

<span data-ttu-id="1819c-255">映射`xml:lang`方案是，运行时对象模型可以访问 XML 指定的语言信息，而无需专门使用 XMLDOM 进行处理。</span><span class="sxs-lookup"><span data-stu-id="1819c-255">The scenario for mapping `xml:lang` is so that a runtime object model has access to XML-specified language information without specifically processing with an XMLDOM.</span></span>

<span data-ttu-id="1819c-256">定义将继承到可分配给定义类型的所有派生类型。</span><span class="sxs-lookup"><span data-stu-id="1819c-256">The definition inherits to all derived types that are assignable to the defining type.</span></span> <span data-ttu-id="1819c-257">可以通过应用于<xref:System.Windows.Markup.XmlLangPropertyAttribute>特定派生类型来覆盖特定派生类型上的定义，尽管这种情况并不常见。</span><span class="sxs-lookup"><span data-stu-id="1819c-257">You can override the definition on a specific derived type by applying <xref:System.Windows.Markup.XmlLangPropertyAttribute> on the specific derived type, although that is an uncommon scenario.</span></span>

## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a><span data-ttu-id="1819c-258">装配层级的 XAML 相关 CLR 属性</span><span class="sxs-lookup"><span data-stu-id="1819c-258">XAML-Related CLR Attributes at the Assembly Level</span></span>

<span data-ttu-id="1819c-259">以下各节介绍不应用于类型或成员定义但应用于程序集的与 XAML 相关的属性。</span><span class="sxs-lookup"><span data-stu-id="1819c-259">The following sections describe the XAML-related attributes that are not applied to types or member definitions, but are instead applied to assemblies.</span></span> <span data-ttu-id="1819c-260">这些属性与定义包含要在 XAML 中使用的自定义类型的库的总体目标相关。</span><span class="sxs-lookup"><span data-stu-id="1819c-260">These attributes are pertinent to the overall goal of defining a library that contains custom types to use in XAML.</span></span> <span data-ttu-id="1819c-261">某些属性不一定直接影响 XAML 节点流，而是在节点流中传递，供其他使用者使用。</span><span class="sxs-lookup"><span data-stu-id="1819c-261">Some of the attributes do not necessarily influence the XAML node stream directly, but are passed on in the node stream for other consumers to use.</span></span> <span data-ttu-id="1819c-262">信息的使用者包括需要 XAML 命名空间信息和关联的前缀信息的设计环境或序列化过程。</span><span class="sxs-lookup"><span data-stu-id="1819c-262">Consumers for the information include design environments or serialization processes that need XAML namespace information and associated prefix information.</span></span> <span data-ttu-id="1819c-263">XAML 架构上下文（包括 .NET XAML 服务默认值）也使用此信息。</span><span class="sxs-lookup"><span data-stu-id="1819c-263">A XAML schema context (including the .NET XAML Services default) also uses this information.</span></span>

### <a name="xmlnscompatiblewithattribute"></a><span data-ttu-id="1819c-264">与属性兼容的 Xmlns</span><span class="sxs-lookup"><span data-stu-id="1819c-264">XmlnsCompatibleWithAttribute</span></span>

<span data-ttu-id="1819c-265">**参考文档：**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-265">**Reference Documentation:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute></span></span>

<span data-ttu-id="1819c-266">**参数：**</span><span class="sxs-lookup"><span data-stu-id="1819c-266">**Arguments:**</span></span>

- <span data-ttu-id="1819c-267">指定要归纳的 XAML 命名空间的标识符的字符串。</span><span class="sxs-lookup"><span data-stu-id="1819c-267">A string that specifies the identifier of the XAML namespace to subsume.</span></span>

- <span data-ttu-id="1819c-268">指定 XAML 命名空间的标识符的字符串，该名称空间可以从上一个参数中归入 XAML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="1819c-268">A string that specifies the identifier of the XAML namespace that can subsume the XAML namespace from the previous argument.</span></span>

  <span data-ttu-id="1819c-269"><xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>指定 XAML 命名空间可以由另一个 XAML 命名空间进行归用。</span><span class="sxs-lookup"><span data-stu-id="1819c-269"><xref:System.Windows.Markup.XmlnsCompatibleWithAttribute> specifies that a XAML namespace can be subsumed by another XAML namespace.</span></span> <span data-ttu-id="1819c-270">通常，先前定义的 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 中指示了包含 XAML 命令空间。</span><span class="sxs-lookup"><span data-stu-id="1819c-270">Typically, the subsuming XAML namespace is indicated in a previously defined <xref:System.Windows.Markup.XmlnsDefinitionAttribute>.</span></span> <span data-ttu-id="1819c-271">此技术可用于在库中对 XAML 词汇进行版本控制，并使之与以前定义的标记（针对早期版本化的词汇表）兼容。</span><span class="sxs-lookup"><span data-stu-id="1819c-271">This technique can be used for versioning a XAML vocabulary in a library and to make it compatible with previously defined markup against the earlier versioned vocabulary.</span></span>

### <a name="xmlnsdefinitionattribute"></a><span data-ttu-id="1819c-272">Xmlns 定义属性</span><span class="sxs-lookup"><span data-stu-id="1819c-272">XmlnsDefinitionAttribute</span></span>

<span data-ttu-id="1819c-273">**参考文档：**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-273">**Reference Documentation:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute></span></span>

<span data-ttu-id="1819c-274">**参数：**</span><span class="sxs-lookup"><span data-stu-id="1819c-274">**Arguments:**</span></span>

- <span data-ttu-id="1819c-275">指定要定义的 XAML 命名空间的标识符的字符串。</span><span class="sxs-lookup"><span data-stu-id="1819c-275">A string that specifies the identifier of the XAML namespace to define.</span></span>

- <span data-ttu-id="1819c-276">命名 CLR 命名空间的字符串。</span><span class="sxs-lookup"><span data-stu-id="1819c-276">A string that names a CLR namespace.</span></span> <span data-ttu-id="1819c-277">CLR 命名空间应在程序集中定义公共类型，并且至少应使用一种 CLR 命名空间类型来使用 XAML。</span><span class="sxs-lookup"><span data-stu-id="1819c-277">The CLR namespace should define public types in your assembly, and at least one of the CLR namespace types should be intended for XAML usage.</span></span>

  <span data-ttu-id="1819c-278"><xref:System.Windows.Markup.XmlnsDefinitionAttribute>指定 XAML 命名空间和 CLR 命名空间之间的每个程序集映射，然后 XAML 对象编写器或 XAML 架构上下文用于类型解析。</span><span class="sxs-lookup"><span data-stu-id="1819c-278"><xref:System.Windows.Markup.XmlnsDefinitionAttribute> specifies a mapping on a per-assembly basis between a XAML namespace and a CLR namespace, which is then used for type resolution by a XAML object writer or XAML schema context.</span></span>

  <span data-ttu-id="1819c-279">可以有多个<xref:System.Windows.Markup.XmlnsDefinitionAttribute>组件。</span><span class="sxs-lookup"><span data-stu-id="1819c-279">More than one <xref:System.Windows.Markup.XmlnsDefinitionAttribute> can be applied to an assembly.</span></span> <span data-ttu-id="1819c-280">这可能是出于以下任何原因的组合：</span><span class="sxs-lookup"><span data-stu-id="1819c-280">This might be done for any combination of the following reasons:</span></span>

- <span data-ttu-id="1819c-281">库设计包含多个 CLR 命名空间，用于运行时 API 访问的逻辑组织;但是，您希望这些命名空间中的所有类型都可用于 XAML，通过引用相同的 XAML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="1819c-281">The library design contains multiple CLR namespaces for logical organization of run-time API access; however, you want all types in those namespaces to be XAML-usable by referencing the same XAML namespace.</span></span> <span data-ttu-id="1819c-282">在这种情况下，使用相同的<xref:System.Windows.Markup.XmlnsDefinitionAttribute><xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A>值但不同的<xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A>值应用多个属性。</span><span class="sxs-lookup"><span data-stu-id="1819c-282">In this case, you apply several <xref:System.Windows.Markup.XmlnsDefinitionAttribute> attributes using the same <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> value but different <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> values.</span></span> <span data-ttu-id="1819c-283">如果要定义框架或应用程序打算成为常用的默认 XAML 命名空间的 XAML 命名空间的映射，则此功能尤其有用。</span><span class="sxs-lookup"><span data-stu-id="1819c-283">This is especially useful if you are defining mappings for the XAML namespace that your framework or application intends to be the default XAML namespace in common usage.</span></span>

- <span data-ttu-id="1819c-284">库设计包含多个 CLR 命名空间，您希望在这些 CLR 命名空间中类型的用法之间进行深思熟虑的 XAML 命名空间分离。</span><span class="sxs-lookup"><span data-stu-id="1819c-284">The library design contains multiple CLR namespaces, and you want a deliberate XAML namespace separation between the usages of types in those CLR namespaces.</span></span>

- <span data-ttu-id="1819c-285">在程序集中定义 CLR 命名空间，并希望它可以通过多个 XAML 命名空间进行访问。</span><span class="sxs-lookup"><span data-stu-id="1819c-285">You define a CLR namespace in the assembly, and you want it to be accessible through more than one XAML namespace.</span></span> <span data-ttu-id="1819c-286">当您支持具有相同代码库的多个词汇库时，将发生此情况。</span><span class="sxs-lookup"><span data-stu-id="1819c-286">This scenario occurs when you are supporting multiple vocabularies with the same codebase.</span></span>

- <span data-ttu-id="1819c-287">在一个或多个 CLR 命名空间中定义 XAML 语言支持。</span><span class="sxs-lookup"><span data-stu-id="1819c-287">You define XAML language support in one or more CLR namespaces.</span></span> <span data-ttu-id="1819c-288">在这种情况下，<xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A>值应为`http://schemas.microsoft.com/winfx/2006/xaml`。</span><span class="sxs-lookup"><span data-stu-id="1819c-288">In this case, the <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> value should be `http://schemas.microsoft.com/winfx/2006/xaml`.</span></span>

### <a name="xmlnsprefixattribute"></a><span data-ttu-id="1819c-289">Xmlns前缀属性</span><span class="sxs-lookup"><span data-stu-id="1819c-289">XmlnsPrefixAttribute</span></span>

<span data-ttu-id="1819c-290">**参考文档：**  <xref:System.Windows.Markup.XmlnsPrefixAttribute></span><span class="sxs-lookup"><span data-stu-id="1819c-290">**Reference Documentation:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute></span></span>

<span data-ttu-id="1819c-291">**参数：**</span><span class="sxs-lookup"><span data-stu-id="1819c-291">**Arguments:**</span></span>

- <span data-ttu-id="1819c-292">指定 XAML 命名空间标识符的字符串。</span><span class="sxs-lookup"><span data-stu-id="1819c-292">A string that specifies the identifier of a XAML namespace.</span></span>

- <span data-ttu-id="1819c-293">指定建议前缀的字符串。</span><span class="sxs-lookup"><span data-stu-id="1819c-293">A string that specifies a recommended prefix.</span></span>

  <span data-ttu-id="1819c-294"><xref:System.Windows.Markup.XmlnsDefinitionAttribute>指定用于 XAML 命名空间的建议前缀。</span><span class="sxs-lookup"><span data-stu-id="1819c-294"><xref:System.Windows.Markup.XmlnsDefinitionAttribute> specifies a recommended prefix to use for a XAML namespace.</span></span> <span data-ttu-id="1819c-295">在由 .NET XAML 服务<xref:System.Xaml.XamlXmlWriter>序列化的 XAML 文件中编写元素和属性时，或者当 XAML 实现库与具有 XAML 编辑功能的设计环境交互时，前缀非常有用。</span><span class="sxs-lookup"><span data-stu-id="1819c-295">The prefix is useful when writing elements and attributes in a XAML file that is serialized by .NET XAML Services <xref:System.Xaml.XamlXmlWriter>, or when a XAML-implementing library interacts with a design environment that has XAML editing features.</span></span>

  <span data-ttu-id="1819c-296">可以有多个<xref:System.Windows.Markup.XmlnsPrefixAttribute>组件。</span><span class="sxs-lookup"><span data-stu-id="1819c-296">More than one <xref:System.Windows.Markup.XmlnsPrefixAttribute> can be applied to an assembly.</span></span> <span data-ttu-id="1819c-297">这可能是出于以下任何原因的组合：</span><span class="sxs-lookup"><span data-stu-id="1819c-297">This might be done for any combination of the following reasons:</span></span>

- <span data-ttu-id="1819c-298">程序集定义多个 XAML 命名空间的类型。</span><span class="sxs-lookup"><span data-stu-id="1819c-298">Your assembly defines types for more than one XAML namespace.</span></span> <span data-ttu-id="1819c-299">在这种情况下，为每个 XAML 命名空间定义不同的前缀值。</span><span class="sxs-lookup"><span data-stu-id="1819c-299">In this case, define different prefix values for each XAML namespace.</span></span>

- <span data-ttu-id="1819c-300">您支持多个词汇，并且对每个词汇表和 XAML 命名空间使用不同的前缀。</span><span class="sxs-lookup"><span data-stu-id="1819c-300">You are supporting multiple vocabularies, and you use different prefixes for each vocabulary and XAML namespace.</span></span>

- <span data-ttu-id="1819c-301">在程序集中定义 XAML 语言支持，并为<xref:System.Windows.Markup.XmlnsDefinitionAttribute>`http://schemas.microsoft.com/winfx/2006/xaml`</span><span class="sxs-lookup"><span data-stu-id="1819c-301">You define XAML language support in the assembly and have a <xref:System.Windows.Markup.XmlnsDefinitionAttribute> for `http://schemas.microsoft.com/winfx/2006/xaml`.</span></span> <span data-ttu-id="1819c-302">在这种情况下，通常应升级前缀`x`。</span><span class="sxs-lookup"><span data-stu-id="1819c-302">In this case, you typically should promote the prefix `x`.</span></span>

> [!NOTE]
> <span data-ttu-id="1819c-303">.NET XAML 服务还定义了与 XAML<xref:System.Windows.Markup.RootNamespaceAttribute>相关的属性 。</span><span class="sxs-lookup"><span data-stu-id="1819c-303">.NET XAML Services also defines the XAML-related attribute <xref:System.Windows.Markup.RootNamespaceAttribute>.</span></span> <span data-ttu-id="1819c-304">此属性是项目系统支持的程序集级属性，与 XAML 自定义类型无关。</span><span class="sxs-lookup"><span data-stu-id="1819c-304">This attribute is an assembly-level attribute for project system support, and it is not relevant for XAML custom types.</span></span>

## <a name="see-also"></a><span data-ttu-id="1819c-305">请参阅</span><span class="sxs-lookup"><span data-stu-id="1819c-305">See also</span></span>

- <xref:System.Attribute>
- [<span data-ttu-id="1819c-306">定义与 .NET XAML 服务一起使用的自定义类型</span><span class="sxs-lookup"><span data-stu-id="1819c-306">Defining Custom Types for Use with .NET XAML Services</span></span>](define-custom-types.md)
