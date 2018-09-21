---
title: 异常设计准则
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51cc5296a7b3f6d75b5e56d6bbc74330fa147848
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46517940"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="24231-102">异常设计准则</span><span class="sxs-lookup"><span data-stu-id="24231-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="24231-103">异常处理有很多优于基于返回值的错误报告。</span><span class="sxs-lookup"><span data-stu-id="24231-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="24231-104">良好的框架设计可帮助应用程序开发人员的好处的异常。</span><span class="sxs-lookup"><span data-stu-id="24231-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="24231-105">本部分讨论其优势的异常，并提供了有效地使用它们的准则。</span><span class="sxs-lookup"><span data-stu-id="24231-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="24231-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="24231-106">In This Section</span></span>  
 [<span data-ttu-id="24231-107">异常引发</span><span class="sxs-lookup"><span data-stu-id="24231-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="24231-108">使用标准异常类型</span><span class="sxs-lookup"><span data-stu-id="24231-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="24231-109">异常和性能</span><span class="sxs-lookup"><span data-stu-id="24231-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="24231-110">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="24231-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="24231-111">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="24231-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24231-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="24231-112">See also</span></span>

- [<span data-ttu-id="24231-113">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="24231-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
