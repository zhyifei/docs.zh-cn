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
ms.openlocfilehash: 95aff35569e58eacfd064609140a29b53e0036da
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743813"
---
# <a name="naming-resources"></a><span data-ttu-id="bf982-102">命名资源</span><span class="sxs-lookup"><span data-stu-id="bf982-102">Naming Resources</span></span>
<span data-ttu-id="bf982-103">由于可本地化的资源可像属性那样通过某些对象进行引用，因此资源的命名准则与属性准则相似。</span><span class="sxs-lookup"><span data-stu-id="bf982-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>

 <span data-ttu-id="bf982-104">✔️在资源键中使用 PascalCasing。</span><span class="sxs-lookup"><span data-stu-id="bf982-104">✔️ DO use PascalCasing in resource keys.</span></span>

 <span data-ttu-id="bf982-105">✔️提供描述性而不是短标识符。</span><span class="sxs-lookup"><span data-stu-id="bf982-105">✔️ DO provide descriptive rather than short identifiers.</span></span>

 <span data-ttu-id="bf982-106">❌ 不使用主要 CLR 语言的特定于语言的关键字。</span><span class="sxs-lookup"><span data-stu-id="bf982-106">❌ DO NOT use language-specific keywords of the main CLR languages.</span></span>

 <span data-ttu-id="bf982-107">✔️在命名资源中仅使用字母数字字符和下划线。</span><span class="sxs-lookup"><span data-stu-id="bf982-107">✔️ DO use only alphanumeric characters and underscores in naming resources.</span></span>

 <span data-ttu-id="bf982-108">✔️对异常消息资源使用以下命名约定。</span><span class="sxs-lookup"><span data-stu-id="bf982-108">✔️ DO use the following naming convention for exception message resources.</span></span>

 <span data-ttu-id="bf982-109">资源标识符应为异常类型名称加上异常的短标识符：</span><span class="sxs-lookup"><span data-stu-id="bf982-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>

 <span data-ttu-id="bf982-110">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span><span class="sxs-lookup"><span data-stu-id="bf982-110">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span></span>
 `ArgumentExceptionFileNameIsMalformed`

 <span data-ttu-id="bf982-111">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="bf982-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="bf982-112">\*在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。</span><span class="sxs-lookup"><span data-stu-id="bf982-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="bf982-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf982-113">See also</span></span>

- [<span data-ttu-id="bf982-114">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="bf982-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="bf982-115">命名规则</span><span class="sxs-lookup"><span data-stu-id="bf982-115">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
