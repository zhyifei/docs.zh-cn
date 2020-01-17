---
title: 从 Newtonsoft.json 迁移到 system.exception-.NET
author: tdykstra
ms.author: tdykstra
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 01f94bcfce97da8c71b1b709baa34c2b7509a5e5
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116683"
---
# <a name="how-to-migrate-from-newtonsoftjson-to-systemtextjson"></a><span data-ttu-id="c8395-102">如何从 Newtonsoft.json 迁移到 system.exception</span><span class="sxs-lookup"><span data-stu-id="c8395-102">How to migrate from Newtonsoft.Json to System.Text.Json</span></span>

<span data-ttu-id="c8395-103">本文介绍如何从[newtonsoft.json](https://www.newtonsoft.com/json)迁移到 <xref:System.Text.Json>。</span><span class="sxs-lookup"><span data-stu-id="c8395-103">This article shows how to migrate from [Newtonsoft.Json](https://www.newtonsoft.com/json) to <xref:System.Text.Json>.</span></span>

 <span data-ttu-id="c8395-104">`System.Text.Json` 主要侧重于性能、安全性和标准符合性。</span><span class="sxs-lookup"><span data-stu-id="c8395-104">`System.Text.Json` focuses primarily on performance, security, and standards compliance.</span></span> <span data-ttu-id="c8395-105">它在默认行为方面有一些重要差异，并且不会使功能与 `Newtonsoft.Json`具有相同的功能。</span><span class="sxs-lookup"><span data-stu-id="c8395-105">It has some key differences in default behavior and doesn't aim to have feature parity with `Newtonsoft.Json`.</span></span> <span data-ttu-id="c8395-106">在某些情况下，`System.Text.Json` 没有内置功能，但存在建议的解决方法。</span><span class="sxs-lookup"><span data-stu-id="c8395-106">For some scenarios, `System.Text.Json` has no built-in functionality, but there are recommended workarounds.</span></span> <span data-ttu-id="c8395-107">对于其他情况，解决方法是不切实际的。</span><span class="sxs-lookup"><span data-stu-id="c8395-107">For other scenarios, workarounds are impractical.</span></span> <span data-ttu-id="c8395-108">如果你的应用程序依赖于缺少的功能，请考虑[归档问题](https://github.com/dotnet/runtime/issues/new)，以了解是否可以添加对你的方案的支持。</span><span class="sxs-lookup"><span data-stu-id="c8395-108">If your application depends on a missing feature, consider [filing an issue](https://github.com/dotnet/runtime/issues/new) to find out if support for your scenario can be added.</span></span>

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

<span data-ttu-id="c8395-109">本文的大部分内容介绍如何使用 <xref:System.Text.Json.JsonSerializer> API，但它还包括有关如何使用 <xref:System.Text.Json.JsonDocument> （表示文档对象模型或 DOM）、<xref:System.Text.Json.Utf8JsonReader>和 <xref:System.Text.Json.Utf8JsonWriter> 类型的指导。</span><span class="sxs-lookup"><span data-stu-id="c8395-109">Most of this article is about how to use the <xref:System.Text.Json.JsonSerializer> API, but it also includes guidance on how to use the <xref:System.Text.Json.JsonDocument> (which represents the Document Object Model or DOM), <xref:System.Text.Json.Utf8JsonReader>, and <xref:System.Text.Json.Utf8JsonWriter> types.</span></span> <span data-ttu-id="c8395-110">本文按以下顺序划分为多个部分：</span><span class="sxs-lookup"><span data-stu-id="c8395-110">The article is organized into sections in the following order:</span></span>

* [<span data-ttu-id="c8395-111">与 Newtonsoft.json 相比，**默认**JsonSerializer 行为的差异</span><span class="sxs-lookup"><span data-stu-id="c8395-111">Differences in **default** JsonSerializer behavior compared to Newtonsoft.Json</span></span>](#differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson)
* [<span data-ttu-id="c8395-112">使用需要解决方法的 JsonSerializer 的方案</span><span class="sxs-lookup"><span data-stu-id="c8395-112">Scenarios using JsonSerializer that require workarounds</span></span>](#scenarios-using-jsonserializer-that-require-workarounds)
* [<span data-ttu-id="c8395-113">JsonSerializer 当前不支持的方案</span><span class="sxs-lookup"><span data-stu-id="c8395-113">Scenarios that JsonSerializer currently doesn't support</span></span>](#scenarios-that-jsonserializer-currently-doesnt-support)
* [<span data-ttu-id="c8395-114">与 JToken 相比，JsonDocument 和 JsonElement （例如 JObject、JArray）</span><span class="sxs-lookup"><span data-stu-id="c8395-114">JsonDocument and JsonElement compared to JToken (like JObject, JArray)</span></span>](#jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray)
* [<span data-ttu-id="c8395-115">Utf8JsonReader 与 JsonTextReader 的比较</span><span class="sxs-lookup"><span data-stu-id="c8395-115">Utf8JsonReader compared to JsonTextReader</span></span>](#utf8jsonreader-compared-to-jsontextreader)
* [<span data-ttu-id="c8395-116">Utf8JsonWriter 与 JsonTextWriter 的比较</span><span class="sxs-lookup"><span data-stu-id="c8395-116">Utf8JsonWriter compared to JsonTextWriter</span></span>](#utf8jsonwriter-compared-to-jsontextwriter)

## <a name="differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson"></a><span data-ttu-id="c8395-117">与 Newtonsoft.json 相比，默认 JsonSerializer 行为的差异</span><span class="sxs-lookup"><span data-stu-id="c8395-117">Differences in default JsonSerializer behavior compared to Newtonsoft.Json</span></span>

<span data-ttu-id="c8395-118">默认情况下，<xref:System.Text.Json> 是严格的，它可以避免代表调用方的任何猜测或解释，强调确定的行为。</span><span class="sxs-lookup"><span data-stu-id="c8395-118"><xref:System.Text.Json> is strict by default and avoids any guessing or interpretation on the caller's behalf, emphasizing deterministic behavior.</span></span> <span data-ttu-id="c8395-119">此库是以这种方式特意设计的，用于提高性能和安全性。</span><span class="sxs-lookup"><span data-stu-id="c8395-119">The library is intentionally designed this way for performance and security.</span></span> <span data-ttu-id="c8395-120">默认情况下，`Newtonsoft.Json` 是灵活的。</span><span class="sxs-lookup"><span data-stu-id="c8395-120">`Newtonsoft.Json` is flexible by default.</span></span> <span data-ttu-id="c8395-121">这种设计的根本差别在于默认行为中的许多特定差异。</span><span class="sxs-lookup"><span data-stu-id="c8395-121">This fundamental difference in design is behind many of the following specific differences in default behavior.</span></span>

### <a name="case-insensitive-deserialization"></a><span data-ttu-id="c8395-122">不区分大小写的反序列化</span><span class="sxs-lookup"><span data-stu-id="c8395-122">Case-insensitive deserialization</span></span> 

<span data-ttu-id="c8395-123">在反序列化过程中，默认情况下 `Newtonsoft.Json` 不区分大小写的属性名称匹配。</span><span class="sxs-lookup"><span data-stu-id="c8395-123">During deserialization, `Newtonsoft.Json` does case-insensitive property name matching by default.</span></span> <span data-ttu-id="c8395-124"><xref:System.Text.Json> 的默认值是区分大小写的，这将提供更好的性能，因为它执行完全匹配。</span><span class="sxs-lookup"><span data-stu-id="c8395-124">The <xref:System.Text.Json> default is case-sensitive, which gives better performance since it's doing an exact match.</span></span> <span data-ttu-id="c8395-125">有关如何执行不区分大小写的匹配的信息，请参阅不区分[大小写的属性匹配](system-text-json-how-to.md#case-insensitive-property-matching)。</span><span class="sxs-lookup"><span data-stu-id="c8395-125">For information about how to do case-insensitive matching, see [Case-insensitive property matching](system-text-json-how-to.md#case-insensitive-property-matching).</span></span>

<span data-ttu-id="c8395-126">如果使用 ASP.NET Core 间接使用 `System.Text.Json`，则无需执行任何操作，如 `Newtonsoft.Json`。</span><span class="sxs-lookup"><span data-stu-id="c8395-126">If you're using `System.Text.Json` indirectly by using ASP.NET Core, you don't need to do anything to get behavior like `Newtonsoft.Json`.</span></span> <span data-ttu-id="c8395-127">ASP.NET Core 指定[camel 大小写属性名称](system-text-json-how-to.md#use-camel-case-for-all-json-property-names)和不区分大小写的匹配项在使用 `System.Text.Json`时的设置。</span><span class="sxs-lookup"><span data-stu-id="c8395-127">ASP.NET Core specifies the settings for [camel-casing property names](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) and case-insensitive matching when it uses `System.Text.Json`.</span></span>

### <a name="comments"></a><span data-ttu-id="c8395-128">Comments</span><span class="sxs-lookup"><span data-stu-id="c8395-128">Comments</span></span>

<span data-ttu-id="c8395-129">在反序列化过程中，默认情况下 `Newtonsoft.Json` 忽略 JSON 中的注释。</span><span class="sxs-lookup"><span data-stu-id="c8395-129">During deserialization, `Newtonsoft.Json` ignores comments in the JSON by default.</span></span> <span data-ttu-id="c8395-130">默认情况下，<xref:System.Text.Json> 会引发注释异常，因为[RFC 8259](https://tools.ietf.org/html/rfc8259)规范不包含它们。</span><span class="sxs-lookup"><span data-stu-id="c8395-130">The <xref:System.Text.Json> default is to throw exceptions for comments because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't include them.</span></span> <span data-ttu-id="c8395-131">有关如何允许注释的信息，请参阅[允许注释和尾随逗号](system-text-json-how-to.md#allow-comments-and-trailing-commas)。</span><span class="sxs-lookup"><span data-stu-id="c8395-131">For information about how to allow comments, see [Allow comments and trailing commas](system-text-json-how-to.md#allow-comments-and-trailing-commas).</span></span>

### <a name="trailing-commas"></a><span data-ttu-id="c8395-132">尾随逗号</span><span class="sxs-lookup"><span data-stu-id="c8395-132">Trailing commas</span></span>

<span data-ttu-id="c8395-133">在反序列化过程中，默认情况下 `Newtonsoft.Json` 忽略尾随逗号。</span><span class="sxs-lookup"><span data-stu-id="c8395-133">During deserialization, `Newtonsoft.Json` ignores trailing commas by default.</span></span> <span data-ttu-id="c8395-134">它还会忽略多个尾随逗号（例如 `[{"Color":"Red"},{"Color":"Green"},,]`）。</span><span class="sxs-lookup"><span data-stu-id="c8395-134">It also ignores multiple trailing commas (for example, `[{"Color":"Red"},{"Color":"Green"},,]`).</span></span> <span data-ttu-id="c8395-135">默认情况下，<xref:System.Text.Json> 会引发尾随逗号的异常，因为[RFC 8259](https://tools.ietf.org/html/rfc8259)规范不允许这样做。</span><span class="sxs-lookup"><span data-stu-id="c8395-135">The <xref:System.Text.Json> default is to throw exceptions for trailing commas because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't allow them.</span></span> <span data-ttu-id="c8395-136">有关如何使 `System.Text.Json` 接受它们的信息，请参阅[允许注释和尾随逗号](system-text-json-how-to.md#allow-comments-and-trailing-commas)。</span><span class="sxs-lookup"><span data-stu-id="c8395-136">For information about how to make `System.Text.Json` accept them, see [Allow comments and trailing commas](system-text-json-how-to.md#allow-comments-and-trailing-commas).</span></span> <span data-ttu-id="c8395-137">没有办法允许多个尾随逗号。</span><span class="sxs-lookup"><span data-stu-id="c8395-137">There's no way to allow multiple trailing commas.</span></span>

### <a name="json-strings-property-names-and-string-values"></a><span data-ttu-id="c8395-138">JSON 字符串（属性名称和字符串值）</span><span class="sxs-lookup"><span data-stu-id="c8395-138">JSON strings (property names and string values)</span></span>

<span data-ttu-id="c8395-139">在反序列化期间，`Newtonsoft.Json` 接受用双引号引起来的属性名称、单引号或不带引号。</span><span class="sxs-lookup"><span data-stu-id="c8395-139">During deserialization, `Newtonsoft.Json` accepts property names surrounded by double quotes, single quotes, or without quotes.</span></span> <span data-ttu-id="c8395-140">它接受括在双引号或单引号中的字符串值。</span><span class="sxs-lookup"><span data-stu-id="c8395-140">It accepts string values surrounded by double quotes or single quotes.</span></span> <span data-ttu-id="c8395-141">例如，`Newtonsoft.Json` 接受以下 JSON：</span><span class="sxs-lookup"><span data-stu-id="c8395-141">For example, `Newtonsoft.Json` accepts the following JSON:</span></span>

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

<span data-ttu-id="c8395-142">`System.Text.Json` 仅接受双引号中的属性名称和字符串值，因为[RFC 8259](https://tools.ietf.org/html/rfc8259)规范要求使用该格式，这是唯一视为有效 JSON 的格式。</span><span class="sxs-lookup"><span data-stu-id="c8395-142">`System.Text.Json` only accepts property names and string values in double quotes because that format is required by the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification and is the only format considered valid JSON.</span></span>

<span data-ttu-id="c8395-143">用单引号括起来的值会导致[JsonException](xref:System.Text.Json.JsonException) ，并出现以下消息：</span><span class="sxs-lookup"><span data-stu-id="c8395-143">A value enclosed in single quotes results in a [JsonException](xref:System.Text.Json.JsonException) with the following message:</span></span>

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a><span data-ttu-id="c8395-144">字符串属性的非字符串值</span><span class="sxs-lookup"><span data-stu-id="c8395-144">Non-string values for string properties</span></span>

<span data-ttu-id="c8395-145">`Newtonsoft.Json` 接受非字符串值（如数字或文本 `true` 和 `false`），以便反序列化到类型字符串的属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-145">`Newtonsoft.Json` accepts non-string values, such as a number or the literals `true` and `false`, for deserialization to properties of type string.</span></span> <span data-ttu-id="c8395-146">下面是 `Newtonsoft.Json` 成功反序列化为以下类的 JSON 示例：</span><span class="sxs-lookup"><span data-stu-id="c8395-146">Here's an example of JSON that `Newtonsoft.Json` successfully deserializes to the following class:</span></span>

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

<span data-ttu-id="c8395-147">`System.Text.Json` 不会将非字符串值反序列化为字符串属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-147">`System.Text.Json` doesn't deserialize non-string values into string properties.</span></span> <span data-ttu-id="c8395-148">为字符串字段接收的非字符串值会导致[JsonException](xref:System.Text.Json.JsonException) ，并出现以下消息：</span><span class="sxs-lookup"><span data-stu-id="c8395-148">A non-string value received for a string field results in a [JsonException](xref:System.Text.Json.JsonException) with the following message:</span></span>

```
The JSON value could not be converted to System.String.
```

### <a name="converter-registration-precedence"></a><span data-ttu-id="c8395-149">转换器注册优先顺序</span><span class="sxs-lookup"><span data-stu-id="c8395-149">Converter registration precedence</span></span>

<span data-ttu-id="c8395-150">自定义转换器的 `Newtonsoft.Json` 注册优先级如下：</span><span class="sxs-lookup"><span data-stu-id="c8395-150">The `Newtonsoft.Json` registration precedence for custom converters is as follows:</span></span>

* <span data-ttu-id="c8395-151">属性上的属性</span><span class="sxs-lookup"><span data-stu-id="c8395-151">Attribute on property</span></span>
* <span data-ttu-id="c8395-152">类型上的属性</span><span class="sxs-lookup"><span data-stu-id="c8395-152">Attribute on type</span></span>
* <span data-ttu-id="c8395-153">[转换器](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm)集合</span><span class="sxs-lookup"><span data-stu-id="c8395-153">[Converters](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm) collection</span></span>

<span data-ttu-id="c8395-154">此顺序意味着 `Converters` 集合中的自定义转换器由通过在类型级别应用特性而注册的转换器重写。</span><span class="sxs-lookup"><span data-stu-id="c8395-154">This order means that a custom converter in the `Converters` collection is overridden by a converter that is registered by applying an attribute at the type level.</span></span> <span data-ttu-id="c8395-155">这两个注册都由属性级别的特性重写。</span><span class="sxs-lookup"><span data-stu-id="c8395-155">Both of those registrations are overridden by an attribute at the property level.</span></span>

<span data-ttu-id="c8395-156">自定义转换器的 <xref:System.Text.Json> 注册优先级不同：</span><span class="sxs-lookup"><span data-stu-id="c8395-156">The <xref:System.Text.Json> registration precedence for custom converters is different:</span></span>

* <span data-ttu-id="c8395-157">属性上的属性</span><span class="sxs-lookup"><span data-stu-id="c8395-157">Attribute on property</span></span>
* <span data-ttu-id="c8395-158"><xref:System.Text.Json.JsonSerializerOptions.Converters> 集合</span><span class="sxs-lookup"><span data-stu-id="c8395-158"><xref:System.Text.Json.JsonSerializerOptions.Converters> collection</span></span>
* <span data-ttu-id="c8395-159">类型上的属性</span><span class="sxs-lookup"><span data-stu-id="c8395-159">Attribute on type</span></span>

<span data-ttu-id="c8395-160">此处的差别在于 `Converters` 集合中的自定义转换器将覆盖类型级别的特性。</span><span class="sxs-lookup"><span data-stu-id="c8395-160">The difference here is that a custom converter in the `Converters` collection overrides an attribute at the type level.</span></span> <span data-ttu-id="c8395-161">此优先顺序的目的是使运行时更改覆盖设计时选项。</span><span class="sxs-lookup"><span data-stu-id="c8395-161">The intention behind this order of precedence is to make run-time changes override design-time choices.</span></span> <span data-ttu-id="c8395-162">无法更改优先级。</span><span class="sxs-lookup"><span data-stu-id="c8395-162">There's no way to change the precedence.</span></span>

<span data-ttu-id="c8395-163">有关自定义转换器注册的详细信息，请参阅[注册自定义转换器](system-text-json-converters-how-to.md#register-a-custom-converter)。</span><span class="sxs-lookup"><span data-stu-id="c8395-163">For more information about custom converter registration, see [Register a custom converter](system-text-json-converters-how-to.md#register-a-custom-converter).</span></span>

### <a name="character-escaping"></a><span data-ttu-id="c8395-164">字符转义</span><span class="sxs-lookup"><span data-stu-id="c8395-164">Character escaping</span></span>

<span data-ttu-id="c8395-165">在序列化过程中，`Newtonsoft.Json` 相对的方式是让字符通过而不进行转义。</span><span class="sxs-lookup"><span data-stu-id="c8395-165">During serialization, `Newtonsoft.Json` is relatively permissive about letting characters through without escaping them.</span></span> <span data-ttu-id="c8395-166">也就是说，它不会将它们替换为 `\uxxxx`，其中 `xxxx` 为字符的码位。</span><span class="sxs-lookup"><span data-stu-id="c8395-166">That is, it doesn't replace them with `\uxxxx` where `xxxx` is the character's code point.</span></span> <span data-ttu-id="c8395-167">如果它被转义，它会通过在字符前发出 `\` （例如，`"` 变为 `\"`）来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="c8395-167">Where it does escape them, it does so by emitting a `\` before the character (for example, `"` becomes `\"`).</span></span> <span data-ttu-id="c8395-168">默认情况下，<xref:System.Text.Json> 转义更多字符，以对跨站点脚本（XSS）或信息泄露攻击提供深层防御保护，并使用六个字符的序列执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c8395-168"><xref:System.Text.Json> escapes more characters by default to provide defense-in-depth protections against cross-site scripting (XSS) or information-disclosure attacks and does so by using the six-character sequence.</span></span> <span data-ttu-id="c8395-169">默认情况下，`System.Text.Json` 转义所有非 ASCII 字符，因此，如果在 `Newtonsoft.Json`中使用 `StringEscapeHandling.EscapeNonAscii`，则无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="c8395-169">`System.Text.Json` escapes all non-ASCII characters by default, so you don't need to do anything if you're using `StringEscapeHandling.EscapeNonAscii` in `Newtonsoft.Json`.</span></span> <span data-ttu-id="c8395-170">默认情况下，`System.Text.Json` 还会对 HTML 敏感字符进行转义。</span><span class="sxs-lookup"><span data-stu-id="c8395-170">`System.Text.Json` also escapes HTML-sensitive characters, by default.</span></span> <span data-ttu-id="c8395-171">有关如何重写默认 `System.Text.Json` 行为的信息，请参阅[自定义字符编码](system-text-json-how-to.md#customize-character-encoding)。</span><span class="sxs-lookup"><span data-stu-id="c8395-171">For information about how to override the default `System.Text.Json` behavior, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="deserialization-of-object-properties"></a><span data-ttu-id="c8395-172">对象属性的反序列化</span><span class="sxs-lookup"><span data-stu-id="c8395-172">Deserialization of object properties</span></span>

<span data-ttu-id="c8395-173">`Newtonsoft.Json` 反序列化到类型 `Dictionary<string, object>`的 Poco 或字典中 `object` 属性时，它：</span><span class="sxs-lookup"><span data-stu-id="c8395-173">When `Newtonsoft.Json` deserializes to `object` properties in POCOs or in dictionaries of type `Dictionary<string, object>`, it:</span></span>

* <span data-ttu-id="c8395-174">推断 JSON 负载中的基元值的类型（不是 `null`），并以装箱对象的形式返回存储的 `string`、`long`、`double`、`boolean`或 `DateTime`。</span><span class="sxs-lookup"><span data-stu-id="c8395-174">Infers the type of primitive values in the JSON payload (other than `null`) and returns the stored `string`, `long`, `double`, `boolean`, or `DateTime` as a boxed object.</span></span> <span data-ttu-id="c8395-175">*基元值*是单个 json 值，如 json 数字、字符串、`true`、`false`或 `null`。</span><span class="sxs-lookup"><span data-stu-id="c8395-175">*Primitive values* are single JSON values such as a JSON number, string, `true`, `false`, or `null`.</span></span>
* <span data-ttu-id="c8395-176">为 JSON 有效负载中的复杂值返回 `JObject` 或 `JArray`。</span><span class="sxs-lookup"><span data-stu-id="c8395-176">Returns a `JObject` or `JArray` for complex values in the JSON payload.</span></span> <span data-ttu-id="c8395-177">*复杂值*是括在大括号（`{}`）中的 JSON 键/值对的集合或括号（`[]`）中的值列表。</span><span class="sxs-lookup"><span data-stu-id="c8395-177">*Complex values* are collections of JSON key-value pairs within braces (`{}`) or lists of values within brackets (`[]`).</span></span> <span data-ttu-id="c8395-178">大括号或大括号中的属性和值可以有其他属性或值。</span><span class="sxs-lookup"><span data-stu-id="c8395-178">The properties and values within the braces or brackets can have additional properties or values.</span></span>
* <span data-ttu-id="c8395-179">如果有效负载具有 `null` JSON 文本，则返回空引用。</span><span class="sxs-lookup"><span data-stu-id="c8395-179">Returns a null reference when the payload has the `null` JSON literal.</span></span>

<span data-ttu-id="c8395-180"><xref:System.Text.Json> 在 `System.Object` 属性或字典值中存储基元和复杂值的已装箱 `JsonElement`。</span><span class="sxs-lookup"><span data-stu-id="c8395-180"><xref:System.Text.Json> stores a boxed `JsonElement` for both primitive and complex values within the `System.Object` property or dictionary value.</span></span> <span data-ttu-id="c8395-181">但是，它将 `null` 视为 `Newtonsoft.Json`，并在有效负载中具有 `null` JSON 文本时返回空引用。</span><span class="sxs-lookup"><span data-stu-id="c8395-181">However, it treats `null` the same as `Newtonsoft.Json` and returns a null reference when the payload has the `null` JSON literal in it.</span></span>

<span data-ttu-id="c8395-182">若要实现 `object` 属性的类型推理，请创建一个转换器，如[如何编写自定义转换器](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties)中的示例。</span><span class="sxs-lookup"><span data-stu-id="c8395-182">To implement type inference for `object` properties, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).</span></span>

### <a name="maximum-depth"></a><span data-ttu-id="c8395-183">最大深度</span><span class="sxs-lookup"><span data-stu-id="c8395-183">Maximum depth</span></span>

<span data-ttu-id="c8395-184">默认情况下，`Newtonsoft.Json` 没有最大深度限制。</span><span class="sxs-lookup"><span data-stu-id="c8395-184">`Newtonsoft.Json` doesn't have a maximum depth limit by default.</span></span> <span data-ttu-id="c8395-185">对于 <xref:System.Text.Json>，默认限制为64，可通过设置 <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>进行配置。</span><span class="sxs-lookup"><span data-stu-id="c8395-185">For <xref:System.Text.Json> there's a default limit  of 64, and it's configurable by setting <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>.</span></span>

### <a name="omit-null-value-properties"></a><span data-ttu-id="c8395-186">省略 null 值属性</span><span class="sxs-lookup"><span data-stu-id="c8395-186">Omit null-value properties</span></span>

<span data-ttu-id="c8395-187">`Newtonsoft.Json` 具有一个全局设置，该设置会导致从序列化中排除 null 值属性： [NullValueHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_NullValueHandling.htm)。</span><span class="sxs-lookup"><span data-stu-id="c8395-187">`Newtonsoft.Json` has a global setting that causes null-value properties to be excluded from serialization: [NullValueHandling.Ignore](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_NullValueHandling.htm).</span></span> <span data-ttu-id="c8395-188"><xref:System.Text.Json> 中的相应选项 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues%2A>。</span><span class="sxs-lookup"><span data-stu-id="c8395-188">The corresponding option in <xref:System.Text.Json> is <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues%2A>.</span></span>

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a><span data-ttu-id="c8395-189">使用需要解决方法的 JsonSerializer 的方案</span><span class="sxs-lookup"><span data-stu-id="c8395-189">Scenarios using JsonSerializer that require workarounds</span></span>

<span data-ttu-id="c8395-190">内置功能不支持以下方案，但提供了有关解决方法的示例代码。</span><span class="sxs-lookup"><span data-stu-id="c8395-190">The following scenarios aren't supported by built-in functionality, but sample code is provided for workarounds.</span></span> <span data-ttu-id="c8395-191">大多数解决方法要求您实现[自定义转换器](system-text-json-converters-how-to.md)。</span><span class="sxs-lookup"><span data-stu-id="c8395-191">Most of the workarounds require that you implement [custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="specify-date-format"></a><span data-ttu-id="c8395-192">指定日期格式</span><span class="sxs-lookup"><span data-stu-id="c8395-192">Specify date format</span></span>

<span data-ttu-id="c8395-193">`Newtonsoft.Json` 提供多种方法来控制如何序列化和反序列化 `DateTime` 和 `DateTimeOffset` 类型的属性：</span><span class="sxs-lookup"><span data-stu-id="c8395-193">`Newtonsoft.Json` provides several ways to control how properties of `DateTime` and `DateTimeOffset` types are serialized and deserialized:</span></span>

* <span data-ttu-id="c8395-194">`DateTimeZoneHandling` 设置可用于将所有 `DateTime` 值序列化为 UTC 日期。</span><span class="sxs-lookup"><span data-stu-id="c8395-194">The `DateTimeZoneHandling` setting can be used to serialize all `DateTime` values as UTC dates.</span></span>
* <span data-ttu-id="c8395-195">`DateFormatString` 设置和 `DateTime` 转换器可用于自定义日期字符串的格式。</span><span class="sxs-lookup"><span data-stu-id="c8395-195">The `DateFormatString` setting and `DateTime` converters can be used to customize the format of date strings.</span></span>

<span data-ttu-id="c8395-196">在 <xref:System.Text.Json>中，具有内置支持的唯一格式是 ISO 8601-1:2019，因为它被广泛采用、明确地利用，并准确地进行往返。</span><span class="sxs-lookup"><span data-stu-id="c8395-196">In <xref:System.Text.Json>, the only format that has built-in support is ISO 8601-1:2019 since it's widely adopted, unambiguous, and makes round trips precisely.</span></span> <span data-ttu-id="c8395-197">若要使用任何其他格式，请创建自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="c8395-197">To use any other format, create a custom converter.</span></span> <span data-ttu-id="c8395-198">有关详细信息，请参阅[系统中的 DateTime 和 DateTimeOffset 支持](../datetime/system-text-json-support.md)。</span><span class="sxs-lookup"><span data-stu-id="c8395-198">For more information, see [DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md).</span></span>

### <a name="quoted-numbers"></a><span data-ttu-id="c8395-199">引用数字</span><span class="sxs-lookup"><span data-stu-id="c8395-199">Quoted numbers</span></span>

<span data-ttu-id="c8395-200">`Newtonsoft.Json` 可以序列化或反序列化 JSON 字符串表示的数字（用引号括起来）。</span><span class="sxs-lookup"><span data-stu-id="c8395-200">`Newtonsoft.Json` can serialize or deserialize numbers represented by JSON strings (surrounded by quotes).</span></span> <span data-ttu-id="c8395-201">例如，它可以接受： `{"DegreesCelsius":"23"}` 而不是 `{"DegreesCelsius":23}`。</span><span class="sxs-lookup"><span data-stu-id="c8395-201">For example, it can accept: `{"DegreesCelsius":"23"}` instead of `{"DegreesCelsius":23}`.</span></span> <span data-ttu-id="c8395-202">若要在 <xref:System.Text.Json>中启用该行为，请实现如下所示的自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="c8395-202">To enable that behavior in <xref:System.Text.Json>, implement a custom converter like the following example.</span></span> <span data-ttu-id="c8395-203">转换器处理定义为 `long`的属性：</span><span class="sxs-lookup"><span data-stu-id="c8395-203">The converter handles properties defined as `long`:</span></span>

* <span data-ttu-id="c8395-204">它将其序列化为 JSON 字符串。</span><span class="sxs-lookup"><span data-stu-id="c8395-204">It serializes them as JSON strings.</span></span> 
* <span data-ttu-id="c8395-205">它在反序列化时接受引号内的 JSON 数字和数字。</span><span class="sxs-lookup"><span data-stu-id="c8395-205">It accepts JSON numbers and numbers within quotes while deserializing.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/LongToStringConverter.cs)]

<span data-ttu-id="c8395-206">使用单个 `long` 属性上[的属性](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property)或通过[将转换器添加](system-text-json-converters-how-to.md#registration-sample---converters-collection)到 <xref:System.Text.Json.JsonSerializerOptions.Converters> 集合来注册此自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="c8395-206">Register this custom converter by [using an attribute](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) on individual `long` properties or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

### <a name="dictionary-with-non-string-key"></a><span data-ttu-id="c8395-207">带有非字符串键的字典</span><span class="sxs-lookup"><span data-stu-id="c8395-207">Dictionary with non-string key</span></span>

<span data-ttu-id="c8395-208">`Newtonsoft.Json` 支持 `Dictionary<TKey, TValue>`类型的集合。</span><span class="sxs-lookup"><span data-stu-id="c8395-208">`Newtonsoft.Json` supports collections of type `Dictionary<TKey, TValue>`.</span></span> <span data-ttu-id="c8395-209"><xref:System.Text.Json> 中的字典集合的内置支持仅限于 `Dictionary<string, TValue>`。</span><span class="sxs-lookup"><span data-stu-id="c8395-209">The built-in support for dictionary collections in <xref:System.Text.Json> is limited to `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="c8395-210">也就是说，键必须是字符串。</span><span class="sxs-lookup"><span data-stu-id="c8395-210">That is, the key must be a string.</span></span>

<span data-ttu-id="c8395-211">若要支持使用整数或其他类型作为键的字典，请创建一个转换器，如[如何编写自定义转换器](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key)中的示例。</span><span class="sxs-lookup"><span data-stu-id="c8395-211">To support a dictionary with an integer or some other type as the key, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).</span></span>

### <a name="polymorphic-serialization"></a><span data-ttu-id="c8395-212">多态序列化</span><span class="sxs-lookup"><span data-stu-id="c8395-212">Polymorphic serialization</span></span>

<span data-ttu-id="c8395-213">`Newtonsoft.Json` 自动执行多态序列化。</span><span class="sxs-lookup"><span data-stu-id="c8395-213">`Newtonsoft.Json` automatically does polymorphic serialization.</span></span> <span data-ttu-id="c8395-214">有关 <xref:System.Text.Json>的有限多态序列化功能的信息，请参阅[序列化派生类的属性](system-text-json-how-to.md#serialize-properties-of-derived-classes)。</span><span class="sxs-lookup"><span data-stu-id="c8395-214">For information about the limited polymorphic serialization capabilities of <xref:System.Text.Json>, see [Serialize properties of derived classes](system-text-json-how-to.md#serialize-properties-of-derived-classes).</span></span>

<span data-ttu-id="c8395-215">所述的解决方法是定义属性，这些属性可能包含派生类作为 `object`类型。</span><span class="sxs-lookup"><span data-stu-id="c8395-215">The workaround described there is to define properties that may contain derived classes as type `object`.</span></span> <span data-ttu-id="c8395-216">如果这是不可能的，另一种方法是为整个继承类型层次结构创建带有 `Write` 方法的转换器，如[如何编写自定义转换器](system-text-json-converters-how-to.md#support-polymorphic-deserialization)中的示例。</span><span class="sxs-lookup"><span data-stu-id="c8395-216">If that isn't possible, another option is to create a converter with a `Write` method for the whole inheritance type hierarchy like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

### <a name="polymorphic-deserialization"></a><span data-ttu-id="c8395-217">多态反序列化</span><span class="sxs-lookup"><span data-stu-id="c8395-217">Polymorphic deserialization</span></span>

<span data-ttu-id="c8395-218">`Newtonsoft.Json` 具有在序列化时将类型名称元数据添加到 JSON 的 `TypeNameHandling` 设置。</span><span class="sxs-lookup"><span data-stu-id="c8395-218">`Newtonsoft.Json` has a `TypeNameHandling` setting that adds type name metadata to the JSON while serializing.</span></span> <span data-ttu-id="c8395-219">在反序列化以执行多态反序列化时，它会使用元数据。</span><span class="sxs-lookup"><span data-stu-id="c8395-219">It uses the metadata while deserializing to do polymorphic deserialization.</span></span> <span data-ttu-id="c8395-220"><xref:System.Text.Json> 可以执行有限范围的多[态序列化](system-text-json-how-to.md#serialize-properties-of-derived-classes)，但不能执行多态反序列化。</span><span class="sxs-lookup"><span data-stu-id="c8395-220"><xref:System.Text.Json> can do a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but not polymorphic deserialization.</span></span>

<span data-ttu-id="c8395-221">若要支持多态反序列化，请创建一个转换器，如[如何编写自定义转换器](system-text-json-converters-how-to.md#support-polymorphic-deserialization)中的示例。</span><span class="sxs-lookup"><span data-stu-id="c8395-221">To support polymorphic deserialization, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

### <a name="required-properties"></a><span data-ttu-id="c8395-222">必需的属性</span><span class="sxs-lookup"><span data-stu-id="c8395-222">Required properties</span></span>

<span data-ttu-id="c8395-223">在反序列化过程中，如果 JSON 中的某个属性为目标类型，则 <xref:System.Text.Json> 不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="c8395-223">During deserialization, <xref:System.Text.Json> doesn't throw an exception if no value is received in the JSON for one of the properties of the target type.</span></span> <span data-ttu-id="c8395-224">例如，如果您有一个 `WeatherForecast` 类：</span><span class="sxs-lookup"><span data-stu-id="c8395-224">For example, if you have a `WeatherForecast` class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="c8395-225">反序列化下面的 JSON 时没有错误：</span><span class="sxs-lookup"><span data-stu-id="c8395-225">The following JSON is deserialized without error:</span></span>

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

<span data-ttu-id="c8395-226">若要使反序列化在 JSON 中没有 `Date` 属性时失败，请实现自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="c8395-226">To make deserialization fail if no `Date` property is in the JSON, implement a custom converter.</span></span> <span data-ttu-id="c8395-227">如果反序列化完成后未设置 `Date` 属性，以下示例转换器代码将引发异常：</span><span class="sxs-lookup"><span data-stu-id="c8395-227">The following sample converter code throws an exception if the `Date` property isn't set after deserialization is complete:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRequiredPropertyConverter.cs)]

<span data-ttu-id="c8395-228">通过[使用 POCO 类的属性](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type)或通过[将转换器添加](system-text-json-converters-how-to.md#registration-sample---converters-collection)到 <xref:System.Text.Json.JsonSerializerOptions.Converters> 集合来注册此自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="c8395-228">Register this custom converter by [using an attribute on the POCO class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="c8395-229">如果遵循此模式，请不要在递归调用 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 或 <xref:System.Text.Json.JsonSerializer.Deserialize%2A>时传入选项对象。</span><span class="sxs-lookup"><span data-stu-id="c8395-229">If you follow this pattern, don't pass in the options object when recursively calling <xref:System.Text.Json.JsonSerializer.Serialize%2A> or <xref:System.Text.Json.JsonSerializer.Deserialize%2A>.</span></span> <span data-ttu-id="c8395-230">Options 对象包含 <xref:System.Text.Json.JsonSerializerOptions.Converters%2A> 集合。</span><span class="sxs-lookup"><span data-stu-id="c8395-230">The options object contains the <xref:System.Text.Json.JsonSerializerOptions.Converters%2A> collection.</span></span> <span data-ttu-id="c8395-231">如果将其传递给 `Serialize` 或 `Deserialize`，则自定义转换器将调用自身，从而产生导致堆栈溢出异常的无限循环。</span><span class="sxs-lookup"><span data-stu-id="c8395-231">If you pass it in to `Serialize` or `Deserialize`, the custom converter calls into itself, making an infinite loop that results in a stack overflow exception.</span></span> <span data-ttu-id="c8395-232">如果默认选项不可行，请使用所需设置创建选项的新实例。</span><span class="sxs-lookup"><span data-stu-id="c8395-232">If the default options are not feasible, create a new instance of the options with the settings that you need.</span></span> <span data-ttu-id="c8395-233">此方法会变慢，因为每个新实例都是独立缓存的。</span><span class="sxs-lookup"><span data-stu-id="c8395-233">This approach will be slow since each new instance caches independently.</span></span>

<span data-ttu-id="c8395-234">前面的转换器代码是简化的示例。</span><span class="sxs-lookup"><span data-stu-id="c8395-234">The preceding converter code is a simplified example.</span></span> <span data-ttu-id="c8395-235">如果需要处理属性（例如[[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute)或不同选项（如自定义编码器），则需要其他逻辑。</span><span class="sxs-lookup"><span data-stu-id="c8395-235">Additional logic would be required if you need to handle attributes (such as [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) or different options (such as custom encoders).</span></span> <span data-ttu-id="c8395-236">此外，示例代码不处理在构造函数中为其设置了默认值的属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-236">Also, the example code doesn't handle properties for which a default value is set in the constructor.</span></span> <span data-ttu-id="c8395-237">但这种方法不区分以下方案：</span><span class="sxs-lookup"><span data-stu-id="c8395-237">And this approach doesn't differentiate between the following scenarios:</span></span>

* <span data-ttu-id="c8395-238">JSON 中缺少属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-238">A property is missing from the JSON.</span></span>
* <span data-ttu-id="c8395-239">JSON 中提供了不可为 null 的类型的属性，但该值是该类型的默认值，如 `int`为零。</span><span class="sxs-lookup"><span data-stu-id="c8395-239">A property for a non-nullable type is present in the JSON, but the value is the default for the type, such as zero for an `int`.</span></span>
* <span data-ttu-id="c8395-240">JSON 中存在可为 null 的类型的属性，但该值为 null。</span><span class="sxs-lookup"><span data-stu-id="c8395-240">A property for a nullable type is present in the JSON, but the value is null.</span></span>

### <a name="deserialize-null-to-non-nullable-type"></a><span data-ttu-id="c8395-241">将 null 反序列化为不可为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="c8395-241">Deserialize null to non-nullable type</span></span> 

<span data-ttu-id="c8395-242">在以下情况下 `Newtonsoft.Json` 不会引发异常：</span><span class="sxs-lookup"><span data-stu-id="c8395-242">`Newtonsoft.Json` doesn't throw an exception in the following scenario:</span></span>

* <span data-ttu-id="c8395-243">`NullValueHandling` 设置为 `Ignore`，</span><span class="sxs-lookup"><span data-stu-id="c8395-243">`NullValueHandling` is set to `Ignore`, and</span></span>
* <span data-ttu-id="c8395-244">在反序列化过程中，JSON 包含不可以为 null 的类型的 null 值。</span><span class="sxs-lookup"><span data-stu-id="c8395-244">During deserialization, the JSON contains a null value for a non-nullable type.</span></span>

<span data-ttu-id="c8395-245">在相同的情况下，<xref:System.Text.Json> 会引发异常。</span><span class="sxs-lookup"><span data-stu-id="c8395-245">In the same scenario, <xref:System.Text.Json> does throw an exception.</span></span> <span data-ttu-id="c8395-246">（相应的 null 处理设置为 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>。）</span><span class="sxs-lookup"><span data-stu-id="c8395-246">(The corresponding null handling setting is <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>.)</span></span>

<span data-ttu-id="c8395-247">如果你拥有目标类型，最佳解决方法是使该属性可以为 null （例如，将 `int` 更改为 `int?`）。</span><span class="sxs-lookup"><span data-stu-id="c8395-247">If you own the target type, the best workaround is to make the property in question nullable (for example, change `int` to `int?`).</span></span>

<span data-ttu-id="c8395-248">另一种解决方法是创建类型的转换器，如以下用于处理 `DateTimeOffset` 类型的 null 值的示例：</span><span class="sxs-lookup"><span data-stu-id="c8395-248">Another workaround is to make a converter for the type, such as the following example that handles null values for `DateTimeOffset` types:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetNullHandlingConverter.cs)]

<span data-ttu-id="c8395-249">通过[使用属性上的特性](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property)或通过[将转换器添加](system-text-json-converters-how-to.md#registration-sample---converters-collection)到 <xref:System.Text.Json.JsonSerializerOptions.Converters> 集合来注册此自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="c8395-249">Register this custom converter by [using an attribute on the property](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="c8395-250">**注意：** 前面的转换器**处理 null 值的方式不同**于指定默认值的 poco 的 `Newtonsoft.Json`。</span><span class="sxs-lookup"><span data-stu-id="c8395-250">**Note:** The preceding converter **handles null values differently** than `Newtonsoft.Json` does for POCOs that specify default values.</span></span> <span data-ttu-id="c8395-251">例如，假设以下代码表示目标对象：</span><span class="sxs-lookup"><span data-stu-id="c8395-251">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="c8395-252">假设使用前面的转换器反序列化以下 JSON：</span><span class="sxs-lookup"><span data-stu-id="c8395-252">And suppose the following JSON is deserialized by using the preceding converter:</span></span>

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="c8395-253">反序列化后，`Date` 属性具有1/1/0001 （`default(DateTimeOffset)`），也就是说，在构造函数中设置的值将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="c8395-253">After deserialization, the `Date` property has 1/1/0001 (`default(DateTimeOffset)`), that is, the value set in the constructor is overwritten.</span></span> <span data-ttu-id="c8395-254">给定相同的 POCO 和 JSON，`Newtonsoft.Json` 反序列化会将1/1/2001 保留在 `Date` 属性中。</span><span class="sxs-lookup"><span data-stu-id="c8395-254">Given the same POCO and JSON, `Newtonsoft.Json` deserialization would leave 1/1/2001 in the `Date` property.</span></span>

### <a name="deserialize-to-immutable-classes-and-structs"></a><span data-ttu-id="c8395-255">反序列化到不可变的类和结构</span><span class="sxs-lookup"><span data-stu-id="c8395-255">Deserialize to immutable classes and structs</span></span>

<span data-ttu-id="c8395-256">`Newtonsoft.Json` 可以反序列化为不可变的类和结构，因为它可以使用具有参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="c8395-256">`Newtonsoft.Json` can deserialize to immutable classes and structs because it can use constructors that have parameters.</span></span> <span data-ttu-id="c8395-257"><xref:System.Text.Json> 仅支持公共无参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="c8395-257"><xref:System.Text.Json> supports only public parameterless constructors.</span></span> <span data-ttu-id="c8395-258">作为一种解决方法，可以在自定义转换器中调用具有参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="c8395-258">As a workaround, you can call a constructor with parameters in a custom converter.</span></span>

<span data-ttu-id="c8395-259">下面是包含多个构造函数参数的不可变结构：</span><span class="sxs-lookup"><span data-stu-id="c8395-259">Here's an immutable struct with multiple constructor parameters:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePoint.cs#ImmutablePoint)]

<span data-ttu-id="c8395-260">下面是一个用于序列化和反序列化此结构的转换器：</span><span class="sxs-lookup"><span data-stu-id="c8395-260">And here's a converter that serializes and deserializes this struct:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePointConverter.cs)]

<span data-ttu-id="c8395-261">通过[将转换器添加](system-text-json-converters-how-to.md#registration-sample---converters-collection)到 <xref:System.Text.Json.JsonSerializerOptions.Converters> 集合来注册此自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="c8395-261">Register this custom converter by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="c8395-262">有关处理开放式泛型属性的类似转换器的示例，请参阅[键值对的内置转换器](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs)。</span><span class="sxs-lookup"><span data-stu-id="c8395-262">For an example of a similar converter that handles open generic properties, see the [built-in converter for key-value pairs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs).</span></span>

### <a name="specify-constructor-to-use"></a><span data-ttu-id="c8395-263">指定要使用的构造函数</span><span class="sxs-lookup"><span data-stu-id="c8395-263">Specify constructor to use</span></span>

<span data-ttu-id="c8395-264">使用 `Newtonsoft.Json` `[JsonConstructor]` 属性可以指定在反序列化到 POCO 时要调用的构造函数。</span><span class="sxs-lookup"><span data-stu-id="c8395-264">The `Newtonsoft.Json` `[JsonConstructor]` attribute lets you specify which constructor to call when deserializing to a POCO.</span></span> <span data-ttu-id="c8395-265"><xref:System.Text.Json> 仅支持无参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="c8395-265"><xref:System.Text.Json> supports only parameterless constructors.</span></span> <span data-ttu-id="c8395-266">作为一种解决方法，可以在自定义转换器中调用所需的任何构造函数。</span><span class="sxs-lookup"><span data-stu-id="c8395-266">As a workaround, you can call whichever constructor you need in a custom converter.</span></span> <span data-ttu-id="c8395-267">请参阅[反序列化为不可变类和结构](#deserialize-to-immutable-classes-and-structs)的示例。</span><span class="sxs-lookup"><span data-stu-id="c8395-267">See the example for [Deserialize to immutable classes and structs](#deserialize-to-immutable-classes-and-structs).</span></span>

### <a name="conditionally-ignore-a-property"></a><span data-ttu-id="c8395-268">有条件地忽略属性</span><span class="sxs-lookup"><span data-stu-id="c8395-268">Conditionally ignore a property</span></span>

<span data-ttu-id="c8395-269">`Newtonsoft.Json` 有多种方法可以在序列化或反序列化时有条件地忽略属性：</span><span class="sxs-lookup"><span data-stu-id="c8395-269">`Newtonsoft.Json` has several ways to conditionally ignore a property on serialization or deserialization:</span></span>

* <span data-ttu-id="c8395-270">`DefaultContractResolver` 允许根据任意条件选择要包括或排除的属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-270">`DefaultContractResolver` lets you select properties to include or exclude, based on arbitrary criteria.</span></span> 
* <span data-ttu-id="c8395-271">`JsonSerializerSettings` 上的 `NullValueHandling` 和 `DefaultValueHandling` 设置允许您指定应忽略所有 null 值或默认值属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-271">The `NullValueHandling` and `DefaultValueHandling` settings on `JsonSerializerSettings` let you specify that all null-value or default-value properties should be ignored.</span></span>
* <span data-ttu-id="c8395-272">利用 `[JsonProperty]` 特性上的 `NullValueHandling` 和 `DefaultValueHandling` 设置，可指定在设置为 null 或默认值时应忽略的单个属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-272">The `NullValueHandling` and `DefaultValueHandling` settings on the `[JsonProperty]` attribute let you specify individual properties that should be ignored when set to null or the default value.</span></span>

<span data-ttu-id="c8395-273"><xref:System.Text.Json> 提供以下方法，在序列化时省略属性：</span><span class="sxs-lookup"><span data-stu-id="c8395-273"><xref:System.Text.Json> provides the following ways to omit properties while serializing:</span></span>

* <span data-ttu-id="c8395-274">属性的[[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties)特性会导致在序列化期间从 JSON 中省略该属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-274">The [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties) attribute on a property causes the property to be omitted from the JSON during serialization.</span></span>
* <span data-ttu-id="c8395-275">[IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) global 选项可让你排除所有 null 值属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-275">The [IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) global option lets you exclude all null-value properties.</span></span>
* <span data-ttu-id="c8395-276">[IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) global 选项可让你排除所有的只读属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-276">The [IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) global option lets you exclude all read-only properties.</span></span>

<span data-ttu-id="c8395-277">这些选项**不**允许你：</span><span class="sxs-lookup"><span data-stu-id="c8395-277">These options **don't** let you:</span></span>

* <span data-ttu-id="c8395-278">忽略所有具有该类型的默认值的属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-278">Ignore all properties that have the default value for the type.</span></span>
* <span data-ttu-id="c8395-279">忽略具有类型默认值的选定属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-279">Ignore selected properties that have the default value for the type.</span></span>
* <span data-ttu-id="c8395-280">如果所选属性的值为 null，则忽略该属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-280">Ignore selected properties if their value is null.</span></span>
* <span data-ttu-id="c8395-281">根据运行时计算的任意条件忽略所选属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-281">Ignore selected properties based on arbitrary criteria evaluated at run time.</span></span> 

<span data-ttu-id="c8395-282">对于该功能，可以编写自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="c8395-282">For that functionality, you can write a custom converter.</span></span> <span data-ttu-id="c8395-283">下面是一个示例 POCO 和一个用于说明此方法的自定义转换器：</span><span class="sxs-lookup"><span data-stu-id="c8395-283">Here's a sample POCO and a custom converter for it that illustrates this approach:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

<span data-ttu-id="c8395-284">如果转换器的值为 null、空字符串或 "N/A"，转换器将导致从序列化中省略 `Summary` 属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-284">The converter causes the `Summary` property to be omitted from serialization if its value is null, an empty string, or "N/A".</span></span> 

<span data-ttu-id="c8395-285">通过[使用类上的特性](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type)或通过[将转换器添加](system-text-json-converters-how-to.md#registration-sample---converters-collection)到 <xref:System.Text.Json.JsonSerializerOptions.Converters> 集合来注册此自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="c8395-285">Register this custom converter by [using an attribute on the class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="c8395-286">此方法在以下情况下需要其他逻辑：</span><span class="sxs-lookup"><span data-stu-id="c8395-286">This approach requires additional logic if:</span></span>

* <span data-ttu-id="c8395-287">POCO 包含复杂属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-287">The POCO includes complex properties.</span></span>
* <span data-ttu-id="c8395-288">需要处理诸如诸如自定义编码器之类 `[JsonIgnore]` 或选项之类的属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-288">You need to handle attributes such as `[JsonIgnore]` or options such as custom encoders.</span></span>

### <a name="callbacks"></a><span data-ttu-id="c8395-289">回调</span><span class="sxs-lookup"><span data-stu-id="c8395-289">Callbacks</span></span>

<span data-ttu-id="c8395-290">`Newtonsoft.Json` 允许您在序列化或反序列化过程中的多个点执行自定义代码：</span><span class="sxs-lookup"><span data-stu-id="c8395-290">`Newtonsoft.Json` lets you execute custom code at several points in the serialization or deserialization process:</span></span>

* <span data-ttu-id="c8395-291">OnDeserializing （开始反序列化对象时）</span><span class="sxs-lookup"><span data-stu-id="c8395-291">OnDeserializing (when beginning to deserialize an object)</span></span>
* <span data-ttu-id="c8395-292">OnDeserialized （反序列化对象后）</span><span class="sxs-lookup"><span data-stu-id="c8395-292">OnDeserialized (when finished deserializing an object)</span></span>
* <span data-ttu-id="c8395-293">OnSerializing （开始序列化对象时）</span><span class="sxs-lookup"><span data-stu-id="c8395-293">OnSerializing (when beginning to serialize an object)</span></span>
* <span data-ttu-id="c8395-294">OnSerialized （对对象进行序列化后）</span><span class="sxs-lookup"><span data-stu-id="c8395-294">OnSerialized (when finished serializing an object)</span></span>

<span data-ttu-id="c8395-295">在 <xref:System.Text.Json>中，可以通过编写自定义转换器来模拟回调。</span><span class="sxs-lookup"><span data-stu-id="c8395-295">In <xref:System.Text.Json>, you can simulate callbacks by writing a custom converter.</span></span> <span data-ttu-id="c8395-296">下面的示例演示了 POCO 的自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="c8395-296">The following example shows a custom converter for a POCO.</span></span> <span data-ttu-id="c8395-297">转换器包含代码，该代码在与 `Newtonsoft.Json` 回调相对应的每个点上显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="c8395-297">The converter includes code that displays a message at each point that corresponds to a `Newtonsoft.Json` callback.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastCallbacksConverter.cs)]

<span data-ttu-id="c8395-298">通过[使用类上的特性](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type)或通过[将转换器添加](system-text-json-converters-how-to.md#registration-sample---converters-collection)到 <xref:System.Text.Json.JsonSerializerOptions.Converters> 集合来注册此自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="c8395-298">Register this custom converter by [using an attribute on the class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="c8395-299">如果使用的是前面的示例的自定义转换器：</span><span class="sxs-lookup"><span data-stu-id="c8395-299">If you use a custom converter that follows the preceding sample:</span></span>

* <span data-ttu-id="c8395-300">`OnDeserializing` 代码无权访问新的 POCO 实例。</span><span class="sxs-lookup"><span data-stu-id="c8395-300">The `OnDeserializing` code doesn't have access to the new POCO instance.</span></span> <span data-ttu-id="c8395-301">若要在反序列化开始时操作新的 POCO 实例，请将该代码放入 POCO 构造函数中。</span><span class="sxs-lookup"><span data-stu-id="c8395-301">To manipulate the new POCO instance at the start of deserialization, put that code in the POCO constructor.</span></span>
* <span data-ttu-id="c8395-302">当递归调用 `Serialize` 或 `Deserialize`时，请勿传入选项对象。</span><span class="sxs-lookup"><span data-stu-id="c8395-302">Don't pass in the options object when recursively calling `Serialize` or `Deserialize`.</span></span> <span data-ttu-id="c8395-303">Options 对象包含 `Converters` 集合。</span><span class="sxs-lookup"><span data-stu-id="c8395-303">The options object contains the `Converters` collection.</span></span> <span data-ttu-id="c8395-304">如果将其传递给 `Serialize` 或 `Deserialize`，则将使用转换器，这将导致堆栈溢出异常。</span><span class="sxs-lookup"><span data-stu-id="c8395-304">If you pass it in to `Serialize` or `Deserialize`, the converter will be used, making an infinite loop that results in a stack overflow exception.</span></span>

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a><span data-ttu-id="c8395-305">JsonSerializer 当前不支持的方案</span><span class="sxs-lookup"><span data-stu-id="c8395-305">Scenarios that JsonSerializer currently doesn't support</span></span>

<span data-ttu-id="c8395-306">解决方法在以下情况下可能会比较难实现。</span><span class="sxs-lookup"><span data-stu-id="c8395-306">Workarounds are possible for the following scenarios, but some of them would be relatively difficult to implement.</span></span> <span data-ttu-id="c8395-307">本文并不提供这些方案的代码示例。</span><span class="sxs-lookup"><span data-stu-id="c8395-307">This article doesn't provide code samples for workarounds for these scenarios.</span></span>

<span data-ttu-id="c8395-308">这并不是在 `System.Text.Json`中没有等效项 `Newtonsoft.Json` 功能的详尽列表。</span><span class="sxs-lookup"><span data-stu-id="c8395-308">This is not an exhaustive list of `Newtonsoft.Json` features that have no equivalents in `System.Text.Json`.</span></span> <span data-ttu-id="c8395-309">此列表包括[GitHub 问题](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)或[StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json)文章中请求的许多方案。</span><span class="sxs-lookup"><span data-stu-id="c8395-309">The list includes many of the scenarios that have been requested in [GitHub issues](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) or [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json) posts.</span></span>

<span data-ttu-id="c8395-310">如果为这些方案之一实现了解决方法并可以共享代码，请选择页面底部的 "**此页面**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="c8395-310">If you implement a workaround for one of these scenarios and can share the code, select the "**This page**" button at the bottom of the page.</span></span> <span data-ttu-id="c8395-311">这将创建一个 GitHub 问题，并将其添加到页面底部列出的问题。</span><span class="sxs-lookup"><span data-stu-id="c8395-311">That creates a GitHub issue and adds it to the issues that are listed at the bottom of the page.</span></span>

### <a name="types-without-built-in-support"></a><span data-ttu-id="c8395-312">无内置支持的类型</span><span class="sxs-lookup"><span data-stu-id="c8395-312">Types without built-in support</span></span>

<span data-ttu-id="c8395-313"><xref:System.Text.Json> 不为以下类型提供内置支持：</span><span class="sxs-lookup"><span data-stu-id="c8395-313"><xref:System.Text.Json> doesn't provide built-in support for the following types:</span></span>

* <span data-ttu-id="c8395-314"><xref:System.Data.DataTable> 和相关类型</span><span class="sxs-lookup"><span data-stu-id="c8395-314"><xref:System.Data.DataTable> and related types</span></span>
* <span data-ttu-id="c8395-315">F#类型，如可[区分联合](../../fsharp/language-reference/discriminated-unions.md)、[记录类型](../../fsharp/language-reference/records.md)和[匿名记录类型](../../fsharp/language-reference/anonymous-records.md)。</span><span class="sxs-lookup"><span data-stu-id="c8395-315">F# types, such as [discriminated unions](../../fsharp/language-reference/discriminated-unions.md), [record types](../../fsharp/language-reference/records.md), and [anonymous record types](../../fsharp/language-reference/anonymous-records.md).</span></span>
* <span data-ttu-id="c8395-316"><xref:System.Collections.Specialized> 命名空间中的集合类型</span><span class="sxs-lookup"><span data-stu-id="c8395-316">Collection types in the <xref:System.Collections.Specialized> namespace</span></span>
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <span data-ttu-id="c8395-317"><xref:System.ValueTuple> 及其关联的泛型类型</span><span class="sxs-lookup"><span data-stu-id="c8395-317"><xref:System.ValueTuple> and its associated generic types</span></span>

<span data-ttu-id="c8395-318">对于没有内置支持的类型，可以实现自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="c8395-318">Custom converters can be implemented for types that don't have built-in support.</span></span>

### <a name="public-and-non-public-fields"></a><span data-ttu-id="c8395-319">公共和非公共字段</span><span class="sxs-lookup"><span data-stu-id="c8395-319">Public and non-public fields</span></span>

<span data-ttu-id="c8395-320">`Newtonsoft.Json` 可以对字段以及属性进行序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="c8395-320">`Newtonsoft.Json` can serialize and deserialize fields as well as properties.</span></span> <span data-ttu-id="c8395-321"><xref:System.Text.Json> 仅适用于公共属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-321"><xref:System.Text.Json> only works with public properties.</span></span> <span data-ttu-id="c8395-322">自定义转换器可提供此功能。</span><span class="sxs-lookup"><span data-stu-id="c8395-322">Custom converters can provide this functionality.</span></span>

### <a name="internal-and-private-property-setters-and-getters"></a><span data-ttu-id="c8395-323">内部和私有属性资源库和 getter</span><span class="sxs-lookup"><span data-stu-id="c8395-323">Internal and private property setters and getters</span></span>

<span data-ttu-id="c8395-324">`Newtonsoft.Json` 可以通过 `JsonProperty` 属性使用私有和内部属性 setter 和 getter。</span><span class="sxs-lookup"><span data-stu-id="c8395-324">`Newtonsoft.Json` can use private and internal property setters and getters via the `JsonProperty` attribute.</span></span> <span data-ttu-id="c8395-325"><xref:System.Text.Json> 仅支持公共 setter。</span><span class="sxs-lookup"><span data-stu-id="c8395-325"><xref:System.Text.Json> supports only public setters.</span></span> <span data-ttu-id="c8395-326">自定义转换器可提供此功能。</span><span class="sxs-lookup"><span data-stu-id="c8395-326">Custom converters can provide this functionality.</span></span>

### <a name="preserve-object-references-and-handle-loops"></a><span data-ttu-id="c8395-327">保留对象引用并处理循环</span><span class="sxs-lookup"><span data-stu-id="c8395-327">Preserve object references and handle loops</span></span>

<span data-ttu-id="c8395-328">默认情况下，`Newtonsoft.Json` 按值进行序列化。</span><span class="sxs-lookup"><span data-stu-id="c8395-328">By default, `Newtonsoft.Json` serializes by value.</span></span> <span data-ttu-id="c8395-329">例如，如果对象包含两个属性，这些属性包含对同一 `Person` 对象的引用，则在 JSON 中复制 `Person` 对象属性的值。</span><span class="sxs-lookup"><span data-stu-id="c8395-329">For example, if an object contains two properties that contain a reference to the same `Person` object, the values of that `Person` object's properties are duplicated in the JSON.</span></span>

<span data-ttu-id="c8395-330">`Newtonsoft.Json` 在 `JsonSerializerSettings` 上具有 `PreserveReferencesHandling` 设置，可让你按引用进行序列化：</span><span class="sxs-lookup"><span data-stu-id="c8395-330">`Newtonsoft.Json` has a `PreserveReferencesHandling` setting on `JsonSerializerSettings` that lets you serialize by reference:</span></span>

* <span data-ttu-id="c8395-331">标识符元数据将添加到为第一个 `Person` 对象创建的 JSON。</span><span class="sxs-lookup"><span data-stu-id="c8395-331">An identifier metadata is added to the JSON created for the first `Person` object.</span></span>
* <span data-ttu-id="c8395-332">为第二个 `Person` 对象创建的 JSON 包含对该标识符而不是属性值的引用。</span><span class="sxs-lookup"><span data-stu-id="c8395-332">The JSON that is created for the second `Person` object contains a reference to that identifier instead of property values.</span></span>

<span data-ttu-id="c8395-333">`Newtonsoft.Json` 还具有一个 `ReferenceLoopHandling` 设置，使你可以忽略循环引用，而不是引发异常。</span><span class="sxs-lookup"><span data-stu-id="c8395-333">`Newtonsoft.Json` also has a `ReferenceLoopHandling` setting that lets you ignore circular references rather than throw an exception.</span></span>

<span data-ttu-id="c8395-334"><xref:System.Text.Json> 仅支持按值进行序列化，并且为循环引用引发了异常。</span><span class="sxs-lookup"><span data-stu-id="c8395-334"><xref:System.Text.Json> only supports serialization by value and throws an exception for circular references.</span></span>

### <a name="systemruntimeserialization-attributes"></a><span data-ttu-id="c8395-335">System.object 特性</span><span class="sxs-lookup"><span data-stu-id="c8395-335">System.Runtime.Serialization attributes</span></span>

<span data-ttu-id="c8395-336"><xref:System.Text.Json> 不支持 `System.Runtime.Serialization` 命名空间中的属性，如 `DataMemberAttribute` 和 `IgnoreDataMemberAttribute`。</span><span class="sxs-lookup"><span data-stu-id="c8395-336"><xref:System.Text.Json> doesn't support attributes from the `System.Runtime.Serialization` namespace, such as `DataMemberAttribute` and `IgnoreDataMemberAttribute`.</span></span>

### <a name="octal-numbers"></a><span data-ttu-id="c8395-337">八进制数</span><span class="sxs-lookup"><span data-stu-id="c8395-337">Octal numbers</span></span>

<span data-ttu-id="c8395-338">`Newtonsoft.Json` 将带前导零的数字视为八进制数。</span><span class="sxs-lookup"><span data-stu-id="c8395-338">`Newtonsoft.Json` treats numbers with a leading zero as octal numbers.</span></span> <span data-ttu-id="c8395-339"><xref:System.Text.Json> 不允许前导零，因为[RFC 8259](https://tools.ietf.org/html/rfc8259)规范不允许这样做。</span><span class="sxs-lookup"><span data-stu-id="c8395-339"><xref:System.Text.Json> doesn't allow leading zeroes because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't allow them.</span></span>

### <a name="populate-existing-objects"></a><span data-ttu-id="c8395-340">填充现有对象</span><span class="sxs-lookup"><span data-stu-id="c8395-340">Populate existing objects</span></span>

<span data-ttu-id="c8395-341">中的 `JsonConvert.PopulateObject` 方法 `Newtonsoft.Json` 将 JSON 文档反序列化为类的现有实例，而不是创建新的实例。</span><span class="sxs-lookup"><span data-stu-id="c8395-341">The `JsonConvert.PopulateObject` method in `Newtonsoft.Json` deserializes a JSON document to an existing instance of a class, instead of creating a new instance.</span></span> <span data-ttu-id="c8395-342"><xref:System.Text.Json> 始终使用默认的公共无参数构造函数创建目标类型的新实例。</span><span class="sxs-lookup"><span data-stu-id="c8395-342"><xref:System.Text.Json> always creates a new instance of the target type by using the default public parameterless constructor.</span></span> <span data-ttu-id="c8395-343">自定义转换器可以反序列化到现有实例。</span><span class="sxs-lookup"><span data-stu-id="c8395-343">Custom converters can deserialize to an existing instance.</span></span>

### <a name="reuse-rather-than-replace-properties"></a><span data-ttu-id="c8395-344">重用而不是替换属性</span><span class="sxs-lookup"><span data-stu-id="c8395-344">Reuse rather than replace properties</span></span>

<span data-ttu-id="c8395-345">使用 `Newtonsoft.Json` `ObjectCreationHandling` 设置，您可以指定在反序列化过程中应重复使用属性中的对象，而不是替换。</span><span class="sxs-lookup"><span data-stu-id="c8395-345">The `Newtonsoft.Json` `ObjectCreationHandling` setting lets you specify that objects in properties should be reused rather than replaced during deserialization.</span></span> <span data-ttu-id="c8395-346"><xref:System.Text.Json> 始终替换属性中的对象。</span><span class="sxs-lookup"><span data-stu-id="c8395-346"><xref:System.Text.Json> always replaces objects in properties.</span></span>  <span data-ttu-id="c8395-347">自定义转换器可提供此功能。</span><span class="sxs-lookup"><span data-stu-id="c8395-347">Custom converters can provide this functionality.</span></span>

### <a name="add-to-collections-without-setters"></a><span data-ttu-id="c8395-348">不带 setter 的添加到集合</span><span class="sxs-lookup"><span data-stu-id="c8395-348">Add to collections without setters</span></span>

<span data-ttu-id="c8395-349">反序列化期间 `Newtonsoft.Json` 会将对象添加到集合，即使属性没有 setter。</span><span class="sxs-lookup"><span data-stu-id="c8395-349">During deserialization, `Newtonsoft.Json` adds objects to a collection even if the property has no setter.</span></span> <span data-ttu-id="c8395-350"><xref:System.Text.Json> 忽略没有 setter 的属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-350"><xref:System.Text.Json> ignores properties that don't have setters.</span></span> <span data-ttu-id="c8395-351">自定义转换器可提供此功能。</span><span class="sxs-lookup"><span data-stu-id="c8395-351">Custom converters can provide this functionality.</span></span>

### <a name="missingmemberhandling"></a><span data-ttu-id="c8395-352">MissingMemberHandling</span><span class="sxs-lookup"><span data-stu-id="c8395-352">MissingMemberHandling</span></span>

<span data-ttu-id="c8395-353">如果 JSON 包含目标类型中缺少的属性，则可以将 `Newtonsoft.Json` 配置为在反序列化期间引发异常。</span><span class="sxs-lookup"><span data-stu-id="c8395-353">`Newtonsoft.Json` can be configured to throw exceptions during deserialization if the JSON includes properties that are missing in the target type.</span></span> <span data-ttu-id="c8395-354"><xref:System.Text.Json> 忽略 JSON 中的额外属性，除非使用[[JsonExtensionData] 属性](system-text-json-how-to.md#handle-overflow-json)。</span><span class="sxs-lookup"><span data-stu-id="c8395-354"><xref:System.Text.Json> ignores extra properties in the JSON, except when you use the [[JsonExtensionData] attribute](system-text-json-how-to.md#handle-overflow-json).</span></span> <span data-ttu-id="c8395-355">缺少成员功能的解决方法。</span><span class="sxs-lookup"><span data-stu-id="c8395-355">There's no workaround for the missing member feature.</span></span>

### <a name="tracewriter"></a><span data-ttu-id="c8395-356">TraceWriter</span><span class="sxs-lookup"><span data-stu-id="c8395-356">TraceWriter</span></span>

<span data-ttu-id="c8395-357">`Newtonsoft.Json` 允许使用 `TraceWriter` 进行调试，以查看由序列化或反序列化生成的日志。</span><span class="sxs-lookup"><span data-stu-id="c8395-357">`Newtonsoft.Json` lets you debug by using a `TraceWriter` to view logs that are generated by serialization or deserialization.</span></span> <span data-ttu-id="c8395-358"><xref:System.Text.Json> 不会进行日志记录。</span><span class="sxs-lookup"><span data-stu-id="c8395-358"><xref:System.Text.Json> doesn't do logging.</span></span>

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a><span data-ttu-id="c8395-359">与 JToken 相比，JsonDocument 和 JsonElement （例如 JObject、JArray）</span><span class="sxs-lookup"><span data-stu-id="c8395-359">JsonDocument and JsonElement compared to JToken (like JObject, JArray)</span></span>

<span data-ttu-id="c8395-360"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> 提供了从现有 JSON 有效负载分析和生成**只读**文档对象模型（DOM）的功能。</span><span class="sxs-lookup"><span data-stu-id="c8395-360"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to parse and build a **read-only** Document Object Model (DOM) from existing JSON payloads.</span></span> <span data-ttu-id="c8395-361">DOM 提供对 JSON 有效负载中的数据的随机访问。</span><span class="sxs-lookup"><span data-stu-id="c8395-361">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="c8395-362">可以通过 <xref:System.Text.Json.JsonElement> 类型访问构成有效负载的 JSON 元素。</span><span class="sxs-lookup"><span data-stu-id="c8395-362">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="c8395-363">`JsonElement` 类型提供了 Api，可将 JSON 文本转换为常见的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="c8395-363">The `JsonElement` type provides APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="c8395-364">`JsonDocument` 公开 <xref:System.Text.Json.JsonDocument.RootElement> 属性。</span><span class="sxs-lookup"><span data-stu-id="c8395-364">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

### <a name="jsondocument-is-idisposable"></a><span data-ttu-id="c8395-365">JsonDocument 为 IDisposable</span><span class="sxs-lookup"><span data-stu-id="c8395-365">JsonDocument is IDisposable</span></span>

<span data-ttu-id="c8395-366">`JsonDocument` 会将内存中的数据视图生成到已入池的缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="c8395-366">`JsonDocument` builds an in-memory view of the data into a pooled buffer.</span></span> <span data-ttu-id="c8395-367">因此，与 `Newtonsoft.Json``JObject` 或 `JArray` 不同，`JsonDocument` 类型实现 `IDisposable` 并且需要在 using 块中使用。</span><span class="sxs-lookup"><span data-stu-id="c8395-367">Therefore, unlike `JObject` or `JArray` from `Newtonsoft.Json`, the `JsonDocument` type implements `IDisposable` and needs to be used inside a using block.</span></span> 

<span data-ttu-id="c8395-368">如果要将生存期所有权和处置责任转移到调用方，只需从 API 返回 `JsonDocument`。</span><span class="sxs-lookup"><span data-stu-id="c8395-368">Only return a `JsonDocument` from your API if you want to transfer lifetime ownership and dispose responsibility to the caller.</span></span> <span data-ttu-id="c8395-369">在大多数情况下，这并不是必需的。</span><span class="sxs-lookup"><span data-stu-id="c8395-369">In most scenarios, that isn't necessary.</span></span> <span data-ttu-id="c8395-370">如果调用方需要使用整个 JSON 文档，则返回 <xref:System.Text.Json.JsonDocument.RootElement%2A>的 <xref:System.Text.Json.JsonElement.Clone%2A>，这是 <xref:System.Text.Json.JsonElement>的。</span><span class="sxs-lookup"><span data-stu-id="c8395-370">If the caller needs to work with the entire JSON document, return the <xref:System.Text.Json.JsonElement.Clone%2A> of the <xref:System.Text.Json.JsonDocument.RootElement%2A>, which is a <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="c8395-371">如果调用方需要使用 JSON 文档中的特定元素，则返回 <xref:System.Text.Json.JsonElement>的 <xref:System.Text.Json.JsonElement.Clone%2A>。</span><span class="sxs-lookup"><span data-stu-id="c8395-371">If the caller needs to work with a particular element within the JSON document, return the <xref:System.Text.Json.JsonElement.Clone%2A> of that <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="c8395-372">如果在不进行 `Clone`的情况下直接返回 `RootElement` 或子元素，则在释放拥有该方法的 `JsonDocument` 后，调用方将无法访问返回的 `JsonElement`。</span><span class="sxs-lookup"><span data-stu-id="c8395-372">If you return the `RootElement` or a sub-element directly without making a `Clone`, the caller won't be able to access the returned `JsonElement` after the `JsonDocument` that owns it is disposed.</span></span>

<span data-ttu-id="c8395-373">下面是一个示例，要求你进行 `Clone`：</span><span class="sxs-lookup"><span data-stu-id="c8395-373">Here's an example that requires you to make a `Clone`:</span></span>

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

<span data-ttu-id="c8395-374">前面的代码需要包含 `fileName` 属性的 `JsonElement`。</span><span class="sxs-lookup"><span data-stu-id="c8395-374">The preceding code expects a `JsonElement` that contains a `fileName` property.</span></span> <span data-ttu-id="c8395-375">它将打开 JSON 文件并创建一个 `JsonDocument`。</span><span class="sxs-lookup"><span data-stu-id="c8395-375">It opens the JSON file and creates a `JsonDocument`.</span></span> <span data-ttu-id="c8395-376">方法假设调用方想要使用整个文档，因此它将返回 `RootElement`的 `Clone`。</span><span class="sxs-lookup"><span data-stu-id="c8395-376">The method assumes that the caller wants to work with the entire document, so it returns the `Clone` of the `RootElement`.</span></span> 

<span data-ttu-id="c8395-377">如果接收到 `JsonElement` 并返回子元素，则无需返回子元素的 `Clone`。</span><span class="sxs-lookup"><span data-stu-id="c8395-377">If you receive a `JsonElement` and are returning a sub-element, it's not necessary to return a `Clone` of the sub-element.</span></span> <span data-ttu-id="c8395-378">调用方负责使传入 `JsonElement` 所属的 `JsonDocument` 保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="c8395-378">The caller is responsible for keeping alive the `JsonDocument` that the passed-in `JsonElement` belongs to.</span></span> <span data-ttu-id="c8395-379">例如：</span><span class="sxs-lookup"><span data-stu-id="c8395-379">For example:</span></span>

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a><span data-ttu-id="c8395-380">JsonDocument 是只读的</span><span class="sxs-lookup"><span data-stu-id="c8395-380">JsonDocument is read-only</span></span>

<span data-ttu-id="c8395-381"><xref:System.Text.Json> DOM 无法添加、删除或修改 JSON 元素。</span><span class="sxs-lookup"><span data-stu-id="c8395-381">The <xref:System.Text.Json> DOM can't add, remove, or modify JSON elements.</span></span> <span data-ttu-id="c8395-382">它是以这种方式设计的，可用于分析常见 JSON 负载大小（即 < 1 MB）的分配。</span><span class="sxs-lookup"><span data-stu-id="c8395-382">It's designed this way for performance and to reduce allocations for parsing common JSON payload sizes (that is, < 1 MB).</span></span> <span data-ttu-id="c8395-383">如果你的方案当前使用可修改的 DOM，以下解决方法之一可能是可行的：</span><span class="sxs-lookup"><span data-stu-id="c8395-383">If your scenario currently uses a modifiable DOM, one of the following workarounds might be feasible:</span></span>

* <span data-ttu-id="c8395-384">若要从头开始生成 `JsonDocument` （即，不将现有 JSON 有效负载传入 `Parse` 方法），请使用 `Utf8JsonWriter` 编写 JSON 文本，并分析用于生成新 `JsonDocument`的输出。</span><span class="sxs-lookup"><span data-stu-id="c8395-384">To build a `JsonDocument` from scratch (that is, without passing in an existing JSON payload to the `Parse` method), write the JSON text by using the `Utf8JsonWriter` and parse the output from that to make a new `JsonDocument`.</span></span>
* <span data-ttu-id="c8395-385">若要修改现有 `JsonDocument`，请使用它来编写 JSON 文本，在编写时进行更改，并分析用于生成新 `JsonDocument`的输出。</span><span class="sxs-lookup"><span data-stu-id="c8395-385">To modify an existing `JsonDocument`, use it to write JSON text, making changes while you write, and parse the output from that to make a new `JsonDocument`.</span></span>
* <span data-ttu-id="c8395-386">若要合并与 `Newtonsoft.Json``JObject.Merge` 或 `JContainer.Merge` Api 相同的现有 JSON 文档，请参阅[此 GitHub 问题](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853)。</span><span class="sxs-lookup"><span data-stu-id="c8395-386">To merge existing JSON documents, equivalent to the `JObject.Merge` or `JContainer.Merge` APIs from `Newtonsoft.Json`, see [this GitHub issue](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).</span></span>

### <a name="jsonelement-is-a-union-struct"></a><span data-ttu-id="c8395-387">JsonElement 是联合结构</span><span class="sxs-lookup"><span data-stu-id="c8395-387">JsonElement is a union struct</span></span>

<span data-ttu-id="c8395-388">`JsonDocument` 公开 `RootElement` 为类型 <xref:System.Text.Json.JsonElement>的属性，它是包含任何 JSON 元素的联合结构类型。</span><span class="sxs-lookup"><span data-stu-id="c8395-388">`JsonDocument` exposes the `RootElement` as a property of type <xref:System.Text.Json.JsonElement>, which is a union, struct type that encompasses any JSON element.</span></span> <span data-ttu-id="c8395-389">`Newtonsoft.Json` 使用 `JObject`、`JArray`和 `JToken`等专用层次结构类型。</span><span class="sxs-lookup"><span data-stu-id="c8395-389">`Newtonsoft.Json` uses dedicated hierarchical types like `JObject`,`JArray`, `JToken`, and so forth.</span></span> <span data-ttu-id="c8395-390">`JsonElement` 是可以搜索和枚举的内容，可以使用 `JsonElement` 将 JSON 元素具体化为 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="c8395-390">`JsonElement` is what you can search and enumerate over, and you can use `JsonElement` to materialize JSON elements into .NET types.</span></span>

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a><span data-ttu-id="c8395-391">如何搜索子元素的 JsonDocument 和 JsonElement</span><span class="sxs-lookup"><span data-stu-id="c8395-391">How to search a JsonDocument and JsonElement for sub-elements</span></span>

<span data-ttu-id="c8395-392">使用 `Newtonsoft.Json` `JObject` 或 `JArray` 搜索 JSON 令牌的速度往往相对较快，因为它们是在某些字典中查找的。</span><span class="sxs-lookup"><span data-stu-id="c8395-392">Searches for JSON tokens using `JObject` or `JArray` from `Newtonsoft.Json` tend to be relatively fast because they're lookups in some dictionary.</span></span> <span data-ttu-id="c8395-393">相比之下，搜索 `JsonElement` 要求按顺序搜索属性，因此速度相对较慢（例如，使用 `TryGetProperty`时）。</span><span class="sxs-lookup"><span data-stu-id="c8395-393">By comparison, searches on `JsonElement` require a sequential search of the properties and hence is relatively slow (for example when using `TryGetProperty`).</span></span> <span data-ttu-id="c8395-394"><xref:System.Text.Json> 旨在最大程度地减少初始分析时间，而不是查找时间。</span><span class="sxs-lookup"><span data-stu-id="c8395-394"><xref:System.Text.Json> is designed to minimize initial parse time rather than lookup time.</span></span> <span data-ttu-id="c8395-395">因此，在通过 `JsonDocument` 对象搜索时，请使用以下方法优化性能：</span><span class="sxs-lookup"><span data-stu-id="c8395-395">Therefore, use the following approaches to optimize performance when searching through a `JsonDocument` object:</span></span>

* <span data-ttu-id="c8395-396">使用内置枚举器（<xref:System.Text.Json.JsonElement.EnumerateArray%2A> 和 <xref:System.Text.Json.JsonElement.EnumerateObject%2A>），而不是执行自己的索引或循环。</span><span class="sxs-lookup"><span data-stu-id="c8395-396">Use the built-in enumerators (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> and <xref:System.Text.Json.JsonElement.EnumerateObject%2A>) rather than doing your own indexing or loops.</span></span>
* <span data-ttu-id="c8395-397">不要使用 `RootElement`通过每个属性对整个 `JsonDocument` 执行顺序搜索。</span><span class="sxs-lookup"><span data-stu-id="c8395-397">Don't do a sequential search on the whole `JsonDocument` through every property by using `RootElement`.</span></span> <span data-ttu-id="c8395-398">而是基于 JSON 数据的已知结构搜索嵌套的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="c8395-398">Instead, search on nested JSON objects based on the known structure of the JSON data.</span></span> <span data-ttu-id="c8395-399">例如，如果要查找 `Student` 对象中的 `Grade` 属性，请遍历 `Student` 对象，并获得每个对象的 `Grade` 值，而不是搜索查找 `JsonElement` 属性的所有 `Grade` 对象。</span><span class="sxs-lookup"><span data-stu-id="c8395-399">For example, if you're looking for a `Grade` property in `Student` objects, loop through the `Student` objects and get the value of `Grade` for each, rather than searching through all `JsonElement` objects looking for `Grade` properties.</span></span> <span data-ttu-id="c8395-400">这样做将导致不必要的传递相同的数据。</span><span class="sxs-lookup"><span data-stu-id="c8395-400">Doing the latter will result in unnecessary passes over the same data.</span></span>

<span data-ttu-id="c8395-401">有关代码示例，请参阅[使用 JsonDocument 访问数据](system-text-json-how-to.md#use-jsondocument-for-access-to-data)。</span><span class="sxs-lookup"><span data-stu-id="c8395-401">For a code example, see [Use JsonDocument for access to data](system-text-json-how-to.md#use-jsondocument-for-access-to-data).</span></span>

## <a name="utf8jsonreader-compared-to-jsontextreader"></a><span data-ttu-id="c8395-402">Utf8JsonReader 与 JsonTextReader 的比较</span><span class="sxs-lookup"><span data-stu-id="c8395-402">Utf8JsonReader compared to JsonTextReader</span></span>

<span data-ttu-id="c8395-403"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> 是适用于 UTF-8 编码的 JSON 文本的高性能、低分配、只进读取器、从[ReadOnlySpan\<byte >](xref:System.ReadOnlySpan%601)或[ReadOnlySequence\<字节 >](xref:System.Buffers.ReadOnlySequence%601)读取。</span><span class="sxs-lookup"><span data-stu-id="c8395-403"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) or [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601).</span></span> <span data-ttu-id="c8395-404">`Utf8JsonReader` 是可用于生成自定义分析程序和反的低级别类型。</span><span class="sxs-lookup"><span data-stu-id="c8395-404">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span>

<span data-ttu-id="c8395-405">以下各节介绍使用 `Utf8JsonReader`的推荐编程模式。</span><span class="sxs-lookup"><span data-stu-id="c8395-405">The following sections explain recommended programming patterns for using `Utf8JsonReader`.</span></span>

### <a name="utf8jsonreader-is-a-ref-struct"></a><span data-ttu-id="c8395-406">Utf8JsonReader 是 ref 结构</span><span class="sxs-lookup"><span data-stu-id="c8395-406">Utf8JsonReader is a ref struct</span></span>

<span data-ttu-id="c8395-407">由于 `Utf8JsonReader` 类型是*ref 结构*，因此它具有[某些限制](../../csharp/language-reference/keywords/ref.md#ref-struct-types)。</span><span class="sxs-lookup"><span data-stu-id="c8395-407">Because the `Utf8JsonReader` type is a *ref struct*, it has [certain limitations](../../csharp/language-reference/keywords/ref.md#ref-struct-types).</span></span> <span data-ttu-id="c8395-408">例如，不能将它作为字段存储在 ref 结构之外的类或结构中。</span><span class="sxs-lookup"><span data-stu-id="c8395-408">For example, it can't be stored as a field on a class or struct other than a ref struct.</span></span> <span data-ttu-id="c8395-409">为了实现高性能，此类型必须为 `ref struct`，因为它需要缓存输入[ReadOnlySpan\<byte >](xref:System.ReadOnlySpan%601)，这本身就是一个 ref 结构。</span><span class="sxs-lookup"><span data-stu-id="c8395-409">To achieve high performance, this type must be a `ref struct` since it needs to cache the input [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), which itself is a ref struct.</span></span> <span data-ttu-id="c8395-410">此外，此类型是可变的，因为它包含状态。</span><span class="sxs-lookup"><span data-stu-id="c8395-410">In addition, this type is mutable since it holds state.</span></span> <span data-ttu-id="c8395-411">因此，请通过引用而不是按值**传递它**。</span><span class="sxs-lookup"><span data-stu-id="c8395-411">Therefore, **pass it by ref** rather than by value.</span></span> <span data-ttu-id="c8395-412">通过值传递它会导致结构复制，并且状态更改对调用方不可见。</span><span class="sxs-lookup"><span data-stu-id="c8395-412">Passing it by value would result in a struct copy and the state changes would not be visible to the caller.</span></span> <span data-ttu-id="c8395-413">这与 `Newtonsoft.Json` 不同，因为 `Newtonsoft.Json` `JsonTextReader` 是一个类。</span><span class="sxs-lookup"><span data-stu-id="c8395-413">This differs from `Newtonsoft.Json` since the `Newtonsoft.Json` `JsonTextReader` is a class.</span></span> <span data-ttu-id="c8395-414">有关如何使用 ref 结构的详细信息，请参阅[编写安全且高效C#的代码](../../csharp/write-safe-efficient-code.md)。</span><span class="sxs-lookup"><span data-stu-id="c8395-414">For more information about how to use ref structs, see [Write safe and efficient C# code](../../csharp/write-safe-efficient-code.md).</span></span>

### <a name="read-utf-8-text"></a><span data-ttu-id="c8395-415">读取 UTF-8 文本</span><span class="sxs-lookup"><span data-stu-id="c8395-415">Read UTF-8 text</span></span>

<span data-ttu-id="c8395-416">若要在使用 `Utf8JsonReader`时实现最佳性能，请阅读已经编码为 UTF-8 文本而不是 UTF-16 字符串的 JSON 有效负载。</span><span class="sxs-lookup"><span data-stu-id="c8395-416">To achieve the best possible performance while using the `Utf8JsonReader`, read JSON payloads already encoded as UTF-8 text rather than as UTF-16 strings.</span></span> <span data-ttu-id="c8395-417">有关代码示例，请参阅[使用 Utf8JsonReader 筛选数据](system-text-json-how-to.md#filter-data-using-utf8jsonreader)。</span><span class="sxs-lookup"><span data-stu-id="c8395-417">For a code example, see [Filter data using Utf8JsonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader).</span></span>

### <a name="read-with-a-stream-or-pipereader"></a><span data-ttu-id="c8395-418">使用流或 PipeReader 进行读取</span><span class="sxs-lookup"><span data-stu-id="c8395-418">Read with a Stream or PipeReader</span></span>

<span data-ttu-id="c8395-419">`Utf8JsonReader` 支持从 UTF-8 编码的[ReadOnlySpan\<byte >](xref:System.ReadOnlySpan%601)或[ReadOnlySequence\<字节 >](xref:System.Buffers.ReadOnlySequence%601) （这是从 <xref:System.IO.Pipelines.PipeReader>读取的结果）进行读取。</span><span class="sxs-lookup"><span data-stu-id="c8395-419">The `Utf8JsonReader` supports reading from a UTF-8 encoded [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) or [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) (which is the result of reading from a <xref:System.IO.Pipelines.PipeReader>).</span></span>

<span data-ttu-id="c8395-420">对于同步读取，可以读取 JSON 有效负载，直到流的末尾到字节数组中，并将其传递给读取器。</span><span class="sxs-lookup"><span data-stu-id="c8395-420">For synchronous reading, you could read the JSON payload until the end of the stream into a byte array and pass that into the reader.</span></span> <span data-ttu-id="c8395-421">若要从字符串读取（编码为 UTF-16），请调用 <xref:System.Text.Encoding.UTF8>。<xref:System.Text.Encoding.GetBytes%2A></span><span class="sxs-lookup"><span data-stu-id="c8395-421">For reading from a string (which is encoded as UTF-16), call <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A></span></span> <span data-ttu-id="c8395-422">首先将字符串转码为 UTF-8 编码的字节数组。</span><span class="sxs-lookup"><span data-stu-id="c8395-422">to first transcode the string to a UTF-8 encoded byte array.</span></span> <span data-ttu-id="c8395-423">然后将其传递到 `Utf8JsonReader`。</span><span class="sxs-lookup"><span data-stu-id="c8395-423">Then pass that to the `Utf8JsonReader`.</span></span> 

<span data-ttu-id="c8395-424">由于 `Utf8JsonReader` 将输入视为 JSON 文本，因此 UTF-8 字节顺序标记（BOM）被视为无效的 JSON。</span><span class="sxs-lookup"><span data-stu-id="c8395-424">Since the `Utf8JsonReader` considers the input to be JSON text, a UTF-8 byte order mark (BOM) is considered invalid JSON.</span></span> <span data-ttu-id="c8395-425">调用方需要在将数据传递给读取器之前对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="c8395-425">The caller needs to filter that out before passing the data to the reader.</span></span>

<span data-ttu-id="c8395-426">有关代码示例，请参阅[Use Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader)。</span><span class="sxs-lookup"><span data-stu-id="c8395-426">For code examples, see [Use Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader).</span></span>

### <a name="read-with-multi-segment-readonlysequence"></a><span data-ttu-id="c8395-427">阅读多段 ReadOnlySequence</span><span class="sxs-lookup"><span data-stu-id="c8395-427">Read with multi-segment ReadOnlySequence</span></span>

<span data-ttu-id="c8395-428">如果 JSON 输入是[ReadOnlySpan\<byte >](xref:System.ReadOnlySpan%601)，则每个 JSON 元素都可以通过读取循环从读取器上的 `ValueSpan` 属性进行访问。</span><span class="sxs-lookup"><span data-stu-id="c8395-428">If your JSON input is a [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), each JSON element can be accessed from the `ValueSpan` property on the reader as you go through the read loop.</span></span> <span data-ttu-id="c8395-429">但是，如果输入是[ReadOnlySequence\<byte >](xref:System.Buffers.ReadOnlySequence%601) （这是从 <xref:System.IO.Pipelines.PipeReader>中读取的结果），某些 JSON 元素可能会跨 `ReadOnlySequence<byte>` 对象的多个段。</span><span class="sxs-lookup"><span data-stu-id="c8395-429">However, if your input is a [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) (which is the result of reading from a <xref:System.IO.Pipelines.PipeReader>), some JSON elements might straddle multiple segments of the `ReadOnlySequence<byte>` object.</span></span> <span data-ttu-id="c8395-430">不能从连续内存块 <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> 访问这些元素。</span><span class="sxs-lookup"><span data-stu-id="c8395-430">These elements would not be accessible from <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> in a contiguous memory block.</span></span> <span data-ttu-id="c8395-431">相反，每次将多段 `ReadOnlySequence<byte>` 为输入时，请轮询读取器上的 <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> 属性，以确定如何访问当前 JSON 元素。</span><span class="sxs-lookup"><span data-stu-id="c8395-431">Instead, whenever you have a multi-segment `ReadOnlySequence<byte>` as input, poll the <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> property on the reader to figure out how to access the current JSON element.</span></span> <span data-ttu-id="c8395-432">下面是建议的模式：</span><span class="sxs-lookup"><span data-stu-id="c8395-432">Here's a recommended pattern:</span></span>

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

### <a name="use-valuetextequals-for-property-name-lookups"></a><span data-ttu-id="c8395-433">使用 ValueTextEquals 进行属性名称查找</span><span class="sxs-lookup"><span data-stu-id="c8395-433">Use ValueTextEquals for property name lookups</span></span>

<span data-ttu-id="c8395-434">不要使用 <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> 通过调用属性名称查找 <xref:System.MemoryExtensions.SequenceEqual%2A> 来执行逐字节的比较。</span><span class="sxs-lookup"><span data-stu-id="c8395-434">Don't use <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> to do byte-by-byte comparisons by calling <xref:System.MemoryExtensions.SequenceEqual%2A> for property name lookups.</span></span> <span data-ttu-id="c8395-435">改为调用 <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A>，因为该方法 unescapes 在 JSON 中转义的任何字符。</span><span class="sxs-lookup"><span data-stu-id="c8395-435">Call <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A> instead, because that method unescapes any characters that are escaped in the JSON.</span></span> <span data-ttu-id="c8395-436">下面的示例演示如何搜索名为 "name" 的属性：</span><span class="sxs-lookup"><span data-stu-id="c8395-436">Here's an example that shows how to search for a property that is named "name":</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a><span data-ttu-id="c8395-437">将 null 值读入可为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="c8395-437">Read null values into nullable value types</span></span>

<span data-ttu-id="c8395-438">`Newtonsoft.Json` 提供返回 <xref:System.Nullable%601>的 Api，如 `ReadAsBoolean`，通过返回 `TokenType` 来处理 `Null` `bool?`。</span><span class="sxs-lookup"><span data-stu-id="c8395-438">`Newtonsoft.Json` provides APIs that return <xref:System.Nullable%601>, such as `ReadAsBoolean`, which handles a `Null` `TokenType` for you by returning a `bool?`.</span></span> <span data-ttu-id="c8395-439">内置 `System.Text.Json` Api 仅返回不可以为 null 的值类型。</span><span class="sxs-lookup"><span data-stu-id="c8395-439">The built-in `System.Text.Json` APIs return only non-nullable value types.</span></span> <span data-ttu-id="c8395-440">例如，<xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> 返回 `bool`。</span><span class="sxs-lookup"><span data-stu-id="c8395-440">For example, <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> returns a `bool`.</span></span> <span data-ttu-id="c8395-441">如果它找到 JSON 中的 `Null`，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="c8395-441">It throws an exception if it finds `Null` in the JSON.</span></span> <span data-ttu-id="c8395-442">下面的示例演示了两种处理空值的方法，一个方法是通过返回一个可以为 null 的值类型，另一个是返回默认值：</span><span class="sxs-lookup"><span data-stu-id="c8395-442">The following examples show two ways to handle nulls, one by returning a nullable value type and one by returning the default value:</span></span>

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

### <a name="multi-targeting"></a><span data-ttu-id="c8395-443">多目标</span><span class="sxs-lookup"><span data-stu-id="c8395-443">Multi-targeting</span></span>

<span data-ttu-id="c8395-444">如果需要继续为某些目标框架使用 `Newtonsoft.Json`，则可以使用多个目标框架，并具有两种实现。</span><span class="sxs-lookup"><span data-stu-id="c8395-444">If you need to continue to use `Newtonsoft.Json` for certain target frameworks, you can multi-target and have two implementations.</span></span> <span data-ttu-id="c8395-445">但是，这并不是很简单，需要一些 `#ifdefs` 和源复制。</span><span class="sxs-lookup"><span data-stu-id="c8395-445">However, this is not trivial and would require some `#ifdefs` and source duplication.</span></span> <span data-ttu-id="c8395-446">共享尽可能多代码的一种方法是围绕 `Utf8JsonReader` 和 `Newtonsoft.Json` `JsonTextReader`创建 `ref struct` 包装。</span><span class="sxs-lookup"><span data-stu-id="c8395-446">One way to share as much code as possible is to create a `ref struct` wrapper around `Utf8JsonReader` and `Newtonsoft.Json` `JsonTextReader`.</span></span> <span data-ttu-id="c8395-447">此包装将统一公共 surface 区域，同时隔离行为差异。</span><span class="sxs-lookup"><span data-stu-id="c8395-447">This wrapper would unify the public surface area while isolating the behavioral differences.</span></span> <span data-ttu-id="c8395-448">这使您可以将这些更改与类型的构造隔离，并按引用传递新类型。</span><span class="sxs-lookup"><span data-stu-id="c8395-448">This lets you isolate the changes mainly to the construction of the type, along with passing the new type around by reference.</span></span> <span data-ttu-id="c8395-449">下面是[DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/)库的模式：</span><span class="sxs-lookup"><span data-stu-id="c8395-449">This is the pattern that the [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) library follows:</span></span>

* [<span data-ttu-id="c8395-450">UnifiedJsonReader.JsonTextReader.cs</span><span class="sxs-lookup"><span data-stu-id="c8395-450">UnifiedJsonReader.JsonTextReader.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [<span data-ttu-id="c8395-451">UnifiedJsonReader.Utf8JsonReader.cs</span><span class="sxs-lookup"><span data-stu-id="c8395-451">UnifiedJsonReader.Utf8JsonReader.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a><span data-ttu-id="c8395-452">Utf8JsonWriter 与 JsonTextWriter 的比较</span><span class="sxs-lookup"><span data-stu-id="c8395-452">Utf8JsonWriter compared to JsonTextWriter</span></span>

<span data-ttu-id="c8395-453"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> 是一种高性能的方式，用于从常见的 .NET 类型（如 `String`、`Int32`和 `DateTime`）编写 UTF-8 编码的 JSON 文本。</span><span class="sxs-lookup"><span data-stu-id="c8395-453"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="c8395-454">编写器是可用于生成自定义序列化程序的低级别类型。</span><span class="sxs-lookup"><span data-stu-id="c8395-454">The writer is a low-level type that can be used to build custom serializers.</span></span>

<span data-ttu-id="c8395-455">以下各节介绍使用 `Utf8JsonWriter`的推荐编程模式。</span><span class="sxs-lookup"><span data-stu-id="c8395-455">The following sections explain recommended programming patterns for using `Utf8JsonWriter`.</span></span>

### <a name="write-with-utf-8-text"></a><span data-ttu-id="c8395-456">用 UTF-8 文本编写</span><span class="sxs-lookup"><span data-stu-id="c8395-456">Write with UTF-8 text</span></span>

<span data-ttu-id="c8395-457">若要在使用 `Utf8JsonWriter`时实现最佳性能，请编写已经编码为 UTF-8 文本而不是 UTF-16 字符串的 JSON 有效负载。</span><span class="sxs-lookup"><span data-stu-id="c8395-457">To achieve the best possible performance while using the `Utf8JsonWriter`, write JSON payloads already encoded as UTF-8 text rather than as UTF-16 strings.</span></span> <span data-ttu-id="c8395-458">使用 <xref:System.Text.Json.JsonEncodedText> 将已知字符串属性名称和值作为静态缓存并预先编码，并将其传递给编写器，而不是使用 UTF-16 字符串文本。</span><span class="sxs-lookup"><span data-stu-id="c8395-458">Use <xref:System.Text.Json.JsonEncodedText> to cache and pre-encode known string property names and values as statics, and pass those to the writer, rather than using UTF-16 string literals.</span></span> <span data-ttu-id="c8395-459">这比缓存和使用 UTF-8 字节数组更快。</span><span class="sxs-lookup"><span data-stu-id="c8395-459">This is faster than caching and using UTF-8 byte arrays.</span></span>

<span data-ttu-id="c8395-460">如果需要进行自定义转义，此方法也适用。</span><span class="sxs-lookup"><span data-stu-id="c8395-460">This approach also works if you need to do custom escaping.</span></span> <span data-ttu-id="c8395-461">`System.Text.Json` 不允许在编写字符串时禁用转义。</span><span class="sxs-lookup"><span data-stu-id="c8395-461">`System.Text.Json` doesn't let you disable escaping while writing a string.</span></span> <span data-ttu-id="c8395-462">但是，你可以将自己的自定义 <xref:System.Text.Encodings.Web.JavaScriptEncoder> 作为一个选项传入写入器，或创建自己的 `JsonEncodedText`，使用你的 `JavascriptEncoder` 进行转义，然后写入 `JsonEncodedText` 而不是字符串。</span><span class="sxs-lookup"><span data-stu-id="c8395-462">However, you could pass in your own custom <xref:System.Text.Encodings.Web.JavaScriptEncoder> as an option to the writer, or create your own `JsonEncodedText` that uses your `JavascriptEncoder` to do the escaping, and then write the `JsonEncodedText` instead of the string.</span></span> <span data-ttu-id="c8395-463">有关详细信息，请参阅[自定义字符编码](system-text-json-how-to.md#customize-character-encoding)。</span><span class="sxs-lookup"><span data-stu-id="c8395-463">For more information, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="write-raw-values"></a><span data-ttu-id="c8395-464">写入原始值</span><span class="sxs-lookup"><span data-stu-id="c8395-464">Write raw values</span></span>

<span data-ttu-id="c8395-465">`Newtonsoft.Json` `WriteRawValue` 方法写入原始 JSON，其中应为值。</span><span class="sxs-lookup"><span data-stu-id="c8395-465">The `Newtonsoft.Json` `WriteRawValue` method writes raw JSON where a value is expected.</span></span> <span data-ttu-id="c8395-466"><xref:System.Text.Json> 没有直接等效项，但以下是确保仅编写有效 JSON 的解决方法：</span><span class="sxs-lookup"><span data-stu-id="c8395-466"><xref:System.Text.Json> has no direct equivalent, but here's a workaround that ensures only valid JSON is written:</span></span>

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a><span data-ttu-id="c8395-467">自定义字符转义</span><span class="sxs-lookup"><span data-stu-id="c8395-467">Customize character escaping</span></span>

<span data-ttu-id="c8395-468">`JsonTextWriter` 的[StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm)设置提供了用于转义所有非 ASCII 字符**或**HTML 字符的选项。</span><span class="sxs-lookup"><span data-stu-id="c8395-468">The [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) setting of `JsonTextWriter` offers options to escape all non-ASCII characters **or** HTML characters.</span></span> <span data-ttu-id="c8395-469">默认情况下，`Utf8JsonWriter` 转义所有非 ASCII**和**HTML 字符。</span><span class="sxs-lookup"><span data-stu-id="c8395-469">By default, `Utf8JsonWriter` escapes all non-ASCII **and** HTML characters.</span></span> <span data-ttu-id="c8395-470">这种转义是出于深层防御的安全原因。</span><span class="sxs-lookup"><span data-stu-id="c8395-470">This escaping is done for defense-in-depth security reasons.</span></span> <span data-ttu-id="c8395-471">若要指定不同的转义策略，请创建 <xref:System.Text.Encodings.Web.JavaScriptEncoder> 并设置 <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="c8395-471">To specify a different escaping policy, create a <xref:System.Text.Encodings.Web.JavaScriptEncoder> and set <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c8395-472">有关详细信息，请参阅[自定义字符编码](system-text-json-how-to.md#customize-character-encoding)。</span><span class="sxs-lookup"><span data-stu-id="c8395-472">For more information, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="customize-json-format"></a><span data-ttu-id="c8395-473">自定义 JSON 格式</span><span class="sxs-lookup"><span data-stu-id="c8395-473">Customize JSON format</span></span>

<span data-ttu-id="c8395-474">`JsonTextWriter` 包括以下设置，`Utf8JsonWriter` 没有等效项：</span><span class="sxs-lookup"><span data-stu-id="c8395-474">`JsonTextWriter` includes the following settings, for which `Utf8JsonWriter` has no equivalent:</span></span>

* <span data-ttu-id="c8395-475">[缩进](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm)-指定缩进的字符数。</span><span class="sxs-lookup"><span data-stu-id="c8395-475">[Indentation](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) - Specifies how many characters to indent.</span></span> <span data-ttu-id="c8395-476">`Utf8JsonWriter` 始终执行2个字符缩进。</span><span class="sxs-lookup"><span data-stu-id="c8395-476">`Utf8JsonWriter` always does 2-character indentation.</span></span>
* <span data-ttu-id="c8395-477">[IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) -指定要用于缩进的字符。</span><span class="sxs-lookup"><span data-stu-id="c8395-477">[IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) - Specifies the character to use for indentation.</span></span>  <span data-ttu-id="c8395-478">`Utf8JsonWriter` 始终使用空格。</span><span class="sxs-lookup"><span data-stu-id="c8395-478">`Utf8JsonWriter` always uses whitespace.</span></span>
* <span data-ttu-id="c8395-479">[QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) -指定用来包围字符串值的字符。</span><span class="sxs-lookup"><span data-stu-id="c8395-479">[QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) - Specifies the character to use to surround string values.</span></span>  <span data-ttu-id="c8395-480">`Utf8JsonWriter` 始终使用双引号。</span><span class="sxs-lookup"><span data-stu-id="c8395-480">`Utf8JsonWriter` always uses double quotes.</span></span>
* <span data-ttu-id="c8395-481">[QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) -指定是否将属性名称括在引号中。</span><span class="sxs-lookup"><span data-stu-id="c8395-481">[QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) - Specifies whether or not to surround property names with quotes.</span></span>  <span data-ttu-id="c8395-482">`Utf8JsonWriter` 总是用引号将它们括起来。</span><span class="sxs-lookup"><span data-stu-id="c8395-482">`Utf8JsonWriter` always surrounds them with quotes.</span></span>

<span data-ttu-id="c8395-483">没有解决方法可让你自定义以这些方式 `Utf8JsonWriter` 生成的 JSON。</span><span class="sxs-lookup"><span data-stu-id="c8395-483">There are no workarounds that would let you customize the JSON produced by `Utf8JsonWriter` in these ways.</span></span>

### <a name="write-null-values"></a><span data-ttu-id="c8395-484">写入空值</span><span class="sxs-lookup"><span data-stu-id="c8395-484">Write null values</span></span>

<span data-ttu-id="c8395-485">若要使用 `Utf8JsonWriter`来写入空值，请调用：</span><span class="sxs-lookup"><span data-stu-id="c8395-485">To write null values by using `Utf8JsonWriter`, call:</span></span>

* <span data-ttu-id="c8395-486"><xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A> 写入值为 null 的键值对。</span><span class="sxs-lookup"><span data-stu-id="c8395-486"><xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A> to write a key-value pair with null as the value.</span></span>
* <span data-ttu-id="c8395-487"><xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A> 将 null 作为 JSON 数组的元素写入。</span><span class="sxs-lookup"><span data-stu-id="c8395-487"><xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A> to write null as an element of a JSON array.</span></span>

<span data-ttu-id="c8395-488">对于字符串属性，如果字符串为 null，则 <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> 和 <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> 等效于 `WriteNull` 和 `WriteNullValue`。</span><span class="sxs-lookup"><span data-stu-id="c8395-488">For a string property, if the string is null, <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> and <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> are equivalent to `WriteNull` and `WriteNullValue`.</span></span>

### <a name="write-timespan-uri-or-char-values"></a><span data-ttu-id="c8395-489">写入 Timespan、Uri 或 char 值</span><span class="sxs-lookup"><span data-stu-id="c8395-489">Write Timespan, Uri, or char values</span></span>

<span data-ttu-id="c8395-490">`JsonTextWriter` 提供针对[TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm)、 [Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm)和[char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm)值的 `WriteValue` 方法。</span><span class="sxs-lookup"><span data-stu-id="c8395-490">`JsonTextWriter` provides `WriteValue` methods for [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm), and [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) values.</span></span> <span data-ttu-id="c8395-491">`Utf8JsonWriter` 没有等效的方法。</span><span class="sxs-lookup"><span data-stu-id="c8395-491">`Utf8JsonWriter` doesn't have equivalent methods.</span></span> <span data-ttu-id="c8395-492">相反，请将这些值设置为字符串格式（例如，通过调用 `ToString()`）并调用 <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>。</span><span class="sxs-lookup"><span data-stu-id="c8395-492">Instead, format these values as strings (by calling `ToString()`, for example) and call <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>.</span></span>

### <a name="multi-targeting"></a><span data-ttu-id="c8395-493">多目标</span><span class="sxs-lookup"><span data-stu-id="c8395-493">Multi-targeting</span></span>

<span data-ttu-id="c8395-494">如果需要继续为某些目标框架使用 `Newtonsoft.Json`，则可以使用多个目标框架，并具有两种实现。</span><span class="sxs-lookup"><span data-stu-id="c8395-494">If you need to continue to use `Newtonsoft.Json` for certain target frameworks, you can multi-target and have two implementations.</span></span> <span data-ttu-id="c8395-495">但是，这并不是很简单，需要一些 `#ifdefs` 和源复制。</span><span class="sxs-lookup"><span data-stu-id="c8395-495">However, this is not trivial and would require some `#ifdefs` and source duplication.</span></span> <span data-ttu-id="c8395-496">共享尽可能多的代码的一种方法是创建围绕 `Utf8JsonWriter` 和 `Newtonsoft` `JsonTextWriter`的包装。</span><span class="sxs-lookup"><span data-stu-id="c8395-496">One way to share as much code as possible is to create a wrapper around `Utf8JsonWriter` and `Newtonsoft` `JsonTextWriter`.</span></span> <span data-ttu-id="c8395-497">此包装将统一公共 surface 区域，同时隔离行为差异。</span><span class="sxs-lookup"><span data-stu-id="c8395-497">This wrapper would unify the public surface area while isolating the behavioral differences.</span></span> <span data-ttu-id="c8395-498">这使您可以将主要更改隔离为类型的构造。</span><span class="sxs-lookup"><span data-stu-id="c8395-498">This lets you isolate the changes mainly to the construction of the type.</span></span> <span data-ttu-id="c8395-499">[DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/)库如下：</span><span class="sxs-lookup"><span data-stu-id="c8395-499">[Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) library follows:</span></span>

* [<span data-ttu-id="c8395-500">UnifiedJsonWriter.JsonTextWriter.cs</span><span class="sxs-lookup"><span data-stu-id="c8395-500">UnifiedJsonWriter.JsonTextWriter.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [<span data-ttu-id="c8395-501">UnifiedJsonWriter.Utf8JsonWriter.cs</span><span class="sxs-lookup"><span data-stu-id="c8395-501">UnifiedJsonWriter.Utf8JsonWriter.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a><span data-ttu-id="c8395-502">其他资源</span><span class="sxs-lookup"><span data-stu-id="c8395-502">Additional resources</span></span>

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* [<span data-ttu-id="c8395-503">System.web 概述</span><span class="sxs-lookup"><span data-stu-id="c8395-503">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="c8395-504">如何使用 system.exception</span><span class="sxs-lookup"><span data-stu-id="c8395-504">How to use System.Text.Json</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="c8395-505">如何编写自定义转换器</span><span class="sxs-lookup"><span data-stu-id="c8395-505">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="c8395-506">系统中的 DateTime 和 DateTimeOffset 支持</span><span class="sxs-lookup"><span data-stu-id="c8395-506">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* [<span data-ttu-id="c8395-507">System.web API 参考</span><span class="sxs-lookup"><span data-stu-id="c8395-507">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="c8395-508">System.web. 串行化 API 参考</span><span class="sxs-lookup"><span data-stu-id="c8395-508">System.Text.Json.Serialization API reference</span></span>](xref:System.Text.Json.Serialization)
