---
title: 相等运算符
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
caps.latest.revision: 13
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cd740e9b7a5d38229b3564bfeca003fc4d189624
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="equality-operators"></a><span data-ttu-id="9c6ea-102">相等运算符</span><span class="sxs-lookup"><span data-stu-id="9c6ea-102">Equality Operators</span></span>
<span data-ttu-id="9c6ea-103">本部分讨论重载相等运算符并引用`operator==`和`operator!=`作为相等运算符。</span><span class="sxs-lookup"><span data-stu-id="9c6ea-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>  
  
 <span data-ttu-id="9c6ea-104">**X 不**重载相等运算符和不在其他之一。</span><span class="sxs-lookup"><span data-stu-id="9c6ea-104">**X DO NOT** overload one of the equality operators and not the other.</span></span>  
  
 <span data-ttu-id="9c6ea-105">**✓ 执行**确保<xref:System.Object.Equals%2A?displayProperty=nameWithType>和相等运算符具有完全相同的语义和类似的性能特征。</span><span class="sxs-lookup"><span data-stu-id="9c6ea-105">**✓ DO** ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>  
  
 <span data-ttu-id="9c6ea-106">这通常意味着`Object.Equals`需要时重载相等运算符时被重写。</span><span class="sxs-lookup"><span data-stu-id="9c6ea-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>  
  
 <span data-ttu-id="9c6ea-107">**请避免 x**相等运算符从引发异常。</span><span class="sxs-lookup"><span data-stu-id="9c6ea-107">**X AVOID** throwing exceptions from equality operators.</span></span>  
  
 <span data-ttu-id="9c6ea-108">例如，返回 false 如果的自变量之一为 null 而不是引发`NullReferenceException`。</span><span class="sxs-lookup"><span data-stu-id="9c6ea-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>  
  
## <a name="equality-operators-on-value-types"></a><span data-ttu-id="9c6ea-109">有关值类型的相等运算符</span><span class="sxs-lookup"><span data-stu-id="9c6ea-109">Equality Operators on Value Types</span></span>  
 <span data-ttu-id="9c6ea-110">**✓ 执行**重载相等运算符的值类型，如果相等是有意义。</span><span class="sxs-lookup"><span data-stu-id="9c6ea-110">**✓ DO** overload the equality operators on value types, if equality is meaningful.</span></span>  
  
 <span data-ttu-id="9c6ea-111">在大多数编程语言中，没有默认实现的`operator==`为值类型。</span><span class="sxs-lookup"><span data-stu-id="9c6ea-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>  
  
## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="9c6ea-112">对引用类型的相等运算符</span><span class="sxs-lookup"><span data-stu-id="9c6ea-112">Equality Operators on Reference Types</span></span>  
 <span data-ttu-id="9c6ea-113">**请避免 x**重载相等运算符对可变引用类型。</span><span class="sxs-lookup"><span data-stu-id="9c6ea-113">**X AVOID** overloading equality operators on mutable reference types.</span></span>  
  
 <span data-ttu-id="9c6ea-114">许多语言都有内置的相等运算符对于引用类型。</span><span class="sxs-lookup"><span data-stu-id="9c6ea-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="9c6ea-115">内置运算符通常实现引用相等性，并更改为值相等的默认行为时，许多开发人员感到惊奇多功能。</span><span class="sxs-lookup"><span data-stu-id="9c6ea-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>  
  
 <span data-ttu-id="9c6ea-116">因为不可变性使困难得多，需要注意引用相等性和值相等性之间的差异，用于不可变的引用类型缓解此问题。</span><span class="sxs-lookup"><span data-stu-id="9c6ea-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>  
  
 <span data-ttu-id="9c6ea-117">**请避免 x**重载相等运算符对引用类型，如果实现可能会显著慢于引用相等性的。</span><span class="sxs-lookup"><span data-stu-id="9c6ea-117">**X AVOID** overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>  
  
 <span data-ttu-id="9c6ea-118">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="9c6ea-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9c6ea-119">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="9c6ea-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c6ea-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c6ea-120">See Also</span></span>  
 [<span data-ttu-id="9c6ea-121">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="9c6ea-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="9c6ea-122">使用准则</span><span class="sxs-lookup"><span data-stu-id="9c6ea-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
