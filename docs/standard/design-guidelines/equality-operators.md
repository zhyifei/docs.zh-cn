---
title: 같음 연산자
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
ms.openlocfilehash: 34fc8eef5270369419b76899f0dbe1ace106caf6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741704"
---
# <a name="equality-operators"></a><span data-ttu-id="a7697-102">같음 연산자</span><span class="sxs-lookup"><span data-stu-id="a7697-102">Equality Operators</span></span>
<span data-ttu-id="a7697-103">本部分讨论了重载相等运算符并将 `operator==` 和 `operator!=` 引用为相等运算符。</span><span class="sxs-lookup"><span data-stu-id="a7697-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>

 <span data-ttu-id="a7697-104">❌ 不要重载某个相等运算符而不是另一个相等运算符。</span><span class="sxs-lookup"><span data-stu-id="a7697-104">❌ DO NOT overload one of the equality operators and not the other.</span></span>

 <span data-ttu-id="a7697-105">✔️确保 <xref:System.Object.Equals%2A?displayProperty=nameWithType> 和相等运算符具有完全相同的语义和类似的性能特征。</span><span class="sxs-lookup"><span data-stu-id="a7697-105">✔️ DO ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>

 <span data-ttu-id="a7697-106">这通常意味着，在重载相等运算符时需要替代 `Object.Equals`。</span><span class="sxs-lookup"><span data-stu-id="a7697-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>

 <span data-ttu-id="a7697-107">❌ 避免从相等运算符引发异常。</span><span class="sxs-lookup"><span data-stu-id="a7697-107">❌ AVOID throwing exceptions from equality operators.</span></span>

 <span data-ttu-id="a7697-108">例如，如果其中一个参数为 null，则返回 false，而不是引发 `NullReferenceException`。</span><span class="sxs-lookup"><span data-stu-id="a7697-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>

## <a name="equality-operators-on-value-types"></a><span data-ttu-id="a7697-109">值类型的等式运算符</span><span class="sxs-lookup"><span data-stu-id="a7697-109">Equality Operators on Value Types</span></span>
 <span data-ttu-id="a7697-110">✔️如果相等性是有意义的，则对值类型重载相等运算符。</span><span class="sxs-lookup"><span data-stu-id="a7697-110">✔️ DO overload the equality operators on value types, if equality is meaningful.</span></span>

 <span data-ttu-id="a7697-111">在大多数编程语言中，值类型没有 `operator==` 的默认实现。</span><span class="sxs-lookup"><span data-stu-id="a7697-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>

## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="a7697-112">引用类型的等式运算符</span><span class="sxs-lookup"><span data-stu-id="a7697-112">Equality Operators on Reference Types</span></span>
 <span data-ttu-id="a7697-113">❌ 避免对可变引用类型重载相等运算符。</span><span class="sxs-lookup"><span data-stu-id="a7697-113">❌ AVOID overloading equality operators on mutable reference types.</span></span>

 <span data-ttu-id="a7697-114">许多语言都具有针对引用类型的内置等式运算符。</span><span class="sxs-lookup"><span data-stu-id="a7697-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="a7697-115">内置运算符通常实现引用等式，当默认行更改为值等式时，许多开发人员都会感到惊讶。</span><span class="sxs-lookup"><span data-stu-id="a7697-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>

 <span data-ttu-id="a7697-116">对于不可变的引用类型来说，此问题可得到缓解，因为不可变性使得引用等式和值等式之间的区别更难以被注意到。</span><span class="sxs-lookup"><span data-stu-id="a7697-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>

 <span data-ttu-id="a7697-117">如果实现的速度远远低于引用相等性，❌ 避免对引用类型重载相等运算符。</span><span class="sxs-lookup"><span data-stu-id="a7697-117">❌ AVOID overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>

 <span data-ttu-id="a7697-118">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="a7697-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="a7697-119">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="a7697-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="a7697-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7697-120">See also</span></span>

- [<span data-ttu-id="a7697-121">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="a7697-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="a7697-122">사용 지침</span><span class="sxs-lookup"><span data-stu-id="a7697-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
