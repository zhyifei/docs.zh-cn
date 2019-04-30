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
author: KrzysztofCwalina
ms.openlocfilehash: d7023bbe59eb3590af47952a2fe24c5f40b3ca68
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945517"
---
# <a name="member-design-guidelines"></a><span data-ttu-id="b481e-102">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="b481e-102">Member Design Guidelines</span></span>
<span data-ttu-id="b481e-103">方法、属性、事件、构造函数和字段统称为成员。</span><span class="sxs-lookup"><span data-stu-id="b481e-103">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="b481e-104">框架功能最终以成员的方式向框架用户公开。</span><span class="sxs-lookup"><span data-stu-id="b481e-104">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="b481e-105">成员可以是虚拟的或非虚拟的，具体的或抽象的，静态的或实例的，并且可以具有多个不同的可访问范围。</span><span class="sxs-lookup"><span data-stu-id="b481e-105">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="b481e-106">这些多样性提供了令人难以置信的表现力，但同时也需要框架设计者小心处理。</span><span class="sxs-lookup"><span data-stu-id="b481e-106">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="b481e-107">本章提供了在设计任何类型的成员时应遵循的基本准则。</span><span class="sxs-lookup"><span data-stu-id="b481e-107">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b481e-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="b481e-108">In This Section</span></span>  
 [<span data-ttu-id="b481e-109">成员重载</span><span class="sxs-lookup"><span data-stu-id="b481e-109">Member Overloading</span></span>](../../../docs/standard/design-guidelines/member-overloading.md)  
 [<span data-ttu-id="b481e-110">属性设计</span><span class="sxs-lookup"><span data-stu-id="b481e-110">Property Design</span></span>](../../../docs/standard/design-guidelines/property.md)  
 [<span data-ttu-id="b481e-111">构造函数设计</span><span class="sxs-lookup"><span data-stu-id="b481e-111">Constructor Design</span></span>](../../../docs/standard/design-guidelines/constructor.md)  
 [<span data-ttu-id="b481e-112">事件设计</span><span class="sxs-lookup"><span data-stu-id="b481e-112">Event Design</span></span>](../../../docs/standard/design-guidelines/event.md)  
 [<span data-ttu-id="b481e-113">字段设计</span><span class="sxs-lookup"><span data-stu-id="b481e-113">Field Design</span></span>](../../../docs/standard/design-guidelines/field.md)  
 [<span data-ttu-id="b481e-114">扩展方法</span><span class="sxs-lookup"><span data-stu-id="b481e-114">Extension Methods</span></span>](../../../docs/standard/design-guidelines/extension-methods.md)  
 [<span data-ttu-id="b481e-115">运算符重载</span><span class="sxs-lookup"><span data-stu-id="b481e-115">Operator Overloads</span></span>](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [<span data-ttu-id="b481e-116">参数设计</span><span class="sxs-lookup"><span data-stu-id="b481e-116">Parameter Design</span></span>](../../../docs/standard/design-guidelines/parameter-design.md)  
 <span data-ttu-id="b481e-117">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="b481e-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b481e-118">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="b481e-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b481e-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="b481e-119">See also</span></span>

- [<span data-ttu-id="b481e-120">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="b481e-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
