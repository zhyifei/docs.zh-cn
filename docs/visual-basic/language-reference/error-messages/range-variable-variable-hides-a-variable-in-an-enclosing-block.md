---
title: 范围变量&lt;变量&gt;隐藏封闭块、 以前定义的范围变量或查询表达式中隐式声明的变量中的变量
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: f02533cf7cb79c34e5bb5a6d445aaef7ab0e86da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593121"
---
# <a name="range-variable-ltvariablegt-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="bfa0b-102">范围变量&lt;变量&gt;隐藏封闭块、 以前定义的范围变量或查询表达式中隐式声明的变量中的变量</span><span class="sxs-lookup"><span data-stu-id="bfa0b-102">Range variable &lt;variable&gt; hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>
<span data-ttu-id="bfa0b-103">中指定的范围变量名称`Select`， `From`， `Aggregate`，或`Let`子句的查询，或查询，隐式声明的变量名之前已指定的范围变量的名称重复例如，字段名称或聚合函数的名称。</span><span class="sxs-lookup"><span data-stu-id="bfa0b-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>  
  
 <span data-ttu-id="bfa0b-104">**错误 ID:** BC36633</span><span class="sxs-lookup"><span data-stu-id="bfa0b-104">**Error ID:** BC36633</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bfa0b-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="bfa0b-105">To correct this error</span></span>  
  
-   <span data-ttu-id="bfa0b-106">确保在特定的查询作用域的所有范围变量都具有唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="bfa0b-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="bfa0b-107">可以将查询括在圆括号中以确保嵌套的查询具有一个唯一范围。</span><span class="sxs-lookup"><span data-stu-id="bfa0b-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfa0b-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfa0b-108">See Also</span></span>  
 [<span data-ttu-id="bfa0b-109">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="bfa0b-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="bfa0b-110">From 子句</span><span class="sxs-lookup"><span data-stu-id="bfa0b-110">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="bfa0b-111">Let 子句</span><span class="sxs-lookup"><span data-stu-id="bfa0b-111">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)  
 [<span data-ttu-id="bfa0b-112">Aggregate 子句</span><span class="sxs-lookup"><span data-stu-id="bfa0b-112">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="bfa0b-113">Select 子句</span><span class="sxs-lookup"><span data-stu-id="bfa0b-113">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
