---
title: 成员设计准则
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1598ac63af38f1ca3e11104bc8e1cd6323d35ed
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259962"
---
# <a name="member-design-guidelines"></a><span data-ttu-id="e05e3-102">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="e05e3-102">Member Design Guidelines</span></span>
<span data-ttu-id="e05e3-103">方法、 属性、 事件、 构造函数和字段统称为成员。</span><span class="sxs-lookup"><span data-stu-id="e05e3-103">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="e05e3-104">成员是最终的框架功能公开给最终用户的一种框架的方式。</span><span class="sxs-lookup"><span data-stu-id="e05e3-104">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="e05e3-105">成员可以是虚拟或非虚拟或抽象的具体静态或实例，并可以有多个不同的作用域的可访问性。</span><span class="sxs-lookup"><span data-stu-id="e05e3-105">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="e05e3-106">所有这样的多样性提供令人难以置信的表达力度，但在同一时间需要的部分框架设计器的小心。</span><span class="sxs-lookup"><span data-stu-id="e05e3-106">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="e05e3-107">本章提供了基本设计的任何类型的成员时应遵循的指导原则。</span><span class="sxs-lookup"><span data-stu-id="e05e3-107">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e05e3-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="e05e3-108">In This Section</span></span>  
 [<span data-ttu-id="e05e3-109">成员重载</span><span class="sxs-lookup"><span data-stu-id="e05e3-109">Member Overloading</span></span>](../../../docs/standard/design-guidelines/member-overloading.md)  
 [<span data-ttu-id="e05e3-110">属性设计</span><span class="sxs-lookup"><span data-stu-id="e05e3-110">Property Design</span></span>](../../../docs/standard/design-guidelines/property.md)  
 [<span data-ttu-id="e05e3-111">构造函数设计</span><span class="sxs-lookup"><span data-stu-id="e05e3-111">Constructor Design</span></span>](../../../docs/standard/design-guidelines/constructor.md)  
 [<span data-ttu-id="e05e3-112">事件设计</span><span class="sxs-lookup"><span data-stu-id="e05e3-112">Event Design</span></span>](../../../docs/standard/design-guidelines/event.md)  
 [<span data-ttu-id="e05e3-113">字段设计</span><span class="sxs-lookup"><span data-stu-id="e05e3-113">Field Design</span></span>](../../../docs/standard/design-guidelines/field.md)  
 [<span data-ttu-id="e05e3-114">扩展方法</span><span class="sxs-lookup"><span data-stu-id="e05e3-114">Extension Methods</span></span>](../../../docs/standard/design-guidelines/extension-methods.md)  
 [<span data-ttu-id="e05e3-115">运算符重载</span><span class="sxs-lookup"><span data-stu-id="e05e3-115">Operator Overloads</span></span>](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [<span data-ttu-id="e05e3-116">参数设计</span><span class="sxs-lookup"><span data-stu-id="e05e3-116">Parameter Design</span></span>](../../../docs/standard/design-guidelines/parameter-design.md)  
 <span data-ttu-id="e05e3-117">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="e05e3-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e05e3-118">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="e05e3-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e05e3-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="e05e3-119">See also</span></span>

- [<span data-ttu-id="e05e3-120">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="e05e3-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
