---
title: 键入的&#39; &lt;variablename&gt; &#39;无法推断，因为循环边界和步骤变量未扩大到同一类型
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: d6fdd9445b5336773d150c643c7bf1ca58a0c87a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="type-of-39ltvariablenamegt39-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a>键入的&#39; &lt;variablename&gt; &#39;无法推断，因为循环边界和步骤变量未扩大到同一类型
在编写完`For...Next`循环在其中编译器无法推断 for 循环控制变量的数据类型因为满足以下条件：  
  
-   未在 `As` 子句中指定循环控制变量的数据类型。  
  
-   循环边界和步骤变量包含至少两种数据类型。  
  
-   数据类型之间不存在任何标准转换。  
  
 因此，编译器无法推断的循环控制变量的数据类型。  
  
 在下面的示例中，步骤变量是一个字符和循环边界都是整数。 由于没有任何标准字符和整数之间转换，将报告此错误。  
  
```vb  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 **错误 ID:** BC30982  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   更改类型的循环边界和步骤变量，根据需要，以便至少一个是其他扩大到的类型。 在前面的示例中，更改的类型`stepVar`到`Integer`。  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     - 或 -  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   使用显式转换函数将循环边界和步骤变量转换为相应的类型。 在前面的示例中，应用`Val`函数来`stepVar`。  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [隐式转换和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Infer 语句](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [扩大转换和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
