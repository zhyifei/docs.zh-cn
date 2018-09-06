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
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "44036020"
---
# <a name="type-design-guidelines"></a><span data-ttu-id="bd098-102">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="bd098-102">Type Design Guidelines</span></span>
<span data-ttu-id="bd098-103">从 CLR 角度来看，有只有两个类别的类型 — 引用类型和值类型，但为了框架设计有关的讨论，我们可以将类型划分为多个逻辑组，每个都有其自己特定的设计规则。</span><span class="sxs-lookup"><span data-stu-id="bd098-103">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>  
  
 <span data-ttu-id="bd098-104">类是引用类型的一般情况。</span><span class="sxs-lookup"><span data-stu-id="bd098-104">Classes are the general case of reference types.</span></span> <span data-ttu-id="bd098-105">它们构成了在框架的大多数类型的大容量。</span><span class="sxs-lookup"><span data-stu-id="bd098-105">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="bd098-106">类欠其受欢迎程度设置面向对象的所支持的功能的丰富和常规适用性。</span><span class="sxs-lookup"><span data-stu-id="bd098-106">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="bd098-107">基类和抽象类是与扩展相关的特殊逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="bd098-107">Base classes and abstract classes are special logical groups related to extensibility.</span></span>  
  
 <span data-ttu-id="bd098-108">接口是由引用类型和值类型可以实现的类型。</span><span class="sxs-lookup"><span data-stu-id="bd098-108">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="bd098-109">因此，它们可以充当多态的引用类型和值类型的层次结构的根。</span><span class="sxs-lookup"><span data-stu-id="bd098-109">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="bd098-110">此外，可以使用接口来模拟多个继承，不由 CLR 本机支持。</span><span class="sxs-lookup"><span data-stu-id="bd098-110">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>  
  
 <span data-ttu-id="bd098-111">结构是值类型的一般情况下，且应将其保留对于小型的简单类型，类似于语言基元。</span><span class="sxs-lookup"><span data-stu-id="bd098-111">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>  
  
 <span data-ttu-id="bd098-112">枚举都是用来定义的值，如一周、 控制台颜色和等等的天的短集的值类型的一种特殊情况。</span><span class="sxs-lookup"><span data-stu-id="bd098-112">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>  
  
 <span data-ttu-id="bd098-113">静态类是用于容器的静态成员的类型。</span><span class="sxs-lookup"><span data-stu-id="bd098-113">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="bd098-114">它们通常用于提供其他操作的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="bd098-114">They are commonly used to provide shortcuts to other operations.</span></span>  
  
 <span data-ttu-id="bd098-115">委托、 异常、 属性、 数组和集合是适用于特定用途的引用类型的所有特殊情况下，在本书中其他位置讨论了为其设计和使用情况的指导原则。</span><span class="sxs-lookup"><span data-stu-id="bd098-115">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>  
  
 <span data-ttu-id="bd098-116">**✓ DO** 确保每个类型定义完善的一组相关成员，而不仅仅是随机的不相关的功能集合。</span><span class="sxs-lookup"><span data-stu-id="bd098-116">**✓ DO** ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bd098-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="bd098-117">In This Section</span></span>  
 [<span data-ttu-id="bd098-118">在类和结构之间选择</span><span class="sxs-lookup"><span data-stu-id="bd098-118">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [<span data-ttu-id="bd098-119">抽象类设计</span><span class="sxs-lookup"><span data-stu-id="bd098-119">Abstract Class Design</span></span>](../../../docs/standard/design-guidelines/abstract-class.md)  
 [<span data-ttu-id="bd098-120">静态类设计</span><span class="sxs-lookup"><span data-stu-id="bd098-120">Static Class Design</span></span>](../../../docs/standard/design-guidelines/static-class.md)  
 [<span data-ttu-id="bd098-121">接口设计</span><span class="sxs-lookup"><span data-stu-id="bd098-121">Interface Design</span></span>](../../../docs/standard/design-guidelines/interface.md)  
 [<span data-ttu-id="bd098-122">结构设计</span><span class="sxs-lookup"><span data-stu-id="bd098-122">Struct Design</span></span>](../../../docs/standard/design-guidelines/struct.md)  
 [<span data-ttu-id="bd098-123">枚举设计</span><span class="sxs-lookup"><span data-stu-id="bd098-123">Enum Design</span></span>](../../../docs/standard/design-guidelines/enum.md)  
 [<span data-ttu-id="bd098-124">嵌套类型</span><span class="sxs-lookup"><span data-stu-id="bd098-124">Nested Types</span></span>](../../../docs/standard/design-guidelines/nested-types.md)  
 <span data-ttu-id="bd098-125">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="bd098-125">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="bd098-126">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="bd098-126">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd098-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd098-127">See also</span></span>

- [<span data-ttu-id="bd098-128">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="bd098-128">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
