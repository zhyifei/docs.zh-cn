---
title: 用于实现抽象的基类
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
ms.openlocfilehash: b22923338f8488b6f7684e565f62d9afc16e6aa0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741782"
---
# <a name="base-classes-for-implementing-abstractions"></a><span data-ttu-id="3d1e8-102">用于实现抽象的基类</span><span class="sxs-lookup"><span data-stu-id="3d1e8-102">Base Classes for Implementing Abstractions</span></span>
<span data-ttu-id="3d1e8-103">严格地说，当一个类派生出另一个类时，它就成了一个基类。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-103">Strictly speaking, a class becomes a base class when another class is derived from it.</span></span> <span data-ttu-id="3d1e8-104">但是，在本部分中，基类是一个主要用于提供公共抽象的类，或者是供其他类通过继承重用某些默认实现的类。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-104">For the purpose of this section, however, a base class is a class designed mainly to provide a common abstraction or for other classes to reuse some default implementation though inheritance.</span></span> <span data-ttu-id="3d1e8-105">基类通常位于继承层次结构的中间位置，位于根部的层次结构抽象和末端的一些自定义实现之间。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-105">Base classes usually sit in the middle of inheritance hierarchies, between an abstraction at the root of a hierarchy and several custom implementations at the bottom.</span></span>

 <span data-ttu-id="3d1e8-106">它们可以为实现抽象提供帮助。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-106">They serve as implementation helpers for implementing abstractions.</span></span> <span data-ttu-id="3d1e8-107">例如，用于项的有序集合的某个框架抽象是 <xref:System.Collections.Generic.IList%601> 接口。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-107">For example, one of the Framework’s abstractions for ordered collections of items is the <xref:System.Collections.Generic.IList%601> interface.</span></span> <span data-ttu-id="3d1e8-108">实现 <xref:System.Collections.Generic.IList%601> 并不简单，因此框架提供了多个基类，如 <xref:System.Collections.ObjectModel.Collection%601> 和 <xref:System.Collections.ObjectModel.KeyedCollection%602>，它们用作实现自定义集合的帮助程序。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-108">Implementing <xref:System.Collections.Generic.IList%601> is not trivial, and therefore the Framework provides several base classes, such as <xref:System.Collections.ObjectModel.Collection%601> and <xref:System.Collections.ObjectModel.KeyedCollection%602>, which serve as helpers for implementing custom collections.</span></span>

 <span data-ttu-id="3d1e8-109">基类通常不适合作为抽象本身，因为它们往往包含太多的实现。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-109">Base classes are usually not suited to serve as abstractions by themselves, because they tend to contain too much implementation.</span></span> <span data-ttu-id="3d1e8-110">例如，`Collection<T>` 基类包含许多与实现非泛型 `IList` 接口（以便更好地集成非泛型集合）相关的实现，以及它是存储在其一个字段的内存中的项的集合。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-110">For example, the `Collection<T>` base class contains lots of implementation related to the fact that it implements the nongeneric `IList` interface (to integrate better with nongeneric collections) and to the fact that it is a collection of items stored in memory in one of its fields.</span></span>

 <span data-ttu-id="3d1e8-111">如前所述，基类可以为需要实现抽象的用户提供宝贵的帮助，但同时它们可能是一个重大的不利因素。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-111">As previously discussed, base classes can provide invaluable help for users who need to implement abstractions, but at the same time they can be a significant liability.</span></span> <span data-ttu-id="3d1e8-112">它们增加了继承层次结构的广度和深度，因此在概念上使框架更加复杂。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-112">They add surface area and increase the depth of inheritance hierarchies and so conceptually complicate the framework.</span></span> <span data-ttu-id="3d1e8-113">因此，只有在为框架用户提供巨大价值的时候才应使用基类。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-113">Therefore, base classes should be used only if they provide significant value to the users of the framework.</span></span> <span data-ttu-id="3d1e8-114">如果它们仅对框架的实现者有用，则应该避免使用它们，在这种情况下，应该考虑委托到内部实现而不是从基类继承。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-114">They should be avoided if they provide value only to the implementers of the framework, in which case delegation to an internal implementation instead of inheritance from a base class should be strongly considered.</span></span>

 <span data-ttu-id="3d1e8-115">✔️考虑使基类抽象，即使它们不包含任何抽象成员也是如此。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-115">✔️ CONSIDER making base classes abstract even if they don’t contain any abstract members.</span></span> <span data-ttu-id="3d1e8-116">这会清楚地告知用户该类根据设计只能用于继承。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-116">This clearly communicates to the users that the class is designed solely to be inherited from.</span></span>

 <span data-ttu-id="3d1e8-117">✔️考虑将基类置于不同于主线方案类型的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-117">✔️ CONSIDER placing base classes in a separate namespace from the mainline scenario types.</span></span> <span data-ttu-id="3d1e8-118">根据定义，基类用于高级可扩展性场景，因此对大多数用户来说并没有意义。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-118">By definition, base classes are intended for advanced extensibility scenarios and therefore are not interesting to the majority of users.</span></span>

 <span data-ttu-id="3d1e8-119">如果类用于公共 Api，则 ❌ 避免使用 "Base" 后缀命名基类。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-119">❌ AVOID naming base classes with a "Base" suffix if the class is intended for use in public APIs.</span></span>

 <span data-ttu-id="3d1e8-120">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="3d1e8-120">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="3d1e8-121">\*在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。</span><span class="sxs-lookup"><span data-stu-id="3d1e8-121">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="3d1e8-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d1e8-122">See also</span></span>

- [<span data-ttu-id="3d1e8-123">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="3d1e8-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="3d1e8-124">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="3d1e8-124">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
