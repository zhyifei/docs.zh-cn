---
title: .NET Core CLI 工具遥测
description: 了解可收集使用情况信息以供分析的 .NET Core 工具遥测功能、收集哪些数据，以及如何禁用遥测。
author: richlander
ms.author: mairaw
ms.date: 08/04/2017
ms.openlocfilehash: 4c04867f5db512ef53c23ec41ea66db570a82021
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216078"
---
# <a name="net-core-cli-tools-telemetry"></a><span data-ttu-id="fbb3d-103">.NET Core CLI 工具遥测</span><span class="sxs-lookup"><span data-stu-id="fbb3d-103">.NET Core CLI Tools telemetry</span></span>

<span data-ttu-id="fbb3d-104">[.NET Core SDK](index.md) 包括可收集使用情况信息的[遥测功能](https://github.com/dotnet/cli/pull/2145)。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-104">The [.NET Core SDK](index.md) includes a [telemetry feature](https://github.com/dotnet/cli/pull/2145) that collects usage information.</span></span> <span data-ttu-id="fbb3d-105">请务必让 .NET 团队了解到工具使用情况，以便我们可以进行改进。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-105">It's important that the .NET Team understands how the tools are used so that we can improve them.</span></span> <span data-ttu-id="fbb3d-106">有关详细信息，请参阅[从 .NET Core SDK 遥测中所了解到的内容](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/)。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-106">For more information, see [What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).</span></span>

<span data-ttu-id="fbb3d-107">数据为匿名收集，并以汇总形式发布，以供 Microsoft 和社区根据 [Creative Commons Attribution 许可证](https://creativecommons.org/licenses/by/4.0/)使用。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-107">The collected data is anonymous and published in an aggregated form for use by both Microsoft and the community under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span> 

## <a name="scope"></a><span data-ttu-id="fbb3d-108">范围</span><span class="sxs-lookup"><span data-stu-id="fbb3d-108">Scope</span></span>

<span data-ttu-id="fbb3d-109">`dotnet` 命令用于启动应用程序和 .NET Core CLI。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-109">The `dotnet` command is used to launch both apps and the .NET Core CLI.</span></span> <span data-ttu-id="fbb3d-110">`dotnet` 命令本身不收集遥测数据。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-110">The `dotnet` command itself doesn't collect telemetry.</span></span> <span data-ttu-id="fbb3d-111">`dotnet` 命令运行的 .NET Core CLI 命令收集遥测数据。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-111">The .NET Core CLI commands run by the `dotnet` command collect the telemetry.</span></span>

<span data-ttu-id="fbb3d-112">使用 `dotnet` 命令本身且没有附加任何命令时，不会启用遥测：</span><span class="sxs-lookup"><span data-stu-id="fbb3d-112">Telemetry *isn't enabled* when using the `dotnet` command itself, with no command attached:</span></span>

- `dotnet`
- `dotnet [path-to-app]`

<span data-ttu-id="fbb3d-113">使用 [.NET Core CLI 命令](index.md)时，就会启用遥测，如：</span><span class="sxs-lookup"><span data-stu-id="fbb3d-113">Telemetry *is enabled* when using the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`


## <a name="behavior"></a><span data-ttu-id="fbb3d-114">行为</span><span class="sxs-lookup"><span data-stu-id="fbb3d-114">Behavior</span></span>

<span data-ttu-id="fbb3d-115">.NET Core CLI 工具遥测功能默认处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-115">The .NET Core CLI Tools telemetry feature is enabled by default.</span></span> <span data-ttu-id="fbb3d-116">通过将 `DOTNET_CLI_TELEMETRY_OPTOUT` 环境变量设置为 `1` 或 `true`，可以选择退出遥测功能。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-116">Opt-out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

## <a name="data-points"></a><span data-ttu-id="fbb3d-117">数据点</span><span class="sxs-lookup"><span data-stu-id="fbb3d-117">Data points</span></span>

<span data-ttu-id="fbb3d-118">此功能收集以下数据：</span><span class="sxs-lookup"><span data-stu-id="fbb3d-118">The feature collects the following data:</span></span>

- <span data-ttu-id="fbb3d-119">调用时间戳&#8224;</span><span class="sxs-lookup"><span data-stu-id="fbb3d-119">Timestamp of invocation&#8224;</span></span>
- <span data-ttu-id="fbb3d-120">调用的命令（例如，“build”）&#8224;</span><span class="sxs-lookup"><span data-stu-id="fbb3d-120">Command invoked (for example, "build")&#8224;</span></span>
- <span data-ttu-id="fbb3d-121">用于确定地理位置的三个八进制数 IP 地址&#8224;</span><span class="sxs-lookup"><span data-stu-id="fbb3d-121">Three octet IP address used to determine geographical location&#8224;</span></span>
- <span data-ttu-id="fbb3d-122">命令的 `ExitCode`</span><span class="sxs-lookup"><span data-stu-id="fbb3d-122">`ExitCode` of the command</span></span>
- <span data-ttu-id="fbb3d-123">测试运行程序（对于测试项目）</span><span class="sxs-lookup"><span data-stu-id="fbb3d-123">Test runner (for test projects)</span></span>
- <span data-ttu-id="fbb3d-124">操作系统和版本&#8224;</span><span class="sxs-lookup"><span data-stu-id="fbb3d-124">Operating system and version&#8224;</span></span>
- <span data-ttu-id="fbb3d-125">“运行时”节点中是否有运行时 ID</span><span class="sxs-lookup"><span data-stu-id="fbb3d-125">Whether runtime IDs are present in the runtimes node</span></span>
- <span data-ttu-id="fbb3d-126">.NET Core SDK 版本&#8224;</span><span class="sxs-lookup"><span data-stu-id="fbb3d-126">.NET Core SDK version&#8224;</span></span>

<span data-ttu-id="fbb3d-127">&#8224;此指标已发布。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-127">&#8224;This metric is published.</span></span>

<span data-ttu-id="fbb3d-128">自 .NET Core SDK 2.0 起，收集以下新数据点：</span><span class="sxs-lookup"><span data-stu-id="fbb3d-128">Starting with .NET Core SDK 2.0, new data points are collected:</span></span>

- <span data-ttu-id="fbb3d-129">`dotnet` 命令参数和选项：仅收集已知参数和选项（非任意字符串）。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-129">`dotnet` command arguments and options: only known arguments and options are collected (not arbitrary strings).</span></span>
- <span data-ttu-id="fbb3d-130">SDK 是否在容器中运行。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-130">Whether the SDK is running in a container.</span></span>
- <span data-ttu-id="fbb3d-131">目标框架。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-131">Target frameworks.</span></span>
- <span data-ttu-id="fbb3d-132">经过哈希处理的 MAC 地址：计算机的加密 (SHA256) 匿名的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-132">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> <span data-ttu-id="fbb3d-133">此指标未发布。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-133">This metric is not published.</span></span>
- <span data-ttu-id="fbb3d-134">经过哈希处理的当前工作目录。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-134">Hashed current working directory.</span></span>

<span data-ttu-id="fbb3d-135">此功能不收集用户名或电子邮件地址等个人数据。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-135">The feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="fbb3d-136">也不会扫描代码，亦不会提取项目级敏感数据，如名称、存储库或作者。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-136">It doesn't scan your code and doesn't extract sensitive project-level data, such as name, repo, or author.</span></span> <span data-ttu-id="fbb3d-137">数据通过 [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) 技术安全地发送到 Microsoft 服务器，提供对保留数据的受限访问权限，并在严格的安全控制下从安全 [Azure 存储](https://azure.microsoft.com/services/storage/)系统发布。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-137">The data is sent securely to Microsoft servers using [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="fbb3d-138">我们需要知道工具使用情况及其是否在正常运行，而不是使用这些工具生成的内容。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-138">We want to know how the tools are used and if they're working well, not what you're building with the tools.</span></span> <span data-ttu-id="fbb3d-139">如果怀疑遥测在收集敏感数据，或认为我们处理数据的方式不安全或不恰当，请[在 dotnet/cli 存储库问题中记录问题](https://github.com/dotnet/cli/issues)以供调查。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-139">If you suspect that the telemetry is collecting sensitive data or that we're insecurely or inappropriately handling data, [file an issue in the dotnet/cli repo issues](https://github.com/dotnet/cli/issues) for investigation.</span></span>

## <a name="published-data"></a><span data-ttu-id="fbb3d-140">已发布的数据</span><span class="sxs-lookup"><span data-stu-id="fbb3d-140">Published data</span></span>

<span data-ttu-id="fbb3d-141">数据每季度发布一次，并在 [.NET Core SDK 使用情况数据](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)中列出。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-141">Published data is available quarterly and are listed at [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span></span> <span data-ttu-id="fbb3d-142">数据文件列如下：</span><span class="sxs-lookup"><span data-stu-id="fbb3d-142">The columns of a data file are:</span></span>
- <span data-ttu-id="fbb3d-143">时间戳</span><span class="sxs-lookup"><span data-stu-id="fbb3d-143">Timestamp</span></span>
- <span data-ttu-id="fbb3d-144">Occurrences&#8224;</span><span class="sxs-lookup"><span data-stu-id="fbb3d-144">Occurrences&#8224;</span></span>
- <span data-ttu-id="fbb3d-145">命令</span><span class="sxs-lookup"><span data-stu-id="fbb3d-145">Command</span></span>
- <span data-ttu-id="fbb3d-146">Geography&#8225;</span><span class="sxs-lookup"><span data-stu-id="fbb3d-146">Geography&#8225;</span></span>
- <span data-ttu-id="fbb3d-147">OSFamily</span><span class="sxs-lookup"><span data-stu-id="fbb3d-147">OSFamily</span></span>
- <span data-ttu-id="fbb3d-148">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="fbb3d-148">RuntimeID</span></span>
- <span data-ttu-id="fbb3d-149">OSVersion</span><span class="sxs-lookup"><span data-stu-id="fbb3d-149">OSVersion</span></span>
- <span data-ttu-id="fbb3d-150">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="fbb3d-150">SDKVersion</span></span>

<span data-ttu-id="fbb3d-151">&#8224;Occurrences 列显示相应命令当天用于该行指标的总次数。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-151">&#8224;The *Occurrences* column displays the aggregate count of that command's use for that row's metrics that day.</span></span> 

<span data-ttu-id="fbb3d-152">&#8225;通常情况下，Geography 列显示国家/地区名称。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-152">&#8225;Typically, the *Geography* column displays the name of a country.</span></span> <span data-ttu-id="fbb3d-153">在某些情况下，此列中会显示南极洲，要么是因为研究人员在南极洲使用 .NET Core，要么是因为位置数据不正确。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-153">In some cases, the continent of Antarctica appears in this column, either due to researchers using .NET Core in Antarctica or incorrect location data.</span></span>

### <a name="example"></a><span data-ttu-id="fbb3d-154">示例</span><span class="sxs-lookup"><span data-stu-id="fbb3d-154">Example</span></span>

| <span data-ttu-id="fbb3d-155">时间戳</span><span class="sxs-lookup"><span data-stu-id="fbb3d-155">Timestamp</span></span>      | <span data-ttu-id="fbb3d-156">Occurrences</span><span class="sxs-lookup"><span data-stu-id="fbb3d-156">Occurrences</span></span> | <span data-ttu-id="fbb3d-157">命令</span><span class="sxs-lookup"><span data-stu-id="fbb3d-157">Command</span></span> | <span data-ttu-id="fbb3d-158">Geography</span><span class="sxs-lookup"><span data-stu-id="fbb3d-158">Geography</span></span> | <span data-ttu-id="fbb3d-159">OSFamily</span><span class="sxs-lookup"><span data-stu-id="fbb3d-159">OSFamily</span></span> | <span data-ttu-id="fbb3d-160">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="fbb3d-160">RuntimeID</span></span>     | <span data-ttu-id="fbb3d-161">OSVersion</span><span class="sxs-lookup"><span data-stu-id="fbb3d-161">OSVersion</span></span> | <span data-ttu-id="fbb3d-162">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="fbb3d-162">SDKVersion</span></span> |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| <span data-ttu-id="fbb3d-163">4/16/2017 0:00</span><span class="sxs-lookup"><span data-stu-id="fbb3d-163">4/16/2017 0:00</span></span> | <span data-ttu-id="fbb3d-164">8</span><span class="sxs-lookup"><span data-stu-id="fbb3d-164">8</span></span>           | <span data-ttu-id="fbb3d-165">运行</span><span class="sxs-lookup"><span data-stu-id="fbb3d-165">run</span></span>     | <span data-ttu-id="fbb3d-166">Uganda</span><span class="sxs-lookup"><span data-stu-id="fbb3d-166">Uganda</span></span>    | <span data-ttu-id="fbb3d-167">Darwin</span><span class="sxs-lookup"><span data-stu-id="fbb3d-167">Darwin</span></span>   | <span data-ttu-id="fbb3d-168">osx.10.12-x64</span><span class="sxs-lookup"><span data-stu-id="fbb3d-168">osx.10.12-x64</span></span> | <span data-ttu-id="fbb3d-169">10.12</span><span class="sxs-lookup"><span data-stu-id="fbb3d-169">10.12</span></span>     | <span data-ttu-id="fbb3d-170">1.0.1</span><span class="sxs-lookup"><span data-stu-id="fbb3d-170">1.0.1</span></span>      |

### <a name="datasets"></a><span data-ttu-id="fbb3d-171">数据集</span><span class="sxs-lookup"><span data-stu-id="fbb3d-171">Datasets</span></span>

[<span data-ttu-id="fbb3d-172">2016 - Q3</span><span class="sxs-lookup"><span data-stu-id="fbb3d-172">2016 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)  
[<span data-ttu-id="fbb3d-173">2016 - Q4</span><span class="sxs-lookup"><span data-stu-id="fbb3d-173">2016 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)  
[<span data-ttu-id="fbb3d-174">2017 - Q1</span><span class="sxs-lookup"><span data-stu-id="fbb3d-174">2017 - Q1</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)  
[<span data-ttu-id="fbb3d-175">2017 - Q2</span><span class="sxs-lookup"><span data-stu-id="fbb3d-175">2017 - Q2</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)

<span data-ttu-id="fbb3d-176">其他数据集使用标准的 URL 格式进行发布。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-176">Additional datasets are posted using a standard URL format.</span></span> <span data-ttu-id="fbb3d-177">请将 `<YEAR>` 替换为相应年份，并将 `<QUARTER>` 替换为相应季度（使用 `1`、`2`、`3` 或 `4`）。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-177">Replace `<YEAR>` with the year and replace `<QUARTER>` with the quarter of the year (use `1`, `2`, `3`, or `4`).</span></span> <span data-ttu-id="fbb3d-178">文件采用制表符分隔值 (TSV) 格式。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-178">The files are in tab-separated values (*TSV*) format.</span></span> 

```
https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv
```

## <a name="license"></a><span data-ttu-id="fbb3d-179">许可证</span><span class="sxs-lookup"><span data-stu-id="fbb3d-179">License</span></span>

<span data-ttu-id="fbb3d-180">.NET Core 的 Microsoft 分发由 [MICROSOFT .NET LIBRARY EULA](https://aka.ms/dotnet-core-eula) 授权。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-180">The Microsoft distribution of .NET Core is licensed with the [MICROSOFT .NET LIBRARY EULA](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="fbb3d-181">此许可证包括“DATA”部分，用于启用遥测（如下所示）。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-181">This license includes the "DATA" section to enable telemetry (shown below).</span></span>

<span data-ttu-id="fbb3d-182">[.NET NuGet 包](https://www.nuget.org/profiles/dotnetframework)使用相同许可证，但不启用遥测（见[范围](#scope)）。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-182">[.NET NuGet packages](https://www.nuget.org/profiles/dotnetframework) use the same license but don't enable telemetry (see [Scope](#scope)).</span></span>

> 2. <span data-ttu-id="fbb3d-183">DATA。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-183">DATA.</span></span> <span data-ttu-id="fbb3d-184">此软件可能会收集并向 Microsoft 发送你的信息和软件使用信息。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-184">The software may collect information about you and your use of the software, and send that to Microsoft.</span></span> <span data-ttu-id="fbb3d-185">Microsoft 可能会使用此类信息来改进我们的产品和服务。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-185">Microsoft may use this information to improve our products and services.</span></span> <span data-ttu-id="fbb3d-186">可以参阅帮助文档和隐私声明 http://go.microsoft.com/fwlink/?LinkId=528096 ，详细了解数据收集和使用。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-186">You can learn more about data collection and use in the help documentation and the privacy statement at http://go.microsoft.com/fwlink/?LinkId=528096.</span></span> <span data-ttu-id="fbb3d-187">使用此软件即表示同意接受这些做法。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-187">Your use of the software operates as your consent to these practices.</span></span>

## <a name="disclosure"></a><span data-ttu-id="fbb3d-188">公开</span><span class="sxs-lookup"><span data-stu-id="fbb3d-188">Disclosure</span></span>

<span data-ttu-id="fbb3d-189">.NET Core CLI 工具在用户首次运行其中一个命令（例如，`dotnet restore`）时显示以下文本。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-189">The .NET Core CLI Tools display the following text when you first run one of the commands (for example, `dotnet restore`).</span></span> <span data-ttu-id="fbb3d-190">文本可能会因运行的 SDK 版本而略有不同。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-190">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="fbb3d-191">此“首次运行”体验是 Microsoft 通知用户有关数据收集信息的方式。</span><span class="sxs-lookup"><span data-stu-id="fbb3d-191">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core @ https://aka.ms/dotnet-docs. Use dotnet --help to see available commands or go to https://aka.ms/dotnet-cli-docs.
 
Telemetry
--------------
The .NET Core tools collect usage data in order to improve your experience. The data is anonymous and does not include command-line arguments. The data is collected by Microsoft and shared with the community.
You can opt out of telemetry by setting a DOTNET_CLI_TELEMETRY_OPTOUT environment variable to 1 using your favorite shell.
You can read more about .NET Core tools telemetry @ https://aka.ms/dotnet-cli-telemetry.
```

## <a name="see-also"></a><span data-ttu-id="fbb3d-192">请参阅</span><span class="sxs-lookup"><span data-stu-id="fbb3d-192">See also</span></span>

[<span data-ttu-id="fbb3d-193">从 .NET Core SDK 遥测中所了解到的内容</span><span class="sxs-lookup"><span data-stu-id="fbb3d-193">What we've learned from .NET Core SDK Telemetry</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/)  
<span data-ttu-id="fbb3d-194">[遥测参考源（dotnet/cli 存储库；版本/2.0.0 分支）](https://github.com/dotnet/cli/tree/release/2.0.0/src/dotnet/Telemetry) </span><span class="sxs-lookup"><span data-stu-id="fbb3d-194">[Telemetry reference source (dotnet/cli repo; release/2.0.0 branch)](https://github.com/dotnet/cli/tree/release/2.0.0/src/dotnet/Telemetry) </span></span>  
[<span data-ttu-id="fbb3d-195">.NET Core SDK 使用情况数据</span><span class="sxs-lookup"><span data-stu-id="fbb3d-195">.NET Core SDK Usage Data</span></span>](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)
