---
title: 嵌套类型
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
author: KrzysztofCwalina
ms.openlocfilehash: 22c14d05105154ff642cb8a44eda8e7c5d0575e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559536"
---
# <a name="nested-types"></a><span data-ttu-id="8e7b8-102">嵌套类型</span><span class="sxs-lookup"><span data-stu-id="8e7b8-102">Nested Types</span></span>
<span data-ttu-id="8e7b8-103">嵌套的类型是另一种类型，称为封闭类型的范围内定义的类型。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-103">A nested type is a type defined within the scope of another type, which is called the enclosing type.</span></span> <span data-ttu-id="8e7b8-104">嵌套的类型有权访问其封闭类型的所有成员。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-104">A nested type has access to all members of its enclosing type.</span></span> <span data-ttu-id="8e7b8-105">例如，它有权访问在封闭类型和受保护的封闭类型的所有祖先中定义的字段定义的私有字段。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-105">For example, it has access to private fields defined in the enclosing type and to protected fields defined in all ascendants of the enclosing type.</span></span>  
  
 <span data-ttu-id="8e7b8-106">一般情况下，应谨慎使用嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-106">In general, nested types should be used sparingly.</span></span> <span data-ttu-id="8e7b8-107">其原因有若干：</span><span class="sxs-lookup"><span data-stu-id="8e7b8-107">There are several reasons for this.</span></span> <span data-ttu-id="8e7b8-108">一些开发人员不完全熟悉这一概念。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-108">Some developers are not fully familiar with the concept.</span></span> <span data-ttu-id="8e7b8-109">这些开发人员，例如，可能与声明的嵌套类型的变量的语法问题。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-109">These developers might, for example, have problems with the syntax of declaring variables of nested types.</span></span> <span data-ttu-id="8e7b8-110">嵌套的类型与其封闭类型时，还非常紧密耦合，并且这种情况下为通用类型不适合。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-110">Nested types are also very tightly coupled with their enclosing types, and as such are not suited to be general-purpose types.</span></span>  
  
 <span data-ttu-id="8e7b8-111">嵌套的类型是最适合用于建模的其封闭类型的实现详细信息。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-111">Nested types are best suited for modeling implementation details of their enclosing types.</span></span> <span data-ttu-id="8e7b8-112">最终用户应几乎不需要声明嵌套类型的变量和几乎永远不能进行显式实例化嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-112">The end user should rarely have to declare variables of a nested type and almost never should have to explicitly instantiate nested types.</span></span> <span data-ttu-id="8e7b8-113">例如，集合的枚举器可以为该集合的嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-113">For example, the enumerator of a collection can be a nested type of that collection.</span></span> <span data-ttu-id="8e7b8-114">枚举器通常通过其封闭类型实例化，因为许多语言都支持 foreach 语句，枚举器变量几乎不需要最终用户声明。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-114">Enumerators are usually instantiated by their enclosing type, and because many languages support the foreach statement, enumerator variables rarely have to be declared by the end user.</span></span>  
  
 <span data-ttu-id="8e7b8-115">**✓ 务必** 使用嵌套的类型，从而使成员可访问性语义都需要的嵌套的类型和其外部类型之间的关系时。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-115">**✓ DO** use nested types when the relationship between the nested type and its outer type is such that member-accessibility semantics are desirable.</span></span>  
  
 <span data-ttu-id="8e7b8-116">**X 切忌** 使用公共嵌套的类型作为自己的逻辑分组构造; 为此使用命名空间。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-116">**X DO NOT** use public nested types as a logical grouping construct; use namespaces for this.</span></span>  
  
 <span data-ttu-id="8e7b8-117">**X 避免** 公共公开嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-117">**X AVOID** publicly exposed nested types.</span></span> <span data-ttu-id="8e7b8-118">唯一的例外是嵌套类型的变量需要声明仅在极少数情况下，如生成子类或其他高级自定义方案。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-118">The only exception to this is if variables of the nested type need to be declared only in rare scenarios such as subclassing or other advanced customization scenarios.</span></span>  
  
 <span data-ttu-id="8e7b8-119">**X 切忌** 使用嵌套的类型，如果类型为可能包含类型的外部引用。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-119">**X DO NOT** use nested types if the type is likely to be referenced outside of the containing type.</span></span>  
  
 <span data-ttu-id="8e7b8-120">例如，传递给方法的类上定义的枚举应未定义为类中的嵌套类型。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-120">For example, an enum passed to a method defined on a class should not be defined as a nested type in the class.</span></span>  
  
 <span data-ttu-id="8e7b8-121">**X 切忌** 使用嵌套的类型，如果他们需要通过客户端代码来实例化。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-121">**X DO NOT** use nested types if they need to be instantiated by client code.</span></span>  <span data-ttu-id="8e7b8-122">如果类型具有公共构造函数，它可能不应进行嵌套。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-122">If a type has a public constructor, it should probably not be nested.</span></span>  
  
 <span data-ttu-id="8e7b8-123">如果可以实例化一个类型，这种方法似乎以指示该类型具有上其自己的框架中的位置 （你可以创建它，使用它，和销毁而完全不必使用外部类型），并因此不应嵌套。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-123">If a type can be instantiated, that seems to indicate the type has a place in the framework on its own (you can create it, work with it, and destroy it without ever using the outer type), and thus should not be nested.</span></span> <span data-ttu-id="8e7b8-124">不应内部类型广泛重用之外没有任何关系的外部类型都为外部类型。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-124">Inner types should not be widely reused outside of the outer type without any relationship whatsoever to the outer type.</span></span>  
  
 <span data-ttu-id="8e7b8-125">**X 切忌** 定义为接口成员的嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-125">**X DO NOT** define a nested type as a member of an interface.</span></span> <span data-ttu-id="8e7b8-126">许多语言不支持此类构造。</span><span class="sxs-lookup"><span data-stu-id="8e7b8-126">Many languages do not support such a construct.</span></span>  
  
 <span data-ttu-id="8e7b8-127">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="8e7b8-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="8e7b8-128">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="8e7b8-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e7b8-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e7b8-129">See also</span></span>

- [<span data-ttu-id="8e7b8-130">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="8e7b8-130">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="8e7b8-131">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="8e7b8-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
