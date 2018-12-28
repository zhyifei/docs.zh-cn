---
title: 框架设计准则
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
author: KrzysztofCwalina
ms.openlocfilehash: 2317ed0dbe8a6e69452ac0721ffed1b9da50a907
ms.sourcegitcommit: 49af435bfdd41faf26d38c20c5b0cc07e87bea60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2018
ms.locfileid: "53396924"
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="b8705-102">框架设计准则</span><span class="sxs-lookup"><span data-stu-id="b8705-102">Framework Design Guidelines</span></span>
<span data-ttu-id="b8705-103">本部分提供的准则适用于设计那些可扩展 .NET Framework 并与之交互的库。</span><span class="sxs-lookup"><span data-stu-id="b8705-103">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="b8705-104">目的是通过提供独立于开发所用编程语言的统一编程模型，帮助库设计者确保 API 的一致性和易用性。</span><span class="sxs-lookup"><span data-stu-id="b8705-104">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="b8705-105">建议在开发可扩展 .NET Framework 的类和组件时遵循这些设计准则。</span><span class="sxs-lookup"><span data-stu-id="b8705-105">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="b8705-106">不一致的库设计会对开发人员的工作效率产生负面影响，影响用户采用它。</span><span class="sxs-lookup"><span data-stu-id="b8705-106">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="b8705-107">这些准则已整理成简单的建议，其开头词为`要 `Do``，`考虑 `Consider``，`避免 `Avoid``和`不要 `Do not``。</span><span class="sxs-lookup"><span data-stu-id="b8705-107">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="b8705-108">这些准则旨在帮助类库设计人员了解如何在不同解决方案之间进行权衡取舍。</span><span class="sxs-lookup"><span data-stu-id="b8705-108">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="b8705-109">在某些情况下，若要进行良好的库设计，必须违反这些设计准则。</span><span class="sxs-lookup"><span data-stu-id="b8705-109">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="b8705-110">这种情况应该很罕见，重要的是，你的决定要有明确和令人信服的理由。</span><span class="sxs-lookup"><span data-stu-id="b8705-110">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="b8705-111">这些准则摘自本书*Framework 设计准则：约定、 语法和模式的可重用的.NET 库，第 2 版*，作者 Krzysztof Cwalina 和 Brad Abrams。</span><span class="sxs-lookup"><span data-stu-id="b8705-111">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b8705-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="b8705-112">In This Section</span></span>  
 [<span data-ttu-id="b8705-113">命名规则</span><span class="sxs-lookup"><span data-stu-id="b8705-113">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 <span data-ttu-id="b8705-114">提供在类库中命名程序集、名称空间、类型和成员的准则。</span><span class="sxs-lookup"><span data-stu-id="b8705-114">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="b8705-115">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="b8705-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 <span data-ttu-id="b8705-116">提供了使用静态和抽象类、 接口、 枚举、 结构和其他类型的指导原则。</span><span class="sxs-lookup"><span data-stu-id="b8705-116">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="b8705-117">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="b8705-117">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 <span data-ttu-id="b8705-118">提供设计和使用属性、 方法、 构造函数、 字段、 事件、 运算符和参数的准则。</span><span class="sxs-lookup"><span data-stu-id="b8705-118">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="b8705-119">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="b8705-119">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 <span data-ttu-id="b8705-120">讨论可扩展性机制，例如子类化，使用事件、虚拟成员和回调，并说明如何选择最符合框架要求的机制。</span><span class="sxs-lookup"><span data-stu-id="b8705-120">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="b8705-121">异常的设计准则</span><span class="sxs-lookup"><span data-stu-id="b8705-121">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)  
 <span data-ttu-id="b8705-122">描述设计、 引发和捕获异常的设计准则。</span><span class="sxs-lookup"><span data-stu-id="b8705-122">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="b8705-123">使用准则</span><span class="sxs-lookup"><span data-stu-id="b8705-123">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 <span data-ttu-id="b8705-124">介绍常见类型（如数组、属性和集合、支持序列化及重载相等运算符）的使用准则。</span><span class="sxs-lookup"><span data-stu-id="b8705-124">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="b8705-125">常用设计模型</span><span class="sxs-lookup"><span data-stu-id="b8705-125">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 <span data-ttu-id="b8705-126">提供选择和实现依赖属性的指南。</span><span class="sxs-lookup"><span data-stu-id="b8705-126">Provides guidelines for choosing and implementing dependency properties.</span></span>  
  
 <span data-ttu-id="b8705-127">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="b8705-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b8705-128">*通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。* </span><span class="sxs-lookup"><span data-stu-id="b8705-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8705-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8705-129">See also</span></span>

- [<span data-ttu-id="b8705-130">概述</span><span class="sxs-lookup"><span data-stu-id="b8705-130">Overview</span></span>](../../../docs/framework/get-started/overview.md)  
- [<span data-ttu-id="b8705-131">.NET Framework 的路线图</span><span class="sxs-lookup"><span data-stu-id="b8705-131">Roadmap for the .NET Framework</span></span>](https://msdn.microsoft.com/library/0b46b7c6-9163-4f99-8e58-0d1ee7da8c67)  
- [<span data-ttu-id="b8705-132">开发指南</span><span class="sxs-lookup"><span data-stu-id="b8705-132">Development Guide</span></span>](../../../docs/framework/development-guide.md)
