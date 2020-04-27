---
ms.openlocfilehash: 2afe5ae80c2d7feca89737b767a6335950d04416
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021649"
---
### <a name="jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument"></a>JsonEncodedText.Encode 方法具有附加的 JavaScriptEncoder 参数

从 .NET Core 3.0 预览版 8 开始，<xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> 方法包含可选的 <xref:System.Text.Encodings.Web.JavaScriptEncoder> 参数。

#### <a name="change-description"></a>更改描述

.NET Core 3.0 包含一个新类型 xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>。 从 .NET Core 3.0 预览版 8 开始，所有 <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> 方法重载的签名都已更改，以包含可选的 <xref:System.Text.Encodings.Web.JavaScriptEncoder> 参数。 进行此更改是为了允许不同的或自定义编码器。

.NET Core 3.0 预览版 7 中的 `Encode` 方法的签名为：

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

.NET Core 3.0 预览版 8 及更高版本中的相同 `Encode` 方法的签名为：

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

#### <a name="version-introduced"></a>引入的版本

.NET Core 3.0 预览版 8

#### <a name="recommended-action"></a>建议操作

这只是二进制的重大变更；针对 .NET Core 3.0 预览版 8 或更高版本的重新编译将修复所有运行时问题。

#### <a name="category"></a>类别

Core .NET 库

#### <a name="affected-apis"></a>受影响的 API

- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Byte%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Char%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Byte},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Char},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)`

-->
