---
ms.openlocfilehash: cd13e7560ee98e0c862c5e2293521c6aaa273455
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344268"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a><span data-ttu-id="1dd13-101">Razor：运行时编译已移动到包</span><span class="sxs-lookup"><span data-stu-id="1dd13-101">Razor: Runtime compilation moved to a package</span></span>

<span data-ttu-id="1dd13-102">支持 Razor 视图的运行时编译，已将 Razor Pages 移动到单独的包中。</span><span class="sxs-lookup"><span data-stu-id="1dd13-102">Support for runtime compilation of Razor views and Razor Pages has moved to a separate package.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1dd13-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="1dd13-103">Version introduced</span></span>

<span data-ttu-id="1dd13-104">3.0</span><span class="sxs-lookup"><span data-stu-id="1dd13-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="1dd13-105">旧行为</span><span class="sxs-lookup"><span data-stu-id="1dd13-105">Old behavior</span></span>

<span data-ttu-id="1dd13-106">无需额外的包，即可使用运行时编译。</span><span class="sxs-lookup"><span data-stu-id="1dd13-106">Runtime compilation is available without needing additional packages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="1dd13-107">新行为</span><span class="sxs-lookup"><span data-stu-id="1dd13-107">New behavior</span></span>

<span data-ttu-id="1dd13-108">此功能已移至 [Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/) 包中。</span><span class="sxs-lookup"><span data-stu-id="1dd13-108">The functionality has been moved to the [Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/) package.</span></span>

<span data-ttu-id="1dd13-109">以下 API 以前在 `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` 中提供，用于支持运行时编译。</span><span class="sxs-lookup"><span data-stu-id="1dd13-109">The following APIs were previously available in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` to support runtime compilation.</span></span> <span data-ttu-id="1dd13-110">现在可通过 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions` 获取 API。</span><span class="sxs-lookup"><span data-stu-id="1dd13-110">The APIs are now available via `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span></span>

- <span data-ttu-id="1dd13-111">`RazorViewEngineOptions.FileProviders` 现在为 `MvcRazorRuntimeCompilationOptions.FileProviders`</span><span class="sxs-lookup"><span data-stu-id="1dd13-111">`RazorViewEngineOptions.FileProviders` is now `MvcRazorRuntimeCompilationOptions.FileProviders`</span></span>
- <span data-ttu-id="1dd13-112">`RazorViewEngineOptions.AdditionalCompilationReferences` 现在为 `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`</span><span class="sxs-lookup"><span data-stu-id="1dd13-112">`RazorViewEngineOptions.AdditionalCompilationReferences` is now `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`</span></span>

<span data-ttu-id="1dd13-113">此外，已删除 `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange`。</span><span class="sxs-lookup"><span data-stu-id="1dd13-113">In addition, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` has been removed.</span></span> <span data-ttu-id="1dd13-114">默认情况下，通过引用 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` 包来启用对文件更改的重新编译。</span><span class="sxs-lookup"><span data-stu-id="1dd13-114">Recompilation on file changes is enabled by default by referencing the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1dd13-115">更改原因</span><span class="sxs-lookup"><span data-stu-id="1dd13-115">Reason for change</span></span>

<span data-ttu-id="1dd13-116">此更改是删除 Roslyn 上的 ASP.NET Core 共享框架依赖项所必需的。</span><span class="sxs-lookup"><span data-stu-id="1dd13-116">This change was necessary to remove the ASP.NET Core shared framework dependency on Roslyn.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1dd13-117">建议操作</span><span class="sxs-lookup"><span data-stu-id="1dd13-117">Recommended action</span></span>

<span data-ttu-id="1dd13-118">需要对 Razor 文件进行运行时编译或重新编译的应用应执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1dd13-118">Apps that require runtime compilation or recompilation of Razor files should take the following steps:</span></span>

1. <span data-ttu-id="1dd13-119">添加对 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` 包的引用。</span><span class="sxs-lookup"><span data-stu-id="1dd13-119">Add a reference to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>
1. <span data-ttu-id="1dd13-120">更新项目的 `Startup.ConfigureServices` 方法以包含对 `AddRazorRuntimeCompilation` 的调用。</span><span class="sxs-lookup"><span data-stu-id="1dd13-120">Update the project's `Startup.ConfigureServices` method to include a call to `AddRazorRuntimeCompilation`.</span></span> <span data-ttu-id="1dd13-121">例如：</span><span class="sxs-lookup"><span data-stu-id="1dd13-121">For example:</span></span>

    ```csharp
    services.AddMvc()
        .AddRazorRuntimeCompilation();
    ```

#### <a name="category"></a><span data-ttu-id="1dd13-122">类别</span><span class="sxs-lookup"><span data-stu-id="1dd13-122">Category</span></span>

<span data-ttu-id="1dd13-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1dd13-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1dd13-124">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="1dd13-124">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
