---
ms.openlocfilehash: 8479168b64153d3c729f8814a2649df8d46f2135
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394432"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a>Razor：运行时编译已移动到包

支持 Razor 视图的运行时编译，已将 Razor Pages 移动到单独的包中。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="old-behavior"></a>旧行为

无需额外的包，即可使用运行时编译。

#### <a name="new-behavior"></a>新行为

该功能已移动到 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` 包。

以下 API 以前在 `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` 中提供，用于支持运行时编译。 现在可通过 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions` 获取 API。

- `RazorViewEngineOptions.FileProviders` -> `MvcRazorRuntimeCompilationOptions.FileProviders`
- `RazorViewEngineOptions.AdditionalCompilationReferences` -> `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`

此外，已删除 `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange`。 默认情况下，通过引用 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` 包来启用对文件更改的重新编译。

#### <a name="reason-for-change"></a>更改原因

此更改是删除 Roslyn 上的 ASP.NET Core 共享框架依赖项所必需的。

#### <a name="recommended-action"></a>建议的操作

需要对 Razor 文件进行运行时编译或重新编译的应用应执行以下步骤：

1. 添加对 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` 包的引用。
1. 更新项目的 `Startup.ConfigureServices` 方法以包含对 `AddMvcRazorRuntimeCompilation` 的调用。 例如，在 `Startup.ConfigureServices` 中：

    ```csharp
    services.AddMvc()
        .AddMvcRazorRuntimeCompilation();
    ```

#### <a name="category"></a>类别

ASP.NET Core

#### <a name="affected-apis"></a>受影响的 API

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
