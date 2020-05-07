---
ms.openlocfilehash: b3cc04d5675ea63a0a6b967e293da8a1bd79830d
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595672"
---
### <a name="uribuilder-properties-no-longer-prepend-leading-characters"></a><span data-ttu-id="99f83-101">UriBuilder 属性不再预置前导字符</span><span class="sxs-lookup"><span data-stu-id="99f83-101">UriBuilder properties no longer prepend leading characters</span></span>

<span data-ttu-id="99f83-102">如果已存在一个字符，则 <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> 不再预置前导 `#` 字符，且 <xref:System.UriBuilder.Query?displayProperty=nameWithType> 不再预置前导 `?` 字符。</span><span class="sxs-lookup"><span data-stu-id="99f83-102"><xref:System.UriBuilder.Fragment?displayProperty=nameWithType> no longer prepends a leading `#` character and <xref:System.UriBuilder.Query?displayProperty=nameWithType> no longer prepends a leading `?` character when one is already present.</span></span>

#### <a name="change-description"></a><span data-ttu-id="99f83-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="99f83-103">Change description</span></span>

<span data-ttu-id="99f83-104">在 .NET Framework 中，<xref:System.UriBuilder.Fragment?displayProperty=nameWithType> 和 <xref:System.UriBuilder.Query?displayProperty=nameWithType> 属性始终将 `#` 或 `?` 字符分别预置到所存储的值。</span><span class="sxs-lookup"><span data-stu-id="99f83-104">In .NET Framework, the <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> and <xref:System.UriBuilder.Query?displayProperty=nameWithType> properties always prepend a `#` or `?` character, respectively, to the value being stored.</span></span> <span data-ttu-id="99f83-105">如果字符串已经包含其中一个前导字符，则此行为可能会导致存储值中包含多个 `#` 或 `?` 字符。</span><span class="sxs-lookup"><span data-stu-id="99f83-105">This behavior can result in multiple `#` or `?` characters in the stored value if the string already contains one of these leading characters.</span></span> <span data-ttu-id="99f83-106">例如，<xref:System.UriBuilder.Fragment?displayProperty=nameWithType> 的值可能会变为 `##main`。</span><span class="sxs-lookup"><span data-stu-id="99f83-106">For example, the value of <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> might become `##main`.</span></span>

<span data-ttu-id="99f83-107">从 .NET Core 1.0 开始，如果在字符串的开头已经存在一个字符，则这些属性将不再将 `#` 或 `?` 字符预置到存储值之前。</span><span class="sxs-lookup"><span data-stu-id="99f83-107">Starting in .NET Core 1.0, these properties no longer prepend the `#` or `?` characters to the stored value if one is already present at the beginning of the string.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="99f83-108">引入的版本</span><span class="sxs-lookup"><span data-stu-id="99f83-108">Version introduced</span></span>

<span data-ttu-id="99f83-109">1.0</span><span class="sxs-lookup"><span data-stu-id="99f83-109">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="99f83-110">建议操作</span><span class="sxs-lookup"><span data-stu-id="99f83-110">Recommended action</span></span>

<span data-ttu-id="99f83-111">设置属性值时，不再需要显式删除这些前导字符。</span><span class="sxs-lookup"><span data-stu-id="99f83-111">You no longer need to explicitly remove any of these leading characters when setting the property values.</span></span> <span data-ttu-id="99f83-112">这在追加值时特别有用，因为不再需要在每次追加时删除前导 `#` 或 `?`。</span><span class="sxs-lookup"><span data-stu-id="99f83-112">This is especially useful when you're appending values, because you no longer have to remove the leading `#` or `?` each time you append.</span></span>

<span data-ttu-id="99f83-113">例如，下面的代码片段显示 .NET Framework 和 .NET Core 之间的行为差异。</span><span class="sxs-lookup"><span data-stu-id="99f83-113">For example, the following code snippet shows the behavior difference between .NET Framework and .NET Core.</span></span>

```csharp
var builder = new UriBuilder();
builder.Query = "one=1";
builder.Query += "&two=2";
builder.Query += "&three=3";
builder.Query += "&four=4";

Console.WriteLine(builder.Query);
```

- <span data-ttu-id="99f83-114">在 .NET Framework 中，输出为 `????one=1&two=2&three=3&four=4`。</span><span class="sxs-lookup"><span data-stu-id="99f83-114">In .NET Framework, the output is `????one=1&two=2&three=3&four=4`.</span></span>
- <span data-ttu-id="99f83-115">在 .NET Core 中，输出为 `?one=1&two=2&three=3&four=4`。</span><span class="sxs-lookup"><span data-stu-id="99f83-115">In .NET Core, the output is `?one=1&two=2&three=3&four=4`.</span></span>

#### <a name="category"></a><span data-ttu-id="99f83-116">类别</span><span class="sxs-lookup"><span data-stu-id="99f83-116">Category</span></span>

<span data-ttu-id="99f83-117">Core .NET 库</span><span class="sxs-lookup"><span data-stu-id="99f83-117">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="99f83-118">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="99f83-118">Affected APIs</span></span>

- <xref:System.UriBuilder.Fragment?displayProperty=fullName>
- <xref:System.UriBuilder.Query?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.UriBuilder.Fragment`
- `T:System.UriBuilder.Query`

-->
