---
ms.openlocfilehash: be1fad236dd3eed047b010e93285aec8bc607b61
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394331"
---
### <a name="hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced"></a><span data-ttu-id="f24ac-101">托管：IHostingEnvironment 和 IApplicationLifetime 类型标记为过时并被替换</span><span class="sxs-lookup"><span data-stu-id="f24ac-101">Hosting: IHostingEnvironment and IApplicationLifetime types marked obsolete and replaced</span></span>

<span data-ttu-id="f24ac-102">引入了新类型以替换现有的 `IHostingEnvironment` 和 `IApplicationLifetime` 类型。</span><span class="sxs-lookup"><span data-stu-id="f24ac-102">New types have been introduced to replace existing `IHostingEnvironment` and `IApplicationLifetime` types.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f24ac-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="f24ac-103">Version introduced</span></span>

<span data-ttu-id="f24ac-104">3.0</span><span class="sxs-lookup"><span data-stu-id="f24ac-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="f24ac-105">旧行为</span><span class="sxs-lookup"><span data-stu-id="f24ac-105">Old behavior</span></span>

<span data-ttu-id="f24ac-106">`Microsoft.Extensions.Hosting` 和 `Microsoft.AspNetCore.Hosting` 有两个不同的 `IHostingEnvironment` 和 `IApplicationLifetime` 类型。</span><span class="sxs-lookup"><span data-stu-id="f24ac-106">There were two different `IHostingEnvironment` and `IApplicationLifetime` types from `Microsoft.Extensions.Hosting` and `Microsoft.AspNetCore.Hosting`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="f24ac-107">新行为</span><span class="sxs-lookup"><span data-stu-id="f24ac-107">New behavior</span></span>

<span data-ttu-id="f24ac-108">旧类型已标记为过时，并已替换为新类型。</span><span class="sxs-lookup"><span data-stu-id="f24ac-108">The old types have been marked as obsolete and replaced with new types.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f24ac-109">更改原因</span><span class="sxs-lookup"><span data-stu-id="f24ac-109">Reason for change</span></span>

<span data-ttu-id="f24ac-110">在 ASP.NET Core 2.1 中引入 `Microsoft.Extensions.Hosting` 时，从 `Microsoft.AspNetCore.Hosting` 复制了某些类型（如 `IHostingEnvironment` 和 `IApplicationLifetime`）。</span><span class="sxs-lookup"><span data-stu-id="f24ac-110">When `Microsoft.Extensions.Hosting` was introduced in ASP.NET Core 2.1, some types like `IHostingEnvironment` and `IApplicationLifetime` were copied from `Microsoft.AspNetCore.Hosting`.</span></span> <span data-ttu-id="f24ac-111">某些 ASP.NET Core 3.0 更改会导致应用包括 `Microsoft.Extensions.Hosting` 和 `Microsoft.AspNetCore.Hosting` 命名空间。</span><span class="sxs-lookup"><span data-stu-id="f24ac-111">Some ASP.NET Core 3.0 changes cause apps to include both the `Microsoft.Extensions.Hosting` and `Microsoft.AspNetCore.Hosting` namespaces.</span></span> <span data-ttu-id="f24ac-112">如果同时引用了两个命名空间，则使用这些重复类型会导致“引用不明确”编译器错误。</span><span class="sxs-lookup"><span data-stu-id="f24ac-112">Any use of those duplicate types causes an "ambiguous reference" compiler error when both namespaces are referenced.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f24ac-113">建议的操作</span><span class="sxs-lookup"><span data-stu-id="f24ac-113">Recommended action</span></span>

<span data-ttu-id="f24ac-114">将旧类型的所有使用替换为新引入的类型，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f24ac-114">Replaced any usages of the old types with the newly introduced types as below:</span></span>

<span data-ttu-id="f24ac-115">**过时类型（警告）：**</span><span class="sxs-lookup"><span data-stu-id="f24ac-115">**Obsolete types (warning):**</span></span>

- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>

<span data-ttu-id="f24ac-116">**新类型：**</span><span class="sxs-lookup"><span data-stu-id="f24ac-116">**New types:**</span></span>

- <xref:Microsoft.Extensions.Hosting.IHostEnvironment?displayProperty=nameWithType>
- `Microsoft.AspNetCore.Hosting.IWebHostEnvironment : IHostEnvironment`
- <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.Environments?displayProperty=nameWithType>

<span data-ttu-id="f24ac-117">新的 `IHostEnvironment` `IsDevelopment` 和 `IsProduction` 扩展方法在 `Microsoft.Extensions.Hosting` 命名空间中。</span><span class="sxs-lookup"><span data-stu-id="f24ac-117">The new `IHostEnvironment` `IsDevelopment` and `IsProduction` extension methods are in the `Microsoft.Extensions.Hosting` namespace.</span></span> <span data-ttu-id="f24ac-118">可能需要将该命名空间添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="f24ac-118">That namespace may need to be added to your project.</span></span>

#### <a name="category"></a><span data-ttu-id="f24ac-119">类别</span><span class="sxs-lookup"><span data-stu-id="f24ac-119">Category</span></span>

<span data-ttu-id="f24ac-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f24ac-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f24ac-121">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="f24ac-121">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.EnvironmentName`
- `T:Microsoft.AspNetCore.Hosting.IApplicationLifetime`
- `T:Microsoft.AspNetCore.Hosting.IHostingEnvironment`
- `T:Microsoft.Extensions.Hosting.EnvironmentName`
- `T:Microsoft.Extensions.Hosting.IApplicationLifetime`
- `T:Microsoft.Extensions.Hosting.IHostingEnvironment`

-->
