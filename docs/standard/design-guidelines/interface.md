---
title: 接口设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
author: KrzysztofCwalina
ms.openlocfilehash: 1f982aa37f92b7270725574d949989ca120297d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026362"
---
# <a name="interface-design"></a><span data-ttu-id="e6e5b-102">接口设计</span><span class="sxs-lookup"><span data-stu-id="e6e5b-102">Interface Design</span></span>
<span data-ttu-id="e6e5b-103">虽然大多数 API 最好使用类和结构进行建模，但有些情况下接口更合适或是唯一的选择。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-103">Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more appropriate or are the only option.</span></span>  
  
 <span data-ttu-id="e6e5b-104">CLR 不支持多重继承（即，CLR 类不能从多个基类继承），但它允许类型除了继承基类之外还实现一个或多个接口。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-104">The CLR does not support multiple inheritance (i.e., CLR classes cannot inherit from more than one base class), but it does allow types to implement one or more interfaces in addition to inheriting from a base class.</span></span> <span data-ttu-id="e6e5b-105">因此，通常使用接口来实现多重继承的效果。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-105">Therefore, interfaces are often used to achieve the effect of multiple inheritance.</span></span> <span data-ttu-id="e6e5b-106">例如，<xref:System.IDisposable>是一个接口，允许类型支持可释放性，而不依赖于他们想要参与的任何其他继承层次结构。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-106">For example, <xref:System.IDisposable> is an interface that allows types to support disposability independent of any other inheritance hierarchy in which they want to participate.</span></span>  
  
 <span data-ttu-id="e6e5b-107">适合定义接口的另一种情况是创建一个可以由多种类型支持的公共接口，包括一些值类型。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-107">The other situation in which defining an interface is appropriate is in creating a common interface that can be supported by several types, including some value types.</span></span> <span data-ttu-id="e6e5b-108">值类型不能继承 <xref:System.ValueType> 之外的其他类型，但是它们可以实现接口，因此使用接口是提供公共基类型的唯一选择。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-108">Value types cannot inherit from types other than <xref:System.ValueType>, but they can implement interfaces, so using an interface is the only option in order to provide a common base type.</span></span>  
  
 <span data-ttu-id="e6e5b-109">**✓ 务必**定义一个接口，如果需要某些通用 API 受到包含值类型的一组类型的支持。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-109">**✓ DO** define an interface if you need some common API to be supported by a set of types that includes value types.</span></span>  
  
 <span data-ttu-id="e6e5b-110">**✓ 考虑**定义一个接口，如果需要在已继承自其他类型的类型上支持其功能。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-110">**✓ CONSIDER** defining an interface if you need to support its functionality on types that already inherit from some other type.</span></span>  
  
 <span data-ttu-id="e6e5b-111">**X 避免**使用标记接口（不包含任何成员的接口）。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-111">**X AVOID** using marker interfaces (interfaces with no members).</span></span>  
  
 <span data-ttu-id="e6e5b-112">如果需要将类标记为具有特定特征（标记），通常使用自定义特性而不是接口。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-112">If you need to mark a class as having a specific characteristic (marker), in general, use a custom attribute rather than an interface.</span></span>  
  
 <span data-ttu-id="e6e5b-113">**✓ 务必**至少提供一种作为接口的实现的类型。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-113">**✓ DO** provide at least one type that is an implementation of an interface.</span></span>  
  
 <span data-ttu-id="e6e5b-114">此做法有助于验证接口的设计。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-114">Doing this helps to validate the design of the interface.</span></span> <span data-ttu-id="e6e5b-115">例如，<xref:System.Collections.Generic.List%601> 是 <xref:System.Collections.Generic.IList%601> 接口的实现。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-115">For example, <xref:System.Collections.Generic.List%601> is an implementation of the <xref:System.Collections.Generic.IList%601> interface.</span></span>  
  
 <span data-ttu-id="e6e5b-116">**✓ 务必**为你定义的每个接口提供至少一个使用它的 API（将接口作为类型化为接口的参数或属性的方法）。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-116">**✓ DO** provide at least one API that consumes each interface you define (a method taking the interface as a parameter or a property typed as the interface).</span></span>  
  
 <span data-ttu-id="e6e5b-117">此做法有助于验证接口设计。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-117">Doing this helps to validate the interface design.</span></span> <span data-ttu-id="e6e5b-118">例如，<xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> 使用 <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> 接口。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-118">For example, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consumes the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interface.</span></span>  
  
 <span data-ttu-id="e6e5b-119">**X 切忌**将成员添加到之前发布的接口中。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-119">**X DO NOT** add members to an interface that has previously shipped.</span></span>  
  
 <span data-ttu-id="e6e5b-120">这样做会破坏接口的实现。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-120">Doing so would break implementations of the interface.</span></span> <span data-ttu-id="e6e5b-121">应创建一个新接口以避免版本控制问题。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-121">You should create a new interface in order to avoid versioning problems.</span></span>  
  
 <span data-ttu-id="e6e5b-122">除了这些指南中描述的情况之外，一般情况下，应该在设计托管代码的可重用库时选择类而不是接口。</span><span class="sxs-lookup"><span data-stu-id="e6e5b-122">Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces in designing managed code reusable libraries.</span></span>  
  
 <span data-ttu-id="e6e5b-123">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="e6e5b-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e6e5b-124">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="e6e5b-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6e5b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6e5b-125">See also</span></span>

- [<span data-ttu-id="e6e5b-126">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="e6e5b-126">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="e6e5b-127">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="e6e5b-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
