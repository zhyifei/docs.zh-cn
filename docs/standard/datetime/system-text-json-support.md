---
title: System.Text.Json 中的 DateTime 和 DateTimeOffset 支持
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
ms.openlocfilehash: 000a6b6dc892e65b50ae413ab3cb95d2a73ef0ef
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182571"
---
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a><span data-ttu-id="93f42-103">System.Text.Json 中的 DateTime 和 DateTimeOffset 支持</span><span class="sxs-lookup"><span data-stu-id="93f42-103">DateTime and DateTimeOffset support in System.Text.Json</span></span>

<span data-ttu-id="93f42-104">根据 ISO 8601:-2019 扩展配置文件，system.web 库分析<xref:System.DateTime>并<xref:System.DateTimeOffset>写入和值。</span><span class="sxs-lookup"><span data-stu-id="93f42-104">The System.Text.Json library parses and writes <xref:System.DateTime> and <xref:System.DateTimeOffset> values according to the ISO 8601:-2019 extended profile.</span></span>
<span data-ttu-id="93f42-105">[转换器](xref:System.Text.Json.Serialization.JsonConverter%601)为序列化和反序列<xref:System.Text.Json.JsonSerializer>化提供自定义支持。</span><span class="sxs-lookup"><span data-stu-id="93f42-105">[Converters](xref:System.Text.Json.Serialization.JsonConverter%601) provide custom support for serializing and deserializing with <xref:System.Text.Json.JsonSerializer>.</span></span>
<span data-ttu-id="93f42-106">当使用<xref:System.Text.Json.Utf8JsonReader>和时， <xref:System.Text.Json.Utf8JsonWriter>还可以实现自定义支持。</span><span class="sxs-lookup"><span data-stu-id="93f42-106">Custom support can also be implemented when using <xref:System.Text.Json.Utf8JsonReader> and <xref:System.Text.Json.Utf8JsonWriter>.</span></span>

## <a name="support-for-the-iso-8601-12019-format"></a><span data-ttu-id="93f42-107">支持 ISO 8601-1:2019 格式</span><span class="sxs-lookup"><span data-stu-id="93f42-107">Support for the ISO 8601-1:2019 format</span></span>

<span data-ttu-id="93f42-108"><xref:System.Text.Json.JsonSerializer> <xref:System.DateTime> <xref:System.DateTimeOffset> 、 、<xref:System.Text.Json.Utf8JsonReader>和类型根据ISO8601-1:2019格式的扩展配置文件分析并写入和文本表示形式;例如，2019-07-26T16<xref:System.Text.Json.JsonElement> <xref:System.Text.Json.Utf8JsonWriter>：59:57-05:00。</span><span class="sxs-lookup"><span data-stu-id="93f42-108">The <xref:System.Text.Json.JsonSerializer>, <xref:System.Text.Json.Utf8JsonReader>, <xref:System.Text.Json.Utf8JsonWriter>, and <xref:System.Text.Json.JsonElement> types parse and write <xref:System.DateTime> and <xref:System.DateTimeOffset> text representations according to the extended profile of the ISO 8601-1:2019 format; for example, 2019-07-26T16:59:57-05:00.</span></span>

<span data-ttu-id="93f42-109"><xref:System.DateTime>和<xref:System.DateTimeOffset>数据可通过以下方式<xref:System.Text.Json.JsonSerializer>序列化：</span><span class="sxs-lookup"><span data-stu-id="93f42-109"><xref:System.DateTime> and <xref:System.DateTimeOffset> data can be serialized with <xref:System.Text.Json.JsonSerializer>:</span></span>

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/csharp/serializing-with-jsonserializer/Program.cs)]

<span data-ttu-id="93f42-110">还可以通过以下方式<xref:System.Text.Json.JsonSerializer>对其进行反序列化：</span><span class="sxs-lookup"><span data-stu-id="93f42-110">They can also be deserialized with <xref:System.Text.Json.JsonSerializer>:</span></span>

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-valid/Program.cs)]

<span data-ttu-id="93f42-111">对于默认选项，输入<xref:System.DateTime>和<xref:System.DateTimeOffset>文本表示形式必须符合扩展 ISO 8601-1:2019 配置文件。</span><span class="sxs-lookup"><span data-stu-id="93f42-111">With default options, input <xref:System.DateTime> and <xref:System.DateTimeOffset> text representations must conform to the extended ISO 8601-1:2019 profile.</span></span>
<span data-ttu-id="93f42-112">尝试对不符合配置文件的表示形式进行反序列<xref:System.Text.Json.JsonSerializer>化将导致<xref:System.Text.Json.JsonException>引发：</span><span class="sxs-lookup"><span data-stu-id="93f42-112">Attempting to deserialize representations that don't conform to the profile will cause <xref:System.Text.Json.JsonSerializer> to throw a <xref:System.Text.Json.JsonException>:</span></span>

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-error/Program.cs)]

