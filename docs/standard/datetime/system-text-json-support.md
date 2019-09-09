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
ms.openlocfilehash: 5bff01b10b2bdea4fdcfee86e348c47f44d50103
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374476"
---
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a><span data-ttu-id="a50cb-103">System.Text.Json 中的 DateTime 和 DateTimeOffset 支持</span><span class="sxs-lookup"><span data-stu-id="a50cb-103">DateTime and DateTimeOffset support in System.Text.Json</span></span>

<span data-ttu-id="a50cb-104">根据 ISO 8601:-2019 扩展配置文件，system.web 库分析<xref:System.DateTime>并<xref:System.DateTimeOffset>写入和值。</span><span class="sxs-lookup"><span data-stu-id="a50cb-104">The System.Text.Json library parses and writes <xref:System.DateTime> and <xref:System.DateTimeOffset> values according to the ISO 8601:-2019 extended profile.</span></span>
<span data-ttu-id="a50cb-105">[转换器](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0)为序列化和反序列<xref:System.Text.Json.JsonSerializer>化提供自定义支持。</span><span class="sxs-lookup"><span data-stu-id="a50cb-105">[Converters](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0) provide custom support for serializing and deserializing with <xref:System.Text.Json.JsonSerializer>.</span></span>

## <a name="support-for-the-iso-8601-12019-format"></a><span data-ttu-id="a50cb-106">支持 ISO 8601-1:2019 格式</span><span class="sxs-lookup"><span data-stu-id="a50cb-106">Support for the ISO 8601-1:2019 format</span></span>

<span data-ttu-id="a50cb-107"><xref:System.Text.Json.JsonSerializer> <xref:System.DateTime> <xref:System.DateTimeOffset> 、 、<xref:System.Text.Json.Utf8JsonReader>和类型根据ISO8601-1:2019格式的扩展配置文件分析并写入和文本表示形式;例如，2019-07-26T16<xref:System.Text.Json.JsonElement> <xref:System.Text.Json.Utf8JsonWriter>：59:57-05:00。</span><span class="sxs-lookup"><span data-stu-id="a50cb-107">The <xref:System.Text.Json.JsonSerializer>, <xref:System.Text.Json.Utf8JsonReader>, <xref:System.Text.Json.Utf8JsonWriter>, and <xref:System.Text.Json.JsonElement> types parse and write <xref:System.DateTime> and <xref:System.DateTimeOffset> text representations according to the extended profile of the ISO 8601-1:2019 format; for example, 2019-07-26T16:59:57-05:00.</span></span>

<span data-ttu-id="a50cb-108"><xref:System.DateTime>和<xref:System.DateTimeOffset>数据可通过以下方式<xref:System.Text.Json.JsonSerializer>序列化：</span><span class="sxs-lookup"><span data-stu-id="a50cb-108"><xref:System.DateTime> and <xref:System.DateTimeOffset> data can be serialized with <xref:System.Text.Json.JsonSerializer>:</span></span>

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/serializing-with-jsonserializer.cs)]

<span data-ttu-id="a50cb-109">还可以通过以下方式<xref:System.Text.Json.JsonSerializer>对其进行反序列化：</span><span class="sxs-lookup"><span data-stu-id="a50cb-109">They can also be deserialized with <xref:System.Text.Json.JsonSerializer>:</span></span>

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/deserializing-with-jsonserializer-valid.cs)]

<span data-ttu-id="a50cb-110">对于默认选项，输入<xref:System.DateTime>和<xref:System.DateTimeOffset>文本表示形式必须符合扩展 ISO 8601-1:2019 配置文件。</span><span class="sxs-lookup"><span data-stu-id="a50cb-110">With default options, input <xref:System.DateTime> and <xref:System.DateTimeOffset> text representations must conform to the extended ISO 8601-1:2019 profile.</span></span>
<span data-ttu-id="a50cb-111">尝试对不符合配置文件的表示形式进行反序列<xref:System.Text.Json.JsonSerializer>化将导致<xref:System.Text.Json.JsonException>引发：</span><span class="sxs-lookup"><span data-stu-id="a50cb-111">Attempting to deserialize representations that don't conform to the profile will cause <xref:System.Text.Json.JsonSerializer> to throw a <xref:System.Text.Json.JsonException>:</span></span>

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/deserializing-with-jsonserializer-error.cs)]

