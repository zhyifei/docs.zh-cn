---
title: ".NET 中分析数值字符串"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parsing strings, numeric strings
- numeric strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
ms.assetid: e39324ee-72e5-42d4-a80d-bf3ee7fc6c59
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c9bb58b0d7b45ca197653742844be01ac3bbe41
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-numeric-strings-in-net"></a>NET 中分析数值字符串
所有数字类型都具有两个静态分析方法（`Parse` 和 `TryParse`），可以使用它们将数字的字符串表示形式转换为数字类型。 这两个方法使你可以分析使用[标准数字格式字符串](../../../docs/standard/base-types/standard-numeric-format-strings.md)和[自定义数字格式字符串](../../../docs/standard/base-types/custom-numeric-format-strings.md)中所述的格式字符串生成的字符串。 默认情况下，`Parse` 和 `TryParse` 方法可以成功地将仅包含整数十进制数字的字符串转化为整数值。 它们可以将包含整数和小数十进制数字、组分隔符和十进制分隔符的字符串转换为浮点值。 `Parse` 方法在操作失败时引发异常，而 `TryParse` 方法返回 `false`。  
  
## <a name="parsing-and-format-providers"></a>分析和格式提供程序  
 通常，数值的字符串表示因区域性而异。 数值字符串的元素都会因区域性而异，如货币符号、组（或千位）分隔符和十进制分隔符。 分析方法可隐式或显式使用可以识别这些特定于区域性的变体的格式提供程序。 如果在调用中指定任何格式提供程序`Parse`或`TryParse`方法，与当前线程区域性关联的格式提供程序 (<xref:System.Globalization.NumberFormatInfo>返回对象<xref:System.Globalization.NumberFormatInfo.CurrentInfo%2A?displayProperty=nameWithType>属性) 使用。  
  
 格式提供程序都由<xref:System.IFormatProvider>实现。 此接口具有一个成员，<xref:System.IFormatProvider.GetFormat%2A>方法，其单个参数是<xref:System.Type>对象，表示要设置格式类型。 此方法返回提供格式设置信息的对象。 .NET 支持以下两个<xref:System.IFormatProvider>分析数值字符串的实现：  
  
-   A<xref:System.Globalization.CultureInfo>对象，其<xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=nameWithType>方法返回<xref:System.Globalization.NumberFormatInfo>提供区域性特定格式设置信息的对象。  
  
