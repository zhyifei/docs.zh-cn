---
title: + 运算符（Visual Basic）
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
ms.openlocfilehash: 3187551afb7d25470f48dad894188766a811bb0a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701000"
---
# <a name="-operator-visual-basic"></a>+ 运算符 (Visual Basic)
将两个数相加或返回数值表达式的正值。 还可用于连接两个字符串表达式。  
  
## <a name="syntax"></a>语法  
  
```vb
expression1 + expression2
```
  
或

```vb  
+expression1  
```  
  
## <a name="parts"></a>部件  
  
|术语|Definition|  
|---|---|  
|`expression1`|必需。 任何数值或字符串表达式。|  
|`expression2`|必需，除非 `+` 运算符计算负值。 任何数值或字符串表达式。|  
  
## <a name="result"></a>结果  
 如果 `expression1` 和 `expression2` 均为数值，则结果是其算术和。  
  
 如果 `expression2` 不存在，则 `+` 运算符为表达式的未更改值的*一元*标识运算符。 从这种意义上讲，操作包括保留 `expression1`的符号，因此如果 `expression1` 为负，则结果为负。  
  
 如果 `expression1` 和 `expression2` 都是字符串，则结果是其值的串联。  
  
 如果 `expression1` 和 `expression2` 属于混合类型，则执行的操作取决于它们的类型、内容和[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)的设置。 有关详细信息，请参阅 "备注" 中的表。  
  
## <a name="supported-types"></a>支持的类型  
 所有数值类型，包括未签名和浮点类型以及 `Decimal`和 `String`。  
  
## <a name="remarks"></a>备注  
 通常，如果可能，`+` 会执行算术加法运算，并且仅当两个表达式都是字符串时才会进行连接。  
  
 如果两个表达式都不是 `Object`，则 Visual Basic 执行以下操作。  
  
|表达式的数据类型|编译器操作|  
|---|---|  
|这两个表达式均为数值数据类型（`SByte`、`Byte`、`Short`、`UShort`、`Integer`、`UInteger`、`Long`、`ULong`、`Decimal`、`Single`或 `Double`）|“添加”。 Result 数据类型是一种适合 `expression1` 和 `expression2`的数据类型的数值类型。 请参阅[运算符结果的数据类型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)中的 "整数算法" 表。|  
|这两个表达式的类型都是 `String`|起来.|  
|一个表达式为数值数据类型，另一个表达式为字符串|如果 `On``Option Strict`，则会生成编译器错误。<br /><br /> 如果 `Off``Option Strict`，则将 `String` 隐式转换为 `Double` 并添加。<br /><br /> 如果 `String` 无法转换为 `Double`，则引发 <xref:System.InvalidCastException> 异常。|  
|一个表达式为数值数据类型，另一个表达式为[Nothing](../../../visual-basic/language-reference/nothing.md)|添加，`Nothing` 值为零。|  
|一个表达式是字符串，另一个表达式是 `Nothing`|串联，`Nothing` 值为 ""。|  
  
 如果一个表达式是 `Object` 表达式，Visual Basic 会执行以下操作。  
  
|表达式的数据类型|编译器操作|  
|---|---|  
|`Object` 表达式保存数字值，另一种是数值数据类型|如果 `On``Option Strict`，则会生成编译器错误。<br /><br /> 如果 `Off``Option Strict`，则添加。|  
|`Object` 表达式保存一个数字值，另一个的类型为 `String`|如果 `On``Option Strict`，则会生成编译器错误。<br /><br /> 如果 `Off``Option Strict`，则将 `String` 隐式转换为 `Double` 并添加。<br /><br /> 如果 `String` 无法转换为 `Double`，则引发 <xref:System.InvalidCastException> 异常。|  
|`Object` 表达式包含一个字符串，另一个是数值数据类型|如果 `On``Option Strict`，则会生成编译器错误。<br /><br /> 如果 `Off``Option Strict`，则将字符串 `Object` 隐式转换为 `Double` 并添加。<br /><br /> 如果字符串 `Object` 无法转换为 `Double`，则引发 <xref:System.InvalidCastException> 异常。|  
|`Object` 表达式保存了一个字符串，另一个的类型为 `String`|如果 `On``Option Strict`，则会生成编译器错误。<br /><br /> 如果 `Off``Option Strict`，则将 `Object` 隐式转换为 `String` 并连接。|  
  
 如果两个表达式都 `Object` 表达式，则 Visual Basic 执行以下操作（仅`Option Strict Off`）。  
  
|表达式的数据类型|编译器操作|  
|---|---|  
|这两个表达式 `Object` 都包含数值|“添加”。|  
|这两个表达式 `Object` 类型 `String`|起来.|  
|一个 `Object` 表达式保存一个数值，另一个表达式保存一个字符串|将字符串 `Object` 隐式转换为 `Double` 并添加。<br /><br /> 如果字符串 `Object` 无法转换为数值，则引发 <xref:System.InvalidCastException> 异常。|  
  
 如果 `Object` 表达式的计算结果均为[Nothing](../../../visual-basic/language-reference/nothing.md)或 <xref:System.DBNull>，则 `+` 运算符将其视为值为 "" 的 `String`。  
  
> [!NOTE]
> 当使用 `+` 运算符时，可能无法确定是进行加法还是字符串串联。 使用 `&` 运算符进行串联以消除多义性，并提供自文档代码。  
  
## <a name="overloading"></a>重载  
 可以*重载*`+` 运算符，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。 如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。 有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用 `+` 运算符来添加数字。 如果操作数均为数值，则 Visual Basic 计算算术结果。 算术结果表示两个操作数之和。  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 你还可以使用 `+` 运算符来串联字符串。 如果两个操作数都是字符串，Visual Basic 将它们连接起来。 连接结果表示一个字符串，该字符串包含两个操作数的内容。  
  
 如果操作数属于混合类型，则结果取决于[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)的设置。 下面的示例演示了 `On``Option Strict` 时的结果。  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 下面的示例演示了 `Off``Option Strict` 时的结果。  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 为了消除多义性，应使用 `&` 运算符而不是 `+` 进行串联。  
  
## <a name="see-also"></a>另请参阅

- [& 运算符](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [串联运算符](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)
