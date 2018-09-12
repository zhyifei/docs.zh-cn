---
title: 抽象（抽象类型和接口）
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ad8b2dd3dbf2a7a75c98a3115d4351dfea4e1a0
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2018
ms.locfileid: "44698353"
---
# <a name="abstractions-abstract-types-and-interfaces"></a><span data-ttu-id="66c98-102">抽象（抽象类型和接口）</span><span class="sxs-lookup"><span data-stu-id="66c98-102">Abstractions (Abstract Types and Interfaces)</span></span>
<span data-ttu-id="66c98-103">一种抽象是描述协定，但不提供完整的实现的协定的类型。</span><span class="sxs-lookup"><span data-stu-id="66c98-103">An abstraction is a type that describes a contract but does not provide a full implementation of the contract.</span></span> <span data-ttu-id="66c98-104">通常作为抽象类或接口，实现的抽象概念以及它们与一组定义完善的参考文档，描述所需的语义的实现的协定的类型。</span><span class="sxs-lookup"><span data-stu-id="66c98-104">Abstractions are usually implemented as abstract classes or interfaces, and they come with a well-defined set of reference documentation describing the required semantics of the types implementing the contract.</span></span> <span data-ttu-id="66c98-105">一些.NET Framework 中最重要的抽象包括<xref:System.IO.Stream>， <xref:System.Collections.Generic.IEnumerable%601>，和<xref:System.Object>。</span><span class="sxs-lookup"><span data-stu-id="66c98-105">Some of the most important abstractions in the .NET Framework include <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, and <xref:System.Object>.</span></span>  
  
 <span data-ttu-id="66c98-106">您可以通过实现支持一种抽象的协定的具体类型和使用框架 Api 使用 （操作系统上） 使用此具体类型来扩展框架的抽象。</span><span class="sxs-lookup"><span data-stu-id="66c98-106">You can extend frameworks by implementing a concrete type that supports the contract of an abstraction and using this concrete type with framework APIs consuming (operating on) the abstraction.</span></span>  
  
 <span data-ttu-id="66c98-107">一种有意义且有用的抽象，能够承受测试是时间的很难设计。</span><span class="sxs-lookup"><span data-stu-id="66c98-107">A meaningful and useful abstraction that is able to withstand the test of time is very difficult to design.</span></span> <span data-ttu-id="66c98-108">主要困难获取正确成员，没有更多并没有更少的集。</span><span class="sxs-lookup"><span data-stu-id="66c98-108">The main difficulty is getting the right set of members, no more and no fewer.</span></span> <span data-ttu-id="66c98-109">如果抽象具有太多的成员，将很难或几乎不可能实现。</span><span class="sxs-lookup"><span data-stu-id="66c98-109">If an abstraction has too many members, it becomes difficult or even impossible to implement.</span></span> <span data-ttu-id="66c98-110">如果是承诺的功能的成员太少，变得无用的许多有趣的情形。</span><span class="sxs-lookup"><span data-stu-id="66c98-110">If it has too few members for the promised functionality, it becomes useless in many interesting scenarios.</span></span>  
  
 <span data-ttu-id="66c98-111">框架中的太多抽象还产生负面影响的 framework 的可用性。</span><span class="sxs-lookup"><span data-stu-id="66c98-111">Too many abstractions in a framework also negatively affect usability of the framework.</span></span> <span data-ttu-id="66c98-112">通常是很难理解抽象，无需了解它如何适用于具体的实现和对抽象操作的 Api 的更大的图片。</span><span class="sxs-lookup"><span data-stu-id="66c98-112">It is often quite difficult to understand an abstraction without understanding how it fits into the larger picture of the concrete implementations and the APIs operating on the abstraction.</span></span> <span data-ttu-id="66c98-113">此外，抽象和其成员的名称是一定是抽象的这通常会使它们比较难懂且 unapproachable 而无需第一个了解其使用情况的更广泛的上下文。</span><span class="sxs-lookup"><span data-stu-id="66c98-113">Also, names of abstractions and their members are necessarily abstract, which often makes them cryptic and unapproachable without first understanding the broader context of their usage.</span></span>  
  
 <span data-ttu-id="66c98-114">但是，抽象提供非常强大的可扩展性的其他扩展性机制通常不能与匹配。</span><span class="sxs-lookup"><span data-stu-id="66c98-114">However, abstractions provide extremely powerful extensibility that the other extensibility mechanisms cannot often match.</span></span> <span data-ttu-id="66c98-115">它们的许多体系结构模式，如插件，核心反转控制 (IoC)、 管道和等等。</span><span class="sxs-lookup"><span data-stu-id="66c98-115">They are at the core of many architectural patterns, such as plug-ins, inversion of control (IoC), pipelines, and so on.</span></span> <span data-ttu-id="66c98-116">它们也是非常重要的可测试性的框架。</span><span class="sxs-lookup"><span data-stu-id="66c98-116">They are also extremely important for testability of frameworks.</span></span> <span data-ttu-id="66c98-117">很好的抽象，使得可以去掉用于单元测试的大量依赖关系。</span><span class="sxs-lookup"><span data-stu-id="66c98-117">Good abstractions make it possible to stub out heavy dependencies for the purpose of unit testing.</span></span> <span data-ttu-id="66c98-118">总之，抽象是负责的现代面向对象的框架广受欢迎的丰富功能。</span><span class="sxs-lookup"><span data-stu-id="66c98-118">In summary, abstractions are responsible for the sought-after richness of the modern object-oriented frameworks.</span></span>  
  
 <span data-ttu-id="66c98-119">**X DO NOT** 提供抽象，除非它们通过开发几个具体实现和使用抽象的 Api 测试过。</span><span class="sxs-lookup"><span data-stu-id="66c98-119">**X DO NOT** provide abstractions unless they are tested by developing several concrete implementations and APIs consuming the abstractions.</span></span>  
  
 <span data-ttu-id="66c98-120">**✓ DO** 设计抽象时，请仔细选择一个抽象类和接口之间。</span><span class="sxs-lookup"><span data-stu-id="66c98-120">**✓ DO** choose carefully between an abstract class and an interface when designing an abstraction.</span></span>  
  
 <span data-ttu-id="66c98-121">**✓ CONSIDER** 提供抽象的具体实现的引用测试。</span><span class="sxs-lookup"><span data-stu-id="66c98-121">**✓ CONSIDER** providing reference tests for concrete implementations of abstractions.</span></span> <span data-ttu-id="66c98-122">此类测试应允许用户以测试是否它们的实现正确地实现该协定。</span><span class="sxs-lookup"><span data-stu-id="66c98-122">Such tests should allow users to test whether their implementations correctly implement the contract.</span></span>  
  
 <span data-ttu-id="66c98-123">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="66c98-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="66c98-124">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="66c98-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66c98-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="66c98-125">See also</span></span>

- [<span data-ttu-id="66c98-126">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="66c98-126">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="66c98-127">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="66c98-127">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
