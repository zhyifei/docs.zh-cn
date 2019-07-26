---
title: 无法推断“<variablename>”的类型，因为循环边界和步骤变量未扩大到同一类型
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: c3086f79fb71693810bc8f14e8c0f493aa1e6515
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512709"
---
# <a name="type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="dc809-102">因为循环边界\<和步骤变量未扩大到同一类型, 所以无法推断 "variablename >" 的类型</span><span class="sxs-lookup"><span data-stu-id="dc809-102">Type of '\<variablename>' cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>

<span data-ttu-id="dc809-103">你编写了一个`For...Next`循环, 该循环中编译器无法推断循环控制变量的数据类型, 因为满足以下条件:</span><span class="sxs-lookup"><span data-stu-id="dc809-103">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>

- <span data-ttu-id="dc809-104">未在 `As` 子句中指定循环控制变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="dc809-104">The data type of the loop control variable is not specified with an `As` clause.</span></span>

- <span data-ttu-id="dc809-105">循环边界和步骤变量包含至少两种数据类型。</span><span class="sxs-lookup"><span data-stu-id="dc809-105">The loop bounds and step variable contain at least two data types.</span></span>

- <span data-ttu-id="dc809-106">数据类型之间不存在标准转换。</span><span class="sxs-lookup"><span data-stu-id="dc809-106">No standard conversions exist between the data types.</span></span>

 <span data-ttu-id="dc809-107">因此, 编译器无法推断循环控制变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="dc809-107">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>

 <span data-ttu-id="dc809-108">在下面的示例中, 步骤变量是一个字符, 并且循环边界都是整数。</span><span class="sxs-lookup"><span data-stu-id="dc809-108">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="dc809-109">由于字符和整数之间没有标准转换, 因此将报告此错误。</span><span class="sxs-lookup"><span data-stu-id="dc809-109">Because there is no standard conversion between characters and integers, this error is reported.</span></span>

```vb
Dim stepVar = "1"c
Dim m = 0
Dim n = 20

' Not valid.
' For i = 1 To 10 Step stepVar
    ' Loop processing
' Next
```

<span data-ttu-id="dc809-110">**错误 ID:** BC30982</span><span class="sxs-lookup"><span data-stu-id="dc809-110">**Error ID:** BC30982</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="dc809-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="dc809-111">To correct this error</span></span>

- <span data-ttu-id="dc809-112">根据需要更改循环边界和步骤变量的类型, 以使其中至少有一个类型为其他类型。</span><span class="sxs-lookup"><span data-stu-id="dc809-112">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="dc809-113">在前面的示例中, 将的`stepVar`类型更改为。 `Integer`</span><span class="sxs-lookup"><span data-stu-id="dc809-113">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>

  ```vb
  Dim stepVar = 1
  ```

  <span data-ttu-id="dc809-114">或</span><span class="sxs-lookup"><span data-stu-id="dc809-114">-or-</span></span>

  ```vb
  Dim stepVar As Integer = 1
  ```

- <span data-ttu-id="dc809-115">使用显式转换函数将循环边界和步骤变量转换为适当的类型。</span><span class="sxs-lookup"><span data-stu-id="dc809-115">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="dc809-116">在前面的示例中, 将`Val` `stepVar`函数应用于。</span><span class="sxs-lookup"><span data-stu-id="dc809-116">In the preceding example, apply the `Val` function to `stepVar`.</span></span>

  ```vb
  For i = 1 To 10 Step Val(stepVar)
      ' Loop processing
  Next
  ```

## <a name="see-also"></a><span data-ttu-id="dc809-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc809-117">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="dc809-118">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="dc809-118">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="dc809-119">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="dc809-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="dc809-120">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="dc809-120">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="dc809-121">Option Infer 语句</span><span class="sxs-lookup"><span data-stu-id="dc809-121">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="dc809-122">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="dc809-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="dc809-123">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="dc809-123">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
