---
ms.openlocfilehash: 75945e7ff26c1c6db891d12cef4c16ed210da6af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394034"
---
### <a name="mvc-web-api-compatibility-shim-removed"></a><span data-ttu-id="efbc7-101">MVC：已删除 Web API 兼容性填充码</span><span class="sxs-lookup"><span data-stu-id="efbc7-101">MVC: Web API compatibility shim removed</span></span>

<span data-ttu-id="efbc7-102">从 ASP.NET Core 3.0 开始，不再提供 `Microsoft.AspNetCore.Mvc.WebApiCompatShim` 包。</span><span class="sxs-lookup"><span data-stu-id="efbc7-102">Starting with ASP.NET Core 3.0, the `Microsoft.AspNetCore.Mvc.WebApiCompatShim` package is no longer available.</span></span>

#### <a name="change-description"></a><span data-ttu-id="efbc7-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="efbc7-103">Change description</span></span>

<span data-ttu-id="efbc7-104">`Microsoft.AspNetCore.Mvc.WebApiCompatShim` (WebApiCompatShim) 包在 ASP.NET Core 中提供了与 ASP.NET 4.x Web API 2 的部分兼容性，以简化将现有 Web API 实现迁移到 ASP.NET Core 的工作。</span><span class="sxs-lookup"><span data-stu-id="efbc7-104">The `Microsoft.AspNetCore.Mvc.WebApiCompatShim` (WebApiCompatShim) package provides partial compatibility in ASP.NET Core with ASP.NET 4.x Web API 2 to simplify migrating existing Web API implementations to ASP.NET Core.</span></span> <span data-ttu-id="efbc7-105">但是，使用 WebApiCompatShim 的应用不会从最近 ASP.NET Core 版本中提供的与 API 相关的功能中获益。</span><span class="sxs-lookup"><span data-stu-id="efbc7-105">However, apps using the WebApiCompatShim don't benefit from the API-related features shipping in recent ASP.NET Core releases.</span></span> <span data-ttu-id="efbc7-106">此类功能包括改进的开放 API 规范生成、标准化错误处理和客户端代码生成。</span><span class="sxs-lookup"><span data-stu-id="efbc7-106">Such features include improved Open API specification generation, standardized error handling, and client code generation.</span></span> <span data-ttu-id="efbc7-107">为了更好地专注于 3.0 中的 API 工作，已删除 WebApiCompatShim。</span><span class="sxs-lookup"><span data-stu-id="efbc7-107">To better focus the API efforts in 3.0, WebApiCompatShim was removed.</span></span> <span data-ttu-id="efbc7-108">使用 WebApiCompatShim 的现有应用应迁移到较新的 `[ApiController]` 模型。</span><span class="sxs-lookup"><span data-stu-id="efbc7-108">Existing apps using the WebApiCompatShim should migrate to the newer `[ApiController]` model.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="efbc7-109">引入的版本</span><span class="sxs-lookup"><span data-stu-id="efbc7-109">Version introduced</span></span>

<span data-ttu-id="efbc7-110">3.0</span><span class="sxs-lookup"><span data-stu-id="efbc7-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="efbc7-111">更改原因</span><span class="sxs-lookup"><span data-stu-id="efbc7-111">Reason for change</span></span>

<span data-ttu-id="efbc7-112">Web API 兼容性填充码是一种迁移工具。</span><span class="sxs-lookup"><span data-stu-id="efbc7-112">The Web API compatibility shim was a migration tool.</span></span> <span data-ttu-id="efbc7-113">它限制用户对 ASP.NET Core 中添加的新功能的访问。</span><span class="sxs-lookup"><span data-stu-id="efbc7-113">It restricts user access to new functionality added in ASP.NET Core.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="efbc7-114">建议操作</span><span class="sxs-lookup"><span data-stu-id="efbc7-114">Recommended action</span></span>

<span data-ttu-id="efbc7-115">删除此填充码的使用，直接迁移到 ASP.NET Core 本身中的类似功能。</span><span class="sxs-lookup"><span data-stu-id="efbc7-115">Remove usage of this shim and migrate directly to the similar functionality in ASP.NET Core itself.</span></span>

#### <a name="category"></a><span data-ttu-id="efbc7-116">类别</span><span class="sxs-lookup"><span data-stu-id="efbc7-116">Category</span></span>

<span data-ttu-id="efbc7-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="efbc7-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="efbc7-118">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="efbc7-118">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.WebApiCompatShim?displayProperty=fullName>

<!--

#### Affected APIs

N:Microsoft.AspNetCore.Mvc.WebApiCompatShim

-->
