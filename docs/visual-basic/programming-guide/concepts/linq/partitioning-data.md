---
title: "分区数据 (Visual Basic) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9d0df2bc473f48fba4bbb094317166407f7c7ec2
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="partitioning-data-visual-basic"></a><span data-ttu-id="8daa0-102">分区数据 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8daa0-102">Partitioning Data (Visual Basic)</span></span>
<span data-ttu-id="8daa0-103">在 LINQ 中分区是指将输入的序列划分为两个部分，而无需重新排列元素，并返回的部分之一的操作。</span><span class="sxs-lookup"><span data-stu-id="8daa0-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="8daa0-104">下图显示三个不同分区的操作序列的字符的结果。</span><span class="sxs-lookup"><span data-stu-id="8daa0-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="8daa0-105">第一次操作返回序列中的前三个元素。</span><span class="sxs-lookup"><span data-stu-id="8daa0-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="8daa0-106">第二个操作跳过前三个元素，并返回剩余元素。</span><span class="sxs-lookup"><span data-stu-id="8daa0-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="8daa0-107">第三个操作跳过序列中的前两个元素，并返回接下来三个元素。</span><span class="sxs-lookup"><span data-stu-id="8daa0-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 <span data-ttu-id="8daa0-108">![LINQ 分区操作](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span><span class="sxs-lookup"><span data-stu-id="8daa0-108">![LINQ Partitioning Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span></span>  
  
 <span data-ttu-id="8daa0-109">下一节中列出分区序列的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="8daa0-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="8daa0-110">运算符</span><span class="sxs-lookup"><span data-stu-id="8daa0-110">Operators</span></span>  
  
|<span data-ttu-id="8daa0-111">运算符名称</span><span class="sxs-lookup"><span data-stu-id="8daa0-111">Operator Name</span></span>|<span data-ttu-id="8daa0-112">描述</span><span class="sxs-lookup"><span data-stu-id="8daa0-112">Description</span></span>|<span data-ttu-id="8daa0-113">Visual Basic 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="8daa0-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="8daa0-114">更多信息</span><span class="sxs-lookup"><span data-stu-id="8daa0-114">More Information</span></span>|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="8daa0-115">Skip</span><span class="sxs-lookup"><span data-stu-id="8daa0-115">Skip</span></span>|<span data-ttu-id="8daa0-116">跳过序列中的指定位置之前的元素。</span><span class="sxs-lookup"><span data-stu-id="8daa0-116">Skips elements up to a specified position in a sequence.</span></span>|`Skip`|<span data-ttu-id="8daa0-117"><xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8daa0-117"><xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="8daa0-118"><xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName></xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8daa0-118"><xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="8daa0-119">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="8daa0-119">SkipWhile</span></span>|<span data-ttu-id="8daa0-120">跳过基于谓词的函数，直到某元素不满足条件的元素。</span><span class="sxs-lookup"><span data-stu-id="8daa0-120">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Skip While`|<span data-ttu-id="8daa0-121"><xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName></xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8daa0-121"><xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="8daa0-122"><xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName></xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8daa0-122"><xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="8daa0-123">Take</span><span class="sxs-lookup"><span data-stu-id="8daa0-123">Take</span></span>|<span data-ttu-id="8daa0-124">序列中的指定位置之前提取元素。</span><span class="sxs-lookup"><span data-stu-id="8daa0-124">Takes elements up to a specified position in a sequence.</span></span>|`Take`|<span data-ttu-id="8daa0-125"><xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8daa0-125"><xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="8daa0-126"><xref:System.Linq.Queryable.Take%2A?displayProperty=fullName></xref:System.Linq.Queryable.Take%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8daa0-126"><xref:System.Linq.Queryable.Take%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="8daa0-127">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="8daa0-127">TakeWhile</span></span>|<span data-ttu-id="8daa0-128">采用基于谓词的函数，直到元素不满足条件的元素。</span><span class="sxs-lookup"><span data-stu-id="8daa0-128">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Take While`|<span data-ttu-id="8daa0-129"><xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName></xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8daa0-129"><xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="8daa0-130"><xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName></xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8daa0-130"><xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="8daa0-131">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="8daa0-131">Query Expression Syntax Examples</span></span>  
  
