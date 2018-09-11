---
title: 静态类设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3a0a51fc6055190f9a0189de2e17d98f88036ea
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2018
ms.locfileid: "44367354"
---
# <a name="static-class-design"></a><span data-ttu-id="9a9bb-102">静态类设计</span><span class="sxs-lookup"><span data-stu-id="9a9bb-102">Static Class Design</span></span>
<span data-ttu-id="9a9bb-103">静态类被定义为仅包含静态成员的类 (当然除了继承自的实例成员<xref:System.Object?displayProperty=nameWithType>和可能是私有构造函数)。</span><span class="sxs-lookup"><span data-stu-id="9a9bb-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="9a9bb-104">某些语言用于静态类提供内置支持。</span><span class="sxs-lookup"><span data-stu-id="9a9bb-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="9a9bb-105">在 C# 2.0 及更高版本，当一个类声明为静态，密封的抽象，并且可以重写任何实例成员，或将其声明。</span><span class="sxs-lookup"><span data-stu-id="9a9bb-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>  
  
 <span data-ttu-id="9a9bb-106">静态类是纯粹的面向对象的设计和简单性之间泄漏。</span><span class="sxs-lookup"><span data-stu-id="9a9bb-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="9a9bb-107">它们通常用于提供其他操作的快捷方式 (如<xref:System.IO.File?displayProperty=nameWithType>)，持有者的扩展方法或为其完整的面向对象的包装器是不能确保的功能 (如<xref:System.Environment?displayProperty=nameWithType>)。</span><span class="sxs-lookup"><span data-stu-id="9a9bb-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="9a9bb-108">**✓ DO** 静态类应谨慎使用。</span><span class="sxs-lookup"><span data-stu-id="9a9bb-108">**✓ DO** use static classes sparingly.</span></span>  
  
 <span data-ttu-id="9a9bb-109">应仅作为 framework 的面向对象的核心的支持类使用静态的类。</span><span class="sxs-lookup"><span data-stu-id="9a9bb-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>  
  
 <span data-ttu-id="9a9bb-110">**X DO NOT** 静态类视为杂项存储桶。</span><span class="sxs-lookup"><span data-stu-id="9a9bb-110">**X DO NOT** treat static classes as a miscellaneous bucket.</span></span>  
  
 <span data-ttu-id="9a9bb-111">**X DO NOT** 声明或重写中的静态类的实例成员。</span><span class="sxs-lookup"><span data-stu-id="9a9bb-111">**X DO NOT** declare or override instance members in static classes.</span></span>  
  
 <span data-ttu-id="9a9bb-112">**✓ DO** 静态类声明为密封的抽象，并添加一个私有实例构造函数，如果您的编程语言不具有对静态类的内置支持。</span><span class="sxs-lookup"><span data-stu-id="9a9bb-112">**✓ DO** declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>  
  
 <span data-ttu-id="9a9bb-113">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="9a9bb-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9a9bb-114">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="9a9bb-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a9bb-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a9bb-115">See also</span></span>

- [<span data-ttu-id="9a9bb-116">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="9a9bb-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="9a9bb-117">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="9a9bb-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
