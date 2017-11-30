---
title: "类型的 &#39;&lt;variablename&gt;&#39; 无法推断，因为循环边界和步骤变量未扩大到同一类型"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords: BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 022e29e38a93d2880bbfa250e65a8b95b39ff140
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="type-of-39ltvariablenamegt39-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="94649-102">类型的 &#39;&lt;variablename&gt;&#39; 无法推断，因为循环边界和步骤变量未扩大到同一类型</span><span class="sxs-lookup"><span data-stu-id="94649-102">Type of &#39;&lt;variablename&gt;&#39; cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>
<span data-ttu-id="94649-103">在编写完`For...Next`循环在其中编译器无法推断 for 循环控制变量的数据类型因为满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="94649-103">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>  
  
-   <span data-ttu-id="94649-104">未在 `As` 子句中指定循环控制变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="94649-104">The data type of the loop control variable is not specified with an `As` clause.</span></span>  
  
-   <span data-ttu-id="94649-105">循环边界和步骤变量包含至少两种数据类型。</span><span class="sxs-lookup"><span data-stu-id="94649-105">The loop bounds and step variable contain at least two data types.</span></span>  
  
-   <span data-ttu-id="94649-106">数据类型之间不存在任何标准转换。</span><span class="sxs-lookup"><span data-stu-id="94649-106">No standard conversions exist between the data types.</span></span>  
  
 <span data-ttu-id="94649-107">因此，编译器无法推断的循环控制变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="94649-107">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>  
  
 <span data-ttu-id="94649-108">在下面的示例中，步骤变量是一个字符和循环边界都是整数。</span><span class="sxs-lookup"><span data-stu-id="94649-108">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="94649-109">由于没有任何标准字符和整数之间转换，将报告此错误。</span><span class="sxs-lookup"><span data-stu-id="94649-109">Because there is no standard conversion between characters and integers, this error is reported.</span></span>  
  
```vb  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 <span data-ttu-id="94649-110">**错误 ID:** BC30982</span><span class="sxs-lookup"><span data-stu-id="94649-110">**Error ID:** BC30982</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="94649-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="94649-111">To correct this error</span></span>  
  
-   <span data-ttu-id="94649-112">更改类型的循环边界和步骤变量，根据需要，以便至少一个是其他扩大到的类型。</span><span class="sxs-lookup"><span data-stu-id="94649-112">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="94649-113">在前面的示例中，更改的类型`stepVar`到`Integer`。</span><span class="sxs-lookup"><span data-stu-id="94649-113">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     <span data-ttu-id="94649-114">- 或 -</span><span class="sxs-lookup"><span data-stu-id="94649-114">—or—</span></span>  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   <span data-ttu-id="94649-115">使用显式转换函数将循环边界和步骤变量转换为相应的类型。</span><span class="sxs-lookup"><span data-stu-id="94649-115">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="94649-116">在前面的示例中，应用`Val`函数来`stepVar`。</span><span class="sxs-lookup"><span data-stu-id="94649-116">In the preceding example, apply the `Val` function to `stepVar`.</span></span>  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="94649-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94649-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [<span data-ttu-id="94649-118">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="94649-118">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="94649-119">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="94649-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="94649-120">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="94649-120">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="94649-121">Option Infer 语句</span><span class="sxs-lookup"><span data-stu-id="94649-121">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="94649-122">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="94649-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="94649-123">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="94649-123">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
