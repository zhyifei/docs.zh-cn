---
title: 用于实现抽象的基类
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f326ee895251678c7a23ea84a11e83951edf2cc
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45519466"
---
# <a name="base-classes-for-implementing-abstractions"></a><span data-ttu-id="a6c5b-102">用于实现抽象的基类</span><span class="sxs-lookup"><span data-stu-id="a6c5b-102">Base Classes for Implementing Abstractions</span></span>
<span data-ttu-id="a6c5b-103">严格地说，一个类成为基类时另一个类派生。</span><span class="sxs-lookup"><span data-stu-id="a6c5b-103">Strictly speaking, a class becomes a base class when another class is derived from it.</span></span> <span data-ttu-id="a6c5b-104">但是，对于本部分中，基类是主要用于提供常见抽象或重复使用某些其他类的默认实现但继承的类。</span><span class="sxs-lookup"><span data-stu-id="a6c5b-104">For the purpose of this section, however, a base class is a class designed mainly to provide a common abstraction or for other classes to reuse some default implementation though inheritance.</span></span> <span data-ttu-id="a6c5b-105">基类，这些类通常位于继承层次结构，层次结构的根处的抽象和底部的多个自定义实现之间的中间。</span><span class="sxs-lookup"><span data-stu-id="a6c5b-105">Base classes usually sit in the middle of inheritance hierarchies, between an abstraction at the root of a hierarchy and several custom implementations at the bottom.</span></span>  
  
 <span data-ttu-id="a6c5b-106">它们用于实现抽象处理为实现帮助器。</span><span class="sxs-lookup"><span data-stu-id="a6c5b-106">They serve as implementation helpers for implementing abstractions.</span></span> <span data-ttu-id="a6c5b-107">例如，一项的有序集合的框架的抽象是<xref:System.Collections.Generic.IList%601>接口。</span><span class="sxs-lookup"><span data-stu-id="a6c5b-107">For example, one of the Framework’s abstractions for ordered collections of items is the <xref:System.Collections.Generic.IList%601> interface.</span></span> <span data-ttu-id="a6c5b-108">实现<xref:System.Collections.Generic.IList%601>并非易事，并因此框架提供多个基类，例如<xref:System.Collections.ObjectModel.Collection%601>和<xref:System.Collections.ObjectModel.KeyedCollection%602>，它用于实现自定义集合作为帮助程序。</span><span class="sxs-lookup"><span data-stu-id="a6c5b-108">Implementing <xref:System.Collections.Generic.IList%601> is not trivial, and therefore the Framework provides several base classes, such as <xref:System.Collections.ObjectModel.Collection%601> and <xref:System.Collections.ObjectModel.KeyedCollection%602>, which serve as helpers for implementing custom collections.</span></span>  
  
 <span data-ttu-id="a6c5b-109">基本类并通常不适合作为抽象本身，因为他们往往会包含太多实现。</span><span class="sxs-lookup"><span data-stu-id="a6c5b-109">Base classes are usually not suited to serve as abstractions by themselves, because they tend to contain too much implementation.</span></span> <span data-ttu-id="a6c5b-110">例如，`Collection<T>`基类提供了很多实现这一事实，它实现非泛型相关的`IList`接口 （若要将与非泛型集合更好地集成），它是一系列项存储在中的一个字段的内存。</span><span class="sxs-lookup"><span data-stu-id="a6c5b-110">For example, the `Collection<T>` base class contains lots of implementation related to the fact that it implements the nongeneric `IList` interface (to integrate better with nongeneric collections) and to the fact that it is a collection of items stored in memory in one of its fields.</span></span>  
  
 <span data-ttu-id="a6c5b-111">如前面所述，基类，这些类可以提供宝贵帮助的用户需要实现的抽象，但在同一时间可重大的责任。</span><span class="sxs-lookup"><span data-stu-id="a6c5b-111">As previously discussed, base classes can provide invaluable help for users who need to implement abstractions, but at the same time they can be a significant liability.</span></span> <span data-ttu-id="a6c5b-112">他们添加外围和增加的继承层次结构的深度和使框架，因此在概念上变得复杂。</span><span class="sxs-lookup"><span data-stu-id="a6c5b-112">They add surface area and increase the depth of inheritance hierarchies and so conceptually complicate the framework.</span></span> <span data-ttu-id="a6c5b-113">因此，仅当它们带来巨大价值的框架用户，则应使用基类，这些类。</span><span class="sxs-lookup"><span data-stu-id="a6c5b-113">Therefore, base classes should be used only if they provide significant value to the users of the framework.</span></span> <span data-ttu-id="a6c5b-114">如果它们仅对 framework，在其中写委派而不是继承的内部实现从基类则强烈建议的实施者提供的值，它们应避免使用。</span><span class="sxs-lookup"><span data-stu-id="a6c5b-114">They should be avoided if they provide value only to the implementers of the framework, in which case delegation to an internal implementation instead of inheritance from a base class should be strongly considered.</span></span>  
  
 <span data-ttu-id="a6c5b-115">**✓ CONSIDER** 进行基本类抽象，即使它们不包含任何抽象成员。</span><span class="sxs-lookup"><span data-stu-id="a6c5b-115">**✓ CONSIDER** making base classes abstract even if they don’t contain any abstract members.</span></span> <span data-ttu-id="a6c5b-116">这清楚地传达给用户的类仅用于从继承。</span><span class="sxs-lookup"><span data-stu-id="a6c5b-116">This clearly communicates to the users that the class is designed solely to be inherited from.</span></span>  
  
 <span data-ttu-id="a6c5b-117">**✓ CONSIDER** 置于单独的命名空间从主线方案类型的基类，这些类。</span><span class="sxs-lookup"><span data-stu-id="a6c5b-117">**✓ CONSIDER** placing base classes in a separate namespace from the mainline scenario types.</span></span> <span data-ttu-id="a6c5b-118">根据定义，基类，这些类适用于高级的扩展性方案，因此都不会用到的大部分用户。</span><span class="sxs-lookup"><span data-stu-id="a6c5b-118">By definition, base classes are intended for advanced extensibility scenarios and therefore are not interesting to the majority of users.</span></span>  
  
 <span data-ttu-id="a6c5b-119">**X AVOID** 命名为"基本"后缀的基类，如果类旨在用于在公共 Api 中使用。</span><span class="sxs-lookup"><span data-stu-id="a6c5b-119">**X AVOID** naming base classes with a "Base" suffix if the class is intended for use in public APIs.</span></span>  
  
 <span data-ttu-id="a6c5b-120">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="a6c5b-120">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a6c5b-121">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="a6c5b-121">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6c5b-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6c5b-122">See also</span></span>

- [<span data-ttu-id="a6c5b-123">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="a6c5b-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="a6c5b-124">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="a6c5b-124">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
