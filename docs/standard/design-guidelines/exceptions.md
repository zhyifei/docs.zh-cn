---
title: "异常设计准则"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 30ee456632070f778d51d7fb40475a795a0f620b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="cccf3-102">异常设计准则</span><span class="sxs-lookup"><span data-stu-id="cccf3-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="cccf3-103">异常处理有很多优于基于返回值的错误报告。</span><span class="sxs-lookup"><span data-stu-id="cccf3-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="cccf3-104">设计良好的框架可帮助应用程序开发人员实现的异常的优点。</span><span class="sxs-lookup"><span data-stu-id="cccf3-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="cccf3-105">本部分讨论的异常的好处，并显示有关高效使用它们的准则。</span><span class="sxs-lookup"><span data-stu-id="cccf3-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cccf3-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="cccf3-106">In This Section</span></span>  
 [<span data-ttu-id="cccf3-107">异常引发</span><span class="sxs-lookup"><span data-stu-id="cccf3-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="cccf3-108">使用标准异常类型</span><span class="sxs-lookup"><span data-stu-id="cccf3-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="cccf3-109">异常和性能</span><span class="sxs-lookup"><span data-stu-id="cccf3-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="cccf3-110">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="cccf3-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="cccf3-111">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="cccf3-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cccf3-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cccf3-112">See Also</span></span>  
 [<span data-ttu-id="cccf3-113">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="cccf3-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
