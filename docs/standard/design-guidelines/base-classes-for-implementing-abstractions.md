---
title: 用于实现抽象的基类
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
author: KrzysztofCwalina
ms.openlocfilehash: 411596f342930c9387dc6523d25805bddad18687
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148662"
---
# <a name="base-classes-for-implementing-abstractions"></a><span data-ttu-id="33f85-102">用于实现抽象的基类</span><span class="sxs-lookup"><span data-stu-id="33f85-102">Base Classes for Implementing Abstractions</span></span>
<span data-ttu-id="33f85-103">严格地说，当一个类派生出另一个类时，它就成了一个基类。</span><span class="sxs-lookup"><span data-stu-id="33f85-103">Strictly speaking, a class becomes a base class when another class is derived from it.</span></span> <span data-ttu-id="33f85-104">但是，在本部分中，基类是一个主要用于提供公共抽象的类，或者是供其他类通过继承重用某些默认实现的类。</span><span class="sxs-lookup"><span data-stu-id="33f85-104">For the purpose of this section, however, a base class is a class designed mainly to provide a common abstraction or for other classes to reuse some default implementation though inheritance.</span></span> <span data-ttu-id="33f85-105">基类通常位于继承层次结构的中间位置，位于根部的层次结构抽象和末端的一些自定义实现之间。</span><span class="sxs-lookup"><span data-stu-id="33f85-105">Base classes usually sit in the middle of inheritance hierarchies, between an abstraction at the root of a hierarchy and several custom implementations at the bottom.</span></span>  
  
 <span data-ttu-id="33f85-106">它们可以为实现抽象提供帮助。</span><span class="sxs-lookup"><span data-stu-id="33f85-106">They serve as implementation helpers for implementing abstractions.</span></span> <span data-ttu-id="33f85-107">例如，框架中有序项集合的抽象之一是 <xref:System.Collections.Generic.IList%601> 接口。</span><span class="sxs-lookup"><span data-stu-id="33f85-107">For example, one of the Framework’s abstractions for ordered collections of items is the <xref:System.Collections.Generic.IList%601> interface.</span></span> <span data-ttu-id="33f85-108">实现 <xref:System.Collections.Generic.IList%601> 并不简单，因此框架提供了几个基类，例如 <xref:System.Collections.ObjectModel.Collection%601> 和 <xref:System.Collections.ObjectModel.KeyedCollection%602>，来为实现自定义集合提供帮助。</span><span class="sxs-lookup"><span data-stu-id="33f85-108">Implementing <xref:System.Collections.Generic.IList%601> is not trivial, and therefore the Framework provides several base classes, such as <xref:System.Collections.ObjectModel.Collection%601> and <xref:System.Collections.ObjectModel.KeyedCollection%602>, which serve as helpers for implementing custom collections.</span></span>  
  
 <span data-ttu-id="33f85-109">基类通常不适合作为抽象本身，因为它们往往包含太多的实现。</span><span class="sxs-lookup"><span data-stu-id="33f85-109">Base classes are usually not suited to serve as abstractions by themselves, because they tend to contain too much implementation.</span></span> <span data-ttu-id="33f85-110">例如，`Collection<T>` 基类包含许多实现，这些实现与一些实际情况有关，即它实现了非泛型的 `IList` 接口（目的是更好地与非泛型集合集成），并且它是存储在某个字段的内存中的项的集合。</span><span class="sxs-lookup"><span data-stu-id="33f85-110">For example, the `Collection<T>` base class contains lots of implementation related to the fact that it implements the nongeneric `IList` interface (to integrate better with nongeneric collections) and to the fact that it is a collection of items stored in memory in one of its fields.</span></span>  
  
 <span data-ttu-id="33f85-111">如前所述，基类可以为需要实现抽象的用户提供宝贵的帮助，但同时它们可能是一个重大的不利因素。</span><span class="sxs-lookup"><span data-stu-id="33f85-111">As previously discussed, base classes can provide invaluable help for users who need to implement abstractions, but at the same time they can be a significant liability.</span></span> <span data-ttu-id="33f85-112">它们增加了继承层次结构的广度和深度，因此在概念上使框架更加复杂。</span><span class="sxs-lookup"><span data-stu-id="33f85-112">They add surface area and increase the depth of inheritance hierarchies and so conceptually complicate the framework.</span></span> <span data-ttu-id="33f85-113">因此，只有在为框架用户提供巨大价值的时候才应使用基类。</span><span class="sxs-lookup"><span data-stu-id="33f85-113">Therefore, base classes should be used only if they provide significant value to the users of the framework.</span></span> <span data-ttu-id="33f85-114">如果它们仅对框架的实现者有用，则应该避免使用它们，在这种情况下，应该考虑委托到内部实现而不是从基类继承。</span><span class="sxs-lookup"><span data-stu-id="33f85-114">They should be avoided if they provide value only to the implementers of the framework, in which case delegation to an internal implementation instead of inheritance from a base class should be strongly considered.</span></span>  
  
 <span data-ttu-id="33f85-115">**✓ CONSIDER** 进行基本类抽象，即使它们不包含任何抽象成员。</span><span class="sxs-lookup"><span data-stu-id="33f85-115">**✓ CONSIDER** making base classes abstract even if they don’t contain any abstract members.</span></span> <span data-ttu-id="33f85-116">这清楚地传达给用户的类仅用于从继承。</span><span class="sxs-lookup"><span data-stu-id="33f85-116">This clearly communicates to the users that the class is designed solely to be inherited from.</span></span>  
  
 <span data-ttu-id="33f85-117">**✓ CONSIDER** 置于单独的命名空间从主线方案类型的基类，这些类。</span><span class="sxs-lookup"><span data-stu-id="33f85-117">**✓ CONSIDER** placing base classes in a separate namespace from the mainline scenario types.</span></span> <span data-ttu-id="33f85-118">根据定义，基类，这些类适用于高级的扩展性方案，因此都不会用到的大部分用户。</span><span class="sxs-lookup"><span data-stu-id="33f85-118">By definition, base classes are intended for advanced extensibility scenarios and therefore are not interesting to the majority of users.</span></span>  
  
 <span data-ttu-id="33f85-119">**X AVOID** 命名为"基本"后缀的基类，如果类旨在用于在公共 Api 中使用。</span><span class="sxs-lookup"><span data-stu-id="33f85-119">**X AVOID** naming base classes with a "Base" suffix if the class is intended for use in public APIs.</span></span>  
  
 <span data-ttu-id="33f85-120">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="33f85-120">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="33f85-121">*通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*</span><span class="sxs-lookup"><span data-stu-id="33f85-121">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33f85-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="33f85-122">See also</span></span>

- [<span data-ttu-id="33f85-123">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="33f85-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="33f85-124">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="33f85-124">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
