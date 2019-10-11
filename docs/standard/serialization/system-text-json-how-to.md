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
# <a name="how-to-serialize-and-deserialize-json-in-net"></a><span data-ttu-id="c2ff3-102">如何在 .NET 中对 JSON 进行序列化和反序列化</span><span class="sxs-lookup"><span data-stu-id="c2ff3-102">How to serialize and deserialize JSON in .NET</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2ff3-103">JSON 序列化文档正在构造。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-103">The JSON serialization documentation is under construction.</span></span> <span data-ttu-id="c2ff3-104">本文不介绍所有方案。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-104">This article doesn't cover all scenarios.</span></span> <span data-ttu-id="c2ff3-105">有关详细信息，请查看 GitHub 上的 dotnet/corefx 存储库中的[system.web 问题](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)，尤其是标记为[Json 功能的文档](https://github.com/dotnet/corefx/labels/json-functionality-doc)。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-105">For more information, examine [System.Text.Json issues](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) in the dotnet/corefx repository on GitHub, especially those labeled [json-functionality-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span></span>

<span data-ttu-id="c2ff3-106">本文介绍如何使用 <xref:System.Text.Json> 命名空间在 JavaScript 对象表示法（JSON）之间进行序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-106">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="c2ff3-107">方向和示例代码直接使用库，而不是通过框架（如[ASP.NET Core](/aspnet/core/)）使用。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

## <a name="namespaces"></a><span data-ttu-id="c2ff3-108">命名空间</span><span class="sxs-lookup"><span data-stu-id="c2ff3-108">Namespaces</span></span>

<span data-ttu-id="c2ff3-109">@No__t 的命名空间包含所有入口点和主要类型。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-109">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="c2ff3-110">@No__t 的命名空间包含用于高级方案的属性和 Api，以及特定于序列化和反序列化的自定义。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-110">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="c2ff3-111">因此，本文中所示的代码示例需要以下一项或两项 `using` 指令：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-111">Therefore, the code examples shown in this article require one or both of the following `using` directives:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="c2ff3-112">@No__t 中当前不支持 @no__t 命名空间中的属性。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-112">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="c2ff3-113">如何将 .NET 对象写入 JSON （序列化）</span><span class="sxs-lookup"><span data-stu-id="c2ff3-113">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="c2ff3-114">若要将 JSON 写入字符串，请调用 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-114">To write JSON to a string, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c2ff3-115">下面的示例使用具有泛型类型参数的重载：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-115">The following example uses an overload with a generic type parameter:</span></span>

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="c2ff3-116">您可以省略泛型类型参数并改用泛型类型推理：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-116">You can omit the generic type parameter and use generic type inference instead:</span></span>

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="c2ff3-117">下面是要进行序列化的示例类型，其中包含集合和嵌套类：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-117">Here's an example type to be serialized, which contains collections and nested classes:</span></span>

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

<span data-ttu-id="c2ff3-118">默认情况下，JSON 输出为缩小：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-118">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="c2ff3-119">下面的示例演示了相同的 JSON 格式（也就是用空格和缩进进行整齐打印）：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-119">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

<span data-ttu-id="c2ff3-120">@No__t 的重载允许您序列化到 @no__t 1。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-120">Overloads of <xref:System.Text.Json.JsonSerializer.Serialize%2A> let you serialize to a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="c2ff3-121">@No__t-0 重载的异步版本可用。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-121">Async versions of the `Stream` overloads are available.</span></span>

### <a name="serialize-to-utf-8"></a><span data-ttu-id="c2ff3-122">序列化为 UTF-8</span><span class="sxs-lookup"><span data-stu-id="c2ff3-122">Serialize to UTF-8</span></span>

<span data-ttu-id="c2ff3-123">若要序列化为 UTF-8，请调用 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 方法：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-123">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

