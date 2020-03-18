---
ms.openlocfilehash: f6fd75c5b49156f44d31c650ea452eb549f13b0e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901916"
---
### <a name="mvc-jsonresult-moved-to-microsoftaspnetcoremvccore"></a><span data-ttu-id="6da65-101">MVC：JsonResult 已移至 Microsoft.AspNetCore.Mvc.Core</span><span class="sxs-lookup"><span data-stu-id="6da65-101">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>

<span data-ttu-id="6da65-102">`JsonResult` 已移至 `Microsoft.AspNetCore.Mvc.Core` 程序集。</span><span class="sxs-lookup"><span data-stu-id="6da65-102">`JsonResult` has moved to the `Microsoft.AspNetCore.Mvc.Core` assembly.</span></span> <span data-ttu-id="6da65-103">此类型用于在 [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json) 中进行定义。</span><span class="sxs-lookup"><span data-stu-id="6da65-103">This type used to be defined in [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json).</span></span> <span data-ttu-id="6da65-104">已将程序集级别 [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) 属性添加到 `Microsoft.AspNetCore.Mvc.Formatters.Json`，以便为大多数用户解决此问题。</span><span class="sxs-lookup"><span data-stu-id="6da65-104">An assembly-level [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) attribute was added to `Microsoft.AspNetCore.Mvc.Formatters.Json` to address this issue for the majority of users.</span></span> <span data-ttu-id="6da65-105">使用第三方库的应用可能会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="6da65-105">Apps that use third-party libraries may encounter issues.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6da65-106">引入的版本</span><span class="sxs-lookup"><span data-stu-id="6da65-106">Version introduced</span></span>

<span data-ttu-id="6da65-107">3.0 预览版 6</span><span class="sxs-lookup"><span data-stu-id="6da65-107">3.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="6da65-108">旧行为</span><span class="sxs-lookup"><span data-stu-id="6da65-108">Old behavior</span></span>

<span data-ttu-id="6da65-109">已成功生成使用基于 2.2 的库的应用。</span><span class="sxs-lookup"><span data-stu-id="6da65-109">An app using a 2.2-based library builds successfully.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="6da65-110">新行为</span><span class="sxs-lookup"><span data-stu-id="6da65-110">New behavior</span></span>

<span data-ttu-id="6da65-111">使用基于 2.2 的库的应用无法进行编译。</span><span class="sxs-lookup"><span data-stu-id="6da65-111">An app using a 2.2-based library fails compilation.</span></span> <span data-ttu-id="6da65-112">提供了包含以下文本变体的错误：</span><span class="sxs-lookup"><span data-stu-id="6da65-112">An error containing a variation of the following text is provided:</span></span>

```
The type 'JsonResult' exists in both 'Microsoft.AspNetCore.Mvc.Core, Version=3.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60' and 'Microsoft.AspNetCore.Mvc.Formatters.Json, Version=2.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60'
```

<span data-ttu-id="6da65-113">有关此类问题的示例，请参阅 [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220)。</span><span class="sxs-lookup"><span data-stu-id="6da65-113">For an example of such an issue, see [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="6da65-114">更改原因</span><span class="sxs-lookup"><span data-stu-id="6da65-114">Reason for change</span></span>

<span data-ttu-id="6da65-115">按 [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325) 所述，对 ASP.NET Core 组成进行平台级别的更改。</span><span class="sxs-lookup"><span data-stu-id="6da65-115">Platform-level changes to the composition of ASP.NET Core as described at [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6da65-116">建议操作</span><span class="sxs-lookup"><span data-stu-id="6da65-116">Recommended action</span></span>

<span data-ttu-id="6da65-117">根据 2.2 版本的 `Microsoft.AspNetCore.Mvc.Formatters.Json` 编译的库可能需要重新编译才能解决所有使用者的问题。</span><span class="sxs-lookup"><span data-stu-id="6da65-117">Libraries compiled against the 2.2 version of `Microsoft.AspNetCore.Mvc.Formatters.Json` may need to recompile to address the problem for all consumers.</span></span> <span data-ttu-id="6da65-118">如果受到影响，请与库作者联系。</span><span class="sxs-lookup"><span data-stu-id="6da65-118">If affected, contact the library author.</span></span> <span data-ttu-id="6da65-119">请求重新编译库以面向 ASP.NET Core 3.0。</span><span class="sxs-lookup"><span data-stu-id="6da65-119">Request recompilation of the library to target ASP.NET Core 3.0.</span></span>

#### <a name="category"></a><span data-ttu-id="6da65-120">类别</span><span class="sxs-lookup"><span data-stu-id="6da65-120">Category</span></span>

<span data-ttu-id="6da65-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6da65-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6da65-122">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="6da65-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.JsonResult?displayProperty=nameWithType>

<!-- 

### Affected APIs

`T:Microsoft.AspNetCore.Mvc.JsonResult`

-->
