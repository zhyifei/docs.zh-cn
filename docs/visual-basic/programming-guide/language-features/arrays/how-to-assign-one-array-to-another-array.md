---
title: 如何：将一个数组赋给另一个数组 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: 63c7d187152fcb5ea84378c677aa687f334f63de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a>如何：将一个数组赋给另一个数组 (Visual Basic)
因为数组对象，你可以在赋值语句和其他对象类型一样使用它们。 一个数组变量保留一个指向数据构成的数组元素和的秩和长度的信息，并赋值将复制仅此指针。  
  
### <a name="to-assign-one-array-to-another-array"></a>若要将一个数组赋给另一个数组  
  
1.  确保两个数组具有相同秩 （维数） 和兼容的元素数据类型。  
  
2.  使用标准赋值语句将源数组赋给目标数组。 不用按照任一数组名称与括号。  
  
    ```  
    Dim formArray() As System.Windows.Forms.Form  
    Dim controlArray() As System.Windows.Forms.Control  
    controlArray = formArray  
    ```  
  
 如果你将一个数组赋给另一个时，以下规则适用：  
  
-   **相等的秩。** 目标数组的秩 （维数） 必须与源数组中的相同。  
  
     提供两个数组的秩相等，维度不需要相等。 在分配期间可以更改给定维度中的元素数。  
  
-   **元素类型。** 任一这两个数组必须具有*引用类型*元素或两个数组必须具有*值类型*元素。 有关详细信息，请参阅[值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)。  
  
    -   如果这两个数组具有值类型的元素，元素数据类型必须完全相同。 唯一的例外是： 你可以将分配的数组`Enum`指向数组的基类型的元素`Enum`。  
  
    -   如果这两个数组具有引用类型元素，则源元素类型必须从目标元素类型派生。 在这种情况下，两个数组具有继承关系与它们的元素相同。 这称为*数组协方差*。  
  
 编译器会报告错误如果违反了上述规则，例如当数据类型不兼容或者数组的秩不相等。 你可以添加到你的代码，以确保赋值前数组是相容处理的错误。 你还可以使用[TryCast 运算符](../../../../visual-basic/language-reference/operators/trycast-operator.md)关键字，如果你想要避免引发异常。  
  
## <a name="see-also"></a>请参阅  
 [数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [数组疑难解答](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [Enum 语句](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [数组转换](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
