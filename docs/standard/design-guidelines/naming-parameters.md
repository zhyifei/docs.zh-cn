---
title: 命名参数
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3e5dfe35fd4f2939898acee44764535c6de5fe9e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="naming-parameters"></a><span data-ttu-id="20b6a-102">命名参数</span><span class="sxs-lookup"><span data-stu-id="20b6a-102">Naming Parameters</span></span>
<span data-ttu-id="20b6a-103">超出可读性的明显原因，务必遵循参数名称的指南，因为在可视化设计工具提供了 Intellisense 和浏览功能的类时，参数将显示在文档和设计器。</span><span class="sxs-lookup"><span data-stu-id="20b6a-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>  
  
 <span data-ttu-id="20b6a-104">**✓ 执行**参数名称中使用 camelcasing 大小写约定。</span><span class="sxs-lookup"><span data-stu-id="20b6a-104">**✓ DO** use camelCasing in parameter names.</span></span>  
  
 <span data-ttu-id="20b6a-105">**✓ 执行**使用描述性的参数名称。</span><span class="sxs-lookup"><span data-stu-id="20b6a-105">**✓ DO** use descriptive parameter names.</span></span>  
  
 <span data-ttu-id="20b6a-106">**请考虑 ✓**使用基于参数的含义，而不是参数的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="20b6a-106">**✓ CONSIDER** using names based on a parameter’s meaning rather than the parameter’s type.</span></span>  
  
### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="20b6a-107">命名运算符重载参数</span><span class="sxs-lookup"><span data-stu-id="20b6a-107">Naming Operator Overload Parameters</span></span>  
 <span data-ttu-id="20b6a-108">**✓ 执行**使用`left`和`right`为二元运算符重载参数名称，如果没有给参数的类型没有意义。</span><span class="sxs-lookup"><span data-stu-id="20b6a-108">**✓ DO** use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="20b6a-109">**✓ 执行**使用`value`的一元运算符重载参数名称，如果没有给参数的类型没有意义。</span><span class="sxs-lookup"><span data-stu-id="20b6a-109">**✓ DO** use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="20b6a-110">**请考虑 ✓**有意义的名称，运算符的重载参数，如果这样做会增加巨大的价值。</span><span class="sxs-lookup"><span data-stu-id="20b6a-110">**✓ CONSIDER** meaningful names for operator overload parameters if doing so adds significant value.</span></span>  
  
 <span data-ttu-id="20b6a-111">**X 不**使用缩写或数值索引运算符重载参数名称。</span><span class="sxs-lookup"><span data-stu-id="20b6a-111">**X DO NOT** use abbreviations or numeric indices for operator overload parameter names.</span></span>  
  
 <span data-ttu-id="20b6a-112">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="20b6a-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="20b6a-113">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="20b6a-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20b6a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="20b6a-114">See Also</span></span>  
 [<span data-ttu-id="20b6a-115">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="20b6a-115">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="20b6a-116">命名规则</span><span class="sxs-lookup"><span data-stu-id="20b6a-116">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
