---
title: 相等运算符
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
author: KrzysztofCwalina
ms.openlocfilehash: ef1a0aff1ac59434d9d9a6f0371bf236f637050e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61960326"
---
# <a name="equality-operators"></a><span data-ttu-id="efd15-102">相等运算符</span><span class="sxs-lookup"><span data-stu-id="efd15-102">Equality Operators</span></span>
<span data-ttu-id="efd15-103">本部分讨论了重载相等运算符并将 `operator==` 和 `operator!=` 引用为相等运算符。</span><span class="sxs-lookup"><span data-stu-id="efd15-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>  
  
 <span data-ttu-id="efd15-104">**X 请勿**重载这两个相等运算符的任意一个。</span><span class="sxs-lookup"><span data-stu-id="efd15-104">**X DO NOT** overload one of the equality operators and not the other.</span></span>  
  
 <span data-ttu-id="efd15-105">**✓ 请确**保 <xref:System.Object.Equals%2A?displayProperty=nameWithType> 和相等运算符具有完全相同的语义和类似的性能特性。</span><span class="sxs-lookup"><span data-stu-id="efd15-105">**✓ DO** ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>  
  
 <span data-ttu-id="efd15-106">这通常意味着，在重载相等运算符时需要替代 `Object.Equals`。</span><span class="sxs-lookup"><span data-stu-id="efd15-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>  
  
 <span data-ttu-id="efd15-107">**X 避免**从等式运算符中引发异常。</span><span class="sxs-lookup"><span data-stu-id="efd15-107">**X AVOID** throwing exceptions from equality operators.</span></span>  
  
 <span data-ttu-id="efd15-108">例如，如果其中一个参数为 null，则返回 false，而不是引发 `NullReferenceException`。</span><span class="sxs-lookup"><span data-stu-id="efd15-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>  
  
## <a name="equality-operators-on-value-types"></a><span data-ttu-id="efd15-109">值类型的等式运算符</span><span class="sxs-lookup"><span data-stu-id="efd15-109">Equality Operators on Value Types</span></span>  
 <span data-ttu-id="efd15-110">**✓ 如果**等式有意义，请对值类型重载等式运算符。</span><span class="sxs-lookup"><span data-stu-id="efd15-110">**✓ DO** overload the equality operators on value types, if equality is meaningful.</span></span>  
  
 <span data-ttu-id="efd15-111">在大多数编程语言中，值类型没有 `operator==` 的默认实现。</span><span class="sxs-lookup"><span data-stu-id="efd15-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>  
  
## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="efd15-112">引用类型的等式运算符</span><span class="sxs-lookup"><span data-stu-id="efd15-112">Equality Operators on Reference Types</span></span>  
 <span data-ttu-id="efd15-113">**X 避免**对可变引用类型重载等式运算符。</span><span class="sxs-lookup"><span data-stu-id="efd15-113">**X AVOID** overloading equality operators on mutable reference types.</span></span>  
  
 <span data-ttu-id="efd15-114">许多语言都具有针对引用类型的内置等式运算符。</span><span class="sxs-lookup"><span data-stu-id="efd15-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="efd15-115">内置运算符通常实现引用等式，当默认行更改为值等式时，许多开发人员都会感到惊讶。</span><span class="sxs-lookup"><span data-stu-id="efd15-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>  
  
 <span data-ttu-id="efd15-116">对于不可变的引用类型来说，此问题可得到缓解，因为不可变性使得引用等式和值等式之间的区别更难以被注意到。</span><span class="sxs-lookup"><span data-stu-id="efd15-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>  
  
 <span data-ttu-id="efd15-117">**X 如果**实现速度明显慢于引用等式，请避免对引用类型重载等式运算符。</span><span class="sxs-lookup"><span data-stu-id="efd15-117">**X AVOID** overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>  
  
 <span data-ttu-id="efd15-118">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="efd15-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="efd15-119">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="efd15-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efd15-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="efd15-120">See also</span></span>

- [<span data-ttu-id="efd15-121">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="efd15-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="efd15-122">使用准则</span><span class="sxs-lookup"><span data-stu-id="efd15-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