<span data-ttu-id="93f42-113">提供对 JSON 有效负载（包括<xref:System.DateTime>和<xref:System.DateTimeOffset>表示形式）内容的结构化访问。 <xref:System.Text.Json.JsonDocument></span><span class="sxs-lookup"><span data-stu-id="93f42-113">The <xref:System.Text.Json.JsonDocument> provides structured access to the contents of a JSON payload, including <xref:System.DateTime> and <xref:System.DateTimeOffset> representations.</span></span> <span data-ttu-id="93f42-114">下面的示例演示了当给定温度集合时，可以计算星期一的平均温度：</span><span class="sxs-lookup"><span data-stu-id="93f42-114">The example below shows how, when given a collection of temperatures, the average temperature on Mondays can be calculated:</span></span>

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-valid/Program.cs)]

<span data-ttu-id="93f42-115">尝试使用不符合<xref:System.DateTime>表示形式的有效负载来计算平均温度将导致<xref:System.Text.Json.JsonDocument>引发<xref:System.FormatException>：</span><span class="sxs-lookup"><span data-stu-id="93f42-115">Attempting to compute the average temperature given a payload with non-compliant <xref:System.DateTime> representations will cause <xref:System.Text.Json.JsonDocument> to throw a <xref:System.FormatException>:</span></span>

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-error/Program.cs)]

<span data-ttu-id="93f42-116">较低级别<xref:System.Text.Json.Utf8JsonWriter>的<xref:System.DateTime>写入<xref:System.DateTimeOffset>和数据：</span><span class="sxs-lookup"><span data-stu-id="93f42-116">The lower level <xref:System.Text.Json.Utf8JsonWriter> writes <xref:System.DateTime> and <xref:System.DateTimeOffset> data:</span></span>

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/writing-with-utf8jsonwriter/Program.cs)]

<span data-ttu-id="93f42-117"><xref:System.Text.Json.Utf8JsonReader>分析<xref:System.DateTime> 和<xref:System.DateTimeOffset>数据：</span><span class="sxs-lookup"><span data-stu-id="93f42-117"><xref:System.Text.Json.Utf8JsonReader> parses <xref:System.DateTime> and <xref:System.DateTimeOffset> data:</span></span>

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-valid/Program.cs)]

<span data-ttu-id="93f42-118">尝试使用<xref:System.Text.Json.Utf8JsonReader>读取不符合格式将导致其<xref:System.FormatException>引发：</span><span class="sxs-lookup"><span data-stu-id="93f42-118">Attempting to read non-compliant formats with <xref:System.Text.Json.Utf8JsonReader> will cause it to throw a <xref:System.FormatException>:</span></span>

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-error/Program.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset"></a><span data-ttu-id="93f42-119">对和的<xref:System.DateTime>自定义支持<xref:System.DateTimeOffset></span><span class="sxs-lookup"><span data-stu-id="93f42-119">Custom support for <xref:System.DateTime> and <xref:System.DateTimeOffset></span></span>

### <a name="when-using-xrefsystemtextjsonjsonserializer"></a><span data-ttu-id="93f42-120">当使用<xref:System.Text.Json.JsonSerializer></span><span class="sxs-lookup"><span data-stu-id="93f42-120">When using <xref:System.Text.Json.JsonSerializer></span></span>

<span data-ttu-id="93f42-121">如果希望序列化程序执行自定义分析或格式设置，可以实现[自定义转换器](xref:System.Text.Json.Serialization.JsonConverter%601)。</span><span class="sxs-lookup"><span data-stu-id="93f42-121">If you want the serializer to perform custom parsing or formatting, you can implement [custom converters](xref:System.Text.Json.Serialization.JsonConverter%601).</span></span>
<span data-ttu-id="93f42-122">下面是几个示例：</span><span class="sxs-lookup"><span data-stu-id="93f42-122">Here are a few examples:</span></span>

#### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a><span data-ttu-id="93f42-123">使用`DateTime(Offset).Parse`和`DateTime(Offset).ToString`</span><span class="sxs-lookup"><span data-stu-id="93f42-123">Using `DateTime(Offset).Parse` and `DateTime(Offset).ToString`</span></span>

