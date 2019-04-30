---
title: x:FieldModifier 指令
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: c20564bcf8a25b1b59887fbefe6419671e0d6c03
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971857"
---
# <a name="xfieldmodifier-directive"></a><span data-ttu-id="25ca6-102">x:FieldModifier 指令</span><span class="sxs-lookup"><span data-stu-id="25ca6-102">x:FieldModifier Directive</span></span>
<span data-ttu-id="25ca6-103">修改 XAML 编译行为，以便与定义的已命名的对象引用的字段<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>而不是访问<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>默认行为。</span><span class="sxs-lookup"><span data-stu-id="25ca6-103">Modifies XAML compilation behavior so that fields for named object references are defined with <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> access instead of the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> default behavior.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="25ca6-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="25ca6-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="25ca6-105">XAML 值</span><span class="sxs-lookup"><span data-stu-id="25ca6-105">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25ca6-106">*Public*</span><span class="sxs-lookup"><span data-stu-id="25ca6-106">*Public*</span></span>|<span data-ttu-id="25ca6-107">传递以指定确切的字符串<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>与<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>各不相同，具体取决于使用的代码隐藏编程语言。</span><span class="sxs-lookup"><span data-stu-id="25ca6-107">The exact string you pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that is used.</span></span> <span data-ttu-id="25ca6-108">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="25ca6-108">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="25ca6-109">依赖项</span><span class="sxs-lookup"><span data-stu-id="25ca6-109">Dependencies</span></span>  
 <span data-ttu-id="25ca6-110">如果使用 XAML 生产`x:FieldModifier`任意位置，该 XAML 生产的根元素必须声明[X:class 指令](x-class-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="25ca6-110">If a XAML production uses `x:FieldModifier` anywhere, the root element of that XAML production must declare an [x:Class Directive](x-class-directive.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25ca6-111">备注</span><span class="sxs-lookup"><span data-stu-id="25ca6-111">Remarks</span></span>  
 <span data-ttu-id="25ca6-112">`x:FieldModifier` 不相关的声明的类或其成员的常规访问级别。</span><span class="sxs-lookup"><span data-stu-id="25ca6-112">`x:FieldModifier` is not relevant for declaring the general access level of a class or its members.</span></span> <span data-ttu-id="25ca6-113">如果是 XAML 生产的一部分的特定 XAML 对象处理时，并将成为应用程序的对象图中可以访问的对象，此选项仅适用于 XAML 处理行为。</span><span class="sxs-lookup"><span data-stu-id="25ca6-113">It is relevant only for XAML-processing behavior when a particular XAML object that is part of a XAML production is processed, and becomes an object that is potentially accessible in the object graph of an application.</span></span> <span data-ttu-id="25ca6-114">默认情况下，此类对象的字段引用将保持私有，以防止控件使用者直接修改的对象图。</span><span class="sxs-lookup"><span data-stu-id="25ca6-114">By default, the field reference for such an object is kept private, which prevents control consumers from modifying the object graph directly.</span></span> <span data-ttu-id="25ca6-115">相反，控件使用者应使用标准模式的情况下启用的编程模型，如通过获取布局根、 子元素集合，专用的公共属性，修改对象图形等。</span><span class="sxs-lookup"><span data-stu-id="25ca6-115">Instead, control consumers are expected to modify the object graph by using standard patterns that are enabled by programming models, such as by obtaining the layout root, the child element collections, the dedicated public properties, and so on.</span></span>  
  
 <span data-ttu-id="25ca6-116">值为`x:FieldModifier`属性因编程语言，并在特定框架中它的用途而异。</span><span class="sxs-lookup"><span data-stu-id="25ca6-116">The value for the `x:FieldModifier` attribute varies by programming language, and its purpose can vary in specific frameworks.</span></span> <span data-ttu-id="25ca6-117">要使用的字符串取决于如何实现每种语言及其<xref:System.CodeDom.Compiler.CodeDomProvider>和类型转换器，它将返回定义的含义<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>和<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>，以及该语言是否区分大小写。</span><span class="sxs-lookup"><span data-stu-id="25ca6-117">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="25ca6-118">对于 C#，要传递的用于指定的字符串<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>是`public`。</span><span class="sxs-lookup"><span data-stu-id="25ca6-118">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `public`.</span></span>  
  
- <span data-ttu-id="25ca6-119">用于 Microsoft Visual Basic.NET，要传递的用于指定的字符串<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>是`Public`。</span><span class="sxs-lookup"><span data-stu-id="25ca6-119">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `Public`.</span></span>  
  
- <span data-ttu-id="25ca6-120">有关[!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)]，XAML 没有目标当前存在; 因此，要传递的字符串是不确定。</span><span class="sxs-lookup"><span data-stu-id="25ca6-120">For [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no targets for XAML currently exist; therefore, the string to pass is undefined.</span></span>  
  
 <span data-ttu-id="25ca6-121">此外可以指定<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>(`internal`中C#， `Friend` Visual Basic 中) 但指定<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>并不常见因为`NotPublic`因为该行为已是默认值。</span><span class="sxs-lookup"><span data-stu-id="25ca6-121">You can also specify <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` in C#, `Friend` in Visual Basic) but specifying <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is unusual because `NotPublic` as the behavior is already the default.</span></span>  
  
 <span data-ttu-id="25ca6-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 是默认行为，因为它不是很频繁编译 XAML 的程序集之外的代码需要访问 XAML 创建的元素。</span><span class="sxs-lookup"><span data-stu-id="25ca6-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is the default behavior because it is infrequent that code outside the assembly that compiled the XAML needs access to a XAML-created element.</span></span> <span data-ttu-id="25ca6-123">WPF 安全体系结构以及 XAML 编译行为将声明为公共，存储元素实例的字段，除非专门设置`x:FieldModifier`以允许公共访问。</span><span class="sxs-lookup"><span data-stu-id="25ca6-123">WPF security architecture together with XAML compilation behavior will not declare fields that store element instances as public, unless you specifically set the `x:FieldModifier` to allow public access.</span></span>  
  
 <span data-ttu-id="25ca6-124">`x:FieldModifier` 带有的元素才[X:name 指令](x-name-directive.md)因为该名称用于引用后它是公共字段。</span><span class="sxs-lookup"><span data-stu-id="25ca6-124">`x:FieldModifier` is only relevant for elements with an [x:Name Directive](x-name-directive.md) because that name is used to reference the field after it is public.</span></span>  
  
 <span data-ttu-id="25ca6-125">默认情况下，根元素的分部类是公共的则但是，您可以通过使其非公共使用[X:classmodifier 指令](x-classmodifier-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="25ca6-125">By default, the partial class for the root element is public; however, you can make it nonpublic by using the [x:ClassModifier Directive](x-classmodifier-directive.md).</span></span> <span data-ttu-id="25ca6-126">[X:classmodifier 指令](x-classmodifier-directive.md)还会影响根元素类的实例的访问级别。</span><span class="sxs-lookup"><span data-stu-id="25ca6-126">The [x:ClassModifier Directive](x-classmodifier-directive.md) also affects the access level of the instance of the root element class.</span></span> <span data-ttu-id="25ca6-127">将两者放入`x:Name`并`x:FieldModifier`根元素，但这仅生成公共字段副本的根元素，具有真正的根元素类访问级别仍受[X:classmodifier 指令](x-classmodifier-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="25ca6-127">You can put both `x:Name` and `x:FieldModifier` on the root element, but this only makes a public field copy of the root element, with the true root element class access level still controlled by [x:ClassModifier Directive](x-classmodifier-directive.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25ca6-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="25ca6-128">See also</span></span>

- [<span data-ttu-id="25ca6-129">XAML 及 WPF 的自定义类</span><span class="sxs-lookup"><span data-stu-id="25ca6-129">XAML and Custom Classes for WPF</span></span>](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [<span data-ttu-id="25ca6-130">WPF 中的代码隐藏和 XAML</span><span class="sxs-lookup"><span data-stu-id="25ca6-130">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="25ca6-131">x:Name 指令</span><span class="sxs-lookup"><span data-stu-id="25ca6-131">x:Name Directive</span></span>](x-name-directive.md)
- <span data-ttu-id="25ca6-132">[Building a WPF Application (WPF)](../wpf/app-development/building-a-wpf-application-wpf.md)（生成 WPF 应用程序 (WPF)）</span><span class="sxs-lookup"><span data-stu-id="25ca6-132">[Building a WPF Application (WPF)](../wpf/app-development/building-a-wpf-application-wpf.md)</span></span>
- [<span data-ttu-id="25ca6-133">x:ClassModifier 指令</span><span class="sxs-lookup"><span data-stu-id="25ca6-133">x:ClassModifier Directive</span></span>](x-classmodifier-directive.md)
