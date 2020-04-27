---
ms.openlocfilehash: cc3251e3b31143bd95793b407e50cf76e0e30142
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021626"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a><span data-ttu-id="c10a3-101">Json 序列化程序异常类型从 `JsonException` 更改为 `NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="c10a3-101">Json serializer exception type changed from `JsonException` to `NotSupportedException`</span></span>

<span data-ttu-id="c10a3-102">在 .NET Core 3.0 预览版 6 到 8 中，如果序列化程序遇到不受支持的派生集合类型，则会引发 <xref:System.Text.Json.JsonException>。</span><span class="sxs-lookup"><span data-stu-id="c10a3-102">In .NET Core 3.0 Preview 6 through 8, the serializer would throw a <xref:System.Text.Json.JsonException> when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="c10a3-103">从 .NET Core 3.0 预览版 9 开始，序列化程序转而引发 <xref:System.NotSupportedException>。</span><span class="sxs-lookup"><span data-stu-id="c10a3-103">Starting in .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> instead.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c10a3-104">更改描述</span><span class="sxs-lookup"><span data-stu-id="c10a3-104">Change description</span></span>

<span data-ttu-id="c10a3-105">在 .NET Core 3.0 预览版 6 到预览版 8 中，如果序列化程序遇到不受支持的派生集合类型，则会引发 <xref:System.Text.Json.JsonException>。</span><span class="sxs-lookup"><span data-stu-id="c10a3-105">In .NET Core 3.0 Preview 6 through Preview 8, the serializer would throw a <xref:System.Text.Json.JsonException>  when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="c10a3-106">不受支持的派生集合类型  是任何不能分配给以下类型之一的集合类型：</span><span class="sxs-lookup"><span data-stu-id="c10a3-106">An *unsupported derived collection type* is any collection type that isn't assignable to one of the following types:</span></span>

- <xref:System.Collections.IList>
- <xref:System.Collections.Generic.ICollection%601>
- <xref:System.Collections.Generic.Stack%601>
- <xref:System.Collections.Generic.Queue%601>
- <xref:System.Collections.IDictionary>
- [<span data-ttu-id="c10a3-107">IDictionary\<String,T></span><span class="sxs-lookup"><span data-stu-id="c10a3-107">IDictionary\<String,T></span></span>](xref:System.Collections.Generic.IDictionary%602)

<span data-ttu-id="c10a3-108">从 .NET Core 3.0 预览版 9 开始，序列化程序在遇到不受支持的集合类型时会引发 <xref:System.NotSupportedException>。</span><span class="sxs-lookup"><span data-stu-id="c10a3-108">Starting with .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> When encountering an unsupported collection type.</span></span> <span data-ttu-id="c10a3-109">新的异常类型更好地反映了反序列化操作失败的原因。</span><span class="sxs-lookup"><span data-stu-id="c10a3-109">The new exception type better reflects why the deserialization operation is failing.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c10a3-110">引入的版本</span><span class="sxs-lookup"><span data-stu-id="c10a3-110">Version introduced</span></span>

<span data-ttu-id="c10a3-111">3.0 预览版 9</span><span class="sxs-lookup"><span data-stu-id="c10a3-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c10a3-112">建议操作</span><span class="sxs-lookup"><span data-stu-id="c10a3-112">Recommended action</span></span>

<span data-ttu-id="c10a3-113">如果要在反序列化时捕获 <xref:System.Text.Json.JsonException>，则可能要考虑同时捕获 <xref:System.NotSupportedException>。</span><span class="sxs-lookup"><span data-stu-id="c10a3-113">If you're catching <xref:System.Text.Json.JsonException> when deserializing, you might want to consider also catching <xref:System.NotSupportedException>.</span></span>

#### <a name="category"></a><span data-ttu-id="c10a3-114">类别</span><span class="sxs-lookup"><span data-stu-id="c10a3-114">Category</span></span>

<span data-ttu-id="c10a3-115">Core .NET 库</span><span class="sxs-lookup"><span data-stu-id="c10a3-115">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c10a3-116">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="c10a3-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
