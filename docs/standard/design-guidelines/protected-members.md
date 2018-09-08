---
title: 受保护的成员
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4574dffc3f9dd1b60d655bfde33a4ddc1a81d350
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44140939"
---
# <a name="protected-members"></a><span data-ttu-id="c9e49-102">受保护的成员</span><span class="sxs-lookup"><span data-stu-id="c9e49-102">Protected Members</span></span>
<span data-ttu-id="c9e49-103">受保护的成员本身不提供任何可扩展性，但它们会使通过子类化可扩展性功能更强大。</span><span class="sxs-lookup"><span data-stu-id="c9e49-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="c9e49-104">它们可以用于公开高级自定义选项，而不必要地复杂化的主要公共接口。</span><span class="sxs-lookup"><span data-stu-id="c9e49-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="c9e49-105">框架设计器需要要小心使用受保护的成员，因为"保护"的名称可以提供安全的错觉。</span><span class="sxs-lookup"><span data-stu-id="c9e49-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="c9e49-106">任何人都能够子类未密封的类并访问受保护成员和公共成员使用的防御性编码做法适用于受保护的成员的因此完全相同。</span><span class="sxs-lookup"><span data-stu-id="c9e49-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="c9e49-107">**✓ CONSIDER** 使用受保护的高级自定义的成员。</span><span class="sxs-lookup"><span data-stu-id="c9e49-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="c9e49-108">**✓ DO** 处理未密封类作为公共以便进行安全、 文档和兼容性分析中的受保护的成员。</span><span class="sxs-lookup"><span data-stu-id="c9e49-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="c9e49-109">任何人都可以从类继承，并且可以访问受保护的成员。</span><span class="sxs-lookup"><span data-stu-id="c9e49-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="c9e49-110">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="c9e49-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c9e49-111">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="c9e49-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e49-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9e49-112">See also</span></span>

- [<span data-ttu-id="c9e49-113">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="c9e49-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="c9e49-114">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="c9e49-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
