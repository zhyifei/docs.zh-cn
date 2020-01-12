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
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="feb52-102">如何在 .NET 中对 JSON 进行序列化和反序列化（marshal 和取消封送）</span><span class="sxs-lookup"><span data-stu-id="feb52-102">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="feb52-103">本文介绍如何使用 <xref:System.Text.Json> 命名空间在 JavaScript 对象表示法（JSON）之间进行序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="feb52-103">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="feb52-104">方向和示例代码直接使用库，而不是通过框架（如[ASP.NET Core](/aspnet/core/)）使用。</span><span class="sxs-lookup"><span data-stu-id="feb52-104">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="feb52-105">大多数序列化示例代码将 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> 设置为 `true` JSON （对于人工可读性，为缩进和空格）。</span><span class="sxs-lookup"><span data-stu-id="feb52-105">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="feb52-106">对于生产用途，通常会接受此设置的默认 `false` 值。</span><span class="sxs-lookup"><span data-stu-id="feb52-106">For production use, you would typically accept the default value of `false` for this setting.</span></span>

## <a name="namespaces"></a><span data-ttu-id="feb52-107">命名空间</span><span class="sxs-lookup"><span data-stu-id="feb52-107">Namespaces</span></span>

<span data-ttu-id="feb52-108"><xref:System.Text.Json> 命名空间包含所有入口点和主要类型。</span><span class="sxs-lookup"><span data-stu-id="feb52-108">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="feb52-109"><xref:System.Text.Json.Serialization> 命名空间包含用于高级方案的属性和 Api，以及特定于序列化和反序列化的自定义。</span><span class="sxs-lookup"><span data-stu-id="feb52-109">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="feb52-110">本文中所示的代码示例要求其中一个或两个命名空间都有 `using` 指令：</span><span class="sxs-lookup"><span data-stu-id="feb52-110">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="feb52-111">`System.Text.Json`当前不支持 <xref:System.Runtime.Serialization> 命名空间中的属性。</span><span class="sxs-lookup"><span data-stu-id="feb52-111">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="feb52-112">如何将 .NET 对象写入 JSON （序列化）</span><span class="sxs-lookup"><span data-stu-id="feb52-112">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="feb52-113">若要将 JSON 写入字符串或文件，请调用 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="feb52-113">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="feb52-114">下面的示例将 JSON 创建为字符串：</span><span class="sxs-lookup"><span data-stu-id="feb52-114">The following example creates JSON as a string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="feb52-115">下面的示例使用同步代码创建 JSON 文件：</span><span class="sxs-lookup"><span data-stu-id="feb52-115">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="feb52-116">下面的示例使用异步代码创建 JSON 文件：</span><span class="sxs-lookup"><span data-stu-id="feb52-116">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="feb52-117">前面的示例对要序列化的类型使用类型推理。</span><span class="sxs-lookup"><span data-stu-id="feb52-117">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="feb52-118">`Serialize()` 的重载采用泛型类型参数：</span><span class="sxs-lookup"><span data-stu-id="feb52-118">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="feb52-119">序列化示例</span><span class="sxs-lookup"><span data-stu-id="feb52-119">Serialization example</span></span>

<span data-ttu-id="feb52-120">下面是包含集合和嵌套类的示例类：</span><span class="sxs-lookup"><span data-stu-id="feb52-120">Here's an example class that contains collections and a nested class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

<span data-ttu-id="feb52-121">序列化上述类型的实例的 JSON 输出类似于下面的示例。</span><span class="sxs-lookup"><span data-stu-id="feb52-121">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="feb52-122">默认情况下，JSON 输出为缩小：</span><span class="sxs-lookup"><span data-stu-id="feb52-122">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="feb52-123">下面的示例演示了相同的 JSON 格式（也就是用空格和缩进进行整齐打印）：</span><span class="sxs-lookup"><span data-stu-id="feb52-123">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="feb52-124">序列化为 UTF-8</span><span class="sxs-lookup"><span data-stu-id="feb52-124">Serialize to UTF-8</span></span>

<span data-ttu-id="feb52-125">若要序列化为 UTF-8，请调用 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 方法：</span><span class="sxs-lookup"><span data-stu-id="feb52-125">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="feb52-126">还提供了一个采用 <xref:System.Text.Json.Utf8JsonWriter> 的 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 重载。</span><span class="sxs-lookup"><span data-stu-id="feb52-126">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="feb52-127">序列化为 UTF-8 比使用基于字符串的方法更快5-10%。</span><span class="sxs-lookup"><span data-stu-id="feb52-127">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="feb52-128">不同之处在于，不需要将字节（如 UTF-8）转换为字符串（UTF-16）。</span><span class="sxs-lookup"><span data-stu-id="feb52-128">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="feb52-129">序列化行为</span><span class="sxs-lookup"><span data-stu-id="feb52-129">Serialization behavior</span></span>

