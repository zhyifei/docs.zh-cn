---
ms.openlocfilehash: cc3251e3b31143bd95793b407e50cf76e0e30142
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021626"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a>Json 序列化程序异常类型从 `JsonException` 更改为 `NotSupportedException`

在 .NET Core 3.0 预览版 6 到 8 中，如果序列化程序遇到不受支持的派生集合类型，则会引发 <xref:System.Text.Json.JsonException>。 从 .NET Core 3.0 预览版 9 开始，序列化程序转而引发 <xref:System.NotSupportedException>。

#### <a name="change-description"></a>更改描述

在 .NET Core 3.0 预览版 6 到预览版 8 中，如果序列化程序遇到不受支持的派生集合类型，则会引发 <xref:System.Text.Json.JsonException>。 不受支持的派生集合类型  是任何不能分配给以下类型之一的集合类型：

- <xref:System.Collections.IList>
- <xref:System.Collections.Generic.ICollection%601>
- <xref:System.Collections.Generic.Stack%601>
- <xref:System.Collections.Generic.Queue%601>
- <xref:System.Collections.IDictionary>
- [IDictionary\<String,T>](xref:System.Collections.Generic.IDictionary%602)

从 .NET Core 3.0 预览版 9 开始，序列化程序在遇到不受支持的集合类型时会引发 <xref:System.NotSupportedException>。 新的异常类型更好地反映了反序列化操作失败的原因。

#### <a name="version-introduced"></a>引入的版本

3.0 预览版 9

#### <a name="recommended-action"></a>建议操作

如果要在反序列化时捕获 <xref:System.Text.Json.JsonException>，则可能要考虑同时捕获 <xref:System.NotSupportedException>。

#### <a name="category"></a>类别

Core .NET 库

#### <a name="affected-apis"></a>受影响的 API

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
