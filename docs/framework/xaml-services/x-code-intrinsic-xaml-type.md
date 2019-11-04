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
ms.openlocfilehash: 7312c59cdcddfdbda39a4a9f05788b6a021f9b75
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459586"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="409e9-102">x:Code 内部 XAML 类型</span><span class="sxs-lookup"><span data-stu-id="409e9-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="409e9-103">允许在 XAML 生产中放置代码。</span><span class="sxs-lookup"><span data-stu-id="409e9-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="409e9-104">此类代码可由编译 XAML 的任何 XAML 处理器实现进行编译，或在 XAML 生产环境中保留，以供以后使用（如运行时的解释）使用。</span><span class="sxs-lookup"><span data-stu-id="409e9-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="409e9-105">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="409e9-105">XAML Object Element Usage</span></span>  
  
```xaml  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a><span data-ttu-id="409e9-106">备注</span><span class="sxs-lookup"><span data-stu-id="409e9-106">Remarks</span></span>  
 <span data-ttu-id="409e9-107">`x:Code` XAML 指令元素中的代码仍会在提供的常规 XML 命名空间和 XAML 命名空间中进行解释。</span><span class="sxs-lookup"><span data-stu-id="409e9-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="409e9-108">因此，通常需要将用于 `x:Code` 的代码放在 `CDATA` 段中。</span><span class="sxs-lookup"><span data-stu-id="409e9-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>  
  
 <span data-ttu-id="409e9-109">XAML 生产的所有可能的部署机制都不允许 `x:Code`。</span><span class="sxs-lookup"><span data-stu-id="409e9-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="409e9-110">在特定框架（如 WPF）中，必须编译代码。</span><span class="sxs-lookup"><span data-stu-id="409e9-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="409e9-111">在其他框架中，可能通常不允许使用 `x:Code`。</span><span class="sxs-lookup"><span data-stu-id="409e9-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>  
  
 <span data-ttu-id="409e9-112">对于允许托管 `x:Code` 内容的框架，用于 `x:Code` 内容的正确语言编译器由用于编译应用程序的包含项目的设置和目标决定。</span><span class="sxs-lookup"><span data-stu-id="409e9-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="409e9-113">WPF 使用说明</span><span class="sxs-lookup"><span data-stu-id="409e9-113">WPF Usage Notes</span></span>  
 <span data-ttu-id="409e9-114">在 WPF `x:Code` 中声明的代码有几个值得注意的限制：</span><span class="sxs-lookup"><span data-stu-id="409e9-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>  
  
- <span data-ttu-id="409e9-115">`x:Code` 指令元素必须是 XAML 生产的根元素的直接子元素。</span><span class="sxs-lookup"><span data-stu-id="409e9-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>  
  
- <span data-ttu-id="409e9-116">必须在父根元素上提供[X：Class 指令](x-class-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="409e9-116">[x:Class Directive](x-class-directive.md) must be provided on the parent root element.</span></span>  
  
- <span data-ttu-id="409e9-117">放置在 `x:Code` 中的代码将被编译视为在已为该 XAML 页创建的分部类的范围内。</span><span class="sxs-lookup"><span data-stu-id="409e9-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="409e9-118">因此，您定义的所有代码必须是此分部类的成员或变量。</span><span class="sxs-lookup"><span data-stu-id="409e9-118">Therefore all code you define must be members or variables of that partial class.</span></span>  
  
- <span data-ttu-id="409e9-119">除了在分部类中嵌套类之外，你不能定义其他类（允许嵌套，但这不是典型的，因为不能在 XAML 中引用嵌套类）。</span><span class="sxs-lookup"><span data-stu-id="409e9-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="409e9-120">不能定义用于现有分部类的命名空间，也不能将其添加到中。</span><span class="sxs-lookup"><span data-stu-id="409e9-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>  
  
- <span data-ttu-id="409e9-121">对分部类之外的代码实体的引用必须完全限定。</span><span class="sxs-lookup"><span data-stu-id="409e9-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="409e9-122">如果被声明的成员被替代为分部类可重写成员，则必须用特定语言的 override 关键字指定此项。</span><span class="sxs-lookup"><span data-stu-id="409e9-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="409e9-123">如果在 `x:Code` 作用域中声明的成员与在 XAML 中创建的分部类的成员冲突，则编译器将报告冲突，而 XAML 文件将无法编译或加载。</span><span class="sxs-lookup"><span data-stu-id="409e9-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="409e9-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="409e9-124">See also</span></span>

- [<span data-ttu-id="409e9-125">x:Class 指令</span><span class="sxs-lookup"><span data-stu-id="409e9-125">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="409e9-126">WPF 中的代码隐藏和 XAML</span><span class="sxs-lookup"><span data-stu-id="409e9-126">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="409e9-127">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="409e9-127">XAML Overview (WPF)</span></span>](../../desktop-wpf/fundamentals/xaml.md)
