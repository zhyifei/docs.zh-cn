---
ms.openlocfilehash: c9547cdc2f127cf13a3610118a26736930fcd8bd
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021601"
---
### <a name="change-in-semantics-of-stringnull-in-utf8jsonwriter"></a><span data-ttu-id="e5085-101">Utf8JsonWriter 中的 `(string)null` 语义更改</span><span class="sxs-lookup"><span data-stu-id="e5085-101">Change in semantics of `(string)null` in Utf8JsonWriter</span></span>

<span data-ttu-id="e5085-102">在 .NET Core 3.0 预览版 7 中，null 字符串在 <xref:System.Text.Json.Utf8JsonWriter> 中被视为空字符串。</span><span class="sxs-lookup"><span data-stu-id="e5085-102">In .NET Core 3.0 Preview 7, the null string is treated as the empty string in <xref:System.Text.Json.Utf8JsonWriter>.</span></span> <span data-ttu-id="e5085-103">从 .NET Core 3.0 预览版 8 开始，null 字符串在用作属性名称时将引发异常，在用作值时发出 JSON null 令牌。</span><span class="sxs-lookup"><span data-stu-id="e5085-103">Starting with .NET Core 3.0 Preview 8, the null string throws an exception when used as a property name, and it emits the JSON null token when used as a value.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e5085-104">更改描述</span><span class="sxs-lookup"><span data-stu-id="e5085-104">Change description</span></span>

<span data-ttu-id="e5085-105">在 .NET Core 3.0 预览版 7 中，当编写属性名称和编写值时，`null` 字符串都被视为 `""`。</span><span class="sxs-lookup"><span data-stu-id="e5085-105">In .NET Core 3.0 Preview 7, the `null` string was treated as `""` both when writing property names and when writing values.</span></span>  

<span data-ttu-id="e5085-106">从 .NET Core 3.0 预览版 8 开始，`null` 属性名称将引发 `ArgumentNullException`，`null` 值被视为对 <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A?displayProperty=nameWithType> 或 <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue?displayProperty=nameWithType> 的调用。</span><span class="sxs-lookup"><span data-stu-id="e5085-106">Starting with .NET Core 3.0 Preview 8, a `null` property name throws an `ArgumentNullException`, and a `null` value is treated as a call to <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A?displayProperty=nameWithType> or <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="e5085-107">考虑下列代码：</span><span class="sxs-lookup"><span data-stu-id="e5085-107">Consider the following code:</span></span>

```csharp
string propertyName1 = null;
string propertyValue1 = null;
string propertyName2 = "prop2";
string propertyValue2 = null;
string simpleValue1 = null;

using (Utf8JsonWriter writer = new Utf8JsonWriter(stream))
{
    writer.WriteStartArray();

    writer.WriteStartObject();
    writer.WriteString(propertyName1, propertyValue1);
    writer.WriteString(propertyName2, propertyValue2);
    writer.WriteEndObject();

    writer.WriteStringValue(simpleValue1);

    writer.WriteEndArray();
}
```

<span data-ttu-id="e5085-108">如果运行 .NET Core 3.0 预览版 7，编写器将生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="e5085-108">If run with .NET Core 3.0 Preview 7, the writer produces the following output:</span></span>

```js
[{"":"","prop2":""},""]
```

<span data-ttu-id="e5085-109">从 .NET Core 3.0 预览版 8 开始，对 `writer.WriteString(propertyName1, propertyValue1)` 的调用将引发 <xref:System.ArgumentNullException>。</span><span class="sxs-lookup"><span data-stu-id="e5085-109">Starting with .NET Core 3.0 Preview 8, the call to `writer.WriteString(propertyName1, propertyValue1)` throws an <xref:System.ArgumentNullException>.</span></span>  <span data-ttu-id="e5085-110">如果将 `propertyName1 = null` 替换为 `propertyName1 = string.Empty`，则输出现在为：</span><span class="sxs-lookup"><span data-stu-id="e5085-110">If `propertyName1 = null` is replaced with `propertyName1 = string.Empty`, the output would now be:</span></span>

```js
[{"":null,"prop2":null},null]
```

<span data-ttu-id="e5085-111">进行此更改是为了更好地与调用方对 `null` 值的预期相符。</span><span class="sxs-lookup"><span data-stu-id="e5085-111">This change was made to better align with caller expectations for `null` values.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e5085-112">引入的版本</span><span class="sxs-lookup"><span data-stu-id="e5085-112">Version introduced</span></span>

<span data-ttu-id="e5085-113">3.0 预览版 8</span><span class="sxs-lookup"><span data-stu-id="e5085-113">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e5085-114">建议操作</span><span class="sxs-lookup"><span data-stu-id="e5085-114">Recommended action</span></span>

<span data-ttu-id="e5085-115">当用 <xref:System.Text.Json.Utf8JsonWriter> 类编写属性名称和值时：</span><span class="sxs-lookup"><span data-stu-id="e5085-115">When writing property names and values with the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

- <span data-ttu-id="e5085-116">确保使用非 `null` 字符串作为属性名称。</span><span class="sxs-lookup"><span data-stu-id="e5085-116">Ensure non-`null` strings are used as property names.</span></span>

- <span data-ttu-id="e5085-117">如果需要以前的行为，请使用 null 合并调用；例如 `writer.WriteString(propertyName1 ?? "", propertyValue1)`。</span><span class="sxs-lookup"><span data-stu-id="e5085-117">If the previous behavior is desired, use a null coalescing invocation; for example, `writer.WriteString(propertyName1 ?? "", propertyValue1)`.</span></span>

- <span data-ttu-id="e5085-118">如果不需要为 `null` 字符串值编写 `null` 文本，则使用 null 合并调用；例如 `writer.WriteString(propertyName2, propertyValue2 ?? "")`。</span><span class="sxs-lookup"><span data-stu-id="e5085-118">If writing a `null` literal for a `null` string value is not desirable, use a null coalescing invocation; for example, `writer.WriteString(propertyName2, propertyValue2 ?? "")`.</span></span>

#### <a name="category"></a><span data-ttu-id="e5085-119">类别</span><span class="sxs-lookup"><span data-stu-id="e5085-119">Category</span></span>

<span data-ttu-id="e5085-120">Core .NET 库</span><span class="sxs-lookup"><span data-stu-id="e5085-120">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e5085-121">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="e5085-121">Affected APIs</span></span>

- <xref:System.Text.Json.Utf8JsonWriter.WriteBase64String(System.String,System.ReadOnlySpan%7BSystem.Byte%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteBoolean(System.String,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNull(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int32)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int64)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt32)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt64)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Single)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Double)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Decimal)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStartArray(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStartObject(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan%7BSystem.Byte%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan%7BSystem.Char%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Text.Json.JsonEncodedText)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTime)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTimeOffset)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Guid)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName(System.String)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.Utf8JsonWriter.WriteBase64String(System.String,System.ReadOnlySpan{System.Byte})`
- `M:System.Text.Json.Utf8JsonWriter.WriteBoolean(System.String,System.Boolean)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNull(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int32)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int64)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt32)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt64)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Single)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Double)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Decimal)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStartArray(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStartObject(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan{System.Byte})`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan{System.Char})`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Text.Json.JsonEncodedText)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTime)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTimeOffset)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Guid)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WritePropertyName(System.String)`

-->
