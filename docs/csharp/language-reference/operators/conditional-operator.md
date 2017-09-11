---
title: "?: 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 794ff53fe471ef23163503f59599b528df127e2e
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="d27fd-102">?: 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="d27fd-102">?: Operator (C# Reference)</span></span>
<span data-ttu-id="d27fd-103">条件运算符 (`?:`) 根据 Boolean 表达式的值返回两个值之一。</span><span class="sxs-lookup"><span data-stu-id="d27fd-103">The conditional operator (`?:`) returns one of two values depending on the value of a Boolean expression.</span></span> <span data-ttu-id="d27fd-104">下面是条件运算符的语法。</span><span class="sxs-lookup"><span data-stu-id="d27fd-104">Following is the syntax for the conditional operator.</span></span>  
  
```  
condition ? first_expression : second_expression;  
```  
  
## <a name="remarks"></a><span data-ttu-id="d27fd-105">备注</span><span class="sxs-lookup"><span data-stu-id="d27fd-105">Remarks</span></span>  
 <span data-ttu-id="d27fd-106">`condition` 的计算结果必须为 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="d27fd-106">The `condition` must evaluate to `true` or `false`.</span></span> <span data-ttu-id="d27fd-107">如果 `condition` 为 `true`，则将计算 `first_expression` 并使其成为结果。</span><span class="sxs-lookup"><span data-stu-id="d27fd-107">If `condition` is `true`, `first_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="d27fd-108">如果 `condition` 为 `false`，则将计算 `second_expression` 并使其成为结果。</span><span class="sxs-lookup"><span data-stu-id="d27fd-108">If `condition` is `false`, `second_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="d27fd-109">只计算两个表达式之一。</span><span class="sxs-lookup"><span data-stu-id="d27fd-109">Only one of the two expressions is evaluated.</span></span>  
  
 <span data-ttu-id="d27fd-110">`first_expression` 和 `second_expression` 的类型必须相同，或者必须存在从一种类型到另一种类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="d27fd-110">Either the type of `first_expression` and `second_expression` must be the same, or an implicit conversion must exist from one type to the other.</span></span>  
  
 <span data-ttu-id="d27fd-111">你可通过使用条件运算符表达可能更确切地要求 `if-else` 构造的计算。</span><span class="sxs-lookup"><span data-stu-id="d27fd-111">You can express calculations that might otherwise require an `if-else` construction more concisely by using the conditional operator.</span></span> <span data-ttu-id="d27fd-112">例如，以下代码首先使用 `if` 语句，然后使用条件运算符将整数分类为正整数或负整数。</span><span class="sxs-lookup"><span data-stu-id="d27fd-112">For example, the following code uses first an `if` statement and then a conditional operator to classify an integer as positive or negative.</span></span>  
  
```  
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```  
  
 <span data-ttu-id="d27fd-113">条件运算符为右联运算符。</span><span class="sxs-lookup"><span data-stu-id="d27fd-113">The conditional operator is right-associative.</span></span> <span data-ttu-id="d27fd-114">表达式 `a ? b : c ? d : e` 作为 `a ? b : (c ? d : e)` 而非 `(a ? b : c) ? d : e` 进行计算。</span><span class="sxs-lookup"><span data-stu-id="d27fd-114">The expression `a ? b : c ? d : e` is evaluated as `a ? b : (c ? d : e)`, not as `(a ? b : c) ? d : e`.</span></span>  
  
 <span data-ttu-id="d27fd-115">无法重载条件运算符。</span><span class="sxs-lookup"><span data-stu-id="d27fd-115">The conditional operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d27fd-116">示例</span><span class="sxs-lookup"><span data-stu-id="d27fd-116">Example</span></span>  
 <span data-ttu-id="d27fd-117">[!code-cs[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d27fd-117">[!code-cs[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d27fd-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d27fd-118">See Also</span></span>  
 <span data-ttu-id="d27fd-119">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d27fd-119">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d27fd-120">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d27fd-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d27fd-121">[C# 运算符](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="d27fd-121">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="d27fd-122">[if-else](../../../csharp/language-reference/keywords/if-else.md) </span><span class="sxs-lookup"><span data-stu-id="d27fd-122">[if-else](../../../csharp/language-reference/keywords/if-else.md) </span></span>  
 <span data-ttu-id="d27fd-123">[?. 和 ? 运算符](../../../csharp/language-reference/operators/null-conditional-operators.md) </span><span class="sxs-lookup"><span data-stu-id="d27fd-123">[?. and ?Operators](../../../csharp/language-reference/operators/null-conditional-operators.md) </span></span>  
 [<span data-ttu-id="d27fd-124">??运算符</span><span class="sxs-lookup"><span data-stu-id="d27fd-124">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)

