---
title: 类型字符
ms.date: 01/31/2018
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals [Visual Basic]
- F literal type character [Visual Basic]
- '& identifier type character'
- type characters [Visual Basic]
- octal literals [Visual Basic]
- literals [Visual Basic], hexadecimal
- '&O prefix for octal values'
- literals [Visual Basic], default types
- defaults, literal types
- C literal type character [Visual Basic]
- type characters [Visual Basic], literal
- $ identifier type character
- L literal type character [Visual Basic]
- UI literal type characters [Visual Basic]
- default literal types [Visual Basic]
- D literal type character [Visual Basic]
- literals [Visual Basic], octal
- S literal type character [Visual Basic]
- '! identifier type character'
- US literal type characters [Visual Basic]
- '% identifier type character'
- data types [Visual Basic], type characters
- characters [Visual Basic], identifier type
- type characters [Visual Basic], identifier
- '# identifier type character'
- identifier type characters [Visual Basic]
- literal type characters [Visual Basic]
- I literal type character [Visual Basic]
- R literal type character [Visual Basic]
- '@ identifier type character'
- UL literal type characters [Visual Basic]
- literal types [Visual Basic], default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
ms.openlocfilehash: 628461c8136946dd902c0a52048eee7c516c52cd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352925"
---
# <a name="type-characters-visual-basic"></a>类型字符 (Visual Basic)

除了在声明语句中指定数据类型之外，还可以使用*类型字符*强制某些编程元素的数据类型。 类型字符必须紧跟在元素之后，无任何类型的插入字符。

类型字符不是元素名称的一部分。 在不使用类型字符的情况下，可以引用使用类型字符定义的元素。

## <a name="identifier-type-characters"></a>标识符类型字符

Visual Basic 提供一组*标识符类型字符*，可以在声明中使用这些字符来指定变量或常量的数据类型。 下表显示了可用的标识符类型字符和用法示例。
  
|标识符类型字符|数据类型|示例|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 `Boolean`、`Byte`、`Char`、`Date`、`Object`、`SByte`、`Short`、`UInteger`、`ULong`或 `UShort` 数据类型或任何复合数据类型（例如数组或结构）都不存在标识符类型字符。

在某些情况下，可以将 `$` 字符追加到 Visual Basic 函数，例如 `Left$` 而不是 `Left`，以获取 `String`类型的返回值。

在所有情况下，标识符类型字符都必须紧跟在标识符名称后面。

## <a name="literal-type-characters"></a>文本类型字符

*文本*是数据类型的特定值的文本表示形式。  

### <a name="default-literal-types"></a>默认文本类型

在代码中显示的文本形式通常会确定其数据类型。 下表显示了这些默认类型。  
  
|文本格式的文本|默认数据类型|示例|  
|-----------------------------|-----------------------|-------------|  
|数值，无小数部分|`Integer`|`2147483647`|  
|数值，没有小数部分，太大，无法用于 `Integer`|`Long`|`2147483648`|  
|数值，有小数部分|`Double`|`1.2`|  
|包含在双引号内|`String`|`"A"`|  
|括在数字符号内|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a>强制文本类型

Visual Basic 提供一组*文本类型字符*，您可以使用这些字符强制文本采用其形式所指示的数据类型之外的数据类型。 为此，可将字符追加到文本末尾。 下表显示了可用的文本类型字符，其中包含用法的示例。
  
|文本类型字符|数据类型|示例|  
|----------------------------|---------------|-------------|  
|`S`|`Short`|`I = 347S`|
|`I`|`Integer`|`J = 347I`|
|`L`|`Long`|`K = 347L`|
|`D`|`Decimal`|`X = 347D`|
|`F`|`Single`|`Y = 347F`|
|`R`|`Double`|`Z = 347R`|
|`US`|`UShort`|`L = 347US`|
|`UI`|`UInteger`|`M = 347UI`|
|`UL`|`ULong`|`N = 347UL`|
|`C`|`Char`|`Q = "."C`|

`Boolean`、`Byte`、`Date`、`Object`、`SByte`或 `String` 数据类型或任何复合数据类型（例如数组或结构）都不存在文本类型字符。

文本还可以使用标识符类型字符（`%`、`&`、`@`、`!`、`#`、`$`），就像变量、常量和表达式一样。 但是，文本类型字符（`S`、`I`、`L`、`D`、`F`、`R`、`C`）只能与文本一起使用。

在所有情况下，文本类型字符都必须紧跟在文本值之后。

## <a name="hexadecimal-binary-and-octal-literals"></a>十六进制、二进制和八进制文本

编译器通常将整数文本解释为十进制（基数为10）的数字系统。 你还可以将整数文本定义为带有 `&H` 前缀的十六进制（以16为基数）数字，作为带有 `&B` 前缀的二进制（base 2）号，并将指定为带有 `&O` 前缀的八进制（基数为8）数字。 前缀后面的数字必须适用于数字系统。 下表对此进行了说明。  
  
|数字基数|前缀|有效的数字值|示例|
|-----------------|------------|------------------------|-------------|
|十六进制（以 16 为基数）|`&H`|0-9 和 A-f|`&HFFFF`|
|二进制 （以 2 为基数）|`&B`|0-1|`&B01111100`|
|八进制（以 8 为基数）|`&O`|0-7|`&O77`|

从 Visual Basic 2017 开始，可以使用下划线字符（`_`）作为分组分隔符，以增强整数文本的可读性。 下面的示例使用 `_` 字符将二进制文本分组到8位组中：

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

您可以在文本类型为字符的后面跟有前缀的文本。 下面的示例演示了这一点。

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

在上面的示例中，`counter` 的十进制值为-32768，`flags` 的十进制值为 + 32768。

从 Visual Basic 15.5 开始，还可以使用下划线字符（`_`）作为前缀和十六进制、二进制或八进制数字之间的前导分隔符。 例如：

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a>另请参阅

- [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [数据类型](../../../../visual-basic/language-reference/data-types/index.md)
