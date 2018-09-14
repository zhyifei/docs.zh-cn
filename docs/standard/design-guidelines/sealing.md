---
title: 密封
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d8c445de44a69f6c0cb1eaefa0e59d682288318
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45515861"
---
# <a name="sealing"></a><span data-ttu-id="769d1-102">密封</span><span class="sxs-lookup"><span data-stu-id="769d1-102">Sealing</span></span>
<span data-ttu-id="769d1-103">面向对象的框架的功能之一是开发人员可以扩展和未预料到框架设计器的方式自定义它们。</span><span class="sxs-lookup"><span data-stu-id="769d1-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="769d1-104">这是设计的两个电源和可扩展的危险。</span><span class="sxs-lookup"><span data-stu-id="769d1-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="769d1-105">在设计您的框架，它，因此是非常重要时需要，仔细设计可扩展性以及限制可扩展性时这是很危险。</span><span class="sxs-lookup"><span data-stu-id="769d1-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>  
  
 <span data-ttu-id="769d1-106">密封可以防止可扩展性的强大机制。</span><span class="sxs-lookup"><span data-stu-id="769d1-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="769d1-107">密封类或单个成员。</span><span class="sxs-lookup"><span data-stu-id="769d1-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="769d1-108">密封类，可阻止用户从类继承。</span><span class="sxs-lookup"><span data-stu-id="769d1-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="769d1-109">密封成员可阻止用户重写特定成员。</span><span class="sxs-lookup"><span data-stu-id="769d1-109">Sealing a member prevents users from overriding a particular member.</span></span>  
  
 <span data-ttu-id="769d1-110">**X DO NOT** 密封类，而无需有充分的理由要这样做。</span><span class="sxs-lookup"><span data-stu-id="769d1-110">**X DO NOT** seal classes without having a good reason to do so.</span></span>  
  
 <span data-ttu-id="769d1-111">密封类，因为您不能将可扩展性方案不是一个充分的理由。</span><span class="sxs-lookup"><span data-stu-id="769d1-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="769d1-112">框架用户希望从类继承的各种 nonobvious 原因，例如，添加方便成员。</span><span class="sxs-lookup"><span data-stu-id="769d1-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="769d1-113">请参阅[未密封类](../../../docs/standard/design-guidelines/unsealed-classes.md)有关 nonobvious 原因的示例用户想要继承的类型。</span><span class="sxs-lookup"><span data-stu-id="769d1-113">See [Unsealed Classes](../../../docs/standard/design-guidelines/unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>  
  
 <span data-ttu-id="769d1-114">密封类充分的理由包括：</span><span class="sxs-lookup"><span data-stu-id="769d1-114">Good reasons for sealing a class include the following:</span></span>  
  
-   <span data-ttu-id="769d1-115">类是一个静态类。</span><span class="sxs-lookup"><span data-stu-id="769d1-115">The class is a static class.</span></span> <span data-ttu-id="769d1-116">请参阅[静态类设计](../../../docs/standard/design-guidelines/static-class.md)。</span><span class="sxs-lookup"><span data-stu-id="769d1-116">See [Static Class Design](../../../docs/standard/design-guidelines/static-class.md).</span></span>  
  
-   <span data-ttu-id="769d1-117">类继承的受保护成员中存储安全敏感机密。</span><span class="sxs-lookup"><span data-stu-id="769d1-117">The class stores security-sensitive secrets in inherited protected members.</span></span>  
  
-   <span data-ttu-id="769d1-118">类继承许多虚拟成员和密封它们单独的成本会超过保留的未密封的类的好处。</span><span class="sxs-lookup"><span data-stu-id="769d1-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>  
  
-   <span data-ttu-id="769d1-119">类是需要非常快的运行时查找的属性。</span><span class="sxs-lookup"><span data-stu-id="769d1-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="769d1-120">密封的属性具有比未密封的略高性能级别。</span><span class="sxs-lookup"><span data-stu-id="769d1-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="769d1-121">请参阅[属性](../../../docs/standard/design-guidelines/attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="769d1-121">See [Attributes](../../../docs/standard/design-guidelines/attributes.md).</span></span>  
  
 <span data-ttu-id="769d1-122">**X DO NOT** 在密封类型中声明受保护或虚拟成员。</span><span class="sxs-lookup"><span data-stu-id="769d1-122">**X DO NOT** declare protected or virtual members on sealed types.</span></span>  
  
 <span data-ttu-id="769d1-123">根据定义，不能从继承密封的类型。</span><span class="sxs-lookup"><span data-stu-id="769d1-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="769d1-124">这意味着不能调用密封类型上受保护的成员，并且不能重写密封类型上的虚方法。</span><span class="sxs-lookup"><span data-stu-id="769d1-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>  
  
 <span data-ttu-id="769d1-125">**✓ CONSIDER** 密封重写的成员。</span><span class="sxs-lookup"><span data-stu-id="769d1-125">**✓ CONSIDER** sealing members that you override.</span></span>  
  
 <span data-ttu-id="769d1-126">从引入虚拟成员可能导致问题，(中所述[虚拟成员](../../../docs/standard/design-guidelines/virtual-members.md)) 适用于替代，尽管到略有一定程度上。</span><span class="sxs-lookup"><span data-stu-id="769d1-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](../../../docs/standard/design-guidelines/virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="769d1-127">密封替代使您可以避免这些问题从继承层次结构中该点开始。</span><span class="sxs-lookup"><span data-stu-id="769d1-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="769d1-128">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="769d1-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="769d1-129">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="769d1-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="769d1-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="769d1-130">See also</span></span>

- [<span data-ttu-id="769d1-131">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="769d1-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="769d1-132">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="769d1-132">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [<span data-ttu-id="769d1-133">未密封类</span><span class="sxs-lookup"><span data-stu-id="769d1-133">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)
