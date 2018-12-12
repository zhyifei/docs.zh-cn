---
title: 异常设计准则
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
author: KrzysztofCwalina
ms.openlocfilehash: 60c3d25138c224f5eabf44d06b6c9a8373eb5f96
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153185"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="15fab-102">异常设计准则</span><span class="sxs-lookup"><span data-stu-id="15fab-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="15fab-103">与基于返回值的错误报告相比，异常处理具有许多优点。</span><span class="sxs-lookup"><span data-stu-id="15fab-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="15fab-104">良好的框架设计有助于应用程序开发人员理解异常的优势。</span><span class="sxs-lookup"><span data-stu-id="15fab-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="15fab-105">本节讨论异常的优势，并提供如何有效使用它们的准则。</span><span class="sxs-lookup"><span data-stu-id="15fab-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="15fab-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="15fab-106">In This Section</span></span>  
 [<span data-ttu-id="15fab-107">引发异常</span><span class="sxs-lookup"><span data-stu-id="15fab-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="15fab-108">使用标准异常类型</span><span class="sxs-lookup"><span data-stu-id="15fab-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="15fab-109">异常和性能</span><span class="sxs-lookup"><span data-stu-id="15fab-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="15fab-110">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="15fab-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="15fab-111">*通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*</span><span class="sxs-lookup"><span data-stu-id="15fab-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15fab-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="15fab-112">See also</span></span>

- [<span data-ttu-id="15fab-113">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="15fab-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
