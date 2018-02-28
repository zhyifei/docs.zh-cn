---
title: "类型字符 (Visual Basic)"
ms.custom: 
ms.date: 01/31/2018
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
author: rpetrusha
ms.author: ronpet
ms.manager: wpickett
ms.openlocfilehash: 20a9a30689fb62a6956987b06470e76eeb42ebab
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="type-characters-visual-basic"></a>键入字符 (Visual Basic)

除了在声明语句中指定的数据类型，你可以强制使用某些编程元素的数据类型*键入字符*。 类型字符必须紧跟具有不允许插入字符的任何类型的元素。

类型字符不是名称的元素的一部分。 使用类型字符定义的元素可以引用不带类型字符。

## <a name="identifier-type-characters"></a>标识符类型字符

Visual Basic 提供的一组*标识符类型字符*，可用于在声明中指定的变量或常量的数据类型。 下表显示可用的标识符类型字符及其用法的示例。
  
|标识符类型字符|数据类型|示例|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 任何标识符类型字符存在`Boolean`， `Byte`， `Char`， `Date`， `Object`， `SByte`， `Short`， `UInteger`， `ULong`，或`UShort`数据类型或任何复合数据类型，如数组或结构。

在某些情况下，你可以将附加`$`字符到 Visual Basic 函数，例如`Left$`而不是`Left`，以获取类型的返回的值`String`。

在所有情况下，标识符类型字符必须紧跟标识符名称。

## <a name="literal-type-characters"></a>文本类型字符

A*文本*是数据类型的特定值的文本表示。  

### <a name="default-literal-types"></a>默认文本类型

文本的形式通常出现在你的代码中确定其数据类型。 下表显示这些默认类型。  
  
|文本形式的文本|默认数据类型|示例|  
|-----------------------------|-----------------------|-------------|  
|数值，没有小数部分|`Integer`|`2147483647`|  
|数值，没有小数部分，对于来说太大 `Integer`|`Long`|`2147483648`|  
|数值，小数部分|`Double`|`1.2`|  
|用双引号括起来|`String`|`"A"`|  
|包含在数字符号|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a>强制文本类型

Visual Basic 提供的一组*文本类型字符*，你可以使用强制文本采用其窗体的数据类型不是一个指示。 通过将字符追加到文本末尾来执行此操作。 下表显示可用的文本类型字符及其用法的示例。
  
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

没有文本类型字符存在`Boolean`， `Byte`， `Date`， `Object`， `SByte`，或`String`数据类型或任何复合数据类型，如数组或结构。

文本也可以使用标识符类型字符 (`%`， `&`， `@`， `!`， `#`， `$`)，如可以变量、 常量和表达式。 但是，文本类型字符 (`S`， `I`， `L`， `D`， `F`， `R`， `C`) 可以仅用于文本。

在所有情况下，文本类型字符必须紧跟文字值。

## <a name="hexadecimal-binary-and-octal-literals"></a>十六进制、 二进制和八进制文本

编译器通常会解释整数文本处于十进制 (基数为 10) 数字系统。 你还可以定义一个整数为十六进制 (基数为 16) 数字，`&H`前缀，为带二进制 (基数为 2) 数字`&B`前缀，八进制 (基数为 8)，以及带有`&O`前缀。 跟在前缀的数字必须适合于数字系统。 下表阐释了这一点。  
  
|数基|前缀|有效的数字值|示例|
|-----------------|------------|------------------------|-------------|
|十六进制（以 16 为基数）|`&H`|0-9 和 A F|`&HFFFF`|
|二进制 (基数为 2)|`&B`|0-1|`&B01111100`|
|八进制（以 8 为基数）|`&O`|0-7|`&O77`|

从 Visual Basic 自 2017 年开始，你可以使用下划线字符 (`_`) 作为组分隔符以增强整型文本的可读性。 下面的示例使用`_`字符，以便将分组到 8 位组的二进制文本：

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

你可以按照在前缀的文本与文本类型字符。 下面的示例演示了此过程。

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

在前面的示例中， `counter` -32768，十进制值和`flags`32768 的十进制值。

从 Visual Basic 15.5 开始，你还可以使用下划线字符 (`_`) 为之间的前缀和十六进制、 二进制文件，或八进制数字的前导分隔符。 例如:

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a>请参阅

 [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [在 Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
