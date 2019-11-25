---
title: 'How to: Convert an Object to Another Type'
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
You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).  
  
## <a name="example"></a>示例  
 The following example converts an `Object` variable to an `Integer` and a `String`.  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type. If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type). These operations all take extra execution time and make your performance slower.  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 <xref:System?displayProperty=nameWithType> 命名空间的引用。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Object>
- [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [隐式转换和显式转换](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [字符串和其他类型之间的转换](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [数组转换](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [结构](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [数据类型](../../../../visual-basic/language-reference/data-types/index.md)
- [类型转换函数](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
