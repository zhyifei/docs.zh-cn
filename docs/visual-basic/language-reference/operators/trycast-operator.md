---
title: TryCast 运算符 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6be11b49eb3b9d98e3bf147e9b1026d4ffc860c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="trycast-operator-visual-basic"></a>TryCast 运算符 (Visual Basic)
引入了并不会引发异常的类型转换运算。  
  
## <a name="remarks"></a>备注  
 如果尝试的转换失败，`CType`和`DirectCast`都会引发<xref:System.InvalidCastException>错误。 这会产生负面影响你的应用程序的性能。 `TryCast`返回[执行任何操作](../../../visual-basic/language-reference/nothing.md)，以便而无需处理可能发生的异常，你只需测试针对返回的结果`Nothing`。  
  
 你使用`TryCast`关键字使用的相同方式[CType 函数](../../../visual-basic/language-reference/functions/ctype-function.md)和[DirectCast 运算符](../../../visual-basic/language-reference/operators/directcast-operator.md)关键字。 提供作为第一个参数，并将它转换为第二个参数的类型的表达式。 `TryCast`只对引用类型，如类和接口执行操作。 它需要两个类型之间的继承或实现关系。 这意味着一个类型必须继承自或实现其他。  
  
## <a name="errors-and-failures"></a>错误和失败  
 `TryCast`如果它检测到没有继承或实现关系不存在，请生成一个编译器错误。 但是，编译器错误缺乏不保证成功的转换。 如果所需的转换收缩转换，则它可能在运行时失败。 如果发生这种情况，`TryCast`返回[执行任何操作](../../../visual-basic/language-reference/nothing.md)。  
  
## <a name="conversion-keywords"></a>转换关键字  
 类型转换关键字的比较是，如下所示。  
  
|关键字|数据类型|自变量关系|运行时失败|  
|---|---|---|---|  
|[CType 函数](../../../visual-basic/language-reference/functions/ctype-function.md)|任何数据类型|两个数据类型之间必须定义扩大或收缩转换|引发<xref:System.InvalidCastException>|  
|[DirectCast 运算符](../../../visual-basic/language-reference/operators/directcast-operator.md)|任何数据类型|一个类型必须继承自或实现其他类型|引发<xref:System.InvalidCastException>|  
|`TryCast`|仅适用于引用类型|一个类型必须继承自或实现其他类型|返回[执行任何操作](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>示例  
 下面的示例说明如何使用 `TryCast`。  
  
 [!code-vb[VbVbalrKeywords#6](../../../visual-basic/language-reference/codesnippet/VisualBasic/trycast-operator_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [扩大转换和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [隐式转换和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
