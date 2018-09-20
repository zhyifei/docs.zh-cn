---
title: 相等运算符
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27550a8fd8292029cad9c2e699374a190b1a532e
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45521383"
---
# <a name="equality-operators"></a><span data-ttu-id="b5267-102">相等运算符</span><span class="sxs-lookup"><span data-stu-id="b5267-102">Equality Operators</span></span>
<span data-ttu-id="b5267-103">本部分讨论了重载相等运算符并引用`operator==`和`operator!=`作为相等运算符。</span><span class="sxs-lookup"><span data-stu-id="b5267-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>  
  
 <span data-ttu-id="b5267-104">**X DO NOT** 重载相等运算符和不在其他之一。</span><span class="sxs-lookup"><span data-stu-id="b5267-104">**X DO NOT** overload one of the equality operators and not the other.</span></span>  
  
 <span data-ttu-id="b5267-105">**✓ DO** 确保<xref:System.Object.Equals%2A?displayProperty=nameWithType>和相等运算符具有完全相同的语义和类似的性能特征。</span><span class="sxs-lookup"><span data-stu-id="b5267-105">**✓ DO** ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>  
  
 <span data-ttu-id="b5267-106">这通常意味着`Object.Equals`需要重写时重载相等运算符。</span><span class="sxs-lookup"><span data-stu-id="b5267-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>  
  
 <span data-ttu-id="b5267-107">**X AVOID** 相等运算符从引发异常。</span><span class="sxs-lookup"><span data-stu-id="b5267-107">**X AVOID** throwing exceptions from equality operators.</span></span>  
  
 <span data-ttu-id="b5267-108">例如，如果返回 false 的参数之一为 null 而不是引发`NullReferenceException`。</span><span class="sxs-lookup"><span data-stu-id="b5267-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>  
  
## <a name="equality-operators-on-value-types"></a><span data-ttu-id="b5267-109">有关值类型的相等运算符</span><span class="sxs-lookup"><span data-stu-id="b5267-109">Equality Operators on Value Types</span></span>  
 <span data-ttu-id="b5267-110">**✓ DO** 重载相等运算符的值类型，如果相等是有意义。</span><span class="sxs-lookup"><span data-stu-id="b5267-110">**✓ DO** overload the equality operators on value types, if equality is meaningful.</span></span>  
  
 <span data-ttu-id="b5267-111">在大多数编程语言中，没有默认实现的`operator==`对于值类型。</span><span class="sxs-lookup"><span data-stu-id="b5267-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>  
  
## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="b5267-112">对引用类型的相等运算符</span><span class="sxs-lookup"><span data-stu-id="b5267-112">Equality Operators on Reference Types</span></span>  
 <span data-ttu-id="b5267-113">**X AVOID** 重载相等运算符对可变引用类型。</span><span class="sxs-lookup"><span data-stu-id="b5267-113">**X AVOID** overloading equality operators on mutable reference types.</span></span>  
  
 <span data-ttu-id="b5267-114">许多语言具有引用类型的内置相等运算符。</span><span class="sxs-lookup"><span data-stu-id="b5267-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="b5267-115">内置运算符通常实现引用相等性，并默认行为更改为值相等性时，许多开发人员都很惊讶。</span><span class="sxs-lookup"><span data-stu-id="b5267-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>  
  
 <span data-ttu-id="b5267-116">此问题得到缓解不可变的引用类型，因为不可变性，使得很难注意到引用相等性和值相等性之间的差异。</span><span class="sxs-lookup"><span data-stu-id="b5267-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>  
  
 <span data-ttu-id="b5267-117">**X AVOID** 重载相等运算符对引用类型，如果实现可能会显著慢于引用相等性的。</span><span class="sxs-lookup"><span data-stu-id="b5267-117">**X AVOID** overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>  
  
 <span data-ttu-id="b5267-118">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="b5267-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b5267-119">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="b5267-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5267-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5267-120">See also</span></span>

- [<span data-ttu-id="b5267-121">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="b5267-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="b5267-122">使用准则</span><span class="sxs-lookup"><span data-stu-id="b5267-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
