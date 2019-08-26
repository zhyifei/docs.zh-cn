---
title: + 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
ms.openlocfilehash: ab18a7137a31ed8e616f465e7d617305c96d7b10
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943022"
---
# <a name="-operator-visual-basic"></a>+ 运算符 (Visual Basic)
将两个数相加或返回数值表达式的正值。 还可用于连接两个字符串表达式。  
  
## <a name="syntax"></a>语法  
  
```vb
expression1 + expression2  
- or -  
+ expression1  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`expression1`|必需。 任何数值或字符串表达式。|  
|`expression2`|必需, `+`除非操作员计算负值。 任何数值或字符串表达式。|  
  
## <a name="result"></a>结果  
 如果`expression1` 和`expression2`均为数值, 则结果为其算术和。  
  
 如果`expression2`不存在, 则`+`运算符为表达式的未更改值的*一元*标识运算符。 从这种意义上讲, 操作包括保留的符号`expression1`, 因此如果`expression1`为负, 则结果为负。  
  
 如果`expression1` 和`expression2`都是字符串, 则结果是其值的串联。  
  
 如果`expression1` 和`expression2`属于混合类型, 则执行的操作取决于它们的类型、内容和[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)的设置。 有关详细信息, 请参阅 "备注" 中的表。  
  
## <a name="supported-types"></a>支持的类型  
 所有数值类型, 包括无符号和浮点类型以及`Decimal` `String`和。  
  
## <a name="remarks"></a>备注  
 通常, `+`如果可能, 将执行算术加法运算, 并且仅当两个表达式都是字符串时才会进行连接。  
  
 如果两个表达式均`Object`为, 则 Visual Basic 执行以下操作。  
  
|表达式的数据类型|编译器操作|  
|---|---|  
|这两个表达式均为数值`SByte`数据`Byte`类型 ( `UShort`、 `Integer` `Short` `UInteger` 、、`Decimal`、 `ULong` 、、`Double`、、、或) `Long` `Single`|把. Result 数据类型是适用于`expression1`和`expression2`的数据类型的数值类型。 请参阅[运算符结果的数据类型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)中的 "整数算法" 表。|  
|这两个表达式的类型为`String`|起来.|  
|一个表达式为数值数据类型, 另一个表达式为字符串|如果`Option Strict` 为`On`, 则生成编译器错误。<br /><br /> 如果`Option Strict`为`Off` ,则`Double`将隐式转换为并添加。`String`<br /><br /> 如果无法转换为`Double`, 则引发<xref:System.InvalidCastException>异常。 `String`|  
|一个表达式为数值数据类型, 另一个表达式为[Nothing](../../../visual-basic/language-reference/nothing.md)|添加, 其`Nothing`值为零。|  
|一个表达式是字符串, 另一个表达式是`Nothing`|串联, 其`Nothing`值为 ""。|  
  
 如果一个表达式是表达式`Object` , Visual Basic 会执行以下操作。  
  
|表达式的数据类型|编译器操作|  
|---|---|  
|`Object`表达式保存数字值, 另一种是数值数据类型|如果`Option Strict` 为`On`, 则生成编译器错误。<br /><br /> 如果`Option Strict` 为`Off`, 则添加。|  
|`Object`表达式保存一个数字值, 另一个的类型为`String`|如果`Option Strict` 为`On`, 则生成编译器错误。<br /><br /> 如果`Option Strict`为`Off` ,则`Double`将隐式转换为并添加。`String`<br /><br /> 如果无法转换为`Double`, 则引发<xref:System.InvalidCastException>异常。 `String`|  
|`Object`表达式保存一个字符串, 另一个表达式为数值数据类型|如果`Option Strict` 为`On`, 则生成编译器错误。<br /><br /> 如果`Option Strict` `Object` `Double`为`Off`, 则将字符串隐式转换为并添加。<br /><br /> 如果字符串`Object`无法转换为`Double`, 则引发<xref:System.InvalidCastException>异常。|  
|`Object`表达式保存了一个字符串, 另一个的类型为`String`|如果`Option Strict` 为`On`, 则生成编译器错误。<br /><br /> 如果`Option Strict` `Object` `String`为`Off`, 则隐式转换到并连接。|  
  
 如果两个表达式`Object`都是表达式, Visual Basic 将采取以下`Option Strict Off`操作 (仅限)。  
  
|表达式的数据类型|编译器操作|  
|---|---|  
|两`Object`个表达式都保存数字值|把.|  
|这`Object`两个表达式的类型为`String`|起来.|  
|一个`Object`表达式保存一个数字值, 另一个表达式保存一个字符串|将字符串`Object`隐式转换`Double`为并添加。<br /><br /> 如果字符串`Object`不能转换为数字值, 则<xref:System.InvalidCastException>引发异常。|  
  
 如果其中`Object`一个表达式的计算结果<xref:System.DBNull>为[Nothing](../../../visual-basic/language-reference/nothing.md)或`String` , 则`+`运算符将其视为值为 "" 的。  
  
> [!NOTE]
> 使用`+`运算符时, 可能无法确定是进行加法还是字符串串联。 `&`使用运算符进行串联以消除多义性, 并提供自文档代码。  
  
## <a name="overloading"></a>重载  
 运算符可以重载, 这意味着当操作数具有该类或结构的类型时, 该类或结构可以重新定义其行为。 `+` 如果你的代码在该类或结构上使用此运算符, 请确保了解其重新定义的行为。 有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`+`运算符来添加数字。 如果操作数均为数值, 则 Visual Basic 计算算术结果。 算术结果表示两个操作数之和。  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 还可以使用`+`运算符来串联字符串。 如果两个操作数都是字符串, Visual Basic 将它们连接起来。 连接结果表示一个字符串, 该字符串包含两个操作数的内容。  
  
 如果操作数属于混合类型, 则结果取决于[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)的设置。 下面的示例演示了在为`Option Strict` `On`时的结果。  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 下面的示例演示了在为`Option Strict` `Off`时的结果。  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 为了消除多义性, 应使用`&`运算符`+`而不是串联。  
  
## <a name="see-also"></a>请参阅

- [& 运算符](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [串联运算符](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)
