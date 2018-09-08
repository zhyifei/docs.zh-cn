---
title: 抽象类设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5b9dacc4995a126e1ee3f6062dca796194d4882
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44128519"
---
# <a name="abstract-class-design"></a><span data-ttu-id="b787d-102">抽象类设计</span><span class="sxs-lookup"><span data-stu-id="b787d-102">Abstract Class Design</span></span>
<span data-ttu-id="b787d-103">**X DO NOT** 在抽象类型中定义公共或受保护内部构造函数。</span><span class="sxs-lookup"><span data-stu-id="b787d-103">**X DO NOT** define public or protected internal constructors in abstract types.</span></span>  
  
 <span data-ttu-id="b787d-104">构造函数应为公共，仅当用户将需要创建该类型的实例。</span><span class="sxs-lookup"><span data-stu-id="b787d-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="b787d-105">因为不能创建抽象类型的实例，具有公共构造函数的抽象类型不正确是设计并具有误导性的用户。</span><span class="sxs-lookup"><span data-stu-id="b787d-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>  
  
 <span data-ttu-id="b787d-106">**✓ DO** 在抽象类中定义为受保护或内部构造函数。</span><span class="sxs-lookup"><span data-stu-id="b787d-106">**✓ DO** define a protected or an internal constructor in abstract classes.</span></span>  
  
 <span data-ttu-id="b787d-107">受保护的构造函数，则更容易，并只是允许基类以创建子类型时进行其自己的初始化。</span><span class="sxs-lookup"><span data-stu-id="b787d-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>  
  
 <span data-ttu-id="b787d-108">内部构造函数可以用于限制对程序集定义的类的抽象类的具体实现。</span><span class="sxs-lookup"><span data-stu-id="b787d-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>  
  
 <span data-ttu-id="b787d-109">**✓ DO** 提供至少一个继承自每个抽象类，要交付的具体类型。</span><span class="sxs-lookup"><span data-stu-id="b787d-109">**✓ DO** provide at least one concrete type that inherits from each abstract class that you ship.</span></span>  
  
 <span data-ttu-id="b787d-110">这些措施可帮助验证抽象类的设计。</span><span class="sxs-lookup"><span data-stu-id="b787d-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="b787d-111">例如，<xref:System.IO.FileStream?displayProperty=nameWithType>是一种实现的<xref:System.IO.Stream?displayProperty=nameWithType>抽象类。</span><span class="sxs-lookup"><span data-stu-id="b787d-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>  
  
 <span data-ttu-id="b787d-112">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="b787d-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b787d-113">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="b787d-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b787d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b787d-114">See also</span></span>

- [<span data-ttu-id="b787d-115">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="b787d-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="b787d-116">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="b787d-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