<span data-ttu-id="a50cb-112">提供对 JSON 有效负载（包括<xref:System.DateTime>和<xref:System.DateTimeOffset>表示形式）内容的结构化访问。 <xref:System.Text.Json.JsonDocument></span><span class="sxs-lookup"><span data-stu-id="a50cb-112">The <xref:System.Text.Json.JsonDocument> provides structured access to the contents of a JSON payload, including <xref:System.DateTime> and <xref:System.DateTimeOffset> representations.</span></span> <span data-ttu-id="a50cb-113">下面的示例演示了当给定温度集合时，可以计算星期一的平均温度：</span><span class="sxs-lookup"><span data-stu-id="a50cb-113">The example below shows how, when given a collection of temperatures, the average temperature on Mondays can be calculated:</span></span>

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/computing-with-jsondocument-valid.cs)]

<span data-ttu-id="a50cb-114">尝试使用不符合<xref:System.DateTime>表示形式的有效负载来计算平均温度将导致<xref:System.Text.Json.JsonDocument>引发<xref:System.FormatException>：</span><span class="sxs-lookup"><span data-stu-id="a50cb-114">Attempting to compute the average temperature given a payload with non-compliant <xref:System.DateTime> representations will cause <xref:System.Text.Json.JsonDocument> to throw a <xref:System.FormatException>:</span></span>

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/computing-with-jsondocument-error.cs)]

<span data-ttu-id="a50cb-115">较低级别<xref:System.Text.Json.Utf8JsonWriter>的<xref:System.DateTime>写入<xref:System.DateTimeOffset>和数据：</span><span class="sxs-lookup"><span data-stu-id="a50cb-115">The lower level <xref:System.Text.Json.Utf8JsonWriter> writes <xref:System.DateTime> and <xref:System.DateTimeOffset> data:</span></span>

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/writing-with-utf8jsonwriter.cs)]

<span data-ttu-id="a50cb-116"><xref:System.Text.Json.Utf8JsonReader>分析<xref:System.DateTime> 和<xref:System.DateTimeOffset>数据：</span><span class="sxs-lookup"><span data-stu-id="a50cb-116"><xref:System.Text.Json.Utf8JsonReader> parses <xref:System.DateTime> and <xref:System.DateTimeOffset> data:</span></span>

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/reading-with-utf8jsonreader-valid.cs)]

<span data-ttu-id="a50cb-117">尝试使用<xref:System.Text.Json.Utf8JsonReader>读取不符合格式将导致其<xref:System.FormatException>引发：</span><span class="sxs-lookup"><span data-stu-id="a50cb-117">Attempting to read non-compliant formats with <xref:System.Text.Json.Utf8JsonReader> will cause it to throw a <xref:System.FormatException>:</span></span>

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/reading-with-utf8jsonreader-error.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset-in-xrefsystemtextjsonjsonserializer"></a><span data-ttu-id="a50cb-118"><xref:System.DateTime> 和<xref:System.DateTimeOffset>中的自定义支持<xref:System.Text.Json.JsonSerializer></span><span class="sxs-lookup"><span data-stu-id="a50cb-118">Custom support for <xref:System.DateTime> and <xref:System.DateTimeOffset> in <xref:System.Text.Json.JsonSerializer></span></span>

<span data-ttu-id="a50cb-119">如果希望序列化程序执行自定义分析或格式设置，可以实现[自定义转换器](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0)。</span><span class="sxs-lookup"><span data-stu-id="a50cb-119">If you want the serializer to perform custom parsing or formatting, you can implement [custom converters](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0).</span></span>
<span data-ttu-id="a50cb-120">以下是几个示例：</span><span class="sxs-lookup"><span data-stu-id="a50cb-120">Here are a few examples:</span></span>

### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a><span data-ttu-id="a50cb-121">使用`DateTime(Offset).Parse`和`DateTime(Offset).ToString`</span><span class="sxs-lookup"><span data-stu-id="a50cb-121">Using `DateTime(Offset).Parse` and `DateTime(Offset).ToString`</span></span>

