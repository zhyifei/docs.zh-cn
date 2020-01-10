---
title: 成员设计准则
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
ms.openlocfilehash: cf4f1d2fee73e3e65dc4d92ea97a62f4a7e4c4e5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709265"
---
# <a name="member-design-guidelines"></a><span data-ttu-id="e117d-102">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="e117d-102">Member Design Guidelines</span></span>
<span data-ttu-id="e117d-103">方法、属性、事件、构造函数和字段统称为成员。</span><span class="sxs-lookup"><span data-stu-id="e117d-103">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="e117d-104">框架功能最终以成员的方式向框架用户公开。</span><span class="sxs-lookup"><span data-stu-id="e117d-104">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="e117d-105">成员可以是虚拟的或非虚拟的，具体的或抽象的，静态的或实例的，并且可以具有多个不同的可访问范围。</span><span class="sxs-lookup"><span data-stu-id="e117d-105">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="e117d-106">这些多样性提供了令人难以置信的表现力，但同时也需要框架设计者小心处理。</span><span class="sxs-lookup"><span data-stu-id="e117d-106">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="e117d-107">本章提供了在设计任何类型的成员时应遵循的基本准则。</span><span class="sxs-lookup"><span data-stu-id="e117d-107">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e117d-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="e117d-108">In This Section</span></span>  
 [<span data-ttu-id="e117d-109">成员重载</span><span class="sxs-lookup"><span data-stu-id="e117d-109">Member Overloading</span></span>](../../../docs/standard/design-guidelines/member-overloading.md)  
 [<span data-ttu-id="e117d-110">属性设计</span><span class="sxs-lookup"><span data-stu-id="e117d-110">Property Design</span></span>](../../../docs/standard/design-guidelines/property.md)  
 [<span data-ttu-id="e117d-111">构造函数设计</span><span class="sxs-lookup"><span data-stu-id="e117d-111">Constructor Design</span></span>](../../../docs/standard/design-guidelines/constructor.md)  
 [<span data-ttu-id="e117d-112">事件设计</span><span class="sxs-lookup"><span data-stu-id="e117d-112">Event Design</span></span>](../../../docs/standard/design-guidelines/event.md)  
 [<span data-ttu-id="e117d-113">字段设计</span><span class="sxs-lookup"><span data-stu-id="e117d-113">Field Design</span></span>](../../../docs/standard/design-guidelines/field.md)  
 [<span data-ttu-id="e117d-114">扩展方法</span><span class="sxs-lookup"><span data-stu-id="e117d-114">Extension Methods</span></span>](../../../docs/standard/design-guidelines/extension-methods.md)  
 [<span data-ttu-id="e117d-115">运算符重载</span><span class="sxs-lookup"><span data-stu-id="e117d-115">Operator Overloads</span></span>](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [<span data-ttu-id="e117d-116">参数设计</span><span class="sxs-lookup"><span data-stu-id="e117d-116">Parameter Design</span></span>](../../../docs/standard/design-guidelines/parameter-design.md)  
 <span data-ttu-id="e117d-117">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="e117d-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e117d-118">\*在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。</span><span class="sxs-lookup"><span data-stu-id="e117d-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e117d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e117d-119">See also</span></span>

- [<span data-ttu-id="e117d-120">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="e117d-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
