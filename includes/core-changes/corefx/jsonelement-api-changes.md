---
ms.openlocfilehash: 98893470b64de4abf7f04817871e3053bf25b86d
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119100"
---
### <a name="jsonelement-api-changes"></a><span data-ttu-id="b3873-101">JsonElement API 更改</span><span class="sxs-lookup"><span data-stu-id="b3873-101">JsonElement API changes</span></span>

<span data-ttu-id="b3873-102">从 .NET Core 3.0 预览版 7 开始，某些 <xref:System.Text.Json.JsonElement> API 已更改，以实现更轻松的发现和更高的可用性。</span><span class="sxs-lookup"><span data-stu-id="b3873-102">Starting with .NET Core 3.0 Preview 7, some <xref:System.Text.Json.JsonElement> APIs have changed to allow for easier discovery and greater usability.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b3873-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="b3873-103">Change description</span></span>

<span data-ttu-id="b3873-104">在 .NET Core 3.0 预览版 7 中，<xref:System.Text.Json.JsonElement> API 已进行如下更改，以实现更轻松的发现和更高的可用性。</span><span class="sxs-lookup"><span data-stu-id="b3873-104">In .NET Core 3.0 Preview 7, <xref:System.Text.Json.JsonElement> APIs have changed as follows to allow for easier discovery and greater usability.</span></span>

1. <span data-ttu-id="b3873-105">所有 `WriteProperty` 方法重载已从 <xref:System.Text.Json.JsonElement> 中移除。</span><span class="sxs-lookup"><span data-stu-id="b3873-105">All `WriteProperty` method overloads were removed from <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="b3873-106">这会影响诸如以下内容的代码：</span><span class="sxs-lookup"><span data-stu-id="b3873-106">This affects code such as the following:</span></span>

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

1. <span data-ttu-id="b3873-107">`WriteValue` 已重命名为 <xref:System.Text.Json.JsonElement.WriteTo%2A>。</span><span class="sxs-lookup"><span data-stu-id="b3873-107">`WriteValue` was renamed as <xref:System.Text.Json.JsonElement.WriteTo%2A>.</span></span> <span data-ttu-id="b3873-108">这会影响诸如以下内容的代码：</span><span class="sxs-lookup"><span data-stu-id="b3873-108">This affects code such as the following:</span></span>

```csharp
using (JsonDocument doc = JsonDocument.Parse(jsonString))
{
    JsonElement root = doc.RootElement;
    root.WriteValue(writer);
}

```

1. <span data-ttu-id="b3873-109">现在，<xref:System.Text.Json.JsonElement.WriteTo%2A> 在其方法参数为 `null` 时引发 <xref:System.ArgumentNullException>。</span><span class="sxs-lookup"><span data-stu-id="b3873-109"><xref:System.Text.Json.JsonElement.WriteTo%2A> now throws an <xref:System.ArgumentNullException> when its method parameter is `null`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b3873-110">引入的版本</span><span class="sxs-lookup"><span data-stu-id="b3873-110">Version introduced</span></span>

<span data-ttu-id="b3873-111">3.0 预览版 7</span><span class="sxs-lookup"><span data-stu-id="b3873-111">3.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b3873-112">建议的操作</span><span class="sxs-lookup"><span data-stu-id="b3873-112">Recommended action</span></span>

<span data-ttu-id="b3873-113">如果你的代码受这些更改的影响，则可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b3873-113">If your code is affected by these changes, you can do the following:</span></span>

- <span data-ttu-id="b3873-114"><xref:System.Text.Json.JsonElement> 中没有用于 `WriteProperty` 重载的替换 API。</span><span class="sxs-lookup"><span data-stu-id="b3873-114">There is no replacement API for the `WriteProperty` overloads in <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="b3873-115">相反，你可以调用其中一个 <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> 重载和 <xref:System.Text.Json.JsonElement.WriteTo%2A> 方法来存档相同的结果。</span><span class="sxs-lookup"><span data-stu-id="b3873-115">Instead, you can call one of the <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> overloads along with the <xref:System.Text.Json.JsonElement.WriteTo%2A> method to achive the same result.</span></span> <span data-ttu-id="b3873-116">例如:</span><span class="sxs-lookup"><span data-stu-id="b3873-116">For example:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       writer.WritePropertyName(propertyNameString);
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="b3873-117">将 `WriteValue` 方法重命名为 <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>。</span><span class="sxs-lookup"><span data-stu-id="b3873-117">Rename the `WriteValue` method to <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>.</span></span> <span data-ttu-id="b3873-118">方法参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="b3873-118">The method parameter remains unchanged.</span></span> <span data-ttu-id="b3873-119">例如，上面的代码应更改为以下代码：</span><span class="sxs-lookup"><span data-stu-id="b3873-119">For example, the previous code should be changed to the following:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="b3873-120">处理对 <xref:System.Text.Json.JsonElement.WriteTo%2A> 方法的调用中的 <xref:System.ArgumentNullException>。</span><span class="sxs-lookup"><span data-stu-id="b3873-120">Handle the <xref:System.ArgumentNullException> in calls to the <xref:System.Text.Json.JsonElement.WriteTo%2A> method.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b3873-121">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="b3873-121">Affected APIs</span></span>

- <xref:System.Text.Json.JsonElement>
- <xref:System.Text.Json.JsonElement.WriteTo%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonElement.WriteProperty`
- `M:System.Text.Json.JsonElement.WriteValue(System.Text.Json.Utf8JsonWriter)`

-->
