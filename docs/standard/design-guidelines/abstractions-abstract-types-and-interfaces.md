---
title: "抽象（抽象类型和接口）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d601ab89b08dd9e9bd0b27d2cfb1c495c33a2786
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="abstractions-abstract-types-and-interfaces"></a><span data-ttu-id="bf18a-102">抽象（抽象类型和接口）</span><span class="sxs-lookup"><span data-stu-id="bf18a-102">Abstractions (Abstract Types and Interfaces)</span></span>
<span data-ttu-id="bf18a-103">一种抽象是描述的协定，但不提供完整实现的协定的类型。</span><span class="sxs-lookup"><span data-stu-id="bf18a-103">An abstraction is a type that describes a contract but does not provide a full implementation of the contract.</span></span> <span data-ttu-id="bf18a-104">通常作为抽象类或接口，实现的抽象，而且随附一组明确定义的参考文档描述实现协定的类型所需的语义。</span><span class="sxs-lookup"><span data-stu-id="bf18a-104">Abstractions are usually implemented as abstract classes or interfaces, and they come with a well-defined set of reference documentation describing the required semantics of the types implementing the contract.</span></span> <span data-ttu-id="bf18a-105">.NET Framework 中最重要的抽象的一些包括<xref:System.IO.Stream>， <xref:System.Collections.Generic.IEnumerable%601>，和<xref:System.Object>。</span><span class="sxs-lookup"><span data-stu-id="bf18a-105">Some of the most important abstractions in the .NET Framework include <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, and <xref:System.Object>.</span></span>  
  
 <span data-ttu-id="bf18a-106">你可以通过实现支持协定的抽象的具体类型并使用此具体类型 framework Api 使用 （操作系统上） 来扩展框架的抽象。</span><span class="sxs-lookup"><span data-stu-id="bf18a-106">You can extend frameworks by implementing a concrete type that supports the contract of an abstraction and using this concrete type with framework APIs consuming (operating on) the abstraction.</span></span>  
  
 <span data-ttu-id="bf18a-107">能够承受测试有意义且有用抽象是时间的很难设计的。</span><span class="sxs-lookup"><span data-stu-id="bf18a-107">A meaningful and useful abstraction that is able to withstand the test of time is very difficult to design.</span></span> <span data-ttu-id="bf18a-108">主要困难获取正确的一组成员，没有更多和不较少。</span><span class="sxs-lookup"><span data-stu-id="bf18a-108">The main difficulty is getting the right set of members, no more and no fewer.</span></span> <span data-ttu-id="bf18a-109">如果一种抽象具有太多的成员，则它将成为难或甚至无法实现。</span><span class="sxs-lookup"><span data-stu-id="bf18a-109">If an abstraction has too many members, it becomes difficult or even impossible to implement.</span></span> <span data-ttu-id="bf18a-110">如果已承诺的功能的成员太少，则将没有用处，在许多有趣的方案。</span><span class="sxs-lookup"><span data-stu-id="bf18a-110">If it has too few members for the promised functionality, it becomes useless in many interesting scenarios.</span></span>  
  
 <span data-ttu-id="bf18a-111">框架中的太多抽象还造成负面影响的 framework 的可用性。</span><span class="sxs-lookup"><span data-stu-id="bf18a-111">Too many abstractions in a framework also negatively affect usability of the framework.</span></span> <span data-ttu-id="bf18a-112">它通常是很难了解一种抽象，而不了解它如何适用于具体的实现和抽象在操作的 Api 的较大的图片。</span><span class="sxs-lookup"><span data-stu-id="bf18a-112">It is often quite difficult to understand an abstraction without understanding how it fits into the larger picture of the concrete implementations and the APIs operating on the abstraction.</span></span> <span data-ttu-id="bf18a-113">此外，抽象和其成员的名称是一定抽象，这通常使得它们含义隐晦、 unapproachable 而不了解其使用情况的更广泛上下文第一个。</span><span class="sxs-lookup"><span data-stu-id="bf18a-113">Also, names of abstractions and their members are necessarily abstract, which often makes them cryptic and unapproachable without first understanding the broader context of their usage.</span></span>  
  
 <span data-ttu-id="bf18a-114">但是，抽象提供的其他扩展性机制通常不能与匹配的功能非常强大扩展性。</span><span class="sxs-lookup"><span data-stu-id="bf18a-114">However, abstractions provide extremely powerful extensibility that the other extensibility mechanisms cannot often match.</span></span> <span data-ttu-id="bf18a-115">它们的许多体系结构模式，如插件的核心是反向的控件 (IoC)、 管道，依次类推。</span><span class="sxs-lookup"><span data-stu-id="bf18a-115">They are at the core of many architectural patterns, such as plug-ins, inversion of control (IoC), pipelines, and so on.</span></span> <span data-ttu-id="bf18a-116">它们也是非常重要的框架可测试性。</span><span class="sxs-lookup"><span data-stu-id="bf18a-116">They are also extremely important for testability of frameworks.</span></span> <span data-ttu-id="bf18a-117">良好的抽象，使能够出繁重的依赖关系，用于单元测试存根。</span><span class="sxs-lookup"><span data-stu-id="bf18a-117">Good abstractions make it possible to stub out heavy dependencies for the purpose of unit testing.</span></span> <span data-ttu-id="bf18a-118">总之，抽象是负责广受欢迎的丰富功能，现代的面向对象的框架。</span><span class="sxs-lookup"><span data-stu-id="bf18a-118">In summary, abstractions are responsible for the sought-after richness of the modern object-oriented frameworks.</span></span>  
  
 <span data-ttu-id="bf18a-119">**X 不**提供抽象，除非它们通过开发几个具体实现和使用抽象的 Api 测试过。</span><span class="sxs-lookup"><span data-stu-id="bf18a-119">**X DO NOT** provide abstractions unless they are tested by developing several concrete implementations and APIs consuming the abstractions.</span></span>  
  
 <span data-ttu-id="bf18a-120">**✓ 执行**设计抽象时，请仔细选择一个抽象类和接口之间。</span><span class="sxs-lookup"><span data-stu-id="bf18a-120">**✓ DO** choose carefully between an abstract class and an interface when designing an abstraction.</span></span>  
  
 <span data-ttu-id="bf18a-121">**请考虑 ✓**提供抽象的具体实现的引用测试。</span><span class="sxs-lookup"><span data-stu-id="bf18a-121">**✓ CONSIDER** providing reference tests for concrete implementations of abstractions.</span></span> <span data-ttu-id="bf18a-122">此类测试应允许用户以测试是否其实现正确实现协定。</span><span class="sxs-lookup"><span data-stu-id="bf18a-122">Such tests should allow users to test whether their implementations correctly implement the contract.</span></span>  
  
 <span data-ttu-id="bf18a-123">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="bf18a-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="bf18a-124">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="bf18a-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf18a-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf18a-125">See Also</span></span>  
 [<span data-ttu-id="bf18a-126">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="bf18a-126">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="bf18a-127">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="bf18a-127">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
