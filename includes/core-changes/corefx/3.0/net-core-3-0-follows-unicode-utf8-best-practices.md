---
ms.openlocfilehash: db1d09c8c9e606b5327a42977a74a74703282d84
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568072"
---
### <a name="net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences"></a>当替换格式错误的 UTF-8 字节序列时，.NET Core 3.0 遵循 Unicode 最佳做法

如果 <xref:System.Text.UTF8Encoding> 类在执行字节到字符的转码操作期间遇到格式错误的 UTF-8 字节序列，它会在输出字符串中将该序列替换为 '�'（U+FFFD 替换字符）字符。 .NET Core 3.0 与以前版本的 .NET Core 和 .NET Framework 的不同之处在于，在转码操作期间按照 Unicode 最佳做法执行此替换。

这是在整个 .NET 中改进 UTF-8 处理的较大工作量（包括通过新的 <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> 和 <xref:System.Text.Rune?displayProperty=nameWithType> 类型）的一部分。 为 <xref:System.Text.UTF8Encoding> 类型提供了改进的错误处理机制，以便生成与新引入的类型一致的输出。

#### <a name="change-description"></a>更改描述

从 .NET Core 3.0 开始，当将字节转码为字符时，<xref:System.Text.UTF8Encoding> 类会根据 Unicode 最佳做法执行字符替换。 [Unicode 标准 12.0 版第 3.9 节 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) 的  “U+FFFD 替换最大子部分”标题中描述了使用的替换机制。

仅当  输入字节序列包含格式错误的 UTF-8 数据时，此行为才适用。 此外，如果已通过 `throwOnInvalidBytes: true` 构造了 <xref:System.Text.UTF8Encoding> 实例（请参阅 [UTF8Encoding 构造函数文档] <xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>），则 `UTF8Encoding` 实例将继续对无效输入引发，而不是执行 U+FFFD 替换。

下面通过无效的 3 字节输入说明了此更改的影响：

|格式无效的 3 字节输入|.NET Core 3.0 之前的输出|从 .NET Core 3.0 开始的输出|
|---|---|---|
| `[ ED A0 90 ]` | `[ FFFD FFFD ]`（2 字符输出）| `[ FFFD FFFD FFFD ]`（3 字符输出）|

根据以前链接的 Unicode 标准 PDF 的表 3-9  ，此 3 字符输出为首选输出。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="recommended-action"></a>建议的操作

开发人员一方不需要执行任何操作。

#### <a name="category"></a>类别

CoreFx

#### <a name="affected-apis"></a>受影响的 API

- <xref:System.Text.UTF8Encoding.GetCharCount%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetChars%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.UTF8Encoding.GetCharCount`
- `Overload:System.Text.UTF8Encoding.GetChars`
- `M:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)`

-->
