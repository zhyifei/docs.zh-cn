---
title: 框架设计准则
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c54ec4a5cc3c4bef1e6460b2c9971af4e2af983a
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="47b6d-102">框架设计准则</span><span class="sxs-lookup"><span data-stu-id="47b6d-102">Framework Design Guidelines</span></span>
<span data-ttu-id="47b6d-103">本部分提供有关设计的库扩展且使用.NET Framework 进行交互的准则。</span><span class="sxs-lookup"><span data-stu-id="47b6d-103">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="47b6d-104">目的是帮助确保通过提供用于开发的编程语言无关的统一编程模型的 API 一致性和易于使用的库设计器。</span><span class="sxs-lookup"><span data-stu-id="47b6d-104">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="47b6d-105">我们建议你遵循这些设计准则，开发的类和扩展.NET Framework 的组件时。</span><span class="sxs-lookup"><span data-stu-id="47b6d-105">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="47b6d-106">不一致的库设计产生负面影响开发人员工作效率，并且不鼓励采用。</span><span class="sxs-lookup"><span data-stu-id="47b6d-106">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="47b6d-107">这些准则组织为包含以这些前缀的简单建议`Do`， `Consider`， `Avoid`，和`Do not`。</span><span class="sxs-lookup"><span data-stu-id="47b6d-107">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="47b6d-108">这些指南旨在帮助了解不同的解决方案之间权衡的类库设计器。</span><span class="sxs-lookup"><span data-stu-id="47b6d-108">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="47b6d-109">可能有很好的库设计需要违反这些设计准则的情况。</span><span class="sxs-lookup"><span data-stu-id="47b6d-109">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="47b6d-110">这种情况下应该很少见，而且很重要，必须为你确定有充分的理由。</span><span class="sxs-lookup"><span data-stu-id="47b6d-110">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="47b6d-111">这些准则摘自书*Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式*、 Krzysztof Cwalina 和 Brad Abrams。</span><span class="sxs-lookup"><span data-stu-id="47b6d-111">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="47b6d-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="47b6d-112">In This Section</span></span>  
 [<span data-ttu-id="47b6d-113">命名规则</span><span class="sxs-lookup"><span data-stu-id="47b6d-113">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 <span data-ttu-id="47b6d-114">命名程序集、 命名空间、 类型和成员类库中的提供了准则。</span><span class="sxs-lookup"><span data-stu-id="47b6d-114">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="47b6d-115">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="47b6d-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 <span data-ttu-id="47b6d-116">提供用于静态和抽象类、 接口、 枚举、 结构和其他类型的准则。</span><span class="sxs-lookup"><span data-stu-id="47b6d-116">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="47b6d-117">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="47b6d-117">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 <span data-ttu-id="47b6d-118">提供有关设计和使用属性、 方法、 构造函数、 字段、 事件、 运算符和参数的准则。</span><span class="sxs-lookup"><span data-stu-id="47b6d-118">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="47b6d-119">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="47b6d-119">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 <span data-ttu-id="47b6d-120">讨论了扩展性机制，例如子类化，使用事件、 虚拟成员和回调，并说明如何选择最好地满足您的框架的需求的机制。</span><span class="sxs-lookup"><span data-stu-id="47b6d-120">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="47b6d-121">异常的设计准则</span><span class="sxs-lookup"><span data-stu-id="47b6d-121">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)  
 <span data-ttu-id="47b6d-122">描述设计、 引发和捕获异常的设计准则。</span><span class="sxs-lookup"><span data-stu-id="47b6d-122">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="47b6d-123">使用准则</span><span class="sxs-lookup"><span data-stu-id="47b6d-123">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 <span data-ttu-id="47b6d-124">介绍如何使用常见的类型，如数组、 属性和集合、 支持序列化，以及重载相等运算符的指南。</span><span class="sxs-lookup"><span data-stu-id="47b6d-124">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="47b6d-125">常用设计模型</span><span class="sxs-lookup"><span data-stu-id="47b6d-125">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 <span data-ttu-id="47b6d-126">选择并实施依赖项属性和的释放模式提供了准则。</span><span class="sxs-lookup"><span data-stu-id="47b6d-126">Provides guidelines for choosing and implementing dependency properties and the dispose pattern.</span></span>  
  
 <span data-ttu-id="47b6d-127">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="47b6d-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="47b6d-128">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="47b6d-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47b6d-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="47b6d-129">See Also</span></span>  
 [<span data-ttu-id="47b6d-130">概述</span><span class="sxs-lookup"><span data-stu-id="47b6d-130">Overview</span></span>](../../../docs/framework/get-started/overview.md)  
 [<span data-ttu-id="47b6d-131">.NET Framework 的路线图</span><span class="sxs-lookup"><span data-stu-id="47b6d-131">Roadmap for the .NET Framework</span></span>](https://msdn.microsoft.com/library/0b46b7c6-9163-4f99-8e58-0d1ee7da8c67)  
 [<span data-ttu-id="47b6d-132">开发指南</span><span class="sxs-lookup"><span data-stu-id="47b6d-132">Development Guide</span></span>](../../../docs/framework/development-guide.md)
