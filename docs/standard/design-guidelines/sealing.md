---
title: 密封
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
author: KrzysztofCwalina
ms.openlocfilehash: fd1abdb4ff6f4850eea96bcfc3afbfe00a4ae56a
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127688"
---
# <a name="sealing"></a><span data-ttu-id="f2522-102">密封</span><span class="sxs-lookup"><span data-stu-id="f2522-102">Sealing</span></span>
<span data-ttu-id="f2522-103">面向对象的框架的一个特性是开发人员可以以框架设计者未曾预料到的方式扩展和定制它们。</span><span class="sxs-lookup"><span data-stu-id="f2522-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="f2522-104">这是可扩展设计的强大和危险之处。</span><span class="sxs-lookup"><span data-stu-id="f2522-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="f2522-105">因此，在设计框架时，必须根据需要仔细设计可扩展性并在不安全的情况下对其进行限制。</span><span class="sxs-lookup"><span data-stu-id="f2522-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>  
  
 <span data-ttu-id="f2522-106">防止可扩展性的强大机制是密封。</span><span class="sxs-lookup"><span data-stu-id="f2522-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="f2522-107">可以密封类或单个成员。</span><span class="sxs-lookup"><span data-stu-id="f2522-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="f2522-108">密封类会阻止用户继承该类。</span><span class="sxs-lookup"><span data-stu-id="f2522-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="f2522-109">密封成员可阻止用户重写特定成员。</span><span class="sxs-lookup"><span data-stu-id="f2522-109">Sealing a member prevents users from overriding a particular member.</span></span>  
  
 <span data-ttu-id="f2522-110">**X 切忌** 在没有充分理由的情况下密封类。</span><span class="sxs-lookup"><span data-stu-id="f2522-110">**X DO NOT** seal classes without having a good reason to do so.</span></span>  
  
 <span data-ttu-id="f2522-111">因为无法预料到可扩展性场景而密封一个类并不是一个充分的理由。</span><span class="sxs-lookup"><span data-stu-id="f2522-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="f2522-112">框架用户喜欢因各种非显而易见的原因继承类，比如添加一些便利的成员。</span><span class="sxs-lookup"><span data-stu-id="f2522-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="f2522-113">有关用户希望从类型进行继承的非显而易见的原因的示例，请参阅[未密封类](../../../docs/standard/design-guidelines/unsealed-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="f2522-113">See [Unsealed Classes](../../../docs/standard/design-guidelines/unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>  
  
 <span data-ttu-id="f2522-114">对类进行密封的充足理由包括：</span><span class="sxs-lookup"><span data-stu-id="f2522-114">Good reasons for sealing a class include the following:</span></span>  
  
-   <span data-ttu-id="f2522-115">该类是一个静态类。</span><span class="sxs-lookup"><span data-stu-id="f2522-115">The class is a static class.</span></span> <span data-ttu-id="f2522-116">请参阅[静态类设计](../../../docs/standard/design-guidelines/static-class.md)。</span><span class="sxs-lookup"><span data-stu-id="f2522-116">See [Static Class Design](../../../docs/standard/design-guidelines/static-class.md).</span></span>  
  
-   <span data-ttu-id="f2522-117">该类在继承的受保护成员中存储了对安全敏感的机密。</span><span class="sxs-lookup"><span data-stu-id="f2522-117">The class stores security-sensitive secrets in inherited protected members.</span></span>  
  
-   <span data-ttu-id="f2522-118">该类继承了许多虚拟成员，单独密封它们的成本将超过使该类未密封的益处。</span><span class="sxs-lookup"><span data-stu-id="f2522-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>  
  
-   <span data-ttu-id="f2522-119">该类是一个需要极快速运行时查找的属性。</span><span class="sxs-lookup"><span data-stu-id="f2522-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="f2522-120">密封属性的性能水平略高于未密封的属性。</span><span class="sxs-lookup"><span data-stu-id="f2522-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="f2522-121">请参阅[属性](../../../docs/standard/design-guidelines/attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="f2522-121">See [Attributes](../../../docs/standard/design-guidelines/attributes.md).</span></span>  
  
 <span data-ttu-id="f2522-122">**X 切忌** 在密封类型上声明受保护成员或虚拟成员。</span><span class="sxs-lookup"><span data-stu-id="f2522-122">**X DO NOT** declare protected or virtual members on sealed types.</span></span>  
  
 <span data-ttu-id="f2522-123">根据定义，不能从密封类型继承。</span><span class="sxs-lookup"><span data-stu-id="f2522-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="f2522-124">这意味着无法调用密封类型上的受保护成员，并且无法重写密封类型上的虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="f2522-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>  
  
 <span data-ttu-id="f2522-125">**✓ 考虑** 密封重写的成员。</span><span class="sxs-lookup"><span data-stu-id="f2522-125">**✓ CONSIDER** sealing members that you override.</span></span>  
  
 <span data-ttu-id="f2522-126">引入虚拟成员可能导致的问题（在[虚拟成员](../../../docs/standard/design-guidelines/virtual-members.md)中讨论）也适用于重写，尽管程度较低。</span><span class="sxs-lookup"><span data-stu-id="f2522-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](../../../docs/standard/design-guidelines/virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="f2522-127">密封重写可以防止这些继承层次结构中的问题。</span><span class="sxs-lookup"><span data-stu-id="f2522-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="f2522-128">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="f2522-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f2522-129">*通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*</span><span class="sxs-lookup"><span data-stu-id="f2522-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2522-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2522-130">See also</span></span>

- [<span data-ttu-id="f2522-131">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="f2522-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="f2522-132">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="f2522-132">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [<span data-ttu-id="f2522-133">未密封类</span><span class="sxs-lookup"><span data-stu-id="f2522-133">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)
