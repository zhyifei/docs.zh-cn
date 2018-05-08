---
title: CType 函数 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 7b1c7ae2a0126bf7cd487df4e9a7364c98e1c695
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ctype-function-visual-basic"></a>CType 函数 (Visual Basic)
返回表达式显式转换为指定的数据类型、 对象、 结构、 类或接口的结果。  
  
## <a name="syntax"></a>语法  
  
```  
CType(expression, typename)  
```  
  
## <a name="parts"></a>部件  
 `expression`  
 任何有效表达式。 如果值`expression`超出了允许的范围`typename`，Visual Basic 会引发异常。  
  
 `typename`  
 任何表达式，即在内合法`As`中的子句`Dim`语句，任何数据类型、 对象、 结构、 类或接口的名称。  
  
## <a name="remarks"></a>备注  
  
> [!TIP]
>  你还可以使用以下函数执行类型转换：  
>   
>  -   类型转换函数，如`CByte`， `CDbl`，和`CInt`执行向特定的数据类型的转换。 有关详细信息，请参阅[类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)。  
> -   [DirectCast 运算符](../../../visual-basic/language-reference/operators/directcast-operator.md)或[TryCast 运算符](../../../visual-basic/language-reference/operators/trycast-operator.md)。 这些运算符需要一种类型继承自或实现其他类型。 它们可以提供某种程度上更好的性能比`CType`来回进行转换时`Object`数据类型。  
  
 `CType` 是编译的内联，这意味着所计算的表达式过程中进行转换代码。 在某些情况下，代码运行速度更快因为没有过程调用来执行转换。  
  
 如果未定义转换从`expression`到`typename`(例如，从`Integer`到`Date`)，Visual Basic 显示编译时错误消息。  
  
 如果转换失败在运行时，引发相应异常。 如果收缩转换失败，<xref:System.OverflowException>是最常见的结果。 如果转换未定义，<xref:System.InvalidCastException>中引发。 例如，如果发生了此可以`expression`属于类型`Object`和其运行时类型具有不转换为`typename`。  
  
 如果数据类型的`expression`或`typename`是一个类或结构你定义后，你可以定义`CType`在该类或结构用作转换运算符。 这使得`CType`充当*重载运算符*。 如果这样做，你可以控制转换到和从你的类或结构，包括可能引发的异常的行为。  
  
## <a name="overloading"></a>重载  
 `CType`还可以对类或结构代码之外定义重载运算符。 如果你的代码需要在这样的类或结构之间进行转换，请确保你了解的行为及其`CType`运算符。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="converting-dynamic-objects"></a>转换动态对象  
 动态对象的类型转换执行用户定义的动态转换使用通过<xref:System.Dynamic.DynamicObject.TryConvert%2A>或<xref:System.Dynamic.DynamicMetaObject.BindConvert%2A>方法。 如果你正在使用动态对象，使用<xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A>方法将转换的动态对象。  
  
## <a name="example"></a>示例  
 下面的示例使用`CType`函数可将对表达式`Single`数据类型。  
  
 [!code-vb[VbVbalrFunctions#24](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/ctype-function_1.vb)]  
  
 有关其他示例，请参阅[隐式和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.OverflowException>  
 <xref:System.InvalidCastException>  
 [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [转换函数](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [如何：定义转换运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [.NET Framework 中的类型转换](../../../standard/base-types/type-conversion.md)
