---
title: 如何使用C# -.NET 对 JSON 进行序列化和反序列化
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 047d5b5c6fa339089d2054eb6bfe8b3066c1d00c
ms.sourcegitcommit: dfad244ba549702b649bfef3bb057e33f24a8fb2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2020
ms.locfileid: "75904660"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a>如何在 .NET 中对 JSON 进行序列化和反序列化（marshal 和取消封送）

本文介绍如何使用 <xref:System.Text.Json> 命名空间在 JavaScript 对象表示法（JSON）之间进行序列化和反序列化。

方向和示例代码直接使用库，而不是通过框架（如[ASP.NET Core](/aspnet/core/)）使用。

大多数序列化示例代码将 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> 设置为 `true` JSON （对于人工可读性，为缩进和空格）。 对于生产用途，通常会接受此设置的默认 `false` 值。

## <a name="namespaces"></a>命名空间

<xref:System.Text.Json> 命名空间包含所有入口点和主要类型。 <xref:System.Text.Json.Serialization> 命名空间包含用于高级方案的属性和 Api，以及特定于序列化和反序列化的自定义。 本文中所示的代码示例要求其中一个或两个命名空间都有 `using` 指令：

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

`System.Text.Json`当前不支持 <xref:System.Runtime.Serialization> 命名空间中的属性。

## <a name="how-to-write-net-objects-to-json-serialize"></a>如何将 .NET 对象写入 JSON （序列化）

若要将 JSON 写入字符串或文件，请调用 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 方法。

下面的示例将 JSON 创建为字符串：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

下面的示例使用同步代码创建 JSON 文件：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

下面的示例使用异步代码创建 JSON 文件：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

前面的示例对要序列化的类型使用类型推理。 `Serialize()` 的重载采用泛型类型参数：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a>序列化示例

下面是包含集合和嵌套类的示例类：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

序列化上述类型的实例的 JSON 输出类似于下面的示例。 默认情况下，JSON 输出为缩小： 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

