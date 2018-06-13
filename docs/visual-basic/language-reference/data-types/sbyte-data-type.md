---
title: SByte 数据类型 (Visual Basic)
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20a5a9182da50345f97331e6f01e0e3665a2a61c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591416"
---
# <a name="sbyte-data-type-visual-basic"></a>SByte 数据类型 (Visual Basic)

存储带符号的 8 位 （1 个字节） 整数，值的范围从-128 到 127。  
  
## <a name="remarks"></a>备注

使用`SByte`数据类型包含不需要的完整数据宽度的整数值`Integer`甚至数据长度的一半的`Short`。 在某些情况下，公共语言运行时可能能够包你`SByte`紧密合作，以节省内存消耗的变量。

`SByte` 的默认值为 0。

## <a name="literal-assignments"></a>文本分配
  
你可以声明并初始化`SByte`变量中将其分配为十进制文本、 八进制文本中，为十六进制文本、 （开始或利用 Visual Basic 自 2017 年 1） 二进制文本。

在下面的示例中，整数等于表示为十进制数字，十六进制，-102 和二进制文本分配给`SByte`值。 此示例需要使用编译`/removeintchecks`编译器开关。

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> 使用前缀`&h`或`&H`来表示为十六进制文本、 前缀`&b`或`&B`来表示二进制文字和前缀`&o`或`&O`来表示八进制文本。 十进制文本没有前缀。

从 Visual Basic 自 2017 年开始，你还可以使用下划线字符， `_`，作为数字分隔符以增强可读性，如以下示例所示。

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

从 Visual Basic 15.5 开始，你还可以使用下划线字符 (`_`) 为之间的前缀和十六进制、 二进制文件，或八进制数字的前导分隔符。 例如：

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

如果整数文本在 `SByte` 范围之外（即，如果它小于 <xref:System.SByte.MinValue?displayProperty=nameWithType> 或大于 <xref:System.SByte.MaxValue?displayProperty=nameWithType>），会发生编译错误。 当一个整数文本具有无后缀[整数](integer-data-type.md)这方面的推断。 如果整数文本之外的范围，则`Integer`类型，[长](long-data-type.md)这方面的推断。 这意味着，在前面的示例中，数字文本`0x9A`和`0b10011010`都会被解释为 32 位有符号整数值为 156，这超出<xref:System.SByte.MaxValue?displayProperty=nameWithType>。 若要成功编译代码如下将分配到一个非十进制整数`SByte`，你可以执行以下任一操作：

- 通过使用编译禁用整数边界检查`/removeintchecks`编译器开关。

- 使用[键入字符](../../programming-guide\language-features\data-types/type-characters.md)明确地定义你想要分配到的文本值`SByte`。 下面的示例将负文本`Short`值赋给`SByte`。 请注意，负数，必须设置数值的高序位字的高顺序位。 对于本示例中，这位的文本的 15`Short`值。

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>编程提示
  
-   **CLS 遵从性。** `SByte`数据类型不是属于[公共语言规范](http://www.ecma-international.org/publications/standards/Ecma-335.htm)(CLS)，因此符合 cls 的代码不能使用的组件，使用它。

-   **扩大转换。** `SByte`数据类型加宽到`Short`， `Integer`， `Long`， `Decimal`， `Single`，和`Double`。 这意味着你可以将转换`SByte`到而不会遇到这些类型的任何<xref:System.OverflowException?displayProperty=nameWithType>错误。
  
-   **类型字符。** `SByte` 不包含文本类型字符或标识符类型字符。  
  
-   **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.SByte?displayProperty=nameWithType> 结构。
  
## <a name="see-also"></a>请参阅

 <xref:System.SByte?displayProperty=nameWithType>  
 [数据类型](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Short 数据类型](../../../visual-basic/language-reference/data-types/short-data-type.md)  
 [Integer 数据类型](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Long 数据类型](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
