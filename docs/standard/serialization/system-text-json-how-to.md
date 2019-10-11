---
title: 如何使用C# -.NET 对 JSON 进行序列化和反序列化
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 3c988a0151f57b67db19f41aeb88c6fb9b808cb3
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2019
ms.locfileid: "72179205"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a>如何在 .NET 中对 JSON 进行序列化和反序列化

> [!IMPORTANT]
> JSON 序列化文档正在构造。 本文不介绍所有方案。 有关详细信息，请查看 GitHub 上的 dotnet/corefx 存储库中的[system.web 问题](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)，尤其是标记为[Json 功能的文档](https://github.com/dotnet/corefx/labels/json-functionality-doc)。

本文介绍如何使用 <xref:System.Text.Json> 命名空间在 JavaScript 对象表示法（JSON）之间进行序列化和反序列化。 方向和示例代码直接使用库，而不是通过框架（如[ASP.NET Core](/aspnet/core/)）使用。

## <a name="namespaces"></a>命名空间

@No__t 的命名空间包含所有入口点和主要类型。 @No__t 的命名空间包含用于高级方案的属性和 Api，以及特定于序列化和反序列化的自定义。 因此，本文中所示的代码示例需要以下一项或两项 `using` 指令：

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

@No__t 中当前不支持 @no__t 命名空间中的属性。

## <a name="how-to-write-net-objects-to-json-serialize"></a>如何将 .NET 对象写入 JSON （序列化）

若要将 JSON 写入字符串，请调用 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 方法。 下面的示例使用具有泛型类型参数的重载：

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

您可以省略泛型类型参数并改用泛型类型推理：

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize(weatherForecast);
```

下面是要进行序列化的示例类型，其中包含集合和嵌套类：

```csharp
public class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public IList<DateTimeOffset> DatesAvailable { get; set;}
    public Dictionary<string, HighLowTemperatures> TemperatureRanges { get; set; }
    public string [] SummaryWords { get; set; }
}

public class HighLowTemperatures
{
    public Temperature High { get; set; }
    public Temperature Low { get; set; }
}

public class Temperature
{
    public int DegreesCelsius { get; set; }
}
```

默认情况下，JSON 输出为缩小： 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

下面的示例演示了相同的 JSON 格式（也就是用空格和缩进进行整齐打印）：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": {
        "DegreesCelsius": 20
      },
      "Low": {
        "DegreesCelsius": -10
      }
    },
    "Hot": {
      "High": {
        "DegreesCelsius": 60
      },
      "Low": {
        "DegreesCelsius": 20
      }
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

@No__t 的重载允许您序列化到 @no__t 1。 @No__t-0 重载的异步版本可用。

### <a name="serialize-to-utf-8"></a>序列化为 UTF-8

若要序列化为 UTF-8，请调用 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 方法：

```csharp
byte[] utf8Json = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

作为替代方法，可以使用 @no__t 为-1 的 @no__t 0 重载。

序列化为 UTF-8 比使用基于字符串的方法更快 5-10%。 不同之处在于，不需要将字节（如 UTF-8）转换为字符串（UTF-16）。

## <a name="serialization-behavior"></a>序列化行为