```csharp
byte[] utf8Json = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="c2ff3-124">作为替代方法，可以使用 @no__t 为-1 的 @no__t 0 重载。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-124">As an alternative, a <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is available.</span></span>

<span data-ttu-id="c2ff3-125">序列化为 UTF-8 比使用基于字符串的方法更快 5-10%。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-125">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="c2ff3-126">不同之处在于，不需要将字节（如 UTF-8）转换为字符串（UTF-16）。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-126">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="c2ff3-127">序列化行为</span><span class="sxs-lookup"><span data-stu-id="c2ff3-127">Serialization behavior</span></span>

* <span data-ttu-id="c2ff3-128">默认情况下，将序列化所有公共属性。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-128">By default, all public properties are serialized.</span></span> <span data-ttu-id="c2ff3-129">您可以[指定要排除的属性](#exclude-properties)。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-129">You can [specify properties to exclude](#exclude-properties).</span></span>
* <span data-ttu-id="c2ff3-130">[默认编码器](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)会转义非 ascii 字符、ASCII 范围内的 HTML 敏感字符以及必须根据[JSON 规范](https://tools.ietf.org/html/rfc8259#section-7)进行转义的字符。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-130">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="c2ff3-131">默认情况下，JSON 为缩小。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-131">By default, JSON is minified.</span></span> <span data-ttu-id="c2ff3-132">可以很好[打印 JSON](#serialize-to-formatted-json)。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-132">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="c2ff3-133">默认情况下，JSON 名称的大小写与 .NET 名称匹配。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-133">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="c2ff3-134">你可以[自定义 JSON 名称大小写](#customize-json-names)。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-134">You can [customize JSON name casing](#customize-json-names).</span></span>
* <span data-ttu-id="c2ff3-135">检测到循环引用并引发异常。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-135">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="c2ff3-136">有关详细信息，请参阅 GitHub 上的 dotnet/corefx 存储库中的[循环引用问题](https://github.com/dotnet/corefx/issues/38579)。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-136">For more information, see the [issue on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="c2ff3-137">当前排除了字段。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-137">Currently, fields are excluded.</span></span>

<span data-ttu-id="c2ff3-138">支持的类型包括：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-138">Supported types include:</span></span>

* <span data-ttu-id="c2ff3-139">映射到 JavaScript 基元的 .NET 基元，如数值类型、字符串和布尔值。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-139">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="c2ff3-140">用户定义的[普通旧 CLR 对象（poco）](https://stackoverflow.com/questions/250001/poco-definition)。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-140">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="c2ff3-141">一维数组和交错数组（`ArrayName[][]`）。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-141">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="c2ff3-142">`Dictionary<string,TValue>`，其中 `TValue` 是 `object`、`JsonElement` 还是 POCO。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-142">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="c2ff3-143">以下命名空间中的集合。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-143">Collections from the following namespaces.</span></span> <span data-ttu-id="c2ff3-144">有关详细信息，请参阅 GitHub 上的 dotnet/corefx 存储库中的[收集支持问题](https://github.com/dotnet/corefx/issues/36643)。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-144">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="c2ff3-145">如何将 JSON 读入 .NET 对象（反序列化）</span><span class="sxs-lookup"><span data-stu-id="c2ff3-145">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="c2ff3-146">若要从字符串进行反序列化，请调用 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 方法，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-146">To deserialize from a string, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method, as shown in the following example:</span></span>

```csharp
string json = ... ;

