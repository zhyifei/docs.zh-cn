---
title: "在 .NET Framework 中分析日期和时间字符串"
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
- parsing strings, date and time strings
- date and time strings
- ParseExact method
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- DateTime object
- time strings
ms.assetid: 43bae51e-9b1d-41a6-a187-772c0d096d90
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6e3ef01abdb615b2850b5a9d07e1208ee22eda95
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="parsing-date-and-time-strings-in-net"></a>分析 .NET 中的日期和时间字符串
分析方法将日期和时间的字符串表示形式转换为相当的 <xref:System.DateTime> 对象。 <xref:System.DateTime.Parse%2A> 和 <xref:System.DateTime.TryParse%2A> 方法可转换日期和时间的多个常见表示形式中的任何一个。 <xref:System.DateTime.ParseExact%2A> 和 <xref:System.DateTime.TryParseExact%2A> 方法可转换符合日期和时间格式字符串指定的模式的字符串表示形式。 （请参见有关[标准日期和时间格式字符串](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)和[自定义日期和时间格式字符串](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)的主题。）  
  
 分析受提供信息（如用于日期和时间分隔符的字符串，以及月、日和纪元的名称）的格式提供程序影响。 格式提供程序是当前的 <xref:System.Globalization.DateTimeFormatInfo> 对象，由当前线程区域性隐式提供或由分析方法的 <xref:System.IFormatProvider> 参数显式提供。 对于 <xref:System.IFormatProvider> 参数，应指定表示区域性的 <xref:System.Globalization.CultureInfo> 对象，或指定 <xref:System.Globalization.DateTimeFormatInfo> 对象。  
  
 要分析的日期的字符串表示形式必须包含月份以及至少日或年。 时间的字符串表示形式必须包含小时以及至少分钟或 AM/PM 指示符。 但是，分析会在可能时为省略的组成部分提供默认值。 缺失日期默认为当前日期，缺失年份默认为当前年份，缺失的月中几号默认为月的第一天，缺失时间默认值为午夜。  
  
 如果字符串表示形式仅指定时间，分析方法返回 <xref:System.DateTime> 对象，它的 <xref:System.DateTime.Year%2A>、<xref:System.DateTime.Month%2A> 和 <xref:System.DateTime.Day%2A> 属性设置为 <xref:System.DateTime.Today%2A> 属性的相应值。 不过，如果在分析方法中指定了 <xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault> 常量，生成的年、月和日属性值设置为 `1`。  
  
 除了日期和时间组成部分，日期和时间的字符串表示形式还可以包含指示时间与协调世界时 (UTC) 相差多少的偏移量。 例如，字符串“2/14/2007 5:32:00 -7:00”定义比 UTC 早七个小时的时间。 如果在时间的字符串表示形式中省略了偏移，分析方法返回 <xref:System.DateTime> 对象，它的 <xref:System.DateTime.Kind%2A> 属性设置为 <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>。 如果指定了偏移，分析方法返回 <xref:System.DateTime> 对象，它的 <xref:System.DateTime.Kind%2A> 属性设置为 <xref:System.DateTimeKind.Local>，且值调整为采用计算机的本地时区。 可以修改此行为，具体是结合使用 <xref:System.Globalization.DateTimeStyles> 常量和分析方法。  
  
 格式提供程序还用于解释不明确的数字日期。 例如，不清楚字符串“02/03/04”所表示的日期的哪些组成部分是月、日和年。 在这种情况下，组成部分根据格式提供程序中相似日期格式的顺序进行解释。  
  
## <a name="parse"></a>Parse  
 下面的代码示例展示了如何使用 Parse 方法，将字符串转换为 DateTime。 此示例使用与当前线程关联的区域性执行分析。 如果与当前区域性关联的 <xref:System.Globalization.CultureInfo> 无法分析输入字符串，则会抛出 <xref:System.FormatException>。  
  
 [!code-csharp[Parsing.DateAndTime#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example.cs#1)]
 [!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example.vb#1)]  
  
 还可以指定设置为对象定义的区域性之一的 CultureInfo，也可以指定 <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> 属性返回的标准 <xref:System.Globalization.DateTimeFormatInfo> 对象之一。 下面的代码示例使用格式提供程序将德语字符串分析为 DateTime。 定义和传递的是表示 de-DE 区域性的 CultureInfo，其中字符串正在分析中，以确保成功分析此特定字符串。 这会排除 CurrentThread 的 CurrentCulture 中的任何设置。  
  
 [!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example2.cs#2)]
 [!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example2.vb#2)]  
  
 不过，虽然可以使用 <xref:System.DateTime.Parse%2A> 方法重载指定自定义格式提供程序，但此方法不支持使用非标准格式提供程序。 若要分析非标准格式的日期和时间，请改用 <xref:System.DateTime.ParseExact%2A> 方法。  
  
 下面的代码示例使用 <xref:System.Globalization.DateTimeStyles> 枚举，指定不得将字符串未定义字段的当前日期和时间信息添加到 DateTime。  
  
 [!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example3.cs#3)]
 [!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example3.vb#3)]  
  
## <a name="parseexact"></a>ParseExact  
 <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> 方法将符合指定字符串模式的字符串转换为 DateTime 对象。 如果传递到此方法的字符串未采用指定格式，将会抛出 <xref:System.FormatException>。 可以指定一种标准日期和时间格式说明符或自定义日期和时间格式说明符的有限组合。 使用自定义格式说明符可以构造自定义识别字符串。 有关说明符的说明，请参见有关[标准日期和时间格式字符串](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)和[自定义日期和时间格式字符串](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)的主题。  
  
 <xref:System.DateTime.ParseExact%2A> 方法的每个重载还包含 <xref:System.IFormatProvider> 参数，通常用于提供有关字符串格式设置的区域性专用信息。 通常情况下，此 <xref:System.IFormatProvider> 对象为 <xref:System.Globalization.CultureInfo> 对象，表示标准区域性或 <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> 属性返回的 <xref:System.Globalization.DateTimeFormatInfo> 对象。 不过，与其他日期和时间分析函数不同，此方法还支持 <xref:System.IFormatProvider>，用于定义非标准日期和时间格式。  
  
 在下面的代码示例中，向 ParseExact 方法传递了要分析的字符串对象，后面依次跟的是格式说明符和 CultureInfo 对象。 此 ParseExact 方法只能分析在 en-US 区域性中采用长日期模式的字符串。  
  
 [!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example4.cs#4)]
 [!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example4.vb#4)]  
  
## <a name="see-also"></a>请参阅  
 [Parsing Strings](../../../docs/standard/base-types/parsing-strings.md)  
 [格式设置类型](../../../docs/standard/base-types/formatting-types.md)  
 [.NET 中的类型转换](../../../docs/standard/base-types/type-conversion.md)
