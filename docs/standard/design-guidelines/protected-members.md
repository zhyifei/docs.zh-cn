---
title: "受保护的成员"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c3aacd0f08641c01200f0b1791a78413a306590
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="protected-members"></a><span data-ttu-id="46859-102">受保护的成员</span><span class="sxs-lookup"><span data-stu-id="46859-102">Protected Members</span></span>
<span data-ttu-id="46859-103">受保护的成员本身不提供任何可扩展性，但它们可以使通过子类化的扩展性功能更强大。</span><span class="sxs-lookup"><span data-stu-id="46859-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="46859-104">它们可以用于公开高级自定义选项，而不必要地并发的主要公共接口。</span><span class="sxs-lookup"><span data-stu-id="46859-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="46859-105">请小心使用受保护的成员，因为"保护"的名称可以提供安全的 false 意义上所需要的 framework 设计器。</span><span class="sxs-lookup"><span data-stu-id="46859-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="46859-106">任何人都可以为子类未密封的类和访问受保护成员，以及用于公共成员的防御性编码做法适用于受保护的成员的因此完全相同。</span><span class="sxs-lookup"><span data-stu-id="46859-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="46859-107">**请考虑 ✓**使用受保护的高级自定义的成员。</span><span class="sxs-lookup"><span data-stu-id="46859-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="46859-108">**✓ 执行**处理未密封类作为公共以便进行安全、 文档和兼容性分析中的受保护的成员。</span><span class="sxs-lookup"><span data-stu-id="46859-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="46859-109">任何人都可以从类继承，并且可以访问受保护的成员。</span><span class="sxs-lookup"><span data-stu-id="46859-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="46859-110">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="46859-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="46859-111">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="46859-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46859-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46859-112">See Also</span></span>  
 [<span data-ttu-id="46859-113">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="46859-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="46859-114">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="46859-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
