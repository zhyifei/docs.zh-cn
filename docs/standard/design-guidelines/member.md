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
ms.openlocfilehash: 1c04b431224a1d4f03e85397b854a52856e114e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571392"
---
# <a name="member-design-guidelines"></a><span data-ttu-id="b9c04-102">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="b9c04-102">Member Design Guidelines</span></span>
<span data-ttu-id="b9c04-103">方法、 属性、 事件、 构造函数和字段统称作为成员。</span><span class="sxs-lookup"><span data-stu-id="b9c04-103">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="b9c04-104">成员最终是依据 framework 功能公开给最终用户的 framework 的手段。</span><span class="sxs-lookup"><span data-stu-id="b9c04-104">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="b9c04-105">成员可以是虚拟或非虚拟、 实际或抽象的静态或实例，并且可以有多个不同的作用域的可访问性。</span><span class="sxs-lookup"><span data-stu-id="b9c04-105">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="b9c04-106">所有多样性提供难以置信表现力，但同时需要部分 framework 设计器的小心。</span><span class="sxs-lookup"><span data-stu-id="b9c04-106">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="b9c04-107">本章介绍了设计的任何类型的成员时，应遵循的基本指导原则。</span><span class="sxs-lookup"><span data-stu-id="b9c04-107">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b9c04-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="b9c04-108">In This Section</span></span>  
 [<span data-ttu-id="b9c04-109">成员重载</span><span class="sxs-lookup"><span data-stu-id="b9c04-109">Member Overloading</span></span>](../../../docs/standard/design-guidelines/member-overloading.md)  
 [<span data-ttu-id="b9c04-110">属性设计</span><span class="sxs-lookup"><span data-stu-id="b9c04-110">Property Design</span></span>](../../../docs/standard/design-guidelines/property.md)  
 [<span data-ttu-id="b9c04-111">构造函数设计</span><span class="sxs-lookup"><span data-stu-id="b9c04-111">Constructor Design</span></span>](../../../docs/standard/design-guidelines/constructor.md)  
 [<span data-ttu-id="b9c04-112">事件设计</span><span class="sxs-lookup"><span data-stu-id="b9c04-112">Event Design</span></span>](../../../docs/standard/design-guidelines/event.md)  
 [<span data-ttu-id="b9c04-113">字段设计</span><span class="sxs-lookup"><span data-stu-id="b9c04-113">Field Design</span></span>](../../../docs/standard/design-guidelines/field.md)  
 [<span data-ttu-id="b9c04-114">扩展方法</span><span class="sxs-lookup"><span data-stu-id="b9c04-114">Extension Methods</span></span>](../../../docs/standard/design-guidelines/extension-methods.md)  
 [<span data-ttu-id="b9c04-115">运算符重载</span><span class="sxs-lookup"><span data-stu-id="b9c04-115">Operator Overloads</span></span>](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [<span data-ttu-id="b9c04-116">参数设计</span><span class="sxs-lookup"><span data-stu-id="b9c04-116">Parameter Design</span></span>](../../../docs/standard/design-guidelines/parameter-design.md)  
 <span data-ttu-id="b9c04-117">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="b9c04-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b9c04-118">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="b9c04-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9c04-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9c04-119">See Also</span></span>  
 [<span data-ttu-id="b9c04-120">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="b9c04-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
