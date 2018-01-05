---
title: "x:Code 内部 XAML 类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
caps.latest.revision: "19"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d39249a5d1c0e230d21e6d889b92d0b57c98e2ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="18c71-102">x:Code 内部 XAML 类型</span><span class="sxs-lookup"><span data-stu-id="18c71-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="18c71-103">允许在 XAML 生产的代码的放置位置。</span><span class="sxs-lookup"><span data-stu-id="18c71-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="18c71-104">也可以由任何编译 XAML，也可以由运行时留在更高版本使用 如解释在 XAML 生产的 XAML 处理器实现编译此类代码。</span><span class="sxs-lookup"><span data-stu-id="18c71-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="18c71-105">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="18c71-105">XAML Object Element Usage</span></span>  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a><span data-ttu-id="18c71-106">备注</span><span class="sxs-lookup"><span data-stu-id="18c71-106">Remarks</span></span>  
 <span data-ttu-id="18c71-107">中的代码内`x:Code`XAML 指令元素是仍然解释在常规 XML 命名空间中提供的 XAML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="18c71-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="18c71-108">因此，它是通常需将代码用于括`x:Code`内`CDATA`段。</span><span class="sxs-lookup"><span data-stu-id="18c71-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>  
  
 <span data-ttu-id="18c71-109">`x:Code`不是允许的 XAML 生成的所有可能的部署机制。</span><span class="sxs-lookup"><span data-stu-id="18c71-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="18c71-110">在特定框架 (如 WPF) 必须编译代码。</span><span class="sxs-lookup"><span data-stu-id="18c71-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="18c71-111">在其他框架，`x:Code`可能通常不允许使用情况。</span><span class="sxs-lookup"><span data-stu-id="18c71-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>  
  
 <span data-ttu-id="18c71-112">对于允许托管的框架`x:Code`内容，正确的语言编译器用于`x:Code`内容由设置和用于编译应用程序的包含项目的目标。</span><span class="sxs-lookup"><span data-stu-id="18c71-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="18c71-113">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="18c71-113">WPF Usage Notes</span></span>  
 <span data-ttu-id="18c71-114">中声明的代码`x:Code`WPF 有几个值得注意的限制：</span><span class="sxs-lookup"><span data-stu-id="18c71-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>  
  
-   <span data-ttu-id="18c71-115">`x:Code`指令元素必须在 XAML 生产的根元素的直接子元素。</span><span class="sxs-lookup"><span data-stu-id="18c71-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>  
  
-   <span data-ttu-id="18c71-116">[X:class 指令](../../../docs/framework/xaml-services/x-class-directive.md)必须提供父根元素上。</span><span class="sxs-lookup"><span data-stu-id="18c71-116">[x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md) must be provided on the parent root element.</span></span>  
  
-   <span data-ttu-id="18c71-117">代码放在`x:Code`将被视为编译已针对该 XAML 页正在创建的分部类的作用域内。</span><span class="sxs-lookup"><span data-stu-id="18c71-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="18c71-118">因此你定义的所有代码必须都是该分部类的成员或变量。</span><span class="sxs-lookup"><span data-stu-id="18c71-118">Therefore all code you define must be members or variables of that partial class.</span></span>  
  
-   <span data-ttu-id="18c71-119">不能定义其他类，而非由嵌套在分部类的类 （允许嵌套，但它并不是典型因为嵌套的类不能在 XAML 中引用）。</span><span class="sxs-lookup"><span data-stu-id="18c71-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="18c71-120">无法定义或添加到用于现有的分部类的命名空间之外的 CLR 命名空间。</span><span class="sxs-lookup"><span data-stu-id="18c71-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>  
  
-   <span data-ttu-id="18c71-121">必须完全限定所有对代码的分部类的 CLR 命名空间之外的实体的引用。</span><span class="sxs-lookup"><span data-stu-id="18c71-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="18c71-122">如果所声明的成员的分部类可重写成员的替代，这必须使用特定于语言的重写关键字指定。</span><span class="sxs-lookup"><span data-stu-id="18c71-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="18c71-123">如果在声明成员`x:Code`作用域与从 XAML 创建的分部类的成员冲突，因此的方式，则编译器将报告冲突时，XAML 文件无法编译或加载。</span><span class="sxs-lookup"><span data-stu-id="18c71-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18c71-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="18c71-124">See Also</span></span>  
 [<span data-ttu-id="18c71-125">x:Class 指令</span><span class="sxs-lookup"><span data-stu-id="18c71-125">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="18c71-126">WPF 中的代码隐藏和 XAML</span><span class="sxs-lookup"><span data-stu-id="18c71-126">Code-Behind and XAML in WPF</span></span>](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [<span data-ttu-id="18c71-127">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="18c71-127">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
