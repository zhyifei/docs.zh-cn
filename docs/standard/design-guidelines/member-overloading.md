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
ms.openlocfilehash: e7decab042dd1ee36beacb18956e175196cd112c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709278"
---
# <a name="member-overloading"></a><span data-ttu-id="554a7-102">成员重载</span><span class="sxs-lookup"><span data-stu-id="554a7-102">Member Overloading</span></span>
<span data-ttu-id="554a7-103">成员重载意味着在同一类型上创建两个或多个成员，这些成员仅在参数的数量或类型中不同，但具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="554a7-103">Member overloading means creating two or more members on the same type that differ only in the number or type of parameters but have the same name.</span></span> <span data-ttu-id="554a7-104">例如，在下面的中，将重载 `WriteLine` 方法：</span><span class="sxs-lookup"><span data-stu-id="554a7-104">For example, in the following, the `WriteLine` method is overloaded:</span></span>  
  
```csharp  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 <span data-ttu-id="554a7-105">由于只有方法、构造函数和索引属性可以有参数，因此只能重载这些成员。</span><span class="sxs-lookup"><span data-stu-id="554a7-105">Because only methods, constructors, and indexed properties can have parameters, only those members can be overloaded.</span></span>  
  
 <span data-ttu-id="554a7-106">重载是提高可重用库的可用性、生产力和可读性的最重要方法之一。</span><span class="sxs-lookup"><span data-stu-id="554a7-106">Overloading is one of the most important techniques for improving usability, productivity, and readability of reusable libraries.</span></span> <span data-ttu-id="554a7-107">参数数量重载使您可以提供更简单的构造函数和方法版本。</span><span class="sxs-lookup"><span data-stu-id="554a7-107">Overloading on the number of parameters makes it possible to provide simpler versions of constructors and methods.</span></span> <span data-ttu-id="554a7-108">使用参数类型的重载，可以为在所选的不同类型集上执行相同操作的成员使用相同的成员名称。</span><span class="sxs-lookup"><span data-stu-id="554a7-108">Overloading on the parameter type makes it possible to use the same member name for members performing identical operations on a selected set of different types.</span></span>  
  
 <span data-ttu-id="554a7-109">**✓ 务必** 尝试使用描述性的参数名称以指示较短的重载使用的默认值。</span><span class="sxs-lookup"><span data-stu-id="554a7-109">**✓ DO** try to use descriptive parameter names to indicate the default used by shorter overloads.</span></span>  
  
 <span data-ttu-id="554a7-110">**X AVOID** 随意更改重载中的参数名称。</span><span class="sxs-lookup"><span data-stu-id="554a7-110">**X AVOID** arbitrarily varying parameter names in overloads.</span></span> <span data-ttu-id="554a7-111">如果一个重载中的参数表示与另一个重载中的参数相同的输入，则这些参数应具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="554a7-111">If a parameter in one overload represents the same input as a parameter in another overload, the parameters should have the same name.</span></span>  
  
 <span data-ttu-id="554a7-112">**X 避免** 在排序中的参数中不一致状态重载成员。</span><span class="sxs-lookup"><span data-stu-id="554a7-112">**X AVOID** being inconsistent in the ordering of parameters in overloaded members.</span></span> <span data-ttu-id="554a7-113">具有相同名称的参数应出现在所有重载的同一位置。</span><span class="sxs-lookup"><span data-stu-id="554a7-113">Parameters with the same name should appear in the same position in all overloads.</span></span>  
  
 <span data-ttu-id="554a7-114">**✓ DO** 使只有最长的重载成为虚方法 （如果可扩展性是必需的）。</span><span class="sxs-lookup"><span data-stu-id="554a7-114">**✓ DO** make only the longest overload virtual (if extensibility is required).</span></span> <span data-ttu-id="554a7-115">更短的重载只需调用更长的重载。</span><span class="sxs-lookup"><span data-stu-id="554a7-115">Shorter overloads should simply call through to a longer overload.</span></span>  
  
 <span data-ttu-id="554a7-116">**X 切忌** 使用`ref`或`out`修饰符来重载成员。</span><span class="sxs-lookup"><span data-stu-id="554a7-116">**X DO NOT** use `ref` or `out` modifiers to overload members.</span></span>  
  
 <span data-ttu-id="554a7-117">某些语言无法解析对重载的调用。</span><span class="sxs-lookup"><span data-stu-id="554a7-117">Some languages cannot resolve calls to overloads like this.</span></span> <span data-ttu-id="554a7-118">此外，此类重载通常具有完全不同的语义，但可能不应作为重载，而是使用两种不同的方法。</span><span class="sxs-lookup"><span data-stu-id="554a7-118">In addition, such overloads usually have completely different semantics and probably should not be overloads but two separate methods instead.</span></span>  
  
 <span data-ttu-id="554a7-119">**X 切忌** 具有重载随着在相同的位置以及相似类型的参数，而使用不同的语义。</span><span class="sxs-lookup"><span data-stu-id="554a7-119">**X DO NOT** have overloads with parameters at the same position and similar types yet with different semantics.</span></span>  
  
 <span data-ttu-id="554a7-120">**✓ 务必** 允许`null`要为可选自变量传递。</span><span class="sxs-lookup"><span data-stu-id="554a7-120">**✓ DO**  allow `null` to be passed for optional arguments.</span></span>  
  
 <span data-ttu-id="554a7-121">**✓ 务必** 使用重载，而不是定义具有默认自变量的成员的成员。</span><span class="sxs-lookup"><span data-stu-id="554a7-121">**✓ DO** use member overloading rather than defining members with default arguments.</span></span>  
  
 <span data-ttu-id="554a7-122">默认参数不符合 CLS。</span><span class="sxs-lookup"><span data-stu-id="554a7-122">Default arguments are not CLS compliant.</span></span>  
  
 <span data-ttu-id="554a7-123">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="554a7-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="554a7-124">\*在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。</span><span class="sxs-lookup"><span data-stu-id="554a7-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="554a7-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="554a7-125">See also</span></span>

- [<span data-ttu-id="554a7-126">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="554a7-126">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="554a7-127">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="554a7-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
