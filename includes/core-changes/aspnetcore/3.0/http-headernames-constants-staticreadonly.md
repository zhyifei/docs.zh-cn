---
ms.openlocfilehash: 31e7f84a787d255a474f4c2b1fa3068903dbed52
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901956"
---
### <a name="http-headernames-constants-changed-to-static-readonly"></a><span data-ttu-id="13251-101">HTTP：HeaderNames 常量已更改为静态只读</span><span class="sxs-lookup"><span data-stu-id="13251-101">HTTP: HeaderNames constants changed to static readonly</span></span>

<span data-ttu-id="13251-102">从 ASP.NET Core 3.0 预览版 5 开始，<xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> 中的字段已从 `const` 更改为 `static readonly`。</span><span class="sxs-lookup"><span data-stu-id="13251-102">Starting in ASP.NET Core 3.0 Preview 5, the fields in <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> changed from `const` to `static readonly`.</span></span>

<span data-ttu-id="13251-103">有关讨论，请参阅 [dotnet/aspnetcore#9514](https://github.com/dotnet/aspnetcore/issues/9514)。</span><span class="sxs-lookup"><span data-stu-id="13251-103">For discussion, see [dotnet/aspnetcore#9514](https://github.com/dotnet/aspnetcore/issues/9514).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="13251-104">引入的版本</span><span class="sxs-lookup"><span data-stu-id="13251-104">Version introduced</span></span>

<span data-ttu-id="13251-105">3.0</span><span class="sxs-lookup"><span data-stu-id="13251-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="13251-106">旧行为</span><span class="sxs-lookup"><span data-stu-id="13251-106">Old behavior</span></span>

<span data-ttu-id="13251-107">这些字段以前是 `const`。</span><span class="sxs-lookup"><span data-stu-id="13251-107">These fields used to be `const`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="13251-108">新行为</span><span class="sxs-lookup"><span data-stu-id="13251-108">New behavior</span></span>

<span data-ttu-id="13251-109">这些字段现在是 `static readonly`。</span><span class="sxs-lookup"><span data-stu-id="13251-109">These fields are now `static readonly`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="13251-110">更改原因</span><span class="sxs-lookup"><span data-stu-id="13251-110">Reason for change</span></span>

<span data-ttu-id="13251-111">更改：</span><span class="sxs-lookup"><span data-stu-id="13251-111">The change:</span></span>

* <span data-ttu-id="13251-112">防止将值嵌入到程序集边界内，允许根据需要更正值。</span><span class="sxs-lookup"><span data-stu-id="13251-112">Prevents the values from being embedded across assembly boundaries, allowing for value corrections as needed.</span></span>
* <span data-ttu-id="13251-113">实现更快的引用同等性检查。</span><span class="sxs-lookup"><span data-stu-id="13251-113">Enables faster reference equality checks.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="13251-114">建议操作</span><span class="sxs-lookup"><span data-stu-id="13251-114">Recommended action</span></span>

<span data-ttu-id="13251-115">针对 3.0 重新编译。</span><span class="sxs-lookup"><span data-stu-id="13251-115">Recompile against 3.0.</span></span> <span data-ttu-id="13251-116">通过以下方式使用这些字段的源代码将无法再执行此项操作：</span><span class="sxs-lookup"><span data-stu-id="13251-116">Source code using these fields in the following ways can no longer do so:</span></span>

* <span data-ttu-id="13251-117">作为特性参数</span><span class="sxs-lookup"><span data-stu-id="13251-117">As an attribute argument</span></span>
* <span data-ttu-id="13251-118">作为 `switch` 语句中的 `case`</span><span class="sxs-lookup"><span data-stu-id="13251-118">As a `case` in a `switch` statement</span></span>
* <span data-ttu-id="13251-119">定义其他 `const` 时</span><span class="sxs-lookup"><span data-stu-id="13251-119">When defining another `const`</span></span>

<span data-ttu-id="13251-120">若要解决中断性变更，请切换到使用自定义标头名称常量或字符串文本。</span><span class="sxs-lookup"><span data-stu-id="13251-120">To work around the breaking change, switch to using self-defined header name constants or string literals.</span></span>

#### <a name="category"></a><span data-ttu-id="13251-121">类别</span><span class="sxs-lookup"><span data-stu-id="13251-121">Category</span></span>

<span data-ttu-id="13251-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="13251-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="13251-123">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="13251-123">Affected APIs</span></span>

<xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.Net.Http.Headers.HeaderNames`

-->
