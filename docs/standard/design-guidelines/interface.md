---
title: "接口设计"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: dc7185f9541952d528de38b627052239f5d8b4ae
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="interface-design"></a><span data-ttu-id="2a161-102">接口设计</span><span class="sxs-lookup"><span data-stu-id="2a161-102">Interface Design</span></span>
<span data-ttu-id="2a161-103">尽管大多数 Api 最佳使用类和结构进行建模，有一些情况下在其中更合适或接口的唯一选择。</span><span class="sxs-lookup"><span data-stu-id="2a161-103">Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more appropriate or are the only option.</span></span>  
  
 <span data-ttu-id="2a161-104">CLR 不支持多重继承 （即，CLR 类不能从多个基类继承），但它允许实现除了从基类继承的一个或多个接口的类型。</span><span class="sxs-lookup"><span data-stu-id="2a161-104">The CLR does not support multiple inheritance (i.e., CLR classes cannot inherit from more than one base class), but it does allow types to implement one or more interfaces in addition to inheriting from a base class.</span></span> <span data-ttu-id="2a161-105">因此，接口通常用于实现多重继承的效果。</span><span class="sxs-lookup"><span data-stu-id="2a161-105">Therefore, interfaces are often used to achieve the effect of multiple inheritance.</span></span> <span data-ttu-id="2a161-106">例如，<xref:System.IDisposable>是一个接口，用于类型来支持 disposability 独立于他们想要参与任何其他继承的层次结构。</span><span class="sxs-lookup"><span data-stu-id="2a161-106">For example, <xref:System.IDisposable> is an interface that allows types to support disposability independent of any other inheritance hierarchy in which they want to participate.</span></span>  
  
 <span data-ttu-id="2a161-107">其他接口中的定义是相应的情形是在创建了公共接口，可以支持几种类型，包括某些值类型。</span><span class="sxs-lookup"><span data-stu-id="2a161-107">The other situation in which defining an interface is appropriate is in creating a common interface that can be supported by several types, including some value types.</span></span> <span data-ttu-id="2a161-108">值类型不能从继承类型以外<xref:System.ValueType>，但它们可以实现接口，因此使用接口是为了提供通用的基类型的唯一选项。</span><span class="sxs-lookup"><span data-stu-id="2a161-108">Value types cannot inherit from types other than <xref:System.ValueType>, but they can implement interfaces, so using an interface is the only option in order to provide a common base type.</span></span>  
  
 <span data-ttu-id="2a161-109">**✓ 执行**定义一个接口，如果你需要一些常见的 API 来支持的一组包含值类型的类型。</span><span class="sxs-lookup"><span data-stu-id="2a161-109">**✓ DO** define an interface if you need some common API to be supported by a set of types that includes value types.</span></span>  
  
 <span data-ttu-id="2a161-110">**请考虑 ✓**定义的接口，如果你需要在已继承自其他类型的类型上支持其功能。</span><span class="sxs-lookup"><span data-stu-id="2a161-110">**✓ CONSIDER** defining an interface if you need to support its functionality on types that already inherit from some other type.</span></span>  
  
 <span data-ttu-id="2a161-111">**请避免 x**使用标记接口 （不包含任何成员的接口）。</span><span class="sxs-lookup"><span data-stu-id="2a161-111">**X AVOID** using marker interfaces (interfaces with no members).</span></span>  
  
 <span data-ttu-id="2a161-112">如果你需要将标记为具有特定特征 （标记） 的类，通常情况下，使用的自定义特性，而不是接口。</span><span class="sxs-lookup"><span data-stu-id="2a161-112">If you need to mark a class as having a specific characteristic (marker), in general, use a custom attribute rather than an interface.</span></span>  
  
 <span data-ttu-id="2a161-113">**✓ 执行**提供至少一种类型的接口的实现。</span><span class="sxs-lookup"><span data-stu-id="2a161-113">**✓ DO** provide at least one type that is an implementation of an interface.</span></span>  
  
 <span data-ttu-id="2a161-114">执行此可帮助验证接口的设计。</span><span class="sxs-lookup"><span data-stu-id="2a161-114">Doing this helps to validate the design of the interface.</span></span> <span data-ttu-id="2a161-115">例如，<xref:System.Collections.Generic.List%601>实现的<xref:System.Collections.Generic.IList%601>接口。</span><span class="sxs-lookup"><span data-stu-id="2a161-115">For example, <xref:System.Collections.Generic.List%601> is an implementation of the <xref:System.Collections.Generic.IList%601> interface.</span></span>  
  
 <span data-ttu-id="2a161-116">**✓ 执行**提供使用你定义的每个接口的至少一个 API （采用作为参数或属性的接口的方法类型化为接口）。</span><span class="sxs-lookup"><span data-stu-id="2a161-116">**✓ DO** provide at least one API that consumes each interface you define (a method taking the interface as a parameter or a property typed as the interface).</span></span>  
  
 <span data-ttu-id="2a161-117">执行此可帮助验证接口设计。</span><span class="sxs-lookup"><span data-stu-id="2a161-117">Doing this helps to validate the interface design.</span></span> <span data-ttu-id="2a161-118">例如，<xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType>使用<xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType>接口。</span><span class="sxs-lookup"><span data-stu-id="2a161-118">For example, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consumes the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interface.</span></span>  
  
 <span data-ttu-id="2a161-119">**X 不**将成员添加到具有以前发布的接口。</span><span class="sxs-lookup"><span data-stu-id="2a161-119">**X DO NOT** add members to an interface that has previously shipped.</span></span>  
  
 <span data-ttu-id="2a161-120">这样将会破坏接口的实现。</span><span class="sxs-lookup"><span data-stu-id="2a161-120">Doing so would break implementations of the interface.</span></span> <span data-ttu-id="2a161-121">为了避免版本控制问题，应创建一个新的接口。</span><span class="sxs-lookup"><span data-stu-id="2a161-121">You should create a new interface in order to avoid versioning problems.</span></span>  
  
 <span data-ttu-id="2a161-122">除了这些准则中所述的情况下，你应该一般情况下，选择类，而不是接口在设计托管的代码可重用库。</span><span class="sxs-lookup"><span data-stu-id="2a161-122">Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces in designing managed code reusable libraries.</span></span>  
  
 <span data-ttu-id="2a161-123">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="2a161-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2a161-124">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="2a161-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a161-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a161-125">See Also</span></span>  
 [<span data-ttu-id="2a161-126">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="2a161-126">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="2a161-127">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="2a161-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
