---
ms.openlocfilehash: 375a6f57a867c2a11fe95753c1085d6d708db2bd
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237299"
---
### <a name="jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument"></a><span data-ttu-id="cd92a-101">JsonEncodedText.Encode 方法具有附加的 JavaScriptEncoder 参数</span><span class="sxs-lookup"><span data-stu-id="cd92a-101">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>

<span data-ttu-id="cd92a-102">从 .NET Core 3.0 预览版 8 开始，<xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> 方法包含可选的 <xref:System.Text.Encodings.Web.JavaScriptEncoder> 参数。</span><span class="sxs-lookup"><span data-stu-id="cd92a-102">Starting with .NET Core 3.0 Preview 8, the <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> methods contain an optional <xref:System.Text.Encodings.Web.JavaScriptEncoder> argument.</span></span>

#### <a name="change-description"></a><span data-ttu-id="cd92a-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="cd92a-103">Change description</span></span>

<span data-ttu-id="cd92a-104">.NET Core 3.0 包含一个新类型 xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="cd92a-104">.NET Core 3.0 includes a new type, xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cd92a-105">从 .NET Core 3.0 预览版 8 开始，所有 <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> 方法重载的签名都已更改，以包含可选的 <xref:System.Text.Encodings.Web.JavaScriptEncoder> 参数。</span><span class="sxs-lookup"><span data-stu-id="cd92a-105">Starting with .NET Core 3.0 Preview 8, the signature of all <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> method overloads has changed to include an optional <xref:System.Text.Encodings.Web.JavaScriptEncoder> parameter.</span></span> <span data-ttu-id="cd92a-106">进行此更改是为了允许不同的或自定义编码器。</span><span class="sxs-lookup"><span data-stu-id="cd92a-106">This change was made to allow for a different or custom encoder.</span></span>

<span data-ttu-id="cd92a-107">.NET Core 3.0 预览版 7 中的 `Encode` 方法的签名为：</span><span class="sxs-lookup"><span data-stu-id="cd92a-107">The signature of the `Encode` methods in .NET Core 3.0 Preview 7 is:</span></span>

```csharp
namespace System.Text.Json
{
    public readonly struct JsonEncodedText
    {
        public static JsonEncodedText Encode(ReadOnlySpan<byte> utf8Value);
        public static JsonEncodedText Encode(ReadOnlySpan<char> value);
        public static JsonEncodedText Encode(string value);
    }
}
```

<span data-ttu-id="cd92a-108">.NET Core 3.0 预览版 8 及更高版本中的相同 `Encode` 方法的签名为：</span><span class="sxs-lookup"><span data-stu-id="cd92a-108">The signature of the same `Encode` methods in .NET Core 3.0 Preview 8 and later versions is:</span></span>

```csharp
namespace System.Text.Json
{
    public readonly struct JsonEncodedText
    {
        public static JsonEncodedText Encode(ReadOnlySpan<byte> utf8Value, JavaScriptEncoder encoder = null);
        public static JsonEncodedText Encode(ReadOnlySpan<char> value, JavaScriptEncoder encoder = null);
        public static JsonEncodedText Encode(string value, JavaScriptEncoder encoder = null);
    }
}
```

#### <a name="version-introduced"></a><span data-ttu-id="cd92a-109">引入的版本</span><span class="sxs-lookup"><span data-stu-id="cd92a-109">Version introduced</span></span>

<span data-ttu-id="cd92a-110">.NET Core 3.0 预览版 8</span><span class="sxs-lookup"><span data-stu-id="cd92a-110">.NET Core 3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cd92a-111">建议的操作</span><span class="sxs-lookup"><span data-stu-id="cd92a-111">Recommended action</span></span>

<span data-ttu-id="cd92a-112">这只是二进制的重大变更；针对 .NET Core 3.0 预览版 8 或更高版本的重新编译将修复所有运行时问题。</span><span class="sxs-lookup"><span data-stu-id="cd92a-112">This is a binary breaking change only; a recompile against .NET Core 3.0 Preview 8 or a later version will fix any runtime issues.</span></span>

#### <a name="category"></a><span data-ttu-id="cd92a-113">类别</span><span class="sxs-lookup"><span data-stu-id="cd92a-113">Category</span></span>

<span data-ttu-id="cd92a-114">CoreFx</span><span class="sxs-lookup"><span data-stu-id="cd92a-114">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cd92a-115">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="cd92a-115">Affected APIs</span></span>

<xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Byte%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
<xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Char%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
<xref:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Byte},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Char},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)`

-->
