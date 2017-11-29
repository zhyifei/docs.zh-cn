---
title: ".NET 性能提示"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- C# language, performance
- performance [C#]
- Visual Basic, performance
- performance [Visual Basic]
ms.assetid: ae275793-857d-4102-9095-b4c2a02d57f4
caps.latest.revision: "36"
author: BillWagner
ms.author: wiwagn
manager: wpickett
ms.openlocfilehash: 93db69b67bfac3bcefbc818032aae64df0fd47b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="net-performance-tips"></a><span data-ttu-id="7f57c-102">.NET 性能提示</span><span class="sxs-lookup"><span data-stu-id="7f57c-102">.NET Performance Tips</span></span>
<span data-ttu-id="7f57c-103">术语“性能”通常指程序的执行速度。</span><span class="sxs-lookup"><span data-stu-id="7f57c-103">The term *performance* generally refers to the execution speed of a program.</span></span> <span data-ttu-id="7f57c-104">有时通过遵循源代码中的一些基本规则便可以提高执行速度。</span><span class="sxs-lookup"><span data-stu-id="7f57c-104">You can sometimes increase execution speed by following certain basic rules in your source code.</span></span> <span data-ttu-id="7f57c-105">在某些程序中，十分重要的一点是需要仔细检查代码并使用探查器确保程序尽可能快地运行。</span><span class="sxs-lookup"><span data-stu-id="7f57c-105">In some programs, it is important to examine code closely and use profilers to make sure that it is running as fast as possible.</span></span> <span data-ttu-id="7f57c-106">而在其他程序中，由于代码在编写时便运行得足够快，因此不必执行此类优化。</span><span class="sxs-lookup"><span data-stu-id="7f57c-106">In other programs, you do not have to perform such optimization because the code is running acceptably fast as it is written.</span></span> <span data-ttu-id="7f57c-107">本文列出了一些性能可能遭受影响的常见领域以及相关改进建议，并提供其他性能主题的链接。</span><span class="sxs-lookup"><span data-stu-id="7f57c-107">This article lists some common areas where performance can suffer and tips for improving it as well as links to additional performance topics.</span></span> <span data-ttu-id="7f57c-108">有关规划和测量性能的详细信息，请参阅[性能](../../../docs/framework/performance/index.md)</span><span class="sxs-lookup"><span data-stu-id="7f57c-108">For more information about planning and measuring for performance, see [Performance](../../../docs/framework/performance/index.md)</span></span>  
  
## <a name="boxing-and-unboxing"></a><span data-ttu-id="7f57c-109">装箱和取消装箱</span><span class="sxs-lookup"><span data-stu-id="7f57c-109">Boxing and Unboxing</span></span>  
 <span data-ttu-id="7f57c-110">如果值类型必须被频繁装箱，那么在这些情况下最好避免使用值类型（例如在诸如 <xref:System.Collections.ArrayList?displayProperty=nameWithType> 的非泛型集合类中）。</span><span class="sxs-lookup"><span data-stu-id="7f57c-110">It is best to avoid using value types in situations where they must be boxed a high number of times, for example in non-generic collections classes such as <xref:System.Collections.ArrayList?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7f57c-111">可通过使用泛型集合（例如 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>）来避免装箱值类型。</span><span class="sxs-lookup"><span data-stu-id="7f57c-111">You can avoid boxing of value types by using generic collections such as <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7f57c-112">装箱和取消装箱过程需要进行大量的计算。</span><span class="sxs-lookup"><span data-stu-id="7f57c-112">Boxing and unboxing are computationally expensive processes.</span></span> <span data-ttu-id="7f57c-113">对值类型进行装箱时，必须创建一个全新的对象。</span><span class="sxs-lookup"><span data-stu-id="7f57c-113">When a value type is boxed, an entirely new object must be created.</span></span> <span data-ttu-id="7f57c-114">这可能比简单的引用赋值用时最多长 20 倍。</span><span class="sxs-lookup"><span data-stu-id="7f57c-114">This can take up to 20 times longer than a simple reference assignment.</span></span> <span data-ttu-id="7f57c-115">取消装箱的过程所需时间可达赋值操作的四倍。</span><span class="sxs-lookup"><span data-stu-id="7f57c-115">When unboxing, the casting process can take four times as long as an assignment.</span></span> <span data-ttu-id="7f57c-116">有关详细信息，请参阅[装箱和取消装箱](~/docs/csharp/programming-guide/types/boxing-and-unboxing.md)。</span><span class="sxs-lookup"><span data-stu-id="7f57c-116">For more information, see [Boxing and Unboxing](~/docs/csharp/programming-guide/types/boxing-and-unboxing.md).</span></span>  
  
## <a name="strings"></a><span data-ttu-id="7f57c-117">字符串</span><span class="sxs-lookup"><span data-stu-id="7f57c-117">Strings</span></span>  
 <span data-ttu-id="7f57c-118">在连接大量字符串变量时，例如在紧凑循环中，请使用 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 而不是 C# [+ 运算符](~/docs/csharp/language-reference/operators/addition-operator.md)或 Visual Basic [串联运算符](~/docs/visual-basic/language-reference/operators/concatenation-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="7f57c-118">When you concatenate a large number of string variables, for example in a tight loop, use <xref:System.Text.StringBuilder?displayProperty=nameWithType> instead of the C# [+ operator](~/docs/csharp/language-reference/operators/addition-operator.md) or the Visual Basic [Concatenation Operators](~/docs/visual-basic/language-reference/operators/concatenation-operators.md).</span></span> <span data-ttu-id="7f57c-119">有关详细信息，请参阅[如何连接多个字符串](~/docs/csharp/programming-guide/strings/how-to-concatenate-multiple-strings.md)和 [Visual Basic 中的串联运算符](~/docs/visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="7f57c-119">For more information, see [How to: Concatenate Multiple Strings](~/docs/csharp/programming-guide/strings/how-to-concatenate-multiple-strings.md) and [Concatenation Operators in Visual Basic](~/docs/visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md).</span></span>  
  
## <a name="destructors"></a><span data-ttu-id="7f57c-120">析构函数</span><span class="sxs-lookup"><span data-stu-id="7f57c-120">Destructors</span></span>  
 <span data-ttu-id="7f57c-121">不应使用空的析构函数。</span><span class="sxs-lookup"><span data-stu-id="7f57c-121">Empty destructors should not be used.</span></span> <span data-ttu-id="7f57c-122">如果类包含析构函数，则 Finalize 队列中会创建一个条目。</span><span class="sxs-lookup"><span data-stu-id="7f57c-122">When a class contains a destructor, an entry is created in the Finalize queue.</span></span> <span data-ttu-id="7f57c-123">调用析构函数时，将调用垃圾回收器来处理此队列。</span><span class="sxs-lookup"><span data-stu-id="7f57c-123">When the destructor is called, the garbage collector is invoked to process the queue.</span></span> <span data-ttu-id="7f57c-124">如果析构函数为空，只会导致性能损失。</span><span class="sxs-lookup"><span data-stu-id="7f57c-124">If the destructor is empty, this simply results in a loss of performance.</span></span> <span data-ttu-id="7f57c-125">有关详细信息，请参阅[析构函数](~/docs/csharp/programming-guide/classes-and-structs/destructors.md)和[对象生存期：如何创建和销毁对象](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)。</span><span class="sxs-lookup"><span data-stu-id="7f57c-125">For more information, see [Destructors](~/docs/csharp/programming-guide/classes-and-structs/destructors.md) and [Object Lifetime: How Objects Are Created and Destroyed](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
## <a name="other-resources"></a><span data-ttu-id="7f57c-126">其他资源</span><span class="sxs-lookup"><span data-stu-id="7f57c-126">Other Resources</span></span>  
  
-   [<span data-ttu-id="7f57c-127">编写更快的托管代码：了解代价</span><span class="sxs-lookup"><span data-stu-id="7f57c-127">Writing Faster Managed Code: Know What Things Cost</span></span>](http://go.microsoft.com/fwlink/?LinkId=99294)  
  
-   [<span data-ttu-id="7f57c-128">编写高性能的托管应用程序：入门</span><span class="sxs-lookup"><span data-stu-id="7f57c-128">Writing High-Performance Managed Applications: A Primer</span></span>](http://go.microsoft.com/fwlink/?LinkId=99295)  
  
-   [<span data-ttu-id="7f57c-129">垃圾回收器基础知识和性能提示</span><span class="sxs-lookup"><span data-stu-id="7f57c-129">Garbage Collector Basics and Performance Hints</span></span>](http://go.microsoft.com/fwlink/?LinkId=99296)  
  
-   [<span data-ttu-id="7f57c-130">.NET 应用程序的性能提示和技巧</span><span class="sxs-lookup"><span data-stu-id="7f57c-130">Performance Tips and Tricks in .NET Applications</span></span>](http://go.microsoft.com/fwlink/?LinkId=99297)  
  
-   [<span data-ttu-id="7f57c-131">了解用于 .NET 的诊断工具</span><span class="sxs-lookup"><span data-stu-id="7f57c-131">Inside Diagnostic Tools for .NET</span></span>](http://go.microsoft.com/fwlink/?LinkId=112407)  
  
-   [<span data-ttu-id="7f57c-132">Rico Mariani 关于性能问题的见解</span><span class="sxs-lookup"><span data-stu-id="7f57c-132">Rico Mariani's Performance Tidbits</span></span>](http://go.microsoft.com/fwlink/?LinkId=115679)  
  
## <a name="see-also"></a><span data-ttu-id="7f57c-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f57c-133">See Also</span></span>  
 [<span data-ttu-id="7f57c-134">性能</span><span class="sxs-lookup"><span data-stu-id="7f57c-134">Performance</span></span>](../../../docs/framework/performance/index.md)  
 [<span data-ttu-id="7f57c-135">编程概念</span><span class="sxs-lookup"><span data-stu-id="7f57c-135">Programming Concepts</span></span>](http://msdn.microsoft.com/library/65c12cca-af4f-4017-886e-2dbc00a189d6)  
 [<span data-ttu-id="7f57c-136">Visual Basic 编程指南</span><span class="sxs-lookup"><span data-stu-id="7f57c-136">Visual Basic Programming Guide</span></span>](../../visual-basic/programming-guide/index.md)  
 [<span data-ttu-id="7f57c-137">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="7f57c-137">C# Programming Guide</span></span>](http://msdn.microsoft.com/library/ac0f23a2-6bf3-4077-be99-538ae5fd3bc5)
