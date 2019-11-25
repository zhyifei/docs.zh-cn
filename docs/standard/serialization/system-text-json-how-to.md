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
ms.openlocfilehash: 3d3dc0011562e25854938aff857f2832a5978b49
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283332"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a><span data-ttu-id="62433-102">如何在 .NET 中对 JSON 进行序列化和反序列化</span><span class="sxs-lookup"><span data-stu-id="62433-102">How to serialize and deserialize JSON in .NET</span></span>

<span data-ttu-id="62433-103">本文介绍如何使用 <xref:System.Text.Json> 命名空间在 JavaScript 对象表示法（JSON）之间进行序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="62433-103">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="62433-104">方向和示例代码直接使用库，而不是通过框架（如[ASP.NET Core](/aspnet/core/)）使用。</span><span class="sxs-lookup"><span data-stu-id="62433-104">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="62433-105">大多数序列化示例代码将 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> 设置为 `true` JSON （对于人工可读性，为缩进和空格）。</span><span class="sxs-lookup"><span data-stu-id="62433-105">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="62433-106">对于生产用途，通常会接受此设置的默认 `false` 值。</span><span class="sxs-lookup"><span data-stu-id="62433-106">For production use, you would typically accept the default value of `false` for this setting.</span></span>

## <a name="namespaces"></a><span data-ttu-id="62433-107">命名空间</span><span class="sxs-lookup"><span data-stu-id="62433-107">Namespaces</span></span>

<span data-ttu-id="62433-108"><xref:System.Text.Json> 命名空间包含所有入口点和主要类型。</span><span class="sxs-lookup"><span data-stu-id="62433-108">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="62433-109"><xref:System.Text.Json.Serialization> 命名空间包含用于高级方案的属性和 Api，以及特定于序列化和反序列化的自定义。</span><span class="sxs-lookup"><span data-stu-id="62433-109">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="62433-110">本文中所示的代码示例要求其中一个或两个命名空间都有 `using` 指令：</span><span class="sxs-lookup"><span data-stu-id="62433-110">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="62433-111">`System.Text.Json`当前不支持 <xref:System.Runtime.Serialization> 命名空间中的属性。</span><span class="sxs-lookup"><span data-stu-id="62433-111">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="62433-112">如何将 .NET 对象写入 JSON （序列化）</span><span class="sxs-lookup"><span data-stu-id="62433-112">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="62433-113">若要将 JSON 写入字符串或文件，请调用 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="62433-113">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="62433-114">下面的示例将 JSON 创建为字符串：</span><span class="sxs-lookup"><span data-stu-id="62433-114">The following example creates JSON as a string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="62433-115">下面的示例使用同步代码创建 JSON 文件：</span><span class="sxs-lookup"><span data-stu-id="62433-115">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="62433-116">下面的示例使用异步代码创建 JSON 文件：</span><span class="sxs-lookup"><span data-stu-id="62433-116">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="62433-117">前面的示例对要序列化的类型使用类型推理。</span><span class="sxs-lookup"><span data-stu-id="62433-117">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="62433-118">`Serialize()` 的重载采用泛型类型参数：</span><span class="sxs-lookup"><span data-stu-id="62433-118">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="62433-119">序列化示例</span><span class="sxs-lookup"><span data-stu-id="62433-119">Serialization example</span></span>

<span data-ttu-id="62433-120">下面是包含集合和嵌套类的示例类：</span><span class="sxs-lookup"><span data-stu-id="62433-120">Here's an example class that contains collections and a nested class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

<span data-ttu-id="62433-121">序列化上述类型的实例的 JSON 输出类似于下面的示例。</span><span class="sxs-lookup"><span data-stu-id="62433-121">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="62433-122">默认情况下，JSON 输出为缩小：</span><span class="sxs-lookup"><span data-stu-id="62433-122">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="62433-123">下面的示例演示了相同的 JSON 格式（也就是用空格和缩进进行整齐打印）：</span><span class="sxs-lookup"><span data-stu-id="62433-123">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="62433-124">序列化为 UTF-8</span><span class="sxs-lookup"><span data-stu-id="62433-124">Serialize to UTF-8</span></span>

<span data-ttu-id="62433-125">若要序列化为 UTF-8，请调用 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 方法：</span><span class="sxs-lookup"><span data-stu-id="62433-125">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="62433-126">还提供了一个采用 <xref:System.Text.Json.Utf8JsonWriter> 的 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 重载。</span><span class="sxs-lookup"><span data-stu-id="62433-126">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="62433-127">序列化为 UTF-8 比使用基于字符串的方法更快5-10%。</span><span class="sxs-lookup"><span data-stu-id="62433-127">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="62433-128">不同之处在于，不需要将字节（如 UTF-8）转换为字符串（UTF-16）。</span><span class="sxs-lookup"><span data-stu-id="62433-128">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="62433-129">序列化行为</span><span class="sxs-lookup"><span data-stu-id="62433-129">Serialization behavior</span></span>