* 默认情况下，将序列化所有公共属性。 您可以[指定要排除的属性](#exclude-properties)。
* [默认编码器](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)会转义非 ascii 字符、ASCII 范围内的 HTML 敏感字符以及必须根据[JSON 规范](https://tools.ietf.org/html/rfc8259#section-7)进行转义的字符。
* 默认情况下，JSON 为缩小。 可以很好[打印 JSON](#serialize-to-formatted-json)。
* 默认情况下，JSON 名称的大小写与 .NET 名称匹配。 你可以[自定义 JSON 名称大小写](#customize-json-names)。
* 检测到循环引用并引发异常。 有关详细信息，请参阅 GitHub 上的 dotnet/corefx 存储库中的[循环引用问题](https://github.com/dotnet/corefx/issues/38579)。
* 当前排除了字段。

支持的类型包括：

* 映射到 JavaScript 基元的 .NET 基元，如数值类型、字符串和布尔值。
* 用户定义的[普通旧 CLR 对象（poco）](https://stackoverflow.com/questions/250001/poco-definition)。
* 一维数组和交错数组（`ArrayName[][]`）。
* `Dictionary<string,TValue>`，其中 `TValue` 是 `object`、`JsonElement` 还是 POCO。
* 以下命名空间中的集合。 有关详细信息，请参阅 GitHub 上的 dotnet/corefx 存储库中的[收集支持问题](https://github.com/dotnet/corefx/issues/36643)。
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

## <a name="how-to-read-json-into-net-objects-deserialize"></a>如何将 JSON 读入 .NET 对象（反序列化）

若要从字符串进行反序列化，请调用 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 方法，如以下示例中所示：

```csharp
string json = ... ;

var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

有关示例，请参阅[序列化](#how-to-write-net-objects-to-json-serialize)部分。 JSON 和 .NET 对象是相同的，但方向反转。

@No__t 的重载使你可以从 @no__t 进行反序列化。  @No__t-0 重载的异步版本可用。

### <a name="deserialize-from-utf-8"></a>从 UTF-8 反序列化

若要从 UTF-8 进行反序列化，请调用采用 @no__t 或 @no__t 的 @no__t 0 重载，如以下示例中所示：

```csharp
byte[] utf8Json;
//...
var readOnlySpan = new ReadOnlySpan<byte>(utf8Json);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(readOnlySpan);
```

```csharp
byte[] utf8Json;
//...
var utf8Reader = new Utf8JsonReader(utf8Json);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(ref utf8Reader);
```

## <a name="deserialization-behavior"></a>反序列化行为

* 默认情况下，属性名称匹配区分大小写。 可以[指定不区分大小写](#case-insensitive-property-matching)。
* 如果 JSON 包含只读属性的值，则该值将被忽略，并且不会引发异常。
* 不支持反序列化到不具有无参数构造函数的引用类型。
* 不支持对不可变对象或只读属性进行反序列化。 有关详细信息，请参阅 github 上的 dotnet/corefx 存储库中对[不可变对象支持](https://github.com/dotnet/corefx/issues/38569)的 GitHub 问题和对[只读属性的支持问题](https://github.com/dotnet/corefx/issues/38163)。
* 默认情况下，枚举作为数字支持。
* 不支持字段。
* 默认情况下，JSON 中的注释或尾随逗号引发异常。 如果需要[，可以允许注释和尾随逗号](#allow-comments-and-trailing-commas)。
* [默认的最大深度](xref:System.Text.Json.JsonReaderOptions.MaxDepth)为64。

## <a name="serialize-to-formatted-json"></a>序列化为格式化的 JSON

若要整齐地打印 JSON 输出，请将 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> 设置为 `true`：

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

下面是要序列化的示例类型和 JSON 输出：

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

## <a name="allow-comments-and-trailing-commas"></a>允许注释和尾随逗号

默认情况下，JSON 中不允许使用注释和尾随逗号。 若要允许 JSON 中的注释，请将 <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> 属性设置为 `JsonCommentHandling.Skip`。 若要允许尾随逗号，请将 <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> 属性设置为 `true`。 下面的示例演示如何允许两种方法：

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

下面是包含注释和尾随逗号的示例 JSON：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="customize-json-names"></a>自定义 JSON 名称

默认情况下，JSON 输出中的属性名称和字典键不变，包括大小写。 本部分介绍如何执行以下操作：

* 自定义各个属性名称
* 将所有属性名称转换为 camel 大小写
* 实现自定义属性命名策略
* 将字典键转换为 camel 大小写

目前，不支持将枚举自动转换为 camel 大小写。 有关详细信息，请参阅 GitHub 上的 dotnet/corefx 存储库中的[枚举 camel 大小写支持问题](https://github.com/dotnet/corefx/issues/37725)。

### <a name="customize-individual-property-names"></a>自定义各个属性名称

若要设置单个属性的名称，请使用[[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute)属性。

下面是序列化和生成的 JSON 的示例类型：

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

此属性设置的属性名称：

* 同时适用于序列化和反序列化。
* 优先于属性命名策略。

### <a name="use-camel-case-for-all-json-property-names"></a>对所有 JSON 属性名称使用 camel 大小写

若要对所有 JSON 属性名称使用 camel 大小写，请将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 设置为 `JsonNamingPolicy.CamelCase`，如以下示例中所示：

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

下面是一个用于序列化和 JSON 输出的示例类：

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
  "summary": "Hot",
  "Wind": 35
}
```

Camel 大小写属性命名策略：

* 适用于序列化和反序列化。
* 由 `[JsonPropertyName]` 特性重写。

### <a name="use-a-custom-json-property-naming-policy"></a>使用自定义 JSON 属性命名策略

若要使用自定义 JSON 属性命名策略，请创建一个派生自 @no__t 0 的类，并重写 <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> 方法，如以下示例中所示：

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

然后，将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 属性设置为命名策略类的实例：

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

下面是一个用于序列化和 JSON 输出的示例类：

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATUREC": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

JSON 属性命名策略：

* 适用于序列化和反序列化。
* 由 `[JsonPropertyName]` 特性重写。

### <a name="camel-case-dictionary-keys"></a>Camel 大小写字典密钥

如果要序列化的对象的属性的类型为 `Dictionary<string,TValue>`，则可以将 @no__t 键转换为 camel 大小写形式。 为此，请将 @no__t 设置为 `JsonNamingPolicy.CamelCase`，如以下示例中所示：

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

下面是一个示例对象，用于序列化和 JSON 输出：

|属性 |ReplTest1  |
|---------|---------|
| Date    | 8/1/2019 12:00:00 AM-07:00|
| TemperatureC| 25 |
| 总结| 修复|
| TemperatureRanges | 冷，20<br>热，40|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "cold": 20,
    "hot": 40
  }
}
```

Camel 大小写命名策略仅适用于序列化。

## <a name="exclude-properties"></a>排除属性

默认情况下，将序列化所有公共属性。 如果你不想让某些用户出现在 JSON 输出中，则可以使用几个选项。 本部分介绍如何排除：

* 单个属性
* 所有只读属性
* 所有 null 值属性 

### <a name="exclude-individual-properties"></a>排除单个属性

若要忽略各个属性，请使用[[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute)属性。

下面是要序列化的示例类型和 JSON 输出：

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonIgnore]
    public int WindSpeed { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

### <a name="exclude-all-read-only-properties"></a>排除所有只读属性

若要排除所有只读属性，请将 @no__t 设置为 `true`，如以下示例中所示：

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

下面是要序列化的示例类型和 JSON 输出：

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public int WindSpeed { get; private set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
}
```

此选项仅适用于序列化。 在反序列化期间，默认情况下将忽略只读属性。 如果属性包含公共 getter 而不是公共 setter，则该属性为只读。

### <a name="exclude-all-null-value-properties"></a>排除所有 null 值属性

若要排除所有 null 值属性，请将 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> 属性设置为 `true`，如以下示例中所示：

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

下面是一个示例对象，用于序列化和 JSON 输出：

|属性 |ReplTest1  |
|---------|---------|
| Date    | 8/1/2019 12:00:00 AM-07:00|
| TemperatureC| 25 |
| 总结| null|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

此设置适用于序列化和反序列化。 在反序列化过程中，仅当 JSON 中的 null 值有效时才会将其忽略。 不可以为 null 的值类型的 Null 值将导致异常。 有关详细信息，请参阅 GitHub 上的 dotnet/corefx 存储库中[不可以为 null 的值类型的问题](https://github.com/dotnet/corefx/issues/40922)。

## <a name="case-insensitive-property-matching"></a>不区分大小写的属性匹配

默认情况下，反序列化将查找 JSON 与目标对象属性之间区分大小写的属性名称匹配。 若要更改此行为，请将 @no__t 0 设置为 `true`：

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

下面是采用 camel 大小写属性名称的示例 JSON。 它可以反序列化为具有 Pascal 大小写属性名称的以下类型。

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
  "summary": "Hot",
}
```

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

## <a name="include-properties-of-derived-classes"></a>包含派生类的属性

在编译时指定要序列化的类型时，不支持多态序列化。 例如，假设您有一个 @no__t 0 类和一个派生类 `WeatherForecastWithWind`：

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
class WeatherForecastWithWind : WeatherForecast
{
    public int WindSpeed { get; set; }
}
```

并且假设类型传递到，或由推断，在编译时 `Serialize` 方法 @no__t 为-1：

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

```csharp
WeatherForecast weatherForecast;
//...
json = JsonSerializer.Serialize(weatherForecast);
```

在这种情况下，即使 @no__t 对象实际上是 @no__t 2 对象，也不会序列化 `WindSpeed` 属性。 仅序列化基类属性：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

此行为旨在帮助防止在派生的运行时创建的类型中发生意外的数据泄露。

若要序列化派生类型的属性，请使用以下方法之一：

* 调用 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 的重载，以便在运行时指定类型：

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* 将要序列化的对象声明为 `object`。

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

在前面的示例方案中，这两种方法都会导致在 JSON 输出中包含 `WindSpeed` 属性：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

## <a name="handle-overflow-json"></a>句柄溢出 JSON

反序列化时，可能会收到 JSON 中的数据，该数据不是由目标类型的属性表示的。 例如，假设目标类型为：

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

要反序列化的 JSON 如下：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
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

如果将所显示的 JSON 反序列化为显示的类型，则 @no__t 的 "0" 和 "@no__t" 属性没有任何位置，并且将丢失。 若要捕获额外数据（如这些属性），请将[JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute)特性应用于类型 `Dictionary<string,object>` 或 `Dictionary<string,JsonElement>` 的属性：

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonExtensionData]
    public Dictionary<string, object> ExtensionData { get; set; }
}
```

反序列化前面显示的此示例类型的 JSON 时，额外的数据将成为 `ExtensionData` 属性的键值对：

|属性 |ReplTest1  |说明  |
|---------|---------|---------|
| Date    | 8/1/2019 12:00:00 AM-07:00||
| TemperatureC| 0 | 区分大小写不匹配（在 JSON 中 `temperatureC`），因此未设置属性。 |
| 总结 | 修复 ||
| ExtensionData | temperatureC:25 |由于大小写不匹配，因此此 JSON 属性是一个额外的，并成为字典中的键值对。|
|| DatesAvailable:<br>  8/1/2019 12:00:00 AM-07:00<br>8/2/2019 12:00:00 AM-07:00 |JSON 中的额外属性将成为键值对，并将数组作为值对象。|
| |SummaryWords:<br>酷<br>风<br>Humid |JSON 中的额外属性将成为键值对，并将数组作为值对象。|

序列化目标对象时，扩展数据键值对将成为 JSON 属性，就像它们位于传入 JSON 中一样：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 0,
  "Summary": "Hot",
  "temperatureC": 25,
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

请注意，`ExtensionData` 属性名称未出现在 JSON 中。 此行为允许 JSON 进行往返，而不会丢失任何不会被反序列化的额外数据。

## <a name="use-utf8jsonwriter-directly"></a>直接使用 Utf8JsonWriter

下面的示例演示如何直接使用 @no__t 0 类。

```csharp
var options = new JsonWriterOptions
{
    Indented = true
};

using (var stream = new MemoryStream())
{
    using (var writer = new Utf8JsonWriter(stream, options))
    {
        writer.WriteStartObject();
        writer.WriteString("date", DateTimeOffset.UtcNow);
        writer.WriteNumber("temp", 42);
        writer.WriteEndObject();
    }

    string json = Encoding.UTF8.GetString(stream.ToArray());
    Console.WriteLine(json);
}
```

## <a name="use-utf8jsonreader-directly"></a>直接使用 Utf8JsonReader

下面的示例演示如何直接使用 @no__t 0 类。 此代码假定 `jsonUtf8` 变量是包含有效 JSON 的字节数组，编码为 UTF-8。

```csharp
var options = new JsonReaderOptions
{
    AllowTrailingCommas = true,
    CommentHandling = JsonCommentHandling.Skip
};
Utf8JsonReader reader = new Utf8JsonReader(jsonUtf8, options);

while (reader.Read())
{
    Console.Write(reader.TokenType);

    switch (reader.TokenType)
    {
        case JsonTokenType.PropertyName:
        case JsonTokenType.String:
            {
                string text = reader.GetString();
                Console.Write(" ");
                Console.Write(text);
                break;
            }

        case JsonTokenType.Number:
            {
                int value = reader.GetInt32();
                Console.Write(" ");
                Console.Write(value);
                break;
            }

            // Other token types elided for brevity
    }

    Console.WriteLine();
}
```

## <a name="additional-resources"></a>其他资源

* [System.web 概述](system-text-json-overview.md)
* [System.web API 参考](xref:System.Text.Json)
* [系统中的 DateTime 和 DateTimeOffset 支持](../datetime/system-text-json-support.md)