### <a name="skip"></a><span data-ttu-id="8daa0-132">Skip</span><span class="sxs-lookup"><span data-stu-id="8daa0-132">Skip</span></span>  
 <span data-ttu-id="8daa0-133">下面的代码示例使用`Skip`中的子句[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]前要跳过过的字符串数组中的前四个字符串数组中返回剩余的字符串。</span><span class="sxs-lookup"><span data-stu-id="8daa0-133">The following code example uses the `Skip` clause in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span></span>  
  
 <span data-ttu-id="8daa0-134">[!code-vb[CsLINQPartitioning #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8daa0-134">[!code-vb[CsLINQPartitioning#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]</span></span>  
  
### <a name="skipwhile"></a><span data-ttu-id="8daa0-135">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="8daa0-135">SkipWhile</span></span>  
 <span data-ttu-id="8daa0-136">下面的代码示例使用`Skip While`中的子句[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]来跳过该字符串的第一个字母时数组中的字符串为"a"。</span><span class="sxs-lookup"><span data-stu-id="8daa0-136">The following code example uses the `Skip While` clause in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to skip over the strings in an array while the first letter of the string is "a".</span></span> <span data-ttu-id="8daa0-137">返回数组中的剩余的字符串。</span><span class="sxs-lookup"><span data-stu-id="8daa0-137">The remaining strings in the array are returned.</span></span>  
  
 <span data-ttu-id="8daa0-138">[!code-vb[CsLINQPartitioning #&2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8daa0-138">[!code-vb[CsLINQPartitioning#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]</span></span>  
  
### <a name="take"></a><span data-ttu-id="8daa0-139">Take</span><span class="sxs-lookup"><span data-stu-id="8daa0-139">Take</span></span>  
 <span data-ttu-id="8daa0-140">下面的代码示例使用`Take`中的子句[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]可返回的字符串数组中的前两个字符串。</span><span class="sxs-lookup"><span data-stu-id="8daa0-140">The following code example uses the `Take` clause in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to return the first two strings in an array of strings.</span></span>  
  
 <span data-ttu-id="8daa0-141">[!code-vb[CsLINQPartitioning #&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="8daa0-141">[!code-vb[CsLINQPartitioning#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]</span></span>  
  
### <a name="takewhile"></a><span data-ttu-id="8daa0-142">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="8daa0-142">TakeWhile</span></span>  
 <span data-ttu-id="8daa0-143">下面的代码示例使用`Take While`中的子句[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]字符串的长度小于或等于&5; 时从数组中返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="8daa0-143">The following code example uses the `Take While` clause in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to return strings from an array while the length of the string is five or less.</span></span>  
  
 <span data-ttu-id="8daa0-144">[!code-vb[CsLINQPartitioning #&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="8daa0-144">[!code-vb[CsLINQPartitioning#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8daa0-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8daa0-145">See Also</span></span>  
 <span data-ttu-id="8daa0-146"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="8daa0-146"><xref:System.Linq></span></span>   
<span data-ttu-id="8daa0-147"> [标准查询运算符概述 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="8daa0-147"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="8daa0-148"> [Skip 子句](../../../../visual-basic/language-reference/queries/skip-clause.md) </span><span class="sxs-lookup"><span data-stu-id="8daa0-148"> [Skip Clause](../../../../visual-basic/language-reference/queries/skip-clause.md) </span></span>  
<span data-ttu-id="8daa0-149"> [Skip While 子句](../../../../visual-basic/language-reference/queries/skip-while-clause.md) </span><span class="sxs-lookup"><span data-stu-id="8daa0-149"> [Skip While Clause](../../../../visual-basic/language-reference/queries/skip-while-clause.md) </span></span>  
<span data-ttu-id="8daa0-150"> [Take 子句](../../../../visual-basic/language-reference/queries/take-clause.md) </span><span class="sxs-lookup"><span data-stu-id="8daa0-150"> [Take Clause](../../../../visual-basic/language-reference/queries/take-clause.md) </span></span>  
<span data-ttu-id="8daa0-151"> [Take While 子句](../../../../visual-basic/language-reference/queries/take-while-clause.md)</span><span class="sxs-lookup"><span data-stu-id="8daa0-151"> [Take While Clause](../../../../visual-basic/language-reference/queries/take-while-clause.md)</span></span>
