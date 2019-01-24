---
title: 受保护的成员
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: KrzysztofCwalina
ms.openlocfilehash: 7d940f10799df2efc6c6d031781e1ef7cf777dd6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559330"
---
# <a name="protected-members"></a><span data-ttu-id="6ec89-102">受保护的成员</span><span class="sxs-lookup"><span data-stu-id="6ec89-102">Protected Members</span></span>
<span data-ttu-id="6ec89-103">受保护的成员本身不提供任何可扩展性，但它们可以通过子类化使可扩展性更强大。</span><span class="sxs-lookup"><span data-stu-id="6ec89-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="6ec89-104">它们可用于公开高级自定义选项，而不会毫无必要地使主公共接口复杂化。</span><span class="sxs-lookup"><span data-stu-id="6ec89-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="6ec89-105">框架设计者需要小心使用受保护的成员，因为“受保护”一词会给人一种虚假的安全感。</span><span class="sxs-lookup"><span data-stu-id="6ec89-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="6ec89-106">任何人都能够对未密封的类进行子类化并访问受保护的成员，因此所有用于公共成员的防御性编码实践都适用于受保护的成员。</span><span class="sxs-lookup"><span data-stu-id="6ec89-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="6ec89-107">**✓ 考虑** 使用受保护的高级自定义的成员。</span><span class="sxs-lookup"><span data-stu-id="6ec89-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="6ec89-108">**✓ 务必** 处理未密封类作为公共以便进行安全、 文档和兼容性分析中的受保护的成员。</span><span class="sxs-lookup"><span data-stu-id="6ec89-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="6ec89-109">任何人都可以从类继承，并且可以访问受保护的成员。</span><span class="sxs-lookup"><span data-stu-id="6ec89-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="6ec89-110">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="6ec89-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6ec89-111">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="6ec89-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec89-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ec89-112">See also</span></span>

- [<span data-ttu-id="6ec89-113">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="6ec89-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="6ec89-114">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="6ec89-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
