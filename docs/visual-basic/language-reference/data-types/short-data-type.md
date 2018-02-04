---
title: "Short 数据类型 (Visual Basic)"
ms.date: 01/31/2018
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
author: rpetrusha
ms.author: ronpet
f1_keywords:
- vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: 10c9869d4fb84cd013b22bc791bd31fad745f3d3
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="short-data-type-visual-basic"></a>Short 数据类型 (Visual Basic)
保存有符号 16 位 （2 个字节） 整数，值的范围从-32768 到 32767。  
  
## <a name="remarks"></a>备注  
 使用`Short`数据类型包含不需要的完整数据宽度的整数值`Integer`。 在某些情况下，公共语言运行时可以 pack 你`Short`紧密合作，以节省内存消耗的变量。  
  
 `Short` 的默认值为 0。  
  
## <a name="literal-assignments"></a>文本分配

你可以声明并初始化`Short`变量中将其分配为十进制文本、 八进制文本中，为十六进制文本、 （开始或利用 Visual Basic 自 2017 年 1） 二进制文本。 如果整数文本在 `Short` 范围之外（即，如果它小于 <xref:System.Int16.MinValue?displayProperty=nameWithType> 或大于 <xref:System.Int16.MaxValue?displayProperty=nameWithType>），会发生编译错误。

在下面的示例中，整数等于 1,034，表示为十进制数字，十六进制，和从隐式转换二进制文本[整数](integer-data-type.md)到`Short`值。

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> 使用前缀`&h`或`&H`来表示为十六进制文本、 前缀`&b`或`&B`来表示二进制文字和前缀`&o`或`&O`来表示八进制文本。 十进制文本没有前缀。

从 Visual Basic 自 2017 年开始，你还可以使用下划线字符， `_`，作为数字分隔符以增强可读性，如以下示例所示。

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

从 Visual Basic 15.5 开始，你还可以使用下划线字符 (`_`) 为之间的前缀和十六进制、 二进制文件，或八进制数字的前导分隔符。 例如:

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

此外可以包括数值`S`[键入字符](../../programming-guide\language-features\data-types/type-characters.md)来表示`Short`数据类型，如以下示例所示。

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a>编程提示

-   **扩大转换。** `Short`数据类型加宽到`Integer`， `Long`， `Decimal`， `Single`，或`Double`。 这意味着，你可以将 `Short` 转换为这些类型中的任意类型，而不会遇到 <xref:System.OverflowException?displayProperty=nameWithType> 错误。  
  
-   **类型字符。** 将文本类型字符 `S` 追加到文本会将其强制转换为 `Short` 数据类型。 `Short`中有任何标识符类型字符。  
  
-   **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.Int16?displayProperty=nameWithType> 结构。  
  
## <a name="see-also"></a>请参阅

 <xref:System.Int16?displayProperty=nameWithType>  
 [数据类型](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Integer 数据类型](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Long 数据类型](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
