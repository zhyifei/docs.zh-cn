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
author: KrzysztofCwalina
ms.openlocfilehash: 94900dee72230a1b9d099d78168acc508af62af7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026453"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="4cccd-102">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="4cccd-102">Designing for Extensibility</span></span>
<span data-ttu-id="4cccd-103">设计一个框架的一个重要方面是确保仔细考虑框架的可扩展性。</span><span class="sxs-lookup"><span data-stu-id="4cccd-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="4cccd-104">这要求你了解与各种可扩展性机制相关的成本和收益。</span><span class="sxs-lookup"><span data-stu-id="4cccd-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="4cccd-105">本章可帮助你确定哪些可扩展性机制（子类、事件、虚拟成员、回调等）可以最好地满足框架的要求。</span><span class="sxs-lookup"><span data-stu-id="4cccd-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="4cccd-106">有许多方法可以在框架中实现可扩展性。</span><span class="sxs-lookup"><span data-stu-id="4cccd-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="4cccd-107">有些方法功能不强但成本较低，有些方法功能强大但成本较高。</span><span class="sxs-lookup"><span data-stu-id="4cccd-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="4cccd-108">对于任何给定的可扩展性要求，应该选择满足要求的成本最低的可扩展性机制。</span><span class="sxs-lookup"><span data-stu-id="4cccd-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="4cccd-109">请记住，通常可以在以后添加更多的可扩展性，但不能在不引入中断性变更的情况下将其删除。</span><span class="sxs-lookup"><span data-stu-id="4cccd-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4cccd-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="4cccd-110">In This Section</span></span>  
 [<span data-ttu-id="4cccd-111">未密封类</span><span class="sxs-lookup"><span data-stu-id="4cccd-111">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [<span data-ttu-id="4cccd-112">受保护的成员</span><span class="sxs-lookup"><span data-stu-id="4cccd-112">Protected Members</span></span>](../../../docs/standard/design-guidelines/protected-members.md)  
 [<span data-ttu-id="4cccd-113">事件和回调</span><span class="sxs-lookup"><span data-stu-id="4cccd-113">Events and Callbacks</span></span>](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [<span data-ttu-id="4cccd-114">虚拟成员</span><span class="sxs-lookup"><span data-stu-id="4cccd-114">Virtual Members</span></span>](../../../docs/standard/design-guidelines/virtual-members.md)  
 [<span data-ttu-id="4cccd-115">抽象（抽象类型和接口）</span><span class="sxs-lookup"><span data-stu-id="4cccd-115">Abstractions (Abstract Types and Interfaces)</span></span>](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="4cccd-116">用于实现抽象的基类</span><span class="sxs-lookup"><span data-stu-id="4cccd-116">Base Classes for Implementing Abstractions</span></span>](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="4cccd-117">密封</span><span class="sxs-lookup"><span data-stu-id="4cccd-117">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)  
 <span data-ttu-id="4cccd-118">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="4cccd-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="4cccd-119">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="4cccd-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cccd-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cccd-120">See also</span></span>

- [<span data-ttu-id="4cccd-121">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="4cccd-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
