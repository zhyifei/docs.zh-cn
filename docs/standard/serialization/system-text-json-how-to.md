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
ms.openlocfilehash: f0245feb710f33d5fcea2a7125b8753ba6064018
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740431"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a><span data-ttu-id="71bec-102">如何在 .NET 中对 JSON 进行序列化和反序列化</span><span class="sxs-lookup"><span data-stu-id="71bec-102">How to serialize and deserialize JSON in .NET</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71bec-103">JSON 序列化文档正在构造。</span><span class="sxs-lookup"><span data-stu-id="71bec-103">The JSON serialization documentation is under construction.</span></span> <span data-ttu-id="71bec-104">本文不介绍所有方案。</span><span class="sxs-lookup"><span data-stu-id="71bec-104">This article doesn't cover all scenarios.</span></span> <span data-ttu-id="71bec-105">有关详细信息，请查看 GitHub 上的 dotnet/corefx 存储库中的[system.web 问题](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)，尤其是标记为[Json 功能的文档](https://github.com/dotnet/corefx/labels/json-functionality-doc)。</span><span class="sxs-lookup"><span data-stu-id="71bec-105">For more information, examine [System.Text.Json issues](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) in the dotnet/corefx repository on GitHub, especially those labeled [json-functionality-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span></span>

<span data-ttu-id="71bec-106">本文介绍如何使用 <xref:System.Text.Json> 命名空间在 JavaScript 对象表示法（JSON）之间进行序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="71bec-106">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="71bec-107">方向和示例代码直接使用库，而不是通过框架（如[ASP.NET Core](/aspnet/core/)）使用。</span><span class="sxs-lookup"><span data-stu-id="71bec-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

## <a name="namespaces"></a><span data-ttu-id="71bec-108">命名空间</span><span class="sxs-lookup"><span data-stu-id="71bec-108">Namespaces</span></span>

<span data-ttu-id="71bec-109"><xref:System.Text.Json> 命名空间包含所有入口点和主要类型。</span><span class="sxs-lookup"><span data-stu-id="71bec-109">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="71bec-110"><xref:System.Text.Json.Serialization> 命名空间包含用于高级方案的属性和 Api，以及特定于序列化和反序列化的自定义。</span><span class="sxs-lookup"><span data-stu-id="71bec-110">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="71bec-111">本文中所示的代码示例要求其中一个或两个命名空间都有 `using` 指令：</span><span class="sxs-lookup"><span data-stu-id="71bec-111">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="71bec-112">`System.Text.Json`当前不支持 <xref:System.Runtime.Serialization> 命名空间中的属性。</span><span class="sxs-lookup"><span data-stu-id="71bec-112">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="71bec-113">如何将 .NET 对象写入 JSON （序列化）</span><span class="sxs-lookup"><span data-stu-id="71bec-113">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="71bec-114">若要将 JSON 写入字符串或文件，请调用 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="71bec-114">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="71bec-115">下面的示例将 JSON 创建为字符串：</span><span class="sxs-lookup"><span data-stu-id="71bec-115">The following example creates JSON as a string:</span></span>

```csharp
string json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="71bec-116">下面的示例使用同步代码创建 JSON 文件：</span><span class="sxs-lookup"><span data-stu-id="71bec-116">The following example uses synchronous code to create a JSON file:</span></span>

```csharp
File.WriteAllText(outputFileName, JsonSerializer.Serialize(weatherForecast));
```

<span data-ttu-id="71bec-117">下面的示例使用异步代码创建 JSON 文件：</span><span class="sxs-lookup"><span data-stu-id="71bec-117">The following example uses asynchronous code to create a JSON file:</span></span>

```csharp
using (FileStream fs = File.Create(outputFileName))
{
    await JsonSerializer.SerializeAsync(fs, weatherForecast);
}
```

<span data-ttu-id="71bec-118">前面的示例对要序列化的类型使用类型推理。</span><span class="sxs-lookup"><span data-stu-id="71bec-118">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="71bec-119">`Serialize()` 的重载采用泛型类型参数：</span><span class="sxs-lookup"><span data-stu-id="71bec-119">An overload of `Serialize()` takes a generic type parameter:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

### <a name="serialization-example"></a><span data-ttu-id="71bec-120">序列化示例</span><span class="sxs-lookup"><span data-stu-id="71bec-120">Serialization example</span></span>

<span data-ttu-id="71bec-121">下面是包含集合和嵌套类的示例类型：</span><span class="sxs-lookup"><span data-stu-id="71bec-121">Here's an example type that contains collections and nested classes:</span></span>

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

<span data-ttu-id="71bec-122">序列化上述类型的实例的 JSON 输出类似于下面的示例。</span><span class="sxs-lookup"><span data-stu-id="71bec-122">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="71bec-123">默认情况下，JSON 输出为缩小：</span><span class="sxs-lookup"><span data-stu-id="71bec-123">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="71bec-124">下面的示例演示了相同的 JSON 格式（也就是用空格和缩进进行整齐打印）：</span><span class="sxs-lookup"><span data-stu-id="71bec-124">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="71bec-125">序列化为 UTF-8</span><span class="sxs-lookup"><span data-stu-id="71bec-125">Serialize to UTF-8</span></span>

<span data-ttu-id="71bec-126">若要序列化为 UTF-8，请调用 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 方法：</span><span class="sxs-lookup"><span data-stu-id="71bec-126">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

```csharp
byte[] jsonUtf8Bytes = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="71bec-127">还提供了一个采用 <xref:System.Text.Json.Utf8JsonWriter> 的 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 重载。</span><span class="sxs-lookup"><span data-stu-id="71bec-127">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="71bec-128">序列化为 UTF-8 比使用基于字符串的方法更快5-10%。</span><span class="sxs-lookup"><span data-stu-id="71bec-128">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="71bec-129">不同之处在于，不需要将字节（如 UTF-8）转换为字符串（UTF-16）。</span><span class="sxs-lookup"><span data-stu-id="71bec-129">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="71bec-130">序列化行为</span><span class="sxs-lookup"><span data-stu-id="71bec-130">Serialization behavior</span></span>

