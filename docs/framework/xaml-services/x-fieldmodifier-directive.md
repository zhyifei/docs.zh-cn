---
title: x:FieldModifier 指令
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 646ad1ca99d83f9fb2994f3c394eca27a60c0eac
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484722"
---
# <a name="xfieldmodifier-directive"></a><span data-ttu-id="9d449-102">x:FieldModifier 指令</span><span class="sxs-lookup"><span data-stu-id="9d449-102">x:FieldModifier Directive</span></span>
<span data-ttu-id="9d449-103">修改 XAML 编译行为, 以便使用<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> access 而不<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>是默认行为来定义命名对象引用的字段。</span><span class="sxs-lookup"><span data-stu-id="9d449-103">Modifies XAML compilation behavior so that fields for named object references are defined with <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> access instead of the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> default behavior.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="9d449-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="9d449-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="9d449-105">XAML 值</span><span class="sxs-lookup"><span data-stu-id="9d449-105">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9d449-106">*Public*</span><span class="sxs-lookup"><span data-stu-id="9d449-106">*Public*</span></span>|<span data-ttu-id="9d449-107">传递给指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>的确切字符串与<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>不同, 具体取决于所使用的代码隐藏编程语言。</span><span class="sxs-lookup"><span data-stu-id="9d449-107">The exact string you pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that is used.</span></span> <span data-ttu-id="9d449-108">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="9d449-108">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="9d449-109">依赖项</span><span class="sxs-lookup"><span data-stu-id="9d449-109">Dependencies</span></span>  
 <span data-ttu-id="9d449-110">如果 xaml 生产使用`x:FieldModifier`任意位置, 则该 xaml 生产的根元素必须声明[x:Class 指令](x-class-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="9d449-110">If a XAML production uses `x:FieldModifier` anywhere, the root element of that XAML production must declare an [x:Class Directive](x-class-directive.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d449-111">备注</span><span class="sxs-lookup"><span data-stu-id="9d449-111">Remarks</span></span>  
 <span data-ttu-id="9d449-112">`x:FieldModifier`与声明类或其成员的常规访问级别无关。</span><span class="sxs-lookup"><span data-stu-id="9d449-112">`x:FieldModifier` is not relevant for declaring the general access level of a class or its members.</span></span> <span data-ttu-id="9d449-113">当处理作为 XAML 生产一部分的特定 XAML 对象时, 此方法仅适用于 XAML 处理行为, 并成为可在应用程序的对象图中访问的对象。</span><span class="sxs-lookup"><span data-stu-id="9d449-113">It is relevant only for XAML-processing behavior when a particular XAML object that is part of a XAML production is processed, and becomes an object that is potentially accessible in the object graph of an application.</span></span> <span data-ttu-id="9d449-114">默认情况下, 此类对象的字段引用保持为私有, 这会阻止控件使用者直接修改对象图。</span><span class="sxs-lookup"><span data-stu-id="9d449-114">By default, the field reference for such an object is kept private, which prevents control consumers from modifying the object graph directly.</span></span> <span data-ttu-id="9d449-115">相反, 控件使用者应该使用由编程模型启用的标准模式 (如通过获取布局根、子元素集合、专用公共属性等) 来修改对象关系图。</span><span class="sxs-lookup"><span data-stu-id="9d449-115">Instead, control consumers are expected to modify the object graph by using standard patterns that are enabled by programming models, such as by obtaining the layout root, the child element collections, the dedicated public properties, and so on.</span></span>  
  
 <span data-ttu-id="9d449-116">`x:FieldModifier`特性的值因编程语言而异, 其用途在特定框架中可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="9d449-116">The value for the `x:FieldModifier` attribute varies by programming language, and its purpose can vary in specific frameworks.</span></span> <span data-ttu-id="9d449-117">要使用的字符串取决于每种语言如何实现<xref:System.CodeDom.Compiler.CodeDomProvider>其和返回的类型转换器, 以定义<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>和<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>的含义, 以及该语言是否区分大小写。</span><span class="sxs-lookup"><span data-stu-id="9d449-117">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="9d449-118">对于C#, 要传递的要传递<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>的字符串为。 `public`</span><span class="sxs-lookup"><span data-stu-id="9d449-118">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `public`.</span></span>  
  
- <span data-ttu-id="9d449-119">对于 Microsoft Visual Basic .net, 要传递<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `Public`的字符串为。</span><span class="sxs-lookup"><span data-stu-id="9d449-119">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `Public`.</span></span>  
  
- <span data-ttu-id="9d449-120">对于C++/cli, 当前不存在 XAML 的目标;因此, 传递的字符串未定义。</span><span class="sxs-lookup"><span data-stu-id="9d449-120">For C++/CLI, no targets for XAML currently exist; therefore, the string to pass is undefined.</span></span>  
  
 <span data-ttu-id="9d449-121">你还可以在<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Visual Basic`internal`中C#指定`Friend` (在中), <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>但指定不`NotPublic`常见, 因为行为已是默认值。</span><span class="sxs-lookup"><span data-stu-id="9d449-121">You can also specify <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` in C#, `Friend` in Visual Basic) but specifying <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is unusual because `NotPublic` as the behavior is already the default.</span></span>  
  
 <span data-ttu-id="9d449-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>是默认行为, 因为编译 XAML 的程序集之外的代码很少需要访问 XAML 创建的元素。</span><span class="sxs-lookup"><span data-stu-id="9d449-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is the default behavior because it is infrequent that code outside the assembly that compiled the XAML needs access to a XAML-created element.</span></span> <span data-ttu-id="9d449-123">WPF 安全体系结构与 XAML 编译行为一起不会声明将元素实例存储为公共的字段, 除非您专门`x:FieldModifier`将设置为允许公共访问。</span><span class="sxs-lookup"><span data-stu-id="9d449-123">WPF security architecture together with XAML compilation behavior will not declare fields that store element instances as public, unless you specifically set the `x:FieldModifier` to allow public access.</span></span>  
  
 <span data-ttu-id="9d449-124">`x:FieldModifier`仅适用于具有[X:Name 指令](x-name-directive.md)的元素, 因为该名称用于在其公开后引用字段。</span><span class="sxs-lookup"><span data-stu-id="9d449-124">`x:FieldModifier` is only relevant for elements with an [x:Name Directive](x-name-directive.md) because that name is used to reference the field after it is public.</span></span>  
  
 <span data-ttu-id="9d449-125">默认情况下, 根元素的分部类是公共的;但是, 可以使用[X:ClassModifier 指令](x-classmodifier-directive.md)使其成为非公共的。</span><span class="sxs-lookup"><span data-stu-id="9d449-125">By default, the partial class for the root element is public; however, you can make it nonpublic by using the [x:ClassModifier Directive](x-classmodifier-directive.md).</span></span> <span data-ttu-id="9d449-126">[X:ClassModifier 指令](x-classmodifier-directive.md)还会影响 root 元素类的实例的访问级别。</span><span class="sxs-lookup"><span data-stu-id="9d449-126">The [x:ClassModifier Directive](x-classmodifier-directive.md) also affects the access level of the instance of the root element class.</span></span> <span data-ttu-id="9d449-127">你可以将`x:Name`和`x:FieldModifier`置于根元素上, 但这只会生成根元素的公共字段副本, 其真正的根元素类访问级别仍由[x:ClassModifier 指令](x-classmodifier-directive.md)控制。</span><span class="sxs-lookup"><span data-stu-id="9d449-127">You can put both `x:Name` and `x:FieldModifier` on the root element, but this only makes a public field copy of the root element, with the true root element class access level still controlled by [x:ClassModifier Directive](x-classmodifier-directive.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d449-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d449-128">See also</span></span>

- [<span data-ttu-id="9d449-129">XAML 及 WPF 的自定义类</span><span class="sxs-lookup"><span data-stu-id="9d449-129">XAML and Custom Classes for WPF</span></span>](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [<span data-ttu-id="9d449-130">WPF 中的代码隐藏和 XAML</span><span class="sxs-lookup"><span data-stu-id="9d449-130">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="9d449-131">x:Name 指令</span><span class="sxs-lookup"><span data-stu-id="9d449-131">x:Name Directive</span></span>](x-name-directive.md)
- <span data-ttu-id="9d449-132">[Building a WPF Application (WPF)](../wpf/app-development/building-a-wpf-application-wpf.md)（生成 WPF 应用程序 (WPF)）</span><span class="sxs-lookup"><span data-stu-id="9d449-132">[Building a WPF Application (WPF)](../wpf/app-development/building-a-wpf-application-wpf.md)</span></span>
- [<span data-ttu-id="9d449-133">x:ClassModifier 指令</span><span class="sxs-lookup"><span data-stu-id="9d449-133">x:ClassModifier Directive</span></span>](x-classmodifier-directive.md)
