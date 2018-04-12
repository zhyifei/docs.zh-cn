---
title: Distinct 子句 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ed92d5d601c1ec329728346ac881c4fa2bad8aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="bcd9d-102">Distinct 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bcd9d-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="bcd9d-103">限制当前的范围变量，以消除后续查询子句中的重复值的值。</span><span class="sxs-lookup"><span data-stu-id="bcd9d-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcd9d-104">语法</span><span class="sxs-lookup"><span data-stu-id="bcd9d-104">Syntax</span></span>  
  
```  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="bcd9d-105">备注</span><span class="sxs-lookup"><span data-stu-id="bcd9d-105">Remarks</span></span>  
 <span data-ttu-id="bcd9d-106">你可以使用`Distinct`子句返回唯一项的列表。</span><span class="sxs-lookup"><span data-stu-id="bcd9d-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="bcd9d-107">`Distinct`子句将使查询后，若要忽略重复的查询结果。</span><span class="sxs-lookup"><span data-stu-id="bcd9d-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="bcd9d-108">`Distinct`子句应用于重复的值中，所有返回指定的字段`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="bcd9d-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="bcd9d-109">如果没有`Select`指定子句，`Distinct`子句应用于查询中标识的范围变量`From`子句。</span><span class="sxs-lookup"><span data-stu-id="bcd9d-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="bcd9d-110">如果范围变量不是一个不可变类型，查询将只会忽略查询结果，如果类型的所有成员都匹配现有的查询结果。</span><span class="sxs-lookup"><span data-stu-id="bcd9d-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcd9d-111">示例</span><span class="sxs-lookup"><span data-stu-id="bcd9d-111">Example</span></span>  
 <span data-ttu-id="bcd9d-112">下面的查询表达式将联接客户的列表和客户订单的列表。</span><span class="sxs-lookup"><span data-stu-id="bcd9d-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="bcd9d-113">`Distinct`子句目的是为了返回唯一客户名称的列表和订单日期。</span><span class="sxs-lookup"><span data-stu-id="bcd9d-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bcd9d-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bcd9d-114">See Also</span></span>  
 [<span data-ttu-id="bcd9d-115">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="bcd9d-115">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="bcd9d-116">查询</span><span class="sxs-lookup"><span data-stu-id="bcd9d-116">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="bcd9d-117">From 子句</span><span class="sxs-lookup"><span data-stu-id="bcd9d-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="bcd9d-118">Select 子句</span><span class="sxs-lookup"><span data-stu-id="bcd9d-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="bcd9d-119">Where 子句</span><span class="sxs-lookup"><span data-stu-id="bcd9d-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
