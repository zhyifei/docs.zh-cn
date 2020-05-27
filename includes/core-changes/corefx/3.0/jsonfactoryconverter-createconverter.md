---
ms.openlocfilehash: 43da6233b70927e7320874772976b9e93a0bd69f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83720997"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a>JsonFactoryConverter.CreateConverter 签名已更改

为了促进 <xref:System.Text.Json.Serialization.JsonConverterFactory> 类的构成，已使 <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> 方法成为公共方法，并给出了类型为 <xref:System.Text.Json.JsonSerializerOptions> 的第二个参数。

#### <a name="change-description"></a>更改描述

在版本 3.0 预览版 8 之前，.Net Core 中的 `CreateConverter` 方法的签名如下：

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

在 .NET Core 3.0 预览版 8 及更高版本中，则为：

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

在进行此更改之前，很难编写密封的工厂转换器，因为无法轻松地从中获取 <xref:System.Text.Json.Serialization.JsonConverter%601>。 让工厂方法成为公共方法，同时传递当前 <xref:System.Text.Json.JsonSerializerOptions>，允许实现更灵活的构造。

#### <a name="version-introduced"></a>引入的版本

3.0 预览版 8

#### <a name="recommended-action"></a>建议操作

需要更新并重新编译派生类。

#### <a name="affected-apis"></a>受影响的 API

- <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>

<!-- For tool use only

#### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