<span data-ttu-id="a50cb-122">如果无法确定输入<xref:System.DateTime>或<xref:System.DateTimeOffset>文本表示形式的格式，则可以使用转换器读取逻辑`DateTime(Offset).Parse`中的方法。</span><span class="sxs-lookup"><span data-stu-id="a50cb-122">If you can't determine the formats of your input <xref:System.DateTime> or <xref:System.DateTimeOffset> text representations, you can use the `DateTime(Offset).Parse` method in your converter read logic.</span></span> <span data-ttu-id="a50cb-123">这允许使用。NET 对分析各种<xref:System.DateTime>和<xref:System.DateTimeOffset>文本格式的广泛支持，包括非 iso 8601 字符串和不符合扩展 iso 8601-1:2019 配置文件的 iso 8601 格式。</span><span class="sxs-lookup"><span data-stu-id="a50cb-123">This allows you to use .NET's extensive support for parsing various <xref:System.DateTime> and <xref:System.DateTimeOffset> text formats, including non-ISO 8601 strings and ISO 8601 formats that don't conform to the extended ISO 8601-1:2019 profile.</span></span> <span data-ttu-id="a50cb-124">与使用序列化程序的本机实现相比，此方法的性能大大降低。</span><span class="sxs-lookup"><span data-stu-id="a50cb-124">This approach is significantly less performant than using the serializer's native implementation.</span></span>

