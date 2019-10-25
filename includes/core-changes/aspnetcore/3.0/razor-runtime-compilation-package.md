---
ms.openlocfilehash: 8479168b64153d3c729f8814a2649df8d46f2135
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394432"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a><span data-ttu-id="32f66-101">Razor：运行时编译已移动到包</span><span class="sxs-lookup"><span data-stu-id="32f66-101">Razor: Runtime compilation moved to a package</span></span>

<span data-ttu-id="32f66-102">支持 Razor 视图的运行时编译，已将 Razor Pages 移动到单独的包中。</span><span class="sxs-lookup"><span data-stu-id="32f66-102">Support for runtime compilation of Razor views and Razor Pages has moved to a separate package.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="32f66-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="32f66-103">Version introduced</span></span>

<span data-ttu-id="32f66-104">3.0</span><span class="sxs-lookup"><span data-stu-id="32f66-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="32f66-105">旧行为</span><span class="sxs-lookup"><span data-stu-id="32f66-105">Old behavior</span></span>

<span data-ttu-id="32f66-106">无需额外的包，即可使用运行时编译。</span><span class="sxs-lookup"><span data-stu-id="32f66-106">Runtime compilation is available without needing additional packages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="32f66-107">新行为</span><span class="sxs-lookup"><span data-stu-id="32f66-107">New behavior</span></span>

<span data-ttu-id="32f66-108">该功能已移动到 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` 包。</span><span class="sxs-lookup"><span data-stu-id="32f66-108">The functionality has been moved to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

<span data-ttu-id="32f66-109">以下 API 以前在 `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` 中提供，用于支持运行时编译。</span><span class="sxs-lookup"><span data-stu-id="32f66-109">The following APIs were previously available in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` to support runtime compilation.</span></span> <span data-ttu-id="32f66-110">现在可通过 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions` 获取 API。</span><span class="sxs-lookup"><span data-stu-id="32f66-110">The APIs are now available via `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span></span>

- `RazorViewEngineOptions.FileProviders` -> `MvcRazorRuntimeCompilationOptions.FileProviders`
- `RazorViewEngineOptions.AdditionalCompilationReferences` -> `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`

<span data-ttu-id="32f66-111">此外，已删除 `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange`。</span><span class="sxs-lookup"><span data-stu-id="32f66-111">In addition, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` has been removed.</span></span> <span data-ttu-id="32f66-112">默认情况下，通过引用 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` 包来启用对文件更改的重新编译。</span><span class="sxs-lookup"><span data-stu-id="32f66-112">Recompilation on file changes is enabled by default by referencing the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="32f66-113">更改原因</span><span class="sxs-lookup"><span data-stu-id="32f66-113">Reason for change</span></span>

<span data-ttu-id="32f66-114">此更改是删除 Roslyn 上的 ASP.NET Core 共享框架依赖项所必需的。</span><span class="sxs-lookup"><span data-stu-id="32f66-114">This change was necessary to remove the ASP.NET Core shared framework dependency on Roslyn.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="32f66-115">建议的操作</span><span class="sxs-lookup"><span data-stu-id="32f66-115">Recommended action</span></span>

<span data-ttu-id="32f66-116">需要对 Razor 文件进行运行时编译或重新编译的应用应执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="32f66-116">Apps that require runtime compilation or recompilation of Razor files should take the following steps:</span></span>

1. <span data-ttu-id="32f66-117">添加对 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` 包的引用。</span><span class="sxs-lookup"><span data-stu-id="32f66-117">Add a reference to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>
1. <span data-ttu-id="32f66-118">更新项目的 `Startup.ConfigureServices` 方法以包含对 `AddMvcRazorRuntimeCompilation` 的调用。</span><span class="sxs-lookup"><span data-stu-id="32f66-118">Update the project's `Startup.ConfigureServices` method to include a call to `AddMvcRazorRuntimeCompilation`.</span></span> <span data-ttu-id="32f66-119">例如，在 `Startup.ConfigureServices` 中：</span><span class="sxs-lookup"><span data-stu-id="32f66-119">For example, in `Startup.ConfigureServices`:</span></span>

    ```csharp
    services.AddMvc()
        .AddMvcRazorRuntimeCompilation();
    ```

#### <a name="category"></a><span data-ttu-id="32f66-120">类别</span><span class="sxs-lookup"><span data-stu-id="32f66-120">Category</span></span>

<span data-ttu-id="32f66-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="32f66-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="32f66-122">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="32f66-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
