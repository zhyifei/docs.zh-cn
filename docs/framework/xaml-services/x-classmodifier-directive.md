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
ms.openlocfilehash: c3c08f61b49a6367663cf02099dda86d1a692284
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484744"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="7e306-102">x:ClassModifier 指令</span><span class="sxs-lookup"><span data-stu-id="7e306-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="7e306-103">如果`x:Class`还提供了, 则修改 XAML 编译行为。</span><span class="sxs-lookup"><span data-stu-id="7e306-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="7e306-104">具体而言, 而不是创建`class` `Public`具有访问级别 ( `x:Class`默认值) 的部分, 而是创建具有`NotPublic`访问级别的。</span><span class="sxs-lookup"><span data-stu-id="7e306-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="7e306-105">此行为会影响生成的程序集中类的访问级别。</span><span class="sxs-lookup"><span data-stu-id="7e306-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="7e306-106">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="7e306-106">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="7e306-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="7e306-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7e306-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="7e306-108">*NotPublic*</span></span>|<span data-ttu-id="7e306-109">要传递给指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>的确切字符串与<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>不同, 具体取决于所使用的代码隐藏编程语言。</span><span class="sxs-lookup"><span data-stu-id="7e306-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="7e306-110">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="7e306-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="7e306-111">依赖项</span><span class="sxs-lookup"><span data-stu-id="7e306-111">Dependencies</span></span>  
 <span data-ttu-id="7e306-112">还必须在同一元素上提供[x:Class](x-class-directive.md) , 并且该元素必须是页面中的根元素。</span><span class="sxs-lookup"><span data-stu-id="7e306-112">[x:Class](x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="7e306-113">有关详细信息, 请参阅[ \[\] 4.3.1.8 部分](https://go.microsoft.com/fwlink/?LinkId=114525)。</span><span class="sxs-lookup"><span data-stu-id="7e306-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e306-114">备注</span><span class="sxs-lookup"><span data-stu-id="7e306-114">Remarks</span></span>  
 <span data-ttu-id="7e306-115">.NET Framework XAML 服务`x:ClassModifier`用法的值因编程语言而异。</span><span class="sxs-lookup"><span data-stu-id="7e306-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="7e306-116">要使用的字符串取决于每种语言如何实现<xref:System.CodeDom.Compiler.CodeDomProvider>其和返回的类型转换器, 以定义<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>和<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>的含义, 以及该语言是否区分大小写。</span><span class="sxs-lookup"><span data-stu-id="7e306-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="7e306-117">对于C#, 要传递的要传递<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>的字符串为。 `internal`</span><span class="sxs-lookup"><span data-stu-id="7e306-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
- <span data-ttu-id="7e306-118">对于 Microsoft Visual Basic .net, 要传递<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `Friend`的字符串为。</span><span class="sxs-lookup"><span data-stu-id="7e306-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
- <span data-ttu-id="7e306-119">对于C++/cli, 不存在支持编译 XAML 的目标;因此, 传递的值未指定。</span><span class="sxs-lookup"><span data-stu-id="7e306-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="7e306-120">你还可以在<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> Visual Basic`public`中C#指定`Public` (在中为); 但是<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> , 由于已是<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>默认行为, 因此不常指定。</span><span class="sxs-lookup"><span data-stu-id="7e306-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="7e306-121">具有等效用户代码访问级别限制的其他`private`值 (如在中C#) 与不相关`x:ClassModifier` , 因为 XAML 中不支持嵌套类引用, 因此, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>修饰符具有相同的效果.</span><span class="sxs-lookup"><span data-stu-id="7e306-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="7e306-122">安全说明</span><span class="sxs-lookup"><span data-stu-id="7e306-122">Security Notes</span></span>  
 <span data-ttu-id="7e306-123">中`x:ClassModifier`声明的访问级别仍受特定框架及其功能的解释。</span><span class="sxs-lookup"><span data-stu-id="7e306-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="7e306-124">Wpf 包含加载和实例化类型的功能`x:ClassModifier` , `internal`其中, 如果通过包 URI 引用从 WPF 资源引用此类, 则为。</span><span class="sxs-lookup"><span data-stu-id="7e306-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="7e306-125">这种情况与其他框架所实现的情况类似, 但并不依赖`x:ClassModifier`于阻止所有可能的实例化尝试。</span><span class="sxs-lookup"><span data-stu-id="7e306-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e306-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e306-126">See also</span></span>

- [<span data-ttu-id="7e306-127">x:Class 指令</span><span class="sxs-lookup"><span data-stu-id="7e306-127">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="7e306-128">WPF 中的代码隐藏和 XAML</span><span class="sxs-lookup"><span data-stu-id="7e306-128">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="7e306-129">x:FieldModifier 指令</span><span class="sxs-lookup"><span data-stu-id="7e306-129">x:FieldModifier Directive</span></span>](x-fieldmodifier-directive.md)
- [<span data-ttu-id="7e306-130">安全性 (WPF)</span><span class="sxs-lookup"><span data-stu-id="7e306-130">Security (WPF)</span></span>](../wpf/security-wpf.md)
- [<span data-ttu-id="7e306-131">从 WPF 迁移到 System.Xaml 的类型</span><span class="sxs-lookup"><span data-stu-id="7e306-131">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
