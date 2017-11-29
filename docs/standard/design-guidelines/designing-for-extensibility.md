---
title: "扩展性设计"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dbee2fb24b9acf9bc2512b399e3a74e66720cc3c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="23d05-102">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="23d05-102">Designing for Extensibility</span></span>
<span data-ttu-id="23d05-103">一个重要方面的设计一个框架时，必须确保已仔细考虑框架的扩展性。</span><span class="sxs-lookup"><span data-stu-id="23d05-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="23d05-104">这需要了解的成本和收益与各种扩展性机制。</span><span class="sxs-lookup"><span data-stu-id="23d05-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="23d05-105">本章可帮助你确定哪个扩展性机制 — 子类化、 事件、 虚拟成员、 回调和等等 — 能够最好地满足您的框架的要求。</span><span class="sxs-lookup"><span data-stu-id="23d05-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="23d05-106">有多种方法，以便扩展性框架中。</span><span class="sxs-lookup"><span data-stu-id="23d05-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="23d05-107">它们到非常强大但昂贵范围内较不强大但成本较低。</span><span class="sxs-lookup"><span data-stu-id="23d05-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="23d05-108">对于任何给定的可扩展性要求，你应该选择满足要求的成本最低扩展性机制。</span><span class="sxs-lookup"><span data-stu-id="23d05-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="23d05-109">请记住，通常可以添加更大的扩展性更高版本，但您可以永远不会收回它而不会引入重大更改。</span><span class="sxs-lookup"><span data-stu-id="23d05-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23d05-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="23d05-110">In This Section</span></span>  
 [<span data-ttu-id="23d05-111">未密封的类</span><span class="sxs-lookup"><span data-stu-id="23d05-111">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [<span data-ttu-id="23d05-112">受保护的成员</span><span class="sxs-lookup"><span data-stu-id="23d05-112">Protected Members</span></span>](../../../docs/standard/design-guidelines/protected-members.md)  
 [<span data-ttu-id="23d05-113">事件和回调</span><span class="sxs-lookup"><span data-stu-id="23d05-113">Events and Callbacks</span></span>](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [<span data-ttu-id="23d05-114">虚拟成员</span><span class="sxs-lookup"><span data-stu-id="23d05-114">Virtual Members</span></span>](../../../docs/standard/design-guidelines/virtual-members.md)  
 [<span data-ttu-id="23d05-115">抽象 （抽象类型和接口）</span><span class="sxs-lookup"><span data-stu-id="23d05-115">Abstractions (Abstract Types and Interfaces)</span></span>](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="23d05-116">用于实现抽象基类</span><span class="sxs-lookup"><span data-stu-id="23d05-116">Base Classes for Implementing Abstractions</span></span>](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="23d05-117">密封</span><span class="sxs-lookup"><span data-stu-id="23d05-117">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)  
 <span data-ttu-id="23d05-118">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="23d05-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="23d05-119">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="23d05-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d05-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23d05-120">See Also</span></span>  
 [<span data-ttu-id="23d05-121">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="23d05-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
