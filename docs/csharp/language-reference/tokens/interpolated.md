---
title: $ - 字符串内插（C# 参考）
description: 与传统的字符串复合格式设置相比，字符串内插提供更具可读性且更方便的语法，用于设置字符串输出的格式。
ms.date: 03/26/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6873c3b419323fa9f5523143ad607289b6fd6e2
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="---string-interpolation-c-reference"></a>$ - 字符串内插（C# 参考）

`$` 特殊字符将字符串文本标识为内插字符串。 内插字符串类似于包含内插表达式的模板字符串。 例如，在赋值语句或方法调用中解析内插字符串时，内插表达式替换为其结果的字符串表示形式以生成结果字符串。 此功能在 C# 6 及更高版本中提供。

与使用[字符串复合格式设置](../../../standard/base-types/composite-formatting.md)功能创建格式化字符串相比，字符串内插是更具可读性且更方便的方法。 下面的示例使用了这两种功能生成同样的输出结果：

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

> [!NOTE]
> 字符串开头的 `$` 和 `"` 之间不能有任何空格。 如果有空格，会导致编译时错误。

具备内插表达式的项的结构如下所示：

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

括号中的元素是可选的。 下表对每个元素进行了描述。

|元素|描述|
|-------------|-----------------|
|`interpolatedExpression`|可计算获取要进行格式设置的结果的表达式。 `null` 结果的字符串表示形式为 <xref:System.String.Empty?displayProperty=nameWithType>。|
|`alignment`|常数表达式，它的值定义内插表达式结果的字符串表示形式中的最小字符数。 如果值为正，则字符串表示形式为右对齐；如果值为负，则为左对齐。 有关详细信息，请参阅[对齐组件](../../../standard/base-types/composite-formatting.md#alignment-component)。|
|`formatString`|表达式结果的类型所支持的一个标准格式字符串或自定义格式字符串。 有关更多信息，请参阅[格式字符串组件](../../../standard/base-types/composite-formatting.md#format-string-component)。|

以下示例使用上表中所描述的可选格式设置组件：

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

要在内插字符串生成的文本中包含大括号（“{”或“}”），请使用两个大括号，即“{{”或“}}”。 有关详细信息，请参阅[转义大括号](../../../standard/base-types/composite-formatting.md#escaping-braces)。

因为冒号 (:) 在内插表达式项中具有特殊含义，为了在内插表达式中使用[条件运算符](../operators/conditional-operator.md)，请将表达式放在括号内。

以下示例演示如何将大括号加入到结果字符串中，以及如何在内插表达式中使用条件运算符：

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

逐字内插字符串使用 `$` 字符，后跟 `@` 字符。 有关逐字字符串的详细信息，请参阅[字符串](../keywords/string.md)主题。

> [!NOTE]
> 在逐字内插字符串中，`$` 标记必须出现 `@` 标记之前。

## <a name="implicit-conversions"></a>隐式转换

内插字符串有 3 种隐式类型转换：

1. 将内插字符串转换为 <xref:System.String> 实例，该类例是内插字符串的解析结果，其中内插表达式项被替换为结果的格式设置正确的字符串表示形式。 此类转换使用当前区域性。

1. 将内插字符串转换为表示复合格式字符串的 <xref:System.FormattableString> 变量，同时也将表达式结果格式化。 这允许通过单个 <xref:System.FormattableString> 实例创建多个包含区域性特定内容的结果字符串。 要执行此操作，请调用以下方法之一：

      - <xref:System.FormattableString.ToString> 重载，生成 <xref:System.Globalization.CultureInfo.CurrentCulture> 的结果字符串。
      - <xref:System.FormattableString.Invariant%2A> 方法，生成 <xref:System.Globalization.CultureInfo.InvariantCulture> 的结果字符串。
      - <xref:System.FormattableString.ToString(System.IFormatProvider)> 方法，生成特定区域性的结果字符串。

1. 将内插字符串转换为 <xref:System.IFormattable> 变量，使用此变量也可通过单个 <xref:System.IFormattable> 实例创建多个包含区域性特定内容的结果字符串。

以下示例通过隐式转换为 <xref:System.FormattableString> 来创建特定于区域性的结果字符串：

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-reading"></a>其他阅读材料

如果不熟悉字符串内插，请查看[内插字符串快速入门](../../quick-starts//interpolated-strings.yml)。 请参阅[字符串内插](../../tutorials/string-interpolation.md)教程查看更多相关示例。

## <a name="see-also"></a>请参阅  
 <xref:System.String.Format%2A?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 [复合格式设置](../../../standard/base-types/composite-formatting.md)  
 [字符串](../../../csharp/programming-guide/strings/index.md)  
 [C# 特殊字符](../../../csharp/language-reference/tokens/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 参考](../../../csharp/language-reference/index.md)  