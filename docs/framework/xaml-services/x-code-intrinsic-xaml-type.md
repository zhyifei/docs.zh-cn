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
ms.openlocfilehash: 7bb78b05be7b3edc4471bc276010eabd92a07a14
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145231"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="95aa4-102">x:Code 内部 XAML 类型</span><span class="sxs-lookup"><span data-stu-id="95aa4-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="95aa4-103">允许放置 XAML 生产中的代码。</span><span class="sxs-lookup"><span data-stu-id="95aa4-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="95aa4-104">此类代码也可以通过编译 XAML 或由运行时中以备后用，例如解释 XAML 生产留下任何 XAML 处理器实现编译。</span><span class="sxs-lookup"><span data-stu-id="95aa4-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="95aa4-105">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="95aa4-105">XAML Object Element Usage</span></span>  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a><span data-ttu-id="95aa4-106">备注</span><span class="sxs-lookup"><span data-stu-id="95aa4-106">Remarks</span></span>  
 <span data-ttu-id="95aa4-107">中的代码`x:Code`XAML 指令元素是仍在常规 XML 命名空间中解释和提供的 XAML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="95aa4-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="95aa4-108">因此，它是通常只需要使用的代码放入`x:Code`内`CDATA`段。</span><span class="sxs-lookup"><span data-stu-id="95aa4-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>  
  
 <span data-ttu-id="95aa4-109">`x:Code` 不允许的 XAML 生产的所有可能的部署机制。</span><span class="sxs-lookup"><span data-stu-id="95aa4-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="95aa4-110">在特定的框架 (如 WPF) 必须编译代码。</span><span class="sxs-lookup"><span data-stu-id="95aa4-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="95aa4-111">在其他框架`x:Code`可能通常不允许使用情况。</span><span class="sxs-lookup"><span data-stu-id="95aa4-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>  
  
 <span data-ttu-id="95aa4-112">允许托管的框架`x:Code`内容，正确的语言编译器用于`x:Code`内容由设置和用于编译应用程序的包含项目的目标。</span><span class="sxs-lookup"><span data-stu-id="95aa4-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="95aa4-113">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="95aa4-113">WPF Usage Notes</span></span>  
 <span data-ttu-id="95aa4-114">代码中声明`x:Code`WPF 有几个值得注意的限制：</span><span class="sxs-lookup"><span data-stu-id="95aa4-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>  
  
-   <span data-ttu-id="95aa4-115">`x:Code`指令元素必须是 XAML 生产的根元素的直接子元素。</span><span class="sxs-lookup"><span data-stu-id="95aa4-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>  
  
-   <span data-ttu-id="95aa4-116">[X:class 指令](x-class-directive.md)必须提供父根元素上。</span><span class="sxs-lookup"><span data-stu-id="95aa4-116">[x:Class Directive](x-class-directive.md) must be provided on the parent root element.</span></span>  
  
-   <span data-ttu-id="95aa4-117">该代码放在`x:Code`将被视为由编译为已经对此 XAML 页创建的分部类的作用域内。</span><span class="sxs-lookup"><span data-stu-id="95aa4-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="95aa4-118">因此您定义的所有代码必须都是该分部类的成员或变量。</span><span class="sxs-lookup"><span data-stu-id="95aa4-118">Therefore all code you define must be members or variables of that partial class.</span></span>  
  
-   <span data-ttu-id="95aa4-119">不能定义其他类，比由嵌套在分部类的类 （允许嵌套，但它不是典型因为嵌套的类不能在 XAML 中引用）。</span><span class="sxs-lookup"><span data-stu-id="95aa4-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="95aa4-120">不能定义或添加到用于现有的分部类的命名空间之外的 CLR 命名空间。</span><span class="sxs-lookup"><span data-stu-id="95aa4-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>  
  
-   <span data-ttu-id="95aa4-121">必须完全限定所有的分部类的 CLR 命名空间之外的代码实体的引用。</span><span class="sxs-lookup"><span data-stu-id="95aa4-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="95aa4-122">如果所声明的成员是重写的分部类可重写成员，这必须指定与特定于语言的 override 关键字。</span><span class="sxs-lookup"><span data-stu-id="95aa4-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="95aa4-123">如果在中声明成员`x:Code`作用域与带 XAML 创建的分部类的成员冲突，这样，编译器会报告冲突，XAML 文件无法编译或加载。</span><span class="sxs-lookup"><span data-stu-id="95aa4-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95aa4-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="95aa4-124">See also</span></span>

- [<span data-ttu-id="95aa4-125">x:Class 指令</span><span class="sxs-lookup"><span data-stu-id="95aa4-125">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="95aa4-126">WPF 中的代码隐藏和 XAML</span><span class="sxs-lookup"><span data-stu-id="95aa4-126">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="95aa4-127">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="95aa4-127">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
