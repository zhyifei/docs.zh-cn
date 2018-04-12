---
title: Widening (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 034099397c1d296a42712b8c202e2ac99a0fb43b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)
指示转换运算符 (`CType`) 将一个类或结构转换为可以包含原始类或结构的所有可能值的类型。  
  
## <a name="converting-with-the-widening-keyword"></a>转换使用扩大关键字  
 必须指定转换过程`Public Shared`除了`Widening`。  
  
 扩大转换在运行时始终成功，并且永远不会导致数据丢失。 示例包括`Single`到`Double`，`Char`到`String`，和到与其基类型的派生的类型。 最后一个转换扩大转换，因为派生的类型包含的基类型的所有成员，因此基类型的实例。  
  
 使用的代码不需要使用`CType`进行扩大转换，即使`Option Strict`是`On`。  
  
 `Widening`关键字可在此上下文中：  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 有关示例定义的扩大转换和收缩转换运算符，请参阅[如何： 定义转换运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)。  
  
## <a name="see-also"></a>另请参阅  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [扩大转换和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [如何：定义运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [CType 函数](../../../visual-basic/language-reference/functions/ctype-function.md)  
 [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [如何：定义转换运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
