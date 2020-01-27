---
title: 静态类设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
ms.openlocfilehash: 104fa204a95ef31d34e224348068e3a6505aded5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743591"
---
# <a name="static-class-design"></a><span data-ttu-id="9a630-102">静态类设计</span><span class="sxs-lookup"><span data-stu-id="9a630-102">Static Class Design</span></span>
<span data-ttu-id="9a630-103">静态类的定义为：仅包含静态成员的类 (当然除了继承自<xref:System.Object?displayProperty=nameWithType> 的实例成员和可能是私有的构造函数)。</span><span class="sxs-lookup"><span data-stu-id="9a630-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="9a630-104">某些语言提供对静态类的内置支持。</span><span class="sxs-lookup"><span data-stu-id="9a630-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="9a630-105">在 C# 2.0 及更高版本中，当类声明为静态时，它是密封、抽象的，并且不能覆盖或声明实例成员。</span><span class="sxs-lookup"><span data-stu-id="9a630-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>

 <span data-ttu-id="9a630-106">静态类是纯面向对象设计和简单性之间的妥协。</span><span class="sxs-lookup"><span data-stu-id="9a630-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="9a630-107">它们通常用于提供其他操作的快捷方式（例如<xref:System.IO.File?displayProperty=nameWithType> ），扩展方法的持有者，或完全面向对象的包装器不合适的功能（例如<xref:System.Environment?displayProperty=nameWithType> ）。</span><span class="sxs-lookup"><span data-stu-id="9a630-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="9a630-108">✔️尽量少使用静态类。</span><span class="sxs-lookup"><span data-stu-id="9a630-108">✔️ DO use static classes sparingly.</span></span>

 <span data-ttu-id="9a630-109">静态类应仅用作框架的面向对象核心的支持类。</span><span class="sxs-lookup"><span data-stu-id="9a630-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>

 <span data-ttu-id="9a630-110">❌ 不要将静态类视为其他存储桶。</span><span class="sxs-lookup"><span data-stu-id="9a630-110">❌ DO NOT treat static classes as a miscellaneous bucket.</span></span>

 <span data-ttu-id="9a630-111">❌ 不声明或重写静态类中的实例成员。</span><span class="sxs-lookup"><span data-stu-id="9a630-111">❌ DO NOT declare or override instance members in static classes.</span></span>

 <span data-ttu-id="9a630-112">如果你的编程语言没有对静态类的内置支持，✔️会将静态类声明为密封、抽象并添加私有实例构造函数。</span><span class="sxs-lookup"><span data-stu-id="9a630-112">✔️ DO declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>

 <span data-ttu-id="9a630-113">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="9a630-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="9a630-114">\*在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。</span><span class="sxs-lookup"><span data-stu-id="9a630-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="9a630-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a630-115">See also</span></span>

- [<span data-ttu-id="9a630-116">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="9a630-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="9a630-117">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="9a630-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
