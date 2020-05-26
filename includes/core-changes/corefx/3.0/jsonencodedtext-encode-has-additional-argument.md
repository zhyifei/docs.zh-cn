---
ms.openlocfilehash: d90996ae1b87cdea815daf979bece094d8602f70
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721506"
---
### <a name="jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument"></a><span data-ttu-id="49b75-101">JsonEncodedText.Encode 方法具有附加的 JavaScriptEncoder 参数</span><span class="sxs-lookup"><span data-stu-id="49b75-101">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>

<span data-ttu-id="49b75-102">从 .NET Core 3.0 预览版 8 开始，<xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> 方法包含可选的 <xref:System.Text.Encodings.Web.JavaScriptEncoder> 参数。</span><span class="sxs-lookup"><span data-stu-id="49b75-102">Starting with .NET Core 3.0 Preview 8, the <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> methods contain an optional <xref:System.Text.Encodings.Web.JavaScriptEncoder> argument.</span></span>

#### <a name="change-description"></a><span data-ttu-id="49b75-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="49b75-103">Change description</span></span>

<span data-ttu-id="49b75-104">.NET Core 3.0 包含一个新类型 xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="49b75-104">.NET Core 3.0 includes a new type, xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="49b75-105">从 .NET Core 3.0 预览版 8 开始，所有 <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> 方法重载的签名都已更改，以包含可选的 <xref:System.Text.Encodings.Web.JavaScriptEncoder> 参数。</span><span class="sxs-lookup"><span data-stu-id="49b75-105">Starting with .NET Core 3.0 Preview 8, the signature of all <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> method overloads has changed to include an optional <xref:System.Text.Encodings.Web.JavaScriptEncoder> parameter.</span></span> <span data-ttu-id="49b75-106">进行此更改是为了允许不同的或自定义编码器。</span><span class="sxs-lookup"><span data-stu-id="49b75-106">This change was made to allow for a different or custom encoder.</span></span>

<span data-ttu-id="49b75-107">.NET Core 3.0 预览版 7 中的 `Encode` 方法的签名为：</span><span class="sxs-lookup"><span data-stu-id="49b75-107">The signature of the `Encode` methods in .NET Core 3.0 Preview 7 is:</span></span>

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

<span data-ttu-id="49b75-108">.NET Core 3.0 预览版 8 及更高版本中的相同 `Encode` 方法的签名为：</span><span class="sxs-lookup"><span data-stu-id="49b75-108">The signature of the same `Encode` methods in .NET Core 3.0 Preview 8 and later versions is:</span></span>

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

#### <a name="version-introduced"></a><span data-ttu-id="49b75-109">引入的版本</span><span class="sxs-lookup"><span data-stu-id="49b75-109">Version introduced</span></span>

<span data-ttu-id="49b75-110">.NET Core 3.0 预览版 8</span><span class="sxs-lookup"><span data-stu-id="49b75-110">.NET Core 3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="49b75-111">建议操作</span><span class="sxs-lookup"><span data-stu-id="49b75-111">Recommended action</span></span>

<span data-ttu-id="49b75-112">这只是二进制的重大变更；针对 .NET Core 3.0 预览版 8 或更高版本的重新编译将修复所有运行时问题。</span><span class="sxs-lookup"><span data-stu-id="49b75-112">This is a binary breaking change only; a recompile against .NET Core 3.0 Preview 8 or a later version will fix any runtime issues.</span></span>

#### <a name="category"></a><span data-ttu-id="49b75-113">类别</span><span class="sxs-lookup"><span data-stu-id="49b75-113">Category</span></span>

<span data-ttu-id="49b75-114">Core .NET 库</span><span class="sxs-lookup"><span data-stu-id="49b75-114">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="49b75-115">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="49b75-115">Affected APIs</span></span>

- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Byte%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Char%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Byte},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Char},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)`

-->
