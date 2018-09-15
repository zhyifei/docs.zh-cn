---
title: 数组
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ac7e28c3172f2ed68d402e1d04a1664644c7f25
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2018
ms.locfileid: "45658712"
---
# <a name="arrays"></a><span data-ttu-id="97563-102">数组</span><span class="sxs-lookup"><span data-stu-id="97563-102">Arrays</span></span>
<span data-ttu-id="97563-103">**✓ DO** 喜欢使用通过公共 Api 中的数组的集合。</span><span class="sxs-lookup"><span data-stu-id="97563-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="97563-104">[集合](../../../docs/standard/design-guidelines/guidelines-for-collections.md)部分提供有关如何集合和数组之间进行选择的详细信息。</span><span class="sxs-lookup"><span data-stu-id="97563-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="97563-105">**X DO NOT** 使用只读数组字段。</span><span class="sxs-lookup"><span data-stu-id="97563-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="97563-106">该字段本身是只读的无法更改，但可以更改数组中的元素。</span><span class="sxs-lookup"><span data-stu-id="97563-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="97563-107">**✓ CONSIDER** 使用交错的数组而不多维数组。</span><span class="sxs-lookup"><span data-stu-id="97563-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="97563-108">交错的数组是具有也存在数组的元素的数组。</span><span class="sxs-lookup"><span data-stu-id="97563-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="97563-109">构成元素的数组可以是不同的大小，以与多维数组相比某些集的数据 （例如，稀疏矩阵） 的不太浪费空间。</span><span class="sxs-lookup"><span data-stu-id="97563-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="97563-110">此外，CLR 优化交错数组的索引操作，因此它们可能会表现出更好的运行时性能在某些情况下。</span><span class="sxs-lookup"><span data-stu-id="97563-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="97563-111">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="97563-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="97563-112">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="97563-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97563-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="97563-113">See also</span></span>

- <xref:System.Array>  
- [<span data-ttu-id="97563-114">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="97563-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="97563-115">使用准则</span><span class="sxs-lookup"><span data-stu-id="97563-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
