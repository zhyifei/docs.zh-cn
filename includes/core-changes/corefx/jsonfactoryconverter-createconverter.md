---
ms.openlocfilehash: 9052f509ec6df4e4b911e2f33b5c8197adb9a2c3
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198355"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a><span data-ttu-id="39961-101">JsonFactoryConverter.CreateConverter 签名已更改</span><span class="sxs-lookup"><span data-stu-id="39961-101">JsonFactoryConverter.CreateConverter signature changed</span></span>

<span data-ttu-id="39961-102">为了促进 <xref:System.Text.Json.Serialization.JsonConverterFactory> 类的构成，已使 <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> 方法成为公共方法，并给出了类型为 <xref:System.Text.Json.JsonSerializerOptions> 的第二个参数。</span><span class="sxs-lookup"><span data-stu-id="39961-102">To facilitate the composition of <xref:System.Text.Json.Serialization.JsonConverterFactory> classes, the <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> method has been made public and given a second argument of type <xref:System.Text.Json.JsonSerializerOptions>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="39961-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="39961-103">Change description</span></span>

<span data-ttu-id="39961-104">在版本 3.0 预览版 8 之前，.Net Core 中的 `CreateConverter` 方法的签名如下：</span><span class="sxs-lookup"><span data-stu-id="39961-104">The signature of the `CreateConverter` method in .NET Core prior to version 3.0 Preview 8 was:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

<span data-ttu-id="39961-105">在 .NET Core 3.0 预览版 8 及更高版本中，则为：</span><span class="sxs-lookup"><span data-stu-id="39961-105">In .NET Core 3.0 Preview 8 and later versions, it is:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

<span data-ttu-id="39961-106">在进行此更改之前，很难编写密封的工厂转换器，因为无法轻松地从中获取 <xref:System.Text.Json.Serialization.JsonConverter%601>。</span><span class="sxs-lookup"><span data-stu-id="39961-106">Before this change, it was difficult to compose sealed factory converters, since there was no easy way to get the <xref:System.Text.Json.Serialization.JsonConverter%601> from it.</span></span> <span data-ttu-id="39961-107">让工厂方法成为公共方法，同时传递当前 <xref:System.Text.Json.JsonSerializerOptions>，允许实现更灵活的构造。</span><span class="sxs-lookup"><span data-stu-id="39961-107">Making the factory method public and also passing the current <xref:System.Text.Json.JsonSerializerOptions> allow for much more flexible composition.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="39961-108">引入的版本</span><span class="sxs-lookup"><span data-stu-id="39961-108">Version introduced</span></span>

<span data-ttu-id="39961-109">3.0 预览版 8</span><span class="sxs-lookup"><span data-stu-id="39961-109">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="39961-110">建议的操作</span><span class="sxs-lookup"><span data-stu-id="39961-110">Recommended action</span></span>

<span data-ttu-id="39961-111">需要更新并重新编译派生类。</span><span class="sxs-lookup"><span data-stu-id="39961-111">Derived classes need to be updated and recompiled.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="39961-112">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="39961-112">Affected APIs</span></span>

<span data-ttu-id="39961-113"><xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="39961-113"><xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>.</span></span>

<!-- For tool use only

### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
