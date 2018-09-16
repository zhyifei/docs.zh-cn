---
title: 虚成员
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92b648e7886fb0214238e32eacae2870b470340
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45674450"
---
# <a name="virtual-members"></a><span data-ttu-id="c8d2c-102">虚成员</span><span class="sxs-lookup"><span data-stu-id="c8d2c-102">Virtual Members</span></span>
<span data-ttu-id="c8d2c-103">可以重写虚拟成员，因此更改行为的子类。</span><span class="sxs-lookup"><span data-stu-id="c8d2c-103">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="c8d2c-104">它们是非常类似于在它们提供的可扩展性方面的回调，但它们是在执行性能和内存消耗方面更好。</span><span class="sxs-lookup"><span data-stu-id="c8d2c-104">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="c8d2c-105">此外，虚拟成员感觉更自然需要创建一种特殊类型的现有类型 （专用化） 的方案中。</span><span class="sxs-lookup"><span data-stu-id="c8d2c-105">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>  
  
 <span data-ttu-id="c8d2c-106">虚拟成员优于回调和事件，但不是与非虚拟方法相比更好地执行。</span><span class="sxs-lookup"><span data-stu-id="c8d2c-106">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>  
  
 <span data-ttu-id="c8d2c-107">虚拟成员的主要缺点是，虚拟成员的行为仅可以修改在编译时。</span><span class="sxs-lookup"><span data-stu-id="c8d2c-107">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="c8d2c-108">可以在运行时修改回调的行为。</span><span class="sxs-lookup"><span data-stu-id="c8d2c-108">The behavior of a callback can be modified at runtime.</span></span>  
  
 <span data-ttu-id="c8d2c-109">虚拟成员，例如回调 （和可能有多个回调），是成本设计、 测试和维护，因为对虚拟成员的任何调用可以重写不可预知的方式，并可以执行任意代码。</span><span class="sxs-lookup"><span data-stu-id="c8d2c-109">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="c8d2c-110">此外，明确定义的虚拟成员的协定，因此设计和记录它们的成本更高版本时通常需要更多精力。</span><span class="sxs-lookup"><span data-stu-id="c8d2c-110">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>  
  
 <span data-ttu-id="c8d2c-111">**X DO NOT** 虚成员，除非你有理由这样做，并且注意与设计、 测试和维护虚拟成员相关的所有成本。</span><span class="sxs-lookup"><span data-stu-id="c8d2c-111">**X DO NOT** make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>  
  
 <span data-ttu-id="c8d2c-112">虚拟成员是更少内能容忍方面可以与其进行而不会破坏兼容性的更改。</span><span class="sxs-lookup"><span data-stu-id="c8d2c-112">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="c8d2c-113">此外，它们是慢于非虚拟成员，主要是因为对虚拟成员的调用不是内联。</span><span class="sxs-lookup"><span data-stu-id="c8d2c-113">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>  
  
 <span data-ttu-id="c8d2c-114">**✓ CONSIDER** 限制只将绝对必要的扩展性。</span><span class="sxs-lookup"><span data-stu-id="c8d2c-114">**✓ CONSIDER** limiting extensibility to only what is absolutely necessary.</span></span>  
  
 <span data-ttu-id="c8d2c-115">**✓ DO** 首选受保护的辅助功能的虚拟成员，而公共可访问性。</span><span class="sxs-lookup"><span data-stu-id="c8d2c-115">**✓ DO** prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="c8d2c-116">公共成员应通过调用受保护虚拟成员来提供可扩展性 （如果需要）。</span><span class="sxs-lookup"><span data-stu-id="c8d2c-116">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>  
  
 <span data-ttu-id="c8d2c-117">一个类的公共成员应为该类的直接使用者提供一组合适的功能。</span><span class="sxs-lookup"><span data-stu-id="c8d2c-117">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="c8d2c-118">旨在子类中, 被重写虚拟成员和受保护的可访问性是作用域为使用其中的所有虚拟扩展点的好办法。</span><span class="sxs-lookup"><span data-stu-id="c8d2c-118">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>  
  
 <span data-ttu-id="c8d2c-119">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="c8d2c-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c8d2c-120">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="c8d2c-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d2c-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8d2c-121">See also</span></span>

- [<span data-ttu-id="c8d2c-122">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="c8d2c-122">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="c8d2c-123">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="c8d2c-123">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
