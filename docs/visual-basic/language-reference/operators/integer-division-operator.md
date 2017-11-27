---
title: "\\ 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 38718b109b4b3865238267039908ea1d51d06229
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>\ 运算符 (Visual Basic)
将两个数相除，返回整数结果。  
  
## <a name="syntax"></a>语法  
  
```  
expression1 \ expression2  
```  
  
## <a name="parts"></a>部件  
 `expression1`  
 必需。 任何数值表达式。  
  
 `expression2`  
 必需。 任何数值表达式。  
  
## <a name="supported-types"></a>支持的类型  
 所有数值类型，包括未签名和浮点类型和`Decimal`。  
  
## <a name="result"></a>结果  
 结果为整数的商的`expression1`除以`expression2`，这将放弃所有余数并保留仅的整数部分。 这称为*截断*。  
  
 结果数据类型为数值类型适用于数据类型的`expression1`和`expression2`。 请参阅中的"整数算法"表[运算符结果的数据类型的](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)。  
  
 [/ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)返回完整的商，也可保留的小数部分的其余部分。  
  
## <a name="remarks"></a>备注  
 在执行之前除法，Visual Basic 尝试将转换到任何浮点数值表达式`Long`。 如果`Option Strict`是`On`，发生编译器错误。 如果`Option Strict`是`Off`、<xref:System.OverflowException>是可能的值的范围超出了如果[Long 数据类型](../../../visual-basic/language-reference/data-types/long-data-type.md)。 转换为`Long`还有受制于*银行家舍入法*。 有关详细信息，请参阅"小数部分"[类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)。  
  
 如果`expression1`或`expression2`计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)，它将被视为零。  
  
## <a name="attempted-division-by-zero"></a>尝试的除数为零  
 如果`expression2`计算结果为零，`\`运算符引发<xref:System.DivideByZeroException>异常。 这适用于所有数值数据类型的操作数。  
  
> [!NOTE]
>  `\`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。 如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`\`运算符执行整数除法。 结果是一个整数，表示两个操作数的整数商而丢弃的其余部分。  
  
 [!code-vb[VbVbalrOperators#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/integer-division-operator_1.vb)]  
  
 在前面的示例表达式分别返回 2、 3、 33 和-22 的值。  
  
## <a name="see-also"></a>另请参阅  
 [\\= 运算符](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [/ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)  
 [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [在 Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
