---
title: 嵌套类型
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 681e11ef3994e4c38dee9f99c6c82cc4b103a0db
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="nested-types"></a><span data-ttu-id="df547-102">嵌套类型</span><span class="sxs-lookup"><span data-stu-id="df547-102">Nested Types</span></span>
<span data-ttu-id="df547-103">嵌套的类型是在另一个类型，这称为封闭类型的范围内定义的类型。</span><span class="sxs-lookup"><span data-stu-id="df547-103">A nested type is a type defined within the scope of another type, which is called the enclosing type.</span></span> <span data-ttu-id="df547-104">嵌套的类型有权访问其封闭类型的所有成员。</span><span class="sxs-lookup"><span data-stu-id="df547-104">A nested type has access to all members of its enclosing type.</span></span> <span data-ttu-id="df547-105">例如，它有权访问在封闭类型和保护的封闭类型的所有祖先中定义的字段定义的私有字段。</span><span class="sxs-lookup"><span data-stu-id="df547-105">For example, it has access to private fields defined in the enclosing type and to protected fields defined in all ascendants of the enclosing type.</span></span>  
  
 <span data-ttu-id="df547-106">一般情况下，应尽量少使用嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="df547-106">In general, nested types should be used sparingly.</span></span> <span data-ttu-id="df547-107">其原因有若干：</span><span class="sxs-lookup"><span data-stu-id="df547-107">There are several reasons for this.</span></span> <span data-ttu-id="df547-108">一些开发人员不完全熟悉这一概念。</span><span class="sxs-lookup"><span data-stu-id="df547-108">Some developers are not fully familiar with the concept.</span></span> <span data-ttu-id="df547-109">这些开发人员例如，可能会有问题的声明的嵌套类型的变量的语法。</span><span class="sxs-lookup"><span data-stu-id="df547-109">These developers might, for example, have problems with the syntax of declaring variables of nested types.</span></span> <span data-ttu-id="df547-110">嵌套的类型与其封闭类型，也非常紧密耦合，并且这种情况下为通用类型不适合。</span><span class="sxs-lookup"><span data-stu-id="df547-110">Nested types are also very tightly coupled with their enclosing types, and as such are not suited to be general-purpose types.</span></span>  
  
 <span data-ttu-id="df547-111">嵌套的类型很适合于建模其封闭类型的实现详细信息。</span><span class="sxs-lookup"><span data-stu-id="df547-111">Nested types are best suited for modeling implementation details of their enclosing types.</span></span> <span data-ttu-id="df547-112">最终用户应几乎不需要声明的嵌套类型的变量，并且几乎从未必须具有显式实例化嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="df547-112">The end user should rarely have to declare variables of a nested type and almost never should have to explicitly instantiate nested types.</span></span> <span data-ttu-id="df547-113">例如，集合的枚举器可以是该集合的嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="df547-113">For example, the enumerator of a collection can be a nested type of that collection.</span></span> <span data-ttu-id="df547-114">枚举器通常由其封闭类型实例化和枚举器变量许多语言都支持 foreach 语句，因为几乎无需最终用户声明。</span><span class="sxs-lookup"><span data-stu-id="df547-114">Enumerators are usually instantiated by their enclosing type, and because many languages support the foreach statement, enumerator variables rarely have to be declared by the end user.</span></span>  
  
 <span data-ttu-id="df547-115">**✓ 执行**使用嵌套的类型，从而使成员可访问性语义都需要的嵌套的类型和其外部类型之间的关系时。</span><span class="sxs-lookup"><span data-stu-id="df547-115">**✓ DO** use nested types when the relationship between the nested type and its outer type is such that member-accessibility semantics are desirable.</span></span>  
  
 <span data-ttu-id="df547-116">**X 不**使用公共嵌套的类型作为自己的逻辑分组构造; 为此使用命名空间。</span><span class="sxs-lookup"><span data-stu-id="df547-116">**X DO NOT** use public nested types as a logical grouping construct; use namespaces for this.</span></span>  
  
 <span data-ttu-id="df547-117">**请避免 x**公共公开嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="df547-117">**X AVOID** publicly exposed nested types.</span></span> <span data-ttu-id="df547-118">唯一的例外是如果需要仅在极少数情况下，例如生成子类或其他高级自定义应用场景中声明的嵌套类型的变量。</span><span class="sxs-lookup"><span data-stu-id="df547-118">The only exception to this is if variables of the nested type need to be declared only in rare scenarios such as subclassing or other advanced customization scenarios.</span></span>  
  
 <span data-ttu-id="df547-119">**X 不**使用嵌套的类型，如果类型为可能包含类型的外部引用。</span><span class="sxs-lookup"><span data-stu-id="df547-119">**X DO NOT** use nested types if the type is likely to be referenced outside of the containing type.</span></span>  
  
 <span data-ttu-id="df547-120">例如，不应为类中的嵌套类型定义枚举传递给在类上定义的方法。</span><span class="sxs-lookup"><span data-stu-id="df547-120">For example, an enum passed to a method defined on a class should not be defined as a nested type in the class.</span></span>  
  
 <span data-ttu-id="df547-121">**X 不**使用嵌套的类型，如果他们需要通过客户端代码来实例化。</span><span class="sxs-lookup"><span data-stu-id="df547-121">**X DO NOT** use nested types if they need to be instantiated by client code.</span></span>  <span data-ttu-id="df547-122">某个类型是否具有公共构造函数，它可能不应进行嵌套。</span><span class="sxs-lookup"><span data-stu-id="df547-122">If a type has a public constructor, it should probably not be nested.</span></span>  
  
 <span data-ttu-id="df547-123">如果可实例化类型，这看起来以指示该类型具有其自身上的框架中的一个位置 （你可以创建、 使用它，以及销毁而完全不必使用外部类型），并因此不应进行嵌套。</span><span class="sxs-lookup"><span data-stu-id="df547-123">If a type can be instantiated, that seems to indicate the type has a place in the framework on its own (you can create it, work with it, and destroy it without ever using the outer type), and thus should not be nested.</span></span> <span data-ttu-id="df547-124">在没有任何关系的外部类型之外，内部类型应不广泛重用承担到外部类型。</span><span class="sxs-lookup"><span data-stu-id="df547-124">Inner types should not be widely reused outside of the outer type without any relationship whatsoever to the outer type.</span></span>  
  
 <span data-ttu-id="df547-125">**X 不**定义为接口成员的嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="df547-125">**X DO NOT** define a nested type as a member of an interface.</span></span> <span data-ttu-id="df547-126">许多语言不支持这样的构造。</span><span class="sxs-lookup"><span data-stu-id="df547-126">Many languages do not support such a construct.</span></span>  
  
 <span data-ttu-id="df547-127">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="df547-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="df547-128">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="df547-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df547-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="df547-129">See Also</span></span>  
 [<span data-ttu-id="df547-130">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="df547-130">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="df547-131">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="df547-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
