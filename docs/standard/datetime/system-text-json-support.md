---
title: 系统中的 DateTime 和 DateTimeOffset 支持
description: 介绍如何在 System.web 库中支持 DateTime 和 DateTimeOffset 类型。
ms.technology: dotnet-standard
author: layomia
ms.author: laakinri
ms.date: 07/22/2019
helpviewer_keywords:
- JSON, Serializer, Utf8
- JSON DateTime, JSON DateTimeOffset
- DateTime, DateTimeOffset
- JsonSerializer, Utf8JsonReader, Utf8JsonWriter, JsonElement, JsonDocument
- JSON Serializer, JSON Reader, JSON Writer
- Converter, JSON Converter, DateTime Converter
- ISO, ISO 8601, ISO 8601-1:2019
ms.openlocfilehash: 182694a3d2df02d5e2c709e33a02bd9fa7d20383
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69973211"
---
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a>系统中的 DateTime 和 DateTimeOffset 支持

根据 ISO 8601:-2019 扩展配置文件, system.web 库分析<xref:System.DateTime>并<xref:System.DateTimeOffset>写入和值。
[转换器](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0)为序列化和反序列<xref:System.Text.Json.JsonSerializer>化提供自定义支持。

## <a name="support-for-the-iso-8601-12019-format"></a>支持 ISO 8601-1:2019 格式

<xref:System.Text.Json.JsonSerializer> <xref:System.DateTime> <xref:System.DateTimeOffset> 、 、<xref:System.Text.Json.Utf8JsonReader>和类型根据ISO8601-1:2019格式的扩展配置文件分析并写入和文本表示形式;例如,2019-07-26T16<xref:System.Text.Json.JsonElement> <xref:System.Text.Json.Utf8JsonWriter>: 59:57-05:00。

<xref:System.DateTime>和<xref:System.DateTimeOffset>数据可通过以下方式<xref:System.Text.Json.JsonSerializer>序列化:

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/serializing-with-jsonserializer.cs)]

还可以通过以下方式<xref:System.Text.Json.JsonSerializer>对其进行反序列化:

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/deserializing-with-jsonserializer-valid.cs)]

对于默认选项, 输入<xref:System.DateTime>和<xref:System.DateTimeOffset>文本表示形式必须符合扩展 ISO 8601-1:2019 配置文件。
尝试对不符合配置文件的表示形式进行反序列<xref:System.Text.Json.JsonSerializer>化将导致<xref:System.Text.Json.JsonException>引发:

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/deserializing-with-jsonserializer-error.cs)]

提供对 JSON 有效负载 (包括<xref:System.DateTime>和<xref:System.DateTimeOffset>表示形式) 内容的结构化访问。 <xref:System.Text.Json.JsonDocument> 下面的示例演示了当给定温度集合时, 可以计算星期一的平均温度:

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/computing-with-jsondocument-valid.cs)]

尝试使用不符合<xref:System.DateTime>表示形式的有效负载来计算平均温度将导致<xref:System.Text.Json.JsonDocument>引发<xref:System.FormatException>:

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/computing-with-jsondocument-error.cs)]

较低级别<xref:System.Text.Json.Utf8JsonWriter>的<xref:System.DateTime>写入<xref:System.DateTimeOffset>和数据:

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/writing-with-utf8jsonwriter.cs)]

<xref:System.Text.Json.Utf8JsonReader>分析<xref:System.DateTime> 和<xref:System.DateTimeOffset>数据:

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/reading-with-utf8jsonreader-valid.cs)]

尝试使用<xref:System.Text.Json.Utf8JsonReader>读取不符合格式将导致其<xref:System.FormatException>引发:

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/reading-with-utf8jsonreader-error.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset-in-xrefsystemtextjsonjsonserializer"></a><xref:System.DateTime> 和<xref:System.DateTimeOffset>中的自定义支持<xref:System.Text.Json.JsonSerializer>

如果希望序列化程序执行自定义分析或格式设置, 可以实现[自定义转换器](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0)。
以下是几个示例：

### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a>使用`DateTime(Offset).Parse`和`DateTime(Offset).ToString`

如果无法确定输入<xref:System.DateTime>或<xref:System.DateTimeOffset>文本表示形式的格式, 则可以使用转换器读取逻辑`DateTime(Offset).Parse`中的方法。 这允许使用。NET 对分析各种<xref:System.DateTime>和<xref:System.DateTimeOffset>文本格式的广泛支持, 包括非 iso 8601 字符串和不符合扩展 iso 8601-1:2019 配置文件的 iso 8601 格式。 与使用序列化程序的本机实现相比, 此方法的性能大大降低。

对于序列化, 可以在转换器`DateTime(Offset).ToString`写入逻辑中使用方法。 这使您可以使用<xref:System.DateTime>任何<xref:System.DateTimeOffset> [标准日期和时间格式](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)以及[自定义日期和时间格式](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings)来编写和值。
与使用序列化程序的本机实现相比, 这种性能也明显降低。

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> 在实现<xref:System.Text.Json.Serialization.JsonConverter%601>时, `T`和<xref:System.DateTime>为时`typeToConvert` , 参数将始终`typeof(DateTime)`为。
参数可用于处理多态事例和使用泛型以高性能方式`typeof(T)`获取。

### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a>使用<xref:System.Buffers.Text.Utf8Parser>和<xref:System.Buffers.Text.Utf8Formatter>

