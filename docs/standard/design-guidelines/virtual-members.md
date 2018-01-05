---
title: "虚成员"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 692a5803ddb538de6dc5f061c18cc0b250d0f4ae
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="virtual-members"></a><span data-ttu-id="85e85-102">虚成员</span><span class="sxs-lookup"><span data-stu-id="85e85-102">Virtual Members</span></span>
<span data-ttu-id="85e85-103">虚拟成员可以被重写，因此更改行为的子类。</span><span class="sxs-lookup"><span data-stu-id="85e85-103">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="85e85-104">它们是非常类似于在它们提供的可扩展性方面的回调，但它们可以在执行性能和内存消耗方面获得更好。</span><span class="sxs-lookup"><span data-stu-id="85e85-104">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="85e85-105">此外，虚拟成员感觉需要创建一个特殊类型的现有类型 （专用） 的方案中更自然。</span><span class="sxs-lookup"><span data-stu-id="85e85-105">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>  
  
 <span data-ttu-id="85e85-106">虚拟成员执行性能优于回调和事件，但不是比非虚拟方法的更好地执行。</span><span class="sxs-lookup"><span data-stu-id="85e85-106">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>  
  
 <span data-ttu-id="85e85-107">虚拟成员的主要缺点是在编译时中的虚拟成员的行为可以仅能修改。</span><span class="sxs-lookup"><span data-stu-id="85e85-107">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="85e85-108">在运行时，可以对回调的行为进行修改。</span><span class="sxs-lookup"><span data-stu-id="85e85-108">The behavior of a callback can be modified at runtime.</span></span>  
  
 <span data-ttu-id="85e85-109">虚拟成员，例如回调 （和可能有多个回调），是用于设计、 测试和维护，因为对虚拟成员的任何调用可以在无法预测的方式中重写，并且能够执行任意代码的成本。</span><span class="sxs-lookup"><span data-stu-id="85e85-109">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="85e85-110">此外，更多工作量通常要求以明确定义的虚拟成员的协定，使设计和记录它们的成本较高。</span><span class="sxs-lookup"><span data-stu-id="85e85-110">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>  
  
 <span data-ttu-id="85e85-111">**X 不**虚成员，除非你有理由这样做，并且注意与设计、 测试和维护虚拟成员相关的所有成本。</span><span class="sxs-lookup"><span data-stu-id="85e85-111">**X DO NOT** make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>  
  
 <span data-ttu-id="85e85-112">虚拟成员是较少 forgiving 哪些可以对它们进行而不会破坏兼容性的更改。</span><span class="sxs-lookup"><span data-stu-id="85e85-112">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="85e85-113">此外，它们是低于非虚拟成员，主要是因为对虚拟成员的调用不内联。</span><span class="sxs-lookup"><span data-stu-id="85e85-113">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>  
  
 <span data-ttu-id="85e85-114">**请考虑 ✓**限制只将绝对必要的扩展性。</span><span class="sxs-lookup"><span data-stu-id="85e85-114">**✓ CONSIDER** limiting extensibility to only what is absolutely necessary.</span></span>  
  
 <span data-ttu-id="85e85-115">**✓ 执行**首选受保护的辅助功能的虚拟成员，而公共可访问性。</span><span class="sxs-lookup"><span data-stu-id="85e85-115">**✓ DO** prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="85e85-116">公共成员应通过调用受保护的虚拟成员提供扩展性 （如果需要）。</span><span class="sxs-lookup"><span data-stu-id="85e85-116">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>  
  
 <span data-ttu-id="85e85-117">类的公共成员应为该类的直接使用者提供正确的功能集。</span><span class="sxs-lookup"><span data-stu-id="85e85-117">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="85e85-118">旨在子类，在中重写虚拟成员和受保护的可访问性是作用域以用于其中的所有虚拟扩展性点的好办法。</span><span class="sxs-lookup"><span data-stu-id="85e85-118">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>  
  
 <span data-ttu-id="85e85-119">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="85e85-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="85e85-120">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="85e85-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e85-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="85e85-121">See Also</span></span>  
 [<span data-ttu-id="85e85-122">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="85e85-122">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="85e85-123">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="85e85-123">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
