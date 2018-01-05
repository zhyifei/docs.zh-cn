---
title: "类型设计准则"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6b02abef0180b6de82e26837863849cce35c994f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="type-design-guidelines"></a><span data-ttu-id="aa84a-102">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="aa84a-102">Type Design Guidelines</span></span>
<span data-ttu-id="aa84a-103">从 CLR 角度来看，有只有两种类型的类别 — 引用类型和值类型，但为了 framework 设计有关的讨论，我们可以将类型划分为多个逻辑组，每个都有其自己的特定设计规则。</span><span class="sxs-lookup"><span data-stu-id="aa84a-103">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>  
  
 <span data-ttu-id="aa84a-104">类是引用类型的一般情况。</span><span class="sxs-lookup"><span data-stu-id="aa84a-104">Classes are the general case of reference types.</span></span> <span data-ttu-id="aa84a-105">它们构成了大量的大部分框架中的类型。</span><span class="sxs-lookup"><span data-stu-id="aa84a-105">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="aa84a-106">类到它们支持面向对象的功能的设置的丰富和它们的常规适用性欠其受欢迎程度。</span><span class="sxs-lookup"><span data-stu-id="aa84a-106">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="aa84a-107">基类和抽象类是与扩展相关的特殊逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="aa84a-107">Base classes and abstract classes are special logical groups related to extensibility.</span></span>  
  
 <span data-ttu-id="aa84a-108">接口是由引用类型和值类型可以实现的类型。</span><span class="sxs-lookup"><span data-stu-id="aa84a-108">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="aa84a-109">因此，它们可以作为引用类型和值类型的多态层次结构的根。</span><span class="sxs-lookup"><span data-stu-id="aa84a-109">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="aa84a-110">此外，接口可以用于模拟本机不支持 CLR 的多个继承。</span><span class="sxs-lookup"><span data-stu-id="aa84a-110">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>  
  
 <span data-ttu-id="aa84a-111">结构是值类型的一般情况下，且应保留对于小型，简单类型，类似于语言基元。</span><span class="sxs-lookup"><span data-stu-id="aa84a-111">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>  
  
 <span data-ttu-id="aa84a-112">枚举是用来定义的值，如一周的控制台颜色，和等的天的短集的值类型的特殊情况。</span><span class="sxs-lookup"><span data-stu-id="aa84a-112">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>  
  
 <span data-ttu-id="aa84a-113">静态类是用于适用于静态成员的容器的类型。</span><span class="sxs-lookup"><span data-stu-id="aa84a-113">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="aa84a-114">它们通常用于提供其他操作的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="aa84a-114">They are commonly used to provide shortcuts to other operations.</span></span>  
  
 <span data-ttu-id="aa84a-115">委托、 异常、 属性、 数组和集合是适用于特定用途的引用类型的所有特殊情况和本书中别处讨论的设计和使用情况的准则。</span><span class="sxs-lookup"><span data-stu-id="aa84a-115">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>  
  
 <span data-ttu-id="aa84a-116">**✓ 执行**确保每个类型定义完善的一组相关成员，而不仅仅是随机的不相关的功能集合。</span><span class="sxs-lookup"><span data-stu-id="aa84a-116">**✓ DO** ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aa84a-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="aa84a-117">In This Section</span></span>  
 [<span data-ttu-id="aa84a-118">在类和结构之间选择</span><span class="sxs-lookup"><span data-stu-id="aa84a-118">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [<span data-ttu-id="aa84a-119">抽象类设计</span><span class="sxs-lookup"><span data-stu-id="aa84a-119">Abstract Class Design</span></span>](../../../docs/standard/design-guidelines/abstract-class.md)  
 [<span data-ttu-id="aa84a-120">静态类设计</span><span class="sxs-lookup"><span data-stu-id="aa84a-120">Static Class Design</span></span>](../../../docs/standard/design-guidelines/static-class.md)  
 [<span data-ttu-id="aa84a-121">接口设计</span><span class="sxs-lookup"><span data-stu-id="aa84a-121">Interface Design</span></span>](../../../docs/standard/design-guidelines/interface.md)  
 [<span data-ttu-id="aa84a-122">结构设计</span><span class="sxs-lookup"><span data-stu-id="aa84a-122">Struct Design</span></span>](../../../docs/standard/design-guidelines/struct.md)  
 [<span data-ttu-id="aa84a-123">枚举设计</span><span class="sxs-lookup"><span data-stu-id="aa84a-123">Enum Design</span></span>](../../../docs/standard/design-guidelines/enum.md)  
 [<span data-ttu-id="aa84a-124">嵌套类型</span><span class="sxs-lookup"><span data-stu-id="aa84a-124">Nested Types</span></span>](../../../docs/standard/design-guidelines/nested-types.md)  
 <span data-ttu-id="aa84a-125">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="aa84a-125">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="aa84a-126">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="aa84a-126">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa84a-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa84a-127">See Also</span></span>  
 [<span data-ttu-id="aa84a-128">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="aa84a-128">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
