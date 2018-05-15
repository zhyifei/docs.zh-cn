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
ms.openlocfilehash: 2945ead7c22b759ce88f6585e2254e9bc540a7ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="arrays"></a><span data-ttu-id="f17f9-102">数组</span><span class="sxs-lookup"><span data-stu-id="f17f9-102">Arrays</span></span>
<span data-ttu-id="f17f9-103">**✓ 执行**喜欢使用通过公共 Api 中的数组的集合。</span><span class="sxs-lookup"><span data-stu-id="f17f9-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="f17f9-104">[集合](../../../docs/standard/design-guidelines/guidelines-for-collections.md)部分提供有关如何选择之间集合和数组的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f17f9-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="f17f9-105">**X 不**使用只读数组字段。</span><span class="sxs-lookup"><span data-stu-id="f17f9-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="f17f9-106">字段自身是只读的和不能更改，但可以更改数组中的元素。</span><span class="sxs-lookup"><span data-stu-id="f17f9-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="f17f9-107">**请考虑 ✓**使用交错的数组而不多维数组。</span><span class="sxs-lookup"><span data-stu-id="f17f9-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="f17f9-108">交错的数组是包含也是数组的元素的数组。</span><span class="sxs-lookup"><span data-stu-id="f17f9-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="f17f9-109">构成元素的数组可以是不同的大小，以减少浪费空间某些集的数据 （例如，稀疏矩阵） 相比多维数组。</span><span class="sxs-lookup"><span data-stu-id="f17f9-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="f17f9-110">此外，CLR 优化对交错数组的索引操作，以便它们可能会在某些情况下更好的运行时性能表现出。</span><span class="sxs-lookup"><span data-stu-id="f17f9-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="f17f9-111">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="f17f9-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f17f9-112">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="f17f9-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f17f9-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f17f9-113">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="f17f9-114">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="f17f9-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="f17f9-115">使用准则</span><span class="sxs-lookup"><span data-stu-id="f17f9-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
