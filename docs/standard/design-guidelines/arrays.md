---
title: 数组
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
author: KrzysztofCwalina
ms.openlocfilehash: dd30cdee0440553a9f955f0b3f4ee420e938b9ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864112"
---
# <a name="arrays"></a><span data-ttu-id="38a0b-102">数组</span><span class="sxs-lookup"><span data-stu-id="38a0b-102">Arrays</span></span>
<span data-ttu-id="38a0b-103">**✓ 务必**在公共 API 中首选使用集合而不是数组。</span><span class="sxs-lookup"><span data-stu-id="38a0b-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="38a0b-104">[集合](../../../docs/standard/design-guidelines/guidelines-for-collections.md)部分提供了有关如何在集合和数组之间进行选择的详细信息。</span><span class="sxs-lookup"><span data-stu-id="38a0b-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="38a0b-105">**X 切忌**使用只读数组字段。</span><span class="sxs-lookup"><span data-stu-id="38a0b-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="38a0b-106">该字段本身是只读的且无法更改，但可以更改数组中的元素。</span><span class="sxs-lookup"><span data-stu-id="38a0b-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="38a0b-107">**✓ 考虑**使用交错数组而不是多维数组。</span><span class="sxs-lookup"><span data-stu-id="38a0b-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="38a0b-108">交错数组是其元素也是数组的一种数组。</span><span class="sxs-lookup"><span data-stu-id="38a0b-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="38a0b-109">构成元素的数组可以具有不同的大小，与多维数组相比，可减少一些数据集（例如，稀疏矩阵）的浪费空间。</span><span class="sxs-lookup"><span data-stu-id="38a0b-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="38a0b-110">此外，CLR 优化了交错数组的索引操作，因此在某些情况下它们可能表现出更好的运行时性能。</span><span class="sxs-lookup"><span data-stu-id="38a0b-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="38a0b-111">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="38a0b-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="38a0b-112">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="38a0b-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a0b-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="38a0b-113">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="38a0b-114">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="38a0b-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="38a0b-115">使用准则</span><span class="sxs-lookup"><span data-stu-id="38a0b-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