* <span data-ttu-id="feb52-130">默认情况下，将序列化所有公共属性。</span><span class="sxs-lookup"><span data-stu-id="feb52-130">By default, all public properties are serialized.</span></span> <span data-ttu-id="feb52-131">您可以[指定要排除的属性](#exclude-properties-from-serialization)。</span><span class="sxs-lookup"><span data-stu-id="feb52-131">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="feb52-132">[默认编码器](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)会转义非 ascii 字符、ASCII 范围内的 HTML 敏感字符以及必须根据[RFC 8259 JSON 规范](https://tools.ietf.org/html/rfc8259#section-7)进行转义的字符。</span><span class="sxs-lookup"><span data-stu-id="feb52-132">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="feb52-133">默认情况下，JSON 为缩小。</span><span class="sxs-lookup"><span data-stu-id="feb52-133">By default, JSON is minified.</span></span> <span data-ttu-id="feb52-134">可以很好[打印 JSON](#serialize-to-formatted-json)。</span><span class="sxs-lookup"><span data-stu-id="feb52-134">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="feb52-135">默认情况下，JSON 名称的大小写与 .NET 名称匹配。</span><span class="sxs-lookup"><span data-stu-id="feb52-135">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="feb52-136">你可以[自定义 JSON 名称大小写](#customize-json-names-and-values)。</span><span class="sxs-lookup"><span data-stu-id="feb52-136">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="feb52-137">检测到循环引用并引发异常。</span><span class="sxs-lookup"><span data-stu-id="feb52-137">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="feb52-138">当前排除了字段。</span><span class="sxs-lookup"><span data-stu-id="feb52-138">Currently, fields are excluded.</span></span>

<span data-ttu-id="feb52-139">支持的类型包括：</span><span class="sxs-lookup"><span data-stu-id="feb52-139">Supported types include:</span></span>

* <span data-ttu-id="feb52-140">映射到 JavaScript 基元的 .NET 基元，如数值类型、字符串和布尔值。</span><span class="sxs-lookup"><span data-stu-id="feb52-140">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="feb52-141">用户定义的[普通旧 CLR 对象（poco）](https://stackoverflow.com/questions/250001/poco-definition)。</span><span class="sxs-lookup"><span data-stu-id="feb52-141">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="feb52-142">一维数组和交错数组（`ArrayName[][]`）。</span><span class="sxs-lookup"><span data-stu-id="feb52-142">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="feb52-143">`Dictionary<string,TValue>`，其中 `TValue` 为 `object`、`JsonElement`或 POCO。</span><span class="sxs-lookup"><span data-stu-id="feb52-143">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="feb52-144">以下命名空间中的集合。</span><span class="sxs-lookup"><span data-stu-id="feb52-144">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="feb52-145">您可以[实现自定义转换器](system-text-json-converters-how-to.md)来处理其他类型或提供内置转换器不支持的功能。</span><span class="sxs-lookup"><span data-stu-id="feb52-145">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="feb52-146">如何将 JSON 读入 .NET 对象（反序列化）</span><span class="sxs-lookup"><span data-stu-id="feb52-146">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="feb52-147">若要从字符串或文件进行反序列化，请调用 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="feb52-147">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="feb52-148">下面的示例从字符串读取 JSON，并为[序列化示例](#serialization-example)创建前面所示 `WeatherForecast` 类的实例：</span><span class="sxs-lookup"><span data-stu-id="feb52-148">The following example reads JSON from a string and creates an instance of the `WeatherForecast` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="feb52-149">若要通过使用同步代码从文件进行反序列化，请将文件读入字符串中，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="feb52-149">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="feb52-150">若要使用异步代码从文件进行反序列化，请调用 <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> 方法：</span><span class="sxs-lookup"><span data-stu-id="feb52-150">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="feb52-151">从 UTF-8 反序列化</span><span class="sxs-lookup"><span data-stu-id="feb52-151">Deserialize from UTF-8</span></span>

<span data-ttu-id="feb52-152">若要从 UTF-8 进行反序列化，请调用采用 `Utf8JsonReader` 或 `ReadOnlySpan<byte>`的 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 重载，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="feb52-152">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="feb52-153">这些示例假定 JSON 位于名为 jsonUtf8Bytes 的字节数组中。</span><span class="sxs-lookup"><span data-stu-id="feb52-153">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="feb52-154">反序列化行为</span><span class="sxs-lookup"><span data-stu-id="feb52-154">Deserialization behavior</span></span>

* <span data-ttu-id="feb52-155">默认情况下，属性名称匹配区分大小写。</span><span class="sxs-lookup"><span data-stu-id="feb52-155">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="feb52-156">可以[指定不区分大小写](#case-insensitive-property-matching)。</span><span class="sxs-lookup"><span data-stu-id="feb52-156">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="feb52-157">如果 JSON 包含只读属性的值，则该值将被忽略，并且不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="feb52-157">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="feb52-158">不支持反序列化到不具有无参数构造函数的引用类型。</span><span class="sxs-lookup"><span data-stu-id="feb52-158">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="feb52-159">不支持对不可变对象或只读属性进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="feb52-159">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="feb52-160">默认情况下，枚举作为数字支持。</span><span class="sxs-lookup"><span data-stu-id="feb52-160">By default, enums are supported as numbers.</span></span> <span data-ttu-id="feb52-161">可以将[枚举名称序列化为字符串](#enums-as-strings)。</span><span class="sxs-lookup"><span data-stu-id="feb52-161">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="feb52-162">不支持字段。</span><span class="sxs-lookup"><span data-stu-id="feb52-162">Fields aren't supported.</span></span>
* <span data-ttu-id="feb52-163">默认情况下，JSON 中的注释或尾随逗号引发异常。</span><span class="sxs-lookup"><span data-stu-id="feb52-163">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="feb52-164">您可以[允许注释和尾随逗号](#allow-comments-and-trailing-commas)。</span><span class="sxs-lookup"><span data-stu-id="feb52-164">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="feb52-165">[默认的最大深度](xref:System.Text.Json.JsonReaderOptions.MaxDepth)为64。</span><span class="sxs-lookup"><span data-stu-id="feb52-165">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="feb52-166">您可以[实现自定义转换器](system-text-json-converters-how-to.md)以提供内置转换器不支持的功能。</span><span class="sxs-lookup"><span data-stu-id="feb52-166">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="feb52-167">序列化为格式化的 JSON</span><span class="sxs-lookup"><span data-stu-id="feb52-167">Serialize to formatted JSON</span></span>

<span data-ttu-id="feb52-168">若要整齐地打印 JSON 输出，请将 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> 设置为 `true`：</span><span class="sxs-lookup"><span data-stu-id="feb52-168">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="feb52-169">下面是一个要进行序列化的示例类型，并显示为漂亮的 JSON 输出：</span><span class="sxs-lookup"><span data-stu-id="feb52-169">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="feb52-170">自定义 JSON 名称和值</span><span class="sxs-lookup"><span data-stu-id="feb52-170">Customize JSON names and values</span></span>

<span data-ttu-id="feb52-171">默认情况下，JSON 输出中的属性名称和字典键不变，包括大小写。</span><span class="sxs-lookup"><span data-stu-id="feb52-171">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="feb52-172">枚举值表示为数值。</span><span class="sxs-lookup"><span data-stu-id="feb52-172">Enum values are represented as numbers.</span></span> <span data-ttu-id="feb52-173">本部分介绍如何：</span><span class="sxs-lookup"><span data-stu-id="feb52-173">This section explains how to:</span></span>

* [<span data-ttu-id="feb52-174">自定义各个属性名称</span><span class="sxs-lookup"><span data-stu-id="feb52-174">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="feb52-175">将所有属性名称转换为 camel 大小写</span><span class="sxs-lookup"><span data-stu-id="feb52-175">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="feb52-176">实现自定义属性命名策略</span><span class="sxs-lookup"><span data-stu-id="feb52-176">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="feb52-177">将字典键转换为 camel 大小写</span><span class="sxs-lookup"><span data-stu-id="feb52-177">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="feb52-178">将枚举转换为字符串和 camel 大小写</span><span class="sxs-lookup"><span data-stu-id="feb52-178">Convert enums to strings and camel case</span></span>](#enums-as-strings) 

<span data-ttu-id="feb52-179">对于需要对 JSON 属性名称和值进行特殊处理的其他方案，可以[实现自定义转换器](system-text-json-converters-how-to.md)。</span><span class="sxs-lookup"><span data-stu-id="feb52-179">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="feb52-180">自定义各个属性名称</span><span class="sxs-lookup"><span data-stu-id="feb52-180">Customize individual property names</span></span>

<span data-ttu-id="feb52-181">若要设置单个属性的名称，请使用[[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute)属性。</span><span class="sxs-lookup"><span data-stu-id="feb52-181">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="feb52-182">下面是序列化和生成的 JSON 的示例类型：</span><span class="sxs-lookup"><span data-stu-id="feb52-182">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="feb52-183">此属性设置的属性名称：</span><span class="sxs-lookup"><span data-stu-id="feb52-183">The property name set by this attribute:</span></span>

* <span data-ttu-id="feb52-184">同时适用于序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="feb52-184">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="feb52-185">优先于属性命名策略。</span><span class="sxs-lookup"><span data-stu-id="feb52-185">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="feb52-186">对所有 JSON 属性名称使用 camel 大小写</span><span class="sxs-lookup"><span data-stu-id="feb52-186">Use camel case for all JSON property names</span></span>

<span data-ttu-id="feb52-187">若要对所有 JSON 属性名称使用 camel 大小写，请将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 设置为 `JsonNamingPolicy.CamelCase`，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="feb52-187">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="feb52-188">下面是一个用于序列化和 JSON 输出的示例类：</span><span class="sxs-lookup"><span data-stu-id="feb52-188">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="feb52-189">Camel 大小写属性命名策略：</span><span class="sxs-lookup"><span data-stu-id="feb52-189">The camel case property naming policy:</span></span>

* <span data-ttu-id="feb52-190">适用于序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="feb52-190">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="feb52-191">`[JsonPropertyName]` 特性重写。</span><span class="sxs-lookup"><span data-stu-id="feb52-191">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="feb52-192">这就是示例中的 JSON 属性名称 `Wind` 不是 camel 大小写的原因。</span><span class="sxs-lookup"><span data-stu-id="feb52-192">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="feb52-193">使用自定义 JSON 属性命名策略</span><span class="sxs-lookup"><span data-stu-id="feb52-193">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="feb52-194">若要使用自定义 JSON 属性命名策略，请创建一个派生自 <xref:System.Text.Json.JsonNamingPolicy> 的类，并重写 <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> 方法，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="feb52-194">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="feb52-195">然后，将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 属性设置为命名策略类的实例：</span><span class="sxs-lookup"><span data-stu-id="feb52-195">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="feb52-196">下面是一个用于序列化和 JSON 输出的示例类：</span><span class="sxs-lookup"><span data-stu-id="feb52-196">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="feb52-197">JSON 属性命名策略：</span><span class="sxs-lookup"><span data-stu-id="feb52-197">The JSON property naming policy:</span></span>

* <span data-ttu-id="feb52-198">适用于序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="feb52-198">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="feb52-199">`[JsonPropertyName]` 特性重写。</span><span class="sxs-lookup"><span data-stu-id="feb52-199">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="feb52-200">这就是示例中 `Wind` 的 JSON 属性名称不大写的原因。</span><span class="sxs-lookup"><span data-stu-id="feb52-200">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="feb52-201">Camel 大小写字典密钥</span><span class="sxs-lookup"><span data-stu-id="feb52-201">Camel case dictionary keys</span></span>

<span data-ttu-id="feb52-202">如果要序列化的对象的属性为 `Dictionary<string,TValue>`类型，则 `string` 键可转换为 camel 大小写形式。</span><span class="sxs-lookup"><span data-stu-id="feb52-202">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="feb52-203">为此，请将 <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> 设置为 `JsonNamingPolicy.CamelCase`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="feb52-203">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="feb52-204">使用名为 `TemperatureRanges` 的字典序列化具有键值对 `"ColdMinTemp", 20` 的对象，`"HotMinTemp", 40` 将导致 JSON 输出，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="feb52-204">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="feb52-205">字典键的 camel 大小写命名策略仅适用于序列化。</span><span class="sxs-lookup"><span data-stu-id="feb52-205">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="feb52-206">如果对字典进行反序列化，即使为 `DictionaryKeyPolicy`指定 `JsonNamingPolicy.CamelCase`，这些键也会与 JSON 文件匹配。</span><span class="sxs-lookup"><span data-stu-id="feb52-206">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="feb52-207">作为字符串的枚举</span><span class="sxs-lookup"><span data-stu-id="feb52-207">Enums as strings</span></span>

<span data-ttu-id="feb52-208">默认情况下，枚举作为数字序列化。</span><span class="sxs-lookup"><span data-stu-id="feb52-208">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="feb52-209">若要将枚举名称序列化为字符串，请使用 <xref:System.Text.Json.Serialization.JsonStringEnumConverter>。</span><span class="sxs-lookup"><span data-stu-id="feb52-209">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="feb52-210">例如，假设需要序列化以下具有枚举的类：</span><span class="sxs-lookup"><span data-stu-id="feb52-210">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="feb52-211">如果 `Hot`摘要，则默认情况下序列化的 JSON 的数值为3：</span><span class="sxs-lookup"><span data-stu-id="feb52-211">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="feb52-212">下面的示例代码序列化枚举名称，而不是数值，并将名称转换为 camel 大小写格式：</span><span class="sxs-lookup"><span data-stu-id="feb52-212">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="feb52-213">生成的 JSON 类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="feb52-213">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="feb52-214">还可以反序列化枚举字符串名称，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="feb52-214">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="feb52-215">从序列化中排除属性</span><span class="sxs-lookup"><span data-stu-id="feb52-215">Exclude properties from serialization</span></span>

<span data-ttu-id="feb52-216">默认情况下，将序列化所有公共属性。</span><span class="sxs-lookup"><span data-stu-id="feb52-216">By default, all public properties are serialized.</span></span> <span data-ttu-id="feb52-217">如果你不想让某些用户出现在 JSON 输出中，则可以使用几个选项。</span><span class="sxs-lookup"><span data-stu-id="feb52-217">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="feb52-218">本部分介绍如何排除：</span><span class="sxs-lookup"><span data-stu-id="feb52-218">This section explains how to exclude:</span></span>

* [<span data-ttu-id="feb52-219">单个属性</span><span class="sxs-lookup"><span data-stu-id="feb52-219">Individual properties</span></span>](#exclude-individual-properties)
* [<span data-ttu-id="feb52-220">所有只读属性</span><span class="sxs-lookup"><span data-stu-id="feb52-220">All read-only properties</span></span>](#exclude-all-read-only-properties)
* [<span data-ttu-id="feb52-221">所有 null 值属性</span><span class="sxs-lookup"><span data-stu-id="feb52-221">All null-value properties</span></span>](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a><span data-ttu-id="feb52-222">排除单个属性</span><span class="sxs-lookup"><span data-stu-id="feb52-222">Exclude individual properties</span></span>

<span data-ttu-id="feb52-223">若要忽略各个属性，请使用[[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute)属性。</span><span class="sxs-lookup"><span data-stu-id="feb52-223">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="feb52-224">下面是要序列化的示例类型和 JSON 输出：</span><span class="sxs-lookup"><span data-stu-id="feb52-224">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="feb52-225">排除所有只读属性</span><span class="sxs-lookup"><span data-stu-id="feb52-225">Exclude all read-only properties</span></span>

<span data-ttu-id="feb52-226">如果属性包含公共 getter 而不是公共 setter，则该属性为只读。</span><span class="sxs-lookup"><span data-stu-id="feb52-226">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="feb52-227">若要排除所有只读属性，请将 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> 设置为 `true`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="feb52-227">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="feb52-228">下面是要序列化的示例类型和 JSON 输出：</span><span class="sxs-lookup"><span data-stu-id="feb52-228">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="feb52-229">此选项仅适用于序列化。</span><span class="sxs-lookup"><span data-stu-id="feb52-229">This option applies only to serialization.</span></span> <span data-ttu-id="feb52-230">在反序列化期间，默认情况下将忽略只读属性。</span><span class="sxs-lookup"><span data-stu-id="feb52-230">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="feb52-231">排除所有 null 值属性</span><span class="sxs-lookup"><span data-stu-id="feb52-231">Exclude all null value properties</span></span>

<span data-ttu-id="feb52-232">若要排除所有 null 值属性，请将 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> 属性设置为 `true`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="feb52-232">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="feb52-233">下面是一个示例对象，用于序列化和 JSON 输出：</span><span class="sxs-lookup"><span data-stu-id="feb52-233">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="feb52-234">Property</span><span class="sxs-lookup"><span data-stu-id="feb52-234">Property</span></span> |<span data-ttu-id="feb52-235">{2&gt;值&lt;2}</span><span class="sxs-lookup"><span data-stu-id="feb52-235">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="feb52-236">日期</span><span class="sxs-lookup"><span data-stu-id="feb52-236">Date</span></span>    | <span data-ttu-id="feb52-237">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="feb52-237">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="feb52-238">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="feb52-238">TemperatureCelsius</span></span>| <span data-ttu-id="feb52-239">25</span><span class="sxs-lookup"><span data-stu-id="feb52-239">25</span></span> |
| <span data-ttu-id="feb52-240">摘要</span><span class="sxs-lookup"><span data-stu-id="feb52-240">Summary</span></span>| <span data-ttu-id="feb52-241">null</span><span class="sxs-lookup"><span data-stu-id="feb52-241">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="feb52-242">此设置适用于序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="feb52-242">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="feb52-243">有关对反序列化的影响的信息，请参阅[反序列化时忽略 null](#ignore-null-when-deserializing)。</span><span class="sxs-lookup"><span data-stu-id="feb52-243">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="feb52-244">自定义字符编码</span><span class="sxs-lookup"><span data-stu-id="feb52-244">Customize character encoding</span></span>

<span data-ttu-id="feb52-245">默认情况下，序列化程序对所有非 ASCII 字符进行转义。</span><span class="sxs-lookup"><span data-stu-id="feb52-245">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="feb52-246">也就是说，它将替换为 `\uxxxx`，其中 `xxxx` 为字符的 Unicode 代码。</span><span class="sxs-lookup"><span data-stu-id="feb52-246">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="feb52-247">例如，如果将 `Summary` 属性设置为西里尔жарко，则 `WeatherForecast` 对象将被序列化，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="feb52-247">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="feb52-248">序列化语言字符集</span><span class="sxs-lookup"><span data-stu-id="feb52-248">Serialize language character sets</span></span>

<span data-ttu-id="feb52-249">若要序列化一种或多种语言的字符集而不进行转义，请在创建 <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>的实例时指定[Unicode 范围](xref:System.Text.Unicode.UnicodeRanges)，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="feb52-249">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="feb52-250">此代码不会对西里尔字符或希腊语字符进行转义。</span><span class="sxs-lookup"><span data-stu-id="feb52-250">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="feb52-251">如果 `Summary` 属性设置为西里尔жарко，则 `WeatherForecast` 对象将被序列化，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="feb52-251">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="feb52-252">若要序列化所有语言集而不进行转义，请使用 <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="feb52-252">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="feb52-253">序列化特定字符</span><span class="sxs-lookup"><span data-stu-id="feb52-253">Serialize specific characters</span></span>

<span data-ttu-id="feb52-254">一种替代方法是指定要允许的单个字符，而不进行转义。</span><span class="sxs-lookup"><span data-stu-id="feb52-254">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="feb52-255">下面的示例仅序列化жарко的前两个字符：</span><span class="sxs-lookup"><span data-stu-id="feb52-255">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="feb52-256">下面是前面的代码生成的 JSON 示例：</span><span class="sxs-lookup"><span data-stu-id="feb52-256">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="feb52-257">序列化所有字符</span><span class="sxs-lookup"><span data-stu-id="feb52-257">Serialize all characters</span></span>

<span data-ttu-id="feb52-258">若要最大程度地减少转义，可以使用 <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="feb52-258">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="feb52-259">与默认编码器相比，`UnsafeRelaxedJsonEscaping` 编码器可以更好地允许字符通过非转义：</span><span class="sxs-lookup"><span data-stu-id="feb52-259">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="feb52-260">它不会转义 HTML 敏感字符，如 `<`、`>`、`&`和 `'`。</span><span class="sxs-lookup"><span data-stu-id="feb52-260">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="feb52-261">它不提供任何针对 XSS 或信息泄露攻击的额外防御防护，如客户端和服务器 disagreeing 在*字符集*上可能导致的任何其他防护。</span><span class="sxs-lookup"><span data-stu-id="feb52-261">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="feb52-262">仅当知道客户端将以 UTF-8 编码的 JSON 解释结果负载时，才使用 unsafe 编码器。</span><span class="sxs-lookup"><span data-stu-id="feb52-262">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="feb52-263">例如，如果服务器正在发送响应标头，则可以使用它 `Content-Type: application/json; charset=utf-8`。</span><span class="sxs-lookup"><span data-stu-id="feb52-263">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="feb52-264">永远不允许将原始 `UnsafeRelaxedJsonEscaping` 输出发送到 HTML 页或 `<script>` 元素。</span><span class="sxs-lookup"><span data-stu-id="feb52-264">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="feb52-265">序列化派生类的属性</span><span class="sxs-lookup"><span data-stu-id="feb52-265">Serialize properties of derived classes</span></span>

<span data-ttu-id="feb52-266">不支持多态类型层次结构的序列化。</span><span class="sxs-lookup"><span data-stu-id="feb52-266">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="feb52-267">例如，如果将某个属性定义为接口或抽象类，则即使运行时类型具有其他属性，也只会序列化对接口或抽象类定义的属性。</span><span class="sxs-lookup"><span data-stu-id="feb52-267">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="feb52-268">此部分中介绍了此行为的例外情况。</span><span class="sxs-lookup"><span data-stu-id="feb52-268">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="feb52-269">例如，假设您有一个 `WeatherForecast` 类和一个派生类 `WeatherForecastDerived`：</span><span class="sxs-lookup"><span data-stu-id="feb52-269">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="feb52-270">并且假设在编译时 `Serialize` 方法的类型实参 `WeatherForecast`：</span><span class="sxs-lookup"><span data-stu-id="feb52-270">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="feb52-271">在这种情况下，即使 `weatherForecast` 对象实际上是 `WeatherForecastDerived` 对象，也不会对 `WindSpeed` 属性进行序列化。</span><span class="sxs-lookup"><span data-stu-id="feb52-271">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="feb52-272">仅序列化基类属性：</span><span class="sxs-lookup"><span data-stu-id="feb52-272">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="feb52-273">此行为旨在帮助防止在派生的运行时创建的类型中发生意外的数据泄露。</span><span class="sxs-lookup"><span data-stu-id="feb52-273">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="feb52-274">若要在前面的示例中序列化派生类型的属性，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="feb52-274">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="feb52-275">调用 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 的重载，以便在运行时指定类型：</span><span class="sxs-lookup"><span data-stu-id="feb52-275">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="feb52-276">将要序列化的对象声明为 `object`。</span><span class="sxs-lookup"><span data-stu-id="feb52-276">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="feb52-277">在前面的示例方案中，这两种方法都会使 `WindSpeed` 属性包括在 JSON 输出中：</span><span class="sxs-lookup"><span data-stu-id="feb52-277">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="feb52-278">这些方法只为要序列化的根对象提供多态序列化，而不提供该根对象的属性的多态序列化。</span><span class="sxs-lookup"><span data-stu-id="feb52-278">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span> 

<span data-ttu-id="feb52-279">如果将较低级别的对象定义为 `object`类型，则可以获取多态序列化。</span><span class="sxs-lookup"><span data-stu-id="feb52-279">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="feb52-280">例如，假设 `WeatherForecast` 类具有一个名为 `PreviousForecast` 的属性，该属性可以定义为类型 `WeatherForecast` 或 `object`：</span><span class="sxs-lookup"><span data-stu-id="feb52-280">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="feb52-281">如果 `PreviousForecast` 属性包含 `WeatherForecastDerived`的实例：</span><span class="sxs-lookup"><span data-stu-id="feb52-281">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="feb52-282">序列化 `WeatherForecastWithPrevious` 的 JSON 输出**不包括**`WindSpeed`。</span><span class="sxs-lookup"><span data-stu-id="feb52-282">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="feb52-283">序列化 `WeatherForecastWithPreviousAsObject` 的 JSON 输出**包括**`WindSpeed`。</span><span class="sxs-lookup"><span data-stu-id="feb52-283">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="feb52-284">若要序列化 `WeatherForecastWithPreviousAsObject`，无需调用 `Serialize<object>` 或 `GetType`，因为根对象不是可能是派生类型的对象。</span><span class="sxs-lookup"><span data-stu-id="feb52-284">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="feb52-285">下面的代码示例不调用 `Serialize<object>` 或 `GetType`：</span><span class="sxs-lookup"><span data-stu-id="feb52-285">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="feb52-286">前面的代码正确地序列化 `WeatherForecastWithPreviousAsObject`：</span><span class="sxs-lookup"><span data-stu-id="feb52-286">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

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

<span data-ttu-id="feb52-287">将属性定义为 `object` 与接口一起使用的方法相同。</span><span class="sxs-lookup"><span data-stu-id="feb52-287">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="feb52-288">假设您具有以下接口和实现，并且您想要使用包含实现实例的属性序列化类：</span><span class="sxs-lookup"><span data-stu-id="feb52-288">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/IForecast.cs)]

<span data-ttu-id="feb52-289">序列化 `Forecasts`的实例时，只有 `Tuesday` 显示 `WindSpeed` 属性，因为 `Tuesday` 定义为 `object`：</span><span class="sxs-lookup"><span data-stu-id="feb52-289">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="feb52-290">下面的示例显示了前面的代码生成的 JSON：</span><span class="sxs-lookup"><span data-stu-id="feb52-290">The following example shows the JSON that results from the preceding code:</span></span>

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

<span data-ttu-id="feb52-291">有关多态**序列化**的详细信息，以及有关**反序列**化的信息，请参阅[如何从 newtonsoft.json 迁移到 system.object](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization)。</span><span class="sxs-lookup"><span data-stu-id="feb52-291">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="feb52-292">允许注释和尾随逗号</span><span class="sxs-lookup"><span data-stu-id="feb52-292">Allow comments and trailing commas</span></span>

<span data-ttu-id="feb52-293">默认情况下，JSON 中不允许使用注释和尾随逗号。</span><span class="sxs-lookup"><span data-stu-id="feb52-293">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="feb52-294">若要允许 JSON 中的注释，请将 <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> 属性设置为 `JsonCommentHandling.Skip`。</span><span class="sxs-lookup"><span data-stu-id="feb52-294">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="feb52-295">若要允许尾随逗号，请将 <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="feb52-295">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="feb52-296">下面的示例演示如何允许两种方法：</span><span class="sxs-lookup"><span data-stu-id="feb52-296">The following example shows how to allow both:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="feb52-297">下面是包含注释和尾随逗号的示例 JSON：</span><span class="sxs-lookup"><span data-stu-id="feb52-297">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="feb52-298">不区分大小写的属性匹配</span><span class="sxs-lookup"><span data-stu-id="feb52-298">Case-insensitive property matching</span></span>

<span data-ttu-id="feb52-299">默认情况下，反序列化将查找 JSON 与目标对象属性之间区分大小写的属性名称匹配。</span><span class="sxs-lookup"><span data-stu-id="feb52-299">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="feb52-300">若要更改此行为，请将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> 设置为 `true`：</span><span class="sxs-lookup"><span data-stu-id="feb52-300">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="feb52-301">下面是采用 camel 大小写属性名称的示例 JSON。</span><span class="sxs-lookup"><span data-stu-id="feb52-301">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="feb52-302">它可以反序列化为具有 Pascal 大小写属性名称的以下类型。</span><span class="sxs-lookup"><span data-stu-id="feb52-302">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="feb52-303">句柄溢出 JSON</span><span class="sxs-lookup"><span data-stu-id="feb52-303">Handle overflow JSON</span></span>

<span data-ttu-id="feb52-304">反序列化时，可能会收到 JSON 中的数据，该数据不是由目标类型的属性表示的。</span><span class="sxs-lookup"><span data-stu-id="feb52-304">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="feb52-305">例如，假设目标类型为：</span><span class="sxs-lookup"><span data-stu-id="feb52-305">For example, suppose your target type is this:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="feb52-306">要反序列化的 JSON 如下：</span><span class="sxs-lookup"><span data-stu-id="feb52-306">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="feb52-307">如果将显示的 JSON 反序列化为显示的类型，则 "`DatesAvailable`" 和 "`SummaryWords`" 属性不会有任何位置，并且将丢失。</span><span class="sxs-lookup"><span data-stu-id="feb52-307">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="feb52-308">若要捕获额外数据（如这些属性），请将[JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute)特性应用到类型 `Dictionary<string,object>` 或 `Dictionary<string,JsonElement>`的属性：</span><span class="sxs-lookup"><span data-stu-id="feb52-308">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="feb52-309">反序列化前面显示的此示例类型的 JSON 时，额外的数据将成为 `ExtensionData` 属性的键值对：</span><span class="sxs-lookup"><span data-stu-id="feb52-309">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="feb52-310">Property</span><span class="sxs-lookup"><span data-stu-id="feb52-310">Property</span></span> |<span data-ttu-id="feb52-311">{2&gt;值&lt;2}</span><span class="sxs-lookup"><span data-stu-id="feb52-311">Value</span></span>  |<span data-ttu-id="feb52-312">注释</span><span class="sxs-lookup"><span data-stu-id="feb52-312">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="feb52-313">日期</span><span class="sxs-lookup"><span data-stu-id="feb52-313">Date</span></span>    | <span data-ttu-id="feb52-314">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="feb52-314">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="feb52-315">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="feb52-315">TemperatureCelsius</span></span>| <span data-ttu-id="feb52-316">0</span><span class="sxs-lookup"><span data-stu-id="feb52-316">0</span></span> | <span data-ttu-id="feb52-317">区分大小写不匹配（`temperatureCelsius` 在 JSON 中），因此未设置属性。</span><span class="sxs-lookup"><span data-stu-id="feb52-317">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="feb52-318">摘要</span><span class="sxs-lookup"><span data-stu-id="feb52-318">Summary</span></span> | <span data-ttu-id="feb52-319">热</span><span class="sxs-lookup"><span data-stu-id="feb52-319">Hot</span></span> ||
| <span data-ttu-id="feb52-320">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="feb52-320">ExtensionData</span></span> | <span data-ttu-id="feb52-321">temperatureCelsius：25</span><span class="sxs-lookup"><span data-stu-id="feb52-321">temperatureCelsius: 25</span></span> |<span data-ttu-id="feb52-322">由于大小写不匹配，因此此 JSON 属性是一个额外的，并成为字典中的键值对。</span><span class="sxs-lookup"><span data-stu-id="feb52-322">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="feb52-323">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="feb52-323">DatesAvailable:</span></span><br>  <span data-ttu-id="feb52-324">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="feb52-324">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="feb52-325">8/2/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="feb52-325">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="feb52-326">JSON 中的额外属性将成为键值对，并将数组作为值对象。</span><span class="sxs-lookup"><span data-stu-id="feb52-326">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="feb52-327">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="feb52-327">SummaryWords:</span></span><br><span data-ttu-id="feb52-328">酷</span><span class="sxs-lookup"><span data-stu-id="feb52-328">Cool</span></span><br><span data-ttu-id="feb52-329">风</span><span class="sxs-lookup"><span data-stu-id="feb52-329">Windy</span></span><br><span data-ttu-id="feb52-330">Humid</span><span class="sxs-lookup"><span data-stu-id="feb52-330">Humid</span></span> |<span data-ttu-id="feb52-331">JSON 中的额外属性将成为键值对，并将数组作为值对象。</span><span class="sxs-lookup"><span data-stu-id="feb52-331">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="feb52-332">序列化目标对象时，扩展数据键值对将成为 JSON 属性，就像它们位于传入 JSON 中一样：</span><span class="sxs-lookup"><span data-stu-id="feb52-332">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="feb52-333">请注意，`ExtensionData` 属性名称不会出现在 JSON 中。</span><span class="sxs-lookup"><span data-stu-id="feb52-333">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="feb52-334">此行为允许 JSON 进行往返，而不会丢失任何不会被反序列化的额外数据。</span><span class="sxs-lookup"><span data-stu-id="feb52-334">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="feb52-335">反序列化时忽略 null</span><span class="sxs-lookup"><span data-stu-id="feb52-335">Ignore null when deserializing</span></span>

<span data-ttu-id="feb52-336">默认情况下，如果 JSON 中的属性为 null，则目标对象中的相应属性将设置为 null。</span><span class="sxs-lookup"><span data-stu-id="feb52-336">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="feb52-337">在某些情况下，target 属性可能具有默认值，并且你不希望 null 值覆盖默认值。</span><span class="sxs-lookup"><span data-stu-id="feb52-337">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="feb52-338">例如，假设以下代码表示目标对象：</span><span class="sxs-lookup"><span data-stu-id="feb52-338">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="feb52-339">假设反序列化以下 JSON：</span><span class="sxs-lookup"><span data-stu-id="feb52-339">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="feb52-340">反序列化后，`WeatherForecastWithDefault` 对象的 `Summary` 属性为 null。</span><span class="sxs-lookup"><span data-stu-id="feb52-340">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="feb52-341">若要更改此行为，请将 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> 设置为 `true`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="feb52-341">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="feb52-342">利用此选项，在反序列化后，`WeatherForecastWithDefault` 对象的 `Summary` 属性是默认值 "无摘要"。</span><span class="sxs-lookup"><span data-stu-id="feb52-342">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="feb52-343">JSON 中的 Null 值仅在有效时才会被忽略。</span><span class="sxs-lookup"><span data-stu-id="feb52-343">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="feb52-344">不可以为 null 的值类型的 Null 值将导致异常。</span><span class="sxs-lookup"><span data-stu-id="feb52-344">Null values for non-nullable value types cause exceptions.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="feb52-345">Utf8JsonReader、Utf8JsonWriter 和 JsonDocument</span><span class="sxs-lookup"><span data-stu-id="feb52-345">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="feb52-346"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> 是适用于 UTF-8 编码的 JSON 文本的高性能、低分配、只进读取器、从 `ReadOnlySpan<byte>` 或 `ReadOnlySequence<byte>`读取。</span><span class="sxs-lookup"><span data-stu-id="feb52-346"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="feb52-347">`Utf8JsonReader` 是可用于生成自定义分析程序和反的低级别类型。</span><span class="sxs-lookup"><span data-stu-id="feb52-347">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="feb52-348"><xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 方法使用 `Utf8JsonReader` 的内容。</span><span class="sxs-lookup"><span data-stu-id="feb52-348">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="feb52-349"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> 是一种高性能的方式，用于从常见的 .NET 类型（如 `String`、`Int32`和 `DateTime`）编写 UTF-8 编码的 JSON 文本。</span><span class="sxs-lookup"><span data-stu-id="feb52-349"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="feb52-350">编写器是可用于生成自定义序列化程序的低级别类型。</span><span class="sxs-lookup"><span data-stu-id="feb52-350">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="feb52-351"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 方法使用 `Utf8JsonWriter` 的内容。</span><span class="sxs-lookup"><span data-stu-id="feb52-351">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="feb52-352"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> 提供使用 `Utf8JsonReader`生成只读文档对象模型（DOM）的功能。</span><span class="sxs-lookup"><span data-stu-id="feb52-352"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="feb52-353">DOM 提供对 JSON 有效负载中的数据的随机访问。</span><span class="sxs-lookup"><span data-stu-id="feb52-353">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="feb52-354">可以通过 <xref:System.Text.Json.JsonElement> 类型访问构成有效负载的 JSON 元素。</span><span class="sxs-lookup"><span data-stu-id="feb52-354">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="feb52-355">`JsonElement` 类型提供数组和对象枚举器，以及用于将 JSON 文本转换为常见 .NET 类型的 Api。</span><span class="sxs-lookup"><span data-stu-id="feb52-355">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="feb52-356">`JsonDocument` 公开 <xref:System.Text.Json.JsonDocument.RootElement> 属性。</span><span class="sxs-lookup"><span data-stu-id="feb52-356">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="feb52-357">以下部分说明了如何使用这些工具来读取和写入 JSON。</span><span class="sxs-lookup"><span data-stu-id="feb52-357">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="feb52-358">使用 JsonDocument 访问数据</span><span class="sxs-lookup"><span data-stu-id="feb52-358">Use JsonDocument for access to data</span></span>

<span data-ttu-id="feb52-359">下面的示例演示如何使用 <xref:System.Text.Json.JsonDocument> 类来随机访问 JSON 字符串中的数据：</span><span class="sxs-lookup"><span data-stu-id="feb52-359">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="feb52-360">前面的代码：</span><span class="sxs-lookup"><span data-stu-id="feb52-360">The preceding code:</span></span>

* <span data-ttu-id="feb52-361">假定 JSON 要分析的字符串中有一个名为 `jsonString`。</span><span class="sxs-lookup"><span data-stu-id="feb52-361">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="feb52-362">计算 `Students` 数组中具有 `Grade` 属性的对象的平均评分。</span><span class="sxs-lookup"><span data-stu-id="feb52-362">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span> 
* <span data-ttu-id="feb52-363">为没有成绩的学生分配默认等级70。</span><span class="sxs-lookup"><span data-stu-id="feb52-363">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="feb52-364">通过每次迭代增加 `count` 变量来对学生进行计数。</span><span class="sxs-lookup"><span data-stu-id="feb52-364">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="feb52-365">一种替代方法是调用 <xref:System.Text.Json.JsonElement.GetArrayLength%2A>，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="feb52-365">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="feb52-366">下面是此代码处理的 JSON 示例：</span><span class="sxs-lookup"><span data-stu-id="feb52-366">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="feb52-367">使用 JsonDocument 编写 JSON</span><span class="sxs-lookup"><span data-stu-id="feb52-367">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="feb52-368">下面的示例演示如何从 <xref:System.Text.Json.JsonDocument>编写 JSON：</span><span class="sxs-lookup"><span data-stu-id="feb52-368">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="feb52-369">前面的代码：</span><span class="sxs-lookup"><span data-stu-id="feb52-369">The preceding code:</span></span>

* <span data-ttu-id="feb52-370">读取 JSON 文件，将数据加载到 `JsonDocument`，并将格式化（整齐打印的） JSON 写入文件。</span><span class="sxs-lookup"><span data-stu-id="feb52-370">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="feb52-371">使用 <xref:System.Text.Json.JsonDocumentOptions> 指定允许但忽略输入 JSON 中的注释。</span><span class="sxs-lookup"><span data-stu-id="feb52-371">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="feb52-372">完成后，将对编写器调用 <xref:System.Text.Json.Utf8JsonWriter.Flush%2A>。</span><span class="sxs-lookup"><span data-stu-id="feb52-372">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="feb52-373">一种替代方法是让编写人员在 autoflush 时进行处理。</span><span class="sxs-lookup"><span data-stu-id="feb52-373">An alternative is to let the writer autoflush when it's disposed.</span></span> 

<span data-ttu-id="feb52-374">下面是示例代码处理的 JSON 输入的示例：</span><span class="sxs-lookup"><span data-stu-id="feb52-374">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

<span data-ttu-id="feb52-375">结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="feb52-375">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="feb52-376">使用 Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="feb52-376">Use Utf8JsonWriter</span></span>

<span data-ttu-id="feb52-377">下面的示例演示如何使用 <xref:System.Text.Json.Utf8JsonWriter> 类：</span><span class="sxs-lookup"><span data-stu-id="feb52-377">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="feb52-378">使用 Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="feb52-378">Use Utf8JsonReader</span></span>

<span data-ttu-id="feb52-379">下面的示例演示如何使用 <xref:System.Text.Json.Utf8JsonReader> 类：</span><span class="sxs-lookup"><span data-stu-id="feb52-379">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="feb52-380">前面的代码假定 `jsonUtf8` 变量是包含有效 JSON 的字节数组，编码为 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="feb52-380">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="feb52-381">使用 Utf8JsonReader 筛选数据</span><span class="sxs-lookup"><span data-stu-id="feb52-381">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="feb52-382">下面的示例演示如何同步读取文件并搜索值：</span><span class="sxs-lookup"><span data-stu-id="feb52-382">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="feb52-383">前面的代码：</span><span class="sxs-lookup"><span data-stu-id="feb52-383">The preceding code:</span></span>

* <span data-ttu-id="feb52-384">假定 JSON 包含一个对象数组，并且每个对象可能包含一个字符串类型的 "name" 属性。</span><span class="sxs-lookup"><span data-stu-id="feb52-384">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="feb52-385">计算以 "大学" 结尾的对象和 "name" 属性值。</span><span class="sxs-lookup"><span data-stu-id="feb52-385">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="feb52-386">假定文件编码为 UTF-16，并将其转码为 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="feb52-386">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="feb52-387">可以通过使用以下代码，将编码为 UTF-8 的文件直接读入 `ReadOnlySpan<byte>`：</span><span class="sxs-lookup"><span data-stu-id="feb52-387">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

  <span data-ttu-id="feb52-388">如果文件包含 UTF-8 字节顺序标记（BOM），请在将字节传递到 `Utf8JsonReader`之前将其删除，因为读取器需要文本。</span><span class="sxs-lookup"><span data-stu-id="feb52-388">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="feb52-389">否则，BOM 被视为无效的 JSON，读取器将引发异常。</span><span class="sxs-lookup"><span data-stu-id="feb52-389">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="feb52-390">下面是前面的代码可以读取的 JSON 示例。</span><span class="sxs-lookup"><span data-stu-id="feb52-390">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="feb52-391">生成的摘要消息为 "2 个，共4个名称以 ' 大学 ' 结尾"：</span><span class="sxs-lookup"><span data-stu-id="feb52-391">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a><span data-ttu-id="feb52-392">其他资源</span><span class="sxs-lookup"><span data-stu-id="feb52-392">Additional resources</span></span>

* [<span data-ttu-id="feb52-393">System.web 概述</span><span class="sxs-lookup"><span data-stu-id="feb52-393">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="feb52-394">如何编写自定义转换器</span><span class="sxs-lookup"><span data-stu-id="feb52-394">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="feb52-395">如何从 Newtonsoft.json 迁移</span><span class="sxs-lookup"><span data-stu-id="feb52-395">How to migrate from Newtonsoft.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="feb52-396">系统中的 DateTime 和 DateTimeOffset 支持</span><span class="sxs-lookup"><span data-stu-id="feb52-396">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* [<span data-ttu-id="feb52-397">System.web API 参考</span><span class="sxs-lookup"><span data-stu-id="feb52-397">System.Text.Json API reference</span></span>](xref:System.Text.Json)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
