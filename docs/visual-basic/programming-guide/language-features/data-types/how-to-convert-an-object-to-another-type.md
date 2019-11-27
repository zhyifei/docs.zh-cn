---
title: 如何：将对象转换为其他类型
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 19708d03b0514f4572c2baa53e05781e5949766b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350076"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>如何：在 Visual Basic 中将一个对象转换为其他类型
您可以使用转换关键字（如[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)）将 `Object` 变量转换为另一种数据类型。  
  
## <a name="example"></a>示例  
 下面的示例将 `Object` 变量转换为 `Integer` 和 `String`。  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 如果知道 `Object` 变量的内容属于特定的数据类型，则最好将该变量转换为该数据类型。 如果继续使用 `Object` 变量，则会产生*装箱*和*取消装箱*（对于值类型）或*后期绑定*（对于引用类型）。 这些操作都需要额外的执行时间，并使性能更慢。  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 <xref:System?displayProperty=nameWithType> 命名空间的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Object>
- [Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [隐式转换和显式转换](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [字符串和其他类型之间的转换](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [数组转换](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [结构](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [数据类型](../../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
