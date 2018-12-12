---
title: 成员重载
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: KrzysztofCwalina
ms.openlocfilehash: 93b294c4b535e015c7f4b021e0f950f038a60361
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152430"
---
# <a name="member-overloading"></a><span data-ttu-id="25ae6-102">成员重载</span><span class="sxs-lookup"><span data-stu-id="25ae6-102">Member Overloading</span></span>
<span data-ttu-id="25ae6-103">成员重载意味着创建两个或多个成员上的相同类型的区别只体现在数量或类型参数，但具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="25ae6-103">Member overloading means creating two or more members on the same type that differ only in the number or type of parameters but have the same name.</span></span> <span data-ttu-id="25ae6-104">例如，在以下内容，`WriteLine`重载方法：</span><span class="sxs-lookup"><span data-stu-id="25ae6-104">For example, in the following, the `WriteLine` method is overloaded:</span></span>  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 <span data-ttu-id="25ae6-105">方法、 构造函数和索引的属性可以具有参数，因为只有这些成员可以进行重载。</span><span class="sxs-lookup"><span data-stu-id="25ae6-105">Because only methods, constructors, and indexed properties can have parameters, only those members can be overloaded.</span></span>  
  
 <span data-ttu-id="25ae6-106">重载是用于提高可用性、 生产力和可重用库的可读性最重要的技术之一。</span><span class="sxs-lookup"><span data-stu-id="25ae6-106">Overloading is one of the most important techniques for improving usability, productivity, and readability of reusable libraries.</span></span> <span data-ttu-id="25ae6-107">重载的参数数量，使可能提供更简单的构造函数和方法的版本。</span><span class="sxs-lookup"><span data-stu-id="25ae6-107">Overloading on the number of parameters makes it possible to provide simpler versions of constructors and methods.</span></span> <span data-ttu-id="25ae6-108">重载参数类型，使得可以使用相同的成员执行相同操作在所选的一组不同类型的成员名称。</span><span class="sxs-lookup"><span data-stu-id="25ae6-108">Overloading on the parameter type makes it possible to use the same member name for members performing identical operations on a selected set of different types.</span></span>  
  
 <span data-ttu-id="25ae6-109">**✓ DO** 尝试使用描述性的参数名称以指示较短的重载使用的默认值。</span><span class="sxs-lookup"><span data-stu-id="25ae6-109">**✓ DO** try to use descriptive parameter names to indicate the default used by shorter overloads.</span></span>  
  
 <span data-ttu-id="25ae6-110">**X AVOID** 随意更改重载中的参数名称。</span><span class="sxs-lookup"><span data-stu-id="25ae6-110">**X AVOID** arbitrarily varying parameter names in overloads.</span></span> <span data-ttu-id="25ae6-111">如果某一重载中的参数表示相同的输入中的另一个重载的参数，参数应具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="25ae6-111">If a parameter in one overload represents the same input as a parameter in another overload, the parameters should have the same name.</span></span>  
  
 <span data-ttu-id="25ae6-112">**X AVOID** 在排序中的参数中不一致状态重载成员。</span><span class="sxs-lookup"><span data-stu-id="25ae6-112">**X AVOID** being inconsistent in the ordering of parameters in overloaded members.</span></span> <span data-ttu-id="25ae6-113">具有相同名称的参数应出现在相同位置中所有重载。</span><span class="sxs-lookup"><span data-stu-id="25ae6-113">Parameters with the same name should appear in the same position in all overloads.</span></span>  
  
 <span data-ttu-id="25ae6-114">**✓ DO** 使只有最长的重载成为虚方法 （如果可扩展性是必需的）。</span><span class="sxs-lookup"><span data-stu-id="25ae6-114">**✓ DO** make only the longest overload virtual (if extensibility is required).</span></span> <span data-ttu-id="25ae6-115">只需较短的重载应调用通过到较长的重载。</span><span class="sxs-lookup"><span data-stu-id="25ae6-115">Shorter overloads should simply call through to a longer overload.</span></span>  
  
 <span data-ttu-id="25ae6-116">**X DO NOT** 使用`ref`或`out`修饰符来重载成员。</span><span class="sxs-lookup"><span data-stu-id="25ae6-116">**X DO NOT** use `ref` or `out` modifiers to overload members.</span></span>  
  
 <span data-ttu-id="25ae6-117">某些语言无法解析对此类重载的调用。</span><span class="sxs-lookup"><span data-stu-id="25ae6-117">Some languages cannot resolve calls to overloads like this.</span></span> <span data-ttu-id="25ae6-118">此外，此类重载通常具有完全不同的语义，可能不应重载，但两个单独的方法相反。</span><span class="sxs-lookup"><span data-stu-id="25ae6-118">In addition, such overloads usually have completely different semantics and probably should not be overloads but two separate methods instead.</span></span>  
  
 <span data-ttu-id="25ae6-119">**X DO NOT** 具有重载随着在相同的位置以及相似类型的参数，而使用不同的语义。</span><span class="sxs-lookup"><span data-stu-id="25ae6-119">**X DO NOT** have overloads with parameters at the same position and similar types yet with different semantics.</span></span>  
  
 <span data-ttu-id="25ae6-120">**✓ DO** 允许`null`要为可选自变量传递。</span><span class="sxs-lookup"><span data-stu-id="25ae6-120">**✓ DO**  allow `null` to be passed for optional arguments.</span></span>  
  
 <span data-ttu-id="25ae6-121">**✓ DO** 使用重载，而不是定义具有默认自变量的成员的成员。</span><span class="sxs-lookup"><span data-stu-id="25ae6-121">**✓ DO** use member overloading rather than defining members with default arguments.</span></span>  
  
 <span data-ttu-id="25ae6-122">默认自变量不符合 CLS。</span><span class="sxs-lookup"><span data-stu-id="25ae6-122">Default arguments are not CLS compliant.</span></span>  
  
 <span data-ttu-id="25ae6-123">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="25ae6-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="25ae6-124">*通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*</span><span class="sxs-lookup"><span data-stu-id="25ae6-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25ae6-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="25ae6-125">See also</span></span>

- [<span data-ttu-id="25ae6-126">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="25ae6-126">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="25ae6-127">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="25ae6-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
