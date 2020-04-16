---
title: x:ClassModifier 指令
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 436204774c2d59b43a77865c666aed702f7681db
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433270"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="86f84-102">x:ClassModifier 指令</span><span class="sxs-lookup"><span data-stu-id="86f84-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="86f84-103">在提供时`x:Class`修改 XAML 编译行为。</span><span class="sxs-lookup"><span data-stu-id="86f84-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="86f84-104">具体而言，提供的不是创建具有`class``Public`访问级别的部分（默认值），而是使用`x:Class``NotPublic`访问级别创建所提供的部分。</span><span class="sxs-lookup"><span data-stu-id="86f84-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="86f84-105">此行为会影响生成的程序集中类的访问级别。</span><span class="sxs-lookup"><span data-stu-id="86f84-105">This behavior affects the access level for the class in the generated assemblies.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="86f84-106">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="86f84-106">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="86f84-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="86f84-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="86f84-108">*不公开*</span><span class="sxs-lookup"><span data-stu-id="86f84-108">*NotPublic*</span></span>|<span data-ttu-id="86f84-109">要指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>的确切字符串与不同<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>，具体取决于您使用的代码背后的编程语言。</span><span class="sxs-lookup"><span data-stu-id="86f84-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="86f84-110">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="86f84-110">See Remarks.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="86f84-111">依赖项</span><span class="sxs-lookup"><span data-stu-id="86f84-111">Dependencies</span></span>

<span data-ttu-id="86f84-112">[x：类](xclass-directive.md)也必须在同一元素上提供，并且该元素必须是页面中的根元素。</span><span class="sxs-lookup"><span data-stu-id="86f84-112">[x:Class](xclass-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="86f84-113">有关详细信息，请参阅[\[MS-XAML\]部分 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))。</span><span class="sxs-lookup"><span data-stu-id="86f84-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="remarks"></a><span data-ttu-id="86f84-114">备注</span><span class="sxs-lookup"><span data-stu-id="86f84-114">Remarks</span></span>

<span data-ttu-id="86f84-115">.NET `x:ClassModifier` XAML 服务使用中的值因编程语言而异。</span><span class="sxs-lookup"><span data-stu-id="86f84-115">The value of `x:ClassModifier` in .NET XAML Services usage varies by programming language.</span></span> <span data-ttu-id="86f84-116">要使用的字符串取决于每种语言如何实现其<xref:System.CodeDom.Compiler.CodeDomProvider>和返回的类型转换器来定义<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>和<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>的含义，以及该语言是否区分大小写。</span><span class="sxs-lookup"><span data-stu-id="86f84-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>

- <span data-ttu-id="86f84-117">对于 C#，要传递到指定的<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>字符串为`internal`。</span><span class="sxs-lookup"><span data-stu-id="86f84-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>

- <span data-ttu-id="86f84-118">对于 Microsoft Visual Basic .NET，要传递<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>要`Friend`指定的字符串为 。</span><span class="sxs-lookup"><span data-stu-id="86f84-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>

- <span data-ttu-id="86f84-119">对于C++/CLI，不存在支持编译 XAML 的目标;因此，未指定要传递的值。</span><span class="sxs-lookup"><span data-stu-id="86f84-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>

<span data-ttu-id="86f84-120">您还可以指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>（`public`在 C# 中`Public`，在视觉基础中）;但是，指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>不常执行，因为<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>已是默认行为。</span><span class="sxs-lookup"><span data-stu-id="86f84-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>

<span data-ttu-id="86f84-121">具有等效用户代码访问级别限制的其他值（如`private`C#中）与 XAML`x:ClassModifier`中不支持嵌套类引用无关，因此<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>，修改器具有相同的效果。</span><span class="sxs-lookup"><span data-stu-id="86f84-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>

## <a name="security-notes"></a><span data-ttu-id="86f84-122">安全说明</span><span class="sxs-lookup"><span data-stu-id="86f84-122">Security Notes</span></span>

<span data-ttu-id="86f84-123">中`x:ClassModifier`宣布的访问级别仍受特定框架及其能力的解释。</span><span class="sxs-lookup"><span data-stu-id="86f84-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="86f84-124">WPF 包括加载和实例化类型的功能，如果`x:ClassModifier``internal`通过包 URI 引用 WPF 资源引用该类。</span><span class="sxs-lookup"><span data-stu-id="86f84-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="86f84-125">由于这种情况，以及可能由其他框架实现的可能其他框架，不完全依赖`x:ClassModifier`来阻止所有可能的实例化尝试。</span><span class="sxs-lookup"><span data-stu-id="86f84-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>

## <a name="see-also"></a><span data-ttu-id="86f84-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="86f84-126">See also</span></span>

- [<span data-ttu-id="86f84-127">x:Class 指令</span><span class="sxs-lookup"><span data-stu-id="86f84-127">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="86f84-128">WPF 中的代码隐藏和 XAML</span><span class="sxs-lookup"><span data-stu-id="86f84-128">Code-Behind and XAML in WPF</span></span>](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="86f84-129">x:FieldModifier 指令</span><span class="sxs-lookup"><span data-stu-id="86f84-129">x:FieldModifier Directive</span></span>](xfieldmodifier-directive.md)
- [<span data-ttu-id="86f84-130">安全性 (WPF)</span><span class="sxs-lookup"><span data-stu-id="86f84-130">Security (WPF)</span></span>](../../framework/wpf/security-wpf.md)
- [<span data-ttu-id="86f84-131">从 WPF 迁移到 System.Xaml 的类型</span><span class="sxs-lookup"><span data-stu-id="86f84-131">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