var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="c2ff3-147">有关示例，请参阅[序列化](#how-to-write-net-objects-to-json-serialize)部分。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-147">For an example, see the [serialize](#how-to-write-net-objects-to-json-serialize) section.</span></span> <span data-ttu-id="c2ff3-148">JSON 和 .NET 对象是相同的，但方向反转。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-148">The JSON and .NET object are the same, but the direction is reversed.</span></span>

<span data-ttu-id="c2ff3-149">@No__t 的重载使你可以从 @no__t 进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-149">Overloads of <xref:System.Text.Json.JsonSerializer.Deserialize*> let you deserialize from a `Stream`.</span></span>  <span data-ttu-id="c2ff3-150">@No__t-0 重载的异步版本可用。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-150">Async versions of the `Stream` overloads are available.</span></span>

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="c2ff3-151">从 UTF-8 反序列化</span><span class="sxs-lookup"><span data-stu-id="c2ff3-151">Deserialize from UTF-8</span></span>

<span data-ttu-id="c2ff3-152">若要从 UTF-8 进行反序列化，请调用采用 @no__t 或 @no__t 的 @no__t 0 重载，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-152">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples:</span></span>

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

## <a name="deserialization-behavior"></a><span data-ttu-id="c2ff3-153">反序列化行为</span><span class="sxs-lookup"><span data-stu-id="c2ff3-153">Deserialization behavior</span></span>

* <span data-ttu-id="c2ff3-154">默认情况下，属性名称匹配区分大小写。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-154">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="c2ff3-155">可以[指定不区分大小写](#case-insensitive-property-matching)。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-155">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="c2ff3-156">如果 JSON 包含只读属性的值，则该值将被忽略，并且不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-156">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="c2ff3-157">不支持反序列化到不具有无参数构造函数的引用类型。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-157">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="c2ff3-158">不支持对不可变对象或只读属性进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-158">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="c2ff3-159">有关详细信息，请参阅 github 上的 dotnet/corefx 存储库中对[不可变对象支持](https://github.com/dotnet/corefx/issues/38569)的 GitHub 问题和对[只读属性的支持问题](https://github.com/dotnet/corefx/issues/38163)。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-159">For more information, see the GitHub [issue on immutable object support](https://github.com/dotnet/corefx/issues/38569) and the [issue on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="c2ff3-160">默认情况下，枚举作为数字支持。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-160">By default, enums are supported as numbers.</span></span>
* <span data-ttu-id="c2ff3-161">不支持字段。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-161">Fields aren't supported.</span></span>
* <span data-ttu-id="c2ff3-162">默认情况下，JSON 中的注释或尾随逗号引发异常。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-162">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="c2ff3-163">如果需要[，可以允许注释和尾随逗号](#allow-comments-and-trailing-commas)。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-163">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas) if needed.</span></span>
* <span data-ttu-id="c2ff3-164">[默认的最大深度](xref:System.Text.Json.JsonReaderOptions.MaxDepth)为64。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-164">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="c2ff3-165">序列化为格式化的 JSON</span><span class="sxs-lookup"><span data-stu-id="c2ff3-165">Serialize to formatted JSON</span></span>

<span data-ttu-id="c2ff3-166">若要整齐地打印 JSON 输出，请将 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> 设置为 `true`：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-166">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="c2ff3-167">下面是要序列化的示例类型和 JSON 输出：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-167">Here's an example type to be serialized and JSON output:</span></span>

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

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="c2ff3-168">允许注释和尾随逗号</span><span class="sxs-lookup"><span data-stu-id="c2ff3-168">Allow comments and trailing commas</span></span>

<span data-ttu-id="c2ff3-169">默认情况下，JSON 中不允许使用注释和尾随逗号。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-169">By default comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="c2ff3-170">若要允许 JSON 中的注释，请将 <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> 属性设置为 `JsonCommentHandling.Skip`。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-170">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span> <span data-ttu-id="c2ff3-171">若要允许尾随逗号，请将 <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-171">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="c2ff3-172">下面的示例演示如何允许两种方法：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-172">The following example shows how to allow both:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="c2ff3-173">下面是包含注释和尾随逗号的示例 JSON：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-173">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="customize-json-names"></a><span data-ttu-id="c2ff3-174">自定义 JSON 名称</span><span class="sxs-lookup"><span data-stu-id="c2ff3-174">Customize JSON names</span></span>

<span data-ttu-id="c2ff3-175">默认情况下，JSON 输出中的属性名称和字典键不变，包括大小写。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-175">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="c2ff3-176">本部分介绍如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-176">This section explains how to:</span></span>

* <span data-ttu-id="c2ff3-177">自定义各个属性名称</span><span class="sxs-lookup"><span data-stu-id="c2ff3-177">Customize individual property names</span></span>
* <span data-ttu-id="c2ff3-178">将所有属性名称转换为 camel 大小写</span><span class="sxs-lookup"><span data-stu-id="c2ff3-178">Convert all property names to camel case</span></span>
* <span data-ttu-id="c2ff3-179">实现自定义属性命名策略</span><span class="sxs-lookup"><span data-stu-id="c2ff3-179">Implement a custom property naming policy</span></span>
* <span data-ttu-id="c2ff3-180">将字典键转换为 camel 大小写</span><span class="sxs-lookup"><span data-stu-id="c2ff3-180">Convert dictionary keys to camel case</span></span>

<span data-ttu-id="c2ff3-181">目前，不支持将枚举自动转换为 camel 大小写。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-181">Currently, there's no support for automatically converting enums to camel case.</span></span> <span data-ttu-id="c2ff3-182">有关详细信息，请参阅 GitHub 上的 dotnet/corefx 存储库中的[枚举 camel 大小写支持问题](https://github.com/dotnet/corefx/issues/37725)。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-182">For more information, see the [issue on enum camel case support](https://github.com/dotnet/corefx/issues/37725) in the dotnet/corefx repository on GitHub.</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="c2ff3-183">自定义各个属性名称</span><span class="sxs-lookup"><span data-stu-id="c2ff3-183">Customize individual property names</span></span>

<span data-ttu-id="c2ff3-184">若要设置单个属性的名称，请使用[[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute)属性。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-184">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="c2ff3-185">下面是序列化和生成的 JSON 的示例类型：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-185">Here's an example type to serialize and resulting JSON:</span></span>

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

<span data-ttu-id="c2ff3-186">此属性设置的属性名称：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-186">The property name set by this attribute:</span></span>

* <span data-ttu-id="c2ff3-187">同时适用于序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-187">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="c2ff3-188">优先于属性命名策略。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-188">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="c2ff3-189">对所有 JSON 属性名称使用 camel 大小写</span><span class="sxs-lookup"><span data-stu-id="c2ff3-189">Use camel case for all JSON property names</span></span>

<span data-ttu-id="c2ff3-190">若要对所有 JSON 属性名称使用 camel 大小写，请将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 设置为 `JsonNamingPolicy.CamelCase`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-190">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="c2ff3-191">下面是一个用于序列化和 JSON 输出的示例类：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-191">Here's an example class to serialize and JSON output:</span></span>

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

<span data-ttu-id="c2ff3-192">Camel 大小写属性命名策略：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-192">The camel case property naming policy:</span></span>

* <span data-ttu-id="c2ff3-193">适用于序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-193">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="c2ff3-194">由 `[JsonPropertyName]` 特性重写。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-194">Is overridden by `[JsonPropertyName]` attributes.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="c2ff3-195">使用自定义 JSON 属性命名策略</span><span class="sxs-lookup"><span data-stu-id="c2ff3-195">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="c2ff3-196">若要使用自定义 JSON 属性命名策略，请创建一个派生自 @no__t 0 的类，并重写 <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> 方法，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-196">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

<span data-ttu-id="c2ff3-197">然后，将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 属性设置为命名策略类的实例：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-197">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="c2ff3-198">下面是一个用于序列化和 JSON 输出的示例类：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-198">Here's an example class to serialize and JSON output:</span></span>

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

<span data-ttu-id="c2ff3-199">JSON 属性命名策略：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-199">The JSON property naming policy:</span></span>

* <span data-ttu-id="c2ff3-200">适用于序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-200">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="c2ff3-201">由 `[JsonPropertyName]` 特性重写。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-201">Is overridden by `[JsonPropertyName]` attributes.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="c2ff3-202">Camel 大小写字典密钥</span><span class="sxs-lookup"><span data-stu-id="c2ff3-202">Camel case dictionary keys</span></span>

<span data-ttu-id="c2ff3-203">如果要序列化的对象的属性的类型为 `Dictionary<string,TValue>`，则可以将 @no__t 键转换为 camel 大小写形式。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-203">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="c2ff3-204">为此，请将 @no__t 设置为 `JsonNamingPolicy.CamelCase`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-204">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="c2ff3-205">下面是一个示例对象，用于序列化和 JSON 输出：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-205">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="c2ff3-206">属性</span><span class="sxs-lookup"><span data-stu-id="c2ff3-206">Property</span></span> |<span data-ttu-id="c2ff3-207">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="c2ff3-207">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="c2ff3-208">Date</span><span class="sxs-lookup"><span data-stu-id="c2ff3-208">Date</span></span>    | <span data-ttu-id="c2ff3-209">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="c2ff3-209">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="c2ff3-210">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="c2ff3-210">TemperatureC</span></span>| <span data-ttu-id="c2ff3-211">25</span><span class="sxs-lookup"><span data-stu-id="c2ff3-211">25</span></span> |
| <span data-ttu-id="c2ff3-212">总结</span><span class="sxs-lookup"><span data-stu-id="c2ff3-212">Summary</span></span>| <span data-ttu-id="c2ff3-213">修复</span><span class="sxs-lookup"><span data-stu-id="c2ff3-213">Hot</span></span>|
| <span data-ttu-id="c2ff3-214">TemperatureRanges</span><span class="sxs-lookup"><span data-stu-id="c2ff3-214">TemperatureRanges</span></span> | <span data-ttu-id="c2ff3-215">冷，20</span><span class="sxs-lookup"><span data-stu-id="c2ff3-215">Cold, 20</span></span><br><span data-ttu-id="c2ff3-216">热，40</span><span class="sxs-lookup"><span data-stu-id="c2ff3-216">Hot, 40</span></span>|

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

<span data-ttu-id="c2ff3-217">Camel 大小写命名策略仅适用于序列化。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-217">The camel case naming policy applies to serialization only.</span></span>

## <a name="exclude-properties"></a><span data-ttu-id="c2ff3-218">排除属性</span><span class="sxs-lookup"><span data-stu-id="c2ff3-218">Exclude properties</span></span>

<span data-ttu-id="c2ff3-219">默认情况下，将序列化所有公共属性。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-219">By default, all public properties are serialized.</span></span> <span data-ttu-id="c2ff3-220">如果你不想让某些用户出现在 JSON 输出中，则可以使用几个选项。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-220">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="c2ff3-221">本部分介绍如何排除：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-221">This section explains how to exclude:</span></span>

* <span data-ttu-id="c2ff3-222">单个属性</span><span class="sxs-lookup"><span data-stu-id="c2ff3-222">Individual properties</span></span>
* <span data-ttu-id="c2ff3-223">所有只读属性</span><span class="sxs-lookup"><span data-stu-id="c2ff3-223">All read-only properties</span></span>
* <span data-ttu-id="c2ff3-224">所有 null 值属性</span><span class="sxs-lookup"><span data-stu-id="c2ff3-224">All null-value properties</span></span> 

### <a name="exclude-individual-properties"></a><span data-ttu-id="c2ff3-225">排除单个属性</span><span class="sxs-lookup"><span data-stu-id="c2ff3-225">Exclude individual properties</span></span>

<span data-ttu-id="c2ff3-226">若要忽略各个属性，请使用[[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute)属性。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-226">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="c2ff3-227">下面是要序列化的示例类型和 JSON 输出：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-227">Here's an example type to serialize and JSON output:</span></span>

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

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="c2ff3-228">排除所有只读属性</span><span class="sxs-lookup"><span data-stu-id="c2ff3-228">Exclude all read-only properties</span></span>

<span data-ttu-id="c2ff3-229">若要排除所有只读属性，请将 @no__t 设置为 `true`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-229">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="c2ff3-230">下面是要序列化的示例类型和 JSON 输出：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-230">Here's an example type to serialize and JSON output:</span></span>

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

<span data-ttu-id="c2ff3-231">此选项仅适用于序列化。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-231">This option applies only to serialization.</span></span> <span data-ttu-id="c2ff3-232">在反序列化期间，默认情况下将忽略只读属性。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-232">During deserialization, read-only properties are ignored by default.</span></span> <span data-ttu-id="c2ff3-233">如果属性包含公共 getter 而不是公共 setter，则该属性为只读。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-233">A property is read-only if it contains a public getter but not a public setter.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="c2ff3-234">排除所有 null 值属性</span><span class="sxs-lookup"><span data-stu-id="c2ff3-234">Exclude all null value properties</span></span>

<span data-ttu-id="c2ff3-235">若要排除所有 null 值属性，请将 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> 属性设置为 `true`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-235">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="c2ff3-236">下面是一个示例对象，用于序列化和 JSON 输出：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-236">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="c2ff3-237">属性</span><span class="sxs-lookup"><span data-stu-id="c2ff3-237">Property</span></span> |<span data-ttu-id="c2ff3-238">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="c2ff3-238">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="c2ff3-239">Date</span><span class="sxs-lookup"><span data-stu-id="c2ff3-239">Date</span></span>    | <span data-ttu-id="c2ff3-240">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="c2ff3-240">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="c2ff3-241">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="c2ff3-241">TemperatureC</span></span>| <span data-ttu-id="c2ff3-242">25</span><span class="sxs-lookup"><span data-stu-id="c2ff3-242">25</span></span> |
| <span data-ttu-id="c2ff3-243">总结</span><span class="sxs-lookup"><span data-stu-id="c2ff3-243">Summary</span></span>| <span data-ttu-id="c2ff3-244">null</span><span class="sxs-lookup"><span data-stu-id="c2ff3-244">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

<span data-ttu-id="c2ff3-245">此设置适用于序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-245">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="c2ff3-246">在反序列化过程中，仅当 JSON 中的 null 值有效时才会将其忽略。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-246">During deserialization, null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="c2ff3-247">不可以为 null 的值类型的 Null 值将导致异常。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-247">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="c2ff3-248">有关详细信息，请参阅 GitHub 上的 dotnet/corefx 存储库中[不可以为 null 的值类型的问题](https://github.com/dotnet/corefx/issues/40922)。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-248">For more information, see the [issue on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="c2ff3-249">不区分大小写的属性匹配</span><span class="sxs-lookup"><span data-stu-id="c2ff3-249">Case-insensitive property matching</span></span>

<span data-ttu-id="c2ff3-250">默认情况下，反序列化将查找 JSON 与目标对象属性之间区分大小写的属性名称匹配。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-250">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="c2ff3-251">若要更改此行为，请将 @no__t 0 设置为 `true`：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-251">To change that behavior, set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

<span data-ttu-id="c2ff3-252">下面是采用 camel 大小写属性名称的示例 JSON。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-252">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="c2ff3-253">它可以反序列化为具有 Pascal 大小写属性名称的以下类型。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-253">It can be deserialized into the following type that has Pascal case property names.</span></span>

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

## <a name="include-properties-of-derived-classes"></a><span data-ttu-id="c2ff3-254">包含派生类的属性</span><span class="sxs-lookup"><span data-stu-id="c2ff3-254">Include properties of derived classes</span></span>

<span data-ttu-id="c2ff3-255">在编译时指定要序列化的类型时，不支持多态序列化。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-255">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="c2ff3-256">例如，假设您有一个 @no__t 0 类和一个派生类 `WeatherForecastWithWind`：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-256">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

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

<span data-ttu-id="c2ff3-257">并且假设类型传递到，或由推断，在编译时 `Serialize` 方法 @no__t 为-1：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-257">And suppose the type passed to, or inferred by, the `Serialize` method at compile time is `WeatherForecast`:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

```csharp
WeatherForecast weatherForecast;
//...
json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="c2ff3-258">在这种情况下，即使 @no__t 对象实际上是 @no__t 2 对象，也不会序列化 `WindSpeed` 属性。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-258">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="c2ff3-259">仅序列化基类属性：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-259">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="c2ff3-260">此行为旨在帮助防止在派生的运行时创建的类型中发生意外的数据泄露。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-260">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="c2ff3-261">若要序列化派生类型的属性，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-261">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="c2ff3-262">调用 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 的重载，以便在运行时指定类型：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-262">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* <span data-ttu-id="c2ff3-263">将要序列化的对象声明为 `object`。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-263">Declare the object to be serialized as `object`.</span></span>

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

<span data-ttu-id="c2ff3-264">在前面的示例方案中，这两种方法都会导致在 JSON 输出中包含 `WindSpeed` 属性：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-264">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

## <a name="handle-overflow-json"></a><span data-ttu-id="c2ff3-265">句柄溢出 JSON</span><span class="sxs-lookup"><span data-stu-id="c2ff3-265">Handle overflow JSON</span></span>

<span data-ttu-id="c2ff3-266">反序列化时，可能会收到 JSON 中的数据，该数据不是由目标类型的属性表示的。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-266">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="c2ff3-267">例如，假设目标类型为：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-267">For example, suppose your target type is this:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="c2ff3-268">要反序列化的 JSON 如下：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-268">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="c2ff3-269">如果将所显示的 JSON 反序列化为显示的类型，则 @no__t 的 "0" 和 "@no__t" 属性没有任何位置，并且将丢失。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-269">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="c2ff3-270">若要捕获额外数据（如这些属性），请将[JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute)特性应用于类型 `Dictionary<string,object>` 或 `Dictionary<string,JsonElement>` 的属性：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-270">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

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

<span data-ttu-id="c2ff3-271">反序列化前面显示的此示例类型的 JSON 时，额外的数据将成为 `ExtensionData` 属性的键值对：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-271">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="c2ff3-272">属性</span><span class="sxs-lookup"><span data-stu-id="c2ff3-272">Property</span></span> |<span data-ttu-id="c2ff3-273">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="c2ff3-273">Value</span></span>  |<span data-ttu-id="c2ff3-274">说明</span><span class="sxs-lookup"><span data-stu-id="c2ff3-274">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="c2ff3-275">Date</span><span class="sxs-lookup"><span data-stu-id="c2ff3-275">Date</span></span>    | <span data-ttu-id="c2ff3-276">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="c2ff3-276">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="c2ff3-277">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="c2ff3-277">TemperatureC</span></span>| <span data-ttu-id="c2ff3-278">0</span><span class="sxs-lookup"><span data-stu-id="c2ff3-278">0</span></span> | <span data-ttu-id="c2ff3-279">区分大小写不匹配（在 JSON 中 `temperatureC`），因此未设置属性。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-279">Case-sensitive mismatch (`temperatureC` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="c2ff3-280">总结</span><span class="sxs-lookup"><span data-stu-id="c2ff3-280">Summary</span></span> | <span data-ttu-id="c2ff3-281">修复</span><span class="sxs-lookup"><span data-stu-id="c2ff3-281">Hot</span></span> ||
| <span data-ttu-id="c2ff3-282">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="c2ff3-282">ExtensionData</span></span> | <span data-ttu-id="c2ff3-283">temperatureC:25</span><span class="sxs-lookup"><span data-stu-id="c2ff3-283">temperatureC: 25</span></span> |<span data-ttu-id="c2ff3-284">由于大小写不匹配，因此此 JSON 属性是一个额外的，并成为字典中的键值对。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-284">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="c2ff3-285">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="c2ff3-285">DatesAvailable:</span></span><br>  <span data-ttu-id="c2ff3-286">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="c2ff3-286">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="c2ff3-287">8/2/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="c2ff3-287">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="c2ff3-288">JSON 中的额外属性将成为键值对，并将数组作为值对象。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-288">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="c2ff3-289">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="c2ff3-289">SummaryWords:</span></span><br><span data-ttu-id="c2ff3-290">酷</span><span class="sxs-lookup"><span data-stu-id="c2ff3-290">Cool</span></span><br><span data-ttu-id="c2ff3-291">风</span><span class="sxs-lookup"><span data-stu-id="c2ff3-291">Windy</span></span><br><span data-ttu-id="c2ff3-292">Humid</span><span class="sxs-lookup"><span data-stu-id="c2ff3-292">Humid</span></span> |<span data-ttu-id="c2ff3-293">JSON 中的额外属性将成为键值对，并将数组作为值对象。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-293">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="c2ff3-294">序列化目标对象时，扩展数据键值对将成为 JSON 属性，就像它们位于传入 JSON 中一样：</span><span class="sxs-lookup"><span data-stu-id="c2ff3-294">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="c2ff3-295">请注意，`ExtensionData` 属性名称未出现在 JSON 中。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-295">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="c2ff3-296">此行为允许 JSON 进行往返，而不会丢失任何不会被反序列化的额外数据。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-296">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="use-utf8jsonwriter-directly"></a><span data-ttu-id="c2ff3-297">直接使用 Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="c2ff3-297">Use Utf8JsonWriter directly</span></span>

<span data-ttu-id="c2ff3-298">下面的示例演示如何直接使用 @no__t 0 类。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-298">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class directly.</span></span>

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

## <a name="use-utf8jsonreader-directly"></a><span data-ttu-id="c2ff3-299">直接使用 Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="c2ff3-299">Use Utf8JsonReader directly</span></span>

<span data-ttu-id="c2ff3-300">下面的示例演示如何直接使用 @no__t 0 类。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-300">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class directly.</span></span> <span data-ttu-id="c2ff3-301">此代码假定 `jsonUtf8` 变量是包含有效 JSON 的字节数组，编码为 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="c2ff3-301">The code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="c2ff3-302">其他资源</span><span class="sxs-lookup"><span data-stu-id="c2ff3-302">Additional resources</span></span>

* [<span data-ttu-id="c2ff3-303">System.web 概述</span><span class="sxs-lookup"><span data-stu-id="c2ff3-303">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="c2ff3-304">System.web API 参考</span><span class="sxs-lookup"><span data-stu-id="c2ff3-304">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="c2ff3-305">系统中的 DateTime 和 DateTimeOffset 支持</span><span class="sxs-lookup"><span data-stu-id="c2ff3-305">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
