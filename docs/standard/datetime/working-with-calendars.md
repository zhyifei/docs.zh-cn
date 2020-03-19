---
title: 使用日历
ms.date: 04/01/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- globalization [.NET], calendars
- calendars, global applications
- global applications, calendars
- world-ready applications, calendars
- international applications [.NET], calendars
- culture, calendars
ms.assetid: 0c1534e5-979b-4c8a-a588-1c24301aefb3
ms.openlocfilehash: de8e5a03c769a22f3320c7785706555898bf8c1c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401231"
---
# <a name="work-with-calendars"></a>使用日历

尽管日期和时间值表示时间中的某一刻，但其字符串表示形式区分区域性，并取决于特定区域性显示日期和时间值所用的约定以及该区域性使用的日历。 本主题将探讨对 .NET 中日历的支持，并讨论在使用日期值时日历类的使用。

## <a name="calendars-in-net"></a>.NET 中的日历

.NET 中的所有日历都派生自类<xref:System.Globalization.Calendar?displayProperty=nameWithType>，该类提供基本日历实现。 从 <xref:System.Globalization.Calendar> 类继承的类之一是 <xref:System.Globalization.EastAsianLunisolarCalendar> 类，该类是所有阴阳历的基类。 .NET 包括以下日历实现：

- <xref:System.Globalization.ChineseLunisolarCalendar>，表示中国阴阳历。

- <xref:System.Globalization.GregorianCalendar>，表示公历。 此日历进一步细分为 <xref:System.Globalization.GregorianCalendarTypes?displayProperty=nameWithType> 枚举定义的子类型（如阿拉伯和中东法国）。 <xref:System.Globalization.GregorianCalendar.CalendarType%2A?displayProperty=nameWithType> 属性指定公历的子类型。

- <xref:System.Globalization.HebrewCalendar>，表示希伯来历。

- <xref:System.Globalization.HijriCalendar>，表示回历。

- <xref:System.Globalization.JapaneseCalendar>，表示日本历。

- <xref:System.Globalization.JapaneseLunisolarCalendar>，表示日本阴阳历。

- <xref:System.Globalization.JulianCalendar>，表示罗马儒略历。

- <xref:System.Globalization.KoreanCalendar>，表示朝鲜历。

- <xref:System.Globalization.KoreanLunisolarCalendar>，表示朝鲜阴阳历。

- <xref:System.Globalization.PersianCalendar>，表示波斯历。

- <xref:System.Globalization.TaiwanCalendar>，表示台湾历。

- <xref:System.Globalization.TaiwanLunisolarCalendar>，表示台湾阴阳历。

- <xref:System.Globalization.ThaiBuddhistCalendar>，表示泰国佛历。

- <xref:System.Globalization.UmAlQuraCalendar>，表示古兰经历。

可通过以下两种方法之一来使用日历：

- 作为特定区域性使用的日历。 每个 <xref:System.Globalization.CultureInfo> 对象都有当前日历，这是该对象当前使用的日历。 所有日期和时间值的字符串表示形式会自动反映当前的区域性及其当前日历。 通常，当前的日历是该区域性的默认日历。 <xref:System.Globalization.CultureInfo>对象还具有可选日历，其中包括区域性可以使用的其他日历。

- 作为与特定区域性无关的独立日历。 在这种情况下，<xref:System.Globalization.Calendar> 方法用于将日期表示为反映日历的值。

请注意，以下六个日历类只能用作独立日历：<xref:System.Globalization.ChineseLunisolarCalendar>、<xref:System.Globalization.JapaneseLunisolarCalendar>、<xref:System.Globalization.JulianCalendar>、<xref:System.Globalization.KoreanLunisolarCalendar>、<xref:System.Globalization.PersianCalendar> 和 <xref:System.Globalization.TaiwanLunisolarCalendar>。 任何区域性都不将这些日历用作默认日历或可选日历。

## <a name="calendars-and-cultures"></a>日历和文化

每个区域性都有默认日历，由 <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType> 属性定义。 <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType> 属性可返回 <xref:System.Globalization.Calendar> 对象的数组，该数组指定特定区域性支持的所有日历，包括该区域性的默认日历。