<span data-ttu-id="93f42-124">如果无法确定输入<xref:System.DateTime>或<xref:System.DateTimeOffset>文本表示形式的格式，则可以使用转换器读取逻辑`DateTime(Offset).Parse`中的方法。</span><span class="sxs-lookup"><span data-stu-id="93f42-124">If you can't determine the formats of your input <xref:System.DateTime> or <xref:System.DateTimeOffset> text representations, you can use the `DateTime(Offset).Parse` method in your converter read logic.</span></span> <span data-ttu-id="93f42-125">这允许使用。NET 对分析各种<xref:System.DateTime>和<xref:System.DateTimeOffset>文本格式的广泛支持，包括非 iso 8601 字符串和不符合扩展 iso 8601-1:2019 配置文件的 iso 8601 格式。</span><span class="sxs-lookup"><span data-stu-id="93f42-125">This allows you to use .NET's extensive support for parsing various <xref:System.DateTime> and <xref:System.DateTimeOffset> text formats, including non-ISO 8601 strings and ISO 8601 formats that don't conform to the extended ISO 8601-1:2019 profile.</span></span> <span data-ttu-id="93f42-126">与使用序列化程序的本机实现相比，此方法的性能大大降低。</span><span class="sxs-lookup"><span data-stu-id="93f42-126">This approach is significantly less performant than using the serializer's native implementation.</span></span>

<span data-ttu-id="93f42-127">对于序列化，可以在转换器`DateTime(Offset).ToString`写入逻辑中使用方法。</span><span class="sxs-lookup"><span data-stu-id="93f42-127">For serializing, you can use the `DateTime(Offset).ToString` method in your converter write logic.</span></span> <span data-ttu-id="93f42-128">这使您可以使用<xref:System.DateTime>任何<xref:System.DateTimeOffset> [标准日期和时间格式](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)以及[自定义日期和时间格式](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings)来编写和值。</span><span class="sxs-lookup"><span data-stu-id="93f42-128">This allows you to write <xref:System.DateTime> and <xref:System.DateTimeOffset> values using any of the [standard date and time formats](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings), and the [custom date and time formats](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>
<span data-ttu-id="93f42-129">与使用序列化程序的本机实现相比，这种性能也明显降低。</span><span class="sxs-lookup"><span data-stu-id="93f42-129">This is also significantly less performant than using the serializer's native implementation.</span></span>

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> <span data-ttu-id="93f42-130">在实现<xref:System.Text.Json.Serialization.JsonConverter%601>时， `T`和<xref:System.DateTime>为时`typeToConvert` ，参数将始终`typeof(DateTime)`为。</span><span class="sxs-lookup"><span data-stu-id="93f42-130">When implementing <xref:System.Text.Json.Serialization.JsonConverter%601>, and `T` is <xref:System.DateTime>, the `typeToConvert` parameter will always be `typeof(DateTime)`.</span></span>
<span data-ttu-id="93f42-131">参数可用于处理多态事例和使用泛型以高性能方式`typeof(T)`获取。</span><span class="sxs-lookup"><span data-stu-id="93f42-131">The parameter is useful for handling polymorphic cases and when using generics to get `typeof(T)` in a performant way.</span></span>

#### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a><span data-ttu-id="93f42-132">使用<xref:System.Buffers.Text.Utf8Parser>和<xref:System.Buffers.Text.Utf8Formatter></span><span class="sxs-lookup"><span data-stu-id="93f42-132">Using <xref:System.Buffers.Text.Utf8Parser> and <xref:System.Buffers.Text.Utf8Formatter></span></span>

<span data-ttu-id="93f42-133">如果输入<xref:System.DateTime>或<xref:System.DateTimeOffset>文本表示形式符合 "R"、"l"、"O" 或 "G"[标准日期和时间格式字符串](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)之一，或者您想要，可以在转换器逻辑中使用快速的基于 utf-8 的分析和格式设置方法。根据其中一种格式写入。</span><span class="sxs-lookup"><span data-stu-id="93f42-133">You can use fast UTF-8-based parsing and formatting methods in your converter logic if your input <xref:System.DateTime> or <xref:System.DateTimeOffset> text representations are compliant with one of the "R", "l", "O", or "G" [standard date and time format strings](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings), or you want to write according to one of these formats.</span></span> <span data-ttu-id="93f42-134">这比使用`DateTime(Offset).Parse`和`DateTime(Offset).ToString`更快。</span><span class="sxs-lookup"><span data-stu-id="93f42-134">This is much faster than using `DateTime(Offset).Parse` and `DateTime(Offset).ToString`.</span></span>

<span data-ttu-id="93f42-135">此示例演示一个自定义转换器，该转换器<xref:System.DateTime>根据["R" 标准格式](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-rfc1123-r-r-format-specifier)对值进行序列化和反序列化：</span><span class="sxs-lookup"><span data-stu-id="93f42-135">This example shows a custom converter that serializes and deserializes <xref:System.DateTime> values according to [the "R" standard format](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-rfc1123-r-r-format-specifier):</span></span>

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> <span data-ttu-id="93f42-136">"R" 标准格式的长度始终为29个字符。</span><span class="sxs-lookup"><span data-stu-id="93f42-136">The "R" standard format will always be 29 characters long.</span></span>

#### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a><span data-ttu-id="93f42-137">使用`DateTime(Offset).Parse`作为序列化程序的本机解析的回退</span><span class="sxs-lookup"><span data-stu-id="93f42-137">Using `DateTime(Offset).Parse` as a fallback to the serializer's native parsing</span></span>

<span data-ttu-id="93f42-138">如果你通常希望输入<xref:System.DateTime>或<xref:System.DateTimeOffset>数据符合扩展 ISO 8601-1:2019 配置文件，则可以使用序列化程序的本机分析逻辑。</span><span class="sxs-lookup"><span data-stu-id="93f42-138">If you generally expect your input <xref:System.DateTime> or <xref:System.DateTimeOffset> data to conform to the extended ISO 8601-1:2019 profile, you can use the serializer's native parsing logic.</span></span> <span data-ttu-id="93f42-139">您还可以实现一种回退机制。</span><span class="sxs-lookup"><span data-stu-id="93f42-139">You can also implement a fallback mechanism just in case.</span></span>
<span data-ttu-id="93f42-140">此示例显示，在无法使用<xref:System.DateTime> <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>分析文本表示形式后，转换器使用<xref:System.DateTime.Parse(System.String)>成功分析数据。</span><span class="sxs-lookup"><span data-stu-id="93f42-140">This example shows that, after failing to parse a <xref:System.DateTime> text representation using <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>, the converter successfully parses the data using <xref:System.DateTime.Parse(System.String)>.</span></span>

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example3/Program.cs)]

