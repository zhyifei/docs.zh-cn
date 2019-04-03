---
title: Distinct 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: fbca9fa8aa227d8d5b6488bef179f4bda08bb38c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830053"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="5a24d-102">Distinct 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a24d-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="5a24d-103">将当前的范围变量，以消除重复值在后续查询子句中的值限制。</span><span class="sxs-lookup"><span data-stu-id="5a24d-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a24d-104">语法</span><span class="sxs-lookup"><span data-stu-id="5a24d-104">Syntax</span></span>  
  
```  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="5a24d-105">备注</span><span class="sxs-lookup"><span data-stu-id="5a24d-105">Remarks</span></span>  
 <span data-ttu-id="5a24d-106">可以使用`Distinct`子句返回唯一项的列表。</span><span class="sxs-lookup"><span data-stu-id="5a24d-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="5a24d-107">`Distinct`子句会使查询以忽略重复的查询结果。</span><span class="sxs-lookup"><span data-stu-id="5a24d-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="5a24d-108">`Distinct`子句应用到重复的值的所有返回指定的字段`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="5a24d-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="5a24d-109">如果没有`Select`指定子句，则`Distinct`子句应用于查询中标识的范围变量`From`子句。</span><span class="sxs-lookup"><span data-stu-id="5a24d-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="5a24d-110">如果范围变量不是不可变类型，查询将只会忽略查询结果，如果该类型的所有成员都匹配现有的查询结果。</span><span class="sxs-lookup"><span data-stu-id="5a24d-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a24d-111">示例</span><span class="sxs-lookup"><span data-stu-id="5a24d-111">Example</span></span>  
 <span data-ttu-id="5a24d-112">下面的查询表达式联接客户列表和客户订单的列表。</span><span class="sxs-lookup"><span data-stu-id="5a24d-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="5a24d-113">`Distinct`子句是包括在内，以返回的唯一客户名称列表，并且订单日期。</span><span class="sxs-lookup"><span data-stu-id="5a24d-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="5a24d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a24d-114">See also</span></span>

- [<span data-ttu-id="5a24d-115">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="5a24d-115">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="5a24d-116">查询</span><span class="sxs-lookup"><span data-stu-id="5a24d-116">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="5a24d-117">From 子句</span><span class="sxs-lookup"><span data-stu-id="5a24d-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="5a24d-118">Select 子句</span><span class="sxs-lookup"><span data-stu-id="5a24d-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="5a24d-119">Where 子句</span><span class="sxs-lookup"><span data-stu-id="5a24d-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
