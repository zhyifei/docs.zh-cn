---
title: "静态类设计"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8c36bf5790d033eddb6bb7e0d910482143a9bcac
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="static-class-design"></a><span data-ttu-id="d3542-102">静态类设计</span><span class="sxs-lookup"><span data-stu-id="d3542-102">Static Class Design</span></span>
<span data-ttu-id="d3542-103">静态该类可以定义为仅包含静态成员的类 (当然除了从继承的实例成员<xref:System.Object?displayProperty=nameWithType>和可能是一个专用的构造函数)。</span><span class="sxs-lookup"><span data-stu-id="d3542-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="d3542-104">某些语言为静态的类提供内置支持。</span><span class="sxs-lookup"><span data-stu-id="d3542-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="d3542-105">在 C# 2.0 版和更高版本的类声明为静态，它是密封的抽象，，可以重写任何实例成员，或将其声明。</span><span class="sxs-lookup"><span data-stu-id="d3542-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>  
  
 <span data-ttu-id="d3542-106">静态类是纯的面向对象的设计和简易性之间的折衷。</span><span class="sxs-lookup"><span data-stu-id="d3542-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="d3542-107">它们通常用于提供其他操作的快捷方式 (如<xref:System.IO.File?displayProperty=nameWithType>)，持有人的扩展方法或为其完整的面向对象的包装，则不能确保的功能 (如<xref:System.Environment?displayProperty=nameWithType>)。</span><span class="sxs-lookup"><span data-stu-id="d3542-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="d3542-108">**✓ 执行**静态类应谨慎使用。</span><span class="sxs-lookup"><span data-stu-id="d3542-108">**✓ DO** use static classes sparingly.</span></span>  
  
 <span data-ttu-id="d3542-109">静态类应只可用作支持框架的面向对象的核心的类。</span><span class="sxs-lookup"><span data-stu-id="d3542-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>  
  
 <span data-ttu-id="d3542-110">**X 不**静态类视为杂项存储桶。</span><span class="sxs-lookup"><span data-stu-id="d3542-110">**X DO NOT** treat static classes as a miscellaneous bucket.</span></span>  
  
 <span data-ttu-id="d3542-111">**X 不**声明或重写中的静态类的实例成员。</span><span class="sxs-lookup"><span data-stu-id="d3542-111">**X DO NOT** declare or override instance members in static classes.</span></span>  
  
 <span data-ttu-id="d3542-112">**✓ 执行**静态类声明为密封的抽象，并添加一个私有实例构造函数，如果您的编程语言不具有对静态类的内置支持。</span><span class="sxs-lookup"><span data-stu-id="d3542-112">**✓ DO** declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>  
  
 <span data-ttu-id="d3542-113">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="d3542-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d3542-114">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="d3542-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3542-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3542-115">See Also</span></span>  
 [<span data-ttu-id="d3542-116">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="d3542-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="d3542-117">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="d3542-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