### <a name="when-writing-with-xrefsystemtextjsonutf8jsonwriter"></a><span data-ttu-id="93f42-141">写入时<xref:System.Text.Json.Utf8JsonWriter></span><span class="sxs-lookup"><span data-stu-id="93f42-141">When writing with <xref:System.Text.Json.Utf8JsonWriter></span></span>

<span data-ttu-id="93f42-142"><xref:System.DateTime>如果要使用`ReadOnlySpan<Byte>` <xref:System.Text.Json.JsonEncodedText> <xref:System.String> <xref:System.DateTimeOffset> `ReadOnlySpan<Char>`编写自定义或文本表示形式，可以将自定义表示形式设置为、、或，然后将其传递给相应的<xref:System.Text.Json.Utf8JsonWriter>[Utf8JsonWriter. WriteStringValue](https://docs.microsoft.com/dotnet/api/system.text.json.utf8jsonwriter.writestringvalue?view=netcore-3.0)或[Utf8JsonWriter. WriteString](https://docs.microsoft.com/dotnet/api/system.text.json.utf8jsonwriter.writestring?view=netcore-3.0)方法。</span><span class="sxs-lookup"><span data-stu-id="93f42-142">If you want to write a custom <xref:System.DateTime> or <xref:System.DateTimeOffset> text representation with <xref:System.Text.Json.Utf8JsonWriter>, you can format your custom representation to a <xref:System.String>, `ReadOnlySpan<Byte>`, `ReadOnlySpan<Char>`, or <xref:System.Text.Json.JsonEncodedText>, then pass it to the corresponding [Utf8JsonWriter.WriteStringValue](https://docs.microsoft.com/dotnet/api/system.text.json.utf8jsonwriter.writestringvalue?view=netcore-3.0) or [Utf8JsonWriter.WriteString](https://docs.microsoft.com/dotnet/api/system.text.json.utf8jsonwriter.writestring?view=netcore-3.0) method.</span></span>

<span data-ttu-id="93f42-143">下面的示例演示如何使用<xref:System.DateTime> <xref:System.DateTime.ToString(System.String,System.IFormatProvider)>创建自定义格式，然后使用方法编写该<xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)>格式：</span><span class="sxs-lookup"><span data-stu-id="93f42-143">The following example shows how a custom <xref:System.DateTime> format can be created with <xref:System.DateTime.ToString(System.String,System.IFormatProvider)>, then written with the <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)> method:</span></span>

[!code-csharp[example-custom-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/custom-writing-with-utf8jsonwriter/Program.cs)]

### <a name="when-reading-with-xrefsystemtextjsonutf8jsonreader"></a><span data-ttu-id="93f42-144">读取时<xref:System.Text.Json.Utf8JsonReader></span><span class="sxs-lookup"><span data-stu-id="93f42-144">When reading with <xref:System.Text.Json.Utf8JsonReader></span></span>

<span data-ttu-id="93f42-145"><xref:System.DateTime>如果要使用<xref:System.String> <xref:System.DateTimeOffset> <xref:System.Text.Json.Utf8JsonReader.GetString>读取自定义或文本表示形式，可以使用获取当前 JSON 标记的值，然后使用自定义逻辑分析该值。 <xref:System.Text.Json.Utf8JsonReader></span><span class="sxs-lookup"><span data-stu-id="93f42-145">If you want to read a custom <xref:System.DateTime> or <xref:System.DateTimeOffset> text representation with <xref:System.Text.Json.Utf8JsonReader>, you can get the value of the current JSON token as a <xref:System.String> using <xref:System.Text.Json.Utf8JsonReader.GetString>, then parse the value using custom logic.</span></span>

