---
title: 如何编写用于 JSON 序列化的自定义转换器-.NET
author: tdykstra
ms.author: tdykstra
ms.date: 10/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: 33d1cd7764e71d9e2fa382c9f3c5feb77e8defb4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283352"
---
# <a name="how-to-write-custom-converters-for-json-serialization-in-net"></a>如何在 .NET 中编写用于 JSON 序列化的自定义转换器

本文介绍如何为 <xref:System.Text.Json> 命名空间中提供的 JSON 序列化类创建自定义转换器。 有关 `System.Text.Json`的简介，请参阅[如何在 .net 中序列化和反序列化 JSON](system-text-json-how-to.md)。

*转换器*是一个类，用于将对象或值转换为 JSON。 `System.Text.Json` 命名空间为映射到 JavaScript 基元的大多数基元类型提供内置的转换器。 可以编写自定义转换器：

* 重写内置转换器的默认行为。 例如，你可能希望用 mm/dd/yyyy 格式而不是默认 ISO 8601-1:2019 格式来表示 `DateTime` 值。
* 支持自定义值类型。 例如，`PhoneNumber` 结构。

你还可以编写自定义转换器，以利用当前版本中未包含的功能来扩展 `System.Text.Json`。 本文的后面部分介绍了以下方案：

* [将推理出的类型反序列化为对象属性](#deserialize-inferred-types-to-object-properties)。
* [支持带有非字符串键的字典](#support-dictionary-with-non-string-key)。
* [支持多态反序列化](#support-polymorphic-deserialization)。

## <a name="custom-converter-patterns"></a>自定义转换器模式

用于创建自定义转换器的模式有两种：基本模式和工厂模式。 工厂模式适用于处理类型 `Enum` 或开放式泛型的转换器。 基本模式适用于非泛型或封闭式泛型类型。  例如，以下类型的转换器需要工厂模式：

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

可以通过基本模式处理的类型的一些示例包括：

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

基本模式创建可处理一种类型的类。 工厂模式创建一个类，用于在运行时确定需要特定类型，并动态创建适当的转换器。

## <a name="sample-basic-converter"></a>示例基本转换器

下面的示例是一个转换器，用于重写现有数据类型的默认序列化。 转换器使用 mm/dd/yyyy 格式作为 `DateTimeOffset` 属性。

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a>示例工厂模式转换器

下面的代码演示与 `Dictionary<Enum,TValue>`一起使用的自定义转换器。 此代码遵循工厂模式，因为第一个泛型类型参数是 `Enum` 的，第二个是打开的。 `CanConvert` 方法仅对具有两个泛型参数的 `Dictionary` 返回 `true`，其中第一个参数是 `Enum` 类型。 内部转换器将获取一个现有转换器，用于处理在运行时为 `TValue`提供的任何类型。 

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

前面的代码与本文后面的[支持字典中包含非字符串密钥](#support-dictionary-with-non-string-key)的内容相同。

## <a name="steps-to-follow-the-basic-pattern"></a>遵循基本模式的步骤

以下步骤说明了如何通过遵循基本模式创建转换器：

* 创建一个派生自 <xref:System.Text.Json.Serialization.JsonConverter%601> 的类，其中 `T` 是要进行序列化和反序列化的类型。
* 重写 `Read` 方法，以便反序列化传入 JSON 并将其转换为类型 `T`。 使用传递给方法的 <xref:System.Text.Json.Utf8JsonReader> 读取 JSON。
* 重写 `Write` 方法以序列化 `T`类型的传入对象。 使用传递给方法的 <xref:System.Text.Json.Utf8JsonWriter> 来写入 JSON。
* 仅在必要时重写 `CanConvert` 方法。 如果要转换的类型为类型 `T`，则默认实现将返回 `true`。 因此，仅支持类型的转换器 `T` 不需要重写此方法。 有关的确需要重写此方法的转换器的示例，请参阅本文后面的多[态反序列化](#support-polymorphic-deserialization)部分。

可以参考[内置的转换器源代码](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/)，作为编写自定义转换器的参考实现。

## <a name="steps-to-follow-the-factory-pattern"></a>遵循工厂模式的步骤

以下步骤说明了如何按照工厂模式创建转换器：

* 创建一个从 <xref:System.Text.Json.Serialization.JsonConverterFactory> 派生的类。
* 重写 `CanConvert` 方法，以便在转换的类型是转换器可处理的类型时返回 true。 例如，如果转换器适用于 `List<T>` 则它可能仅处理 `List<int>`、`List<string>`和 `List<DateTime>`。 
* 重写 `CreateConverter` 方法，以返回将处理在运行时提供的类型转换的转换器类的实例。
* 创建 `CreateConverter` 方法实例化的转换器类。 

对于开放式泛型，必须使用工厂模式，因为用于将对象转换为字符串和从字符串转换的代码对于所有类型都是相同的。 例如，开放式泛型类型的转换器（例如`List<T>`）必须在幕后创建封闭式泛型类型（如`List<DateTime>`）的转换器。 必须编写代码来处理转换器可处理的每个封闭式泛型类型。

`Enum` 类型类似于开放式泛型类型： `Enum` 的转换器必须为特定的 `Enum` （例如`WeekdaysEnum`）创建转换器。 

## <a name="error-handling"></a>错误处理

如果需要在错误处理代码中引发异常，请考虑不使用消息引发 <xref:System.Text.Json.JsonException>。 此异常类型会自动创建一条消息，其中包括导致错误的 JSON 部分的路径。 例如，语句 `throw new JsonException();` 生成如下所示的错误消息：

```
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

如果您提供了一条消息（例如 `throw new JsonException("Error occurred")`，则异常仍将在 <xref:System.Text.Json.JsonException.Path> 属性中提供路径。

## <a name="register-a-custom-converter"></a>注册自定义转换器

*注册*自定义转换器，使 `Serialize` 和 `Deserialize` 方法使用它。 选择以下方法之一：

* 向 <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> 集合添加转换器类的实例。
* 将[[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute)特性应用于需要自定义转换器的属性。
* 将[[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute)特性应用于表示自定义值类型的类或结构。

## <a name="registration-sample---converters-collection"></a>注册示例-转换器集合 

下面是一个示例，该示例将 <xref:System.ComponentModel.DateTimeOffsetConverter> 类型 <xref:System.DateTimeOffset>的属性的默认值：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

假设您序列化以下类型的实例：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

下面是显示使用自定义转换器的 JSON 输出示例：

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

下面的代码使用与使用自定义 `DateTimeOffset` 转换器相同的方法进行反序列化：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a>注册示例-属性上的 [JsonConverter]

下面的代码选择 `Date` 属性的自定义转换器：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

序列化的代码 `WeatherForecastWithConverterAttribute` 不需要使用 `JsonSerializeOptions.Converters`：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

要反序列化的代码也不需要使用 `Converters`：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a>注册示例-[JsonConverter] 类型

下面是创建结构并向其应用 `[JsonConverter]` 特性的代码：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

下面是前面的结构的自定义转换器：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

结构上的 `[JsonConvert]` 特性将自定义转换器注册为 `Temperature`类型的属性的默认值。 序列化或反序列化时，转换器会自动用于以下类型的 `TemperatureCelsius` 属性：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a>转换器注册优先顺序

在序列化或反序列化过程中，按以下顺序为每个 JSON 元素选择一个转换器，从最高优先级到最低优先级列出：

* 应用于属性的 `[JsonConverter]`。
* 添加到 `Converters` 集合中的转换器。
* `[JsonConverter]` 应用于自定义值类型或 POCO。

如果在 `Converters` 集合中注册了某个类型的多个自定义转换器，则使用第一个为 `CanConvert` 返回 true 的转换器。

仅当未注册适用的自定义转换器时，才会选择内置转换器。

## <a name="converter-samples-for-common-scenarios"></a>常见方案的转换器示例

以下各节提供了一些转换器示例，用于解决内置功能不处理的一些常见方案。

* [反序列化推断类型到对象属性](#deserialize-inferred-types-to-object-properties)
* [支持带有非字符串键的字典](#support-dictionary-with-non-string-key)
* [支持多态反序列化](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a>反序列化推断类型到对象属性

反序列化到类型 `Object`的属性时，将创建一个 `JsonElement` 对象。 这是因为反序列化程序不知道要创建什么 CLR 类型，也不会尝试推测。 例如，如果 JSON 属性的值为 "true"，则反序列化程序不会推断值为 `Boolean`，如果元素有 "01/01/2019"，则反序列化程序不会推断出它是一个 `DateTime`。

类型推理可能不准确。 如果反序列化程序分析的 JSON 数字没有小数点作为 `long`，则当最初将值序列化为 `ulong` 或 `BigInteger`时，这可能会导致超出范围的问题。 如果数字最初序列化为 `decimal`，则将带小数点的数字分析为 `double` 可能会损失精度。

对于需要类型推理的方案，以下代码演示了用于 `Object` 属性的自定义转换器。 代码转换：

* `true` 和 `false` `Boolean`
* 要 `long` 的数字或 `double`
* 要 `DateTime` 的日期
* 要 `string` 的字符串
* 要 `JsonElement` 的其他内容

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

下面的代码注册转换器：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertInferredTypesToObject.cs?name=SnippetRegister)]

下面是包含 `Object` 属性的示例类型：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

以下要反序列化的 JSON 示例包含将作为 `DateTime`、`long`和 `string`进行反序列化的值：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

如果没有自定义转换器，反序列化会将 `JsonElement` 放入每个属性中。

`System.Text.Json.Serialization` 命名空间中的 "[单元测试" 文件夹](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/)包含处理对象属性反序列化的自定义转换器的更多示例。

### <a name="support-dictionary-with-non-string-key"></a>支持带有非字符串键的字典

字典集合的内置支持适用于 `Dictionary<string, TValue>`。 也就是说，键必须是字符串。 若要支持使用整数或其他类型作为键的字典，则需要自定义转换器。

下面的代码演示适用于 `Dictionary<Enum,TValue>`的自定义转换器：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

下面的代码注册转换器：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

转换器可以序列化和反序列化以下类的 `TemperatureRanges` 属性，该类使用以下 `Enum`：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

序列化的 JSON 输出类似于以下示例：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "Cold": 20,
    "Hot": 40
  }
}
```

`System.Text.Json.Serialization` 命名空间中的 "[单元测试" 文件夹](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/)包含处理非字符串键字典的自定义转换器的更多示例。

### <a name="support-polymorphic-deserialization"></a>支持多态反序列化

多[态序列化](system-text-json-how-to.md#serialize-properties-of-derived-classes)不需要自定义转换器，但反序列化确实需要自定义转换器。

例如，假设有一个 `Person` 抽象基类，其中包含 `Employee` 和 `Customer` 派生类。 多态反序列化意味着可以在设计时将 `Person` 指定为反序列化目标，并且 JSON 中的 `Customer` 和 `Employee` 对象在运行时正确地反序列化。 在反序列化过程中，您必须查找识别 JSON 中所需类型的线索。 每个方案都有不同的可用线索类型。 例如，可以使用鉴别器属性，或者可能需要依赖于是否存在特定属性。 `System.Text.Json` 的当前版本不提供特性来指定如何处理多态反序列化方案，因此需要自定义转换器。

下面的代码演示一个基类、两个派生类和一个基类的自定义转换器。 转换器使用鉴别器属性执行多态反序列化。 类型鉴别器不在类定义中，而是在序列化过程中创建的，在反序列化期间读取。

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

下面的代码注册转换器：

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertPolymorphic.cs?name=SnippetRegister)]

转换器可以反序列化使用同一转换器进行序列化而创建的 JSON，例如：

```json
[
  {
    "TypeDiscriminator": 1,
    "CreditLimit": 10000,
    "Name": "John"
  },
  {
    "TypeDiscriminator": 2,
    "OfficeNumber": "555-1234",
    "Name": "Nancy"
  }
]
```

## <a name="other-custom-converter-samples"></a>其他自定义转换器示例

`System.Text.Json.Serialization` 源代码中的 "[单元测试" 文件夹](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/)包含其他自定义转换器示例，例如：

* 在反序列化时将 null 转换为0的 `Int32` 转换器
* `Int32` 允许在反序列化时字符串和数字值的转换器
* `Enum` 转换器
* 接受外部数据 `List<T>` 转换器
* 使用以逗号分隔的数字列表的 `Long[]` 转换器 

## <a name="additional-resources"></a>其他资源

* [System.web 概述](system-text-json-overview.md)
* [System.web API 参考](xref:System.Text.Json)
* [如何使用 system.exception](system-text-json-how-to.md)
* [内置转换器的源代码](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/)
* 与 `System.Text.Json` 的自定义转换器相关的 GitHub 问题
  * [36639引入自定义转换器](https://github.com/dotnet/corefx/issues/36639)
  * [38713有关反序列化到对象的信息](https://github.com/dotnet/corefx/issues/38713)
  * [40120关于非字符串键字典](https://github.com/dotnet/corefx/issues/40120)
  * [37787关于多态反序列化](https://github.com/dotnet/corefx/issues/37787)
