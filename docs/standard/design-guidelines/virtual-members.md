---
title: 虚拟成员
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
author: KrzysztofCwalina
ms.openlocfilehash: 1719e9843252c25d1e799471330c6cb08211245b
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128917"
---
# <a name="virtual-members"></a><span data-ttu-id="5c99d-102">虚拟成员</span><span class="sxs-lookup"><span data-stu-id="5c99d-102">Virtual Members</span></span>
<span data-ttu-id="5c99d-103">可以重写虚拟成员，从而改变子类的行为。</span><span class="sxs-lookup"><span data-stu-id="5c99d-103">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="5c99d-104">就提供的可扩展性而言，它们与回调非常相似，但在执行性能和内存消耗方面有更好的表现。</span><span class="sxs-lookup"><span data-stu-id="5c99d-104">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="5c99d-105">此外，虚拟成员在需要创建特殊类型的现有类型（特化）的场景中感觉更自然。</span><span class="sxs-lookup"><span data-stu-id="5c99d-105">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>  
  
 <span data-ttu-id="5c99d-106">虚拟成员的性能优于回调和事件，但不如非虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="5c99d-106">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>  
  
 <span data-ttu-id="5c99d-107">虚拟成员的主要缺点是虚拟成员的行为只能在编译时修改。</span><span class="sxs-lookup"><span data-stu-id="5c99d-107">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="5c99d-108">回调的行为可以在运行时修改。</span><span class="sxs-lookup"><span data-stu-id="5c99d-108">The behavior of a callback can be modified at runtime.</span></span>  
  
 <span data-ttu-id="5c99d-109">虚拟成员，如回调（可能不仅仅是回调），其设计、测试和维护成本很高，因为对虚拟成员的任何调用都可能以不可预测的方式重写，并且可以执行任意代码。</span><span class="sxs-lookup"><span data-stu-id="5c99d-109">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="5c99d-110">此外，通常需要更多的努力来明确定义虚拟成员的协定，因此设计和记录它们的成本更高。</span><span class="sxs-lookup"><span data-stu-id="5c99d-110">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>  
  
 <span data-ttu-id="5c99d-111">**X 切忌** 使用虚拟成员，除非你有充分的理由这样做，并且了解与设计、测试和维护虚拟成员相关的所有成本。</span><span class="sxs-lookup"><span data-stu-id="5c99d-111">**X DO NOT** make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>  
  
 <span data-ttu-id="5c99d-112">在不破坏兼容性的情况下，不容易对虚拟成员进行更改。</span><span class="sxs-lookup"><span data-stu-id="5c99d-112">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="5c99d-113">此外，它们比非虚拟成员慢，主要是因为对虚拟成员的调用不是内联的。</span><span class="sxs-lookup"><span data-stu-id="5c99d-113">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>  
  
 <span data-ttu-id="5c99d-114">**✓ 考虑** 将可扩展性限制在绝对必要的情况。</span><span class="sxs-lookup"><span data-stu-id="5c99d-114">**✓ CONSIDER** limiting extensibility to only what is absolutely necessary.</span></span>  
  
 <span data-ttu-id="5c99d-115">**✓ 务必** 对于虚拟成员，更倾向使用受保护的可访问性而非公共可访问性。</span><span class="sxs-lookup"><span data-stu-id="5c99d-115">**✓ DO** prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="5c99d-116">公共成员应通过调用受保护的虚拟成员来提供可扩展性（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="5c99d-116">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>  
  
 <span data-ttu-id="5c99d-117">一个类的公共成员应该为该类的直接使用者提供正确的功能集。</span><span class="sxs-lookup"><span data-stu-id="5c99d-117">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="5c99d-118">根据设计，虚拟成员在子类中被重写。受保护的可访问性是一种很好的方式，可以将所有虚拟扩展点限定在可以使用它们的地方。</span><span class="sxs-lookup"><span data-stu-id="5c99d-118">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>  
  
 <span data-ttu-id="5c99d-119">*部分版权 © 2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="5c99d-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5c99d-120">*通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*</span><span class="sxs-lookup"><span data-stu-id="5c99d-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c99d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c99d-121">See also</span></span>

- [<span data-ttu-id="5c99d-122">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="5c99d-122">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="5c99d-123">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="5c99d-123">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
