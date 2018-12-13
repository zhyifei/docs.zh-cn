---
title: 抽象（抽象类型和接口）
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
author: KrzysztofCwalina
ms.openlocfilehash: 4ff79af968c8a0a360cade687b8c60cdd71de192
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149908"
---
# <a name="abstractions-abstract-types-and-interfaces"></a><span data-ttu-id="b3831-102">抽象（抽象类型和接口）</span><span class="sxs-lookup"><span data-stu-id="b3831-102">Abstractions (Abstract Types and Interfaces)</span></span>
<span data-ttu-id="b3831-103">抽象是一种描述协定但不提供协定的完整实现的类型。</span><span class="sxs-lookup"><span data-stu-id="b3831-103">An abstraction is a type that describes a contract but does not provide a full implementation of the contract.</span></span> <span data-ttu-id="b3831-104">抽象通常作为抽象类或接口实现，并带有一组明确定义的参考文档，该文档描述实现协定的类型的所需语义。</span><span class="sxs-lookup"><span data-stu-id="b3831-104">Abstractions are usually implemented as abstract classes or interfaces, and they come with a well-defined set of reference documentation describing the required semantics of the types implementing the contract.</span></span> <span data-ttu-id="b3831-105">.NET Framework 中一些最重要的抽象包括 <xref:System.IO.Stream>、<xref:System.Collections.Generic.IEnumerable%601> 和 <xref:System.Object>。</span><span class="sxs-lookup"><span data-stu-id="b3831-105">Some of the most important abstractions in the .NET Framework include <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, and <xref:System.Object>.</span></span>  
  
 <span data-ttu-id="b3831-106">可以扩展框架，方法是：先实现一个支持抽象协定的具体类型，然后将该具体类型与使用（操作）该抽象的框架 API 配合使用。</span><span class="sxs-lookup"><span data-stu-id="b3831-106">You can extend frameworks by implementing a concrete type that supports the contract of an abstraction and using this concrete type with framework APIs consuming (operating on) the abstraction.</span></span>  
  
 <span data-ttu-id="b3831-107">能够经得起时间考验的有意义且有用的抽象很难设计。</span><span class="sxs-lookup"><span data-stu-id="b3831-107">A meaningful and useful abstraction that is able to withstand the test of time is very difficult to design.</span></span> <span data-ttu-id="b3831-108">主要的困难是设置合适的成员，不能多也不能少。</span><span class="sxs-lookup"><span data-stu-id="b3831-108">The main difficulty is getting the right set of members, no more and no fewer.</span></span> <span data-ttu-id="b3831-109">如果抽象具有太多成员，将很难或几乎不可能实现。</span><span class="sxs-lookup"><span data-stu-id="b3831-109">If an abstraction has too many members, it becomes difficult or even impossible to implement.</span></span> <span data-ttu-id="b3831-110">如果承诺功能的成员太少，那么在很多重要的场景中它就变得毫无用处。</span><span class="sxs-lookup"><span data-stu-id="b3831-110">If it has too few members for the promised functionality, it becomes useless in many interesting scenarios.</span></span>  
  
 <span data-ttu-id="b3831-111">框架中太多的抽象也会对框架的可用性产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="b3831-111">Too many abstractions in a framework also negatively affect usability of the framework.</span></span> <span data-ttu-id="b3831-112">如果不理解抽象如何适应具体实现和抽象 API 操作的全局，通常很难理解抽象。</span><span class="sxs-lookup"><span data-stu-id="b3831-112">It is often quite difficult to understand an abstraction without understanding how it fits into the larger picture of the concrete implementations and the APIs operating on the abstraction.</span></span> <span data-ttu-id="b3831-113">此外，抽象的名称及其成员必然是抽象的，如果没有首先理解其使用的更广泛的背景，它们常常会变得更晦涩难懂。</span><span class="sxs-lookup"><span data-stu-id="b3831-113">Also, names of abstractions and their members are necessarily abstract, which often makes them cryptic and unapproachable without first understanding the broader context of their usage.</span></span>  
  
 <span data-ttu-id="b3831-114">但是，抽象提供了非常强大的可扩展性，其他可扩展性机制通常无法与其匹敌。</span><span class="sxs-lookup"><span data-stu-id="b3831-114">However, abstractions provide extremely powerful extensibility that the other extensibility mechanisms cannot often match.</span></span> <span data-ttu-id="b3831-115">它们是许多架构模式（例如插件、控制反转 (IoC)、管道等）的核心。</span><span class="sxs-lookup"><span data-stu-id="b3831-115">They are at the core of many architectural patterns, such as plug-ins, inversion of control (IoC), pipelines, and so on.</span></span> <span data-ttu-id="b3831-116">它们对于框架的可测试性也非常重要。</span><span class="sxs-lookup"><span data-stu-id="b3831-116">They are also extremely important for testability of frameworks.</span></span> <span data-ttu-id="b3831-117">良好的抽象能够为单元测试消除严重的依赖。</span><span class="sxs-lookup"><span data-stu-id="b3831-117">Good abstractions make it possible to stub out heavy dependencies for the purpose of unit testing.</span></span> <span data-ttu-id="b3831-118">总之，抽象让现代的面向对象的框架具有更受欢迎的丰富内涵。</span><span class="sxs-lookup"><span data-stu-id="b3831-118">In summary, abstractions are responsible for the sought-after richness of the modern object-oriented frameworks.</span></span>  
  
 <span data-ttu-id="b3831-119">**X 切忌** 提供抽象，除非通过开发几个使用抽象的具体实现和 API 来测试它们。</span><span class="sxs-lookup"><span data-stu-id="b3831-119">**X DO NOT** provide abstractions unless they are tested by developing several concrete implementations and APIs consuming the abstractions.</span></span>  
  
 <span data-ttu-id="b3831-120">**✓ 务必** 在设计抽象时，仔细选择使用抽象类还是接口。</span><span class="sxs-lookup"><span data-stu-id="b3831-120">**✓ DO** choose carefully between an abstract class and an interface when designing an abstraction.</span></span>  
  
 <span data-ttu-id="b3831-121">**✓ 考虑** 为抽象的具体实现提供参考测试。</span><span class="sxs-lookup"><span data-stu-id="b3831-121">**✓ CONSIDER** providing reference tests for concrete implementations of abstractions.</span></span> <span data-ttu-id="b3831-122">此类测试应允许用户测试其实现是否正确实现了协定。</span><span class="sxs-lookup"><span data-stu-id="b3831-122">Such tests should allow users to test whether their implementations correctly implement the contract.</span></span>  
  
 <span data-ttu-id="b3831-123">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="b3831-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b3831-124">*通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*</span><span class="sxs-lookup"><span data-stu-id="b3831-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3831-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3831-125">See also</span></span>

- [<span data-ttu-id="b3831-126">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="b3831-126">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="b3831-127">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="b3831-127">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
