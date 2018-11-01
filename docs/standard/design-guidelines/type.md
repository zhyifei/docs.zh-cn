---
title: 类型设计准则
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7fb9964d0e542c0937c55ae65bd88b3f7149fa8
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44187934"
---
# <a name="type-design-guidelines"></a><span data-ttu-id="54321-102">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="54321-102">Type Design Guidelines</span></span>
<span data-ttu-id="54321-103">就 CLR 而言，它仅支持两种类型 — 引用类型和值类型。但出于探讨框架设计的目的，我们将类型划分为多个逻辑组，每种都有其特定的设计规则。</span><span class="sxs-lookup"><span data-stu-id="54321-103">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>  
  
 <span data-ttu-id="54321-104">类是使用最普遍的引用类型。</span><span class="sxs-lookup"><span data-stu-id="54321-104">Classes are the general case of reference types.</span></span> <span data-ttu-id="54321-105">多数框架中的大部分引用类型都是类。</span><span class="sxs-lookup"><span data-stu-id="54321-105">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="54321-106">类的广泛应用主要得益于其支持丰富的面向对象功能，以及普适性。</span><span class="sxs-lookup"><span data-stu-id="54321-106">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="54321-107">基类和抽象类是具备扩展性的特殊逻辑组。</span><span class="sxs-lookup"><span data-stu-id="54321-107">Base classes and abstract classes are special logical groups related to extensibility.</span></span>  
  
 <span data-ttu-id="54321-108">接口也是一种类型。</span><span class="sxs-lookup"><span data-stu-id="54321-108">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="54321-109">接口可以被引用类型和值类型实现，因此可以充当这两种类型多态层次结构的根。</span><span class="sxs-lookup"><span data-stu-id="54321-109">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="54321-110">此外，接口也可用于模拟多个继承，而 CLR 本身并不支持该功能。</span><span class="sxs-lookup"><span data-stu-id="54321-110">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>  
  
 <span data-ttu-id="54321-111">结构是常见的值类型。结构应当用来定义类似于语言基元的小型简单类型。</span><span class="sxs-lookup"><span data-stu-id="54321-111">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>  
  
 <span data-ttu-id="54321-112">枚举是一种特殊的值类型，它适用于定义一组数量有限的值，例如一周七天的名称、控制台颜色等。</span><span class="sxs-lookup"><span data-stu-id="54321-112">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>  
  
 <span data-ttu-id="54321-113">静态类的作用是为静态成员提供容器。</span><span class="sxs-lookup"><span data-stu-id="54321-113">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="54321-114">它们通常用来为其他操作提供快捷方式。</span><span class="sxs-lookup"><span data-stu-id="54321-114">They are commonly used to provide shortcuts to other operations.</span></span>  
  
 <span data-ttu-id="54321-115">委托、异常、属性、数组和集合是适用于特定用途的特殊引用类型。关于这些类型的设计准则与使用情况将在本书其他章节中进行讨论。</span><span class="sxs-lookup"><span data-stu-id="54321-115">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>  
  
 <span data-ttu-id="54321-116">**✓ DO**确保每个类型中的成员相互关联，而不仅仅是将不相关的功能集合在一起。</span><span class="sxs-lookup"><span data-stu-id="54321-116">**✓ DO** ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="54321-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="54321-117">In This Section</span></span>  
 [<span data-ttu-id="54321-118">在类和结构之间选择</span><span class="sxs-lookup"><span data-stu-id="54321-118">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [<span data-ttu-id="54321-119">抽象类设计</span><span class="sxs-lookup"><span data-stu-id="54321-119">Abstract Class Design</span></span>](../../../docs/standard/design-guidelines/abstract-class.md)  
 [<span data-ttu-id="54321-120">静态类设计</span><span class="sxs-lookup"><span data-stu-id="54321-120">Static Class Design</span></span>](../../../docs/standard/design-guidelines/static-class.md)  
 [<span data-ttu-id="54321-121">接口设计</span><span class="sxs-lookup"><span data-stu-id="54321-121">Interface Design</span></span>](../../../docs/standard/design-guidelines/interface.md)  
 [<span data-ttu-id="54321-122">结构设计</span><span class="sxs-lookup"><span data-stu-id="54321-122">Struct Design</span></span>](../../../docs/standard/design-guidelines/struct.md)  
 [<span data-ttu-id="54321-123">枚举设计</span><span class="sxs-lookup"><span data-stu-id="54321-123">Enum Design</span></span>](../../../docs/standard/design-guidelines/enum.md)  
 [<span data-ttu-id="54321-124">嵌套类型</span><span class="sxs-lookup"><span data-stu-id="54321-124">Nested Types</span></span>](../../../docs/standard/design-guidelines/nested-types.md)  
 <span data-ttu-id="54321-125">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="54321-125">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="54321-126">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="54321-126">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54321-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="54321-127">See also</span></span>

- [<span data-ttu-id="54321-128">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="54321-128">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
