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
ms.openlocfilehash: ef55549b43ecbef539d7e84a7281fa704a328938
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507585"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="73ca0-102">x:ClassModifier 指令</span><span class="sxs-lookup"><span data-stu-id="73ca0-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="73ca0-103">修改 XAML 编译行为时`x:Class`还提供了。</span><span class="sxs-lookup"><span data-stu-id="73ca0-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="73ca0-104">具体而言，而不是创建一个分部`class`，其`Public`访问级别 （默认值），提供`x:Class`使用创建`NotPublic`访问级别。</span><span class="sxs-lookup"><span data-stu-id="73ca0-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="73ca0-105">此行为会影响生成的程序集中类的访问级别。</span><span class="sxs-lookup"><span data-stu-id="73ca0-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="73ca0-106">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="73ca0-106">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="73ca0-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="73ca0-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="73ca0-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="73ca0-108">*NotPublic*</span></span>|<span data-ttu-id="73ca0-109">确切的字符串传递的用于指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>与<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>各不相同，具体取决于您使用的代码隐藏编程语言。</span><span class="sxs-lookup"><span data-stu-id="73ca0-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="73ca0-110">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="73ca0-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="73ca0-111">依赖项</span><span class="sxs-lookup"><span data-stu-id="73ca0-111">Dependencies</span></span>  
 <span data-ttu-id="73ca0-112">[x： 类](../../../docs/framework/xaml-services/x-class-directive.md)还必须提供在同一元素上并且该元素必须是一个页面中的根元素。</span><span class="sxs-lookup"><span data-stu-id="73ca0-112">[x:Class](../../../docs/framework/xaml-services/x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="73ca0-113">有关详细信息，请参阅[ \[MS XAML\]部分 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525)。</span><span class="sxs-lookup"><span data-stu-id="73ca0-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73ca0-114">备注</span><span class="sxs-lookup"><span data-stu-id="73ca0-114">Remarks</span></span>  
 <span data-ttu-id="73ca0-115">值`x:ClassModifier`.NET Framework XAML 服务中而异的编程语言的使用情况。</span><span class="sxs-lookup"><span data-stu-id="73ca0-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="73ca0-116">要使用的字符串取决于如何实现每种语言及其<xref:System.CodeDom.Compiler.CodeDomProvider>和类型转换器，它将返回定义的含义<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>和<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>，以及该语言是否区分大小写。</span><span class="sxs-lookup"><span data-stu-id="73ca0-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
-   <span data-ttu-id="73ca0-117">对于 C#，要传递的用于指定的字符串<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>是`internal`。</span><span class="sxs-lookup"><span data-stu-id="73ca0-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
-   <span data-ttu-id="73ca0-118">用于 Microsoft Visual Basic.NET，要传递的用于指定的字符串<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>是`Friend`。</span><span class="sxs-lookup"><span data-stu-id="73ca0-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
-   <span data-ttu-id="73ca0-119">有关[!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)]，没有目标存在支持编译 XAML 的; 因此，未指定要传递的值。</span><span class="sxs-lookup"><span data-stu-id="73ca0-119">For [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="73ca0-120">此外可以指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>(`public`在 C# 中，`Public`在 Visual Basic 中); 但是，指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>很少做是因为<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>已经是默认行为。</span><span class="sxs-lookup"><span data-stu-id="73ca0-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="73ca0-121">其他值，相当的用户代码访问级别的限制，如`private`在 C# 中，不是适用于`x:ClassModifier`因为 XAML，不支持嵌套的类的引用，因此，<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>修饰符具有相同的效果。</span><span class="sxs-lookup"><span data-stu-id="73ca0-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="73ca0-122">安全说明</span><span class="sxs-lookup"><span data-stu-id="73ca0-122">Security Notes</span></span>  
 <span data-ttu-id="73ca0-123">中声明的访问级别`x:ClassModifier`仍取决于特定的框架和及其功能的解释。</span><span class="sxs-lookup"><span data-stu-id="73ca0-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="73ca0-124">WPF 还包括加载和实例化类型的功能，`x:ClassModifier`是`internal`，如果该类从 WPF 资源通过 URI 引用的包引用。</span><span class="sxs-lookup"><span data-stu-id="73ca0-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="73ca0-125">这种情况下以及可能其他类似的其他框架实现，因此不要依赖于以独占方式在`x:ClassModifier`来阻止所有可能实例化尝试。</span><span class="sxs-lookup"><span data-stu-id="73ca0-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73ca0-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="73ca0-126">See also</span></span>
- [<span data-ttu-id="73ca0-127">x:Class 指令</span><span class="sxs-lookup"><span data-stu-id="73ca0-127">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)
- [<span data-ttu-id="73ca0-128">WPF 中的代码隐藏和 XAML</span><span class="sxs-lookup"><span data-stu-id="73ca0-128">Code-Behind and XAML in WPF</span></span>](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="73ca0-129">x:FieldModifier 指令</span><span class="sxs-lookup"><span data-stu-id="73ca0-129">x:FieldModifier Directive</span></span>](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)
- [<span data-ttu-id="73ca0-130">安全性 (WPF)</span><span class="sxs-lookup"><span data-stu-id="73ca0-130">Security (WPF)</span></span>](../../../docs/framework/wpf/security-wpf.md)
- [<span data-ttu-id="73ca0-131">从 WPF 迁移到 System.Xaml 的类型</span><span class="sxs-lookup"><span data-stu-id="73ca0-131">Types Migrated from WPF to System.Xaml</span></span>](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
