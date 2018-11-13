---
title: '?: 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 3e45ff6eaaefa5829c3ed9415abe1a12b7a1d069
ms.sourcegitcommit: 4bca8f7e172fd019ef437a4803bf5895c6bc4781
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "50980617"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="fe9d0-102">?: 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="fe9d0-102">?: Operator (C# Reference)</span></span>

<span data-ttu-id="fe9d0-103">条件运算符 (`?:`) 通常被称为三元条件运算符，根据 Boolean 表达式的值返回两个值之一。</span><span class="sxs-lookup"><span data-stu-id="fe9d0-103">The conditional operator (`?:`), commonly known as the ternary conditional operator, returns one of two values depending on the value of a Boolean expression.</span></span> <span data-ttu-id="fe9d0-104">下面是条件运算符的语法。</span><span class="sxs-lookup"><span data-stu-id="fe9d0-104">Following is the syntax for the conditional operator.</span></span>  

```csharp
condition ? first_expression : second_expression;  
```

<span data-ttu-id="fe9d0-105">自 C# 7.2 起，`first_expression` 和 `second_expression` 可以是 [`ref` 表达式](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md)：</span><span class="sxs-lookup"><span data-stu-id="fe9d0-105">Beginning with C# 7.2, the `first_expression` and `second_expression` my be [`ref` expressions](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md):</span></span>

```csharp
ref condition ? ref first_expression : ref second_expression;  
```

<span data-ttu-id="fe9d0-106">可将结果赋给 `ref` 或 `ref readonly` 变量，也可以赋给不带任一修饰符的变量。</span><span class="sxs-lookup"><span data-stu-id="fe9d0-106">The result may be assigned to a `ref` or `ref readonly` variable, or to a variable with neither modifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="fe9d0-107">备注</span><span class="sxs-lookup"><span data-stu-id="fe9d0-107">Remarks</span></span>

<span data-ttu-id="fe9d0-108">`condition` 的计算结果必须为 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="fe9d0-108">The `condition` must evaluate to `true` or `false`.</span></span> <span data-ttu-id="fe9d0-109">如果 `condition` 为 `true`，则将计算 `first_expression` 并使其成为结果。</span><span class="sxs-lookup"><span data-stu-id="fe9d0-109">If `condition` is `true`, `first_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="fe9d0-110">如果 `condition` 为 `false`，则将计算 `second_expression` 并使其成为结果。</span><span class="sxs-lookup"><span data-stu-id="fe9d0-110">If `condition` is `false`, `second_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="fe9d0-111">只计算两个表达式之一。</span><span class="sxs-lookup"><span data-stu-id="fe9d0-111">Only one of the two expressions is evaluated.</span></span> <span data-ttu-id="fe9d0-112">这对于结果为 `ref` 的表达式特别重要，因为以下内容有效：</span><span class="sxs-lookup"><span data-stu-id="fe9d0-112">This is particularly important for expressions where the result is a `ref`, as the following is valid:</span></span>

```csharp
ref (storage != null) ? ref storage[3] : ref defaultValue;
```

<span data-ttu-id="fe9d0-113">`storage` 为空时，不会计算对 `storage` 的引用。</span><span class="sxs-lookup"><span data-stu-id="fe9d0-113">The reference to `storage` is not evaluated when `storage` is null.</span></span>

<span data-ttu-id="fe9d0-114">若结果为值，`first_expression` 和 `second_expression` 的类型必须相同，或者必须存在从一种类型到另一种类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="fe9d0-114">When the result is a value, the type of `first_expression` and `second_expression` must be the same, or there must be an implicit conversion from one type to the other.</span></span> <span data-ttu-id="fe9d0-115">若结果为 `ref`，`first_expression` 和 `second_expression` 的类型必须相同。</span><span class="sxs-lookup"><span data-stu-id="fe9d0-115">When the result is a `ref`, the type of `first_expression` and `second_expression` must be the same.</span></span>

<span data-ttu-id="fe9d0-116">你可通过使用条件运算符表达可能更确切地要求 `if-else` 构造的计算。</span><span class="sxs-lookup"><span data-stu-id="fe9d0-116">You can express calculations that might otherwise require an `if-else` construction more concisely by using the conditional operator.</span></span> <span data-ttu-id="fe9d0-117">例如，以下代码首先使用 `if` 语句，然后使用条件运算符将整数分类为正整数或负整数。</span><span class="sxs-lookup"><span data-stu-id="fe9d0-117">For example, the following code uses first an `if` statement and then a conditional operator to classify an integer as positive or negative.</span></span>

```csharp
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

<span data-ttu-id="fe9d0-118">条件运算符为右联运算符。</span><span class="sxs-lookup"><span data-stu-id="fe9d0-118">The conditional operator is right-associative.</span></span> <span data-ttu-id="fe9d0-119">表达式 `a ? b : c ? d : e` 作为 `a ? b : (c ? d : e)` 而非 `(a ? b : c) ? d : e` 进行计算。</span><span class="sxs-lookup"><span data-stu-id="fe9d0-119">The expression `a ? b : c ? d : e` is evaluated as `a ? b : (c ? d : e)`, not as `(a ? b : c) ? d : e`.</span></span>  
  
<span data-ttu-id="fe9d0-120">无法重载条件运算符。</span><span class="sxs-lookup"><span data-stu-id="fe9d0-120">The conditional operator cannot be overloaded.</span></span>
  
## <a name="example"></a><span data-ttu-id="fe9d0-121">示例</span><span class="sxs-lookup"><span data-stu-id="fe9d0-121">Example</span></span>

<span data-ttu-id="fe9d0-122">以下示例显示结果为值的条件运算符：</span><span class="sxs-lookup"><span data-stu-id="fe9d0-122">The following example shows the conditional operator whose result is a value:</span></span>

[!code-csharp[csRefOperators?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

<span data-ttu-id="fe9d0-123">以下备选示例显示结果为 ref 的条件运算符：</span><span class="sxs-lookup"><span data-stu-id="fe9d0-123">The following alternative shows the conditional operator where the result is a reference:</span></span>

[!code-csharp[csRefOperatorsRef?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

## <a name="see-also"></a><span data-ttu-id="fe9d0-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe9d0-124">See Also</span></span>

- [<span data-ttu-id="fe9d0-125">C# 参考</span><span class="sxs-lookup"><span data-stu-id="fe9d0-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="fe9d0-126">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fe9d0-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="fe9d0-127">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="fe9d0-127">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="fe9d0-128">if-else</span><span class="sxs-lookup"><span data-stu-id="fe9d0-128">if-else</span></span>](../../../csharp/language-reference/keywords/if-else.md)  
- <span data-ttu-id="fe9d0-129">[?. 和 ?[] 运算符](../../../csharp/language-reference/operators/null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="fe9d0-129">[?. and ?[] Operators](../../../csharp/language-reference/operators/null-conditional-operators.md)</span></span>  
- [<span data-ttu-id="fe9d0-130">??运算符</span><span class="sxs-lookup"><span data-stu-id="fe9d0-130">?? Operator</span></span>](../../../csharp/language-reference/operators/null-coalescing-operator.md)
