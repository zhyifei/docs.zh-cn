---
title: Char 数据类型
ms.date: 07/20/2015
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
ms.openlocfilehash: 1ed5b19a307d094fc1d5a6bb0251c57052dc9bc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344052"
---
# <a name="char-data-type-visual-basic"></a>Char 数据类型 (Visual Basic)

保存16位（2字节）无符号码位，范围介于0到65535之间。 每个*码位*或字符代码都表示一个 Unicode 字符。

## <a name="remarks"></a>备注

如果只需要保存单个字符，而不需要 `String`开销，请使用 `Char` 数据类型。 在某些情况下，可以使用 `Char()`，`Char` 元素的数组来保存多个字符。

`Char` 的默认值为码位为0的字符。

## <a name="unicode-characters"></a>Unicode 字符

Unicode 的第一个128码位（0–127）对应于标准美式键盘上的字母和符号。 这前128码位与 ASCII 字符集定义的代码点相同。 第二个128码位（128–255）表示特殊字符，例如基于拉丁语的字母表号、重音、货币符号和分数。 Unicode 对各种符号（包括全球文本字符、音调符号和数学符号和技术符号）使用剩余的代码点（256-65535）。

您可以使用 `Char` 变量上 <xref:System.Char.IsDigit%2A> 和 <xref:System.Char.IsPunctuation%2A> 等方法来确定其 Unicode 分类。

## <a name="type-conversions"></a>类型转换

Visual Basic 不会直接在 `Char` 与数值类型之间转换。 您可以使用 <xref:Microsoft.VisualBasic.Strings.Asc%2A> 或 <xref:Microsoft.VisualBasic.Strings.AscW%2A> 函数将 `Char` 值转换为表示其码位的 `Integer`。 您可以使用 <xref:Microsoft.VisualBasic.Strings.Chr%2A> 或 <xref:Microsoft.VisualBasic.Strings.ChrW%2A> 函数将 `Integer` 值转换为具有该码位的 `Char`。

如果类型检查开关（ [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)）为 on，则必须将文本类型字符追加到单字符字符串文本，才能将其标识为 `Char` 数据类型。 下面的示例阐释了这一点。 第一次分配给 `charVar` 变量会生成编译器错误[BC30512](../../misc/bc30512.md) ，因为 `Option Strict` 为 on。 第二个编译成功，因为 `c` 文本类型字符将文本标识为 `Char` 值。

```vb
Option Strict On

Module CharType
    Public Sub Main()
        Dim charVar As Char

        ' This statement generates compiler error BC30512 because Option Strict is On.  
        charVar = "Z"  

        ' The following statement succeeds because it specifies a Char literal.  
        charVar = "Z"c
    End Sub
End Module
```

## <a name="programming-tips"></a>编程提示

- **负数。** `Char` 是一种无符号类型，不能表示负值。 在任何情况下，不应使用 `Char` 来保存数值。

- **互操作注意事项。** 如果你使用不是为 .NET Framework 编写的组件（如自动化或 COM 对象）进行交互，请记住，在其他环境中字符类型具有不同的数据宽度（8位）。 如果将一个8位参数传递给此类组件，请在新的 Visual Basic 代码中将其声明为 `Byte` 而不是 `Char`。

- **扩大.** `Char` 的数据类型扩大到 `String`。 这意味着你可以将 `Char` 转换为 `String`，而不会遇到 <xref:System.OverflowException?displayProperty=nameWithType>。

- **键入字符。** 将文本类型字符追加 `C` 为单字符字符串会将其强制转换为 `Char` 的数据类型。 `Char` 没有标识符类型字符。

- **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.Char?displayProperty=nameWithType> 结构。

## <a name="see-also"></a>另请参阅

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
- [String 数据类型](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [如何：调用采用无符号类型的 Windows 函数](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
