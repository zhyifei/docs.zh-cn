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
ms.openlocfilehash: 8c247ed7273687dbd61a6f19923b71e07e9ed960
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571503"
---
# <a name="base-classes-for-implementing-abstractions"></a><span data-ttu-id="c537d-102">用于实现抽象的基类</span><span class="sxs-lookup"><span data-stu-id="c537d-102">Base Classes for Implementing Abstractions</span></span>
<span data-ttu-id="c537d-103">严格地说，一个类成为基类，当另一个类派生自它时。</span><span class="sxs-lookup"><span data-stu-id="c537d-103">Strictly speaking, a class becomes a base class when another class is derived from it.</span></span> <span data-ttu-id="c537d-104">但是，对于本部分中，基类是主要用于提供公共抽象或重复使用某些其他类的默认实现但继承的类。</span><span class="sxs-lookup"><span data-stu-id="c537d-104">For the purpose of this section, however, a base class is a class designed mainly to provide a common abstraction or for other classes to reuse some default implementation though inheritance.</span></span> <span data-ttu-id="c537d-105">继承层次结构，在层次结构的根的抽象和一些自定义实现底部之间的中间通常位于基类，这些类。</span><span class="sxs-lookup"><span data-stu-id="c537d-105">Base classes usually sit in the middle of inheritance hierarchies, between an abstraction at the root of a hierarchy and several custom implementations at the bottom.</span></span>  
  
 <span data-ttu-id="c537d-106">它们作为实现帮助器用于实现抽象。</span><span class="sxs-lookup"><span data-stu-id="c537d-106">They serve as implementation helpers for implementing abstractions.</span></span> <span data-ttu-id="c537d-107">例如，其中一个有序集合的项的框架的抽象是<xref:System.Collections.Generic.IList%601>接口。</span><span class="sxs-lookup"><span data-stu-id="c537d-107">For example, one of the Framework’s abstractions for ordered collections of items is the <xref:System.Collections.Generic.IList%601> interface.</span></span> <span data-ttu-id="c537d-108">实现<xref:System.Collections.Generic.IList%601>非同小可，并因此框架提供多个基类，例如<xref:System.Collections.ObjectModel.Collection%601>和<xref:System.Collections.ObjectModel.KeyedCollection%602>，其用于实现自定义集合用作帮助器。</span><span class="sxs-lookup"><span data-stu-id="c537d-108">Implementing <xref:System.Collections.Generic.IList%601> is not trivial, and therefore the Framework provides several base classes, such as <xref:System.Collections.ObjectModel.Collection%601> and <xref:System.Collections.ObjectModel.KeyedCollection%602>, which serve as helpers for implementing custom collections.</span></span>  
  
 <span data-ttu-id="c537d-109">基类，这些类通常是不适合用作抽象本身，因为它们往往包含过多的实现。</span><span class="sxs-lookup"><span data-stu-id="c537d-109">Base classes are usually not suited to serve as abstractions by themselves, because they tend to contain too much implementation.</span></span> <span data-ttu-id="c537d-110">例如，`Collection<T>`基类包含大量与它实现非泛型的事实相关的实现`IList`接口 （以与非泛型集合更好地集成），并在事实项的集合存储在内存中其域中的一个。</span><span class="sxs-lookup"><span data-stu-id="c537d-110">For example, the `Collection<T>` base class contains lots of implementation related to the fact that it implements the nongeneric `IList` interface (to integrate better with nongeneric collections) and to the fact that it is a collection of items stored in memory in one of its fields.</span></span>  
  
 <span data-ttu-id="c537d-111">如前面所述，基类，这些类可以提供有用的帮助的用户需要实现抽象，但同时也可以是重大的责任。</span><span class="sxs-lookup"><span data-stu-id="c537d-111">As previously discussed, base classes can provide invaluable help for users who need to implement abstractions, but at the same time they can be a significant liability.</span></span> <span data-ttu-id="c537d-112">他们添加外围应用和增加继承层次结构的深度并因此从概念上讲在框架上变得复杂化。</span><span class="sxs-lookup"><span data-stu-id="c537d-112">They add surface area and increase the depth of inheritance hierarchies and so conceptually complicate the framework.</span></span> <span data-ttu-id="c537d-113">因此，仅当它们对框架的用户提供巨大价值，则应使用基类，这些类。</span><span class="sxs-lookup"><span data-stu-id="c537d-113">Therefore, base classes should be used only if they provide significant value to the users of the framework.</span></span> <span data-ttu-id="c537d-114">如果它们仅对的框架，在其中的内部实现，而不是继承自基类的区分大小委派应强考虑实施者提供值，它们应避免使用。</span><span class="sxs-lookup"><span data-stu-id="c537d-114">They should be avoided if they provide value only to the implementers of the framework, in which case delegation to an internal implementation instead of inheritance from a base class should be strongly considered.</span></span>  
  
 <span data-ttu-id="c537d-115">**✓ CONSIDER**进行基本类抽象，即使它们不包含任何抽象成员。</span><span class="sxs-lookup"><span data-stu-id="c537d-115">**✓ CONSIDER** making base classes abstract even if they don’t contain any abstract members.</span></span> <span data-ttu-id="c537d-116">它清楚地与用户建立通信，类旨在只是为了从继承。</span><span class="sxs-lookup"><span data-stu-id="c537d-116">This clearly communicates to the users that the class is designed solely to be inherited from.</span></span>  
  
 <span data-ttu-id="c537d-117">**✓ CONSIDER**置于单独的命名空间从主线方案类型的基类，这些类。</span><span class="sxs-lookup"><span data-stu-id="c537d-117">**✓ CONSIDER** placing base classes in a separate namespace from the mainline scenario types.</span></span> <span data-ttu-id="c537d-118">根据定义，基类，这些类旨在供高级的扩展性方案，因此不感兴趣的大多数用户。</span><span class="sxs-lookup"><span data-stu-id="c537d-118">By definition, base classes are intended for advanced extensibility scenarios and therefore are not interesting to the majority of users.</span></span>  
  
 <span data-ttu-id="c537d-119">**X AVOID**命名为"基本"后缀的基类，如果类旨在用于在公共 Api 中使用。</span><span class="sxs-lookup"><span data-stu-id="c537d-119">**X AVOID** naming base classes with a "Base" suffix if the class is intended for use in public APIs.</span></span>  
  
 <span data-ttu-id="c537d-120">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="c537d-120">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c537d-121">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="c537d-121">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c537d-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="c537d-122">See Also</span></span>  
 [<span data-ttu-id="c537d-123">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="c537d-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="c537d-124">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="c537d-124">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
