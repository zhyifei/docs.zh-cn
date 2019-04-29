---
title: 命名资源
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
author: KrzysztofCwalina
ms.openlocfilehash: 44627aafd9ec779625413a0862412a8f6c408109
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756879"
---
# <a name="naming-resources"></a><span data-ttu-id="25247-102">命名资源</span><span class="sxs-lookup"><span data-stu-id="25247-102">Naming Resources</span></span>
<span data-ttu-id="25247-103">由于可本地化的资源可像属性那样通过某些对象进行引用，因此资源的命名准则与属性准则相似。</span><span class="sxs-lookup"><span data-stu-id="25247-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>  
  
 <span data-ttu-id="25247-104">**✓ 务必** 在资源键中使用 PascalCasing。</span><span class="sxs-lookup"><span data-stu-id="25247-104">**✓ DO** use PascalCasing in resource keys.</span></span>  
  
 <span data-ttu-id="25247-105">**✓ 务必** 提供描述性标识符而非简短标识符。</span><span class="sxs-lookup"><span data-stu-id="25247-105">**✓ DO** provide descriptive rather than short identifiers.</span></span>  
  
 <span data-ttu-id="25247-106">**X DO NOT要** 使用主要 CLR 语言中的语言特定关键字。</span><span class="sxs-lookup"><span data-stu-id="25247-106">**X DO NOT** use language-specific keywords of the main CLR languages.</span></span>  
  
 <span data-ttu-id="25247-107">**✓ 务必执行** ：命名资源中只能使用字母数字字符和下划线。</span><span class="sxs-lookup"><span data-stu-id="25247-107">**✓ DO** use only alphanumeric characters and underscores in naming resources.</span></span>  
  
 <span data-ttu-id="25247-108">**✓ 务必** 为异常消息资源使用以下命名约定。</span><span class="sxs-lookup"><span data-stu-id="25247-108">**✓ DO** use the following naming convention for exception message resources.</span></span>  
  
 <span data-ttu-id="25247-109">资源标识符应为异常类型名称加上异常的短标识符：</span><span class="sxs-lookup"><span data-stu-id="25247-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 <span data-ttu-id="25247-110">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="25247-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="25247-111">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="25247-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25247-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="25247-112">See also</span></span>

- [<span data-ttu-id="25247-113">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="25247-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="25247-114">命名规则</span><span class="sxs-lookup"><span data-stu-id="25247-114">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