<span data-ttu-id="a50cb-125">对于序列化，可以在转换器`DateTime(Offset).ToString`写入逻辑中使用方法。</span><span class="sxs-lookup"><span data-stu-id="a50cb-125">For serializing, you can use the `DateTime(Offset).ToString` method in your converter write logic.</span></span> <span data-ttu-id="a50cb-126">这使您可以使用<xref:System.DateTime>任何<xref:System.DateTimeOffset> [标准日期和时间格式](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)以及[自定义日期和时间格式](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings)来编写和值。</span><span class="sxs-lookup"><span data-stu-id="a50cb-126">This allows you to write <xref:System.DateTime> and <xref:System.DateTimeOffset> values using any of the [standard date and time formats](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings), and the [custom date and time formats](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>
<span data-ttu-id="a50cb-127">与使用序列化程序的本机实现相比，这种性能也明显降低。</span><span class="sxs-lookup"><span data-stu-id="a50cb-127">This is also significantly less performant than using the serializer's native implementation.</span></span>

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> <span data-ttu-id="a50cb-128">在实现<xref:System.Text.Json.Serialization.JsonConverter%601>时， `T`和<xref:System.DateTime>为时`typeToConvert` ，参数将始终`typeof(DateTime)`为。</span><span class="sxs-lookup"><span data-stu-id="a50cb-128">When implementing <xref:System.Text.Json.Serialization.JsonConverter%601>, and `T` is <xref:System.DateTime>, the `typeToConvert` parameter will always be `typeof(DateTime)`.</span></span>
<span data-ttu-id="a50cb-129">参数可用于处理多态事例和使用泛型以高性能方式`typeof(T)`获取。</span><span class="sxs-lookup"><span data-stu-id="a50cb-129">The parameter is useful for handling polymorphic cases and when using generics to get `typeof(T)` in a performant way.</span></span>

### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a><span data-ttu-id="a50cb-130">使用<xref:System.Buffers.Text.Utf8Parser>和<xref:System.Buffers.Text.Utf8Formatter></span><span class="sxs-lookup"><span data-stu-id="a50cb-130">Using <xref:System.Buffers.Text.Utf8Parser> and <xref:System.Buffers.Text.Utf8Formatter></span></span>

<span data-ttu-id="a50cb-131">如果输入<xref:System.DateTime>或<xref:System.DateTimeOffset>文本表示形式符合 "R"、"l"、"O" 或 "G"[标准日期和时间格式字符串](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)之一，或者您想要，可以在转换器逻辑中使用快速的基于 utf-8 的分析和格式设置方法。根据其中一种格式写入。</span><span class="sxs-lookup"><span data-stu-id="a50cb-131">You can use fast UTF-8-based parsing and formatting methods in your converter logic if your input <xref:System.DateTime> or <xref:System.DateTimeOffset> text representations are compliant with one of the "R", "l", "O", or "G" [standard date and time format Strings](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings), or you want to write according to one of these formats.</span></span> <span data-ttu-id="a50cb-132">这比使用`DateTime(Offset).Parse`和`DateTime(Offset).ToString`更快。</span><span class="sxs-lookup"><span data-stu-id="a50cb-132">This is much faster than using `DateTime(Offset).Parse` and `DateTime(Offset).ToString`.</span></span>

<span data-ttu-id="a50cb-133">此示例演示一个自定义转换器，该转换器<xref:System.DateTime>根据["R" 标准格式](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-rfc1123-r-r-format-specifier)对值进行序列化和反序列化：</span><span class="sxs-lookup"><span data-stu-id="a50cb-133">This example shows a custom converter that serializes and deserializes <xref:System.DateTime> values according to [the "R" standard format](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-rfc1123-r-r-format-specifier):</span></span>

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> <span data-ttu-id="a50cb-134">"R" 标准格式的长度始终为29个字符。</span><span class="sxs-lookup"><span data-stu-id="a50cb-134">The "R" standard format will always be 29 characters long.</span></span>

### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a><span data-ttu-id="a50cb-135">使用`DateTime(Offset).Parse`作为序列化程序的本机解析的回退</span><span class="sxs-lookup"><span data-stu-id="a50cb-135">Using `DateTime(Offset).Parse` as a fallback to the serializer's native parsing</span></span>

<span data-ttu-id="a50cb-136">如果你通常希望输入<xref:System.DateTime>或<xref:System.DateTimeOffset>数据符合扩展 ISO 8601-1:2019 配置文件，则可以使用序列化程序的本机分析逻辑。</span><span class="sxs-lookup"><span data-stu-id="a50cb-136">If you generally expect your input <xref:System.DateTime> or <xref:System.DateTimeOffset> data to conform to the extended ISO 8601-1:2019 profile, you can use the serializer's native parsing logic.</span></span> <span data-ttu-id="a50cb-137">您还可以实现一种回退机制。</span><span class="sxs-lookup"><span data-stu-id="a50cb-137">You can also implement a fallback mechanism just in case.</span></span>
<span data-ttu-id="a50cb-138">此示例显示，在无法使用<xref:System.DateTime> <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>分析文本表示形式后，转换器使用<xref:System.DateTime.Parse(System.String)>成功分析数据。</span><span class="sxs-lookup"><span data-stu-id="a50cb-138">This example shows that, after failing to parse a <xref:System.DateTime> text representation using <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>, the converter successfully parses the data using <xref:System.DateTime.Parse(System.String)>.</span></span>

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example3/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a><span data-ttu-id="a50cb-139">系统中的扩展 ISO 8601-1:2019 配置文件</span><span class="sxs-lookup"><span data-stu-id="a50cb-139">The extended ISO 8601-1:2019 profile in System.Text.Json</span></span>

### <a name="date-and-time-components"></a><span data-ttu-id="a50cb-140">日期和时间组件</span><span class="sxs-lookup"><span data-stu-id="a50cb-140">Date and time components</span></span>

<span data-ttu-id="a50cb-141">在中<xref:System.Text.Json>实现的扩展 ISO 8601-1:2019 配置文件定义了日期和时间表示的以下组件。</span><span class="sxs-lookup"><span data-stu-id="a50cb-141">The extended ISO 8601-1:2019 profile implemented in <xref:System.Text.Json> defines the following components for date and time representations.</span></span> <span data-ttu-id="a50cb-142">这些组件用于定义分析和格式设置<xref:System.DateTime>和<xref:System.DateTimeOffset>表示形式时支持的各种粒度级别。</span><span class="sxs-lookup"><span data-stu-id="a50cb-142">These components are used to define various levels of granularity supported when parsing and formatting <xref:System.DateTime> and <xref:System.DateTimeOffset> representations.</span></span>

| <span data-ttu-id="a50cb-143">组件</span><span class="sxs-lookup"><span data-stu-id="a50cb-143">Component</span></span>       | <span data-ttu-id="a50cb-144">格式</span><span class="sxs-lookup"><span data-stu-id="a50cb-144">Format</span></span>                      | <span data-ttu-id="a50cb-145">描述</span><span class="sxs-lookup"><span data-stu-id="a50cb-145">Description</span></span>                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="a50cb-146">年</span><span class="sxs-lookup"><span data-stu-id="a50cb-146">Year</span></span>            | <span data-ttu-id="a50cb-147">“yyyy”</span><span class="sxs-lookup"><span data-stu-id="a50cb-147">"yyyy"</span></span>                      | <span data-ttu-id="a50cb-148">0001-9999</span><span class="sxs-lookup"><span data-stu-id="a50cb-148">0001-9999</span></span>                                                                       |
| <span data-ttu-id="a50cb-149">月份</span><span class="sxs-lookup"><span data-stu-id="a50cb-149">Month</span></span>           | <span data-ttu-id="a50cb-150">“MM”</span><span class="sxs-lookup"><span data-stu-id="a50cb-150">"MM"</span></span>                        | <span data-ttu-id="a50cb-151">01-12</span><span class="sxs-lookup"><span data-stu-id="a50cb-151">01-12</span></span>                                                                           |
| <span data-ttu-id="a50cb-152">Day</span><span class="sxs-lookup"><span data-stu-id="a50cb-152">Day</span></span>             | <span data-ttu-id="a50cb-153">“dd”</span><span class="sxs-lookup"><span data-stu-id="a50cb-153">"dd"</span></span>                        | <span data-ttu-id="a50cb-154">01-28、01-29、01-30、01-31 （基于月份/年份）</span><span class="sxs-lookup"><span data-stu-id="a50cb-154">01-28, 01-29, 01-30, 01-31 based on month/year</span></span>                                  |
| <span data-ttu-id="a50cb-155">Hour</span><span class="sxs-lookup"><span data-stu-id="a50cb-155">Hour</span></span>            | <span data-ttu-id="a50cb-156">“HH”</span><span class="sxs-lookup"><span data-stu-id="a50cb-156">"HH"</span></span>                        | <span data-ttu-id="a50cb-157">00-23</span><span class="sxs-lookup"><span data-stu-id="a50cb-157">00-23</span></span>                                                                           |
| <span data-ttu-id="a50cb-158">Minute</span><span class="sxs-lookup"><span data-stu-id="a50cb-158">Minute</span></span>          | <span data-ttu-id="a50cb-159">“mm”</span><span class="sxs-lookup"><span data-stu-id="a50cb-159">"mm"</span></span>                        | <span data-ttu-id="a50cb-160">00-59</span><span class="sxs-lookup"><span data-stu-id="a50cb-160">00-59</span></span>                                                                           |
| <span data-ttu-id="a50cb-161">第二个</span><span class="sxs-lookup"><span data-stu-id="a50cb-161">Second</span></span>          | <span data-ttu-id="a50cb-162">“ss”</span><span class="sxs-lookup"><span data-stu-id="a50cb-162">"ss"</span></span>                        | <span data-ttu-id="a50cb-163">00-59</span><span class="sxs-lookup"><span data-stu-id="a50cb-163">00-59</span></span>                                                                           |
| <span data-ttu-id="a50cb-164">第二部分</span><span class="sxs-lookup"><span data-stu-id="a50cb-164">Second fraction</span></span> | <span data-ttu-id="a50cb-165">“FFFFFFF”</span><span class="sxs-lookup"><span data-stu-id="a50cb-165">"FFFFFFF"</span></span>                   | <span data-ttu-id="a50cb-166">至少一个数字，最多为16位</span><span class="sxs-lookup"><span data-stu-id="a50cb-166">Minimum of one digit, maximum of 16 digits</span></span>                                      |
| <span data-ttu-id="a50cb-167">时间偏移</span><span class="sxs-lookup"><span data-stu-id="a50cb-167">Time offset</span></span>     | <span data-ttu-id="a50cb-168">“K”</span><span class="sxs-lookup"><span data-stu-id="a50cb-168">"K"</span></span>                         | <span data-ttu-id="a50cb-169">"Z" 或 "（" + "/"-"） HH"： "mm"</span><span class="sxs-lookup"><span data-stu-id="a50cb-169">Either "Z" or "('+'/'-')HH':'mm"</span></span>                                                |
| <span data-ttu-id="a50cb-170">部分时间</span><span class="sxs-lookup"><span data-stu-id="a50cb-170">Partial time</span></span>    | <span data-ttu-id="a50cb-171">"HH"： "mm"： "ss [FFFFFFF]"</span><span class="sxs-lookup"><span data-stu-id="a50cb-171">"HH':'mm':'ss[FFFFFFF]"</span></span>     | <span data-ttu-id="a50cb-172">不带 UTC 偏移信息的时间</span><span class="sxs-lookup"><span data-stu-id="a50cb-172">Time without UTC offset information</span></span>                                             |
| <span data-ttu-id="a50cb-173">完整日期</span><span class="sxs-lookup"><span data-stu-id="a50cb-173">Full date</span></span>       | <span data-ttu-id="a50cb-174">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-yyyy'-'mm'-'dd"</span><span class="sxs-lookup"><span data-stu-id="a50cb-174">"yyyy'-'MM'-'dd"</span></span>            | <span data-ttu-id="a50cb-175">日历日期</span><span class="sxs-lookup"><span data-stu-id="a50cb-175">Calendar date</span></span>                                                                   |
| <span data-ttu-id="a50cb-176">全部时间</span><span class="sxs-lookup"><span data-stu-id="a50cb-176">Full time</span></span>       | <span data-ttu-id="a50cb-177">"' Partial time'K"</span><span class="sxs-lookup"><span data-stu-id="a50cb-177">"'Partial time'K"</span></span>           | <span data-ttu-id="a50cb-178">一天中的 UTC 或本地时间与本地时间和 UTC 之间的时间偏移量</span><span class="sxs-lookup"><span data-stu-id="a50cb-178">UTC of day or Local time of day with the time offset between local time and UTC</span></span> |
| <span data-ttu-id="a50cb-179">日期时间</span><span class="sxs-lookup"><span data-stu-id="a50cb-179">Date time</span></span>       | <span data-ttu-id="a50cb-180">"" 完整时间 "不是" "完整时间" "</span><span class="sxs-lookup"><span data-stu-id="a50cb-180">"'Full date''T''Full time'"</span></span> | <span data-ttu-id="a50cb-181">日历日期和当天的时间，例如 2019-07-26T16：59： 57-05：00</span><span class="sxs-lookup"><span data-stu-id="a50cb-181">Calendar date and time of day, e.g. 2019-07-26T16:59:57-05:00</span></span>                   |

### <a name="support-for-parsing"></a><span data-ttu-id="a50cb-182">支持分析</span><span class="sxs-lookup"><span data-stu-id="a50cb-182">Support for parsing</span></span>

<span data-ttu-id="a50cb-183">定义以下级别的粒度：</span><span class="sxs-lookup"><span data-stu-id="a50cb-183">The following levels of granularity are defined for parsing:</span></span>

1. <span data-ttu-id="a50cb-184">"Full date"</span><span class="sxs-lookup"><span data-stu-id="a50cb-184">'Full date'</span></span>
    1. <span data-ttu-id="a50cb-185">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-yyyy'-'mm'-'dd"</span><span class="sxs-lookup"><span data-stu-id="a50cb-185">"yyyy'-'MM'-'dd"</span></span>

2. <span data-ttu-id="a50cb-186">"" 完整日期 "不是" "小时" "：" 分钟 "</span><span class="sxs-lookup"><span data-stu-id="a50cb-186">"'Full date''T''Hour'':''Minute'"</span></span>
    1. <span data-ttu-id="a50cb-187">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"</span><span class="sxs-lookup"><span data-stu-id="a50cb-187">"yyyy'-'MM'-'dd'T'HH':'mm"</span></span>

3. <span data-ttu-id="a50cb-188">"" 完整日期 "不是" "部分时间" "</span><span class="sxs-lookup"><span data-stu-id="a50cb-188">"'Full date''T''Partial time'"</span></span>
    1. <span data-ttu-id="a50cb-189">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ss" （可[排序（"s"）格式说明符](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier)）</span><span class="sxs-lookup"><span data-stu-id="a50cb-189">"yyyy'-'MM'-'dd'T'HH':'mm':'ss" ([The Sortable ("s") Format Specifier](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))</span></span>
    2. <span data-ttu-id="a50cb-190">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ss"。FFFFFFF</span><span class="sxs-lookup"><span data-stu-id="a50cb-190">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF"</span></span>

4. <span data-ttu-id="a50cb-191">"" 完整日期 "不是" "，时间小时" "：" "分钟" "时间偏移" "</span><span class="sxs-lookup"><span data-stu-id="a50cb-191">"'Full date''T''Time hour'':''Minute''Time offset'"</span></span>
    1. <span data-ttu-id="a50cb-192">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "mmZ"</span><span class="sxs-lookup"><span data-stu-id="a50cb-192">"yyyy'-'MM'-'dd'T'HH':'mmZ"</span></span>
    2. <span data-ttu-id="a50cb-193">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "mm （' + '/'-'） HH '： ' mm"</span><span class="sxs-lookup"><span data-stu-id="a50cb-193">"yyyy'-'MM'-'dd'T'HH':'mm('+'/'-')HH':'mm"</span></span>

5. <span data-ttu-id="a50cb-194">"日期时间"</span><span class="sxs-lookup"><span data-stu-id="a50cb-194">'Date time'</span></span>
    1. <span data-ttu-id="a50cb-195">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ssZ"</span><span class="sxs-lookup"><span data-stu-id="a50cb-195">"yyyy'-'MM'-'dd'T'HH':'mm':'ssZ"</span></span>
    2. <span data-ttu-id="a50cb-196">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ss"。FFFFFFFZ"</span><span class="sxs-lookup"><span data-stu-id="a50cb-196">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFFZ"</span></span>
    3. <span data-ttu-id="a50cb-197">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' MM '： ' ss （' + '/'-'） HH '： ' MM"</span><span class="sxs-lookup"><span data-stu-id="a50cb-197">"yyyy'-'MM'-'dd'T'HH':'mm':'ss('+'/'-')HH':'mm"</span></span>
    4. <span data-ttu-id="a50cb-198">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ss"。FFFFFFF （"+"/"-"） HH "：" mm "</span><span class="sxs-lookup"><span data-stu-id="a50cb-198">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF('+'/'-')HH':'mm"</span></span>

<span data-ttu-id="a50cb-199">如果有秒的小数部分，则必须至少有一个数字;`2019-07-26T00:00:00.`不允许。</span><span class="sxs-lookup"><span data-stu-id="a50cb-199">If there are decimal fractions for seconds, there must be at least one digit; `2019-07-26T00:00:00.` is not allowed.</span></span>
<span data-ttu-id="a50cb-200">尽管允许最多包含16个小数位，但仅分析前7个小数。</span><span class="sxs-lookup"><span data-stu-id="a50cb-200">While up to 16 fractional digits are allowed, only the first seven are parsed.</span></span> <span data-ttu-id="a50cb-201">超出的任何内容都将被视为零。</span><span class="sxs-lookup"><span data-stu-id="a50cb-201">Anything beyond that is considered a zero.</span></span>
<span data-ttu-id="a50cb-202">例如， `2019-07-26T00:00:00.1234567890`将按`2019-07-26T00:00:00.1234567`原样进行分析。</span><span class="sxs-lookup"><span data-stu-id="a50cb-202">For example, `2019-07-26T00:00:00.1234567890` will be parsed as if it is `2019-07-26T00:00:00.1234567`.</span></span>
<span data-ttu-id="a50cb-203">这是为了保持与<xref:System.DateTime>实现的兼容性，这仅限于此解决方案。</span><span class="sxs-lookup"><span data-stu-id="a50cb-203">This is to stay compatible with the <xref:System.DateTime> implementation, which is limited to this resolution.</span></span>

<span data-ttu-id="a50cb-204">不支持闰秒。</span><span class="sxs-lookup"><span data-stu-id="a50cb-204">Leap seconds are not supported.</span></span>

### <a name="support-for-formatting"></a><span data-ttu-id="a50cb-205">支持格式设置</span><span class="sxs-lookup"><span data-stu-id="a50cb-205">Support for formatting</span></span>

<span data-ttu-id="a50cb-206">为格式化定义了下列粒度级别：</span><span class="sxs-lookup"><span data-stu-id="a50cb-206">The following levels of granularity are defined for formatting:</span></span>

1. <span data-ttu-id="a50cb-207">"" 完整日期 "不是" "部分时间" "</span><span class="sxs-lookup"><span data-stu-id="a50cb-207">"'Full date''T''Partial time'"</span></span>
    1. <span data-ttu-id="a50cb-208">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ss" （可[排序（"s"）格式说明符](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier)）</span><span class="sxs-lookup"><span data-stu-id="a50cb-208">"yyyy'-'MM'-'dd'T'HH':'mm':'ss"  ([The Sortable ("s") Format Specifier](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))</span></span>

        <span data-ttu-id="a50cb-209">用于设置不包含<xref:System.DateTime>秒的小数部分和不含偏移量信息的格式。</span><span class="sxs-lookup"><span data-stu-id="a50cb-209">Used to format a <xref:System.DateTime> without fractional seconds and without offset information.</span></span>

    2. <span data-ttu-id="a50cb-210">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ss"。FFFFFFF</span><span class="sxs-lookup"><span data-stu-id="a50cb-210">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF"</span></span>

        <span data-ttu-id="a50cb-211">用于设置带小数<xref:System.DateTime>秒但不含偏移信息的的格式。</span><span class="sxs-lookup"><span data-stu-id="a50cb-211">Used to format a <xref:System.DateTime> with fractional seconds but without offset information.</span></span>

2. <span data-ttu-id="a50cb-212">"日期时间"</span><span class="sxs-lookup"><span data-stu-id="a50cb-212">'Date time'</span></span>
    1. <span data-ttu-id="a50cb-213">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ssZ"</span><span class="sxs-lookup"><span data-stu-id="a50cb-213">"yyyy'-'MM'-'dd'T'HH':'mm':'ssZ"</span></span>

        <span data-ttu-id="a50cb-214">用于设置<xref:System.DateTime>或<xref:System.DateTimeOffset>不包含秒的小数部分，但使用 UTC 偏移量。</span><span class="sxs-lookup"><span data-stu-id="a50cb-214">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> without fractional seconds but with a UTC offset.</span></span>

    2. <span data-ttu-id="a50cb-215">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ss"。FFFFFFFZ"</span><span class="sxs-lookup"><span data-stu-id="a50cb-215">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFFZ"</span></span>

        <span data-ttu-id="a50cb-216">用于设置<xref:System.DateTime>或<xref:System.DateTimeOffset>的小数部分的格式，且具有 UTC 偏移量。</span><span class="sxs-lookup"><span data-stu-id="a50cb-216">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> with fractional seconds and with a UTC offset.</span></span>

    3. <span data-ttu-id="a50cb-217">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh '： ' MM '： ' ss （' + '/'-'） HH '： ' MM"</span><span class="sxs-lookup"><span data-stu-id="a50cb-217">"yyyy'-'MM'-'dd'T'HH':'mm':'ss('+'/'-')HH':'mm"</span></span>

        <span data-ttu-id="a50cb-218">用于设置<xref:System.DateTime>或<xref:System.DateTimeOffset>不包含秒的小数部分，但使用本地偏移量。</span><span class="sxs-lookup"><span data-stu-id="a50cb-218">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> without fractional seconds but with a local offset.</span></span>

    4. <span data-ttu-id="a50cb-219">"yyyy'-'mm'-'dd't'hh-YYYY'-'MM'-'DD'T'HH-Yyyy'-'mm'-'dd't'hh"： "MM"： "ss"。FFFFFFF （"+"/"-"） HH "：" mm "</span><span class="sxs-lookup"><span data-stu-id="a50cb-219">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF('+'/'-')HH':'mm"</span></span>

        <span data-ttu-id="a50cb-220">用于设置<xref:System.DateTime>或的小数<xref:System.DateTimeOffset>部分或局部偏移量的格式。</span><span class="sxs-lookup"><span data-stu-id="a50cb-220">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> with fractional seconds and with a local offset.</span></span>
