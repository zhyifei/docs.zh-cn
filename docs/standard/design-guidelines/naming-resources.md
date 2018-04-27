---
title: 命名资源
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b100366952b1f536d187eb72c6d80c86bb3e572e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="naming-resources"></a><span data-ttu-id="39560-102">命名资源</span><span class="sxs-lookup"><span data-stu-id="39560-102">Naming Resources</span></span>
<span data-ttu-id="39560-103">因为可以通过某些对象引用可本地化的资源，就像它们是属性，用于资源的命名准则是类似于属性指南。</span><span class="sxs-lookup"><span data-stu-id="39560-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>  
  
 <span data-ttu-id="39560-104">**✓ 执行**PascalCasing 用资源键。</span><span class="sxs-lookup"><span data-stu-id="39560-104">**✓ DO** use PascalCasing in resource keys.</span></span>  
  
 <span data-ttu-id="39560-105">**✓ 执行**提供描述性而不是短的标识符。</span><span class="sxs-lookup"><span data-stu-id="39560-105">**✓ DO** provide descriptive rather than short identifiers.</span></span>  
  
 <span data-ttu-id="39560-106">**X 不**使用的主要 CLR 语言的语言特定关键字。</span><span class="sxs-lookup"><span data-stu-id="39560-106">**X DO NOT** use language-specific keywords of the main CLR languages.</span></span>  
  
 <span data-ttu-id="39560-107">**✓ 执行**使用仅字母数字字符和下划线在命名资源。</span><span class="sxs-lookup"><span data-stu-id="39560-107">**✓ DO** use only alphanumeric characters and underscores in naming resources.</span></span>  
  
 <span data-ttu-id="39560-108">**✓ 执行**对异常消息资源使用以下命名约定。</span><span class="sxs-lookup"><span data-stu-id="39560-108">**✓ DO** use the following naming convention for exception message resources.</span></span>  
  
 <span data-ttu-id="39560-109">异常类型名称和异常的短标识符，应为资源标识符：</span><span class="sxs-lookup"><span data-stu-id="39560-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 <span data-ttu-id="39560-110">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="39560-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="39560-111">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="39560-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39560-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="39560-112">See Also</span></span>  
 [<span data-ttu-id="39560-113">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="39560-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="39560-114">命名规则</span><span class="sxs-lookup"><span data-stu-id="39560-114">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