* <span data-ttu-id="62433-130">默认情况下，将序列化所有公共属性。</span><span class="sxs-lookup"><span data-stu-id="62433-130">By default, all public properties are serialized.</span></span> <span data-ttu-id="62433-131">您可以[指定要排除的属性](#exclude-properties-from-serialization)。</span><span class="sxs-lookup"><span data-stu-id="62433-131">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="62433-132">[默认编码器](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)会转义非 ascii 字符、ASCII 范围内的 HTML 敏感字符以及必须根据[RFC 8259 JSON 规范](https://tools.ietf.org/html/rfc8259#section-7)进行转义的字符。</span><span class="sxs-lookup"><span data-stu-id="62433-132">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="62433-133">默认情况下，JSON 为缩小。</span><span class="sxs-lookup"><span data-stu-id="62433-133">By default, JSON is minified.</span></span> <span data-ttu-id="62433-134">可以很好[打印 JSON](#serialize-to-formatted-json)。</span><span class="sxs-lookup"><span data-stu-id="62433-134">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="62433-135">默认情况下，JSON 名称的大小写与 .NET 名称匹配。</span><span class="sxs-lookup"><span data-stu-id="62433-135">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="62433-136">你可以[自定义 JSON 名称大小写](#customize-json-names-and-values)。</span><span class="sxs-lookup"><span data-stu-id="62433-136">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="62433-137">检测到循环引用并引发异常。</span><span class="sxs-lookup"><span data-stu-id="62433-137">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="62433-138">有关详细信息，请参阅 GitHub 上的 dotnet/corefx 存储库中的[循环引用问题 38579](https://github.com/dotnet/corefx/issues/38579) 。</span><span class="sxs-lookup"><span data-stu-id="62433-138">For more information, see [issue 38579 on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="62433-139">当前排除了字段。</span><span class="sxs-lookup"><span data-stu-id="62433-139">Currently, fields are excluded.</span></span>

<span data-ttu-id="62433-140">支持的类型包括：</span><span class="sxs-lookup"><span data-stu-id="62433-140">Supported types include:</span></span>

* <span data-ttu-id="62433-141">映射到 JavaScript 基元的 .NET 基元，如数值类型、字符串和布尔值。</span><span class="sxs-lookup"><span data-stu-id="62433-141">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="62433-142">用户定义的[普通旧 CLR 对象（poco）](https://stackoverflow.com/questions/250001/poco-definition)。</span><span class="sxs-lookup"><span data-stu-id="62433-142">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="62433-143">一维数组和交错数组（`ArrayName[][]`）。</span><span class="sxs-lookup"><span data-stu-id="62433-143">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="62433-144">`Dictionary<string,TValue>`，其中 `TValue` 为 `object`、`JsonElement`或 POCO。</span><span class="sxs-lookup"><span data-stu-id="62433-144">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="62433-145">以下命名空间中的集合。</span><span class="sxs-lookup"><span data-stu-id="62433-145">Collections from the following namespaces.</span></span> <span data-ttu-id="62433-146">有关详细信息，请参阅 GitHub 上的 dotnet/corefx 存储库中的[收集支持问题](https://github.com/dotnet/corefx/issues/36643)。</span><span class="sxs-lookup"><span data-stu-id="62433-146">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="62433-147">您可以[实现自定义转换器](system-text-json-converters-how-to.md)来处理其他类型或提供内置转换器不支持的功能。</span><span class="sxs-lookup"><span data-stu-id="62433-147">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="62433-148">如何将 JSON 读入 .NET 对象（反序列化）</span><span class="sxs-lookup"><span data-stu-id="62433-148">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="62433-149">若要从字符串或文件进行反序列化，请调用 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="62433-149">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="62433-150">下面的示例从字符串读取 JSON，并为[序列化示例](#serialization-example)创建前面所示 `WeatherForecast` 类的实例：</span><span class="sxs-lookup"><span data-stu-id="62433-150">The following example reads JSON from a string and creates an instance of the `WeatherForecast` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="62433-151">若要通过使用同步代码从文件进行反序列化，请将文件读入字符串中，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="62433-151">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="62433-152">若要使用异步代码从文件进行反序列化，请调用 <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> 方法：</span><span class="sxs-lookup"><span data-stu-id="62433-152">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="62433-153">从 UTF-8 反序列化</span><span class="sxs-lookup"><span data-stu-id="62433-153">Deserialize from UTF-8</span></span>

<span data-ttu-id="62433-154">若要从 UTF-8 进行反序列化，请调用采用 `Utf8JsonReader` 或 `ReadOnlySpan<byte>`的 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 重载，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="62433-154">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="62433-155">这些示例假定 JSON 位于名为 jsonUtf8Bytes 的字节数组中。</span><span class="sxs-lookup"><span data-stu-id="62433-155">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="62433-156">反序列化行为</span><span class="sxs-lookup"><span data-stu-id="62433-156">Deserialization behavior</span></span>

* <span data-ttu-id="62433-157">默认情况下，属性名称匹配区分大小写。</span><span class="sxs-lookup"><span data-stu-id="62433-157">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="62433-158">可以[指定不区分大小写](#case-insensitive-property-matching)。</span><span class="sxs-lookup"><span data-stu-id="62433-158">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="62433-159">如果 JSON 包含只读属性的值，则该值将被忽略，并且不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="62433-159">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="62433-160">不支持反序列化到不具有无参数构造函数的引用类型。</span><span class="sxs-lookup"><span data-stu-id="62433-160">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="62433-161">不支持对不可变对象或只读属性进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="62433-161">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="62433-162">有关详细信息，请参阅 github 上的 dotnet/corefx 存储库中对[不可变对象支持的 GitHub 问题 38569](https://github.com/dotnet/corefx/issues/38569)和[上的38163问题](https://github.com/dotnet/corefx/issues/38163)。</span><span class="sxs-lookup"><span data-stu-id="62433-162">For more information, see GitHub [issue 38569 on immutable object support](https://github.com/dotnet/corefx/issues/38569) and [issue 38163 on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="62433-163">默认情况下，枚举作为数字支持。</span><span class="sxs-lookup"><span data-stu-id="62433-163">By default, enums are supported as numbers.</span></span> <span data-ttu-id="62433-164">可以将[枚举名称序列化为字符串](#enums-as-strings)。</span><span class="sxs-lookup"><span data-stu-id="62433-164">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="62433-165">不支持字段。</span><span class="sxs-lookup"><span data-stu-id="62433-165">Fields aren't supported.</span></span>
* <span data-ttu-id="62433-166">默认情况下，JSON 中的注释或尾随逗号引发异常。</span><span class="sxs-lookup"><span data-stu-id="62433-166">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="62433-167">您可以[允许注释和尾随逗号](#allow-comments-and-trailing-commas)。</span><span class="sxs-lookup"><span data-stu-id="62433-167">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="62433-168">[默认的最大深度](xref:System.Text.Json.JsonReaderOptions.MaxDepth)为64。</span><span class="sxs-lookup"><span data-stu-id="62433-168">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="62433-169">您可以[实现自定义转换器](system-text-json-converters-how-to.md)以提供内置转换器不支持的功能。</span><span class="sxs-lookup"><span data-stu-id="62433-169">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="62433-170">序列化为格式化的 JSON</span><span class="sxs-lookup"><span data-stu-id="62433-170">Serialize to formatted JSON</span></span>

<span data-ttu-id="62433-171">若要整齐地打印 JSON 输出，请将 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> 设置为 `true`：</span><span class="sxs-lookup"><span data-stu-id="62433-171">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="62433-172">下面是一个要进行序列化的示例类型，并显示为漂亮的 JSON 输出：</span><span class="sxs-lookup"><span data-stu-id="62433-172">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="62433-173">自定义 JSON 名称和值</span><span class="sxs-lookup"><span data-stu-id="62433-173">Customize JSON names and values</span></span>

<span data-ttu-id="62433-174">默认情况下，JSON 输出中的属性名称和字典键不变，包括大小写。</span><span class="sxs-lookup"><span data-stu-id="62433-174">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="62433-175">枚举值表示为数值。</span><span class="sxs-lookup"><span data-stu-id="62433-175">Enum values are represented as numbers.</span></span> <span data-ttu-id="62433-176">本部分介绍如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="62433-176">This section explains how to:</span></span>

* [<span data-ttu-id="62433-177">自定义各个属性名称</span><span class="sxs-lookup"><span data-stu-id="62433-177">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="62433-178">将所有属性名称转换为 camel 大小写</span><span class="sxs-lookup"><span data-stu-id="62433-178">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="62433-179">实现自定义属性命名策略</span><span class="sxs-lookup"><span data-stu-id="62433-179">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="62433-180">将字典键转换为 camel 大小写</span><span class="sxs-lookup"><span data-stu-id="62433-180">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="62433-181">将枚举转换为字符串和 camel 大小写</span><span class="sxs-lookup"><span data-stu-id="62433-181">Convert enums to strings and camel case</span></span>](#enums-as-strings) 

<span data-ttu-id="62433-182">对于需要对 JSON 属性名称和值进行特殊处理的其他方案，可以[实现自定义转换器](system-text-json-converters-how-to.md)。</span><span class="sxs-lookup"><span data-stu-id="62433-182">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="62433-183">自定义各个属性名称</span><span class="sxs-lookup"><span data-stu-id="62433-183">Customize individual property names</span></span>

<span data-ttu-id="62433-184">若要设置单个属性的名称，请使用[[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute)属性。</span><span class="sxs-lookup"><span data-stu-id="62433-184">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="62433-185">下面是序列化和生成的 JSON 的示例类型：</span><span class="sxs-lookup"><span data-stu-id="62433-185">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="62433-186">此属性设置的属性名称：</span><span class="sxs-lookup"><span data-stu-id="62433-186">The property name set by this attribute:</span></span>

* <span data-ttu-id="62433-187">同时适用于序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="62433-187">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="62433-188">优先于属性命名策略。</span><span class="sxs-lookup"><span data-stu-id="62433-188">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="62433-189">对所有 JSON 属性名称使用 camel 大小写</span><span class="sxs-lookup"><span data-stu-id="62433-189">Use camel case for all JSON property names</span></span>

<span data-ttu-id="62433-190">若要对所有 JSON 属性名称使用 camel 大小写，请将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 设置为 `JsonNamingPolicy.CamelCase`，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="62433-190">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="62433-191">下面是一个用于序列化和 JSON 输出的示例类：</span><span class="sxs-lookup"><span data-stu-id="62433-191">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="62433-192">Camel 大小写属性命名策略：</span><span class="sxs-lookup"><span data-stu-id="62433-192">The camel case property naming policy:</span></span>

* <span data-ttu-id="62433-193">适用于序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="62433-193">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="62433-194">`[JsonPropertyName]` 特性重写。</span><span class="sxs-lookup"><span data-stu-id="62433-194">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="62433-195">这就是示例中的 JSON 属性名称 `Wind` 不是 camel 大小写的原因。</span><span class="sxs-lookup"><span data-stu-id="62433-195">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="62433-196">使用自定义 JSON 属性命名策略</span><span class="sxs-lookup"><span data-stu-id="62433-196">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="62433-197">若要使用自定义 JSON 属性命名策略，请创建一个派生自 <xref:System.Text.Json.JsonNamingPolicy> 的类，并重写 <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> 方法，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="62433-197">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="62433-198">然后，将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 属性设置为命名策略类的实例：</span><span class="sxs-lookup"><span data-stu-id="62433-198">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="62433-199">下面是一个用于序列化和 JSON 输出的示例类：</span><span class="sxs-lookup"><span data-stu-id="62433-199">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="62433-200">JSON 属性命名策略：</span><span class="sxs-lookup"><span data-stu-id="62433-200">The JSON property naming policy:</span></span>

* <span data-ttu-id="62433-201">适用于序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="62433-201">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="62433-202">`[JsonPropertyName]` 特性重写。</span><span class="sxs-lookup"><span data-stu-id="62433-202">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="62433-203">这就是示例中 `Wind` 的 JSON 属性名称不大写的原因。</span><span class="sxs-lookup"><span data-stu-id="62433-203">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="62433-204">Camel 大小写字典密钥</span><span class="sxs-lookup"><span data-stu-id="62433-204">Camel case dictionary keys</span></span>

<span data-ttu-id="62433-205">如果要序列化的对象的属性为 `Dictionary<string,TValue>`类型，则 `string` 键可转换为 camel 大小写形式。</span><span class="sxs-lookup"><span data-stu-id="62433-205">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="62433-206">为此，请将 <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> 设置为 `JsonNamingPolicy.CamelCase`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="62433-206">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="62433-207">使用名为 `TemperatureRanges` 的字典序列化具有键值对 `"ColdMinTemp", 20` 的对象，`"HotMinTemp", 40` 将导致 JSON 输出，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="62433-207">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="62433-208">字典键的 camel 大小写命名策略仅适用于序列化。</span><span class="sxs-lookup"><span data-stu-id="62433-208">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="62433-209">如果对字典进行反序列化，即使为 `DictionaryKeyPolicy`指定 `JsonNamingPolicy.CamelCase`，这些键也会与 JSON 文件匹配。</span><span class="sxs-lookup"><span data-stu-id="62433-209">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="62433-210">作为字符串的枚举</span><span class="sxs-lookup"><span data-stu-id="62433-210">Enums as strings</span></span>

<span data-ttu-id="62433-211">默认情况下，枚举作为数字序列化。</span><span class="sxs-lookup"><span data-stu-id="62433-211">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="62433-212">若要将枚举名称序列化为字符串，请使用 <xref:System.Text.Json.Serialization.JsonStringEnumConverter>。</span><span class="sxs-lookup"><span data-stu-id="62433-212">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="62433-213">例如，假设需要序列化以下具有枚举的类：</span><span class="sxs-lookup"><span data-stu-id="62433-213">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="62433-214">如果 `Hot`摘要，则默认情况下序列化的 JSON 的数值为3：</span><span class="sxs-lookup"><span data-stu-id="62433-214">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="62433-215">下面的示例代码序列化枚举名称，而不是数值，并将名称转换为 camel 大小写格式：</span><span class="sxs-lookup"><span data-stu-id="62433-215">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="62433-216">生成的 JSON 类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="62433-216">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="62433-217">还可以反序列化枚举字符串名称，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="62433-217">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="62433-218">从序列化中排除属性</span><span class="sxs-lookup"><span data-stu-id="62433-218">Exclude properties from serialization</span></span>

<span data-ttu-id="62433-219">默认情况下，将序列化所有公共属性。</span><span class="sxs-lookup"><span data-stu-id="62433-219">By default, all public properties are serialized.</span></span> <span data-ttu-id="62433-220">如果你不想让某些用户出现在 JSON 输出中，则可以使用几个选项。</span><span class="sxs-lookup"><span data-stu-id="62433-220">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="62433-221">本部分介绍如何排除：</span><span class="sxs-lookup"><span data-stu-id="62433-221">This section explains how to exclude:</span></span>

* [<span data-ttu-id="62433-222">单个属性</span><span class="sxs-lookup"><span data-stu-id="62433-222">Individual properties</span></span>](#exclude-individual-properties)
* [<span data-ttu-id="62433-223">所有只读属性</span><span class="sxs-lookup"><span data-stu-id="62433-223">All read-only properties</span></span>](#exclude-all-read-only-properties)
* [<span data-ttu-id="62433-224">所有 null 值属性</span><span class="sxs-lookup"><span data-stu-id="62433-224">All null-value properties</span></span>](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a><span data-ttu-id="62433-225">排除单个属性</span><span class="sxs-lookup"><span data-stu-id="62433-225">Exclude individual properties</span></span>

<span data-ttu-id="62433-226">若要忽略各个属性，请使用[[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute)属性。</span><span class="sxs-lookup"><span data-stu-id="62433-226">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="62433-227">下面是要序列化的示例类型和 JSON 输出：</span><span class="sxs-lookup"><span data-stu-id="62433-227">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="62433-228">排除所有只读属性</span><span class="sxs-lookup"><span data-stu-id="62433-228">Exclude all read-only properties</span></span>

<span data-ttu-id="62433-229">如果属性包含公共 getter 而不是公共 setter，则该属性为只读。</span><span class="sxs-lookup"><span data-stu-id="62433-229">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="62433-230">若要排除所有只读属性，请将 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> 设置为 `true`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="62433-230">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="62433-231">下面是要序列化的示例类型和 JSON 输出：</span><span class="sxs-lookup"><span data-stu-id="62433-231">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="62433-232">此选项仅适用于序列化。</span><span class="sxs-lookup"><span data-stu-id="62433-232">This option applies only to serialization.</span></span> <span data-ttu-id="62433-233">在反序列化期间，默认情况下将忽略只读属性。</span><span class="sxs-lookup"><span data-stu-id="62433-233">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="62433-234">排除所有 null 值属性</span><span class="sxs-lookup"><span data-stu-id="62433-234">Exclude all null value properties</span></span>

<span data-ttu-id="62433-235">若要排除所有 null 值属性，请将 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> 属性设置为 `true`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="62433-235">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="62433-236">下面是一个示例对象，用于序列化和 JSON 输出：</span><span class="sxs-lookup"><span data-stu-id="62433-236">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="62433-237">属性</span><span class="sxs-lookup"><span data-stu-id="62433-237">Property</span></span> |<span data-ttu-id="62433-238">“值”</span><span class="sxs-lookup"><span data-stu-id="62433-238">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="62433-239">日期</span><span class="sxs-lookup"><span data-stu-id="62433-239">Date</span></span>    | <span data-ttu-id="62433-240">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="62433-240">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="62433-241">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="62433-241">TemperatureCelsius</span></span>| <span data-ttu-id="62433-242">25</span><span class="sxs-lookup"><span data-stu-id="62433-242">25</span></span> |
| <span data-ttu-id="62433-243">摘要</span><span class="sxs-lookup"><span data-stu-id="62433-243">Summary</span></span>| <span data-ttu-id="62433-244">null</span><span class="sxs-lookup"><span data-stu-id="62433-244">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="62433-245">此设置适用于序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="62433-245">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="62433-246">有关对反序列化的影响的信息，请参阅[反序列化时忽略 null](#ignore-null-when-deserializing)。</span><span class="sxs-lookup"><span data-stu-id="62433-246">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="62433-247">自定义字符编码</span><span class="sxs-lookup"><span data-stu-id="62433-247">Customize character encoding</span></span>

<span data-ttu-id="62433-248">默认情况下，序列化程序对所有非 ASCII 字符进行转义。</span><span class="sxs-lookup"><span data-stu-id="62433-248">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="62433-249">也就是说，它将替换为 `\uxxxx`，其中 `xxxx` 为字符的 Unicode 代码。</span><span class="sxs-lookup"><span data-stu-id="62433-249">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="62433-250">例如，如果将 `Summary` 属性设置为西里尔жарко，则 `WeatherForecast` 对象将被序列化，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="62433-250">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="62433-251">序列化语言字符集</span><span class="sxs-lookup"><span data-stu-id="62433-251">Serialize language character sets</span></span>

<span data-ttu-id="62433-252">若要序列化一种或多种语言的字符集而不进行转义，请在创建 <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>的实例时指定[Unicode 范围](xref:System.Text.Unicode.UnicodeRanges)，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="62433-252">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="62433-253">此代码不会对西里尔字符或希腊语字符进行转义。</span><span class="sxs-lookup"><span data-stu-id="62433-253">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="62433-254">如果 `Summary` 属性设置为西里尔жарко，则 `WeatherForecast` 对象将被序列化，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="62433-254">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="62433-255">若要序列化所有语言集而不进行转义，请使用 <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="62433-255">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="62433-256">序列化特定字符</span><span class="sxs-lookup"><span data-stu-id="62433-256">Serialize specific characters</span></span>

<span data-ttu-id="62433-257">一种替代方法是指定要允许的单个字符，而不进行转义。</span><span class="sxs-lookup"><span data-stu-id="62433-257">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="62433-258">下面的示例仅序列化жарко的前两个字符：</span><span class="sxs-lookup"><span data-stu-id="62433-258">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="62433-259">下面是前面的代码生成的 JSON 示例：</span><span class="sxs-lookup"><span data-stu-id="62433-259">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="62433-260">序列化所有字符</span><span class="sxs-lookup"><span data-stu-id="62433-260">Serialize all characters</span></span>

<span data-ttu-id="62433-261">若要最大程度地减少转义，可以使用 <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="62433-261">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="62433-262">与默认编码器相比，`UnsafeRelaxedJsonEscaping` 编码器可以更好地允许字符通过非转义：</span><span class="sxs-lookup"><span data-stu-id="62433-262">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="62433-263">它不会转义 HTML 敏感字符，如 `<`、`>`、`&`和 `'`。</span><span class="sxs-lookup"><span data-stu-id="62433-263">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="62433-264">它不提供任何针对 XSS 或信息泄露攻击的额外防御防护，如客户端和服务器 disagreeing 在*字符集*上可能导致的任何其他防护。</span><span class="sxs-lookup"><span data-stu-id="62433-264">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="62433-265">仅当知道客户端将以 UTF-8 编码的 JSON 解释结果负载时，才使用 unsafe 编码器。</span><span class="sxs-lookup"><span data-stu-id="62433-265">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="62433-266">例如，如果服务器正在发送响应标头，则可以使用它 `Content-Type: application/json; charset=utf-8`。</span><span class="sxs-lookup"><span data-stu-id="62433-266">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="62433-267">永远不允许将原始 `UnsafeRelaxedJsonEscaping` 输出发送到 HTML 页或 `<script>` 元素。</span><span class="sxs-lookup"><span data-stu-id="62433-267">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="62433-268">序列化派生类的属性</span><span class="sxs-lookup"><span data-stu-id="62433-268">Serialize properties of derived classes</span></span>

<span data-ttu-id="62433-269">在编译时指定要序列化的类型时，不支持多态序列化。</span><span class="sxs-lookup"><span data-stu-id="62433-269">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="62433-270">例如，假设您有一个 `WeatherForecast` 类和一个派生类 `WeatherForecastWithWind`：</span><span class="sxs-lookup"><span data-stu-id="62433-270">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="62433-271">并且假设在编译时 `Serialize` 方法的类型实参 `WeatherForecast`：</span><span class="sxs-lookup"><span data-stu-id="62433-271">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="62433-272">在这种情况下，即使 `weatherForecast` 对象实际上是 `WeatherForecastWithWind` 对象，也不会对 `WindSpeed` 属性进行序列化。</span><span class="sxs-lookup"><span data-stu-id="62433-272">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="62433-273">仅序列化基类属性：</span><span class="sxs-lookup"><span data-stu-id="62433-273">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="62433-274">此行为旨在帮助防止在派生的运行时创建的类型中发生意外的数据泄露。</span><span class="sxs-lookup"><span data-stu-id="62433-274">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="62433-275">若要序列化派生类型的属性，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="62433-275">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="62433-276">调用 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 的重载，以便在运行时指定类型：</span><span class="sxs-lookup"><span data-stu-id="62433-276">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="62433-277">将要序列化的对象声明为 `object`。</span><span class="sxs-lookup"><span data-stu-id="62433-277">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="62433-278">在前面的示例方案中，这两种方法都会使 `WindSpeed` 属性包括在 JSON 输出中：</span><span class="sxs-lookup"><span data-stu-id="62433-278">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

<span data-ttu-id="62433-279">有关多态反序列化的信息，请参阅[支持多态反序列化](system-text-json-converters-how-to.md#support-polymorphic-deserialization)。</span><span class="sxs-lookup"><span data-stu-id="62433-279">For information about polymorphic deserialization, see [Support polymorphic deserialization](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="62433-280">允许注释和尾随逗号</span><span class="sxs-lookup"><span data-stu-id="62433-280">Allow comments and trailing commas</span></span>

<span data-ttu-id="62433-281">默认情况下，JSON 中不允许使用注释和尾随逗号。</span><span class="sxs-lookup"><span data-stu-id="62433-281">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="62433-282">若要允许 JSON 中的注释，请将 <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> 属性设置为 `JsonCommentHandling.Skip`。</span><span class="sxs-lookup"><span data-stu-id="62433-282">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="62433-283">若要允许尾随逗号，请将 <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="62433-283">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="62433-284">下面的示例演示如何允许两种方法：</span><span class="sxs-lookup"><span data-stu-id="62433-284">The following example shows how to allow both:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="62433-285">下面是包含注释和尾随逗号的示例 JSON：</span><span class="sxs-lookup"><span data-stu-id="62433-285">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="62433-286">不区分大小写的属性匹配</span><span class="sxs-lookup"><span data-stu-id="62433-286">Case-insensitive property matching</span></span>

<span data-ttu-id="62433-287">默认情况下，反序列化将查找 JSON 与目标对象属性之间区分大小写的属性名称匹配。</span><span class="sxs-lookup"><span data-stu-id="62433-287">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="62433-288">若要更改此行为，请将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> 设置为 `true`：</span><span class="sxs-lookup"><span data-stu-id="62433-288">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="62433-289">下面是采用 camel 大小写属性名称的示例 JSON。</span><span class="sxs-lookup"><span data-stu-id="62433-289">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="62433-290">它可以反序列化为具有 Pascal 大小写属性名称的以下类型。</span><span class="sxs-lookup"><span data-stu-id="62433-290">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="62433-291">句柄溢出 JSON</span><span class="sxs-lookup"><span data-stu-id="62433-291">Handle overflow JSON</span></span>

<span data-ttu-id="62433-292">反序列化时，可能会收到 JSON 中的数据，该数据不是由目标类型的属性表示的。</span><span class="sxs-lookup"><span data-stu-id="62433-292">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="62433-293">例如，假设目标类型为：</span><span class="sxs-lookup"><span data-stu-id="62433-293">For example, suppose your target type is this:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="62433-294">要反序列化的 JSON 如下：</span><span class="sxs-lookup"><span data-stu-id="62433-294">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="62433-295">如果将显示的 JSON 反序列化为显示的类型，则 "`DatesAvailable`" 和 "`SummaryWords`" 属性不会有任何位置，并且将丢失。</span><span class="sxs-lookup"><span data-stu-id="62433-295">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="62433-296">若要捕获额外数据（如这些属性），请将[JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute)特性应用到类型 `Dictionary<string,object>` 或 `Dictionary<string,JsonElement>`的属性：</span><span class="sxs-lookup"><span data-stu-id="62433-296">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="62433-297">反序列化前面显示的此示例类型的 JSON 时，额外的数据将成为 `ExtensionData` 属性的键值对：</span><span class="sxs-lookup"><span data-stu-id="62433-297">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="62433-298">属性</span><span class="sxs-lookup"><span data-stu-id="62433-298">Property</span></span> |<span data-ttu-id="62433-299">“值”</span><span class="sxs-lookup"><span data-stu-id="62433-299">Value</span></span>  |<span data-ttu-id="62433-300">注意</span><span class="sxs-lookup"><span data-stu-id="62433-300">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="62433-301">日期</span><span class="sxs-lookup"><span data-stu-id="62433-301">Date</span></span>    | <span data-ttu-id="62433-302">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="62433-302">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="62433-303">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="62433-303">TemperatureCelsius</span></span>| <span data-ttu-id="62433-304">0</span><span class="sxs-lookup"><span data-stu-id="62433-304">0</span></span> | <span data-ttu-id="62433-305">区分大小写不匹配（`temperatureCelsius` 在 JSON 中），因此未设置属性。</span><span class="sxs-lookup"><span data-stu-id="62433-305">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="62433-306">摘要</span><span class="sxs-lookup"><span data-stu-id="62433-306">Summary</span></span> | <span data-ttu-id="62433-307">修复</span><span class="sxs-lookup"><span data-stu-id="62433-307">Hot</span></span> ||
| <span data-ttu-id="62433-308">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="62433-308">ExtensionData</span></span> | <span data-ttu-id="62433-309">temperatureCelsius：25</span><span class="sxs-lookup"><span data-stu-id="62433-309">temperatureCelsius: 25</span></span> |<span data-ttu-id="62433-310">由于大小写不匹配，因此此 JSON 属性是一个额外的，并成为字典中的键值对。</span><span class="sxs-lookup"><span data-stu-id="62433-310">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="62433-311">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="62433-311">DatesAvailable:</span></span><br>  <span data-ttu-id="62433-312">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="62433-312">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="62433-313">8/2/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="62433-313">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="62433-314">JSON 中的额外属性将成为键值对，并将数组作为值对象。</span><span class="sxs-lookup"><span data-stu-id="62433-314">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="62433-315">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="62433-315">SummaryWords:</span></span><br><span data-ttu-id="62433-316">酷</span><span class="sxs-lookup"><span data-stu-id="62433-316">Cool</span></span><br><span data-ttu-id="62433-317">风</span><span class="sxs-lookup"><span data-stu-id="62433-317">Windy</span></span><br><span data-ttu-id="62433-318">Humid</span><span class="sxs-lookup"><span data-stu-id="62433-318">Humid</span></span> |<span data-ttu-id="62433-319">JSON 中的额外属性将成为键值对，并将数组作为值对象。</span><span class="sxs-lookup"><span data-stu-id="62433-319">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="62433-320">序列化目标对象时，扩展数据键值对将成为 JSON 属性，就像它们位于传入 JSON 中一样：</span><span class="sxs-lookup"><span data-stu-id="62433-320">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="62433-321">请注意，`ExtensionData` 属性名称不会出现在 JSON 中。</span><span class="sxs-lookup"><span data-stu-id="62433-321">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="62433-322">此行为允许 JSON 进行往返，而不会丢失任何不会被反序列化的额外数据。</span><span class="sxs-lookup"><span data-stu-id="62433-322">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="62433-323">反序列化时忽略 null</span><span class="sxs-lookup"><span data-stu-id="62433-323">Ignore null when deserializing</span></span>

<span data-ttu-id="62433-324">默认情况下，如果 JSON 中的属性为 null，则目标对象中的相应属性将设置为 null。</span><span class="sxs-lookup"><span data-stu-id="62433-324">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="62433-325">在某些情况下，target 属性可能具有默认值，并且你不希望 null 值覆盖默认值。</span><span class="sxs-lookup"><span data-stu-id="62433-325">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="62433-326">例如，假设以下代码表示目标对象：</span><span class="sxs-lookup"><span data-stu-id="62433-326">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="62433-327">假设反序列化以下 JSON：</span><span class="sxs-lookup"><span data-stu-id="62433-327">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="62433-328">反序列化后，`WeatherForecastWithDefault` 对象的 `Summary` 属性为 null。</span><span class="sxs-lookup"><span data-stu-id="62433-328">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="62433-329">若要更改此行为，请将 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> 设置为 `true`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="62433-329">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="62433-330">利用此选项，在反序列化后，`WeatherForecastWithDefault` 对象的 `Summary` 属性是默认值 "无摘要"。</span><span class="sxs-lookup"><span data-stu-id="62433-330">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="62433-331">JSON 中的 Null 值仅在有效时才会被忽略。</span><span class="sxs-lookup"><span data-stu-id="62433-331">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="62433-332">不可以为 null 的值类型的 Null 值将导致异常。</span><span class="sxs-lookup"><span data-stu-id="62433-332">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="62433-333">有关详细信息，请参阅 GitHub 上的 dotnet/corefx 存储库中[不可以为 null 的值类型上的问题 40922](https://github.com/dotnet/corefx/issues/40922) 。</span><span class="sxs-lookup"><span data-stu-id="62433-333">For more information, see [issue 40922 on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="62433-334">Utf8JsonReader、Utf8JsonWriter 和 JsonDocument</span><span class="sxs-lookup"><span data-stu-id="62433-334">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="62433-335"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> 是面向 UTF-8 编码 JSON 文本的一个高性能、低分配、只进读取器，从 `ReadOnlySpan<byte>` 读取信息。</span><span class="sxs-lookup"><span data-stu-id="62433-335"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="62433-336">`Utf8JsonReader` 是可用于生成自定义分析程序和反的低级别类型。</span><span class="sxs-lookup"><span data-stu-id="62433-336">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="62433-337"><xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 方法使用 `Utf8JsonReader` 的内容。</span><span class="sxs-lookup"><span data-stu-id="62433-337">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="62433-338"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> 是一种高性能的方式，用于从常见的 .NET 类型（如 `String`、`Int32`和 `DateTime`）编写 UTF-8 编码的 JSON 文本。</span><span class="sxs-lookup"><span data-stu-id="62433-338"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="62433-339">编写器是可用于生成自定义序列化程序的低级别类型。</span><span class="sxs-lookup"><span data-stu-id="62433-339">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="62433-340"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 方法使用 `Utf8JsonWriter` 的内容。</span><span class="sxs-lookup"><span data-stu-id="62433-340">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="62433-341"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> 提供使用 `Utf8JsonReader`生成只读文档对象模型（DOM）的功能。</span><span class="sxs-lookup"><span data-stu-id="62433-341"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="62433-342">DOM 提供对 JSON 有效负载中的数据的随机访问。</span><span class="sxs-lookup"><span data-stu-id="62433-342">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="62433-343">可以通过 <xref:System.Text.Json.JsonElement> 类型访问构成有效负载的 JSON 元素。</span><span class="sxs-lookup"><span data-stu-id="62433-343">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="62433-344">`JsonElement` 类型提供数组和对象枚举器，以及用于将 JSON 文本转换为常见 .NET 类型的 Api。</span><span class="sxs-lookup"><span data-stu-id="62433-344">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="62433-345">`JsonDocument` 公开 <xref:System.Text.Json.JsonDocument.RootElement> 属性。</span><span class="sxs-lookup"><span data-stu-id="62433-345">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="62433-346">以下部分说明了如何使用这些工具来读取和写入 JSON。</span><span class="sxs-lookup"><span data-stu-id="62433-346">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="62433-347">使用 JsonDocument 访问数据</span><span class="sxs-lookup"><span data-stu-id="62433-347">Use JsonDocument for access to data</span></span>

<span data-ttu-id="62433-348">下面的示例演示如何使用 <xref:System.Text.Json.JsonDocument> 类来随机访问 JSON 字符串中的数据：</span><span class="sxs-lookup"><span data-stu-id="62433-348">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="62433-349">前面的代码：</span><span class="sxs-lookup"><span data-stu-id="62433-349">The preceding code:</span></span>

* <span data-ttu-id="62433-350">假定 JSON 要分析的字符串中有一个名为 `jsonString`。</span><span class="sxs-lookup"><span data-stu-id="62433-350">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="62433-351">计算 `Students` 数组中具有 `Grade` 属性的对象的平均评分。</span><span class="sxs-lookup"><span data-stu-id="62433-351">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span> 
* <span data-ttu-id="62433-352">为没有成绩的学生分配默认等级70。</span><span class="sxs-lookup"><span data-stu-id="62433-352">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="62433-353">通过每次迭代增加 `count` 变量来对学生进行计数。</span><span class="sxs-lookup"><span data-stu-id="62433-353">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="62433-354">一种替代方法是调用 <xref:System.Text.Json.JsonElement.GetArrayLength%2A>，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="62433-354">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="62433-355">下面是此代码处理的 JSON 示例：</span><span class="sxs-lookup"><span data-stu-id="62433-355">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="62433-356">使用 JsonDocument 编写 JSON</span><span class="sxs-lookup"><span data-stu-id="62433-356">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="62433-357">下面的示例演示如何从 <xref:System.Text.Json.JsonDocument>编写 JSON：</span><span class="sxs-lookup"><span data-stu-id="62433-357">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="62433-358">前面的代码：</span><span class="sxs-lookup"><span data-stu-id="62433-358">The preceding code:</span></span>

* <span data-ttu-id="62433-359">读取 JSON 文件，将数据加载到 `JsonDocument`，并将格式化（整齐打印的） JSON 写入文件。</span><span class="sxs-lookup"><span data-stu-id="62433-359">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="62433-360">使用 <xref:System.Text.Json.JsonDocumentOptions> 指定允许但忽略输入 JSON 中的注释。</span><span class="sxs-lookup"><span data-stu-id="62433-360">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="62433-361">完成后，将对编写器调用 <xref:System.Text.Json.Utf8JsonWriter.Flush%2A>。</span><span class="sxs-lookup"><span data-stu-id="62433-361">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="62433-362">一种替代方法是让编写人员在 autoflush 时进行处理。</span><span class="sxs-lookup"><span data-stu-id="62433-362">An alternative is to let the writer autoflush when it's disposed.</span></span> 

<span data-ttu-id="62433-363">下面是示例代码处理的 JSON 输入的示例：</span><span class="sxs-lookup"><span data-stu-id="62433-363">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

<span data-ttu-id="62433-364">结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="62433-364">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="62433-365">使用 Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="62433-365">Use Utf8JsonWriter</span></span>

<span data-ttu-id="62433-366">下面的示例演示如何使用 <xref:System.Text.Json.Utf8JsonWriter> 类：</span><span class="sxs-lookup"><span data-stu-id="62433-366">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="62433-367">使用 Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="62433-367">Use Utf8JsonReader</span></span>

<span data-ttu-id="62433-368">下面的示例演示如何使用 <xref:System.Text.Json.Utf8JsonReader> 类：</span><span class="sxs-lookup"><span data-stu-id="62433-368">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="62433-369">前面的代码假定 `jsonUtf8` 变量是包含有效 JSON 的字节数组，编码为 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="62433-369">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="62433-370">使用 Utf8JsonReader 筛选数据</span><span class="sxs-lookup"><span data-stu-id="62433-370">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="62433-371">下面的示例演示如何同步读取文件并搜索值：</span><span class="sxs-lookup"><span data-stu-id="62433-371">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="62433-372">前面的代码：</span><span class="sxs-lookup"><span data-stu-id="62433-372">The preceding code:</span></span>

* <span data-ttu-id="62433-373">假定文件编码为 UTF-16，并将其转码为 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="62433-373">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="62433-374">可以通过使用以下代码，将编码为 UTF-8 的文件直接读入 `ReadOnlySpan<byte>`：</span><span class="sxs-lookup"><span data-stu-id="62433-374">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

* <span data-ttu-id="62433-375">假定 JSON 包含一个对象数组，并且每个对象可能包含一个字符串类型的 "name" 属性。</span><span class="sxs-lookup"><span data-stu-id="62433-375">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="62433-376">计算以 "大学" 结尾的对象和 `name` 属性值。</span><span class="sxs-lookup"><span data-stu-id="62433-376">Counts objects and `name` property values that end with "University".</span></span>

<span data-ttu-id="62433-377">下面是前面的代码可以读取的 JSON 示例。</span><span class="sxs-lookup"><span data-stu-id="62433-377">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="62433-378">生成的摘要消息为 "2 个，共4个名称以 ' 大学 ' 结尾"：</span><span class="sxs-lookup"><span data-stu-id="62433-378">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a><span data-ttu-id="62433-379">其他资源</span><span class="sxs-lookup"><span data-stu-id="62433-379">Additional resources</span></span>

* [<span data-ttu-id="62433-380">System.web 概述</span><span class="sxs-lookup"><span data-stu-id="62433-380">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="62433-381">System.web API 参考</span><span class="sxs-lookup"><span data-stu-id="62433-381">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="62433-382">为 system.exception 编写自定义转换器</span><span class="sxs-lookup"><span data-stu-id="62433-382">Write custom converters for System.Text.Json</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="62433-383">系统中的 DateTime 和 DateTimeOffset 支持</span><span class="sxs-lookup"><span data-stu-id="62433-383">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* [<span data-ttu-id="62433-384">Dotnet/corefx 存储库中标记为 json 功能的 GitHub 问题-文档</span><span class="sxs-lookup"><span data-stu-id="62433-384">GitHub issues in the dotnet/corefx repository labeled json-functionality-doc</span></span>](https://github.com/dotnet/corefx/labels/json-functionality-doc) 