如果输入<xref:System.DateTime>或<xref:System.DateTimeOffset>文本表示形式符合 "R"、"l"、"O" 或 "G"[标准日期和时间格式字符串](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)之一, 或者您想要, 可以在转换器逻辑中使用快速的基于 utf-8 的分析和格式设置方法。根据其中一种格式写入。 这比使用`DateTime(Offset).Parse`和`DateTime(Offset).ToString`更快。

此示例演示一个自定义转换器, 该转换器<xref:System.DateTime>根据["R" 标准格式](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-rfc1123-r-r-format-specifier)对值进行序列化和反序列化:

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> "R" 标准格式的长度始终为29个字符。

### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a>使用`DateTime(Offset).Parse`作为序列化程序的本机解析的回退

如果你通常希望输入<xref:System.DateTime>或<xref:System.DateTimeOffset>数据符合扩展 ISO 8601-1:2019 配置文件, 则可以使用序列化程序的本机分析逻辑。 您还可以实现一种回退机制。
此示例显示, 在无法使用<xref:System.DateTime> <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>分析文本表示形式后, 转换器使用<xref:System.DateTime.Parse(System.String)>成功分析数据。

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example3/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a>系统中的扩展 ISO 8601-1:2019 配置文件

### <a name="date-and-time-components"></a>日期和时间组件

在中<xref:System.Text.Json>实现的扩展 ISO 8601-1:2019 配置文件定义了日期和时间表示的以下组件。 这些组件用于定义分析和格式设置<xref:System.DateTime>和<xref:System.DateTimeOffset>表示形式时支持的各种粒度级别。

| 组件       | 格式                      | 描述                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| 年            | “yyyy”                      | 0001-9999                                                                       |
| 月份           | “MM”                        | 01-12                                                                           |
| Day             | “dd”                        | 01-28、01-29、01-30、01-31 (基于月份/年份)                                  |
| Hour            | “HH”                        | 00-23                                                                           |
| Minute          | “mm”                        | 00-59                                                                           |
| 第二个          | “ss”                        | 00-59                                                                           |
| 第二部分 | “FFFFFFF”                   | 至少一个数字, 最多为16位                                      |
| 时间偏移     | “K”                         | "Z" 或 "(" + "/"-") HH": "mm"                                                |
| 部分时间    | "HH": "mm": "ss [FFFFFFF]"     | 不带 UTC 偏移信息的时间                                             |
| 完整日期       | "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-yyyy'-'mm'-'dd"            | 日历日期                                                                   |
| 全部时间       | "' Partial time'K"           | 一天中的 UTC 或本地时间与本地时间和 UTC 之间的时间偏移量 |
| 日期时间       | "" 完整时间 "不是" "完整时间" " | 日历日期和当天的时间, 例如 2019-07-26T16:59:57-05:00                   |

### <a name="support-for-parsing"></a>支持分析

定义以下级别的粒度:

1. "Full date"
    1. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-yyyy'-'mm'-'dd"

2. "" 完整日期 "不是" "小时" ":" 分钟 "
    1. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh": "MM"

3. "" 完整日期 "不是" "部分时间" "
    1. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh": "MM": "ss" (可[排序 ("s") 格式说明符](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))
    2. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh": "MM": "ss"。FFFFFFF

4. "" 完整日期 "不是" ", 时间小时" ":" "分钟" "时间偏移" "
    1. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh": "mmZ"
    2. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh": "mm (' + '/'-') HH ': ' mm"

5. "日期时间"
    1. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh": "MM": "ssZ"
    2. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh": "MM": "ss"。FFFFFFFZ"
    3. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh ': ' MM ': ' ss (' + '/'-') HH ': ' MM"
    4. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh": "MM": "ss"。FFFFFFF ("+"/"-") HH ":" mm "

如果有秒的小数部分, 则必须至少有一个数字;`2019-07-26T00:00:00.`不允许。
尽管允许最多包含16个小数位, 但仅分析前7个小数。 超出的任何内容都将被视为零。
例如, `2019-07-26T00:00:00.1234567890`将按`2019-07-26T00:00:00.1234567`原样进行分析。
这是为了保持与<xref:System.DateTime>实现的兼容性, 这仅限于此解决方案。

不支持闰秒。

### <a name="support-for-formatting"></a>支持格式设置

为格式化定义了下列粒度级别:

1. "" 完整日期 "不是" "部分时间" "
    1. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh": "MM": "ss" (可[排序 ("s") 格式说明符](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))

        用于设置不包含<xref:System.DateTime>秒的小数部分和不含偏移量信息的格式。

    2. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh": "MM": "ss"。FFFFFFF

        用于设置带小数<xref:System.DateTime>秒但不含偏移信息的的格式。

2. "日期时间"
    1. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh": "MM": "ssZ"

        用于设置<xref:System.DateTime>或<xref:System.DateTimeOffset>不包含秒的小数部分, 但使用 UTC 偏移量。

    2. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh": "MM": "ss"。FFFFFFFZ"

        用于设置<xref:System.DateTime>或<xref:System.DateTimeOffset>的小数部分的格式, 且具有 UTC 偏移量。

    3. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh ': ' MM ': ' ss (' + '/'-') HH ': ' MM"

        用于设置<xref:System.DateTime>或<xref:System.DateTimeOffset>不包含秒的小数部分, 但使用本地偏移量。

    4. "yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh": "MM": "ss"。FFFFFFF ("+"/"-") HH ":" mm "

        用于设置<xref:System.DateTime>或的小数<xref:System.DateTimeOffset>部分或局部偏移量的格式。
