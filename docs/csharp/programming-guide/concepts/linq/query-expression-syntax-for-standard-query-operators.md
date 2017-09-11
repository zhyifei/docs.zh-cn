---
title: "标准查询运算符的查询表达式语法 (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: e1e17ef2-68ff-4c26-b6e2-015668227fa5
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 30e994329234b8bd455f739694e50121bac63d5d
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="query-expression-syntax-for-standard-query-operators-c"></a><span data-ttu-id="024b3-102">标准查询运算符的查询表达式语法 (C#)</span><span class="sxs-lookup"><span data-stu-id="024b3-102">Query Expression Syntax for Standard Query Operators (C#)</span></span>
<span data-ttu-id="024b3-103">某些使用更频繁的标准查询运算符具有专用的 C# 语言关键字语法，使用这些语法可以在查询表达式中调用这些运算符。</span><span class="sxs-lookup"><span data-stu-id="024b3-103">Some of the more frequently used standard query operators have dedicated C# language keyword syntax that enables them to be called as part of a *query expression*.</span></span> <span data-ttu-id="024b3-104">查询表达式是比基于方法的等效项更具可读性的另一种查询表示形式。</span><span class="sxs-lookup"><span data-stu-id="024b3-104">A query expression is a different, more readable form of expressing a query than its *method-based*  equivalent.</span></span> <span data-ttu-id="024b3-105">查询表达式子句在编译时被转换为对查询方法的调用。</span><span class="sxs-lookup"><span data-stu-id="024b3-105">Query expression clauses are translated into calls to the query methods at compile time.</span></span>  
  
## <a name="query-expression-syntax-table"></a><span data-ttu-id="024b3-106">查询表达式语法表</span><span class="sxs-lookup"><span data-stu-id="024b3-106">Query Expression Syntax Table</span></span>  
 <span data-ttu-id="024b3-107">下表列出包含等效查询表达式子句的标准查询运算符。</span><span class="sxs-lookup"><span data-stu-id="024b3-107">The following table lists the standard query operators that have equivalent query expression clauses.</span></span>  
  
|<span data-ttu-id="024b3-108">方法</span><span class="sxs-lookup"><span data-stu-id="024b3-108">Method</span></span>|<span data-ttu-id="024b3-109">C# 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="024b3-109">C# Query Expression Syntax</span></span>|  
|------------|---------------------------------|  
|<xref:System.Linq.Enumerable.Cast%2A>|<span data-ttu-id="024b3-110">使用显式类型化范围变量，例如：</span><span class="sxs-lookup"><span data-stu-id="024b3-110">Use an explicitly typed range variable, for example:</span></span><br /><br /> `from int i in numbers`<br /><br /> <span data-ttu-id="024b3-111">（有关详细信息，请参阅 [from 子句](../../../../csharp/language-reference/keywords/from-clause.md)。）</span><span class="sxs-lookup"><span data-stu-id="024b3-111">(For more information, see [from clause](../../../../csharp/language-reference/keywords/from-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.GroupBy%2A>|`group … by`<br /><br /> <span data-ttu-id="024b3-112">- 或 -</span><span class="sxs-lookup"><span data-stu-id="024b3-112">-or-</span></span><br /><br /> `group … by … into …`<br /><br /> <span data-ttu-id="024b3-113">（有关详细信息，请参阅 [group 子句](../../../../csharp/language-reference/keywords/group-clause.md)。）</span><span class="sxs-lookup"><span data-stu-id="024b3-113">(For more information, see [group clause](../../../../csharp/language-reference/keywords/group-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|`join … in … on … equals … into …`<br /><br /> <span data-ttu-id="024b3-114">（有关详细信息，请参阅 [join 子句](../../../../csharp/language-reference/keywords/join-clause.md)。）</span><span class="sxs-lookup"><span data-stu-id="024b3-114">(For more information, see [join clause](../../../../csharp/language-reference/keywords/join-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|`join … in … on … equals …`<br /><br /> <span data-ttu-id="024b3-115">（有关详细信息，请参阅 [join 子句](../../../../csharp/language-reference/keywords/join-clause.md)。）</span><span class="sxs-lookup"><span data-stu-id="024b3-115">(For more information, see [join clause](../../../../csharp/language-reference/keywords/join-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby`<br /><br /> <span data-ttu-id="024b3-116">（有关详细信息，请参阅 [orderby 子句](../../../../csharp/language-reference/keywords/orderby-clause.md)。）</span><span class="sxs-lookup"><span data-stu-id="024b3-116">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
<xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby … descending`<br /><br /> <span data-ttu-id="024b3-117">（有关详细信息，请参阅 [orderby 子句](../../../../csharp/language-reference/keywords/orderby-clause.md)。）</span><span class="sxs-lookup"><span data-stu-id="024b3-117">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.Select%2A>|`select`<br /><br /> <span data-ttu-id="024b3-118">（有关详细信息，请参阅 [let 子句](../../../../csharp/language-reference/keywords/select-clause.md)。）</span><span class="sxs-lookup"><span data-stu-id="024b3-118">(For more information, see [select clause](../../../../csharp/language-reference/keywords/select-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.SelectMany%2A>|<span data-ttu-id="024b3-119">多个 `from` 子句。</span><span class="sxs-lookup"><span data-stu-id="024b3-119">Multiple `from` clauses.</span></span><br /><br /> <span data-ttu-id="024b3-120">（有关详细信息，请参阅 [from 子句](../../../../csharp/language-reference/keywords/from-clause.md)。）</span><span class="sxs-lookup"><span data-stu-id="024b3-120">(For more information, see [from clause](../../../../csharp/language-reference/keywords/from-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, …`<br /><br /> <span data-ttu-id="024b3-121">（有关详细信息，请参阅 [orderby 子句](../../../../csharp/language-reference/keywords/orderby-clause.md)。）</span><span class="sxs-lookup"><span data-stu-id="024b3-121">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, … descending`<br /><br /> <span data-ttu-id="024b3-122">（有关详细信息，请参阅 [orderby 子句](../../../../csharp/language-reference/keywords/orderby-clause.md)。）</span><span class="sxs-lookup"><span data-stu-id="024b3-122">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.Where%2A>|`where`<br /><br /> <span data-ttu-id="024b3-123">（有关详细信息，请参阅 [where 子句](../../../../csharp/language-reference/keywords/where-clause.md)。）</span><span class="sxs-lookup"><span data-stu-id="024b3-123">(For more information, see [where clause](../../../../csharp/language-reference/keywords/where-clause.md).)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="024b3-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="024b3-124">See Also</span></span>  
 <span data-ttu-id="024b3-125"><xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="024b3-125"><xref:System.Linq.Enumerable></span></span>   
 <span data-ttu-id="024b3-126"><xref:System.Linq.Queryable></span><span class="sxs-lookup"><span data-stu-id="024b3-126"><xref:System.Linq.Queryable></span></span>   
 <span data-ttu-id="024b3-127">[标准查询运算符概述 (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="024b3-127">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 [<span data-ttu-id="024b3-128">标准查询运算符按执行方式的分类 (C#)</span><span class="sxs-lookup"><span data-stu-id="024b3-128">Classification of Standard Query Operators by Manner of Execution (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)

