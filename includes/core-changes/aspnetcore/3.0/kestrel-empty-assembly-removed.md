---
ms.openlocfilehash: 1c9c899d77dd69e185281d98bfec18ce73d80815
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394382"
---
### <a name="kestrel-empty-https-assembly-removed"></a><span data-ttu-id="43ca4-101">Kestrel：删除了空 HTTPS 程序集</span><span class="sxs-lookup"><span data-stu-id="43ca4-101">Kestrel: Empty HTTPS assembly removed</span></span>

<span data-ttu-id="43ca4-102">已删除程序集 <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="43ca4-102">The assembly <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> has been removed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="43ca4-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="43ca4-103">Version introduced</span></span>

<span data-ttu-id="43ca4-104">3.0</span><span class="sxs-lookup"><span data-stu-id="43ca4-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="43ca4-105">更改原因</span><span class="sxs-lookup"><span data-stu-id="43ca4-105">Reason for change</span></span>

<span data-ttu-id="43ca4-106">在 ASP.NET Core 2.1 中，`Microsoft.AspNetCore.Server.Kestrel.Https` 的内容已移动到 <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName> 中。</span><span class="sxs-lookup"><span data-stu-id="43ca4-106">In ASP.NET Core 2.1, the contents of `Microsoft.AspNetCore.Server.Kestrel.Https` were moved to <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName>.</span></span> <span data-ttu-id="43ca4-107">此更改是使用 `[TypeForwardedTo]` 属性以非中断方式进行的。</span><span class="sxs-lookup"><span data-stu-id="43ca4-107">This change was done in a non-breaking way using `[TypeForwardedTo]` attributes.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="43ca4-108">建议操作</span><span class="sxs-lookup"><span data-stu-id="43ca4-108">Recommended action</span></span>

- <span data-ttu-id="43ca4-109">引用 `Microsoft.AspNetCore.Server.Kestrel.Https` 2.0 的库应将所有 ASP.NET Core 依赖项更新为 2.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="43ca4-109">Libraries referencing `Microsoft.AspNetCore.Server.Kestrel.Https` 2.0 should update all ASP.NET Core dependencies to 2.1 or later.</span></span> <span data-ttu-id="43ca4-110">否则，它们可能会在加载到 ASP.NET Core 3.0 应用时中断。</span><span class="sxs-lookup"><span data-stu-id="43ca4-110">Otherwise, they may break when loaded into an ASP.NET Core 3.0 app.</span></span>
- <span data-ttu-id="43ca4-111">面向 ASP.NET Core 2.1 和更高版本的应用和库应删除对 `Microsoft.AspNetCore.Server.Kestrel.Https` NuGet 包的任何直接引用。</span><span class="sxs-lookup"><span data-stu-id="43ca4-111">Apps and libraries targeting ASP.NET Core 2.1 and later should remove any direct references to the `Microsoft.AspNetCore.Server.Kestrel.Https` NuGet package.</span></span>

#### <a name="category"></a><span data-ttu-id="43ca4-112">类别</span><span class="sxs-lookup"><span data-stu-id="43ca4-112">Category</span></span>

<span data-ttu-id="43ca4-113">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="43ca4-113">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="43ca4-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="43ca4-114">Affected APIs</span></span>

<span data-ttu-id="43ca4-115">None</span><span class="sxs-lookup"><span data-stu-id="43ca4-115">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
