---
ms.openlocfilehash: 79901d0b57816915ca7ea73cfe7fa3d40820434e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568140"
---
### <a name="jsonelement-api-changes"></a>JsonElement API 更改

从 .NET Core 3.0 预览版 7 开始，某些 <xref:System.Text.Json.JsonElement> API 已更改，以实现更轻松的发现和更高的可用性。

#### <a name="change-description"></a>更改描述

在 .NET Core 3.0 预览版 7 中，<xref:System.Text.Json.JsonElement> API 已进行如下更改，以实现更轻松的发现和更高的可用性。

1. 所有 `WriteProperty` 方法重载已从 <xref:System.Text.Json.JsonElement> 中移除。 这会影响诸如以下内容的代码：

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
      JsonElement root = doc.RootElement;
      root.WriteProperty(propertyNameString, writer);
      // ..
      root.WriteProperty(propertyNameSpan, writer);
      // ..
      root.WriteProperty(propertyNameJsonEncoded, writer);
      // ..
      root.WriteProperty(utf8PropertyName, writer);
      //..
   }
   ```

1. `WriteValue` 已重命名为 <xref:System.Text.Json.JsonElement.WriteTo%2A>。 这会影响诸如以下内容的代码：

   ```csharp
    using (JsonDocument doc = JsonDocument.Parse(jsonString))
    {
        JsonElement root = doc.RootElement;
        root.WriteValue(writer);
    }
    ```

1. 现在，<xref:System.Text.Json.JsonElement.WriteTo%2A> 在其方法参数为 <xref:System.ArgumentNullException> 时引发 `null`。

#### <a name="version-introduced"></a>引入的版本

3.0 预览版 7

#### <a name="recommended-action"></a>建议操作

如果你的代码受这些更改的影响，则可以执行以下操作：

- `WriteProperty` 中没有用于 <xref:System.Text.Json.JsonElement> 重载的替换 API。 相反，你可在调用 <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> 方法时一并调用某个 <xref:System.Text.Json.JsonElement.WriteTo%2A> 重载，以获得相同的结果。 例如:

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       writer.WritePropertyName(propertyNameString);
       root.WriteTo(writer);
   }
   ```

- 将 `WriteValue` 方法重命名为 <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>。 方法参数保持不变。 例如，上面的代码应更改为以下代码：

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       root.WriteTo(writer);
   }
   ```

- 处理对 <xref:System.ArgumentNullException> 方法的调用中的 <xref:System.Text.Json.JsonElement.WriteTo%2A>。

#### <a name="affected-apis"></a>受影响的 API

- <xref:System.Text.Json.JsonElement>
- <xref:System.Text.Json.JsonElement.WriteTo%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonElement.WriteProperty`
- `M:System.Text.Json.JsonElement.WriteValue(System.Text.Json.Utf8JsonWriter)`

-->