下面的示例演示 <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType> 和 <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType> 属性。 该示例为泰语（泰国）和日语（日本）区域性创建 `CultureInfo` 对象，并显示它们的默认和可选日历。 请注意，在这两种情况下，区域性的默认日历也包括在 <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType> 集合中。

[!code-csharp[Conceptual.Calendars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/calendarinfo1.cs#1)]
[!code-vb[Conceptual.Calendars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/calendarinfo1.vb#1)]

特定 <xref:System.Globalization.CultureInfo> 对象当前正在使用的日历由区域性的 <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType> 属性定义。 区域性的 <xref:System.Globalization.DateTimeFormatInfo> 对象由 <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> 属性返回。 创建区域性时，其默认值与 <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType> 属性的值相同。 但是，可将区域性的当前日历更改为 <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType> 属性返回的数组中包含的任何日历。 如果尝试将当前日历设置为 <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType> 属性值中不包括的日历，则会引发 <xref:System.ArgumentException>。

以下示例将更改阿拉伯（沙特阿拉伯）区域性使用的日历。 它首先实例化一个 <xref:System.DateTime> 值并使用当前区域性（在此示例中，为英语（美国））和当前区域性的日历（在此示例中，为公历）显示该值。 接下来，该示例将当前区域性更改为阿拉伯语（沙特阿拉伯），并使用其默认的古兰经历显示该日期。 然后，该示例调用 `CalendarExists` 方法来确定阿拉伯语（沙特阿拉伯）区域性是否支持该回历。 因为该日历受支持，所以该示例将当前日历更改为回历并再次显示日期。 请注意，在每种情况下，均使用当前区域性的当前日历来显示日期。

[!code-csharp[Conceptual.Calendars#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/changecalendar2.cs#2)]
[!code-vb[Conceptual.Calendars#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/changecalendar2.vb#2)]

## <a name="dates-and-calendars"></a>日期和日历

除包括 <xref:System.Globalization.Calendar> 类型参数并允许日期的元素（即月、日和年）以指定日历反映值的构造函数外，<xref:System.DateTime> 和 <xref:System.DateTimeOffset> 值始终基于公历。 例如，这意味着 <xref:System.DateTime.Year%2A?displayProperty=nameWithType> 属性返回公历的年，<xref:System.DateTime.Day%2A?displayProperty=nameWithType> 属性返回公历的当月日期。

> [!IMPORTANT]
> 请记住，日期值与其字符串表示形式之间是有差异的，这一点很重要。 前者基于公历，后者基于特定区域性的当前日历。

下面的示例演示了 <xref:System.DateTime> 属性与其对应的 <xref:System.Globalization.Calendar> 方法之间的这一差异。 在此示例中，当前区域性为阿拉伯语（埃及），当前日历为古兰经历。 <xref:System.DateTime> 值设置为 2011 年 7 月 15 日。 很显然，该值被解释为公历日期，因为这些相同的值是由 <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> 方法在使用不变区域性的约定时返回的。 使用当前区域性的约定设置格式后，该日期的字符串表示形式为 14/08/32，与古兰经历中的日期等效。 接下来，使用 `DateTime` 和 `Calendar` 的成员返回 <xref:System.DateTime> 值的日、月和年。 在每种情况下，<xref:System.DateTime> 成员返回的值反映公历中的值，而 <xref:System.Globalization.UmAlQuraCalendar> 成员返回的值反映古兰经历中的值。

[!code-csharp[Conceptual.Calendars#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/datesandcalendars2.cs#3)]
[!code-vb[Conceptual.Calendars#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/datesandcalendars2.vb#3)]

### <a name="instantiate-dates-based-on-a-calendar"></a>基于日历的实例化日期

由于 <xref:System.DateTime> 和 <xref:System.DateTimeOffset> 值基于公历，因此如果要使用不同日历中的日、月或年的值，必须调用包括 <xref:System.Globalization.Calendar> 类型参数的重载构造函数来实例化日期值。 还可以调用特定日历的 <xref:System.Globalization.Calendar.ToDateTime%2A?displayProperty=nameWithType> 方法的重载之一，以基于特定日历的值来实例化 <xref:System.DateTime> 对象。

下面的示例通过向 <xref:System.DateTime> 构造函数传递一个 <xref:System.Globalization.HebrewCalendar> 对象来实例化一个 <xref:System.DateTime> 值，通过调用 <xref:System.DateTime> 方法来实例化另一个 <xref:System.Globalization.HebrewCalendar.ToDateTime%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType> 值。 由于这两个值是使用希伯来历中的相同值创建的，因此对 <xref:System.DateTime.Equals%2A?displayProperty=nameWithType> 方法的调用显示这两个 <xref:System.DateTime> 值相等。

[!code-csharp[Conceptual.Calendars#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatehcdate1.cs#4)]
[!code-vb[Conceptual.Calendars#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatehcdate1.vb#4)]

### <a name="represent-dates-in-the-current-calendar"></a>在当前日历中表示日期

在将日期转换为字符串时，日期和时间格式设置方法始终使用当前日历。 这意味着，年、月和当月日期的字符串表示形式反映当前日历，不一定反映公历。

下面的示例演示当前日历如何影响日期的字符串表示形式。 该示例将当前区域性更改为中文（繁体，台湾），并实例化日期值。 然后，该示例显示当前日历和日期，将当前日历更改为 <xref:System.Globalization.TaiwanCalendar>，并再次显示当前日历和日期。 初次显示日期时，它表示为公历日期。 第二次显示日期时，它表示为台湾日历中的日期。

[!code-csharp[Conceptual.Calendars#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/currentcalendar1.cs#5)]
[!code-vb[Conceptual.Calendars#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/currentcalendar1.vb#5)]

### <a name="represent-dates-in-a-non-current-calendar"></a>在非当前日历中表示日期

若要使用特定区域性的当前日历之外的日历表示日期，必须调用该 <xref:System.Globalization.Calendar> 对象的方法。 例如，<xref:System.Globalization.Calendar.GetYear%2A?displayProperty=nameWithType>、<xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=nameWithType> 和 <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=nameWithType> 方法可将年、月和日转换为反映特定日历的值。

> [!WARNING]
> 由于某些日历不是任何区域性的可选日历，因此用这些日历表示日期始终需要调用日历方法。 对于派生自 <xref:System.Globalization.EastAsianLunisolarCalendar>、<xref:System.Globalization.JulianCalendar> 和 <xref:System.Globalization.PersianCalendar> 类的所有日历而言，均为这种情况。

下面的示例使用 <xref:System.Globalization.JulianCalendar> 对象实例化罗马儒略历的日期 1905 年 1 月 9 日。 使用默认（公历）日历显示此日期时，该日期表示为 1905 年 1 月 22 日。 通过调用各种 <xref:System.Globalization.JulianCalendar> 方法，可用罗马儒略历表示日期。

[!code-csharp[Conceptual.Calendars#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/noncurrentcalendar1.cs#6)]
[!code-vb[Conceptual.Calendars#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/noncurrentcalendar1.vb#6)]

### <a name="calendars-and-date-ranges"></a>日历和日期范围

日历支持的最早日期由其 <xref:System.Globalization.Calendar.MinSupportedDateTime%2A?displayProperty=nameWithType> 属性指示。 对于 <xref:System.Globalization.GregorianCalendar> 类，该日期为公历公元 0001 年 1 月 1 日。 .NET 中的大多数其他日历都支持较晚的日期。 尝试使用日历支持的最早日期前面的日期和时间值将引发 <xref:System.ArgumentOutOfRangeException> 异常。

但是，有一个很重要的异常。 <xref:System.DateTime> 对象和 <xref:System.DateTimeOffset> 对象的默认（未初始化的）值等于 <xref:System.Globalization.GregorianCalendar.MinSupportedDateTime%2A?displayProperty=nameWithType> 值。 如果您尝试在不支持 1 月 1，0001 C.E 的日历中设置此日期的格式。 并且您不提供格式指定器，格式方法使用"s"（可排序日期/时间模式）格式指定器，而不是"G"（一般日期/时间模式）格式指定器。 因此，格式设置操作将不会引发 <xref:System.ArgumentOutOfRangeException> 异常。 相反，它会返回不受支持的日期。 下面的示例阐释了这一点，在使用日语日历将当前区域性设置为日语（日本）以及使用古兰经历将当前区域性设置为阿拉伯语（埃及）时，它将显示 <xref:System.DateTime.MinValue?displayProperty=nameWithType> 的值。 它还会将当前区域性设置为英语（美国），并调用 <xref:System.DateTime.ToString%28System.IFormatProvider%29?displayProperty=nameWithType> 方法以及所有这些 <xref:System.Globalization.CultureInfo> 对象。 在每种情况下，均使用可排序的日期/时间模式来显示日期。

[!code-csharp[Conceptual.Calendars#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/minsupporteddatetime1.cs#11)]
[!code-vb[Conceptual.Calendars#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/minsupporteddatetime1.vb#11)]

## <a name="work-with-eras"></a>使用时代

日历通常将日期划分为纪元。 但是，.NET<xref:System.Globalization.Calendar>中的类不支持由日历定义的每个纪元，并且大多数<xref:System.Globalization.Calendar>类仅支持单个纪元。 只有 <xref:System.Globalization.JapaneseCalendar> 和 <xref:System.Globalization.JapaneseLunisolarCalendar> 类支持多个纪元。

> [!IMPORTANT]
> Reiwa 时代，在<xref:System.Globalization.JapaneseCalendar>和<xref:System.Globalization.JapaneseLunisolarCalendar>的新时代，开始于 2019 年 5 月 1 日。 此更改会影响使用这些日历的所有应用程序。 有关详细信息，请参阅以下文章：
>
> - [在 .NET 中处理日语日历中的新时代](https://devblogs.microsoft.com/dotnet/handling-a-new-era-in-the-japanese-calendar-in-net/)，其中记录添加到 .NET 的功能以支持具有多个时代的日历，并讨论了在处理多纪元日历时使用的最佳做法。
> - [为日本时代的变化准备您的应用程序](/windows/uwp/design/globalizing/japanese-era-change)，它提供有关在 Windows 上测试应用程序的信息，以确保它们准备好迎接时代的变化。
> - [.NET Framework 的新日语时代更新摘要](https://support.microsoft.com/help/4477957/new-japanese-era-updates-for-net-framework)（列出与新日本日历时代相关的单个 Windows 版本的 .NET Framework）更新，其中列出了用于多时代支持的新 .NET Framework 功能，并包含在测试应用程序时要查找的内容。

大多数日历中的时代表示一个极长的时间段。 例如，在公历中，当前时代跨越两千年以上。 对于<xref:System.Globalization.JapaneseCalendar>和<xref:System.Globalization.JapaneseLunisolarCalendar>， 支持多个年代的两个日历， 情况并非如此。 一个时代对应于皇帝统治时期。 对多个时代的支持，特别是在目前时代的上限未知时，提出了特殊的挑战。

### <a name="eras-and-era-names"></a>时代和时代名称

在 .NET 中，表示特定日历实现支持的 eras 的整数在<xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType>数组中按相反顺序存储。 当前时代（是具有最新时间范围的年代）位于索引零，对于<xref:System.Globalization.Calendar>支持多个时代的类，每个连续索引都反映前一个时代。 静态的 <xref:System.Globalization.Calendar.CurrentEra?displayProperty=nameWithType> 属性定义当前纪元在 <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType> 数组中的索引；它是一个值始终为零的常数。 各个 <xref:System.Globalization.Calendar> 类还包括可返回当前纪元值的静态字段。 下表中列出了这些字段。

| 日历类                                        | 当前纪元字段                                                 |
| ----------------------------------------------------- | ----------------------------------------------------------------- |
| <xref:System.Globalization.ChineseLunisolarCalendar>  | <xref:System.Globalization.ChineseLunisolarCalendar.ChineseEra>   |
| <xref:System.Globalization.GregorianCalendar>         | <xref:System.Globalization.GregorianCalendar.ADEra>               |
| <xref:System.Globalization.HebrewCalendar>            | <xref:System.Globalization.HebrewCalendar.HebrewEra>              |
| <xref:System.Globalization.HijriCalendar>             | <xref:System.Globalization.HijriCalendar.HijriEra>                |
| <xref:System.Globalization.JapaneseLunisolarCalendar> | <xref:System.Globalization.JapaneseLunisolarCalendar.JapaneseEra> |
| <xref:System.Globalization.JulianCalendar>            | <xref:System.Globalization.JulianCalendar.JulianEra>              |
| <xref:System.Globalization.KoreanCalendar>            | <xref:System.Globalization.KoreanCalendar.KoreanEra>              |
| <xref:System.Globalization.KoreanLunisolarCalendar>   | <xref:System.Globalization.KoreanLunisolarCalendar.GregorianEra>  |
| <xref:System.Globalization.PersianCalendar>           | <xref:System.Globalization.PersianCalendar.PersianEra>            |
| <xref:System.Globalization.ThaiBuddhistCalendar>      | <xref:System.Globalization.ThaiBuddhistCalendar.ThaiBuddhistEra>  |
| <xref:System.Globalization.UmAlQuraCalendar>          | <xref:System.Globalization.UmAlQuraCalendar.UmAlQuraEra>          |

通过将特定纪元编号传递给 <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType> 或 <xref:System.Globalization.DateTimeFormatInfo.GetAbbreviatedEraName%2A?displayProperty=nameWithType> 方法，可检索与该纪元编号对应的名称。 下面的示例调用这些方法来检索有关 <xref:System.Globalization.GregorianCalendar> 类中的纪元支持信息。 它显示对应于当前纪元第二年 1 月 1 的公历日期，以及对应于每个受支持的日本日历时代第二年的 1 月 1 日的公历日期。

[!code-csharp[Conceptual.Calendars#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatewithera1.cs)]
[!code-vb[Conceptual.Calendars#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatewithera1.vb)]

此外，“g”自定义日期和时间格式字符串还包括一个日期和时间的字符串表示形式的日期纪元名称。 有关详细信息，请参阅[自定义日期和时间格式字符串](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)。

### <a name="instantiatie-a-date-with-an-era"></a>即时使用时代的日期

对于支持多个<xref:System.Globalization.Calendar>时代两个相同的类，由特定年份、月份和月份值组成的日期可能不明确。 例如，由 支持<xref:System.Globalization.JapaneseCalendar>的所有时代都有数字为 1 的年份。 通常，如果未指定纪元，则日期和时间以及日历方法都假定该值属于当前纪元。 包含<xref:System.DateTime.%23ctor%2A>类型<xref:System.Globalization.Calendar>参数的 和<xref:System.DateTimeOffset.%23ctor%2A>构造函数以及[日语日历.Datetime](xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32))和[日语 LunisolarCalendar.ToDateTime](xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32))方法也是如此。 下面的示例实例化了表示未指定时代第二年 1 月 1 日的日期。 如果在 Reiwa 时代是当前时代时执行该示例，则该日期将解释为 Reiwa 时代的第二年。 在<xref:System.DateTime.ToString(System.String,System.IFormatProvider)?displayProperty=nameWithType>方法返回的字符串中，该纪元早于年份，对应于公历中的 2020 年 1 月 1 日。 （雷瓦时代始于公历的 2019 年。

[!code-csharp[A date in the current era](~/samples/snippets/standard/datetime/calendars/current-era/cs/program.cs)]
[!code-vb[A date in the current era](~/samples/snippets/standard/datetime/calendars/current-era/vb/program.vb)]

但是，如果时代发生变化，则此代码的意图变得不明确。 日期是代表当前时代的第二年，还是打算代表海西时代的第二年？ 有两种方法可以避免这种歧义：

- 使用默认<xref:System.Globalization.GregorianCalendar>类实例化日期和时间值。 然后，您可以使用日历或日语 Lunisolar 日历来表示日期的字符串表示形式，如下例所示。

  [!code-csharp[Insantiating a Gregorian date](~/samples/snippets/standard/datetime/calendars/gregorian/cs/program.cs)]
  [!code-vb[Instantiating a Gregorian date](~/samples/snippets/standard/datetime/calendars/gregorian/vb/program.vb)]

- 调用显式指定纪元纪元的日期和时间方法。 这包括以下方法：

  - <xref:System.Globalization.JapaneseCalendar>或<xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)><xref:System.Globalization.JapaneseLunisolarCalendar>类的方法。

  - 或<xref:System.DateTime><xref:System.DateTimeOffset>解析<xref:System.DateTime.Parse%2A>方法，如 ，、 <xref:System.DateTime.TryParse%2A> <xref:System.DateTime.ParseExact%2A>、 或<xref:System.DateTime.TryParseExact%2A>， 包括要解析的字符串，如果当前区域性为<xref:System.Globalization.DateTimeStyles>日本-日本 （"ja-JP"）并且该区域性的日历为<xref:System.Globalization.JapaneseCalendar>， 则可选地作为参数。 要解析的字符串必须包括纪元。

  - 包含<xref:System.DateTime>类型`provider`<xref:System.DateTimeOffset><xref:System.IFormatProvider>参数 的 或 分析方法。 `provider`必须是表示当前日历<xref:System.Globalization.CultureInfo>为 的日本-日本 （"ja-JP"） 区域性的对象<xref:System.Globalization.JapaneseCalendar>，或者其<xref:System.Globalization.DateTimeFormatInfo><xref:System.Globalization.DateTimeFormatInfo.Calendar>属性为<xref:System.Globalization.JapaneseCalendar>的对象。 要解析的字符串必须包括纪元。

  下面的示例使用其中三种方法实例化明治时代的日期和时间，明治时代始于 1868 年 9 月 8 日，于 1912 年 7 月 29 日结束。

  [!code-csharp[A date in a specified era](~/samples/snippets/standard/datetime/calendars/specify-era/cs/program.cs)]
  [!code-vb[A date in a specified era](~/samples/snippets/standard/datetime/calendars/specify-era/vb/program.vb)]

> [!TIP]
> 使用支持多个时代的日历时，*始终*使用公历日期实例化日期，或指定基于该日历实例化日期和时间的年代。

在指定方法的纪元<xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)>时，在日历<xref:System.Globalization.Calendar.Eras>的属性中提供纪元索引。 但是，对于那些时代可能会发生变化的日历，这些索引不是常量值;对于那些时代可能会发生变化的日历，这些索引不是常量值。当前时代为索引 0，而最古老的时代是索引`Eras.Length - 1`。 将新时代添加到日历时，前一个时代的索引将增加一个。 您可以提供相应的时代指数，如下所示：

- 对于当前时代的日期，始终使用日历的属性<xref:System.Globalization.Calendar.CurrentEra>。

- 对于指定时代中的日期，使用 方法<xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType>检索对应于指定纪元名称的索引。 这要求 是<xref:System.Globalization.JapaneseCalendar>表示 ja-JP<xref:System.Globalization.CultureInfo>区域性的对象的当前日历。  （此技术也适用于，<xref:System.Globalization.JapaneseLunisolarCalendar>因为它支持与<xref:System.Globalization.JapaneseCalendar>相同的时代。前面的示例说明了此方法。

### <a name="calendars-eras-and-date-ranges-relaxed-range-checks"></a>日历、时数和日期范围：放宽范围检查

非常类似于单个日历支持日期范围，在 和<xref:System.Globalization.JapaneseCalendar><xref:System.Globalization.JapaneseLunisolarCalendar>类中也有支持范围的年代。 以前，.NET 使用严格的纪元范围检查来确保特定纪元的日期在那个时代的范围内。 也就是说，如果日期超出指定时间的范围，则方法将引发 。 <xref:System.ArgumentOutOfRangeException> 目前，.NET 默认使用宽松的范围检查。 对 .NET 的所有版本的更新引入了宽松的时代范围检查;试图实例化超出指定时代范围的特定于纪元的日期"溢出"到下一个时代，并且不会引发异常。

以下示例尝试实例化 Showa 时代第 65 年的日期，该日期从 1926 年 12 月 25 日开始，到 1989 年 1 月 7 日结束。 此日期对应于 1990 年 1 月 9 日，这超出了 中的<xref:System.Globalization.JapaneseCalendar>Showa 时代的范围。 如示例的输出所示，该示例显示的日期为 1990 年 1 月 9 日，即海西时代的第二年。

  [!code-csharp[Relaxed range checks](~/samples/snippets/standard/datetime/calendars/relaxed-range/cs/program.cs)]
  [!code-vb[Relaxed range checks](~/samples/snippets/standard/datetime/calendars/relaxed-range/vb/program.vb)]

如果不需要放松的范围检查，则可以根据应用程序运行的 .NET 版本，以多种方式恢复严格的范围检查：

- **.NET 核心：** 将以下内容添加到 *.netcore.runtime.json*配置文件：

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.EnforceJapaneseEraYearRanges": true
    }
  }
  ```

- **.NET 框架 4.6 或更高版本：** 在*App.config*文件中设置以下 AppContext 开关：

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.EnforceJapaneseEraYearRanges=true" />
    </runtime>
  </configuration>
  ```

- **.NET 框架 4.5.2 或更早版本：** 设置以下注册表值：

   |  |  |
   |--|--|
   | **密钥** | **HKEY_LOCAL_MACHINE软件\微软\\。NETFramework_应用程序上下文** |
   | **名称** | 开关.系统.全球化.执行日本拉年范围 |
   | **类型** | REG_SZ |
   | **价值** | true |

启用了严格的范围检查后，前面的示例将引发<xref:System.ArgumentOutOfRangeException>并显示以下输出：

```console
Unhandled Exception: System.ArgumentOutOfRangeException: Valid values are between 1 and 64, inclusive.
Parameter name: year
   at System.Globalization.GregorianCalendarHelper.GetYearOffset(Int32 year, Int32 era, Boolean throwOnError)
   at System.Globalization.GregorianCalendarHelper.ToDateTime(Int32 year, Int32 month, Int32 day, Int32 hour, Int32 minute, Int32 second, Int32 millisecond, Int32 era)
   at Example.Main()
```

### <a name="represent-dates-in-calendars-with-multiple-eras"></a>在具有多个时代历的日历中表示日期

如果 <xref:System.Globalization.Calendar> 对象支持纪元并且是 <xref:System.Globalization.CultureInfo> 对象的当前日历，则纪元将包括在完整日期和时间、长日期和短日期模式的日期和时间值的字符串表示形式中。 下面的示例显示当前区域性为日语（日本）并且当前日历为日本日历时的这些日期模式。

[!code-csharp[Conceptual.Calendars#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings1.cs#8)]
[!code-vb[Conceptual.Calendars#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings1.vb#8)]

> [!WARNING]
> 该<xref:System.Globalization.JapaneseCalendar>类是 .NET 中唯一<xref:System.Globalization.CultureInfo><xref:System.Globalization.CultureInfo>一个同时支持多个时代日期的日历类，可以是对象的当前日历-特别是表示日本（日本）区域性的对象的当前日历。

对于所有日历，“g”自定义格式说明符会在结果字符串中包括纪元。 下面的示例使用“MM-dd-yyyy g”自定义格式字符串，在当前日历为公历时在结果字符串中包括纪元。

[!code-csharp[Conceptual.Calendars#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings2.cs#9)]
[!code-vb[Conceptual.Calendars#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings2.vb#9)]

当日期的字符串表示形式用非当前日历来表示时，<xref:System.Globalization.Calendar> 类包括一个可与 <xref:System.Globalization.Calendar.GetEra%2A?displayProperty=nameWithType>、<xref:System.Globalization.Calendar.GetYear%2A?displayProperty=nameWithType> 和 <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=nameWithType> 方法一起使用的 <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=nameWithType> 方法，以明确指示日期及其所属纪元。 下面的示例使用 <xref:System.Globalization.JapaneseLunisolarCalendar> 类来提供演示。 但请注意，在结果字符串中包括有意义的名称或缩写（而不是表示纪元的整数）需要您实例化 <xref:System.Globalization.DateTimeFormatInfo> 对象并使 <xref:System.Globalization.JapaneseCalendar> 成为其当前日历。 （<xref:System.Globalization.JapaneseLunisolarCalendar> 日历不能为任何区域性的当前日历，但在此示例中，两个日历共享相同的纪元。）

[!code-csharp[Conceptual.Calendars#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings3.cs#10)]
[!code-vb[Conceptual.Calendars#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings3.vb#10)]

在日本历法中，一个时代的第一年叫做甘宁（*）。 例如，海西时代的第一年可以描述为海西·甘宁，而不是海西1。 .NET 在格式化使用以下标准或自定义日期和时间格式字符串的日期和时间操作时采用此约定，当这些日期和时间字符串与表示日语（"ja-JP"）区域性<xref:System.Globalization.CultureInfo>的对象使用时，使用<xref:System.Globalization.JapaneseCalendar>该类：

- [长日期模式](../base-types/standard-date-and-time-format-strings.md#LongDate)，由"D"标准日期和时间格式字符串指示。
- [完整日期长时间模式](../base-types/standard-date-and-time-format-strings.md#FullDateLongTime)，由"F"标准日期和时间格式字符串指示。
- [全日期短时间模式](../base-types/standard-date-and-time-format-strings.md#FullDateShortTime)，由"f"标准日期和时间格式字符串指示。
- [年/月模式](../base-types/standard-date-and-time-format-strings.md#YearMonth)，由 Y"或"y"标准日期和时间格式字符串指示。
- ["ggy''"或"ggy"[自定义日期和时间格式字符串](../base-types/custom-date-and-time-format-strings.md)。

例如，下面的示例显示 海西时代第一年在 中<xref:System.Globalization.JapaneseCalendar>的日期。

  [!code-csharp[gannen](~/samples/snippets/standard/datetime/calendars/gannen/cs/program.cs)]
  [!code-vb[gannen](~/samples/snippets/standard/datetime/calendars/gannen/vb/gannen-fmt.vb)]

如果此行为在格式化操作中是不可取的，则可以根据 .NET 的版本执行以下操作，将以前的行为还原为"1"而不是"Gannen"的时代的第一年：

- **.NET 核心：** 将以下内容添加到 *.netcore.runtime.json*配置文件：

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.FormatJapaneseFirstYearAsANumber": true
    }
  }
  ```

- **.NET 框架 4.6 或更高版本：** 在*App.config*文件中设置以下 AppContext 开关：

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.FormatJapaneseFirstYearAsANumber=true" />
    </runtime>
  </configuration>
  ```

- **.NET 框架 4.5.2 或更早版本：** 设置以下注册表值：

   |  |  |
   |--|--|
   | **密钥** | **HKEY_LOCAL_MACHINE软件\微软\\。NETFramework_应用程序上下文** |
   | **名称** | 开关.系统.全球化.日本第一年数字 |
   | **类型** | REG_SZ |
   | **价值** | true |

禁用加宁支持格式化操作后，前面的示例将显示以下输出：

```console
Japanese calendar date: 平成1年8月18日 (Gregorian: Friday, August 18, 1989)
```

.NET 也已更新，以便日期和时间分析操作支持包含表示为"1"或 Gannen 的年份的字符串。 尽管不需要执行此操作，但可以还原以前的行为，仅识别"1"作为时代的第一年。 您可以按照如下方式执行此操作，具体取决于 .NET 的版本：

- **.NET 核心：** 将以下内容添加到 *.netcore.runtime.json*配置文件：

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.EnforceLegacyJapaneseDateParsing": true
    }
  }
  ```

- **.NET 框架 4.6 或更高版本：** 在*App.config*文件中设置以下 AppContext 开关：

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.EnforceLegacyJapaneseDateParsing=true" />
    </runtime>
  </configuration>
  ```

- **.NET 框架 4.5.2 或更早版本：** 设置以下注册表值：

   |  |  |
   |--|--|
   | **密钥** | **HKEY_LOCAL_MACHINE软件\微软\\。NETFramework_应用程序上下文** |
   | **名称** | 开关.系统.全球化.强制执行传统日本日期计算 |
   | **类型** | REG_SZ |
   | **价值** | true |

## <a name="see-also"></a>另请参阅

- [如何：在非公历中显示日期](../../../docs/standard/base-types/how-to-display-dates-in-non-gregorian-calendars.md)
- [示例：日历周范围实用程序](https://code.msdn.microsoft.com/NET-Framework-4-Calendar-3360a84a)
- [日历类](xref:System.Globalization.Calendar)