* <span data-ttu-id="71bec-131">默认情况下，将序列化所有公共属性。</span><span class="sxs-lookup"><span data-stu-id="71bec-131">By default, all public properties are serialized.</span></span> <span data-ttu-id="71bec-132">您可以[指定要排除的属性](#exclude-properties-from-serialization)。</span><span class="sxs-lookup"><span data-stu-id="71bec-132">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="71bec-133">[默认编码器](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)会转义非 ascii 字符、ASCII 范围内的 HTML 敏感字符以及必须根据[JSON 规范](https://tools.ietf.org/html/rfc8259#section-7)进行转义的字符。</span><span class="sxs-lookup"><span data-stu-id="71bec-133">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="71bec-134">默认情况下，JSON 为缩小。</span><span class="sxs-lookup"><span data-stu-id="71bec-134">By default, JSON is minified.</span></span> <span data-ttu-id="71bec-135">可以很好[打印 JSON](#serialize-to-formatted-json)。</span><span class="sxs-lookup"><span data-stu-id="71bec-135">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="71bec-136">默认情况下，JSON 名称的大小写与 .NET 名称匹配。</span><span class="sxs-lookup"><span data-stu-id="71bec-136">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="71bec-137">你可以[自定义 JSON 名称大小写](#customize-json-names-and-values)。</span><span class="sxs-lookup"><span data-stu-id="71bec-137">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="71bec-138">检测到循环引用并引发异常。</span><span class="sxs-lookup"><span data-stu-id="71bec-138">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="71bec-139">有关详细信息，请参阅 GitHub 上的 dotnet/corefx 存储库中的[循环引用问题](https://github.com/dotnet/corefx/issues/38579)。</span><span class="sxs-lookup"><span data-stu-id="71bec-139">For more information, see the [issue on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="71bec-140">当前排除了字段。</span><span class="sxs-lookup"><span data-stu-id="71bec-140">Currently, fields are excluded.</span></span>

<span data-ttu-id="71bec-141">支持的类型包括：</span><span class="sxs-lookup"><span data-stu-id="71bec-141">Supported types include:</span></span>

* <span data-ttu-id="71bec-142">映射到 JavaScript 基元的 .NET 基元，如数值类型、字符串和布尔值。</span><span class="sxs-lookup"><span data-stu-id="71bec-142">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="71bec-143">用户定义的[普通旧 CLR 对象（poco）](https://stackoverflow.com/questions/250001/poco-definition)。</span><span class="sxs-lookup"><span data-stu-id="71bec-143">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="71bec-144">一维数组和交错数组（`ArrayName[][]`）。</span><span class="sxs-lookup"><span data-stu-id="71bec-144">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="71bec-145">`Dictionary<string,TValue>`，其中 `TValue` 为 `object`、`JsonElement`或 POCO。</span><span class="sxs-lookup"><span data-stu-id="71bec-145">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="71bec-146">以下命名空间中的集合。</span><span class="sxs-lookup"><span data-stu-id="71bec-146">Collections from the following namespaces.</span></span> <span data-ttu-id="71bec-147">有关详细信息，请参阅 GitHub 上的 dotnet/corefx 存储库中的[收集支持问题](https://github.com/dotnet/corefx/issues/36643)。</span><span class="sxs-lookup"><span data-stu-id="71bec-147">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="71bec-148">可以[实现自定义转换器](system-text-json-converters-how-to.md)来处理其他类型或提供内置转换器不支持的功能。</span><span class="sxs-lookup"><span data-stu-id="71bec-148">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="71bec-149">如何将 JSON 读入 .NET 对象（反序列化）</span><span class="sxs-lookup"><span data-stu-id="71bec-149">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="71bec-150">若要从字符串或文件进行反序列化，请调用 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="71bec-150">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="71bec-151">下面的示例从字符串读取 JSON：</span><span class="sxs-lookup"><span data-stu-id="71bec-151">The following example reads JSON from a string:</span></span>

```csharp
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(jsonString);
```

<span data-ttu-id="71bec-152">若要通过使用同步代码从文件进行反序列化，请将文件读入字符串中，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="71bec-152">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

```csharp
string jsonString = File.ReadAllText(inputFileName);
weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(jsonString);
```

<span data-ttu-id="71bec-153">若要使用异步代码从文件进行反序列化，请调用 <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> 方法：</span><span class="sxs-lookup"><span data-stu-id="71bec-153">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

```csharp
using (FileStream fs = File.OpenRead(inputFileName))
{
    weatherForecast = await JsonSerializer.DeserializeAsync<WeatherForecast>(fs);
}
```

<span data-ttu-id="71bec-154">有关示例类型和对应的 JSON，请参阅[序列化示例](#serialization-example)部分。</span><span class="sxs-lookup"><span data-stu-id="71bec-154">For an example type and corresponding JSON, see the [Serialization example](#serialization-example) section.</span></span>

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="71bec-155">从 UTF-8 反序列化</span><span class="sxs-lookup"><span data-stu-id="71bec-155">Deserialize from UTF-8</span></span>

<span data-ttu-id="71bec-156">若要从 UTF-8 进行反序列化，请调用采用 `Utf8JsonReader` 或 `ReadOnlySpan<byte>`的 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 重载，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="71bec-156">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="71bec-157">这些示例假定 JSON 位于名为 jsonUtf8Bytes 的字节数组中。</span><span class="sxs-lookup"><span data-stu-id="71bec-157">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

```csharp
var readOnlySpan = new ReadOnlySpan<byte>(jsonUtf8Bytes);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(readOnlySpan);
```

```csharp
var utf8Reader = new Utf8JsonReader(jsonUtf8Bytes);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(ref utf8Reader);
```

## <a name="deserialization-behavior"></a><span data-ttu-id="71bec-158">反序列化行为</span><span class="sxs-lookup"><span data-stu-id="71bec-158">Deserialization behavior</span></span>

* <span data-ttu-id="71bec-159">默认情况下，属性名称匹配区分大小写。</span><span class="sxs-lookup"><span data-stu-id="71bec-159">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="71bec-160">可以[指定不区分大小写](#case-insensitive-property-matching)。</span><span class="sxs-lookup"><span data-stu-id="71bec-160">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="71bec-161">如果 JSON 包含只读属性的值，则该值将被忽略，并且不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="71bec-161">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="71bec-162">不支持反序列化到不具有无参数构造函数的引用类型。</span><span class="sxs-lookup"><span data-stu-id="71bec-162">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="71bec-163">不支持对不可变对象或只读属性进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="71bec-163">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="71bec-164">有关详细信息，请参阅 github 上的 dotnet/corefx 存储库中对[不可变对象支持](https://github.com/dotnet/corefx/issues/38569)的 GitHub 问题和对[只读属性的支持问题](https://github.com/dotnet/corefx/issues/38163)。</span><span class="sxs-lookup"><span data-stu-id="71bec-164">For more information, see the GitHub [issue on immutable object support](https://github.com/dotnet/corefx/issues/38569) and the [issue on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="71bec-165">默认情况下，枚举作为数字支持。</span><span class="sxs-lookup"><span data-stu-id="71bec-165">By default, enums are supported as numbers.</span></span> <span data-ttu-id="71bec-166">可以将[枚举名称序列化为字符串](#enums-as-strings)。</span><span class="sxs-lookup"><span data-stu-id="71bec-166">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="71bec-167">不支持字段。</span><span class="sxs-lookup"><span data-stu-id="71bec-167">Fields aren't supported.</span></span>
* <span data-ttu-id="71bec-168">默认情况下，JSON 中的注释或尾随逗号引发异常。</span><span class="sxs-lookup"><span data-stu-id="71bec-168">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="71bec-169">您可以[允许注释和尾随逗号](#allow-comments-and-trailing-commas)。</span><span class="sxs-lookup"><span data-stu-id="71bec-169">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="71bec-170">[默认的最大深度](xref:System.Text.Json.JsonReaderOptions.MaxDepth)为64。</span><span class="sxs-lookup"><span data-stu-id="71bec-170">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="71bec-171">您可以[实现自定义转换器](system-text-json-converters-how-to.md)以提供内置转换器不支持的功能。</span><span class="sxs-lookup"><span data-stu-id="71bec-171">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="71bec-172">序列化为格式化的 JSON</span><span class="sxs-lookup"><span data-stu-id="71bec-172">Serialize to formatted JSON</span></span>

<span data-ttu-id="71bec-173">若要整齐地打印 JSON 输出，请将 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> 设置为 `true`：</span><span class="sxs-lookup"><span data-stu-id="71bec-173">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="71bec-174">下面是一个要进行序列化的示例类型，并显示为漂亮的 JSON 输出：</span><span class="sxs-lookup"><span data-stu-id="71bec-174">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

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

## <a name="customize-json-names-and-values"></a><span data-ttu-id="71bec-175">自定义 JSON 名称和值</span><span class="sxs-lookup"><span data-stu-id="71bec-175">Customize JSON names and values</span></span>

<span data-ttu-id="71bec-176">默认情况下，JSON 输出中的属性名称和字典键不变，包括大小写。</span><span class="sxs-lookup"><span data-stu-id="71bec-176">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="71bec-177">枚举值表示为数值。</span><span class="sxs-lookup"><span data-stu-id="71bec-177">Enum values are represented as numbers.</span></span> <span data-ttu-id="71bec-178">本部分介绍如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="71bec-178">This section explains how to:</span></span>

* <span data-ttu-id="71bec-179">自定义各个属性名称</span><span class="sxs-lookup"><span data-stu-id="71bec-179">Customize individual property names</span></span>
* <span data-ttu-id="71bec-180">将所有属性名称转换为 camel 大小写</span><span class="sxs-lookup"><span data-stu-id="71bec-180">Convert all property names to camel case</span></span>
* <span data-ttu-id="71bec-181">实现自定义属性命名策略</span><span class="sxs-lookup"><span data-stu-id="71bec-181">Implement a custom property naming policy</span></span>
* <span data-ttu-id="71bec-182">将字典键转换为 camel 大小写</span><span class="sxs-lookup"><span data-stu-id="71bec-182">Convert dictionary keys to camel case</span></span>
* <span data-ttu-id="71bec-183">将枚举转换为字符串和 camel 大小写</span><span class="sxs-lookup"><span data-stu-id="71bec-183">Convert enums to strings and camel case</span></span> 

<span data-ttu-id="71bec-184">对于需要对 JSON 属性名称和值进行特殊处理的其他方案，可以[实现自定义转换器](system-text-json-converters-how-to.md)。</span><span class="sxs-lookup"><span data-stu-id="71bec-184">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="71bec-185">自定义各个属性名称</span><span class="sxs-lookup"><span data-stu-id="71bec-185">Customize individual property names</span></span>

<span data-ttu-id="71bec-186">若要设置单个属性的名称，请使用[[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute)属性。</span><span class="sxs-lookup"><span data-stu-id="71bec-186">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="71bec-187">下面是序列化和生成的 JSON 的示例类型：</span><span class="sxs-lookup"><span data-stu-id="71bec-187">Here's an example type to serialize and resulting JSON:</span></span>

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

<span data-ttu-id="71bec-188">此属性设置的属性名称：</span><span class="sxs-lookup"><span data-stu-id="71bec-188">The property name set by this attribute:</span></span>

* <span data-ttu-id="71bec-189">同时适用于序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="71bec-189">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="71bec-190">优先于属性命名策略。</span><span class="sxs-lookup"><span data-stu-id="71bec-190">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="71bec-191">对所有 JSON 属性名称使用 camel 大小写</span><span class="sxs-lookup"><span data-stu-id="71bec-191">Use camel case for all JSON property names</span></span>

<span data-ttu-id="71bec-192">若要对所有 JSON 属性名称使用 camel 大小写，请将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 设置为 `JsonNamingPolicy.CamelCase`，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="71bec-192">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="71bec-193">下面是一个用于序列化和 JSON 输出的示例类：</span><span class="sxs-lookup"><span data-stu-id="71bec-193">Here's an example class to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureCelsius { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="71bec-194">Camel 大小写属性命名策略：</span><span class="sxs-lookup"><span data-stu-id="71bec-194">The camel case property naming policy:</span></span>

* <span data-ttu-id="71bec-195">适用于序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="71bec-195">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="71bec-196">`[JsonPropertyName]` 特性重写。</span><span class="sxs-lookup"><span data-stu-id="71bec-196">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="71bec-197">这就是示例中的 JSON 属性名称 `Wind` 不是 camel 大小写的原因。</span><span class="sxs-lookup"><span data-stu-id="71bec-197">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="71bec-198">使用自定义 JSON 属性命名策略</span><span class="sxs-lookup"><span data-stu-id="71bec-198">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="71bec-199">若要使用自定义 JSON 属性命名策略，请创建一个派生自 <xref:System.Text.Json.JsonNamingPolicy> 的类，并重写 <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> 方法，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="71bec-199">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

<span data-ttu-id="71bec-200">然后，将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 属性设置为命名策略类的实例：</span><span class="sxs-lookup"><span data-stu-id="71bec-200">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="71bec-201">下面是一个用于序列化和 JSON 输出的示例类：</span><span class="sxs-lookup"><span data-stu-id="71bec-201">Here's an example class to serialize and JSON output:</span></span>

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

<span data-ttu-id="71bec-202">JSON 属性命名策略：</span><span class="sxs-lookup"><span data-stu-id="71bec-202">The JSON property naming policy:</span></span>

* <span data-ttu-id="71bec-203">适用于序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="71bec-203">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="71bec-204">`[JsonPropertyName]` 特性重写。</span><span class="sxs-lookup"><span data-stu-id="71bec-204">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="71bec-205">这就是示例中 `Wind` 的 JSON 属性名称不大写的原因。</span><span class="sxs-lookup"><span data-stu-id="71bec-205">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="71bec-206">Camel 大小写字典密钥</span><span class="sxs-lookup"><span data-stu-id="71bec-206">Camel case dictionary keys</span></span>

<span data-ttu-id="71bec-207">如果要序列化的对象的属性为 `Dictionary<string,TValue>`类型，则 `string` 键可转换为 camel 大小写形式。</span><span class="sxs-lookup"><span data-stu-id="71bec-207">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="71bec-208">为此，请将 <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> 设置为 `JsonNamingPolicy.CamelCase`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="71bec-208">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="71bec-209">使用名为 `TemperatureRanges` 的字典序列化具有键值对 `"ColdMinTemp", 20` 的对象，`"HotMinTemp", 40` 将导致 JSON 输出，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="71bec-209">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

<span data-ttu-id="71bec-210">字典键的 camel 大小写命名策略仅适用于序列化。</span><span class="sxs-lookup"><span data-stu-id="71bec-210">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="71bec-211">如果对字典进行反序列化，即使为 `DictionaryKeyPolicy`指定 `JsonNamingPolicy.CamelCase`，这些键也会与 JSON 文件匹配。</span><span class="sxs-lookup"><span data-stu-id="71bec-211">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="71bec-212">作为字符串的枚举</span><span class="sxs-lookup"><span data-stu-id="71bec-212">Enums as strings</span></span>

<span data-ttu-id="71bec-213">默认情况下，枚举作为数字序列化。</span><span class="sxs-lookup"><span data-stu-id="71bec-213">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="71bec-214">若要将枚举名称序列化为字符串，请使用 <xref:System.Text.Json.Serialization.JsonStringEnumConverter>。</span><span class="sxs-lookup"><span data-stu-id="71bec-214">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="71bec-215">例如，假设需要序列化以下具有枚举的类：</span><span class="sxs-lookup"><span data-stu-id="71bec-215">For example, suppose you need to serialize the following class that has an enum:</span></span>

```csharp
class WeatherForecastWithEnum
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public Summary Summary { get; set; }
}

public enum Summary
{
    Cold, Cool, Warm, Hot
}
```

<span data-ttu-id="71bec-216">如果 `Hot`摘要，则默认情况下序列化的 JSON 的数值为3：</span><span class="sxs-lookup"><span data-stu-id="71bec-216">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": 3
}
```

<span data-ttu-id="71bec-217">下面的示例代码改为序列化枚举名称，并将它们转换为 camel 大小写：</span><span class="sxs-lookup"><span data-stu-id="71bec-217">The following sample code serializes the enum names instead, and converts them to camel case:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new JsonStringEnumConverter(JsonNamingPolicy.CamelCase));
jsonWithEnumsAsStrings = JsonSerializer.Serialize(weatherForecastWithEnum, options);
```

<span data-ttu-id="71bec-218">生成的 JSON 类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="71bec-218">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="71bec-219">同时，支持将枚举作为字符串应用于反序列化，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="71bec-219">The support for enums as strings applies to deserialization also, as shown in the following example:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new JsonStringEnumConverter(JsonNamingPolicy.CamelCase));
weatherForecastWithEnum = JsonSerializer.Deserialize<WeatherForecastWithEnum>(jsonWithEnumsAsStrings, options);
```

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="71bec-220">从序列化中排除属性</span><span class="sxs-lookup"><span data-stu-id="71bec-220">Exclude properties from serialization</span></span>

<span data-ttu-id="71bec-221">默认情况下，将序列化所有公共属性。</span><span class="sxs-lookup"><span data-stu-id="71bec-221">By default, all public properties are serialized.</span></span> <span data-ttu-id="71bec-222">如果你不想让某些用户出现在 JSON 输出中，则可以使用几个选项。</span><span class="sxs-lookup"><span data-stu-id="71bec-222">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="71bec-223">本部分介绍如何排除：</span><span class="sxs-lookup"><span data-stu-id="71bec-223">This section explains how to exclude:</span></span>

* <span data-ttu-id="71bec-224">单个属性</span><span class="sxs-lookup"><span data-stu-id="71bec-224">Individual properties</span></span>
* <span data-ttu-id="71bec-225">所有只读属性</span><span class="sxs-lookup"><span data-stu-id="71bec-225">All read-only properties</span></span>
* <span data-ttu-id="71bec-226">所有 null 值属性</span><span class="sxs-lookup"><span data-stu-id="71bec-226">All null-value properties</span></span> 

### <a name="exclude-individual-properties"></a><span data-ttu-id="71bec-227">排除单个属性</span><span class="sxs-lookup"><span data-stu-id="71bec-227">Exclude individual properties</span></span>

<span data-ttu-id="71bec-228">若要忽略各个属性，请使用[[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute)属性。</span><span class="sxs-lookup"><span data-stu-id="71bec-228">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="71bec-229">下面是要序列化的示例类型和 JSON 输出：</span><span class="sxs-lookup"><span data-stu-id="71bec-229">Here's an example type to serialize and JSON output:</span></span>

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

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="71bec-230">排除所有只读属性</span><span class="sxs-lookup"><span data-stu-id="71bec-230">Exclude all read-only properties</span></span>

<span data-ttu-id="71bec-231">如果属性包含公共 getter 而不是公共 setter，则该属性为只读。</span><span class="sxs-lookup"><span data-stu-id="71bec-231">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="71bec-232">若要排除所有只读属性，请将 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> 设置为 `true`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="71bec-232">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="71bec-233">下面是要序列化的示例类型和 JSON 输出：</span><span class="sxs-lookup"><span data-stu-id="71bec-233">Here's an example type to serialize and JSON output:</span></span>

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

<span data-ttu-id="71bec-234">此选项仅适用于序列化。</span><span class="sxs-lookup"><span data-stu-id="71bec-234">This option applies only to serialization.</span></span> <span data-ttu-id="71bec-235">在反序列化期间，默认情况下将忽略只读属性。</span><span class="sxs-lookup"><span data-stu-id="71bec-235">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="71bec-236">排除所有 null 值属性</span><span class="sxs-lookup"><span data-stu-id="71bec-236">Exclude all null value properties</span></span>

<span data-ttu-id="71bec-237">若要排除所有 null 值属性，请将 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> 属性设置为 `true`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="71bec-237">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="71bec-238">下面是一个示例对象，用于序列化和 JSON 输出：</span><span class="sxs-lookup"><span data-stu-id="71bec-238">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="71bec-239">Property</span><span class="sxs-lookup"><span data-stu-id="71bec-239">Property</span></span> |<span data-ttu-id="71bec-240">“值”</span><span class="sxs-lookup"><span data-stu-id="71bec-240">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="71bec-241">日期</span><span class="sxs-lookup"><span data-stu-id="71bec-241">Date</span></span>    | <span data-ttu-id="71bec-242">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="71bec-242">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="71bec-243">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="71bec-243">TemperatureC</span></span>| <span data-ttu-id="71bec-244">25</span><span class="sxs-lookup"><span data-stu-id="71bec-244">25</span></span> |
| <span data-ttu-id="71bec-245">总结</span><span class="sxs-lookup"><span data-stu-id="71bec-245">Summary</span></span>| <span data-ttu-id="71bec-246">null</span><span class="sxs-lookup"><span data-stu-id="71bec-246">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

<span data-ttu-id="71bec-247">此设置适用于序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="71bec-247">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="71bec-248">有关对反序列化的影响的信息，请参阅[反序列化时忽略 null](#ignore-null-when-deserializing)。</span><span class="sxs-lookup"><span data-stu-id="71bec-248">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="71bec-249">自定义字符编码</span><span class="sxs-lookup"><span data-stu-id="71bec-249">Customize character encoding</span></span>

<span data-ttu-id="71bec-250">默认情况下，序列化程序对所有非 ASCII 字符进行转义。</span><span class="sxs-lookup"><span data-stu-id="71bec-250">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="71bec-251">也就是说，它将替换为 `\uxxxx`，其中 `xxxxx` 为字符的 Unicode 代码。</span><span class="sxs-lookup"><span data-stu-id="71bec-251">That is, it replaces them with `\uxxxx` where `xxxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="71bec-252">例如，如果将 `Summary` 属性设置为西里尔жарко，则 `WeatherForecast` 对象将被序列化，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="71bec-252">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="71bec-253">序列化语言字符集</span><span class="sxs-lookup"><span data-stu-id="71bec-253">Serialize language character sets</span></span>

<span data-ttu-id="71bec-254">若要序列化一种或多种语言的字符集，请在创建 <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>的实例时指定[Unicode 范围](xref:System.Text.Unicode.UnicodeRanges)，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="71bec-254">To serialize the character set(s) of one or more languages, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
using System.Text.Unicode;
```

```csharp
var options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.Create(UnicodeRanges.Cyrillic, UnicodeRanges.GreekExtended)
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="71bec-255">此代码序列化西里尔语和希腊语字符。</span><span class="sxs-lookup"><span data-stu-id="71bec-255">This code serializes Cyrillic and Greek characters.</span></span> <span data-ttu-id="71bec-256">西里尔字符显示在下面的示例中：</span><span class="sxs-lookup"><span data-stu-id="71bec-256">Cyrillic characters are shown in the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "жарко",
}
```

<span data-ttu-id="71bec-257">若要指定所有语言，请使用 <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="71bec-257">To specify all languages, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="71bec-258">序列化特定字符</span><span class="sxs-lookup"><span data-stu-id="71bec-258">Serialize specific characters</span></span>

<span data-ttu-id="71bec-259">一种替代方法是指定要允许的单个字符，而不进行转义。</span><span class="sxs-lookup"><span data-stu-id="71bec-259">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="71bec-260">下面的示例仅序列化жарко的前两个字符：</span><span class="sxs-lookup"><span data-stu-id="71bec-260">The following example serializes only the first two characters of жарко:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
using System.Text.Unicode;
```

```csharp
var encoderSettings = new TextEncoderSettings();
encoderSettings.AllowCharacters('\u0436', '\u0430');
options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.Create(encoderSettings)
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="71bec-261">下面是前面的代码生成的 JSON 示例：</span><span class="sxs-lookup"><span data-stu-id="71bec-261">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="71bec-262">序列化所有字符</span><span class="sxs-lookup"><span data-stu-id="71bec-262">Serialize all characters</span></span>

<span data-ttu-id="71bec-263">若要最大程度地减少转义，可以使用 <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="71bec-263">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
```

```csharp
options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.UnsafeRelaxedJsonEscaping
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

> [!CAUTION]
> <span data-ttu-id="71bec-264">不同于默认编码器，`UnsafeRelaxedJsonEscaping` 编码器：</span><span class="sxs-lookup"><span data-stu-id="71bec-264">Unlike the default encoder, the `UnsafeRelaxedJsonEscaping` encoder:</span></span>
>
> * <span data-ttu-id="71bec-265">不会转义 HTML 敏感字符，如 `<`、`>`、`&`和 `'`。</span><span class="sxs-lookup"><span data-stu-id="71bec-265">Doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="71bec-266">不会针对 XSS 或信息泄露攻击提供任何其他深层防御防护，如客户端和服务器 disagreeing 对*字符集*进行的保护。</span><span class="sxs-lookup"><span data-stu-id="71bec-266">Doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
> * <span data-ttu-id="71bec-267">比默认编码器更宽松，允许字符通过非转义的字符传递。</span><span class="sxs-lookup"><span data-stu-id="71bec-267">Is more permissive than the default encoder on which characters are allowed to pass through unescaped.</span></span>
>
> <span data-ttu-id="71bec-268">仅当知道客户端将以 UTF-8 编码的 JSON 解释结果负载时，才使用 unsafe 编码器。</span><span class="sxs-lookup"><span data-stu-id="71bec-268">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="71bec-269">例如，如果服务器正在发送响应标头，则可以使用它 `Content-Type: application/json; charset=utf-8`。</span><span class="sxs-lookup"><span data-stu-id="71bec-269">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="71bec-270">永远不允许将原始 `UnsafeRelaxedJsonEscaping` 输出发送到 HTML 页或 `<script>` 元素。</span><span class="sxs-lookup"><span data-stu-id="71bec-270">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="71bec-271">序列化派生类的属性</span><span class="sxs-lookup"><span data-stu-id="71bec-271">Serialize properties of derived classes</span></span>

<span data-ttu-id="71bec-272">在编译时指定要序列化的类型时，不支持多态序列化。</span><span class="sxs-lookup"><span data-stu-id="71bec-272">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="71bec-273">例如，假设您有一个 `WeatherForecast` 类和一个派生类 `WeatherForecastWithWind`：</span><span class="sxs-lookup"><span data-stu-id="71bec-273">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

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

<span data-ttu-id="71bec-274">并且假设在编译时 `Serialize` 方法的类型实参 `WeatherForecast`：</span><span class="sxs-lookup"><span data-stu-id="71bec-274">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="71bec-275">在这种情况下，即使 `weatherForecast` 对象实际上是 `WeatherForecastWithWind` 对象，也不会对 `WindSpeed` 属性进行序列化。</span><span class="sxs-lookup"><span data-stu-id="71bec-275">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="71bec-276">仅序列化基类属性：</span><span class="sxs-lookup"><span data-stu-id="71bec-276">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="71bec-277">此行为旨在帮助防止在派生的运行时创建的类型中发生意外的数据泄露。</span><span class="sxs-lookup"><span data-stu-id="71bec-277">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="71bec-278">若要序列化派生类型的属性，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="71bec-278">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="71bec-279">调用 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 的重载，以便在运行时指定类型：</span><span class="sxs-lookup"><span data-stu-id="71bec-279">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* <span data-ttu-id="71bec-280">将要序列化的对象声明为 `object`。</span><span class="sxs-lookup"><span data-stu-id="71bec-280">Declare the object to be serialized as `object`.</span></span>

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

<span data-ttu-id="71bec-281">在前面的示例方案中，这两种方法都会使 `WindSpeed` 属性包括在 JSON 输出中：</span><span class="sxs-lookup"><span data-stu-id="71bec-281">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

<span data-ttu-id="71bec-282">有关多态反序列化的信息，请参阅[支持多态反序列化](system-text-json-converters-how-to.md#support-polymorphic-deserialization)。</span><span class="sxs-lookup"><span data-stu-id="71bec-282">For information about polymorphic deserialization, see [Support polymorphic deserialization](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="71bec-283">允许注释和尾随逗号</span><span class="sxs-lookup"><span data-stu-id="71bec-283">Allow comments and trailing commas</span></span>

<span data-ttu-id="71bec-284">默认情况下，JSON 中不允许使用注释和尾随逗号。</span><span class="sxs-lookup"><span data-stu-id="71bec-284">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="71bec-285">若要允许 JSON 中的注释，请将 <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> 属性设置为 `JsonCommentHandling.Skip`。</span><span class="sxs-lookup"><span data-stu-id="71bec-285">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span> <span data-ttu-id="71bec-286">若要允许尾随逗号，请将 <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="71bec-286">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="71bec-287">下面的示例演示如何允许两种方法：</span><span class="sxs-lookup"><span data-stu-id="71bec-287">The following example shows how to allow both:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="71bec-288">下面是包含注释和尾随逗号的示例 JSON：</span><span class="sxs-lookup"><span data-stu-id="71bec-288">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="71bec-289">不区分大小写的属性匹配</span><span class="sxs-lookup"><span data-stu-id="71bec-289">Case-insensitive property matching</span></span>

<span data-ttu-id="71bec-290">默认情况下，反序列化将查找 JSON 与目标对象属性之间区分大小写的属性名称匹配。</span><span class="sxs-lookup"><span data-stu-id="71bec-290">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="71bec-291">若要更改此行为，请将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> 设置为 `true`：</span><span class="sxs-lookup"><span data-stu-id="71bec-291">To change that behavior, set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

<span data-ttu-id="71bec-292">下面是采用 camel 大小写属性名称的示例 JSON。</span><span class="sxs-lookup"><span data-stu-id="71bec-292">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="71bec-293">它可以反序列化为具有 Pascal 大小写属性名称的以下类型。</span><span class="sxs-lookup"><span data-stu-id="71bec-293">It can be deserialized into the following type that has Pascal case property names.</span></span>

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

## <a name="handle-overflow-json"></a><span data-ttu-id="71bec-294">句柄溢出 JSON</span><span class="sxs-lookup"><span data-stu-id="71bec-294">Handle overflow JSON</span></span>

<span data-ttu-id="71bec-295">反序列化时，可能会收到 JSON 中的数据，该数据不是由目标类型的属性表示的。</span><span class="sxs-lookup"><span data-stu-id="71bec-295">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="71bec-296">例如，假设目标类型为：</span><span class="sxs-lookup"><span data-stu-id="71bec-296">For example, suppose your target type is this:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="71bec-297">要反序列化的 JSON 如下：</span><span class="sxs-lookup"><span data-stu-id="71bec-297">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="71bec-298">如果将显示的 JSON 反序列化为显示的类型，则 "`DatesAvailable`" 和 "`SummaryWords`" 属性不会有任何位置，并且将丢失。</span><span class="sxs-lookup"><span data-stu-id="71bec-298">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="71bec-299">若要捕获额外数据（如这些属性），请将[JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute)特性应用到类型 `Dictionary<string,object>` 或 `Dictionary<string,JsonElement>`的属性：</span><span class="sxs-lookup"><span data-stu-id="71bec-299">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

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

<span data-ttu-id="71bec-300">反序列化前面显示的此示例类型的 JSON 时，额外的数据将成为 `ExtensionData` 属性的键值对：</span><span class="sxs-lookup"><span data-stu-id="71bec-300">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="71bec-301">Property</span><span class="sxs-lookup"><span data-stu-id="71bec-301">Property</span></span> |<span data-ttu-id="71bec-302">“值”</span><span class="sxs-lookup"><span data-stu-id="71bec-302">Value</span></span>  |<span data-ttu-id="71bec-303">注意</span><span class="sxs-lookup"><span data-stu-id="71bec-303">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="71bec-304">日期</span><span class="sxs-lookup"><span data-stu-id="71bec-304">Date</span></span>    | <span data-ttu-id="71bec-305">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="71bec-305">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="71bec-306">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="71bec-306">TemperatureC</span></span>| <span data-ttu-id="71bec-307">0</span><span class="sxs-lookup"><span data-stu-id="71bec-307">0</span></span> | <span data-ttu-id="71bec-308">区分大小写不匹配（`temperatureC` 在 JSON 中），因此未设置属性。</span><span class="sxs-lookup"><span data-stu-id="71bec-308">Case-sensitive mismatch (`temperatureC` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="71bec-309">总结</span><span class="sxs-lookup"><span data-stu-id="71bec-309">Summary</span></span> | <span data-ttu-id="71bec-310">修复</span><span class="sxs-lookup"><span data-stu-id="71bec-310">Hot</span></span> ||
| <span data-ttu-id="71bec-311">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="71bec-311">ExtensionData</span></span> | <span data-ttu-id="71bec-312">temperatureC：25</span><span class="sxs-lookup"><span data-stu-id="71bec-312">temperatureC: 25</span></span> |<span data-ttu-id="71bec-313">由于大小写不匹配，因此此 JSON 属性是一个额外的，并成为字典中的键值对。</span><span class="sxs-lookup"><span data-stu-id="71bec-313">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="71bec-314">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="71bec-314">DatesAvailable:</span></span><br>  <span data-ttu-id="71bec-315">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="71bec-315">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="71bec-316">8/2/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="71bec-316">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="71bec-317">JSON 中的额外属性将成为键值对，并将数组作为值对象。</span><span class="sxs-lookup"><span data-stu-id="71bec-317">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="71bec-318">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="71bec-318">SummaryWords:</span></span><br><span data-ttu-id="71bec-319">酷</span><span class="sxs-lookup"><span data-stu-id="71bec-319">Cool</span></span><br><span data-ttu-id="71bec-320">风</span><span class="sxs-lookup"><span data-stu-id="71bec-320">Windy</span></span><br><span data-ttu-id="71bec-321">Humid</span><span class="sxs-lookup"><span data-stu-id="71bec-321">Humid</span></span> |<span data-ttu-id="71bec-322">JSON 中的额外属性将成为键值对，并将数组作为值对象。</span><span class="sxs-lookup"><span data-stu-id="71bec-322">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="71bec-323">序列化目标对象时，扩展数据键值对将成为 JSON 属性，就像它们位于传入 JSON 中一样：</span><span class="sxs-lookup"><span data-stu-id="71bec-323">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="71bec-324">请注意，`ExtensionData` 属性名称不会出现在 JSON 中。</span><span class="sxs-lookup"><span data-stu-id="71bec-324">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="71bec-325">此行为允许 JSON 进行往返，而不会丢失任何不会被反序列化的额外数据。</span><span class="sxs-lookup"><span data-stu-id="71bec-325">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="71bec-326">反序列化时忽略 null</span><span class="sxs-lookup"><span data-stu-id="71bec-326">Ignore null when deserializing</span></span>

<span data-ttu-id="71bec-327">默认情况下，如果 JSON 中的属性为 null，则目标对象中的相应属性将设置为 null。</span><span class="sxs-lookup"><span data-stu-id="71bec-327">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="71bec-328">在某些情况下，target 属性可能具有默认值，并且你不希望 null 值覆盖默认值。</span><span class="sxs-lookup"><span data-stu-id="71bec-328">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="71bec-329">例如，假设以下代码表示目标对象：</span><span class="sxs-lookup"><span data-stu-id="71bec-329">For example, suppose the following code represents your target object:</span></span>

```csharp
class WeatherForecastWithDefault
{
    public WeatherForecastWithDefault()
    {
        Summary = "No summary";
    }
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="71bec-330">假设反序列化以下 JSON：</span><span class="sxs-lookup"><span data-stu-id="71bec-330">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": null,
}
```

<span data-ttu-id="71bec-331">反序列化后，`WeatherForecastWithDefault` 对象的 `Summary` 属性为 null。</span><span class="sxs-lookup"><span data-stu-id="71bec-331">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="71bec-332">若要更改此行为，请将 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> 设置为 `true`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="71bec-332">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
weatherForecast = JsonSerializer.Deserialize<WeatherForecastWithDefault>(json, options);
```

<span data-ttu-id="71bec-333">利用此选项，在反序列化后，`WeatherForecastWithDefault` 对象的 `Summary` 属性是默认值 "无摘要"。</span><span class="sxs-lookup"><span data-stu-id="71bec-333">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="71bec-334">JSON 中的 Null 值仅在有效时才会被忽略。</span><span class="sxs-lookup"><span data-stu-id="71bec-334">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="71bec-335">不可以为 null 的值类型的 Null 值将导致异常。</span><span class="sxs-lookup"><span data-stu-id="71bec-335">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="71bec-336">有关详细信息，请参阅 GitHub 上的 dotnet/corefx 存储库中[不可以为 null 的值类型的问题](https://github.com/dotnet/corefx/issues/40922)。</span><span class="sxs-lookup"><span data-stu-id="71bec-336">For more information, see the [issue on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="71bec-337">Utf8JsonReader、Utf8JsonWriter 和 JsonDocument</span><span class="sxs-lookup"><span data-stu-id="71bec-337">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="71bec-338"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> 是面向 UTF-8 编码 JSON 文本的一个高性能、低分配的只进读取器，从 `ReadOnlySpan<byte>` 读取信息。</span><span class="sxs-lookup"><span data-stu-id="71bec-338"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="71bec-339">`Utf8JsonReader` 是可用于生成自定义分析程序和反的低级别类型。</span><span class="sxs-lookup"><span data-stu-id="71bec-339">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="71bec-340"><xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 方法使用 `Utf8JsonReader` 的内容。</span><span class="sxs-lookup"><span data-stu-id="71bec-340">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="71bec-341"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> 是一种高性能的方式，用于从常见的 .NET 类型（如 `String`、`Int32`和 `DateTime`）编写 UTF-8 编码的 JSON 文本。</span><span class="sxs-lookup"><span data-stu-id="71bec-341"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="71bec-342">编写器是可用于生成自定义序列化程序的低级别类型。</span><span class="sxs-lookup"><span data-stu-id="71bec-342">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="71bec-343"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 方法使用 `Utf8JsonWriter` 的内容。</span><span class="sxs-lookup"><span data-stu-id="71bec-343">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="71bec-344"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> 提供使用 `Utf8JsonReader`生成只读文档对象模型（DOM）的功能。</span><span class="sxs-lookup"><span data-stu-id="71bec-344"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="71bec-345">DOM 提供对 JSON 有效负载中的数据的随机访问。</span><span class="sxs-lookup"><span data-stu-id="71bec-345">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="71bec-346">可以通过 <xref:System.Text.Json.JsonElement> 类型访问构成有效负载的 JSON 元素。</span><span class="sxs-lookup"><span data-stu-id="71bec-346">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="71bec-347">`JsonElement` 提供数组和对象枚举器，以及用于将 JSON 文本转换为常见 .NET 类型的 Api。</span><span class="sxs-lookup"><span data-stu-id="71bec-347">The `JsonElement` provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="71bec-348">`JsonDocument` 公开 <xref:System.Text.Json.JsonDocument.RootElement> 属性。</span><span class="sxs-lookup"><span data-stu-id="71bec-348">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="71bec-349">以下部分说明了如何使用这些工具来读取和写入 JSON。</span><span class="sxs-lookup"><span data-stu-id="71bec-349">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="71bec-350">使用 JsonDocument 访问数据</span><span class="sxs-lookup"><span data-stu-id="71bec-350">Use JsonDocument for access to data</span></span>

<span data-ttu-id="71bec-351">下面的示例演示如何使用 <xref:System.Text.Json.JsonDocument> 类来随机访问数据：</span><span class="sxs-lookup"><span data-stu-id="71bec-351">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data:</span></span>

```csharp
double sum = 0;
int count = 0;

using (JsonDocument document = JsonDocument.Parse(jsonString))
{
    JsonElement root = document.RootElement;
    JsonElement studentsElement = root.GetProperty("Students");
    foreach (JsonElement student in studentsElement.EnumerateArray())
    {
        if (student.TryGetProperty("Grade", out JsonElement gradeElement))
        {
            sum += gradeElement.GetDouble();
        }
        else
        {
            sum += 70;
        }
        count++;
    }
}

double average = sum / count;
Console.WriteLine($"Average grade: {average}");
```

<span data-ttu-id="71bec-352">前面的代码：</span><span class="sxs-lookup"><span data-stu-id="71bec-352">The preceding code:</span></span>

* <span data-ttu-id="71bec-353">假定 JSON 要分析的字符串中有一个名为 `jsonString`。</span><span class="sxs-lookup"><span data-stu-id="71bec-353">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="71bec-354">计算 `Students` 数组中具有 `Grade` 属性的对象的平均评分。</span><span class="sxs-lookup"><span data-stu-id="71bec-354">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span> 
* <span data-ttu-id="71bec-355">为没有成绩的学生分配默认等级70。</span><span class="sxs-lookup"><span data-stu-id="71bec-355">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="71bec-356">通过每次迭代增加 `count` 变量来对学生进行计数。</span><span class="sxs-lookup"><span data-stu-id="71bec-356">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="71bec-357">一种替代方法是调用 <xref:System.Text.Json.JsonElement.GetArrayLength%2A>：</span><span class="sxs-lookup"><span data-stu-id="71bec-357">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>:</span></span>

  ```csharp
  count = studentsElement.GetArrayLength();
  ```

<span data-ttu-id="71bec-358">下面是此代码处理的 JSON 示例：</span><span class="sxs-lookup"><span data-stu-id="71bec-358">Here's an example of the JSON that this code processes:</span></span>

```json
{
  "Class Name": "Science",
  "Teacher's Name": "Jane",
  "Semester": "2019-01-01",
  "Students": [
    {
      "Name": "John",
      "Grade": 94.3
    },
    {
      "Name": "James",
      "Grade": 81.0
    },
    {
      "Name": "Julia",
      "Grade": 91.9
    },
    {
      "Name": "Jessica",
      "Grade": 72.4
    },
    {
      "Name": "Johnathan"
    }
  ],
  "Final": true
}
```

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="71bec-359">使用 JsonDocument 编写 JSON</span><span class="sxs-lookup"><span data-stu-id="71bec-359">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="71bec-360">下面的示例演示如何从 <xref:System.Text.Json.JsonDocument>编写 JSON：</span><span class="sxs-lookup"><span data-stu-id="71bec-360">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

```csharp
string jsonString = File.ReadAllText(inputFileName);

var writerOptions = new JsonWriterOptions { Indented = true };
var documentOptions = new JsonDocumentOptions { CommentHandling = JsonCommentHandling.Skip };

using (FileStream fs = File.Create(outputFileName))
using (var writer = new Utf8JsonWriter(fs, options: writerOptions))
using (JsonDocument document = JsonDocument.Parse(jsonString, documentOptions))
{
    JsonElement root = document.RootElement;

    if (root.ValueKind == JsonValueKind.Object)
    {
        writer.WriteStartObject();
    }
    else
    {
        return;
    }

    foreach (JsonProperty property in root.EnumerateObject())
    {
        property.WriteTo(writer);
    }

    writer.WriteEndObject();

    writer.Flush();
}
```

<span data-ttu-id="71bec-361">前面的代码：</span><span class="sxs-lookup"><span data-stu-id="71bec-361">The preceding code:</span></span>

* <span data-ttu-id="71bec-362">读取 JSON 文件，将数据加载到 `JsonDocument`，并将格式化（整齐打印的） JSON 写入文件。</span><span class="sxs-lookup"><span data-stu-id="71bec-362">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="71bec-363">使用 <xref:System.Text.Json.JsonDocumentOptions> 指定允许但忽略输入 JSON 中的注释。</span><span class="sxs-lookup"><span data-stu-id="71bec-363">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="71bec-364">完成后，将对编写器调用 <xref:System.Text.Json.Utf8JsonWriter.Flush%2A>。</span><span class="sxs-lookup"><span data-stu-id="71bec-364">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="71bec-365">一种替代方法是让编写人员在 autoflush 时进行处理。</span><span class="sxs-lookup"><span data-stu-id="71bec-365">An alternative is to let the writer autoflush when it's disposed.</span></span> 

<span data-ttu-id="71bec-366">下面是示例代码处理的 JSON 输入的示例：</span><span class="sxs-lookup"><span data-stu-id="71bec-366">Here's an example of JSON input to be processed by the example code:</span></span>

```json
{"Class Name": "Science","Teacher's Name": "Jane","Semester": "2019-01-01","Students": [{"Name": "John","Grade": 94.3},{"Name": "James","Grade": 81.0},{"Name": "Julia","Grade": 91.9},{"Name": "Jessica","Grade": 72.4},{"Name": "Johnathan"}],"Final": true}
```

<span data-ttu-id="71bec-367">结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="71bec-367">The result is the following pretty-printed JSON output:</span></span>

```json
{
  "Class Name": "Science",
  "Teacher\u0027s Name": "Jane",
  "Semester": "2019-01-01",
  "Students": [
    {
      "Name": "John",
      "Grade": 94.3
    },
    {
      "Name": "James",
      "Grade": 81.0
    },
    {
      "Name": "Julia",
      "Grade": 91.9
    },
    {
      "Name": "Jessica",
      "Grade": 72.4
    },
    {
      "Name": "Johnathan"
    }
  ],
  "Final": true
}
```

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="71bec-368">使用 Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="71bec-368">Use Utf8JsonWriter</span></span>

<span data-ttu-id="71bec-369">下面的示例演示如何使用 <xref:System.Text.Json.Utf8JsonWriter> 类：</span><span class="sxs-lookup"><span data-stu-id="71bec-369">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

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

## <a name="use-utf8jsonreader"></a><span data-ttu-id="71bec-370">使用 Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="71bec-370">Use Utf8JsonReader</span></span>

<span data-ttu-id="71bec-371">下面的示例演示如何使用 <xref:System.Text.Json.Utf8JsonReader> 类：</span><span class="sxs-lookup"><span data-stu-id="71bec-371">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

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

<span data-ttu-id="71bec-372">前面的代码假定 `jsonUtf8` 变量是包含有效 JSON 的字节数组，编码为 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="71bec-372">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="71bec-373">使用 Utf8JsonReader 筛选数据</span><span class="sxs-lookup"><span data-stu-id="71bec-373">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="71bec-374">下面的示例演示如何同步读取文件并搜索值：</span><span class="sxs-lookup"><span data-stu-id="71bec-374">The following example shows how to read a file synchronously and search for a value:</span></span>

```csharp
class Program
{
    private static readonly byte[] s_nameUtf8 = Encoding.UTF8.GetBytes("name");
    private static readonly byte[] s_universityUtf8 = Encoding.UTF8.GetBytes("University");

    private static void ReaderFromFileSync(string fileName)
    {
         string jsonString = File.ReadAllText(fileName);
         ReadOnlySpan<byte> jsonReadOnlySpan = Encoding.UTF8.GetBytes(jsonString);

        int count = 0;
        int total = 0;

        var json = new Utf8JsonReader(jsonReadOnlySpan, isFinalBlock: true, state: default);

        while (json.Read())
        {
            JsonTokenType tokenType = json.TokenType;

            switch (tokenType)
            {
                case JsonTokenType.StartObject:
                    total++;
                    break;
                case JsonTokenType.PropertyName:
                    if (json.ValueSpan.SequenceEqual(s_nameUtf8))
                    {
                        bool result = json.Read();

                        Debug.Assert(result);  // Assume valid JSON
                        Debug.Assert(json.TokenType == JsonTokenType.String);   // Assume known, valid JSON schema

                        if (json.ValueSpan.EndsWith(s_universityUtf8))
                        {
                            count++;
                        }
                    }
                    break;
            }
        }
        Console.WriteLine($"{count} out of {total} have names that end with 'University'");
    }
}
```

<span data-ttu-id="71bec-375">前面的代码：</span><span class="sxs-lookup"><span data-stu-id="71bec-375">The preceding code:</span></span>

* <span data-ttu-id="71bec-376">假定文件编码为 UTF-16，并将其转码为 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="71bec-376">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="71bec-377">可以通过使用以下代码，将编码为 UTF-8 的文件直接读入 `ReadOnlySpan<byte>`：</span><span class="sxs-lookup"><span data-stu-id="71bec-377">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

* <span data-ttu-id="71bec-378">假定 JSON 包含一个对象数组，并且每个对象可能包含一个字符串类型的 "name" 属性。</span><span class="sxs-lookup"><span data-stu-id="71bec-378">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="71bec-379">计算以 "大学" 结尾的对象和 `name` 属性值。</span><span class="sxs-lookup"><span data-stu-id="71bec-379">Counts objects and `name` property values that end with "University".</span></span>

<span data-ttu-id="71bec-380">下面是前面的代码可以读取的 JSON 示例。</span><span class="sxs-lookup"><span data-stu-id="71bec-380">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="71bec-381">生成的摘要消息为 "2 个，共4个名称以 ' 大学 ' 结尾"：</span><span class="sxs-lookup"><span data-stu-id="71bec-381">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

```json
[
  {
    "web_pages": [ "https://contoso.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "contoso.edu" ],
    "name": "Contoso Community College"
  },
  {
    "web_pages": [ "http://fabrikam.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "fabrikam.edu" ],
    "name": "Fabrikam Community College"
  },
  {
    "web_pages": [ "http://www.contosouniversity.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "contosouniversity.edu" ],
    "name": "Contoso University"
  },
  {
    "web_pages": [ "http://www.fabrikamuniversity.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "fabrikamuniversity.edu" ],
    "name": "Fabrikam University"
  }
]
```

## <a name="additional-resources"></a><span data-ttu-id="71bec-382">其他资源</span><span class="sxs-lookup"><span data-stu-id="71bec-382">Additional resources</span></span>

* [<span data-ttu-id="71bec-383">System.web 概述</span><span class="sxs-lookup"><span data-stu-id="71bec-383">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="71bec-384">System.web API 参考</span><span class="sxs-lookup"><span data-stu-id="71bec-384">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="71bec-385">为 system.exception 编写自定义转换器</span><span class="sxs-lookup"><span data-stu-id="71bec-385">Write custom converters for System.Text.Json</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="71bec-386">系统中的 DateTime 和 DateTimeOffset 支持</span><span class="sxs-lookup"><span data-stu-id="71bec-386">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
