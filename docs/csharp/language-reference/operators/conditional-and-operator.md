---
title: '&amp;&amp; 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: 459b791fde3e4d3940dbd3d916f940e81f365da6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43388288"
---
# <a name="ampamp-operator-c-reference"></a><span data-ttu-id="c5bf9-102">&amp;&amp; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c5bf9-102">&amp;&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="c5bf9-103">条件 AND 运算符 (`&&`) 对其 `bool` 操作数执行逻辑 AND 运算，但仅在必要时才计算第二个操作数。</span><span class="sxs-lookup"><span data-stu-id="c5bf9-103">The conditional-AND operator (`&&`) performs a logical-AND of its `bool` operands, but only evaluates its second operand if necessary.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5bf9-104">备注</span><span class="sxs-lookup"><span data-stu-id="c5bf9-104">Remarks</span></span>  
 <span data-ttu-id="c5bf9-105">操作</span><span class="sxs-lookup"><span data-stu-id="c5bf9-105">The operation</span></span>  
  
```csharp  
x && y  
```  
  
 <span data-ttu-id="c5bf9-106">对应于该操作</span><span class="sxs-lookup"><span data-stu-id="c5bf9-106">corresponds to the operation</span></span>  
  
```csharp  
x & y  
```  
  
 <span data-ttu-id="c5bf9-107">除非，如果 `x` 为 `false`，不计算 `y`，因为不管 `y` 的值是什么，AND 运算的结果都是 `false`。</span><span class="sxs-lookup"><span data-stu-id="c5bf9-107">except that if `x` is `false`, `y` is not evaluated, because the result of the AND operation is `false` no matter what the value of `y`  is.</span></span> <span data-ttu-id="c5bf9-108">这称作“短路”计算。</span><span class="sxs-lookup"><span data-stu-id="c5bf9-108">This is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="c5bf9-109">不能重载条件 AND 运算符，但常规逻辑运算符以及运算符 [true](../../../csharp/language-reference/keywords/true.md) 和 [false](../../../csharp/language-reference/keywords/false.md) 的重载在某些限制条件下也被视为条件逻辑运算符的重载。</span><span class="sxs-lookup"><span data-stu-id="c5bf9-109">The conditional-AND operator cannot be overloaded, but overloads of the regular logical operators and operators [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) are, with certain restrictions, also considered overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5bf9-110">示例</span><span class="sxs-lookup"><span data-stu-id="c5bf9-110">Example</span></span>  
 <span data-ttu-id="c5bf9-111">在以下示例中，第二个 `if` 语句中的条件表达式仅计算第一个操作数，因为操作数返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="c5bf9-111">In the following example, the conditional expression in the second `if` statement evaluates only the first operand because the operand returns `false`.</span></span>  
  
 [!code-csharp[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="c5bf9-112">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="c5bf9-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c5bf9-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5bf9-113">See Also</span></span>

- [<span data-ttu-id="c5bf9-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c5bf9-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="c5bf9-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c5bf9-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="c5bf9-116">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="c5bf9-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
