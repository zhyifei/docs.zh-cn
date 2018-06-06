---
title: 运算符过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
ms.openlocfilehash: 5b4641ce8509e3111a11ed803d36194d5a301bce
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805706"
---
# <a name="operator-procedures-visual-basic"></a>运算符过程 (Visual Basic)
运算符过程是一系列定义一个标准的运算符的行为的 Visual Basic 语句 (如`*`， `<>`，或`And`) 对类或你定义的结构。 这也称为*运算符重载*。  
  
## <a name="when-to-define-operator-procedures"></a>何时定义运算符过程  
 当你已定义类或结构时，可声明为类或结构的类型的变量。 有时这种变量需要参与一个操作作为表达式的一部分。 若要执行此操作，它必须是运算符的操作数。  
  
 Visual Basic 仅在其基本数据类型上定义运算符。 你可以定义一个运算符的行为或两个操作数均为你的类或结构的类型。  
  
 有关详细信息，请参阅[Operator 语句](../../../../visual-basic/language-reference/statements/operator-statement.md)。  
  
## <a name="types-of-operator-procedure"></a>类型的运算符过程  
 运算符过程可以是以下类型之一：  
  
-   一元运算符的自变量为类或结构类型的其中一个定义。  
  
-   其中至少一个自变量是类或结构类型的二进制运算符的定义。  
  
-   其中的自变量为类或结构类型转换运算符的定义。  
  
-   返回的类或结构类型转换运算符的定义。  
  
 转换运算符始终是一元，并且会一直使用`CType`用作你定义的运算符。  
  
## <a name="declaration-syntax"></a>声明语法  
 声明运算符过程的语法如下所示：  
  
 `Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol* `(` *operand1*`[,`*operand2* `]) As`*数据类型*  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 你使用`Widening`或`Narrowing`关键字仅在类型转换运算符。 运算符符号始终是[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)有关类型转换运算符。  
  
 声明两个操作数定义二元运算符，并声明一个要定义一元运算符，包括类型转换运算符的操作数。 所有操作数都必须都声明`ByVal`。  
  
 声明每个操作数相同的方式声明的参数[Sub 过程](./sub-procedures.md)。  
  
### <a name="data-type"></a>数据类型  
 因为你在类或你定义的结构上定义一个运算符，至少其中一个操作数必须是此类或结构的数据类型。 对于类型转换运算符，操作数或的返回类型必须是类或结构的数据类型。  
  
 有关更多详细信息，请参阅[Operator 语句](../../../../visual-basic/language-reference/statements/operator-statement.md)。  
  
## <a name="calling-syntax"></a>调用语法  
 通过在表达式中使用运算符的隐式调用运算符过程。 你提供操作数你对于预定义的运算符的相同方式。  
  
 隐式调用运算符过程的语法如下所示：  
  
 `Dim testStruct As`  *structurename*  
  
 `Dim testNewStruct As`  *structurename*`= testStruct`*operatorsymbol*  `10`  
  
### <a name="illustration-of-declaration-and-call"></a>声明和调用图  
 以下结构存储构成的高顺序和低序位部分作为一个 128 位有符号的整数值。 它定义`+`运算符添加两个`veryLong`值，并生成生成`veryLong`值。  
  
 [!code-vb[VbVbcnProcedures#23](./codesnippet/VisualBasic/operator-procedures_1.vb)]  
  
 下面的示例演示典型调用`+`上定义的运算符`veryLong`。  
  
 [!code-vb[VbVbcnProcedures#24](./codesnippet/VisualBasic/operator-procedures_2.vb)]  
  
 有关详细信息和示例，请参阅 [Visual Basic 2005 中的运算符重载](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx)。  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [Sub 过程](./sub-procedures.md)  
 [Function 过程](./function-procedures.md)  
 [属性过程](./property-procedures.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [如何：定义运算符](./how-to-define-an-operator.md)  
 [如何：定义转换运算符](./how-to-define-a-conversion-operator.md)  
 [如何：调用运算符过程](./how-to-call-an-operator-procedure.md)  
 [如何：使用定义运算符的类](./how-to-use-a-class-that-defines-operators.md)
