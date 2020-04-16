---
title: x:Code 内部 XAML 类型
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 4da72ed630c1df001e3fd6c7e55f866b94c4d9b1
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432802"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="16604-102">x:Code 内部 XAML 类型</span><span class="sxs-lookup"><span data-stu-id="16604-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="16604-103">允许在 XAML 生产中放置代码。</span><span class="sxs-lookup"><span data-stu-id="16604-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="16604-104">此类代码可以由编译 XAML 的任何 XAML 处理器实现编译，也可以保留在 XAML 生产中供以后使用，例如运行时的解释。</span><span class="sxs-lookup"><span data-stu-id="16604-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="16604-105">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="16604-105">XAML Object Element Usage</span></span>

```xaml
<x:Code>
   // code instructions, usually enclosed by CDATA...
</x:Code>
```

## <a name="remarks"></a><span data-ttu-id="16604-106">备注</span><span class="sxs-lookup"><span data-stu-id="16604-106">Remarks</span></span>

<span data-ttu-id="16604-107">`x:Code` XAML 指令元素中的代码仍在常规 XML 命名空间和提供的 XAML 命名空间中解释。</span><span class="sxs-lookup"><span data-stu-id="16604-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="16604-108">因此，通常需要将用于段`x:Code`内的代码封闭。 `CDATA`</span><span class="sxs-lookup"><span data-stu-id="16604-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>

<span data-ttu-id="16604-109">`x:Code`不允许 XAML 生产的所有可能部署机制。</span><span class="sxs-lookup"><span data-stu-id="16604-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="16604-110">在特定框架（例如 WPF）中，必须编译代码。</span><span class="sxs-lookup"><span data-stu-id="16604-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="16604-111">在其他框架中，`x:Code`通常可能不允许使用。</span><span class="sxs-lookup"><span data-stu-id="16604-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>

<span data-ttu-id="16604-112">对于允许托管`x:Code`内容的框架，用于`x:Code`内容的正确语言编译器由用于编译应用程序的包含项目的设置和目标确定。</span><span class="sxs-lookup"><span data-stu-id="16604-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="16604-113">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="16604-113">WPF Usage Notes</span></span>

<span data-ttu-id="16604-114">`x:Code`为 WPF 声明的代码有几个值得注意的限制：</span><span class="sxs-lookup"><span data-stu-id="16604-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>

- <span data-ttu-id="16604-115">指令`x:Code`元素必须是 XAML 生产根元素的即时子元素。</span><span class="sxs-lookup"><span data-stu-id="16604-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>

- <span data-ttu-id="16604-116">[x：类指令](xclass-directive.md)必须在父根元素上提供。</span><span class="sxs-lookup"><span data-stu-id="16604-116">[x:Class Directive](xclass-directive.md) must be provided on the parent root element.</span></span>

- <span data-ttu-id="16604-117">将位于其中`x:Code`的代码通过编译处理为已为该 XAML 页创建的部分类的范围。</span><span class="sxs-lookup"><span data-stu-id="16604-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="16604-118">因此，您定义的所有代码都必须是该部分类的成员或变量。</span><span class="sxs-lookup"><span data-stu-id="16604-118">Therefore all code you define must be members or variables of that partial class.</span></span>

- <span data-ttu-id="16604-119">除了在部分类中嵌套类（允许嵌套，但它不是典型的，因为嵌套类无法在 XAML 中引用），因此无法定义其他类。</span><span class="sxs-lookup"><span data-stu-id="16604-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="16604-120">不能定义或添加到现有部分类的命名空间以外的 CLR 命名空间。</span><span class="sxs-lookup"><span data-stu-id="16604-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>

- <span data-ttu-id="16604-121">对部分类 CLR 命名空间外的代码实体的引用都必须完全限定。</span><span class="sxs-lookup"><span data-stu-id="16604-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="16604-122">如果声明的成员是覆盖到部分类重写成员，则必须使用特定于语言的重写关键字指定此参数。</span><span class="sxs-lookup"><span data-stu-id="16604-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="16604-123">如果在作用域中`x:Code`声明的成员与从 XAML 创建的部分类的成员发生冲突，编译器报告冲突的方式，XAML 文件无法编译或加载。</span><span class="sxs-lookup"><span data-stu-id="16604-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>

## <a name="see-also"></a><span data-ttu-id="16604-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="16604-124">See also</span></span>

- [<span data-ttu-id="16604-125">x:Class 指令</span><span class="sxs-lookup"><span data-stu-id="16604-125">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="16604-126">WPF 中的代码隐藏和 XAML</span><span class="sxs-lookup"><span data-stu-id="16604-126">Code-Behind and XAML in WPF</span></span>](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="16604-127">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="16604-127">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
