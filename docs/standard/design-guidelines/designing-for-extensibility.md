---
title: 扩展性设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68419fe293dd25936aa3c1e3def10bbe8852e175
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571379"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="856e2-102">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="856e2-102">Designing for Extensibility</span></span>
<span data-ttu-id="856e2-103">一个重要方面的设计一个框架时，必须确保已仔细考虑框架的扩展性。</span><span class="sxs-lookup"><span data-stu-id="856e2-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="856e2-104">这需要了解的成本和收益与各种扩展性机制。</span><span class="sxs-lookup"><span data-stu-id="856e2-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="856e2-105">本章可帮助你确定哪个扩展性机制 — 子类化、 事件、 虚拟成员、 回调和等等 — 能够最好地满足您的框架的要求。</span><span class="sxs-lookup"><span data-stu-id="856e2-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="856e2-106">有多种方法，以便扩展性框架中。</span><span class="sxs-lookup"><span data-stu-id="856e2-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="856e2-107">它们到非常强大但昂贵范围内较不强大但成本较低。</span><span class="sxs-lookup"><span data-stu-id="856e2-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="856e2-108">对于任何给定的可扩展性要求，你应该选择满足要求的成本最低扩展性机制。</span><span class="sxs-lookup"><span data-stu-id="856e2-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="856e2-109">请记住，通常可以添加更大的扩展性更高版本，但您可以永远不会收回它而不会引入重大更改。</span><span class="sxs-lookup"><span data-stu-id="856e2-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="856e2-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="856e2-110">In This Section</span></span>  
 [<span data-ttu-id="856e2-111">未密封类</span><span class="sxs-lookup"><span data-stu-id="856e2-111">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [<span data-ttu-id="856e2-112">受保护的成员</span><span class="sxs-lookup"><span data-stu-id="856e2-112">Protected Members</span></span>](../../../docs/standard/design-guidelines/protected-members.md)  
 [<span data-ttu-id="856e2-113">事件和回调</span><span class="sxs-lookup"><span data-stu-id="856e2-113">Events and Callbacks</span></span>](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [<span data-ttu-id="856e2-114">虚拟成员</span><span class="sxs-lookup"><span data-stu-id="856e2-114">Virtual Members</span></span>](../../../docs/standard/design-guidelines/virtual-members.md)  
 [<span data-ttu-id="856e2-115">抽象（抽象类型和接口）</span><span class="sxs-lookup"><span data-stu-id="856e2-115">Abstractions (Abstract Types and Interfaces)</span></span>](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="856e2-116">用于实现抽象的基类</span><span class="sxs-lookup"><span data-stu-id="856e2-116">Base Classes for Implementing Abstractions</span></span>](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="856e2-117">密封</span><span class="sxs-lookup"><span data-stu-id="856e2-117">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)  
 <span data-ttu-id="856e2-118">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="856e2-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="856e2-119">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="856e2-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="856e2-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="856e2-120">See Also</span></span>  
 [<span data-ttu-id="856e2-121">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="856e2-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
