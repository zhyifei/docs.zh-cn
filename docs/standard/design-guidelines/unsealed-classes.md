---
title: 非密封类
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef0f1c4c9b2d1928d6f96d62ab12df9786756498
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891372"
---
# <a name="unsealed-classes"></a><span data-ttu-id="76003-102">非密封类</span><span class="sxs-lookup"><span data-stu-id="76003-102">Unsealed Classes</span></span>
<span data-ttu-id="76003-103">密封的类不能被继承，并会阻止可扩展性。</span><span class="sxs-lookup"><span data-stu-id="76003-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="76003-104">与此相反，可被继承的类称为非密封类。</span><span class="sxs-lookup"><span data-stu-id="76003-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="76003-105">**✓ 考虑**使用未添加虚拟或受保护成员的非密封类，这是为框架提供经济但有效的可扩展性的好方法。</span><span class="sxs-lookup"><span data-stu-id="76003-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="76003-106">开发人员通常希望从非密封的类继承，以便添加自定义构造函数、新方法或方法重载等便利成员。</span><span class="sxs-lookup"><span data-stu-id="76003-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="76003-107">例如，`System.Messaging.MessageQueue` 是非密封的，因此用户可以创建默认为特定队列路径的自定义队列，或添加自定义方法以简化特定方案的 API。</span><span class="sxs-lookup"><span data-stu-id="76003-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="76003-108">在大多数编程语言中，默认情况下类都是非密封的，这也是框架中大多数类的推荐默认值。</span><span class="sxs-lookup"><span data-stu-id="76003-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="76003-109">框架用户非常需要非密封类型提供的可扩展性，并且这种可扩展性的提供成本相当低，因为非密封类型的相关测试成本也相对较低。</span><span class="sxs-lookup"><span data-stu-id="76003-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="76003-110">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="76003-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="76003-111">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="76003-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76003-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="76003-112">See also</span></span>

- [<span data-ttu-id="76003-113">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="76003-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="76003-114">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="76003-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [<span data-ttu-id="76003-115">密封</span><span class="sxs-lookup"><span data-stu-id="76003-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
