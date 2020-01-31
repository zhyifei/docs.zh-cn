---
title: 命名参数
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
ms.openlocfilehash: ebe2e2db4b109057bf576d4e18cfe511c657707e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743826"
---
# <a name="naming-parameters"></a><span data-ttu-id="a0fff-102">命名参数</span><span class="sxs-lookup"><span data-stu-id="a0fff-102">Naming Parameters</span></span>
<span data-ttu-id="a0fff-103">除了提升可读性这一明显目的外，遵循参数名称准则的一个重要原因是文档和设计器（可视化设计工具在提供 Intellisense 和类浏览功能时）中会显示参数。</span><span class="sxs-lookup"><span data-stu-id="a0fff-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>

 <span data-ttu-id="a0fff-104">✔️在参数名称中使用 camelCasing。</span><span class="sxs-lookup"><span data-stu-id="a0fff-104">✔️ DO use camelCasing in parameter names.</span></span>

 <span data-ttu-id="a0fff-105">✔️使用描述性参数名称。</span><span class="sxs-lookup"><span data-stu-id="a0fff-105">✔️ DO use descriptive parameter names.</span></span>

 <span data-ttu-id="a0fff-106">✔️考虑使用基于参数含义而不是参数类型的名称。</span><span class="sxs-lookup"><span data-stu-id="a0fff-106">✔️ CONSIDER using names based on a parameter’s meaning rather than the parameter’s type.</span></span>

### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="a0fff-107">命名运算符重载参数</span><span class="sxs-lookup"><span data-stu-id="a0fff-107">Naming Operator Overload Parameters</span></span>
 <span data-ttu-id="a0fff-108">✔️如果参数没有任何意义，请将 `left` 和 `right` 用于二元运算符重载参数名称。</span><span class="sxs-lookup"><span data-stu-id="a0fff-108">✔️ DO use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>

 <span data-ttu-id="a0fff-109">如果参数没有任何意义，✔️确实将 `value` 用于一元运算符重载参数名称。</span><span class="sxs-lookup"><span data-stu-id="a0fff-109">✔️ DO use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>

 <span data-ttu-id="a0fff-110">✔️考虑运算符重载参数有意义的名称，如果这样做会增加重要值。</span><span class="sxs-lookup"><span data-stu-id="a0fff-110">✔️ CONSIDER meaningful names for operator overload parameters if doing so adds significant value.</span></span>

 <span data-ttu-id="a0fff-111">❌ 不要对运算符重载参数名称使用缩写或数字索引。</span><span class="sxs-lookup"><span data-stu-id="a0fff-111">❌ DO NOT use abbreviations or numeric indices for operator overload parameter names.</span></span>

 <span data-ttu-id="a0fff-112">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="a0fff-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="a0fff-113">\*在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。</span><span class="sxs-lookup"><span data-stu-id="a0fff-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="a0fff-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0fff-114">See also</span></span>

- [<span data-ttu-id="a0fff-115">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="a0fff-115">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="a0fff-116">命名规则</span><span class="sxs-lookup"><span data-stu-id="a0fff-116">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
