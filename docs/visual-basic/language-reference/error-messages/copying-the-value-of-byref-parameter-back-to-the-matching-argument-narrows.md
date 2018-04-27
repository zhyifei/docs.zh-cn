---
title: 值复制&#39;ByRef&#39;参数&#39; &lt;parametername&gt; &#39;回匹配的自变量类型从收缩&#39; &lt;typename1&gt; &#39;为类型&#39; &lt;typename2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 18c72e56e4b2cc9c2251de2417a9f12a6688323f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a>值复制&#39;ByRef&#39;参数&#39; &lt;parametername&gt; &#39;回匹配的自变量类型从收缩&#39; &lt;typename1&gt; &#39;为类型&#39; &lt;typename2&gt;&#39;
调用过程时使用的自变量扩大到相应的参数类型，并从参数到自变量转换为收缩转换。  
  
 在定义类或结构时，可以定义一个或多个转换运算符来将该类或结构类型转换为其他类型。 也可以定义反向转换运算符来将这些其他类型转换回类或结构类型。 当在过程调用中使用你的类或结构类型时，Visual Basic 可以使用这些转换运算符将自变量类型转换为其对应的参数的类型。  
  
 如果传递参数[ByRef](../../../visual-basic/language-reference/modifiers/byref.md)，Visual Basic 有时会将自变量值复制到本地变量中而不是传递一个引用的过程。 在这种情况下，当过程返回时，Visual Basic 必须随后将局部变量值复制回调用代码中的自变量。  
  
 如果将 `ByRef` 实参值复制到过程中，并且实参与形参为同一类型，则不必进行转换。 但如果类型不同，Visual Basic 必须进行双向转换。 如果你的类或结构类型的类型之一，Visual Basic 必须将其转换传入和传出另一种类型。 如果这些转换之一扩大转换，则可能收缩反向转换。  
  
 **错误 ID:** BC32053  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   如果可能，请与过程参数，使用相同类型的调用自变量，因此 Visual Basic 不需要进行任何转换。  
  
-   如果你需要使用自变量调用过程类型的参数类型不同，但不是需要将值返回到调用自变量、 参数定义为[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)而不是`ByRef`。  
  
-   如果你需要将值返回到调用自变量，定义反向转换运算符用作[Widening](../../../visual-basic/language-reference/modifiers/widening.md)如果可能。  
  
## <a name="see-also"></a>请参阅  
 [过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [过程参数和自变量](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [按值和按引用传递自变量](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [如何：定义运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [如何：定义转换运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [在 Visual Basic 中的类型转换](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [扩大转换和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