<span data-ttu-id="93f42-146">下面的示例演示如何使用<xref:System.DateTimeOffset> <xref:System.Text.Json.Utf8JsonReader.GetString>检索自定义文本表示形式，然后使用<xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)>进行分析：</span><span class="sxs-lookup"><span data-stu-id="93f42-146">The following example shows how a custom <xref:System.DateTimeOffset> text representation can be retrieved using <xref:System.Text.Json.Utf8JsonReader.GetString>, then parsed using <xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)>:</span></span>

[!code-csharp[example-custom-reading-with-utf8jsonreader](~/samples/snippets/standard/datetime/json/csharp/custom-reading-with-utf8jsonreader/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a><span data-ttu-id="93f42-147">系统中的扩展 ISO 8601-1:2019 配置文件</span><span class="sxs-lookup"><span data-stu-id="93f42-147">The extended ISO 8601-1:2019 profile in System.Text.Json</span></span>

### <a name="date-and-time-components"></a><span data-ttu-id="93f42-148">日期和时间组件</span><span class="sxs-lookup"><span data-stu-id="93f42-148">Date and time components</span></span>

<span data-ttu-id="93f42-149">在中<xref:System.Text.Json>实现的扩展 ISO 8601-1:2019 配置文件定义了日期和时间表示的以下组件。</span><span class="sxs-lookup"><span data-stu-id="93f42-149">The extended ISO 8601-1:2019 profile implemented in <xref:System.Text.Json> defines the following components for date and time representations.</span></span> <span data-ttu-id="93f42-150">这些组件用于定义分析和格式设置<xref:System.DateTime>和<xref:System.DateTimeOffset>表示形式时支持的各种粒度级别。</span><span class="sxs-lookup"><span data-stu-id="93f42-150">These components are used to define various levels of granularity supported when parsing and formatting <xref:System.DateTime> and <xref:System.DateTimeOffset> representations.</span></span>

| <span data-ttu-id="93f42-151">组件</span><span class="sxs-lookup"><span data-stu-id="93f42-151">Component</span></span>       | <span data-ttu-id="93f42-152">格式</span><span class="sxs-lookup"><span data-stu-id="93f42-152">Format</span></span>                      | <span data-ttu-id="93f42-153">描述</span><span class="sxs-lookup"><span data-stu-id="93f42-153">Description</span></span>                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="93f42-154">年</span><span class="sxs-lookup"><span data-stu-id="93f42-154">Year</span></span>            | <span data-ttu-id="93f42-155">“yyyy”</span><span class="sxs-lookup"><span data-stu-id="93f42-155">"yyyy"</span></span>                      | <span data-ttu-id="93f42-156">0001-9999</span><span class="sxs-lookup"><span data-stu-id="93f42-156">0001-9999</span></span>                                                                       |
| <span data-ttu-id="93f42-157">月份</span><span class="sxs-lookup"><span data-stu-id="93f42-157">Month</span></span>           | <span data-ttu-id="93f42-158">“MM”</span><span class="sxs-lookup"><span data-stu-id="93f42-158">"MM"</span></span>                        | <span data-ttu-id="93f42-159">01-12</span><span class="sxs-lookup"><span data-stu-id="93f42-159">01-12</span></span>                                                                           |
| <span data-ttu-id="93f42-160">天</span><span class="sxs-lookup"><span data-stu-id="93f42-160">Day</span></span>             | <span data-ttu-id="93f42-161">“dd”</span><span class="sxs-lookup"><span data-stu-id="93f42-161">"dd"</span></span>                        | <span data-ttu-id="93f42-162">01-28、01-29、01-30、01-31 （基于月份/年份）</span><span class="sxs-lookup"><span data-stu-id="93f42-162">01-28, 01-29, 01-30, 01-31 based on month/year</span></span>                                  |
| <span data-ttu-id="93f42-163">小时</span><span class="sxs-lookup"><span data-stu-id="93f42-163">Hour</span></span>            | <span data-ttu-id="93f42-164">“HH”</span><span class="sxs-lookup"><span data-stu-id="93f42-164">"HH"</span></span>                        | <span data-ttu-id="93f42-165">00-23</span><span class="sxs-lookup"><span data-stu-id="93f42-165">00-23</span></span>                                                                           |
| <span data-ttu-id="93f42-166">分钟</span><span class="sxs-lookup"><span data-stu-id="93f42-166">Minute</span></span>          | <span data-ttu-id="93f42-167">“mm”</span><span class="sxs-lookup"><span data-stu-id="93f42-167">"mm"</span></span>                        | <span data-ttu-id="93f42-168">00-59</span><span class="sxs-lookup"><span data-stu-id="93f42-168">00-59</span></span>                                                                           |
| <span data-ttu-id="93f42-169">秒</span><span class="sxs-lookup"><span data-stu-id="93f42-169">Second</span></span>          | <span data-ttu-id="93f42-170">“ss”</span><span class="sxs-lookup"><span data-stu-id="93f42-170">"ss"</span></span>                        | <span data-ttu-id="93f42-171">00-59</span><span class="sxs-lookup"><span data-stu-id="93f42-171">00-59</span></span>                                                                           |
| <span data-ttu-id="93f42-172">第二部分</span><span class="sxs-lookup"><span data-stu-id="93f42-172">Second fraction</span></span> | <span data-ttu-id="93f42-173">“FFFFFFF”</span><span class="sxs-lookup"><span data-stu-id="93f42-173">"FFFFFFF"</span></span>                   | <span data-ttu-id="93f42-174">至少一个数字，最多为16位</span><span class="sxs-lookup"><span data-stu-id="93f42-174">Minimum of one digit, maximum of 16 digits</span></span>                                      |
| <span data-ttu-id="93f42-175">时间偏移</span><span class="sxs-lookup"><span data-stu-id="93f42-175">Time offset</span></span>     | <span data-ttu-id="93f42-176">“K”</span><span class="sxs-lookup"><span data-stu-id="93f42-176">"K"</span></span>                         | <span data-ttu-id="93f42-177">"Z" 或 "（" + "/"-"） HH"： "mm"</span><span class="sxs-lookup"><span data-stu-id="93f42-177">Either "Z" or "('+'/'-')HH':'mm"</span></span>                                                |
| <span data-ttu-id="93f42-178">部分时间</span><span class="sxs-lookup"><span data-stu-id="93f42-178">Partial time</span></span>    | <span data-ttu-id="93f42-179">"HH"： "mm"： "ss [FFFFFFF]"</span><span class="sxs-lookup"><span data-stu-id="93f42-179">"HH':'mm':'ss[FFFFFFF]"</span></span>     | <span data-ttu-id="93f42-180">不带 UTC 偏移信息的时间</span><span class="sxs-lookup"><span data-stu-id="93f42-180">Time without UTC offset information</span></span>                                             |
| <span data-ttu-id="93f42-181">完整日期</span><span class="sxs-lookup"><span data-stu-id="93f42-181">Full date</span></span>       | <span data-ttu-id="93f42-182">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-yyyy'-'mm'-'dd"</span><span class="sxs-lookup"><span data-stu-id="93f42-182">"yyyy'-'MM'-'dd"</span></span>            | <span data-ttu-id="93f42-183">日历日期</span><span class="sxs-lookup"><span data-stu-id="93f42-183">Calendar date</span></span>                                                                   |
| <span data-ttu-id="93f42-184">全部时间</span><span class="sxs-lookup"><span data-stu-id="93f42-184">Full time</span></span>       | <span data-ttu-id="93f42-185">"' Partial time'K"</span><span class="sxs-lookup"><span data-stu-id="93f42-185">"'Partial time'K"</span></span>           | <span data-ttu-id="93f42-186">一天中的 UTC 或本地时间与本地时间和 UTC 之间的时间偏移量</span><span class="sxs-lookup"><span data-stu-id="93f42-186">UTC of day or Local time of day with the time offset between local time and UTC</span></span> |
| <span data-ttu-id="93f42-187">日期时间</span><span class="sxs-lookup"><span data-stu-id="93f42-187">Date time</span></span>       | <span data-ttu-id="93f42-188">"" 完整时间 "不是" "完整时间" "</span><span class="sxs-lookup"><span data-stu-id="93f42-188">"'Full date''T''Full time'"</span></span> | <span data-ttu-id="93f42-189">日历日期和当天的时间，例如 2019-07-26T16：59： 57-05：00</span><span class="sxs-lookup"><span data-stu-id="93f42-189">Calendar date and time of day, e.g. 2019-07-26T16:59:57-05:00</span></span>                   |

### <a name="support-for-parsing"></a><span data-ttu-id="93f42-190">支持分析</span><span class="sxs-lookup"><span data-stu-id="93f42-190">Support for parsing</span></span>

<span data-ttu-id="93f42-191">定义以下级别的粒度：</span><span class="sxs-lookup"><span data-stu-id="93f42-191">The following levels of granularity are defined for parsing:</span></span>

1. <span data-ttu-id="93f42-192">"Full date"</span><span class="sxs-lookup"><span data-stu-id="93f42-192">'Full date'</span></span>
    1. <span data-ttu-id="93f42-193">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-yyyy'-'mm'-'dd"</span><span class="sxs-lookup"><span data-stu-id="93f42-193">"yyyy'-'MM'-'dd"</span></span>

2. <span data-ttu-id="93f42-194">"" 完整日期 "不是" "小时" "：" 分钟 "</span><span class="sxs-lookup"><span data-stu-id="93f42-194">"'Full date''T''Hour'':''Minute'"</span></span>
    1. <span data-ttu-id="93f42-195">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"</span><span class="sxs-lookup"><span data-stu-id="93f42-195">"yyyy'-'MM'-'dd'T'HH':'mm"</span></span>

3. <span data-ttu-id="93f42-196">"" 完整日期 "不是" "部分时间" "</span><span class="sxs-lookup"><span data-stu-id="93f42-196">"'Full date''T''Partial time'"</span></span>
    1. <span data-ttu-id="93f42-197">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ss" （可[排序（"s"）格式说明符](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier)）</span><span class="sxs-lookup"><span data-stu-id="93f42-197">"yyyy'-'MM'-'dd'T'HH':'mm':'ss" ([The Sortable ("s") Format Specifier](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))</span></span>
    2. <span data-ttu-id="93f42-198">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ss"。FFFFFFF</span><span class="sxs-lookup"><span data-stu-id="93f42-198">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF"</span></span>

4. <span data-ttu-id="93f42-199">"" 完整日期 "不是" "，时间小时" "：" "分钟" "时间偏移" "</span><span class="sxs-lookup"><span data-stu-id="93f42-199">"'Full date''T''Time hour'':''Minute''Time offset'"</span></span>
    1. <span data-ttu-id="93f42-200">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "mmZ"</span><span class="sxs-lookup"><span data-stu-id="93f42-200">"yyyy'-'MM'-'dd'T'HH':'mmZ"</span></span>
    2. <span data-ttu-id="93f42-201">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "mm （' + '/'-'） HH '： ' mm"</span><span class="sxs-lookup"><span data-stu-id="93f42-201">"yyyy'-'MM'-'dd'T'HH':'mm('+'/'-')HH':'mm"</span></span>

5. <span data-ttu-id="93f42-202">"日期时间"</span><span class="sxs-lookup"><span data-stu-id="93f42-202">'Date time'</span></span>
    1. <span data-ttu-id="93f42-203">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ssZ"</span><span class="sxs-lookup"><span data-stu-id="93f42-203">"yyyy'-'MM'-'dd'T'HH':'mm':'ssZ"</span></span>
    2. <span data-ttu-id="93f42-204">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ss"。FFFFFFFZ"</span><span class="sxs-lookup"><span data-stu-id="93f42-204">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFFZ"</span></span>
    3. <span data-ttu-id="93f42-205">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' MM '： ' ss （' + '/'-'） HH '： ' MM"</span><span class="sxs-lookup"><span data-stu-id="93f42-205">"yyyy'-'MM'-'dd'T'HH':'mm':'ss('+'/'-')HH':'mm"</span></span>
    4. <span data-ttu-id="93f42-206">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ss"。FFFFFFF （"+"/"-"） HH "：" mm "</span><span class="sxs-lookup"><span data-stu-id="93f42-206">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF('+'/'-')HH':'mm"</span></span>

<span data-ttu-id="93f42-207">如果有秒的小数部分，则必须至少有一个数字;`2019-07-26T00:00:00.`不允许。</span><span class="sxs-lookup"><span data-stu-id="93f42-207">If there are decimal fractions for seconds, there must be at least one digit; `2019-07-26T00:00:00.` is not allowed.</span></span>
<span data-ttu-id="93f42-208">尽管允许最多包含16个小数位，但仅分析前7个小数。</span><span class="sxs-lookup"><span data-stu-id="93f42-208">While up to 16 fractional digits are allowed, only the first seven are parsed.</span></span> <span data-ttu-id="93f42-209">超出的任何内容都将被视为零。</span><span class="sxs-lookup"><span data-stu-id="93f42-209">Anything beyond that is considered a zero.</span></span>
<span data-ttu-id="93f42-210">例如， `2019-07-26T00:00:00.1234567890`将按`2019-07-26T00:00:00.1234567`原样进行分析。</span><span class="sxs-lookup"><span data-stu-id="93f42-210">For example, `2019-07-26T00:00:00.1234567890` will be parsed as if it is `2019-07-26T00:00:00.1234567`.</span></span>
<span data-ttu-id="93f42-211">这是为了保持与<xref:System.DateTime>实现的兼容性，这仅限于此解决方案。</span><span class="sxs-lookup"><span data-stu-id="93f42-211">This is to stay compatible with the <xref:System.DateTime> implementation, which is limited to this resolution.</span></span>

<span data-ttu-id="93f42-212">不支持闰秒。</span><span class="sxs-lookup"><span data-stu-id="93f42-212">Leap seconds are not supported.</span></span>

### <a name="support-for-formatting"></a><span data-ttu-id="93f42-213">支持格式设置</span><span class="sxs-lookup"><span data-stu-id="93f42-213">Support for formatting</span></span>

<span data-ttu-id="93f42-214">为格式化定义了下列粒度级别：</span><span class="sxs-lookup"><span data-stu-id="93f42-214">The following levels of granularity are defined for formatting:</span></span>

1. <span data-ttu-id="93f42-215">"" 完整日期 "不是" "部分时间" "</span><span class="sxs-lookup"><span data-stu-id="93f42-215">"'Full date''T''Partial time'"</span></span>
    1. <span data-ttu-id="93f42-216">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ss" （可[排序（"s"）格式说明符](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier)）</span><span class="sxs-lookup"><span data-stu-id="93f42-216">"yyyy'-'MM'-'dd'T'HH':'mm':'ss"  ([The Sortable ("s") Format Specifier](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))</span></span>

        <span data-ttu-id="93f42-217">用于设置不包含<xref:System.DateTime>秒的小数部分和不含偏移量信息的格式。</span><span class="sxs-lookup"><span data-stu-id="93f42-217">Used to format a <xref:System.DateTime> without fractional seconds and without offset information.</span></span>

    2. <span data-ttu-id="93f42-218">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ss"。FFFFFFF</span><span class="sxs-lookup"><span data-stu-id="93f42-218">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF"</span></span>

        <span data-ttu-id="93f42-219">用于设置带小数<xref:System.DateTime>秒但不含偏移信息的的格式。</span><span class="sxs-lookup"><span data-stu-id="93f42-219">Used to format a <xref:System.DateTime> with fractional seconds but without offset information.</span></span>

2. <span data-ttu-id="93f42-220">"日期时间"</span><span class="sxs-lookup"><span data-stu-id="93f42-220">'Date time'</span></span>
    1. <span data-ttu-id="93f42-221">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ssZ"</span><span class="sxs-lookup"><span data-stu-id="93f42-221">"yyyy'-'MM'-'dd'T'HH':'mm':'ssZ"</span></span>

        <span data-ttu-id="93f42-222">用于设置<xref:System.DateTime>或<xref:System.DateTimeOffset>不包含秒的小数部分，但使用 UTC 偏移量。</span><span class="sxs-lookup"><span data-stu-id="93f42-222">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> without fractional seconds but with a UTC offset.</span></span>

    2. <span data-ttu-id="93f42-223">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ss"。FFFFFFFZ"</span><span class="sxs-lookup"><span data-stu-id="93f42-223">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFFZ"</span></span>

        <span data-ttu-id="93f42-224">用于设置<xref:System.DateTime>或<xref:System.DateTimeOffset>的小数部分的格式，且具有 UTC 偏移量。</span><span class="sxs-lookup"><span data-stu-id="93f42-224">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> with fractional seconds and with a UTC offset.</span></span>

    3. <span data-ttu-id="93f42-225">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' MM '： ' ss （' + '/'-'） HH '： ' MM"</span><span class="sxs-lookup"><span data-stu-id="93f42-225">"yyyy'-'MM'-'dd'T'HH':'mm':'ss('+'/'-')HH':'mm"</span></span>

        <span data-ttu-id="93f42-226">用于设置<xref:System.DateTime>或<xref:System.DateTimeOffset>不包含秒的小数部分，但使用本地偏移量。</span><span class="sxs-lookup"><span data-stu-id="93f42-226">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> without fractional seconds but with a local offset.</span></span>

    4. <span data-ttu-id="93f42-227">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ss"。FFFFFFF （"+"/"-"） HH "：" mm "</span><span class="sxs-lookup"><span data-stu-id="93f42-227">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF('+'/'-')HH':'mm"</span></span>

        <span data-ttu-id="93f42-228">用于设置<xref:System.DateTime>或的小数<xref:System.DateTimeOffset>部分或局部偏移量的格式。</span><span class="sxs-lookup"><span data-stu-id="93f42-228">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> with fractional seconds and with a local offset.</span></span>

<span data-ttu-id="93f42-229">如果存在，则最多可以写入7个小数位。</span><span class="sxs-lookup"><span data-stu-id="93f42-229">If present, a maximum of 7 fractional digits are written.</span></span> <span data-ttu-id="93f42-230">这与<xref:System.DateTime>实现（仅限于此解决方案）一致。</span><span class="sxs-lookup"><span data-stu-id="93f42-230">This aligns with the <xref:System.DateTime> implementation, which is limited to this resolution.</span></span>