-   A<xref:System.Globalization.NumberFormatInfo>对象，其<xref:System.Globalization.NumberFormatInfo.GetFormat%2A?displayProperty=nameWithType>方法返回它自身。  
  
 下面的示例尝试将转换到数组中的每个字符串<xref:System.Double>值。 它首先尝试使用反映“英语(美国)”区域性约定的格式提供程序来分析字符串。 如果此操作将引发<xref:System.FormatException>，它将尝试使用来分析字符串的格式提供程序反映法语 （法国） 区域性的约定。  
  
 [!code-csharp[Parsing.Numbers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/formatproviders1.cs#1)]
 [!code-vb[Parsing.Numbers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/formatproviders1.vb#1)]  
  
## <a name="parsing-and-numberstyles-values"></a>分析和 NumberStyles 值  
 由定义分析操作可以处理的样式元素 （如空白区域、 组分隔符和小数点分隔符）<xref:System.Globalization.NumberStyles>枚举值。 默认情况下，表示整数值的字符串通过使用分析<xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType>值，该值允许仅允许数字、 前导和尾随空格和前导符号。 表示浮点值的字符串分析的组合使用<xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType>和<xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>值; 以及前导和尾随空白、 前导符号、 小数分隔符、 一组此复合样式允许十进制数字分隔符和指数。 通过调用的重载`Parse`或`TryParse`包含类型的参数方法中，<xref:System.Globalization.NumberStyles>和设置一个或多个<xref:System.Globalization.NumberStyles>标志，你可以控制可分析操作出现在字符串中的样式元素成功。  
  
 例如，包含组分隔符的字符串使用 <xref:System.Int32> 方法不能转换为 <xref:System.Int32.Parse%28System.String%29?displayProperty=nameWithType> 值。 但是，如果使用 <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType> 标记，可成功转换，如下面的示例所示。  
  
 [!code-csharp[Parsing.Numbers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/styles1.cs#2)]
 [!code-vb[Parsing.Numbers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/styles1.vb#2)]  
  
> [!WARNING]
>  分析操作始终使用特定区域性的格式设置约定。 如果你不通过传递指定区域性<xref:System.Globalization.CultureInfo>或<xref:System.Globalization.NumberFormatInfo>对象，使用与当前线程关联的区域性。  
  
 下表列出的成员<xref:System.Globalization.NumberStyles>枚举并说明它们对在分析操作的效果。  
  
|NumberStyles 值|对要分析的字符串的影响|  
|------------------------|---------------------------------------|  
|<xref:System.Globalization.NumberStyles.None?displayProperty=nameWithType>|仅允许数字。|  
|<xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>|允许十进制分隔符和小数数字。 对于整数值，仅允许将零作为小数数字。 有效的小数点分隔符由<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A?displayProperty=nameWithType>或<xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A?displayProperty=nameWithType>属性。|  
|<xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType>|“e”或“E”字符可以用于指示指数记数法。 请参阅<xref:System.Globalization.NumberStyles>有关其他信息。|  
|<xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>|允许前导空格。|  
|<xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>|允许尾随空格。|  
|<xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>|正号或负号可以位于数字前面。|  
|<xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>|正号或负号可以位于数字后面。|  
|<xref:System.Globalization.NumberStyles.AllowParentheses?displayProperty=nameWithType>|括号可以用于指示负值。|  
|<xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>|允许组分隔符。 组分隔符字符由<xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A?displayProperty=nameWithType>或<xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A?displayProperty=nameWithType>属性。|  
|<xref:System.Globalization.NumberStyles.AllowCurrencySymbol?displayProperty=nameWithType>|允许货币符号。 由定义的货币符号<xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A?displayProperty=nameWithType>属性。|  
|<xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>|要分析的字符串解释为十六进制数。 它可以包含十六进制数 0-9、A-F 和 a-f。 此标志只能用于分析整数值。|  
  
 此外，<xref:System.Globalization.NumberStyles>枚举提供了以下复合样式，其中包括多个<xref:System.Globalization.NumberStyles>标志。  
  
|复合 NumberStyles 值|包括成员|  
|----------------------------------|----------------------|  
|<xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType>|包括<xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>， <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>，和<xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>样式。 这是用于分析整数值的默认样式。|  
|<xref:System.Globalization.NumberStyles.Number?displayProperty=nameWithType>|包括<xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>， <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>， <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>， <xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>， <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>，和<xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>样式。|  
|<xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType>|包括<xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>， <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>， <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>， <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>，和<xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType>样式。|  
|<xref:System.Globalization.NumberStyles.Currency?displayProperty=nameWithType>|包括之外的所有样式<xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType>和<xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>。|  
|<xref:System.Globalization.NumberStyles.Any?displayProperty=nameWithType>|包括之外的所有样式<xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>。|  
|<xref:System.Globalization.NumberStyles.HexNumber?displayProperty=nameWithType>|包括<xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>， <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>，和<xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>样式。|  
  
## <a name="parsing-and-unicode-digits"></a>分析和 Unicode 数字  
 Unicode 标准为各种书写系统中的数字定义码位。 例如，从 U+0030 到 U+0039 的码位表示从 0 到 9 的基本拉丁文数字，从 U+09E6 到 U+09EF 的码位表示从 0 到 9 的孟加拉文数字，而从 U+FF10 到 U+FF19 的码位表示从 0 到 9 的全角数字。 但是，分析方法唯一可识别的数字是具有 U+0030 到 U+0039 的码位的基本拉丁文数字 0-9。 如果将数值分析方法传递一个字符串包含任何其他数字，则该方法将引发<xref:System.FormatException>。  
  
 下面的示例使用<xref:System.Int32.Parse%2A?displayProperty=nameWithType>方法，以便分析在不同的书写体系中包含的数字的字符串。 正如示例输出所示，虽然尝试分析基本拉丁文数字获得成功，但分析全角、阿拉伯 - 印度文以及孟加拉文数字的尝试将失败。  
  
 [!code-csharp[Parsing.Numbers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/unicode1.cs#3)]
 [!code-vb[Parsing.Numbers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/unicode1.vb#3)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Globalization.NumberStyles>  
 [分析字符串](../../../docs/standard/base-types/parsing-strings.md)  
 [格式设置类型](../../../docs/standard/base-types/formatting-types.md)
