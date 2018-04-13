---
title: 如何：在 Visual Basic 中将一个对象转换为其他类型
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 053c93e7cf842138f5b9299cd2fcfa56342dd40b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>如何：在 Visual Basic 中将一个对象转换为其他类型
你将转换`Object`变量与另一个数据类型，使用转换关键字类似于[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)。  
  
## <a name="example"></a>示例  
 以下示例将转换`Object`变量`Integer`和`String`。  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 如果您知道的内容`Object`变量是否的特定的数据类型，则最好将变量转换为该数据类型。 如果你继续使用`Object`变量，则会引发*装箱*和*取消装箱*（对于值类型） 或*后期绑定*（对于引用类型）。 这些操作中，所有采用额外的执行时间，并会降低性能。  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   对 <xref:System?displayProperty=nameWithType> 命名空间的引用。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Object>  
 [在 Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [隐式转换和显式转换](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [字符串和其他类型之间的转换](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [数组转换](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [结构](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [类型转换函数](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
