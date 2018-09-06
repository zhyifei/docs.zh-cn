---
title: 接口设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c687d7622e82ee206b2201760818827398f8543b
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863715"
---
# <a name="interface-design"></a><span data-ttu-id="5592f-102">接口设计</span><span class="sxs-lookup"><span data-stu-id="5592f-102">Interface Design</span></span>
<span data-ttu-id="5592f-103">尽管大多数 Api 最适合使用类和结构进行建模，存在一些情况下在其中更合适或接口的唯一选择。</span><span class="sxs-lookup"><span data-stu-id="5592f-103">Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more appropriate or are the only option.</span></span>  
  
 <span data-ttu-id="5592f-104">CLR 不支持多重继承 （即，CLR 类不能从多个基类继承），但是它的确允许实现除了继承自基类的一个或多个接口的类型。</span><span class="sxs-lookup"><span data-stu-id="5592f-104">The CLR does not support multiple inheritance (i.e., CLR classes cannot inherit from more than one base class), but it does allow types to implement one or more interfaces in addition to inheriting from a base class.</span></span> <span data-ttu-id="5592f-105">因此，接口通常用于实现多个继承的效果。</span><span class="sxs-lookup"><span data-stu-id="5592f-105">Therefore, interfaces are often used to achieve the effect of multiple inheritance.</span></span> <span data-ttu-id="5592f-106">例如，<xref:System.IDisposable>是一个接口，允许支持 disposability 独立于他们想要参与任何其他继承的层次结构的类型。</span><span class="sxs-lookup"><span data-stu-id="5592f-106">For example, <xref:System.IDisposable> is an interface that allows types to support disposability independent of any other inheritance hierarchy in which they want to participate.</span></span>  
  
 <span data-ttu-id="5592f-107">在创建了公共接口，可以支持几种类型，包括某些值类型的接口是在其中定义相应的其他情况。</span><span class="sxs-lookup"><span data-stu-id="5592f-107">The other situation in which defining an interface is appropriate is in creating a common interface that can be supported by several types, including some value types.</span></span> <span data-ttu-id="5592f-108">值类型不能继承自类型而不<xref:System.ValueType>，但它们可以实现接口，因此使用的接口是为了提供一个公共基类型的唯一选项。</span><span class="sxs-lookup"><span data-stu-id="5592f-108">Value types cannot inherit from types other than <xref:System.ValueType>, but they can implement interfaces, so using an interface is the only option in order to provide a common base type.</span></span>  
  
 <span data-ttu-id="5592f-109">**✓ DO** 定义一个接口，如果你需要一些常见的 API 来支持的一组包含值类型的类型。</span><span class="sxs-lookup"><span data-stu-id="5592f-109">**✓ DO** define an interface if you need some common API to be supported by a set of types that includes value types.</span></span>  
  
 <span data-ttu-id="5592f-110">**✓ CONSIDER** 定义的接口，如果你需要在已继承自其他类型的类型上支持其功能。</span><span class="sxs-lookup"><span data-stu-id="5592f-110">**✓ CONSIDER** defining an interface if you need to support its functionality on types that already inherit from some other type.</span></span>  
  
 <span data-ttu-id="5592f-111">**X AVOID** 使用标记接口 （不包含任何成员的接口）。</span><span class="sxs-lookup"><span data-stu-id="5592f-111">**X AVOID** using marker interfaces (interfaces with no members).</span></span>  
  
 <span data-ttu-id="5592f-112">如果你需要将标记为具有特定特征 （标记） 的类，一般情况下，使用自定义特性而不是接口。</span><span class="sxs-lookup"><span data-stu-id="5592f-112">If you need to mark a class as having a specific characteristic (marker), in general, use a custom attribute rather than an interface.</span></span>  
  
 <span data-ttu-id="5592f-113">**✓ DO**提供至少一种类型的接口的实现。</span><span class="sxs-lookup"><span data-stu-id="5592f-113">**✓ DO** provide at least one type that is an implementation of an interface.</span></span>  
  
 <span data-ttu-id="5592f-114">这些措施可帮助验证接口的设计。</span><span class="sxs-lookup"><span data-stu-id="5592f-114">Doing this helps to validate the design of the interface.</span></span> <span data-ttu-id="5592f-115">例如，<xref:System.Collections.Generic.List%601>是一种实现的<xref:System.Collections.Generic.IList%601>接口。</span><span class="sxs-lookup"><span data-stu-id="5592f-115">For example, <xref:System.Collections.Generic.List%601> is an implementation of the <xref:System.Collections.Generic.IList%601> interface.</span></span>  
  
 <span data-ttu-id="5592f-116">**✓ DO**提供使用你定义的每个接口的至少一个 API （采用作为参数或属性的接口的方法类型化为接口）。</span><span class="sxs-lookup"><span data-stu-id="5592f-116">**✓ DO** provide at least one API that consumes each interface you define (a method taking the interface as a parameter or a property typed as the interface).</span></span>  
  
 <span data-ttu-id="5592f-117">这些措施可帮助验证界面设计。</span><span class="sxs-lookup"><span data-stu-id="5592f-117">Doing this helps to validate the interface design.</span></span> <span data-ttu-id="5592f-118">例如，<xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType>使用<xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType>接口。</span><span class="sxs-lookup"><span data-stu-id="5592f-118">For example, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consumes the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interface.</span></span>  
  
 <span data-ttu-id="5592f-119">**X DO NOT** 将成员添加到具有以前发布的接口。</span><span class="sxs-lookup"><span data-stu-id="5592f-119">**X DO NOT** add members to an interface that has previously shipped.</span></span>  
  
 <span data-ttu-id="5592f-120">执行此操作将会破坏接口的实现。</span><span class="sxs-lookup"><span data-stu-id="5592f-120">Doing so would break implementations of the interface.</span></span> <span data-ttu-id="5592f-121">为了避免版本控制问题，应创建新的接口。</span><span class="sxs-lookup"><span data-stu-id="5592f-121">You should create a new interface in order to avoid versioning problems.</span></span>  
  
 <span data-ttu-id="5592f-122">除了这些指南中所述的情况下，您应，一般情况下，选择类而不是接口在设计托管的代码的可重用库。</span><span class="sxs-lookup"><span data-stu-id="5592f-122">Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces in designing managed code reusable libraries.</span></span>  
  
 <span data-ttu-id="5592f-123">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="5592f-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5592f-124">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="5592f-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5592f-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="5592f-125">See also</span></span>

- [<span data-ttu-id="5592f-126">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="5592f-126">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="5592f-127">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="5592f-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
