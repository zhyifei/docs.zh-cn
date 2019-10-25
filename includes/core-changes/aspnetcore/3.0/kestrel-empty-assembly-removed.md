---
ms.openlocfilehash: 1c9c899d77dd69e185281d98bfec18ce73d80815
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394382"
---
### <a name="kestrel-empty-https-assembly-removed"></a><span data-ttu-id="d38c9-101">Kestrel：删除了空 HTTPS 程序集</span><span class="sxs-lookup"><span data-stu-id="d38c9-101">Kestrel: Empty HTTPS assembly removed</span></span>

<span data-ttu-id="d38c9-102">已删除程序集 <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="d38c9-102">The assembly <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> has been removed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d38c9-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="d38c9-103">Version introduced</span></span>

<span data-ttu-id="d38c9-104">3.0</span><span class="sxs-lookup"><span data-stu-id="d38c9-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d38c9-105">更改原因</span><span class="sxs-lookup"><span data-stu-id="d38c9-105">Reason for change</span></span>

<span data-ttu-id="d38c9-106">在 ASP.NET Core 2.1 中，`Microsoft.AspNetCore.Server.Kestrel.Https` 的内容已移动到 <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName> 中。</span><span class="sxs-lookup"><span data-stu-id="d38c9-106">In ASP.NET Core 2.1, the contents of `Microsoft.AspNetCore.Server.Kestrel.Https` were moved to <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName>.</span></span> <span data-ttu-id="d38c9-107">此更改是使用 `[TypeForwardedTo]` 属性以非中断方式进行的。</span><span class="sxs-lookup"><span data-stu-id="d38c9-107">This change was done in a non-breaking way using `[TypeForwardedTo]` attributes.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d38c9-108">建议的操作</span><span class="sxs-lookup"><span data-stu-id="d38c9-108">Recommended action</span></span>

- <span data-ttu-id="d38c9-109">引用 `Microsoft.AspNetCore.Server.Kestrel.Https` 2.0 的库应将所有 ASP.NET Core 依赖项更新为 2.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d38c9-109">Libraries referencing `Microsoft.AspNetCore.Server.Kestrel.Https` 2.0 should update all ASP.NET Core dependencies to 2.1 or later.</span></span> <span data-ttu-id="d38c9-110">否则，它们可能会在加载到 ASP.NET Core 3.0 应用时中断。</span><span class="sxs-lookup"><span data-stu-id="d38c9-110">Otherwise, they may break when loaded into an ASP.NET Core 3.0 app.</span></span>
- <span data-ttu-id="d38c9-111">面向 ASP.NET Core 2.1 和更高版本的应用和库应删除对 `Microsoft.AspNetCore.Server.Kestrel.Https` NuGet 包的任何直接引用。</span><span class="sxs-lookup"><span data-stu-id="d38c9-111">Apps and libraries targeting ASP.NET Core 2.1 and later should remove any direct references to the `Microsoft.AspNetCore.Server.Kestrel.Https` NuGet package.</span></span>

#### <a name="category"></a><span data-ttu-id="d38c9-112">类别</span><span class="sxs-lookup"><span data-stu-id="d38c9-112">Category</span></span>

<span data-ttu-id="d38c9-113">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d38c9-113">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d38c9-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="d38c9-114">Affected APIs</span></span>

<span data-ttu-id="d38c9-115">无</span><span class="sxs-lookup"><span data-stu-id="d38c9-115">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
