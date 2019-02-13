---
title: .NET API 分析器
description: 了解 .NET API 分析器如何有助于检测弃用的 API 和平台兼容性问题。
author: oliag
ms.author: mairaw
ms.date: 05/31/2018
ms.technology: dotnet-standard
ms.openlocfilehash: d27e5299ad9b1a3dcd89d5a947d91f06a54549e2
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759127"
---
# <a name="net-api-analyzer"></a><span data-ttu-id="9db07-103">.NET API 分析器</span><span class="sxs-lookup"><span data-stu-id="9db07-103">.NET API analyzer</span></span>

<span data-ttu-id="9db07-104">.NET API 分析器是 Roslyn 分析器，可用于发现不同平台上的潜在 C# API 兼容性风险，并检测是否调用了弃用的 API。</span><span class="sxs-lookup"><span data-stu-id="9db07-104">The .NET API Analyzer is a Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span> <span data-ttu-id="9db07-105">可供所有 C# 开发人员在任何开发阶段使用。</span><span class="sxs-lookup"><span data-stu-id="9db07-105">It can be useful for all C# developers at any stage of development.</span></span>

<span data-ttu-id="9db07-106">API 分析器以 NuGet 包 [Microsoft.DotNet.Analyzers.Compatibility](https://www.nuget.org/packages/Microsoft.DotNet.Analyzers.Compatibility/) 的形式提供。</span><span class="sxs-lookup"><span data-stu-id="9db07-106">API Analyzer comes as a NuGet package [Microsoft.DotNet.Analyzers.Compatibility](https://www.nuget.org/packages/Microsoft.DotNet.Analyzers.Compatibility/).</span></span> <span data-ttu-id="9db07-107">在项目中引用此分析器后，它就会自动监视代码，并指出有问题的 API 使用。</span><span class="sxs-lookup"><span data-stu-id="9db07-107">After you reference it in a project, it automatically monitors the code and indicates problematic API usage.</span></span> <span data-ttu-id="9db07-108">还可以单击灯泡图标，获取有关可能解决方案的建议。</span><span class="sxs-lookup"><span data-stu-id="9db07-108">You can also get suggestions on possible fixes by clicking on the light bulb.</span></span> <span data-ttu-id="9db07-109">下拉菜单包括禁止显示警告的选项。</span><span class="sxs-lookup"><span data-stu-id="9db07-109">The drop-down menu includes an option to suppress the warnings.</span></span>

> [!NOTE]
> <span data-ttu-id="9db07-110">.NET API 分析器仍为预发行版。</span><span class="sxs-lookup"><span data-stu-id="9db07-110">The .NET API analyzer is still a pre-release version.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9db07-111">系统必备</span><span class="sxs-lookup"><span data-stu-id="9db07-111">Prerequisites</span></span>

* <span data-ttu-id="9db07-112">Visual Studio 2017 或 Visual Studio for Mac（所有版本）。</span><span class="sxs-lookup"><span data-stu-id="9db07-112">Visual Studio 2017 or Visual Studio for Mac (all versions).</span></span>

## <a name="discovering-deprecated-apis"></a><span data-ttu-id="9db07-113">发现弃用的 API</span><span class="sxs-lookup"><span data-stu-id="9db07-113">Discovering deprecated APIs</span></span>

### <a name="what-are-deprecated-apis"></a><span data-ttu-id="9db07-114">什么是弃用的 API？</span><span class="sxs-lookup"><span data-stu-id="9db07-114">What are deprecated APIs?</span></span>

<span data-ttu-id="9db07-115">.NET 系列是一组不断升级的大型产品，力求更好地满足客户需求。</span><span class="sxs-lookup"><span data-stu-id="9db07-115">The .NET family is a set of large products that are constantly upgraded to better serve customer needs.</span></span> <span data-ttu-id="9db07-116">弃用并将一些 API 替换为新 API 是很自然的。</span><span class="sxs-lookup"><span data-stu-id="9db07-116">It's natural to deprecate some APIs and replace them with new ones.</span></span> <span data-ttu-id="9db07-117">若有更好的替换 API，API 便会被视为弃用。</span><span class="sxs-lookup"><span data-stu-id="9db07-117">An API is considered deprecated when a better alternative exists.</span></span> <span data-ttu-id="9db07-118">指明 API 已遭弃用且不得使用的一种方法是，用 <xref:System.ObsoleteAttribute> 属性标记它。</span><span class="sxs-lookup"><span data-stu-id="9db07-118">One way to inform that an API is deprecated and shouldn't be used is to mark it with the <xref:System.ObsoleteAttribute> attribute.</span></span> <span data-ttu-id="9db07-119">这种方法的缺点是，所有已过时 API 都只有一个诊断 ID（对于 C#，ID 为 [CS0612](../../csharp/misc/cs0612.md)）。</span><span class="sxs-lookup"><span data-stu-id="9db07-119">The disadvantage of this approach is that there is only one diagnostic ID for all obsolete APIs (for C#, [CS0612](../../csharp/misc/cs0612.md)).</span></span> <span data-ttu-id="9db07-120">这表示：</span><span class="sxs-lookup"><span data-stu-id="9db07-120">This means that:</span></span>
- <span data-ttu-id="9db07-121">无法为每个事例设置专用文档。</span><span class="sxs-lookup"><span data-stu-id="9db07-121">It's impossible to have dedicated documents for each case.</span></span>
- <span data-ttu-id="9db07-122">无法禁止显示特定类别的警告。</span><span class="sxs-lookup"><span data-stu-id="9db07-122">It's impossible to suppress certain category of warnings.</span></span> <span data-ttu-id="9db07-123">要么禁止显示所有警告，要么允许显示所有警告。</span><span class="sxs-lookup"><span data-stu-id="9db07-123">You can suppress either all or none of them.</span></span>
- <span data-ttu-id="9db07-124">为了通知用户有新弃用，必须更新引用的程序集或目标包。</span><span class="sxs-lookup"><span data-stu-id="9db07-124">To inform users of a new deprecation, a referenced assembly or targeting package has to be updated.</span></span>

<span data-ttu-id="9db07-125">API 分析器使用 API 专用错误代码，这些代码以 DE（全称是“Deprecation Error”（弃用错误））开头，这样就可以单独控制各个警告的显示。</span><span class="sxs-lookup"><span data-stu-id="9db07-125">The API Analyzer uses API-specific error codes that begin with DE (which stands for Deprecation Error), which allows control over the display of individual warnings.</span></span> <span data-ttu-id="9db07-126">分析器发现的弃用的 API 在 [dotnet/platform-compat](https://github.com/dotnet/platform-compat) 存储库中进行定义。</span><span class="sxs-lookup"><span data-stu-id="9db07-126">The deprecated APIs identified by the analyzer are defined in the [dotnet/platform-compat](https://github.com/dotnet/platform-compat) repo.</span></span>

### <a name="using-the-api-analyzer"></a><span data-ttu-id="9db07-127">使用 API 分析器</span><span class="sxs-lookup"><span data-stu-id="9db07-127">Using the API Analyzer</span></span>

<span data-ttu-id="9db07-128">如果代码使用了弃用的 API（如 <xref:System.Net.WebClient>），API 分析器便会使用绿色波浪线突出显示它。</span><span class="sxs-lookup"><span data-stu-id="9db07-128">When a deprecated API, such as <xref:System.Net.WebClient>, is used in a code, API Analyzer highlights it with a green squiggly line.</span></span> <span data-ttu-id="9db07-129">如果将鼠标悬停在 API 调用之上，就会看到包含 API 弃用相关信息的灯泡，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="9db07-129">When you hover over the API call, a light bulb is displayed with information about the API deprecation, as in the following example:</span></span>

![“显示绿色波浪线且左侧有灯泡的 WebClient API 屏幕截图”](media/api-analyzer/green-squiggle.jpg)

<span data-ttu-id="9db07-131">弃用的 API 每出现一次，“错误列表”窗口中都会显示具有唯一 ID 的警告，如下面的示例所示 (`DE004`)：</span><span class="sxs-lookup"><span data-stu-id="9db07-131">The **Error List** window contains warnings with a unique ID per deprecated API, as shown in the following example (`DE004`):</span></span> 

![“显示警告 ID 和说明的‘错误列表’窗口屏幕截图”](media/api-analyzer/warnings.jpg)

<span data-ttu-id="9db07-133">单击 ID 后，便会转到详细信息网页，其中说明了 API 遭弃用的原因，以及有关可用替换 API 的建议。</span><span class="sxs-lookup"><span data-stu-id="9db07-133">By clicking on the ID, you go to a webpage with detailed information about why the API was deprecated and suggestions regarding alternative APIs that can be used.</span></span>

<span data-ttu-id="9db07-134">可以禁止显示任何警告，具体方法是右键单击突出显示的成员，并选择“禁止 \<诊断 ID>”。</span><span class="sxs-lookup"><span data-stu-id="9db07-134">Any warnings can be suppressed by right-clicking on the highlighted member and selecting **Suppress \<diagnostic ID>**.</span></span> <span data-ttu-id="9db07-135">禁止显示警告的方法有两种：</span><span class="sxs-lookup"><span data-stu-id="9db07-135">There are two ways to suppress warnings:</span></span> 

* [<span data-ttu-id="9db07-136">本地（在源中）</span><span class="sxs-lookup"><span data-stu-id="9db07-136">locally (in source)</span></span>](#suppressing-warnings-locally)
* <span data-ttu-id="9db07-137">[全局（在禁止文件中）](#suppressing-warnings-globally)- 推荐方法</span><span class="sxs-lookup"><span data-stu-id="9db07-137">[globally (in a suppression file)](#suppressing-warnings-globally) - recommended</span></span>

### <a name="suppressing-warnings-locally"></a><span data-ttu-id="9db07-138">在本地禁止显示警告</span><span class="sxs-lookup"><span data-stu-id="9db07-138">Suppressing warnings locally</span></span>

<span data-ttu-id="9db07-139">若要在本地禁止显示警告，请右键单击要对其禁止显示警告的成员，再依次选择“快速操作和重构” > “禁止诊断 ID \<诊断 ID> > “在源中”。</span><span class="sxs-lookup"><span data-stu-id="9db07-139">To suppress warnings locally, right-click on the member you want to suppress warnings for and then select **Quick Actions and Refactorings** > **Suppress *diagnostic ID*\<diagnostic ID>** > **in Source**.</span></span> <span data-ttu-id="9db07-140">此时，[#pragma](../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) 警告预处理器指令会添加到定义的范围内的源代码中：![“用 #pragma 警告禁用指令框定的代码屏幕截图”](media/api-analyzer/suppress-in-source.jpg)</span><span class="sxs-lookup"><span data-stu-id="9db07-140">The [#pragma](../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) warning preprocessor directive is added to your source code in the scope defined: !["Screenshot of code framed with #pragma warning disable"](media/api-analyzer/suppress-in-source.jpg)</span></span>

### <a name="suppressing-warnings-globally"></a><span data-ttu-id="9db07-141">在全局禁止显示警告</span><span class="sxs-lookup"><span data-stu-id="9db07-141">Suppressing warnings globally</span></span>

<span data-ttu-id="9db07-142">若要在全局禁止显示警告，请右键单击要对其禁止显示警告的成员，再依次选择“快速操作和重构” > “禁止诊断 ID \<诊断 ID> > “在禁止文件中”。</span><span class="sxs-lookup"><span data-stu-id="9db07-142">To suppress warnings globally, right-click on the member you want to suppress warnings for and then select **Quick Actions and Refactorings** > **Suppress *diagnostic ID*\<diagnostic ID>** > **in Suppression File**.</span></span>

![“显示绿色波浪线且左侧有灯泡的 WebClient API 屏幕截图”](media/api-analyzer/suppress-in-sup-file.jpg)

<span data-ttu-id="9db07-144">首次禁止后，GlobalSuppressions.cs 文件会添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="9db07-144">A *GlobalSuppressions.cs* file is added to your project after the first suppression.</span></span> <span data-ttu-id="9db07-145">此时，新的全局禁止会追加到此文件中。</span><span class="sxs-lookup"><span data-stu-id="9db07-145">New global suppressions are appended to this file.</span></span>

![“显示绿色波浪线且左侧有灯泡的 WebClient API 屏幕截图”](media/api-analyzer/suppression-file.jpg)

<span data-ttu-id="9db07-147">全局禁止是推荐方法，可确保 API 使用跨项目保持一致。</span><span class="sxs-lookup"><span data-stu-id="9db07-147">Global suppression is the recommended way to ensure consistency of API usage across projects.</span></span>

## <a name="discovering-cross-platform-issues"></a><span data-ttu-id="9db07-148">发现跨平台问题</span><span class="sxs-lookup"><span data-stu-id="9db07-148">Discovering cross-platform issues</span></span>

<span data-ttu-id="9db07-149">与弃用的 API 类似，分析器可发现所有的非跨平台 API。</span><span class="sxs-lookup"><span data-stu-id="9db07-149">Similar to deprecated APIs, the analyzer identifies all APIs that are not cross-platform.</span></span> <span data-ttu-id="9db07-150">例如，<xref:System.Console.WindowWidth?displayProperty=nameWithType> 适用于 Windows，但不适用于 Linux 和 macOS。</span><span class="sxs-lookup"><span data-stu-id="9db07-150">For example, <xref:System.Console.WindowWidth?displayProperty=nameWithType> works on Windows but not on Linux and macOS.</span></span> <span data-ttu-id="9db07-151">诊断 ID 显示在“错误列表”窗口中。</span><span class="sxs-lookup"><span data-stu-id="9db07-151">The diagnostic ID is shown in the **Error List** window.</span></span> <span data-ttu-id="9db07-152">可以禁止显示警告，具体方法是右键单击并选择“快速操作和重构”。</span><span class="sxs-lookup"><span data-stu-id="9db07-152">You can suppress that warning by right-clicking and selecting **Quick Actions and Refactorings**.</span></span> <span data-ttu-id="9db07-153">与禁止显示 API 弃用警告时的两种选择（要么继续使用弃用的成员并禁止显示警告，要么根本就不使用弃用的成员）不同，如果仅对特定平台开发代码，可以对不打算在其上运行代码的其他所有平台禁止显示任何警告。</span><span class="sxs-lookup"><span data-stu-id="9db07-153">Unlike deprecation cases where you have two options (either keep using the deprecated member and suppress warnings or not use it at all), here if you're developing your code only for certain platforms, you can suppress all warnings for all other platforms you don't plan to run your code on.</span></span> <span data-ttu-id="9db07-154">为此，只需编辑项目文件，并添加列出要忽略的所有平台的 `PlatformCompatIgnore` 属性即可。</span><span class="sxs-lookup"><span data-stu-id="9db07-154">To do so, you just need to edit your project file and add the `PlatformCompatIgnore` property that lists all platforms to be ignored.</span></span> <span data-ttu-id="9db07-155">接受的值包括 `Linux`、`macOS` 和 `Windows`。</span><span class="sxs-lookup"><span data-stu-id="9db07-155">The accepted values are: `Linux`, `macOS`, and `Windows`.</span></span>

```xml
<PropertyGroup>
    <PlatformCompatIgnore>Linux;macOS</PlatformCompatIgnore>
</PropertyGroup>
```

<span data-ttu-id="9db07-156">如果代码定目标到多个平台，且要利用其中一些平台不支持的 API，可以使用 `if` 语句作为相应部分代码的临界子句：</span><span class="sxs-lookup"><span data-stu-id="9db07-156">If your code targets multiple platforms and you want to take advantage of an API not supported on some of them, you can guard that part of the code with an `if` statement:</span></span>

```csharp
if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
{
     var w = Console.WindowWidth;
     // More code
}
```

<span data-ttu-id="9db07-157">可以每目标框架/操作系统进行有条件编译，但暂需要[手动](../frameworks.md#how-to-specify-target-frameworks)这样做。</span><span class="sxs-lookup"><span data-stu-id="9db07-157">You can also conditionally compile per target framework/operating system, but you currently need to do that [manually](../frameworks.md#how-to-specify-target-frameworks).</span></span>

## <a name="supported-diagnostics"></a><span data-ttu-id="9db07-158">支持的诊断</span><span class="sxs-lookup"><span data-stu-id="9db07-158">Supported diagnostics</span></span>

<span data-ttu-id="9db07-159">目前，分析器处理以下情况：</span><span class="sxs-lookup"><span data-stu-id="9db07-159">Currently, the analyzer handles the following cases:</span></span>

* <span data-ttu-id="9db07-160">使用抛出 <xref:System.PlatformNotSupportedException> 的 .NET Standard API (PC001)。</span><span class="sxs-lookup"><span data-stu-id="9db07-160">Usage of a .NET Standard API that throws <xref:System.PlatformNotSupportedException> (PC001).</span></span>
* <span data-ttu-id="9db07-161">使用 .NET Framework 4.6.1 不支持的 .NET Standard API (PC002)。</span><span class="sxs-lookup"><span data-stu-id="9db07-161">Usage of a .NET Standard API that isn't available on the .NET Framework 4.6.1 (PC002).</span></span>
* <span data-ttu-id="9db07-162">使用 UWP 中不存在的本机 API (PC003)。</span><span class="sxs-lookup"><span data-stu-id="9db07-162">Usage of a native API that doesn’t exist in UWP (PC003).</span></span>
* <span data-ttu-id="9db07-163">使用标记为弃用的 API (DEXXXX)。</span><span class="sxs-lookup"><span data-stu-id="9db07-163">Usage of an API that is marked as deprecated (DEXXXX).</span></span>

## <a name="ci-machine"></a><span data-ttu-id="9db07-164">CI 计算机</span><span class="sxs-lookup"><span data-stu-id="9db07-164">CI machine</span></span>

<span data-ttu-id="9db07-165">所有这些诊断不仅可以通过 IDE 获取，还能通过命令行在生成项目期间获取（包括 CI 服务器）。</span><span class="sxs-lookup"><span data-stu-id="9db07-165">All these diagnostics are available not only in the IDE, but also on the command line as part of building your project, which includes the CI server.</span></span>

## <a name="configuration"></a><span data-ttu-id="9db07-166">配置</span><span class="sxs-lookup"><span data-stu-id="9db07-166">Configuration</span></span>

<span data-ttu-id="9db07-167">由用户确定应如何处理这些诊断，是生成警告、错误、建议，还是禁用诊断。</span><span class="sxs-lookup"><span data-stu-id="9db07-167">The user decides how the diagnostics should be treated: as warnings, errors, suggestions, or to be turned off.</span></span> <span data-ttu-id="9db07-168">例如，作为架构师，可以确定应将兼容性问题处理为错误，对调用某些弃用的 API 生成警告，而对其他情况仅生成建议。</span><span class="sxs-lookup"><span data-stu-id="9db07-168">For example, as an architect, you can decide that compatibility issues should be treated as errors, calls to some deprecated APIs generate warnings, while others only generate suggestions.</span></span> <span data-ttu-id="9db07-169">可以按诊断 ID 和按项目单独对此进行配置。</span><span class="sxs-lookup"><span data-stu-id="9db07-169">You can configure this separately by diagnostic ID and by project.</span></span> <span data-ttu-id="9db07-170">为此，请在“解决方案资源管理器”中转到项目下的“依赖关系”节点。</span><span class="sxs-lookup"><span data-stu-id="9db07-170">To do so in **Solution Explorer**, navigate to the **Dependencies** node under your project.</span></span> <span data-ttu-id="9db07-171">依次展开节点“依赖关系” > “分析器” > “Microsoft.DotNet.Analyzers.Compatibility”。</span><span class="sxs-lookup"><span data-stu-id="9db07-171">Expand the nodes **Dependencies** > **Analyzers** > **Microsoft.DotNet.Analyzers.Compatibility**.</span></span> <span data-ttu-id="9db07-172">右键单击诊断 ID，选择“设置规则集严重性”，并选中相应选项。</span><span class="sxs-lookup"><span data-stu-id="9db07-172">Right click on the diagnostic ID, select **Set Rule Set Severity** and pick the desired option.</span></span>

![“显示诊断和‘设置规则集严重性’弹出对话框的解决方案资源管理器屏幕截图”](media/api-analyzer/disable-notifications.jpg)

## <a name="see-also"></a><span data-ttu-id="9db07-174">请参阅</span><span class="sxs-lookup"><span data-stu-id="9db07-174">See also</span></span>

- <span data-ttu-id="9db07-175">[API 分析器简介](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/)博客文章。</span><span class="sxs-lookup"><span data-stu-id="9db07-175">[Introducing API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) blog post.</span></span>
- <span data-ttu-id="9db07-176">YouTube 上的 [API 分析器](https://youtu.be/eeBEahYXGd0)演示视频。</span><span class="sxs-lookup"><span data-stu-id="9db07-176">[API Analyzer](https://youtu.be/eeBEahYXGd0) demo video on YouTube.</span></span>
