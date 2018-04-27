---
title: 密封
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8a9ea7fd4f5df08631231db08ba7943a9c131012
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="sealing"></a><span data-ttu-id="77fb4-102">密封</span><span class="sxs-lookup"><span data-stu-id="77fb4-102">Sealing</span></span>
<span data-ttu-id="77fb4-103">面向对象的框架的功能之一是开发人员可以扩展和采用 framework designer 意料之外的方法来自定义它们。</span><span class="sxs-lookup"><span data-stu-id="77fb4-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="77fb4-104">这是设计的两个电源和可扩展的危险。</span><span class="sxs-lookup"><span data-stu-id="77fb4-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="77fb4-105">当您设计您的框架时，它是，因此，若要为扩展性仔细设计，当需要它时，以及限制扩展性危险时非常重要。</span><span class="sxs-lookup"><span data-stu-id="77fb4-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>  
  
 <span data-ttu-id="77fb4-106">密封可以防止扩展性的强大机制。</span><span class="sxs-lookup"><span data-stu-id="77fb4-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="77fb4-107">你可以密封的类或单个成员。</span><span class="sxs-lookup"><span data-stu-id="77fb4-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="77fb4-108">密封类，将阻止用户从类继承。</span><span class="sxs-lookup"><span data-stu-id="77fb4-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="77fb4-109">密封成员可防止用户重写特定成员。</span><span class="sxs-lookup"><span data-stu-id="77fb4-109">Sealing a member prevents users from overriding a particular member.</span></span>  
  
 <span data-ttu-id="77fb4-110">**X 不**密封类，而无需有充分的理由要这样做。</span><span class="sxs-lookup"><span data-stu-id="77fb4-110">**X DO NOT** seal classes without having a good reason to do so.</span></span>  
  
 <span data-ttu-id="77fb4-111">密封类，因为您不能将扩展性方案不充分的理由。</span><span class="sxs-lookup"><span data-stu-id="77fb4-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="77fb4-112">Framework 用户希望能够从类继承由于各种 nonobvious 原因，例如添加方便成员。</span><span class="sxs-lookup"><span data-stu-id="77fb4-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="77fb4-113">请参阅[未密封类](../../../docs/standard/design-guidelines/unsealed-classes.md)的 nonobvious 原因示例用户想要为从一种类型继承。</span><span class="sxs-lookup"><span data-stu-id="77fb4-113">See [Unsealed Classes](../../../docs/standard/design-guidelines/unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>  
  
 <span data-ttu-id="77fb4-114">良好的密封类的原因包括：</span><span class="sxs-lookup"><span data-stu-id="77fb4-114">Good reasons for sealing a class include the following:</span></span>  
  
-   <span data-ttu-id="77fb4-115">此类是静态的类。</span><span class="sxs-lookup"><span data-stu-id="77fb4-115">The class is a static class.</span></span> <span data-ttu-id="77fb4-116">请参阅[静态类设计](../../../docs/standard/design-guidelines/static-class.md)。</span><span class="sxs-lookup"><span data-stu-id="77fb4-116">See [Static Class Design](../../../docs/standard/design-guidelines/static-class.md).</span></span>  
  
-   <span data-ttu-id="77fb4-117">类继承的受保护成员中存储安全敏感机密。</span><span class="sxs-lookup"><span data-stu-id="77fb4-117">The class stores security-sensitive secrets in inherited protected members.</span></span>  
  
-   <span data-ttu-id="77fb4-118">类继承的多个虚成员，密封它们单独的成本将带来的好处将保留未密封的类。</span><span class="sxs-lookup"><span data-stu-id="77fb4-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>  
  
-   <span data-ttu-id="77fb4-119">类是需要非常快的运行时查找的属性。</span><span class="sxs-lookup"><span data-stu-id="77fb4-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="77fb4-120">密封的属性具有略高的性能级别，比未密封的。</span><span class="sxs-lookup"><span data-stu-id="77fb4-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="77fb4-121">请参阅[属性](../../../docs/standard/design-guidelines/attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="77fb4-121">See [Attributes](../../../docs/standard/design-guidelines/attributes.md).</span></span>  
  
 <span data-ttu-id="77fb4-122">**X 不**在密封类型中声明受保护或虚拟成员。</span><span class="sxs-lookup"><span data-stu-id="77fb4-122">**X DO NOT** declare protected or virtual members on sealed types.</span></span>  
  
 <span data-ttu-id="77fb4-123">根据定义，不能从继承密封的类型。</span><span class="sxs-lookup"><span data-stu-id="77fb4-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="77fb4-124">这意味着不能调用密封类型上的受保护的成员，并且密封类型上的虚拟方法不能重写。</span><span class="sxs-lookup"><span data-stu-id="77fb4-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>  
  
 <span data-ttu-id="77fb4-125">**请考虑 ✓**密封重写的成员。</span><span class="sxs-lookup"><span data-stu-id="77fb4-125">**✓ CONSIDER** sealing members that you override.</span></span>  
  
 <span data-ttu-id="77fb4-126">引入虚拟成员所产生的问题 (中所述[虚拟成员](../../../docs/standard/design-guidelines/virtual-members.md)) 应用到同样，重写应用尽管到略有一定程度上。</span><span class="sxs-lookup"><span data-stu-id="77fb4-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](../../../docs/standard/design-guidelines/virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="77fb4-127">密封替代可保护从继承层次结构中该点开始这些问题。</span><span class="sxs-lookup"><span data-stu-id="77fb4-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="77fb4-128">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="77fb4-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="77fb4-129">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="77fb4-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77fb4-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="77fb4-130">See Also</span></span>  
 [<span data-ttu-id="77fb4-131">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="77fb4-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="77fb4-132">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="77fb4-132">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="77fb4-133">未密封类</span><span class="sxs-lookup"><span data-stu-id="77fb4-133">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)
