---
title: 扩展性设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: cd5db2d1e299df1b3d0f706ebc507e6855b72505
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709460"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="9da46-102">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="9da46-102">Designing for Extensibility</span></span>
<span data-ttu-id="9da46-103">设计一个框架的一个重要方面是确保仔细考虑框架的可扩展性。</span><span class="sxs-lookup"><span data-stu-id="9da46-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="9da46-104">这要求你了解与各种可扩展性机制相关的成本和收益。</span><span class="sxs-lookup"><span data-stu-id="9da46-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="9da46-105">本章可帮助你确定哪些可扩展性机制（子类、事件、虚拟成员、回调等）可以最好地满足框架的要求。</span><span class="sxs-lookup"><span data-stu-id="9da46-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="9da46-106">有许多方法可以在框架中实现可扩展性。</span><span class="sxs-lookup"><span data-stu-id="9da46-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="9da46-107">有些方法功能不强但成本较低，有些方法功能强大但成本较高。</span><span class="sxs-lookup"><span data-stu-id="9da46-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="9da46-108">对于任何给定的可扩展性要求，应该选择满足要求的成本最低的可扩展性机制。</span><span class="sxs-lookup"><span data-stu-id="9da46-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="9da46-109">请记住，通常可以在以后添加更多的可扩展性，但不能在不引入中断性变更的情况下将其删除。</span><span class="sxs-lookup"><span data-stu-id="9da46-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9da46-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="9da46-110">In This Section</span></span>  
 [<span data-ttu-id="9da46-111">未密封类</span><span class="sxs-lookup"><span data-stu-id="9da46-111">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [<span data-ttu-id="9da46-112">受保护的成员</span><span class="sxs-lookup"><span data-stu-id="9da46-112">Protected Members</span></span>](../../../docs/standard/design-guidelines/protected-members.md)  
 [<span data-ttu-id="9da46-113">事件和回调</span><span class="sxs-lookup"><span data-stu-id="9da46-113">Events and Callbacks</span></span>](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [<span data-ttu-id="9da46-114">虚拟成员</span><span class="sxs-lookup"><span data-stu-id="9da46-114">Virtual Members</span></span>](../../../docs/standard/design-guidelines/virtual-members.md)  
 [<span data-ttu-id="9da46-115">抽象（抽象类型和接口）</span><span class="sxs-lookup"><span data-stu-id="9da46-115">Abstractions (Abstract Types and Interfaces)</span></span>](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="9da46-116">用于实现抽象的基类</span><span class="sxs-lookup"><span data-stu-id="9da46-116">Base Classes for Implementing Abstractions</span></span>](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="9da46-117">密封</span><span class="sxs-lookup"><span data-stu-id="9da46-117">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)  
 <span data-ttu-id="9da46-118">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="9da46-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9da46-119">\*在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。</span><span class="sxs-lookup"><span data-stu-id="9da46-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9da46-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9da46-120">See also</span></span>

- [<span data-ttu-id="9da46-121">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="9da46-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
