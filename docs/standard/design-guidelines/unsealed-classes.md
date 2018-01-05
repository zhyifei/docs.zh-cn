---
title: "未密封类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ec66fb3dea74e6f738ec308ce0f88945526a0a77
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="unsealed-classes"></a><span data-ttu-id="ef3bd-102">未密封类</span><span class="sxs-lookup"><span data-stu-id="ef3bd-102">Unsealed Classes</span></span>
<span data-ttu-id="ef3bd-103">密封的类不能被继承，并会阻止扩展性。</span><span class="sxs-lookup"><span data-stu-id="ef3bd-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="ef3bd-104">与此相反，可以从继承的类称为未密封的类。</span><span class="sxs-lookup"><span data-stu-id="ef3bd-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="ef3bd-105">**请考虑 ✓**没有使用未密封的类添加虚拟或受保护成员，因为提供成本较低的好办法尚未非常感谢与框架的扩展性。</span><span class="sxs-lookup"><span data-stu-id="ef3bd-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="ef3bd-106">开发人员通常想要从以便添加方便成员，如自定义的构造函数、 新方法或方法重载的未密封类继承。</span><span class="sxs-lookup"><span data-stu-id="ef3bd-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="ef3bd-107">例如，`System.Messaging.MessageQueue`是未密封，因此允许用户创建自定义队列到特定的队列路径该默认行为或添加自定义方法来简化用于特定方案的 API。</span><span class="sxs-lookup"><span data-stu-id="ef3bd-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="ef3bd-108">类在最编程语言中，默认情况下未密封的这也是框架中的大多数类建议的默认设置。</span><span class="sxs-lookup"><span data-stu-id="ef3bd-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="ef3bd-109">未密封的类型提供的扩展性是得多应有的重视 framework 用户和提供由于相对较低的测试与未密封的类型相关联的成本很便宜。</span><span class="sxs-lookup"><span data-stu-id="ef3bd-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="ef3bd-110">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="ef3bd-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ef3bd-111">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="ef3bd-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef3bd-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef3bd-112">See Also</span></span>  
 [<span data-ttu-id="ef3bd-113">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="ef3bd-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="ef3bd-114">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="ef3bd-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="ef3bd-115">密封</span><span class="sxs-lookup"><span data-stu-id="ef3bd-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