下面的示例演示了相同的 JSON 格式（也就是用空格和缩进进行整齐打印）：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": 20,
      "Low": -10
    },
    "Hot": {
      "High": 60,
      "Low": 20
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

### <a name="serialize-to-utf-8"></a>序列化为 UTF-8

若要序列化为 UTF-8，请调用 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 方法：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

还提供了一个采用 <xref:System.Text.Json.Utf8JsonWriter> 的 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 重载。

序列化为 UTF-8 比使用基于字符串的方法更快5-10%。 不同之处在于，不需要将字节（如 UTF-8）转换为字符串（UTF-16）。

## <a name="serialization-behavior"></a>序列化行为

* 默认情况下，将序列化所有公共属性。 您可以[指定要排除的属性](#exclude-properties-from-serialization)。
* [默认编码器](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)会转义非 ascii 字符、ASCII 范围内的 HTML 敏感字符以及必须根据[RFC 8259 JSON 规范](https://tools.ietf.org/html/rfc8259#section-7)进行转义的字符。
* 默认情况下，JSON 为缩小。 可以很好[打印 JSON](#serialize-to-formatted-json)。
* 默认情况下，JSON 名称的大小写与 .NET 名称匹配。 你可以[自定义 JSON 名称大小写](#customize-json-names-and-values)。
* 检测到循环引用并引发异常。
* 当前排除了字段。

支持的类型包括：

* 映射到 JavaScript 基元的 .NET 基元，如数值类型、字符串和布尔值。
* 用户定义的[普通旧 CLR 对象（poco）](https://stackoverflow.com/questions/250001/poco-definition)。
* 一维数组和交错数组（`ArrayName[][]`）。
* `Dictionary<string,TValue>`，其中 `TValue` 为 `object`、`JsonElement`或 POCO。
* 以下命名空间中的集合。
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

您可以[实现自定义转换器](system-text-json-converters-how-to.md)来处理其他类型或提供内置转换器不支持的功能。

## <a name="how-to-read-json-into-net-objects-deserialize"></a>如何将 JSON 读入 .NET 对象（反序列化）

若要从字符串或文件进行反序列化，请调用 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 方法。

下面的示例从字符串读取 JSON，并为[序列化示例](#serialization-example)创建前面所示 `WeatherForecast` 类的实例：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

若要通过使用同步代码从文件进行反序列化，请将文件读入字符串中，如下面的示例中所示：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

若要使用异步代码从文件进行反序列化，请调用 <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> 方法：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a>从 UTF-8 反序列化

若要从 UTF-8 进行反序列化，请调用采用 `Utf8JsonReader` 或 `ReadOnlySpan<byte>`的 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 重载，如下面的示例中所示。 这些示例假定 JSON 位于名为 jsonUtf8Bytes 的字节数组中。

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a>反序列化行为

* 默认情况下，属性名称匹配区分大小写。 可以[指定不区分大小写](#case-insensitive-property-matching)。
* 如果 JSON 包含只读属性的值，则该值将被忽略，并且不会引发异常。
* 不支持反序列化到不具有无参数构造函数的引用类型。
* 不支持对不可变对象或只读属性进行反序列化。
* 默认情况下，枚举作为数字支持。 可以将[枚举名称序列化为字符串](#enums-as-strings)。
* 不支持字段。
* 默认情况下，JSON 中的注释或尾随逗号引发异常。 您可以[允许注释和尾随逗号](#allow-comments-and-trailing-commas)。
* [默认的最大深度](xref:System.Text.Json.JsonReaderOptions.MaxDepth)为64。

您可以[实现自定义转换器](system-text-json-converters-how-to.md)以提供内置转换器不支持的功能。

## <a name="serialize-to-formatted-json"></a>序列化为格式化的 JSON

若要整齐地打印 JSON 输出，请将 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> 设置为 `true`：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

下面是一个要进行序列化的示例类型，并显示为漂亮的 JSON 输出：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a>自定义 JSON 名称和值

默认情况下，JSON 输出中的属性名称和字典键不变，包括大小写。 枚举值表示为数值。 本部分介绍如何：

* [自定义各个属性名称](#customize-individual-property-names)
* [将所有属性名称转换为 camel 大小写](#use-camel-case-for-all-json-property-names)
* [实现自定义属性命名策略](#use-a-custom-json-property-naming-policy)
* [将字典键转换为 camel 大小写](#camel-case-dictionary-keys)
* [将枚举转换为字符串和 camel 大小写](#enums-as-strings) 

对于需要对 JSON 属性名称和值进行特殊处理的其他方案，可以[实现自定义转换器](system-text-json-converters-how-to.md)。

### <a name="customize-individual-property-names"></a>自定义各个属性名称

若要设置单个属性的名称，请使用[[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute)属性。

下面是序列化和生成的 JSON 的示例类型：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

此属性设置的属性名称：

* 同时适用于序列化和反序列化。
* 优先于属性命名策略。

### <a name="use-camel-case-for-all-json-property-names"></a>对所有 JSON 属性名称使用 camel 大小写

若要对所有 JSON 属性名称使用 camel 大小写，请将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 设置为 `JsonNamingPolicy.CamelCase`，如下面的示例中所示：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

下面是一个用于序列化和 JSON 输出的示例类：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

Camel 大小写属性命名策略：

* 适用于序列化和反序列化。
* `[JsonPropertyName]` 特性重写。 这就是示例中的 JSON 属性名称 `Wind` 不是 camel 大小写的原因。

### <a name="use-a-custom-json-property-naming-policy"></a>使用自定义 JSON 属性命名策略

若要使用自定义 JSON 属性命名策略，请创建一个派生自 <xref:System.Text.Json.JsonNamingPolicy> 的类，并重写 <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> 方法，如以下示例中所示：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

然后，将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 属性设置为命名策略类的实例：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

下面是一个用于序列化和 JSON 输出的示例类：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

JSON 属性命名策略：

* 适用于序列化和反序列化。
* `[JsonPropertyName]` 特性重写。 这就是示例中 `Wind` 的 JSON 属性名称不大写的原因。

### <a name="camel-case-dictionary-keys"></a>Camel 大小写字典密钥

如果要序列化的对象的属性为 `Dictionary<string,TValue>`类型，则 `string` 键可转换为 camel 大小写形式。 为此，请将 <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> 设置为 `JsonNamingPolicy.CamelCase`，如以下示例中所示：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

使用名为 `TemperatureRanges` 的字典序列化具有键值对 `"ColdMinTemp", 20` 的对象，`"HotMinTemp", 40` 将导致 JSON 输出，如以下示例所示：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

字典键的 camel 大小写命名策略仅适用于序列化。 如果对字典进行反序列化，即使为 `DictionaryKeyPolicy`指定 `JsonNamingPolicy.CamelCase`，这些键也会与 JSON 文件匹配。

### <a name="enums-as-strings"></a>作为字符串的枚举

默认情况下，枚举作为数字序列化。 若要将枚举名称序列化为字符串，请使用 <xref:System.Text.Json.Serialization.JsonStringEnumConverter>。

例如，假设需要序列化以下具有枚举的类：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

如果 `Hot`摘要，则默认情况下序列化的 JSON 的数值为3：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

下面的示例代码序列化枚举名称，而不是数值，并将名称转换为 camel 大小写格式：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

生成的 JSON 类似于以下示例：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

还可以反序列化枚举字符串名称，如以下示例中所示：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a>从序列化中排除属性

默认情况下，将序列化所有公共属性。 如果你不想让某些用户出现在 JSON 输出中，则可以使用几个选项。 本部分介绍如何排除：

* [单个属性](#exclude-individual-properties)
* [所有只读属性](#exclude-all-read-only-properties)
* [所有 null 值属性](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a>排除单个属性

若要忽略各个属性，请使用[[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute)属性。

下面是要序列化的示例类型和 JSON 输出：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a>排除所有只读属性

如果属性包含公共 getter 而不是公共 setter，则该属性为只读。 若要排除所有只读属性，请将 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> 设置为 `true`，如以下示例中所示：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

下面是要序列化的示例类型和 JSON 输出：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

此选项仅适用于序列化。 在反序列化期间，默认情况下将忽略只读属性。

### <a name="exclude-all-null-value-properties"></a>排除所有 null 值属性

若要排除所有 null 值属性，请将 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> 属性设置为 `true`，如以下示例中所示：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

下面是一个示例对象，用于序列化和 JSON 输出：

|Property |{2&gt;值&lt;2}  |
|---------|---------|
| 日期    | 8/1/2019 12:00:00 AM-07:00|
| TemperatureCelsius| 25 |
| 摘要| null|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

此设置适用于序列化和反序列化。 有关对反序列化的影响的信息，请参阅[反序列化时忽略 null](#ignore-null-when-deserializing)。

## <a name="customize-character-encoding"></a>自定义字符编码

默认情况下，序列化程序对所有非 ASCII 字符进行转义。  也就是说，它将替换为 `\uxxxx`，其中 `xxxx` 为字符的 Unicode 代码。  例如，如果将 `Summary` 属性设置为西里尔жарко，则 `WeatherForecast` 对象将被序列化，如以下示例中所示：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a>序列化语言字符集

若要序列化一种或多种语言的字符集而不进行转义，请在创建 <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>的实例时指定[Unicode 范围](xref:System.Text.Unicode.UnicodeRanges)，如以下示例中所示：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

此代码不会对西里尔字符或希腊语字符进行转义。 如果 `Summary` 属性设置为西里尔жарко，则 `WeatherForecast` 对象将被序列化，如以下示例中所示：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

若要序列化所有语言集而不进行转义，请使用 <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>。

### <a name="serialize-specific-characters"></a>序列化特定字符

一种替代方法是指定要允许的单个字符，而不进行转义。 下面的示例仅序列化жарко的前两个字符：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

下面是前面的代码生成的 JSON 示例：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a>序列化所有字符

若要最大程度地减少转义，可以使用 <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>，如以下示例中所示：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> 与默认编码器相比，`UnsafeRelaxedJsonEscaping` 编码器可以更好地允许字符通过非转义：
>
> * 它不会转义 HTML 敏感字符，如 `<`、`>`、`&`和 `'`。
> * 它不提供任何针对 XSS 或信息泄露攻击的额外防御防护，如客户端和服务器 disagreeing 在*字符集*上可能导致的任何其他防护。
>
> 仅当知道客户端将以 UTF-8 编码的 JSON 解释结果负载时，才使用 unsafe 编码器。 例如，如果服务器正在发送响应标头，则可以使用它 `Content-Type: application/json; charset=utf-8`。 永远不允许将原始 `UnsafeRelaxedJsonEscaping` 输出发送到 HTML 页或 `<script>` 元素。

## <a name="serialize-properties-of-derived-classes"></a>序列化派生类的属性

不支持多态类型层次结构的序列化。 例如，如果将某个属性定义为接口或抽象类，则即使运行时类型具有其他属性，也只会序列化对接口或抽象类定义的属性。 此部分中介绍了此行为的例外情况。

例如，假设您有一个 `WeatherForecast` 类和一个派生类 `WeatherForecastDerived`：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

并且假设在编译时 `Serialize` 方法的类型实参 `WeatherForecast`：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

在这种情况下，即使 `weatherForecast` 对象实际上是 `WeatherForecastDerived` 对象，也不会对 `WindSpeed` 属性进行序列化。 仅序列化基类属性：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

此行为旨在帮助防止在派生的运行时创建的类型中发生意外的数据泄露。

若要在前面的示例中序列化派生类型的属性，请使用以下方法之一：

* 调用 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 的重载，以便在运行时指定类型：

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* 将要序列化的对象声明为 `object`。

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

在前面的示例方案中，这两种方法都会使 `WindSpeed` 属性包括在 JSON 输出中：

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> 这些方法只为要序列化的根对象提供多态序列化，而不提供该根对象的属性的多态序列化。 

如果将较低级别的对象定义为 `object`类型，则可以获取多态序列化。 例如，假设 `WeatherForecast` 类具有一个名为 `PreviousForecast` 的属性，该属性可以定义为类型 `WeatherForecast` 或 `object`：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

如果 `PreviousForecast` 属性包含 `WeatherForecastDerived`的实例：

* 序列化 `WeatherForecastWithPrevious` 的 JSON 输出**不包括**`WindSpeed`。
* 序列化 `WeatherForecastWithPreviousAsObject` 的 JSON 输出**包括**`WindSpeed`。

若要序列化 `WeatherForecastWithPreviousAsObject`，无需调用 `Serialize<object>` 或 `GetType`，因为根对象不是可能是派生类型的对象。 下面的代码示例不调用 `Serialize<object>` 或 `GetType`：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

前面的代码正确地序列化 `WeatherForecastWithPreviousAsObject`：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "PreviousForecast": {
    "WindSpeed": 35,
    "Date": "2019-08-01T00:00:00-07:00",
    "TemperatureCelsius": 25,
    "Summary": "Hot"
  }
}
```

将属性定义为 `object` 与接口一起使用的方法相同。 假设您具有以下接口和实现，并且您想要使用包含实现实例的属性序列化类：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/IForecast.cs)]

序列化 `Forecasts`的实例时，只有 `Tuesday` 显示 `WindSpeed` 属性，因为 `Tuesday` 定义为 `object`：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

下面的示例显示了前面的代码生成的 JSON：

```json
{
  "Monday": {
    "Date": "2020-01-06T00:00:00-08:00",
    "TemperatureCelsius": 10,
    "Summary": "Cool"
  },
  "Tuesday": {
    "Date": "2020-01-07T00:00:00-08:00",
    "TemperatureCelsius": 11,
    "Summary": "Rainy",
    "WindSpeed": 10
  }
}
```

有关多态**序列化**的详细信息，以及有关**反序列**化的信息，请参阅[如何从 newtonsoft.json 迁移到 system.object](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization)。

## <a name="allow-comments-and-trailing-commas"></a>允许注释和尾随逗号

默认情况下，JSON 中不允许使用注释和尾随逗号。 若要允许 JSON 中的注释，请将 <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> 属性设置为 `JsonCommentHandling.Skip`。
若要允许尾随逗号，请将 <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> 属性设置为 `true`。 下面的示例演示如何允许两种方法：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

下面是包含注释和尾随逗号的示例 JSON：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a>不区分大小写的属性匹配

默认情况下，反序列化将查找 JSON 与目标对象属性之间区分大小写的属性名称匹配。 若要更改此行为，请将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> 设置为 `true`：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

下面是采用 camel 大小写属性名称的示例 JSON。 它可以反序列化为具有 Pascal 大小写属性名称的以下类型。

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a>句柄溢出 JSON

反序列化时，可能会收到 JSON 中的数据，该数据不是由目标类型的属性表示的。 例如，假设目标类型为：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

要反序列化的 JSON 如下：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

如果将显示的 JSON 反序列化为显示的类型，则 "`DatesAvailable`" 和 "`SummaryWords`" 属性不会有任何位置，并且将丢失。 若要捕获额外数据（如这些属性），请将[JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute)特性应用到类型 `Dictionary<string,object>` 或 `Dictionary<string,JsonElement>`的属性：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

反序列化前面显示的此示例类型的 JSON 时，额外的数据将成为 `ExtensionData` 属性的键值对：

|Property |{2&gt;值&lt;2}  |注释  |
|---------|---------|---------|
| 日期    | 8/1/2019 12:00:00 AM-07:00||
| TemperatureCelsius| 0 | 区分大小写不匹配（`temperatureCelsius` 在 JSON 中），因此未设置属性。 |
| 摘要 | 热 ||
| ExtensionData | temperatureCelsius：25 |由于大小写不匹配，因此此 JSON 属性是一个额外的，并成为字典中的键值对。|
|| DatesAvailable:<br>  8/1/2019 12:00:00 AM-07:00<br>8/2/2019 12:00:00 AM-07:00 |JSON 中的额外属性将成为键值对，并将数组作为值对象。|
| |SummaryWords:<br>酷<br>风<br>Humid |JSON 中的额外属性将成为键值对，并将数组作为值对象。|

序列化目标对象时，扩展数据键值对将成为 JSON 属性，就像它们位于传入 JSON 中一样：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 0,
  "Summary": "Hot",
  "temperatureCelsius": 25,
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

请注意，`ExtensionData` 属性名称不会出现在 JSON 中。 此行为允许 JSON 进行往返，而不会丢失任何不会被反序列化的额外数据。

## <a name="ignore-null-when-deserializing"></a>反序列化时忽略 null

默认情况下，如果 JSON 中的属性为 null，则目标对象中的相应属性将设置为 null。 在某些情况下，target 属性可能具有默认值，并且你不希望 null 值覆盖默认值。

例如，假设以下代码表示目标对象：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

假设反序列化以下 JSON：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

反序列化后，`WeatherForecastWithDefault` 对象的 `Summary` 属性为 null。

若要更改此行为，请将 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> 设置为 `true`，如以下示例中所示：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

利用此选项，在反序列化后，`WeatherForecastWithDefault` 对象的 `Summary` 属性是默认值 "无摘要"。

JSON 中的 Null 值仅在有效时才会被忽略。 不可以为 null 的值类型的 Null 值将导致异常。

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a>Utf8JsonReader、Utf8JsonWriter 和 JsonDocument

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> 是适用于 UTF-8 编码的 JSON 文本的高性能、低分配、只进读取器、从 `ReadOnlySpan<byte>` 或 `ReadOnlySequence<byte>`读取。 `Utf8JsonReader` 是可用于生成自定义分析程序和反的低级别类型。 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 方法使用 `Utf8JsonReader` 的内容。

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> 是一种高性能的方式，用于从常见的 .NET 类型（如 `String`、`Int32`和 `DateTime`）编写 UTF-8 编码的 JSON 文本。 编写器是可用于生成自定义序列化程序的低级别类型。 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 方法使用 `Utf8JsonWriter` 的内容。

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> 提供使用 `Utf8JsonReader`生成只读文档对象模型（DOM）的功能。 DOM 提供对 JSON 有效负载中的数据的随机访问。 可以通过 <xref:System.Text.Json.JsonElement> 类型访问构成有效负载的 JSON 元素。 `JsonElement` 类型提供数组和对象枚举器，以及用于将 JSON 文本转换为常见 .NET 类型的 Api。 `JsonDocument` 公开 <xref:System.Text.Json.JsonDocument.RootElement> 属性。

以下部分说明了如何使用这些工具来读取和写入 JSON。

## <a name="use-jsondocument-for-access-to-data"></a>使用 JsonDocument 访问数据

下面的示例演示如何使用 <xref:System.Text.Json.JsonDocument> 类来随机访问 JSON 字符串中的数据：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

前面的代码：

* 假定 JSON 要分析的字符串中有一个名为 `jsonString`。
* 计算 `Students` 数组中具有 `Grade` 属性的对象的平均评分。 
* 为没有成绩的学生分配默认等级70。
* 通过每次迭代增加 `count` 变量来对学生进行计数。 一种替代方法是调用 <xref:System.Text.Json.JsonElement.GetArrayLength%2A>，如以下示例中所示：

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

下面是此代码处理的 JSON 示例：

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a>使用 JsonDocument 编写 JSON

下面的示例演示如何从 <xref:System.Text.Json.JsonDocument>编写 JSON：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

前面的代码：

* 读取 JSON 文件，将数据加载到 `JsonDocument`，并将格式化（整齐打印的） JSON 写入文件。
* 使用 <xref:System.Text.Json.JsonDocumentOptions> 指定允许但忽略输入 JSON 中的注释。
* 完成后，将对编写器调用 <xref:System.Text.Json.Utf8JsonWriter.Flush%2A>。 一种替代方法是让编写人员在 autoflush 时进行处理。 

下面是示例代码处理的 JSON 输入的示例：

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

结果如下所示：

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a>使用 Utf8JsonWriter

下面的示例演示如何使用 <xref:System.Text.Json.Utf8JsonWriter> 类：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a>使用 Utf8JsonReader

下面的示例演示如何使用 <xref:System.Text.Json.Utf8JsonReader> 类：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

前面的代码假定 `jsonUtf8` 变量是包含有效 JSON 的字节数组，编码为 UTF-8。

### <a name="filter-data-using-utf8jsonreader"></a>使用 Utf8JsonReader 筛选数据

下面的示例演示如何同步读取文件并搜索值：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

前面的代码：

* 假定 JSON 包含一个对象数组，并且每个对象可能包含一个字符串类型的 "name" 属性。
* 计算以 "大学" 结尾的对象和 "name" 属性值。
* 假定文件编码为 UTF-16，并将其转码为 UTF-8。 可以通过使用以下代码，将编码为 UTF-8 的文件直接读入 `ReadOnlySpan<byte>`：

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

  如果文件包含 UTF-8 字节顺序标记（BOM），请在将字节传递到 `Utf8JsonReader`之前将其删除，因为读取器需要文本。 否则，BOM 被视为无效的 JSON，读取器将引发异常。

下面是前面的代码可以读取的 JSON 示例。 生成的摘要消息为 "2 个，共4个名称以 ' 大学 ' 结尾"：

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a>其他资源

* [System.web 概述](system-text-json-overview.md)
* [如何编写自定义转换器](system-text-json-converters-how-to.md)
* [如何从 Newtonsoft.json 迁移](system-text-json-migrate-from-newtonsoft-how-to.md)
* [系统中的 DateTime 和 DateTimeOffset 支持](../datetime/system-text-json-support.md)
* [System.web API 参考](xref:System.Text.Json)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
