---
title: ^ 运算符 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponention
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e7159f289b687055c7d75cc8da58d6f76607a83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>^ 运算符 (Visual Basic)
引发到另一个数字的幂的数字。  
  
## <a name="syntax"></a>语法  
  
```  
number ^ exponent  
```  
  
## <a name="parts"></a>部件  
 `number`  
 必需。 任何数值表达式。  
  
 `exponent`  
 必需。 任何数值表达式。  
  
## <a name="result"></a>结果  
 结果是`number`的幂`exponent`，始终为`Double`值。  
  
## <a name="supported-types"></a>支持的类型  
 `Double`。 任何其他类型的操作数将转换为`Double`。  
  
## <a name="remarks"></a>备注  
 Visual Basic 始终执行求幂中的[Double 数据类型](../../../visual-basic/language-reference/data-types/double-data-type.md)。  
  
 值`exponent`可以是小数，负的、 和/或文件名。  
  
 在单个表达式中执行多个求幂时`^`运算符从左到右出现的顺序进行计算。  
  
> [!NOTE]
>  `^`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。 如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`^`运算符的指数次幂数。 结果是第一个操作数的第二个次幂。  
  
 [!code-vb[VbVbalrOperators#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-operator_1.vb)]  
  
 前面的示例将生成下列结果：  
  
 `exp1`设置为 4 (2 平方值)。  
  
 `exp2`设置为 19683 (3 立方，然后的值求立方)。  
  
 `exp3`设置为-125 (-5 的立方)。  
  
 `exp4`设置为 625 (-5 的四次幂)。  
  
 `exp5`设置为 2 （8 的立方根）。  
  
 `exp6`设置为 0.5 (1.0 除以 8 的立方根)。  
  
 请注意在前面的示例中的表达式中的括号的重要性。 由于*运算符优先级*，通常情况下，Visual Basic 执行`^`运算符之前的任何其他，即使一元`–`运算符。 如果`exp4`和`exp6`计算时不带括号，将会产生以下结果：  
  
 `exp4 = -5 ^ 4`将计算为 – (5 四次幂)，这将导致-625。  
  
 `exp6 = 8 ^ -1.0 / 3.0`将计算方式 (8 到为-1 电源中或从 0.125) 除以 3.0，它的结果为 0.041666666666666666666666666666667。  
  
## <a name="see-also"></a>另请参阅  
 [^= 运算符](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [在 Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
