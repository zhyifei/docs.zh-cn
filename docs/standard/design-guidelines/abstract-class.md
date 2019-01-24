---
title: 抽象类设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
author: KrzysztofCwalina
ms.openlocfilehash: 6eec3bb4575b89c6476e6c3410050c705141777f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550405"
---
# <a name="abstract-class-design"></a><span data-ttu-id="d269a-102">抽象类设计</span><span class="sxs-lookup"><span data-stu-id="d269a-102">Abstract Class Design</span></span>
<span data-ttu-id="d269a-103">**X** 请勿在抽象类型中定义公共或受保护的内部构造函数。</span><span class="sxs-lookup"><span data-stu-id="d269a-103">**X DO NOT** define public or protected internal constructors in abstract types.</span></span>  
  
 <span data-ttu-id="d269a-104">只有在用户需要创建该类型的实例时，构造函数才应该是公共构造函数。
</span><span class="sxs-lookup"><span data-stu-id="d269a-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="d269a-105">由于无法创建抽象类型的实例，因此带有公共构造函数的抽象类型设计不正确，会误导用户。</span><span class="sxs-lookup"><span data-stu-id="d269a-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>  
  
 <span data-ttu-id="d269a-106">**✓** 请在抽象类中定义受保护的或内部构造函数</span><span class="sxs-lookup"><span data-stu-id="d269a-106">**✓ DO** define a protected or an internal constructor in abstract classes.</span></span>  
  
 <span data-ttu-id="d269a-107">受保护的构造函数更常见，并且只允许基类在创建子类型时自行初始化。</span><span class="sxs-lookup"><span data-stu-id="d269a-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>  
  
 <span data-ttu-id="d269a-108">内部构造函数可用于将抽象类的具体实现限制为定义该类的程序集。</span><span class="sxs-lookup"><span data-stu-id="d269a-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>  
  
 <span data-ttu-id="d269a-109">**✓** 请提供至少一种继承自你交付的每个抽象类的具体类型。</span><span class="sxs-lookup"><span data-stu-id="d269a-109">**✓ DO** provide at least one concrete type that inherits from each abstract class that you ship.</span></span>  
  
 <span data-ttu-id="d269a-110">这些措施有助于验证抽象类的设计。</span><span class="sxs-lookup"><span data-stu-id="d269a-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="d269a-111">例如，<xref:System.IO.FileStream?displayProperty=nameWithType> 是 <xref:System.IO.Stream?displayProperty=nameWithType> 抽象类的实现。</span><span class="sxs-lookup"><span data-stu-id="d269a-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>  
  
 <span data-ttu-id="d269a-112">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="d269a-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d269a-113">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="d269a-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d269a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d269a-114">See also</span></span>

- [<span data-ttu-id="d269a-115">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="d269a-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="d269a-116">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="d269a-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
