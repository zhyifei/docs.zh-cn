---
title: 范围变量 <variable> 隐藏封闭块中的变量、以前定义的范围变量或在查询表达式中隐式声明的变量
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: e31f728de228bea743f6c7b5cbfef3cd73367262
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822708"
---
# <a name="range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="4d4b4-102">范围变量\<变量 > 隐藏封闭块、 以前定义的范围变量或在查询表达式中隐式声明的变量中的变量</span><span class="sxs-lookup"><span data-stu-id="4d4b4-102">Range variable \<variable> hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>
<span data-ttu-id="4d4b4-103">范围变量名称中指定`Select`， `From`， `Aggregate`，或`Let`子句的查询或查询，隐式声明的变量名称中之前已指定的范围变量名称重复例如，字段名称或聚合函数的名称。</span><span class="sxs-lookup"><span data-stu-id="4d4b4-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>  
  
 <span data-ttu-id="4d4b4-104">**错误 ID:** BC36633</span><span class="sxs-lookup"><span data-stu-id="4d4b4-104">**Error ID:** BC36633</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4d4b4-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="4d4b4-105">To correct this error</span></span>  
  
-   <span data-ttu-id="4d4b4-106">确保特定的查询作用域中的所有范围变量都具有唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="4d4b4-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="4d4b4-107">可以将一个查询括在括号中以确保嵌套的查询具有一个唯一范围。</span><span class="sxs-lookup"><span data-stu-id="4d4b4-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d4b4-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d4b4-108">See also</span></span>

- [<span data-ttu-id="4d4b4-109">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="4d4b4-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="4d4b4-110">From 子句</span><span class="sxs-lookup"><span data-stu-id="4d4b4-110">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="4d4b4-111">Let 子句</span><span class="sxs-lookup"><span data-stu-id="4d4b4-111">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)
- [<span data-ttu-id="4d4b4-112">Aggregate 子句</span><span class="sxs-lookup"><span data-stu-id="4d4b4-112">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="4d4b4-113">Select 子句</span><span class="sxs-lookup"><span data-stu-id="4d4b4-113">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
