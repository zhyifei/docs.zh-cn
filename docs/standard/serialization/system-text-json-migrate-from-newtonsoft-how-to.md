---
title: 从Newtonsoft.Json迁移到System.Text.Json- .NET
author: tdykstra
ms.author: tdykstra
no-loc:
- System.Text.Json
- Newtonsoft.Json
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 0828a5654171df39230055215903d3a49690155d
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739240"
---
# <a name="how-to-migrate-from-newtonsoftjson-to-systemtextjson"></a>如何从 Newtonsoft.Json 迁移到 System.Text.Json

本文演示如何从[牛顿软迁移到](https://www.newtonsoft.com/json) <xref:System.Text.Json>。

命名`System.Text.Json`空间提供了从 JavaScript 对象表示法 （JSON） 序列化和反序列化的功能。 该`System.Text.Json`库包含在[.NET Core 3.0](https://aka.ms/netcore3download)共享框架中。 对于其他目标框架，请安装[System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet 包。 该包支持：

* .NET 标准 2.0 及更高版本
* .NET 框架 4.7.2 及更高版本
* .NET 核心 2.0、2.1 和 2.2

`System.Text.Json`主要关注性能、安全性和标准合规性。 它在默认行为上有一些关键差异，并且并不旨在与`Newtonsoft.Json`具有功能奇偶校验。 对于某些方案，`System.Text.Json`没有内置功能，但建议使用解决方法。 对于其他方案，解决方法不切实际。 如果应用程序依赖于缺少的功能，请考虑[提交问题](https://github.com/dotnet/runtime/issues/new)，以了解是否可以添加对方案的支持。

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

本文的大部分内容是关于如何使用<xref:System.Text.Json.JsonSerializer>API 的，但它也包括有关如何使用<xref:System.Text.Json.JsonDocument>（表示文档对象模型或 DOM）<xref:System.Text.Json.Utf8JsonReader>和<xref:System.Text.Json.Utf8JsonWriter>类型的指南。

## <a name="table-of-differences-between-newtonsoftjson-and-systemtextjson"></a>牛顿软.Json 和系统之间的差异表.文本.Json

下表列出了`Newtonsoft.Json`功能和`System.Text.Json`等效项。 等效项分为以下几类：

* 内置功能支持。 从`System.Text.Json`中获取类似行为可能需要使用属性或全局选项。
* 不支持，解决方法是可能的。 解决方法是[自定义转换器](system-text-json-converters-how-to.md)，可能无法提供完整的奇偶校验功能`Newtonsoft.Json`。 对于其中一些，示例代码作为示例提供。 如果依赖于这些`Newtonsoft.Json`功能，迁移将需要修改 .NET 对象模型或其他代码更改。
* 不支持，解决方法不可行或可能。 如果依赖于这些`Newtonsoft.Json`功能，则如果不进行重大更改，迁移就不可能实现。

| 牛顿软.Json 功能                               | 系统.文本.Json 等效 |
|-------------------------------------------------------|-----------------------------|
| 默认情况下，不区分大小写的反序列化           | ✔️[属性命名Case敏感全局设置](#case-insensitive-deserialization) |
| 骆驼大小写属性名称                             | ✔️[属性命名策略全局设置](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) |
| 最小字符转义                            | ✔️[严格字符转义，可配置](#minimal-character-escaping) |
| `NullValueHandling.Ignore`全局设置             | ✔️[忽略空值全局选项](system-text-json-how-to.md#exclude-all-null-value-properties) |
| 允许注释                                        | ✔️ [ReadComment 处理全局设置](#comments) |
| 允许尾随逗号                                 | ✔️[允许尾随全球设置](#trailing-commas) |
| 自定义转换器注册                         | ✔️[优先级顺序不同](#converter-registration-precedence) |
| 默认情况下没有最大深度                           | ✔️[默认最大深度 64，可配置](#maximum-depth) |
| 支持多种类型                    | ⚠️[某些类型需要自定义转换器](#types-without-built-in-support) |
| 将字符串反序列化为数字                        | ⚠️[不支持，解决方法，示例](#quoted-numbers) |
| 使用非字符串`Dictionary`键反序列化          | ⚠️[不支持，解决方法，示例](#dictionary-with-non-string-key) |
| 多态序列化                             | ⚠️[不支持，解决方法，示例](#polymorphic-serialization) |
| 多态反序列化                           | ⚠️[不支持，解决方法，示例](#polymorphic-deserialization) |
| 将推断类型反序列化为`object`属性      | ⚠️[不支持，解决方法，示例](#deserialization-of-object-properties) |
| 将 JSON`null`文本序列化为非空值类型 | ⚠️[不支持，解决方法，示例](#deserialize-null-to-non-nullable-type) |
| 反序列化为不可变类和结构          | ⚠️[不支持，解决方法，示例](#deserialize-to-immutable-classes-and-structs) |
| `[JsonConstructor]` 特性                         | ⚠️[不支持，解决方法，示例](#specify-constructor-to-use) |
| `Required`属性上的`[JsonProperty]`设置        | ⚠️[不支持，解决方法，示例](#required-properties) |
| `NullValueHandling`属性上的`[JsonProperty]`设置 | ⚠️[不支持，解决方法，示例](#conditionally-ignore-a-property)  |
| `DefaultValueHandling`属性上的`[JsonProperty]`设置 | ⚠️[不支持，解决方法，示例](#conditionally-ignore-a-property)  |
| `DefaultValueHandling`全局设置                 | ⚠️[不支持，解决方法，示例](#conditionally-ignore-a-property) |
| `DefaultContractResolver`以排除属性       | ⚠️[不支持，解决方法，示例](#conditionally-ignore-a-property) |
| `DateTimeZoneHandling`、`DateFormatString`设置   | ⚠️[不支持，解决方法，示例](#specify-date-format) |
| 回调                                             | ⚠️[不支持，解决方法，示例](#callbacks) |
| 支持公共和非公共字段              | ⚠️[不支持，解决方法](#public-and-non-public-fields) |
| 支持内部和私有财产设置者和获取者 | ⚠️[不支持，解决方法](#internal-and-private-property-setters-and-getters) |
| `JsonConvert.PopulateObject` 方法                   | ⚠️[不支持，解决方法](#populate-existing-objects) |
| `ObjectCreationHandling`全局设置               | ⚠️[不支持，解决方法](#reuse-rather-than-replace-properties) |
| 添加到没有设置器的集合                    | ⚠️[不支持，解决方法](#add-to-collections-without-setters) |
| `PreserveReferencesHandling`全局设置           | ❌ [不支持](#preserve-object-references-and-handle-loops) |
| `ReferenceLoopHandling`全局设置                | ❌ [不支持](#preserve-object-references-and-handle-loops) |
| 对属性`System.Runtime.Serialization`的支持 | ❌ [不支持](#systemruntimeserialization-attributes) |
| `MissingMemberHandling`全局设置                | ❌ [不支持](#missingmemberhandling) |
| 允许没有引号的属性名称                   | ❌ [不支持](#json-strings-property-names-and-string-values) |
| 允许字符串值周围的单引号              | ❌ [不支持](#json-strings-property-names-and-string-values) |
| 允许字符串属性的非字符串 JSON 值    | ❌ [不支持](#non-string-values-for-string-properties) |

这不是功能的`Newtonsoft.Json`详尽列表。 该列表包括[GitHub 问题](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)或[堆栈溢出](https://stackoverflow.com/questions/tagged/system.text.json)帖子中请求的许多方案。 如果为此处列出的当前没有示例代码的方案之一实现解决方法，并且想要共享解决方案，请在此页面底部**的"反馈"** 部分中选择**此页面**。 这在本文档的 GitHub 存储库中造成了问题，并在此页上**的"反馈"** 部分中列出。

## <a name="differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson"></a>与牛顿软相比，默认Json序列器行为的差异

<xref:System.Text.Json>默认情况下严格，避免代表呼叫者进行任何猜测或解释，强调确定性行为。 为了性能和安全性，特意设计了此库。 `Newtonsoft.Json`默认情况下是灵活的。 这种在设计上的根本差异是以下许多默认行为的具体差异的背后。

### <a name="case-insensitive-deserialization"></a>区分大小写反序列化

在反序列化期间`Newtonsoft.Json`，默认情况下执行不区分大小写的属性名称匹配。 <xref:System.Text.Json>默认值区分大小写，由于执行完全匹配，因此性能更好。 有关如何执行不区分大小写匹配的信息，请参阅[不区分大小写的属性匹配](system-text-json-how-to.md#case-insensitive-property-matching)。

如果您使用ASP.NET酷间接`System.Text.Json`使用，则无需执行任何操作，例如`Newtonsoft.Json`。 ASP.NET Core 指定[骆驼大小写属性名称](system-text-json-how-to.md#use-camel-case-for-all-json-property-names)的设置，以及使用`System.Text.Json`时不区分大小写的匹配。

### <a name="minimal-character-escaping"></a>最小字符转义

在序列化期间`Newtonsoft.Json`，对于让字符通过而不逃避字符相对宽松。 也就是说，它不会将它们替换为`\uxxxx``xxxx`字符的代码点。 当它从它们转义时，它通过在字符之前发出`\`一个（例如，`"`变为`\"`） 来这样做。 <xref:System.Text.Json>默认情况下，可以逃避更多字符，以提供纵深防御，防止跨站点脚本 （XSS） 或信息泄露攻击，并使用六个字符序列这样做。 `System.Text.Json`默认情况下，将转义所有非 ASCII 字符，因此，如果您在`StringEscapeHandling.EscapeNonAscii`中使用`Newtonsoft.Json`，则无需执行任何操作。 `System.Text.Json`默认情况下，也会转义对 HTML 敏感的字符。 有关如何重写默认`System.Text.Json`行为的信息，请参阅[自定义字符编码](system-text-json-how-to.md#customize-character-encoding)。

### <a name="comments"></a>注释

在反序列化期间`Newtonsoft.Json`，默认情况下忽略 JSON 中的注释。 默认值<xref:System.Text.Json>是引发注释异常，因为[RFC 8259](https://tools.ietf.org/html/rfc8259)规范不包括它们。 有关如何允许注释的信息，请参阅[允许注释和尾随逗号](system-text-json-how-to.md#allow-comments-and-trailing-commas)。

### <a name="trailing-commas"></a>尾随逗号

在反序列化期间`Newtonsoft.Json`，默认情况下忽略尾随逗号。 它还忽略多个尾随逗号（例如， `[{"Color":"Red"},{"Color":"Green"},,]`。 默认值<xref:System.Text.Json>是引发尾随逗号的异常，因为[RFC 8259](https://tools.ietf.org/html/rfc8259)规范不允许它们。 有关如何接受`System.Text.Json`它们的信息，请参阅[允许注释和尾随逗号](system-text-json-how-to.md#allow-comments-and-trailing-commas)。 无法允许多个尾随逗号。

### <a name="converter-registration-precedence"></a>转换器注册优先级

自定义`Newtonsoft.Json`转换器的注册优先级如下：

* 属性的属性
* 类型的属性
* [转换器](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm)集合

此顺序表示集合中的`Converters`自定义转换器由通过在类型级别应用属性而注册的转换器覆盖。 这两个注册都由属性级别的属性覆盖。

自定义<xref:System.Text.Json>转换器的注册优先级不同：

* 属性的属性
* <xref:System.Text.Json.JsonSerializerOptions.Converters>收集
* 类型的属性

此处的区别是`Converters`集合中的自定义转换器在类型级别覆盖属性。 此优先级顺序背后的意图是使运行时更改覆盖设计时选择。 没有办法更改优先级。

有关自定义转换器注册的详细信息，请参阅[注册自定义转换器](system-text-json-converters-how-to.md#register-a-custom-converter)。

### <a name="maximum-depth"></a>最大深度

`Newtonsoft.Json`默认情况下，没有最大深度限制。 对于<xref:System.Text.Json>有一个默认限制 64，并且可以通过设置<xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>来配置。

### <a name="json-strings-property-names-and-string-values"></a>JSON 字符串（属性名称和字符串值）

在反序列化期间`Newtonsoft.Json`，接受由双引号、单引号或无引号括起来的属性名称。 它接受由双引号或单引号括起来的字符串值。 例如，`Newtonsoft.Json`接受以下 JSON：

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

`System.Text.Json`仅接受双引号的属性名称和字符串值，因为[RFC 8259](https://tools.ietf.org/html/rfc8259)规范需要该格式，并且是唯一被视为有效 JSON 的格式。

包含在单个报价中的值会产生[JsonException，](xref:System.Text.Json.JsonException)并显示以下消息：

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a>字符串属性的非字符串值

`Newtonsoft.Json`接受非字符串值，如数字或文本`true`和`false`，以便对类型字符串的属性进行反序列化。 下面是一个 JSON 的示例，`Newtonsoft.Json`它成功地反序列化到以下类：

```json
{
  "String1": 1,
  "String2": true,
  "String3": false
}
```

```csharp
public class ExampleClass
{
    public string String1 { get; set; }
    public string String2 { get; set; }
    public string String3 { get; set; }
}
```

`System.Text.Json`不会将非字符串值解序列化为字符串属性。 为字符串字段接收的非字符串值会导致[JonException，](xref:System.Text.Json.JsonException)并显示以下消息：

```
The JSON value could not be converted to System.String.
```

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a>使用 Json 序列化器需要解决方法的方案

内置功能不支持以下方案，但可以采用解决方法。 解决方法是[自定义转换器](system-text-json-converters-how-to.md)，可能无法提供完整的奇偶校验功能`Newtonsoft.Json`。 对于其中一些，示例代码作为示例提供。 如果依赖于这些`Newtonsoft.Json`功能，迁移将需要修改 .NET 对象模型或其他代码更改。

### <a name="types-without-built-in-support"></a>没有内置支持的类型

<xref:System.Text.Json>不为以下类型提供内置支持：

* <xref:System.Data.DataTable>和相关类型
* F# 类型，如[区分联合](../../fsharp/language-reference/discriminated-unions.md)、[记录类型](../../fsharp/language-reference/records.md)和[匿名记录类型](../../fsharp/language-reference/anonymous-records.md)。
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <xref:System.ValueTuple>及其关联的泛型类型

可以为没有内置支持的类型实现自定义转换器。

### <a name="quoted-numbers"></a>报价数字

`Newtonsoft.Json`可以序列化或去序列化 JSON 字符串表示的数字（由引号包围）。 例如，它可以接受：`{"DegreesCelsius":"23"}`而不是 。 `{"DegreesCelsius":23}` 要在 中<xref:System.Text.Json>启用该行为，可以实现自定义转换器，如下所示。 转换器处理定义为`long`的属性：

* 它将它们序列化为 JSON 字符串。
* 它在反序列化时接受报价中的JSON数字和数字。

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/LongToStringConverter.cs)]

`long`通过在单个属性上[使用属性](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property)或[将转换器添加到](system-text-json-converters-how-to.md#registration-sample---converters-collection)<xref:System.Text.Json.JsonSerializerOptions.Converters>集合中来注册此自定义转换器。

### <a name="dictionary-with-non-string-key"></a>带非字符串键的字典

`Newtonsoft.Json`支持 类型的`Dictionary<TKey, TValue>`集合。 中<xref:System.Text.Json>对字典集合的内置支持仅限于`Dictionary<string, TValue>`。 也就是说，键必须是字符串。

要支持以整数或某种类型的字典作为键，请创建一个转换器，如["如何编写自定义转换器](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key)"中的示例。

### <a name="polymorphic-serialization"></a>多态序列化

`Newtonsoft.Json`自动执行多态序列化。 有关 的有限多态序列化功能的信息<xref:System.Text.Json>，请参阅[派生类 的序列化属性](system-text-json-how-to.md#serialize-properties-of-derived-classes)。

描述存在的解决方法是定义可能包含派生类的属性为 类型`object`。 如果这是不可能的，另一个选项是创建一个`Write`转换器，该方法为整个继承类型层次结构，如示例在[如何编写自定义转换器](system-text-json-converters-how-to.md#support-polymorphic-deserialization)。

### <a name="polymorphic-deserialization"></a>多态反序列化

`Newtonsoft.Json`具有在`TypeNameHandling`序列化时向 JSON 添加类型名称元数据的设置。 它使用元数据，同时反序列化，以执行多态反序列化。 <xref:System.Text.Json>可以做有限范围的[多态序列化](system-text-json-how-to.md#serialize-properties-of-derived-classes)，但不能进行多态反序列化。

要支持多态反序列化，请创建一个转换器，如["如何编写自定义转换器](system-text-json-converters-how-to.md#support-polymorphic-deserialization)"中的示例。

### <a name="deserialization-of-object-properties"></a>对象属性的序列化

当`Newtonsoft.Json`反序列化到<xref:System.Object>时， 它：

* 推断 JSON 有效负载`null`（非）中的原始值的类型，并返回存储`string`的 、、、、`boolean``DateTime``long``double`或作为盒装对象。 *基元值*是单个 JSON 值，如 JSON`true`编号`false`、字符串`null`、或 。
* 返回`JObject`或`JArray`用于 JSON 负载中的复杂值。 *复杂值*是大括号 （ ） 内的 JSON`{}`键值对的集合， 或括号内`[]`的值列表 （ 。 大括号或括号中的属性和值可以具有其他属性或值。
* 当有效负载具有`null`JSON 文本时，返回 null 引用。

<xref:System.Text.Json>每当序列化<xref:System.Object>到`JsonElement`时，存储基元值和复杂值的装箱，例如：

* `object` 属性。
* `object`字典值。
* `object`数组值。
* 根`object`。

但是，`System.Text.Json`当`null`有效负载中`Newtonsoft.Json`包含`null`JSON 文本时，请处理 和 返回空引用的相同。

要实现`object`属性的类型推理，请创建一个转换器，如["如何编写自定义转换器](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties)"中的示例。

### <a name="deserialize-null-to-non-nullable-type"></a>将空序列化为非空类型

`Newtonsoft.Json`在以下情况下不会引发异常：

* `NullValueHandling`设置为`Ignore`和
* 在反序列化期间，JSON 包含非空值类型的空值。

在同一方案中，<xref:System.Text.Json>确实会引发异常。 （相应的空处理设置为<xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>.）

如果您拥有目标类型，则最佳解决方法是使有问题的属性为空（例如，更改为`int``int?`。

另一种解决方法是为类型创建转换器，例如处理`DateTimeOffset`类型空值的以下示例：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetNullHandlingConverter.cs)]

[通过使用属性上的属性](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property)或[将转换器添加到](system-text-json-converters-how-to.md#registration-sample---converters-collection)<xref:System.Text.Json.JsonSerializerOptions.Converters>集合中来注册此自定义转换器。

**注：** 前面的转换器**处理空值**的方式与`Newtonsoft.Json`指定默认值的 POCO 不同。 例如，假设以下代码表示目标对象：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

假设使用上述转换器对以下 JSON 进行反序列化：

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

反序列化后，`Date`属性具有 1/1/0001`default(DateTimeOffset)`（），即构造函数中设置的值将被覆盖。 鉴于相同的POCO和JSON，`Newtonsoft.Json`去序列化将留在`Date`财产中1/1/2001。

### <a name="deserialize-to-immutable-classes-and-structs"></a>反序列化为不可变类和结构

`Newtonsoft.Json`可以反序列化为不可变类和结构，因为它可以使用具有参数的构造函数。 <xref:System.Text.Json>仅支持公共无参数构造函数。 作为解决方法，您可以调用具有自定义转换器中参数的构造函数。

下面是具有多个构造函数参数的不可变结构：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePoint.cs#ImmutablePoint)]

下面是一个转换器，可序列化并取消序列化此结构：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePointConverter.cs)]

通过将<xref:System.Text.Json.JsonSerializerOptions.Converters>[转换器添加到集合中来](system-text-json-converters-how-to.md#registration-sample---converters-collection)注册此自定义转换器。

有关处理打开泛型属性的类似转换器的示例，请参阅键[值对的内置转换器](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs)。

### <a name="specify-constructor-to-use"></a>指定要使用的构造函数

该`Newtonsoft.Json``[JsonConstructor]`属性允许您指定在反序列化到 POCO 时调用的构造函数。 <xref:System.Text.Json>仅支持无参数构造函数。 作为解决方法，您可以调用自定义转换器中所需的任何构造函数。 请参阅[反序列化到不可变类和结构的示例](#deserialize-to-immutable-classes-and-structs)。

### <a name="required-properties"></a>必需的属性

在`Newtonsoft.Json`中，通过在`Required``[JsonProperty]`属性上设置指定属性是必需的。 `Newtonsoft.Json`如果 JSON 中未收到标记为所需属性的值，则引发异常。

<xref:System.Text.Json>如果未收到目标类型之一的属性的值，则不会引发异常。 例如，如果您有一个`WeatherForecast`类：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

以下 JSON 已反序列化，没有错误：

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

要使反序列化失败，如果`Date`JSON 中没有属性，则实现自定义转换器。 如果解序列化完成后未设置该属性，`Date`以下示例转换器代码将引发异常：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRequiredPropertyConverter.cs)]

[使用 POCO 类上的属性](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type)或[将转换器添加到](system-text-json-converters-how-to.md#registration-sample---converters-collection)<xref:System.Text.Json.JsonSerializerOptions.Converters>集合中来注册此自定义转换器。

如果遵循此模式，则在递归调用<xref:System.Text.Json.JsonSerializer.Serialize%2A>或<xref:System.Text.Json.JsonSerializer.Deserialize%2A>时不要传递选项对象。 选项对象包含<xref:System.Text.Json.JsonSerializerOptions.Converters%2A>集合。 如果将其传递到`Serialize`或`Deserialize`，则自定义转换器将调用自身，从而产生无限循环，从而导致堆栈溢出异常。 如果默认选项不可行，请使用所需的设置创建选项的新实例。 由于每个新实例单独缓存，此方法将很慢。

前面的转换器代码是一个简化的示例。 如果需要处理属性（如[[JsonIgnore] 或](xref:System.Text.Json.Serialization.JsonIgnoreAttribute)不同的选项（如自定义编码器），则需要其他逻辑。 此外，示例代码不处理构造函数中为其设置默认值的属性。 此方法不区分以下方案：

* JSON 中缺少一个属性。
* 非空类型的属性存在于 JSON 中，但值是类型的默认值，例如 的`int`零。
* 值类型的属性存在于 JSON 中，但该值为 null。

### <a name="conditionally-ignore-a-property"></a>有条件地忽略属性

`Newtonsoft.Json`有几种方法可以有条件地忽略序列化或反序列化的属性：

* `DefaultContractResolver`允许您根据任意条件选择要包括或排除的属性。
* `NullValueHandling`和`DefaultValueHandling`上的`JsonSerializerSettings`设置允许您指定应忽略所有空值或默认值属性。
* 属性`NullValueHandling`上的`DefaultValueHandling``[JsonProperty]`和 设置允许您指定在设置为 null 或默认值时应忽略的单个属性。

<xref:System.Text.Json>提供了在序列化时省略属性的以下方法：

* 属性上的[[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties)属性会导致在序列化期间从 JSON 中省略该属性。
* "[忽略 Nullvalue](system-text-json-how-to.md#exclude-all-null-value-properties)全局"选项允许您排除所有空值属性。
* [通过"忽略只属性](system-text-json-how-to.md#exclude-all-read-only-properties)"全局选项，可以排除所有只读属性。

这些选项**不**允许您：

* 忽略具有类型默认值的所有属性。
* 忽略具有类型默认值的选定属性。
* 如果所选属性的值为空，则忽略它们。
* 忽略基于运行时计算的任意条件选择的属性。

对于该功能，您可以编写自定义转换器。 下面是一个示例 POCO 和一个自定义转换器，说明了此方法：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

如果`Summary`该属性的值为空、空字符串或"N/A"，则转换器会导致在序列化中省略该属性。

通过在[类中使用属性](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type)或将[转换器添加到](system-text-json-converters-how-to.md#registration-sample---converters-collection)<xref:System.Text.Json.JsonSerializerOptions.Converters>集合中来注册此自定义转换器。

此方法需要额外的逻辑，如果：

* POCO 包含复杂的属性。
* 您需要处理属性，如`[JsonIgnore]`或选项，如自定义编码器。

### <a name="specify-date-format"></a>指定日期格式

`Newtonsoft.Json`提供了几种控制 属性`DateTime`和`DateTimeOffset`类型序列化和非序列化的方法：

* 该`DateTimeZoneHandling`设置可用于将所有`DateTime`值序列化为 UTC 日期。
* 设置`DateFormatString`和`DateTime`转换器可用于自定义日期字符串的格式。

在<xref:System.Text.Json>中，唯一具有内置支持的格式是 ISO 8601-1：2019，因为它被广泛采用、明确且精确进行往返。 要使用任何其他格式，请创建自定义转换器。 有关详细信息，请参阅[系统中的日期时间和日期时间偏移支持。](../datetime/system-text-json-support.md)

### <a name="callbacks"></a>回调

`Newtonsoft.Json`允许您在序列化或反序列化过程的几个点执行自定义代码：

* 打开序列化（开始反序列化对象时）
* 打开序列化（完成对象反序列化时）
* 在序列化时（开始序列化对象时）
* 序列化时（完成序列化对象时）

在<xref:System.Text.Json>中，可以通过编写自定义转换器来模拟回调。 下面的示例显示了 POCO 的自定义转换器。 转换器包括代码，该代码在每个点显示对应于`Newtonsoft.Json`回调的消息。

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastCallbacksConverter.cs)]

通过在[类中使用属性](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type)或将[转换器添加到](system-text-json-converters-how-to.md#registration-sample---converters-collection)<xref:System.Text.Json.JsonSerializerOptions.Converters>集合中来注册此自定义转换器。

如果使用遵循上述示例的自定义转换器：

* 代码`OnDeserializing`无法访问新的 POCO 实例。 要在反序列化开始时操作新的 POCO 实例，请将该代码放入 POCO 构造函数中。
* 递归调用`Serialize`或`Deserialize`时，不要传递选项对象。 选项对象包含`Converters`集合。 如果将其传递到`Serialize`或`Deserialize`，则将使用转换器，从而产生无限循环，从而导致堆栈溢出异常。

### <a name="public-and-non-public-fields"></a>公共和非公共字段

`Newtonsoft.Json`可以序列化字段和属性。 <xref:System.Text.Json>仅适用于公共属性。 自定义转换器可以提供此功能。

### <a name="internal-and-private-property-setters-and-getters"></a>内部和私有财产设置者和获取者

`Newtonsoft.Json`可以使用私有和内部属性设置器和获取器通过`JsonProperty`属性。 <xref:System.Text.Json>仅支持公共设置器。 自定义转换器可以提供此功能。

### <a name="populate-existing-objects"></a>填充现有对象

解`JsonConvert.PopulateObject`序列化`Newtonsoft.Json`的 JSON 文档到类的现有实例，而不是创建新实例。 <xref:System.Text.Json>始终使用默认的公共无参数构造函数创建目标类型的新实例。 自定义转换器可以反序列化到现有实例。

### <a name="reuse-rather-than-replace-properties"></a>重用而不是替换属性

该`Newtonsoft.Json``ObjectCreationHandling`设置允许您指定属性中的对象应重复使用，而不是在反序列化期间替换。 <xref:System.Text.Json>始终替换属性中的对象。  自定义转换器可以提供此功能。

### <a name="add-to-collections-without-setters"></a>添加到没有设置器的集合

在反序列化期间`Newtonsoft.Json`，即使属性没有 setter，也会将对象添加到集合中。 <xref:System.Text.Json>忽略没有设置器的属性。 自定义转换器可以提供此功能。

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a>Json 序列化程序当前不支持的方案

对于以下方案，解决方法不可行或不可能。 如果依赖于这些`Newtonsoft.Json`功能，则如果不进行重大更改，迁移就不可能实现。

### <a name="preserve-object-references-and-handle-loops"></a>保留对象引用和句柄循环

默认情况下，`Newtonsoft.Json`按值序列化。 例如，如果对象包含两个属性，其中包含对同`Person`一对象的引用，则该`Person`对象的属性的值将复制在 JSON 中。

`Newtonsoft.Json`具有允许您`PreserveReferencesHandling`按引用`JsonSerializerSettings`序列化的设置：

* 标识符元数据将添加到为第一个`Person`对象创建的 JSON 中。
* 为第二`Person`个对象创建的 JSON 包含对该标识符的引用，而不是属性值。

`Newtonsoft.Json`还有一个`ReferenceLoopHandling`设置，允许您忽略循环引用，而不是引发异常。

<xref:System.Text.Json>仅支持按值序列化，并为循环引用引发异常。

### <a name="systemruntimeserialization-attributes"></a>系统.运行时.序列化属性

<xref:System.Text.Json>不支持命名空间的属性`System.Runtime.Serialization`，如`DataMemberAttribute`和`IgnoreDataMemberAttribute`。

### <a name="octal-numbers"></a>八进制数字

`Newtonsoft.Json`将前导零的数字视为八进制数字。 <xref:System.Text.Json>不允许前导零，因为[RFC 8259](https://tools.ietf.org/html/rfc8259)规范不允许它们。

### <a name="missingmemberhandling"></a>缺少成员处理

`Newtonsoft.Json`如果 JSON 包含目标类型中缺少的属性，则可以配置为在反序列化期间引发异常。 <xref:System.Text.Json>忽略 JSON 中的额外属性，除非使用[[Json 扩展数据] 属性](system-text-json-how-to.md#handle-overflow-json)。 缺少的成员功能没有解决方法。

### <a name="tracewriter"></a>跟踪编写器

`Newtonsoft.Json`允许您使用 查看`TraceWriter`序列化或反序列化生成的日志来调试。 <xref:System.Text.Json>不进行日志记录。

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a>与 JToken 相比，JsonDocument 和 JsonElement（如 JObject、JArray）

<xref:System.Text.Json.JsonDocument?displayProperty=fullName>提供了从现有 JSON 负载解析和构建**只读**文档对象模型 （DOM） 的能力。 DOM 提供对 JSON 负载中数据的随机访问。 构成有效负载的 JSON 元素可通过类型<xref:System.Text.Json.JsonElement>进行访问。 该`JsonElement`类型提供 API 以将 JSON 文本转换为常见的 .NET 类型。 `JsonDocument`公开<xref:System.Text.Json.JsonDocument.RootElement>属性。

### <a name="jsondocument-is-idisposable"></a>JsonDocument 是 I 一次性的

`JsonDocument`将数据的内存中视图构建到池缓冲区中。 因此，与`JObject``JArray`或`Newtonsoft.Json`不同`JsonDocument`，类型`IDisposable`实现和需要在 using 块内使用。

仅当要将`JsonDocument`生存期所有权转移并释放责任给调用方时，才从 API 返回 。 在大多数情况下，这是没有必要的。 如果调用方需要处理整个 JSON 文档，则返回<xref:System.Text.Json.JsonElement.Clone%2A><xref:System.Text.Json.JsonDocument.RootElement%2A><xref:System.Text.Json.JsonElement>中的 。 如果调用方需要使用 JSON 文档中的特定元素，则返回 该<xref:System.Text.Json.JsonElement.Clone%2A><xref:System.Text.Json.JsonElement>元素。 如果在不创建`RootElement`的情况下直接返回 或 子元素`Clone`，则调用方将无法在释放`JsonElement``JsonDocument`拥有的 返回后访问返回。

下面是一个示例，要求您创建 ： `Clone`

```csharp
public JsonElement LookAndLoad(JsonElement source)
{
    string json = File.ReadAllText(source.GetProperty("fileName").GetString());

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        return doc.RootElement.Clone();
    }
}
```

前面的代码需要包含属性`JsonElement`的`fileName`。 它打开 JSON 文件并创建`JsonDocument`一个 。 该方法假定调用方要处理整个文档，因此返回 的`Clone`。 `RootElement`

如果收到`JsonElement`和 正在返回子元素，则无需返回 子元素的 a。 `Clone` 调用方负责保持传入`JsonDocument``JsonElement`所属的处于活动状态。 例如：

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a>JsonDocument 是只读的

DOM<xref:System.Text.Json>无法添加、删除或修改 JSON 元素。 它以这种方式设计是为了提高性能，并减少了用于分析常见 JSON 有效负载大小（即< 1 MB）的分配。 如果方案当前使用可修改的 DOM，则以下解决方法之一可能是可行的：

* 要从头`JsonDocument`开始生成 一个（即，不将现有的 JSON 负载`Parse`传递到方法），请使用 编写 JSON`Utf8JsonWriter`文本，并分析该中的输出以生成新的`JsonDocument`。
* 要修改现有文本`JsonDocument`，请使用它编写 JSON 文本，在写入时进行更改，并分析其输出以创建新`JsonDocument`。
* 要合并现有的 JSON 文档，等效`JObject.Merge`于`JContainer.Merge`中的`Newtonsoft.Json`或 API，请参阅[此 GitHub 问题](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853)。

### <a name="jsonelement-is-a-union-struct"></a>JsonElement 是一个联合结构

`JsonDocument`公开`RootElement`为 类型的<xref:System.Text.Json.JsonElement>属性 ，它是包含任何 JSON 元素的联合结构类型。 `Newtonsoft.Json`使用专用分层类型，`JObject`如`JArray` `JToken`、、、等。 `JsonElement`是您可以搜索和枚举的内容，您可以使用`JsonElement`将 JSON 元素具体化到 .NET 类型中。

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a>如何搜索 JsonDocument 和 JsonElement 的子元素

使用`JObject`或`JArray`从`Newtonsoft.Json`中搜索 JSON 令牌往往相对较快，因为它们是某些字典中的查找。 相比之下，搜索需要`JsonElement`按顺序搜索属性，因此相对较慢（例如，使用`TryGetProperty`时）。 <xref:System.Text.Json>旨在最小化初始分析时间，而不是查找时间。 因此，在搜索`JsonDocument`对象时，请使用以下方法来优化性能：

* 使用内置枚举器 （<xref:System.Text.Json.JsonElement.EnumerateArray%2A>和<xref:System.Text.Json.JsonElement.EnumerateObject%2A>） 而不是执行自己的索引或循环。
* 不要使用`RootElement`对 每个属性执行顺序搜索`JsonDocument`。 相反，根据 JSON 数据的已知结构搜索嵌套的 JSON 对象。 例如`Grade`，如果要在对象中`Student`查找属性，则循环遍历`Student`对象并获取 每个对象的值`Grade`，而不是搜索所有`JsonElement`查找`Grade`属性的对象。 执行后者将导致对同一数据进行不必要的传递。

有关代码示例，请参阅[使用 JsonDocument 访问数据](system-text-json-how-to.md#use-jsondocument-for-access-to-data)。

## <a name="utf8jsonreader-compared-to-jsontextreader"></a>Utf8JsonReader 与 JsonTextReader 相比

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName>是 UTF-8 编码 JSON 文本的高性能、低分配、仅转发读取器，从[ReadOnlySpan\<字节>](xref:System.ReadOnlySpan%601)读取或[\<ReadOnlySequence 字节>](xref:System.Buffers.ReadOnlySequence%601)。 `Utf8JsonReader`是一种低级类型，可用于构建自定义解析器和反序列化器。

以下各节解释使用`Utf8JsonReader`的建议编程模式。

### <a name="utf8jsonreader-is-a-ref-struct"></a>Utf8JonReader 是一个参考结构

由于`Utf8JsonReader`类型是*ref 结构*，因此具有[某些限制](../../csharp/language-reference/builtin-types/struct.md#ref-struct)。 例如，不能将其存储为类或结构上的字段，而不是 ref 结构。 为了实现高性能，此类型必须是 a，`ref struct`因为它需要缓存输入[ReadOnlySpan\<字节>](xref:System.ReadOnlySpan%601)，这本身就是一个 ref 结构。 此外，此类型是可变的，因为它保持状态。 因此，通过 ref 而不是按值**传递它**。 按值传递它将导致结构副本，并且调用方看不到状态更改。 这与 因为`Newtonsoft.Json``Newtonsoft.Json``JsonTextReader`是 类不同。 有关如何使用 ref 结构的详细信息，请参阅[编写安全高效的 C# 代码](../../csharp/write-safe-efficient-code.md)。

### <a name="read-utf-8-text"></a>阅读 UTF-8 文本

为了在使用 时获得最佳性能，`Utf8JsonReader`请阅读 JSON 有效负载，该负载已编码为 UTF-8 文本，而不是 UTF-16 字符串。 有关代码示例，请参阅[使用 Utf8JonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader)筛选数据。

### <a name="read-with-a-stream-or-pipereader"></a>使用流或管道阅读器进行读取

支持`Utf8JsonReader`从 UTF-8 编码的[ReadOnlySpan\<字节>](xref:System.ReadOnlySpan%601)或[ReadOnlySequence\<字节>（](xref:System.Buffers.ReadOnlySequence%601)这是从 读取的结果<xref:System.IO.Pipelines.PipeReader>）读取。

对于同步读取，您可以读取 JSON 有效负载，直到流结束进入字节数组，并将其传递到读取器中。 对于从字符串（编码为 UTF-16）读取，调用<xref:System.Text.Encoding.UTF8>。<xref:System.Text.Encoding.GetBytes%2A> 首先将字符串转码到 UTF-8 编码字节数组。 然后传递给 。 `Utf8JsonReader`

由于`Utf8JsonReader`将输入视为 JSON 文本，因此 UTF-8 字节订单标记 （BOM） 被视为无效的 JSON。 调用方在将数据传递给读取器之前需要筛选出来。

有关代码示例，请参阅[使用 Utf8JonReader](system-text-json-how-to.md#use-utf8jsonreader)。

### <a name="read-with-multi-segment-readonlysequence"></a>使用多段 ReadOnlySequence 进行读取

如果您的 JSON 输入是[ReadOnlySpan\<字节>，](xref:System.ReadOnlySpan%601)则在读取循环时，可以从读取器`ValueSpan`的属性访问每个 JSON 元素。 但是，如果输入是[ReadOnlySequence\<字节>（](xref:System.Buffers.ReadOnlySequence%601)这是从 读取的结果<xref:System.IO.Pipelines.PipeReader>），则某些 JSON 元素可能跨越`ReadOnlySequence<byte>`对象的多个段。 这些元素无法从<xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A>连续内存块中访问。 相反，每当将多段`ReadOnlySequence<byte>`作为输入时，在读取器上<xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A>轮询属性以了解如何访问当前 JSON 元素。 下面是推荐的模式：

```csharp
while (reader.Read())
{
    switch (reader.TokenType)
    {
        // ...
        ReadOnlySpan<byte> jsonElement = reader.HasValueSequence ?
            reader.ValueSequence.ToArray() :
            reader.ValueSpan;
        // ...
    }
}
```

### <a name="use-valuetextequals-for-property-name-lookups"></a>对属性名称查找使用 ValueText 等值

不要使用<xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A>通过调用<xref:System.MemoryExtensions.SequenceEqual%2A>属性名称查找来逐字节比较。 请<xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A>改为调用，因为该方法将取消转义 JSON 中转义的任何字符。 下面是演示如何搜索名为"name"的属性的示例：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a>将空值读取为空值类型

`Newtonsoft.Json`<xref:System.Nullable%601>提供返回 的 API，例如`ReadAsBoolean`，`Null``TokenType`通过返回 来处理`bool?` 内置`System.Text.Json`API 仅返回不可消除的值类型。 例如，<xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType>返回 。 `bool` 如果在 JSON`Null`中找到，它将引发异常。 以下示例显示了处理 null 的两种方法，一种是通过返回空值类型，另一种通过返回默认值来处理空：

```csharp
public bool? ReadAsNullableBoolean()
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return null;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

```csharp
public bool ReadAsBoolean(bool defaultValue)
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return defaultValue;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

### <a name="multi-targeting"></a>多目标

如果需要继续用于`Newtonsoft.Json`某些目标框架，则可以多目标并具有两个实现。 然而，这不是微不足道的，需要一些`#ifdefs`和来源重复。 `ref struct`共享尽可能多的代码的一种方法是围绕`Utf8JsonReader`和`Newtonsoft.Json``JsonTextReader`创建包装器。 此包装器将统一公共表面积，同时隔离行为差异。 这样，您就可以隔离主要对类型构造的更改，以及通过引用传递新类型。 这是[Microsoft.扩展.依赖模型](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/)库遵循的模式：

* [UnifiedJsonReader.JsonTextReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [UnifiedJsonReader.Utf8JsonReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a>Utf8JsonWriter 与 JsonTextWriter 相比

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName>是从常见的 .NET 类型（如`String`）`Int32`和`DateTime`写入 UTF-8 编码的 JSON 文本的高性能方法。 编写器是一种低级类型，可用于构建自定义序列化程序。

以下各节解释使用`Utf8JsonWriter`的建议编程模式。

### <a name="write-with-utf-8-text"></a>使用 UTF-8 文本书写

为了在使用 时获得最佳性能，`Utf8JsonWriter`请编写 JSON 有效负载，该负载已编码为 UTF-8 文本，而不是 UTF-16 字符串。 用于<xref:System.Text.Json.JsonEncodedText>将已知的字符串属性名称和值缓存和预编码为静态，并将这些名称和值传递给编写器，而不是使用 UTF-16 字符串文本。 这比缓存和使用 UTF-8 字节数组更快。

如果需要执行自定义转义，此方法也有效。 `System.Text.Json`不允许您在编写字符串时禁用转义。 但是，您可以将自己的自定义作为选项传递给编写<xref:System.Text.Encodings.Web.JavaScriptEncoder>器，或者创建自己的自定义项`JsonEncodedText`，使用 执行`JavascriptEncoder`转义，然后编写`JsonEncodedText`而不是字符串。 有关详细信息，请参阅[自定义字符编码](system-text-json-how-to.md#customize-character-encoding)。

### <a name="write-raw-values"></a>写入原始值

该方法`Newtonsoft.Json``WriteRawValue`在预期值的地方写入原始 JSON。 <xref:System.Text.Json>没有直接等效项，但下面是一种确保仅写入有效 JSON 的解决方法：

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a>自定义字符转义

[StringEscape处理](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm)设置`JsonTextWriter`提供了用于转义所有非 ASCII 字符**或**HTML 字符的选项。 默认情况下，`Utf8JsonWriter`将转义所有非 ASCII**和**HTML 字符。 此逃生是出于深度安全防御的原因。 要指定不同的转义策略，请创建<xref:System.Text.Encodings.Web.JavaScriptEncoder>和<xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>集 。 有关详细信息，请参阅[自定义字符编码](system-text-json-how-to.md#customize-character-encoding)。

### <a name="customize-json-format"></a>自定义 JSON 格式

`JsonTextWriter`包括以下设置，这些`Utf8JsonWriter`设置没有等效设置：

* [缩进](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm)- 指定缩进的字符数。 `Utf8JsonWriter`总是做两个字符的缩进。
* [缩进符](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm)- 指定用于缩进的字符。  `Utf8JsonWriter`始终使用空白。
* [报价字符](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm)- 指定用于环绕字符串值的字符。  `Utf8JsonWriter`始终使用双引号。
* [报价名称](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm)- 指定是否用引号括括属性名称。  `Utf8JsonWriter`总是用引号包围他们。

没有解决方法可以允许您自定义`Utf8JsonWriter`以这些方式生成的 JSON。

### <a name="write-null-values"></a>写入空值

要使用 调用`Utf8JsonWriter`写入空值：

* <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A>编写一个键值对，其中 null 为值。
* <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A>将 null 写入 JSON 数组的元素。

对于字符串属性，如果字符串为<xref:System.Text.Json.Utf8JsonWriter.WriteString%2A>null，并且<xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>等效于`WriteNull`和`WriteNullValue`。

### <a name="write-timespan-uri-or-char-values"></a>写入时间跨度、Uri 或字符值

`JsonTextWriter`提供了`WriteValue` [TimeSpan、Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm)和[字符](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm)值的方法。 [Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm) `Utf8JsonWriter`没有等效的方法。 相反，将这些值格式化为字符串（例如，`ToString()`通过调用）和调用<xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>。

### <a name="multi-targeting"></a>多目标

如果需要继续用于`Newtonsoft.Json`某些目标框架，则可以多目标并具有两个实现。 然而，这不是微不足道的，需要一些`#ifdefs`和来源重复。 共享尽可能多的代码的一种方法是围绕`Utf8JsonWriter`和`Newtonsoft``JsonTextWriter`创建包装器。 此包装器将统一公共表面积，同时隔离行为差异。 这允许您隔离主要对类型的构造的更改。 [Microsoft.扩展.依赖模型](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/)库如下：

* [UnifiedJsonWriter.JsonTextWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [UnifiedJsonWriter.Utf8JsonWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a>其他资源

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* [System.Text.Json概述](system-text-json-overview.md)
* [如何使用System.Text.Json](system-text-json-how-to.md)
* [如何编写自定义转换器](system-text-json-converters-how-to.md)
* [日期时间和日期时间偏移支持System.Text.Json](../datetime/system-text-json-support.md)
* [System.Text.JsonAPI 参考](xref:System.Text.Json)
* [System.Text.Json.序列化 API 引用](xref:System.Text.Json.Serialization)
