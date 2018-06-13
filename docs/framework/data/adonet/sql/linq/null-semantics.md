---
title: Null 语义
ms.date: 03/30/2017
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
ms.openlocfilehash: b80d198b81e28b0fe1d0107dd04a9694c3069868
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357697"
---
# <a name="null-semantics"></a><span data-ttu-id="6bdaf-102">Null 语义</span><span class="sxs-lookup"><span data-stu-id="6bdaf-102">Null Semantics</span></span>
<span data-ttu-id="6bdaf-103">下表提供指向各个部分的[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]文档其中`null`(`Nothing`在 Visual Basic 中) 问题进行讨论。</span><span class="sxs-lookup"><span data-stu-id="6bdaf-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in Visual Basic) issues are discussed.</span></span>  
  
|<span data-ttu-id="6bdaf-104">主题</span><span class="sxs-lookup"><span data-stu-id="6bdaf-104">Topic</span></span>|<span data-ttu-id="6bdaf-105">描述</span><span class="sxs-lookup"><span data-stu-id="6bdaf-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="6bdaf-106">SQL-CLR 类型不匹配</span><span class="sxs-lookup"><span data-stu-id="6bdaf-106">SQL-CLR Type Mismatches</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|<span data-ttu-id="6bdaf-107">本主题的"Null 语义"部分包括以下方面讨论的三态 SQL Boolean 与两态公共语言运行时 (CLR) <xref:System.Boolean>，文本`Nothing`(Visual Basic 中) 和`null`(C#) 以及其他类似问题。</span><span class="sxs-lookup"><span data-stu-id="6bdaf-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` (Visual Basic) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="6bdaf-108">标准查询运算符转换</span><span class="sxs-lookup"><span data-stu-id="6bdaf-108">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|<span data-ttu-id="6bdaf-109">本主题的“Null 语义”部分介绍 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]中的 null 比较语义。</span><span class="sxs-lookup"><span data-stu-id="6bdaf-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="6bdaf-110">System.String 方法</span><span class="sxs-lookup"><span data-stu-id="6bdaf-110">System.String Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|<span data-ttu-id="6bdaf-111">本主题的“与 .NET 的差异”部分说明从 <xref:System.String.LastIndexOf%2A> 返回 0 为何意味着字符串为 null 或找到的位置为 0。</span><span class="sxs-lookup"><span data-stu-id="6bdaf-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="6bdaf-112">计算数值序列中值的和</span><span class="sxs-lookup"><span data-stu-id="6bdaf-112">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="6bdaf-113">描述如何<xref:System.Linq.Enumerable.Sum%2A>运算符的计算结果为`null`(`Nothing`在 Visual Basic 中) 而不是 0 一个序列，其中只包含 null 或空序列。</span><span class="sxs-lookup"><span data-stu-id="6bdaf-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in Visual Basic) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6bdaf-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bdaf-114">See Also</span></span>  
 [<span data-ttu-id="6bdaf-115">数据类型和函数</span><span class="sxs-lookup"><span data-stu-id="6bdaf-115">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
