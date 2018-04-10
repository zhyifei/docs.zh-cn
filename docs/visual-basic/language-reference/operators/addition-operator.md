---
title: + 运算符 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fb0d66db2d777c046ccec69acc1f2069d21baf6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>+ 运算符 (Visual Basic)
将两个数相加或返回数值表达式的正数值。 此外可以用于连接两个字符串表达式。  
  
## <a name="syntax"></a>语法  
  
```  
      expression1 + expression2  
- or -  
+ expression1  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`expression1`|必需。 任何数值或字符串的表达式。|  
|`expression2`|必填，除非`+`运算符正在计算值为负。 任何数值或字符串的表达式。|  
  
## <a name="result"></a>结果  
 如果`expression1`和`expression2`均为数值，则结果是它们的算术和。  
  
 如果`expression2`不存在，`+`运算符是*一元*恒等运算符的表达式的未更改值。 在这个意义上来说，该操作包含的保留的符号`expression1`，因此结果为负如果`expression1`为负。  
  
 如果`expression1`和`expression2`都是字符串，则结果是其值的串联。  
  
 如果`expression1`和`expression2`是混合类型的执行的操作取决于其类型，其内容和的设置[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。 有关详细信息，请参阅"备注。"中的表  
  
## <a name="supported-types"></a>支持的类型  
 所有数值类型，包括未签名和浮点类型和`Decimal`，和`String`。  
  
## <a name="remarks"></a>备注  
 一般情况下，`+`执行算术加法运算在可能的情况下，并将连接仅当两个表达式均为字符串时，才。  
  
 如果表达式都不是`Object`，Visual Basic 将采取以下措施。  
  
|表达式的数据类型|由编译器的操作|  
|---|---|  
|两个表达式均数值数据类型 (`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`， `ULong`， `Decimal`， `Single`，或`Double`)|添加。 结果数据类型为数值类型适用于数据类型的`expression1`和`expression2`。 请参阅中的"整数算法"表[运算符结果的数据类型的](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)。|  
|这两个表达式均为类型`String`|串联在一起。|  
|一个表达式为数值数据类型，另一个是一个字符串|如果`Option Strict`是`On`，然后将生成编译器错误。<br /><br /> 如果`Option Strict`是`Off`，隐式转换`String`到`Double`和添加。<br /><br /> 如果`String`不能转换为`Double`，然后引发<xref:System.InvalidCastException>异常。|  
|一个表达式为数值数据类型，而另一种是[执行任何操作](../../../visual-basic/language-reference/nothing.md)|添加，请使用`Nothing`值为零。|  
|一个表达式是字符串，并且另一种是`Nothing`|连接，与`Nothing`值为""。|  
  
 如果一个表达式为`Object`表达式，Visual Basic 将采取以下措施。  
  
|表达式的数据类型|由编译器的操作|  
|---|---|  
|`Object`表达式包含的数字值，另一个是数值数据类型|如果`Option Strict`是`On`，然后将生成编译器错误。<br /><br /> 如果`Option Strict`是`Off`，然后添加。|  
|`Object`表达式包含的数字值，另一个是类型的`String`|如果`Option Strict`是`On`，然后将生成编译器错误。<br /><br /> 如果`Option Strict`是`Off`，隐式转换`String`到`Double`和添加。<br /><br /> 如果`String`不能转换为`Double`，然后引发<xref:System.InvalidCastException>异常。|  
|`Object`表达式包含一个字符串，另一个是数值数据类型|如果`Option Strict`是`On`，然后将生成编译器错误。<br /><br /> 如果`Option Strict`是`Off`，然后将字符串隐式转换`Object`到`Double`和添加。<br /><br /> 如果字符串`Object`不能转换为`Double`，然后引发<xref:System.InvalidCastException>异常。|  
|`Object`表达式包含一个字符串，另一个是类型的`String`|如果`Option Strict`是`On`，然后将生成编译器错误。<br /><br /> 如果`Option Strict`是`Off`，隐式转换`Object`到`String`并连接。|  
  
 如果两个表达式均`Object`表达式，Visual Basic 将采取以下措施 (`Option Strict Off`仅)。  
  
|表达式的数据类型|由编译器的操作|  
|---|---|  
|同时`Object`表达式保留数值|添加。|  
|同时`Object`表达式均为类型`String`|串联在一起。|  
|一个`Object`表达式包含的数字值和其他包含字符串|将字符串隐式转换`Object`到`Double`和添加。<br /><br /> 如果字符串`Object`不能转换为数字值，然后引发<xref:System.InvalidCastException>异常。|  
  
 如果任一`Object`表达式计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)或<xref:System.DBNull>、`+`运算符会将其视为`String`值为""。  
  
> [!NOTE]
>  当你使用`+`运算符，你可能不能以确定是否添加或字符串串联将出现。 使用`&`的串联运算符，以消除多义性，并提供自说明代码。  
  
## <a name="overloading"></a>重载  
 `+`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。 如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`+`运算符以添加数字。 如果操作数均为数值的同时，Visual Basic 将计算算术的结果。 算术结果表示两个操作数之和。  
  
 [!code-vb[VbVbalrOperators#6](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_1.vb)]  
  
 你还可以使用`+`运算符来连接字符串。 如果操作数均为两个字符串，Visual Basic 将它们连接。 串联结果表示单个字符串依次排列包含的两个操作数的内容。  
  
 如果操作数都是混合类型，结果取决于的设置[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。 下面的示例演示结果时`Option Strict`是`On`。  
  
 [!code-vb[VbVbalrOperators#53](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_2.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#51](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_4.vb)]  
  
 下面的示例演示结果时`Option Strict`是`Off`。  
  
 [!code-vb[VbVbalrOperators#54](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_5.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#52](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_6.vb)]  
  
 若要消除混淆，应使用`&`运算符而不是`+`的串联。  
  
## <a name="see-also"></a>另请参阅  
 [& 运算符](../../../visual-basic/language-reference/operators/concatenation-operator.md)  
 [串联运算符](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [在 Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)
