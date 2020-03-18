---
ms.openlocfilehash: 79901d0b57816915ca7ea73cfe7fa3d40820434e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568140"
---
### <a name="jsonelement-api-changes"></a><span data-ttu-id="423ea-101">JsonElement API 更改</span><span class="sxs-lookup"><span data-stu-id="423ea-101">JsonElement API changes</span></span>

<span data-ttu-id="423ea-102">从 .NET Core 3.0 预览版 7 开始，某些 <xref:System.Text.Json.JsonElement> API 已更改，以实现更轻松的发现和更高的可用性。</span><span class="sxs-lookup"><span data-stu-id="423ea-102">Starting with .NET Core 3.0 Preview 7, some <xref:System.Text.Json.JsonElement> APIs have changed to allow for easier discovery and greater usability.</span></span>

#### <a name="change-description"></a><span data-ttu-id="423ea-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="423ea-103">Change description</span></span>

<span data-ttu-id="423ea-104">在 .NET Core 3.0 预览版 7 中，<xref:System.Text.Json.JsonElement> API 已进行如下更改，以实现更轻松的发现和更高的可用性。</span><span class="sxs-lookup"><span data-stu-id="423ea-104">In .NET Core 3.0 Preview 7, <xref:System.Text.Json.JsonElement> APIs have changed as follows to allow for easier discovery and greater usability.</span></span>

1. <span data-ttu-id="423ea-105">所有 `WriteProperty` 方法重载已从 <xref:System.Text.Json.JsonElement> 中移除。</span><span class="sxs-lookup"><span data-stu-id="423ea-105">All `WriteProperty` method overloads were removed from <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="423ea-106">这会影响诸如以下内容的代码：</span><span class="sxs-lookup"><span data-stu-id="423ea-106">This affects code such as the following:</span></span>

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

1. <span data-ttu-id="423ea-107">`WriteValue` 已重命名为 <xref:System.Text.Json.JsonElement.WriteTo%2A>。</span><span class="sxs-lookup"><span data-stu-id="423ea-107">`WriteValue` was renamed as <xref:System.Text.Json.JsonElement.WriteTo%2A>.</span></span> <span data-ttu-id="423ea-108">这会影响诸如以下内容的代码：</span><span class="sxs-lookup"><span data-stu-id="423ea-108">This affects code such as the following:</span></span>

   ```csharp
    using (JsonDocument doc = JsonDocument.Parse(jsonString))
    {
        JsonElement root = doc.RootElement;
        root.WriteValue(writer);
    }
    ```

1. <span data-ttu-id="423ea-109">现在，<xref:System.Text.Json.JsonElement.WriteTo%2A> 在其方法参数为 <xref:System.ArgumentNullException> 时引发 `null`。</span><span class="sxs-lookup"><span data-stu-id="423ea-109"><xref:System.Text.Json.JsonElement.WriteTo%2A> now throws an <xref:System.ArgumentNullException> when its method parameter is `null`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="423ea-110">引入的版本</span><span class="sxs-lookup"><span data-stu-id="423ea-110">Version introduced</span></span>

<span data-ttu-id="423ea-111">3.0 预览版 7</span><span class="sxs-lookup"><span data-stu-id="423ea-111">3.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="423ea-112">建议操作</span><span class="sxs-lookup"><span data-stu-id="423ea-112">Recommended action</span></span>

<span data-ttu-id="423ea-113">如果你的代码受这些更改的影响，则可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="423ea-113">If your code is affected by these changes, you can do the following:</span></span>

- <span data-ttu-id="423ea-114">`WriteProperty` 中没有用于 <xref:System.Text.Json.JsonElement> 重载的替换 API。</span><span class="sxs-lookup"><span data-stu-id="423ea-114">There is no replacement API for the `WriteProperty` overloads in <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="423ea-115">相反，你可在调用 <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> 方法时一并调用某个 <xref:System.Text.Json.JsonElement.WriteTo%2A> 重载，以获得相同的结果。</span><span class="sxs-lookup"><span data-stu-id="423ea-115">Instead, you can call one of the <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> overloads along with the <xref:System.Text.Json.JsonElement.WriteTo%2A> method to achieve the same result.</span></span> <span data-ttu-id="423ea-116">例如:</span><span class="sxs-lookup"><span data-stu-id="423ea-116">For example:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       writer.WritePropertyName(propertyNameString);
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="423ea-117">将 `WriteValue` 方法重命名为 <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>。</span><span class="sxs-lookup"><span data-stu-id="423ea-117">Rename the `WriteValue` method to <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>.</span></span> <span data-ttu-id="423ea-118">方法参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="423ea-118">The method parameter remains unchanged.</span></span> <span data-ttu-id="423ea-119">例如，上面的代码应更改为以下代码：</span><span class="sxs-lookup"><span data-stu-id="423ea-119">For example, the previous code should be changed to the following:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="423ea-120">处理对 <xref:System.ArgumentNullException> 方法的调用中的 <xref:System.Text.Json.JsonElement.WriteTo%2A>。</span><span class="sxs-lookup"><span data-stu-id="423ea-120">Handle the <xref:System.ArgumentNullException> in calls to the <xref:System.Text.Json.JsonElement.WriteTo%2A> method.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="423ea-121">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="423ea-121">Affected APIs</span></span>

- <xref:System.Text.Json.JsonElement>
- <xref:System.Text.Json.JsonElement.WriteTo%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonElement.WriteProperty`
- `M:System.Text.Json.JsonElement.WriteValue(System.Text.Json.Utf8JsonWriter)`

-->
