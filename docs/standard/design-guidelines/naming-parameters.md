---
title: 命名参数
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
author: KrzysztofCwalina
ms.openlocfilehash: 0e5b33839372e303b96bd6b84949f9a82da2f689
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026298"
---
# <a name="naming-parameters"></a><span data-ttu-id="48db9-102">命名参数</span><span class="sxs-lookup"><span data-stu-id="48db9-102">Naming Parameters</span></span>
<span data-ttu-id="48db9-103">除了提升可读性这一明显目的外，遵循参数名称准则的一个重要原因是文档和设计器（可视化设计工具在提供 Intellisense 和类浏览功能时）中会显示参数。
</span><span class="sxs-lookup"><span data-stu-id="48db9-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>  
  
 <span data-ttu-id="48db9-104">**✓ 务必** 在参数名称中使用 camelCasing。</span><span class="sxs-lookup"><span data-stu-id="48db9-104">**✓ DO** use camelCasing in parameter names.</span></span>  
  
 <span data-ttu-id="48db9-105">**✓ 务必** 使用描述性参数名称。</span><span class="sxs-lookup"><span data-stu-id="48db9-105">**✓ DO** use descriptive parameter names.</span></span>  
  
 <span data-ttu-id="48db9-106">**✓ 考虑** 使用基于参数含义而非参数类型的名称。</span><span class="sxs-lookup"><span data-stu-id="48db9-106">**✓ CONSIDER** using names based on a parameter’s meaning rather than the parameter’s type.</span></span>  
  
### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="48db9-107">命名运算符重载参数</span><span class="sxs-lookup"><span data-stu-id="48db9-107">Naming Operator Overload Parameters</span></span>  
 <span data-ttu-id="48db9-108">**✓ 务必执行** ：如果参数没有意义，请为二元运算符重载参数名称使用 `left` 和 `right`。</span><span class="sxs-lookup"><span data-stu-id="48db9-108">**✓ DO** use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="48db9-109">**✓ 务必执行** ：如果参数没有意义，请为一元运算符重载参数名称使用 `value`。</span><span class="sxs-lookup"><span data-stu-id="48db9-109">**✓ DO** use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="48db9-110">**✓ 考虑** 为运算符重载参数使用有意义的名称（如果这样做很有用的话）。</span><span class="sxs-lookup"><span data-stu-id="48db9-110">**✓ CONSIDER** meaningful names for operator overload parameters if doing so adds significant value.</span></span>  
  
 <span data-ttu-id="48db9-111">**X DO NOT要** 在运算符重载参数名称中使用缩写形式或数值索引。</span><span class="sxs-lookup"><span data-stu-id="48db9-111">**X DO NOT** use abbreviations or numeric indices for operator overload parameter names.</span></span>  
  
 <span data-ttu-id="48db9-112">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="48db9-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="48db9-113">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="48db9-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48db9-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="48db9-114">See also</span></span>

- [<span data-ttu-id="48db9-115">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="48db9-115">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="48db9-116">命名规则</span><span class="sxs-lookup"><span data-stu-id="48db9-116">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
