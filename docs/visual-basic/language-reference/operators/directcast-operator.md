---
title: DirectCast 运算符 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9b81abea364e328b831ee98c3b847161c3f7dd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="directcast-operator-visual-basic"></a>DirectCast 运算符 (Visual Basic)
引入了基于继承或实现的类型转换操作。  
  
## <a name="remarks"></a>备注  
 `DirectCast`不使用 Visual Basic 运行时帮助器例程进行转换，因此它可以提供某种程度上更好的性能比`CType`转换到和从数据类型时`Object`。  
  
 你使用`DirectCast`关键字类似于你使用的方式[CType 函数](../../../visual-basic/language-reference/functions/ctype-function.md)和[TryCast 运算符](../../../visual-basic/language-reference/operators/trycast-operator.md)关键字。 提供作为第一个参数，并将它转换为第二个参数的类型的表达式。 `DirectCast`需要两个自变量的数据类型之间的继承或实现关系。 这意味着一个类型必须继承自或实现其他。  
  
## <a name="errors-and-failures"></a>错误和失败  
 `DirectCast`如果它检测到没有继承或实现关系不存在，请生成一个编译器错误。 但是，编译器错误缺乏不保证成功的转换。 如果所需的转换收缩转换，则它可能在运行时失败。 如果发生这种情况，则运行时会引发<xref:System.InvalidCastException>错误。  
  
## <a name="conversion-keywords"></a>转换关键字  
 类型转换关键字的比较是，如下所示。  
  
|关键字|数据类型|自变量关系|运行时失败|  
|---|---|---|---|  
|[CType 函数](../../../visual-basic/language-reference/functions/ctype-function.md)|任何数据类型|两个数据类型之间必须定义扩大或收缩转换|引发<xref:System.InvalidCastException>|  
|`DirectCast`|任何数据类型|一个类型必须继承自或实现其他类型|引发<xref:System.InvalidCastException>|  
|[TryCast 运算符](../../../visual-basic/language-reference/operators/trycast-operator.md)|仅适用于引用类型|一个类型必须继承自或实现其他类型|返回[执行任何操作](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>示例  
 下面的示例演示两种含义`DirectCast`，未在运行的时，另一个成功。  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/VisualBasic/directcast-operator_1.vb)]  
  
 在前面的示例中，运行时类型`q`是`Double`。 `CType`将成功，因为`Double`可以转换为`Integer`。 但是，第一个`DirectCast`在运行时失败，因为运行时类型的`Double`不具有与任何继承关系`Integer`，即使已存在的转换。 第二个`DirectCast`会成功，因为它将从类型转换<xref:System.Windows.Forms.Form>类型<xref:System.Windows.Forms.Control>，从中<xref:System.Windows.Forms.Form>继承。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>  
 [扩大转换和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [隐式转换和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
