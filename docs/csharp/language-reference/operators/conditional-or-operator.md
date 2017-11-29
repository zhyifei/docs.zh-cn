---
title: "|| 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
caps.latest.revision: "25"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7b95fd162c9a89789e1970b32473c8acf16ba5cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a137d-102">|| 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a137d-102">|| Operator (C# Reference)</span></span>
<span data-ttu-id="a137d-103">条件 OR 运算符 (`||`) 执行其 `bool` 操作数的逻辑 OR。</span><span class="sxs-lookup"><span data-stu-id="a137d-103">The conditional-OR operator (`||`) performs a logical-OR of its `bool` operands.</span></span> <span data-ttu-id="a137d-104">如果第一个操作数的计算结果为 `true`，则不计算第二个操作数。</span><span class="sxs-lookup"><span data-stu-id="a137d-104">If the first operand evaluates to `true`, the second operand isn't evaluated.</span></span> <span data-ttu-id="a137d-105">如果第一个操作数的计算结果为 `false`，则第二个运算符决定 OR 表达式整体的计算结果是 `true` 还是 `false`。</span><span class="sxs-lookup"><span data-stu-id="a137d-105">If the first operand evaluates to `false`, the second operator determines whether the OR expression as a whole evaluates to `true` or `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a137d-106">备注</span><span class="sxs-lookup"><span data-stu-id="a137d-106">Remarks</span></span>  
 <span data-ttu-id="a137d-107">操作</span><span class="sxs-lookup"><span data-stu-id="a137d-107">The operation</span></span>  
  
```  
x || y  
```  
  
 <span data-ttu-id="a137d-108">对应于该操作</span><span class="sxs-lookup"><span data-stu-id="a137d-108">corresponds to the operation</span></span>  
  
```  
x | y  
```  
  
 <span data-ttu-id="a137d-109">除非，如果 `x` 为 `true`，不计算 `y`，因为不管 `y` 的值是什么，OR 运算的结果都是 `true`。</span><span class="sxs-lookup"><span data-stu-id="a137d-109">except that if `x` is `true`, `y` is not evaluated because the OR operation is `true` regardless of the value of `y`.</span></span> <span data-ttu-id="a137d-110">此概念即“短路”计算。</span><span class="sxs-lookup"><span data-stu-id="a137d-110">This concept is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="a137d-111">不能重载条件 OR 运算符，但常规逻辑运算符以及运算符 [true](../../../csharp/language-reference/keywords/true.md) 和 [false](../../../csharp/language-reference/keywords/false.md) 的重载在某些限制条件下也被视为条件逻辑运算符的重载。</span><span class="sxs-lookup"><span data-stu-id="a137d-111">The conditional-OR operator cannot be overloaded, but overloads of the regular logical operators and the [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) operators are, with certain restrictions, also considered to be overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a137d-112">示例</span><span class="sxs-lookup"><span data-stu-id="a137d-112">Example</span></span>  
 <span data-ttu-id="a137d-113">在以下示例中，使用 `||` 的表达式仅计算第一个操作数。</span><span class="sxs-lookup"><span data-stu-id="a137d-113">In the following examples, the expression that uses `||` evaluates only the first operand.</span></span> <span data-ttu-id="a137d-114">使用 `|` 的表达式计算两个操作数。</span><span class="sxs-lookup"><span data-stu-id="a137d-114">The expression that uses `|` evaluates both operands.</span></span> <span data-ttu-id="a137d-115">在第二个示例中，如果计算两个操作数，则会出现运行时异常。</span><span class="sxs-lookup"><span data-stu-id="a137d-115">In the second example, a run-time exception occurs if both operands are evaluated.</span></span>  
  
 [!code-csharp[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a137d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a137d-116">See Also</span></span>  
 [<span data-ttu-id="a137d-117">C# 参考</span><span class="sxs-lookup"><span data-stu-id="a137d-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a137d-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a137d-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a137d-119">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="a137d-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
