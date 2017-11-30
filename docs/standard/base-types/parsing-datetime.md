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
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1beceb2b2d32c500e73cd7786c480fcd84c3001c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-date-and-time-strings-in-net"></a>分析日期和时间字符串.NET 中
分析方法转换为等效的字符串表示形式的日期和时间<xref:System.DateTime>对象。 <xref:System.DateTime.Parse%2A>和<xref:System.DateTime.TryParse%2A>的方法将转换的任何几个常见表示形式的日期和时间。 <xref:System.DateTime.ParseExact%2A>和<xref:System.DateTime.TryParseExact%2A>方法将符合的字符串表示形式转换为指定的日期和时间格式字符串的模式。 （请参见有关[标准日期和时间格式字符串](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)和[自定义日期和时间格式字符串](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)的主题。）  
  
 分析受提供信息（如用于日期和时间分隔符的字符串，以及月、日和纪元的名称）的格式提供程序影响。 使用格式提供程序是当前<xref:System.Globalization.DateTimeFormatInfo>对象，由当前线程区域性或显式隐式提供<xref:System.IFormatProvider>分析方法的参数。 有关<xref:System.IFormatProvider>参数，指定<xref:System.Globalization.CultureInfo>对象，表示区域性或<xref:System.Globalization.DateTimeFormatInfo>对象。  
  
 要分析的日期的字符串表示形式必须包含月份以及至少日或年。 时间的字符串表示形式必须包含小时以及至少分钟或 AM/PM 指示符。 但是，分析会在可能时为省略的组成部分提供默认值。 缺失日期默认为当前日期，缺失年份默认为当前年份，缺失的月中几号默认为月的第一天，缺失时间默认值为午夜。  
  
 如果字符串表示形式指定仅在时间，则分析将返回<xref:System.DateTime>对象其<xref:System.DateTime.Year%2A>， <xref:System.DateTime.Month%2A>，和<xref:System.DateTime.Day%2A>属性设置为对应的值<xref:System.DateTime.Today%2A>属性。 但是，如果<xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault>常量指定分析方法、 生成年、 月和日属性设置为值`1`。  
  
 除了日期和时间组成部分，日期和时间的字符串表示形式还可以包含指示时间与协调世界时 (UTC) 相差多少的偏移量。 例如，字符串“2/14/2007 5:32:00 -7:00”定义比 UTC 早七个小时的时间。 如果偏移量的时间的字符串表示形式中省略，则分析将返回<xref:System.DateTime>对象其<xref:System.DateTime.Kind%2A>属性设置为<xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>。 如果指定偏移量，则分析将返回<xref:System.DateTime>对象其<xref:System.DateTime.Kind%2A>属性设置为<xref:System.DateTimeKind.Local>且其值调整到您的计算机的本地时区。 你可以通过修改此行为<xref:System.Globalization.DateTimeStyles>常量使用分析方法。  
  
 格式提供程序还用于解释不明确的数字日期。 例如，不清楚字符串“02/03/04”所表示的日期的哪些组成部分是月、日和年。 在这种情况下，组成部分根据格式提供程序中相似日期格式的顺序进行解释。  
  
## <a name="parse"></a>Parse  
 下面的代码示例演示如何使用**分析**方法将字符串转换**DateTime**。 此示例使用与当前线程关联的区域性执行分析。 如果<xref:System.Globalization.CultureInfo>关联与当前区域性无法分析输入的字符串，<xref:System.FormatException>引发。  
  
 [!code-csharp[Parsing.DateAndTime#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example.cs#1)]
 [!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example.vb#1)]  
  
 你还可以指定**CultureInfo**设置为一个由该对象定义的区域性或您可以指定其中一个标准<xref:System.Globalization.DateTimeFormatInfo>返回的对象<xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>属性。 下面的代码示例使用格式提供程序来分析德语字符串插入**DateTime**。 A **CultureInfo**表示 DE-DE 区域性定义并传递与正在分析为确保成功分析此特定字符串的字符串。 这将阻止任何设置位于**CurrentCulture**的**CurrentThread**。  
  
 [!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example2.cs#2)]
 [!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example2.vb#2)]  
  
 但是，尽管你可以使用的重载<xref:System.DateTime.Parse%2A>方法，以指定自定义格式提供程序，该方法不支持的非标准的格式提供程序使用。 若要分析的日期和时间以非标准的格式表示，请使用<xref:System.DateTime.ParseExact%2A>方法相反。  
  
 下面的代码示例使用<xref:System.Globalization.DateTimeStyles>枚举来指定当前日期和时间信息不应添加到**DateTime**字符串未定义的字段。  
  
 [!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example3.cs#3)]
 [!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example3.vb#3)]  
  
## <a name="parseexact"></a>ParseExact  
 <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>方法将符合的字符串转换为指定的字符串模式与**DateTime**对象。 当指定的窗体的不是一个字符串传递给此方法，<xref:System.FormatException>引发。 可以指定一种标准日期和时间格式说明符或自定义日期和时间格式说明符的有限组合。 使用自定义格式说明符可以构造自定义识别字符串。 有关说明符的说明，请参见有关[标准日期和时间格式字符串](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)和[自定义日期和时间格式字符串](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)的主题。  
  
 每个重载<xref:System.DateTime.ParseExact%2A>方法还有<xref:System.IFormatProvider>参数，通常可提供有关格式的字符串的区域性特定信息。 通常情况下，这<xref:System.IFormatProvider>对象是<xref:System.Globalization.CultureInfo>对象以表示标准区域性或<xref:System.Globalization.DateTimeFormatInfo>返回的对象<xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>属性。 但是，与不同的其他日期和时间分析函数，此方法还支持<xref:System.IFormatProvider>，它定义的非标准日期和时间格式。  
  
 在下面的代码示例中， **ParseExact**方法传递一个字符串对象来分析，请跟格式说明符后, 跟**CultureInfo**对象。 这**ParseExact**方法只能分析表现出 EN-US 区域性中的长日期模式的字符串。  
  
 [!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example4.cs#4)]
 [!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example4.vb#4)]  
  
## <a name="see-also"></a>另请参阅  
 [分析字符串](../../../docs/standard/base-types/parsing-strings.md)  
 [格式设置类型](../../../docs/standard/base-types/formatting-types.md)  
 [.NET 中的类型转换](../../../docs/standard/base-types/type-conversion.md)
