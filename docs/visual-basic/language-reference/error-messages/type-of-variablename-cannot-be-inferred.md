---
title: 无法推断“<variablename>”的类型，因为循环边界和步骤变量未扩大到同一类型
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: 1f1df0c7391c027994caabadc4b857bec55f5938
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287490"
---
# <a name="type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="a8051-102">类型\<变量名 > 无法推断，因为循环边界和步骤变量未扩大到同一类型</span><span class="sxs-lookup"><span data-stu-id="a8051-102">Type of '\<variablename>' cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>
<span data-ttu-id="a8051-103">您编写`For...Next`循环中的编译器无法推断 for 循环控制变量的数据类型因为以下条件成立：</span><span class="sxs-lookup"><span data-stu-id="a8051-103">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>  
  
-   <span data-ttu-id="a8051-104">未在 `As` 子句中指定循环控制变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a8051-104">The data type of the loop control variable is not specified with an `As` clause.</span></span>  
  
-   <span data-ttu-id="a8051-105">循环边界和步骤变量包含至少两种数据类型。</span><span class="sxs-lookup"><span data-stu-id="a8051-105">The loop bounds and step variable contain at least two data types.</span></span>  
  
-   <span data-ttu-id="a8051-106">数据类型之间存在的标准转换。</span><span class="sxs-lookup"><span data-stu-id="a8051-106">No standard conversions exist between the data types.</span></span>  
  
 <span data-ttu-id="a8051-107">因此，编译器无法推断的循环控制变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a8051-107">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>  
  
 <span data-ttu-id="a8051-108">在以下示例中，步骤变量是字符，且循环边界都是整数。</span><span class="sxs-lookup"><span data-stu-id="a8051-108">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="a8051-109">由于没有任何标准字符和整数之间转换，会报告此错误。</span><span class="sxs-lookup"><span data-stu-id="a8051-109">Because there is no standard conversion between characters and integers, this error is reported.</span></span>  
  
```vb  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 <span data-ttu-id="a8051-110">**错误 ID:** BC30982</span><span class="sxs-lookup"><span data-stu-id="a8051-110">**Error ID:** BC30982</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a8051-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="a8051-111">To correct this error</span></span>  
  
-   <span data-ttu-id="a8051-112">更改类型的循环边界和步骤变量根据需要，以便在至少一个其他扩大到的类型。</span><span class="sxs-lookup"><span data-stu-id="a8051-112">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="a8051-113">在前面的示例中，更改的类型`stepVar`到`Integer`。</span><span class="sxs-lookup"><span data-stu-id="a8051-113">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     <span data-ttu-id="a8051-114">- 或 -</span><span class="sxs-lookup"><span data-stu-id="a8051-114">—or—</span></span>  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   <span data-ttu-id="a8051-115">使用显式转换函数将转换为相应类型的循环边界和步骤变量。</span><span class="sxs-lookup"><span data-stu-id="a8051-115">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="a8051-116">在上述示例中，将应用`Val`函数来`stepVar`。</span><span class="sxs-lookup"><span data-stu-id="a8051-116">In the preceding example, apply the `Val` function to `stepVar`.</span></span>  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a8051-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8051-117">See also</span></span>
- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="a8051-118">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="a8051-118">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="a8051-119">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="a8051-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="a8051-120">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="a8051-120">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="a8051-121">Option Infer 语句</span><span class="sxs-lookup"><span data-stu-id="a8051-121">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="a8051-122">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="a8051-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="a8051-123">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="a8051-123">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
