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
ms.openlocfilehash: 44d342662e1aaeb51f14470f354f2dadd9a6f18d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743647"
---
# <a name="protected-members"></a><span data-ttu-id="2cc90-102">受保护的成员</span><span class="sxs-lookup"><span data-stu-id="2cc90-102">Protected Members</span></span>
<span data-ttu-id="2cc90-103">受保护的成员本身不提供任何可扩展性，但它们可以通过子类化使可扩展性更强大。</span><span class="sxs-lookup"><span data-stu-id="2cc90-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="2cc90-104">它们可用于公开高级自定义选项，而不会毫无必要地使主公共接口复杂化。</span><span class="sxs-lookup"><span data-stu-id="2cc90-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>

 <span data-ttu-id="2cc90-105">框架设计者需要小心使用受保护的成员，因为“受保护”一词会给人一种虚假的安全感。</span><span class="sxs-lookup"><span data-stu-id="2cc90-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="2cc90-106">任何人都能够对未密封的类进行子类化并访问受保护的成员，因此所有用于公共成员的防御性编码实践都适用于受保护的成员。</span><span class="sxs-lookup"><span data-stu-id="2cc90-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>

 <span data-ttu-id="2cc90-107">✔️考虑使用受保护的成员进行高级自定义。</span><span class="sxs-lookup"><span data-stu-id="2cc90-107">✔️ CONSIDER using protected members for advanced customization.</span></span>

 <span data-ttu-id="2cc90-108">✔️将未密封类中的受保护成员视为公共的，目的是为了实现安全、文档和兼容性分析。</span><span class="sxs-lookup"><span data-stu-id="2cc90-108">✔️ DO treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>

 <span data-ttu-id="2cc90-109">任何人都可以从类继承并访问受保护的成员。</span><span class="sxs-lookup"><span data-stu-id="2cc90-109">Anyone can inherit from a class and access the protected members.</span></span>

 <span data-ttu-id="2cc90-110">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="2cc90-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="2cc90-111">\*在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。</span><span class="sxs-lookup"><span data-stu-id="2cc90-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="2cc90-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cc90-112">See also</span></span>

- [<span data-ttu-id="2cc90-113">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="2cc90-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="2cc90-114">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="2cc90-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
