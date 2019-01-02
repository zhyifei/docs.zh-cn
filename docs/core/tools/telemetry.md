---
title: .NET Core SDK 遥测
description: 了解可收集使用情况信息以供分析的 .NET Core SDK 遥测功能、收集哪些数据，以及如何禁用遥测。
author: richlander
ms.date: 06/20/2018
ms.custom: seodec18
ms.openlocfilehash: 8b0b546d70eab837c2e075f839990870ae9ea6b1
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168840"
---
# <a name="net-core-sdk-telemetry"></a><span data-ttu-id="ac811-103">.NET Core SDK 遥测</span><span class="sxs-lookup"><span data-stu-id="ac811-103">.NET Core SDK telemetry</span></span>

<span data-ttu-id="ac811-104">[.NET Core SDK](index.md) 包括可收集使用情况信息的[遥测功能](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)。</span><span class="sxs-lookup"><span data-stu-id="ac811-104">The [.NET Core SDK](index.md) includes a [telemetry feature](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry) that collects usage information.</span></span> <span data-ttu-id="ac811-105">请务必让 .NET 团队了解到工具使用情况，以便我们对其做出改进。</span><span class="sxs-lookup"><span data-stu-id="ac811-105">It's important that the .NET Team understands how the tools are used so they can be improved.</span></span> <span data-ttu-id="ac811-106">有关详细信息，请参阅[从 .NET Core SDK 遥测中所了解到的内容](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/)。</span><span class="sxs-lookup"><span data-stu-id="ac811-106">For more information, see [What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).</span></span>

<span data-ttu-id="ac811-107">数据为匿名收集，并以汇总形式发布，以供 Microsoft 和社区根据 [Creative Commons Attribution 许可证](https://creativecommons.org/licenses/by/4.0/)使用。</span><span class="sxs-lookup"><span data-stu-id="ac811-107">The collected data is anonymous and published in an aggregated form for use by both Microsoft and the community under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="ac811-108">范围</span><span class="sxs-lookup"><span data-stu-id="ac811-108">Scope</span></span>

<span data-ttu-id="ac811-109">`dotnet` 命令用于启动应用程序和 .NET Core CLI。</span><span class="sxs-lookup"><span data-stu-id="ac811-109">The `dotnet` command is used to launch both apps and the .NET Core CLI.</span></span> <span data-ttu-id="ac811-110">`dotnet` 命令本身不收集遥测数据。</span><span class="sxs-lookup"><span data-stu-id="ac811-110">The `dotnet` command itself doesn't collect telemetry.</span></span> <span data-ttu-id="ac811-111">`dotnet` 命令运行的 .NET Core CLI 命令收集遥测数据。</span><span class="sxs-lookup"><span data-stu-id="ac811-111">The .NET Core CLI commands run by the `dotnet` command collect the telemetry.</span></span>

<span data-ttu-id="ac811-112">使用 `dotnet` 命令本身且没有附加任何命令时，不会启用遥测：</span><span class="sxs-lookup"><span data-stu-id="ac811-112">Telemetry *isn't enabled* when using the `dotnet` command itself, with no command attached:</span></span>

- `dotnet`
- `dotnet [path-to-app]`

<span data-ttu-id="ac811-113">使用 [.NET Core CLI 命令](index.md)时，就会启用遥测，如：</span><span class="sxs-lookup"><span data-stu-id="ac811-113">Telemetry *is enabled* when using the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

## <a name="how-to-opt-out"></a><span data-ttu-id="ac811-114">如何选择退出</span><span class="sxs-lookup"><span data-stu-id="ac811-114">How to opt out</span></span>

<span data-ttu-id="ac811-115">.NET Core SDK 遥测功能默认处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="ac811-115">The .NET Core SDK telemetry feature is enabled by default.</span></span> <span data-ttu-id="ac811-116">通过将 `DOTNET_CLI_TELEMETRY_OPTOUT` 环境变量设置为 `1` 或 `true`，可以选择退出遥测功能。</span><span class="sxs-lookup"><span data-stu-id="ac811-116">Opt out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

## <a name="data-points"></a><span data-ttu-id="ac811-117">数据点</span><span class="sxs-lookup"><span data-stu-id="ac811-117">Data points</span></span>

<span data-ttu-id="ac811-118">此功能收集以下数据：</span><span class="sxs-lookup"><span data-stu-id="ac811-118">The feature collects the following data:</span></span>

- <span data-ttu-id="ac811-119">调用时间戳&#8224;</span><span class="sxs-lookup"><span data-stu-id="ac811-119">Timestamp of invocation&#8224;</span></span>
- <span data-ttu-id="ac811-120">调用的命令（例如，“build”）&#8224;</span><span class="sxs-lookup"><span data-stu-id="ac811-120">Command invoked (for example, "build")&#8224;</span></span>
- <span data-ttu-id="ac811-121">用于确定地理位置的三个八进制数 IP 地址&#8224;</span><span class="sxs-lookup"><span data-stu-id="ac811-121">Three octet IP address used to determine geographical location&#8224;</span></span>
- <span data-ttu-id="ac811-122">命令的 `ExitCode`</span><span class="sxs-lookup"><span data-stu-id="ac811-122">`ExitCode` of the command</span></span>
- <span data-ttu-id="ac811-123">测试运行程序（对于测试项目）</span><span class="sxs-lookup"><span data-stu-id="ac811-123">Test runner (for test projects)</span></span>
- <span data-ttu-id="ac811-124">操作系统和版本&#8224;</span><span class="sxs-lookup"><span data-stu-id="ac811-124">Operating system and version&#8224;</span></span>
- <span data-ttu-id="ac811-125">“运行时”节点中是否有运行时 ID</span><span class="sxs-lookup"><span data-stu-id="ac811-125">Whether runtime IDs are present in the runtimes node</span></span>
- <span data-ttu-id="ac811-126">.NET Core SDK 版本&#8224;</span><span class="sxs-lookup"><span data-stu-id="ac811-126">.NET Core SDK version&#8224;</span></span>

<span data-ttu-id="ac811-127">&#8224;此指标已发布。</span><span class="sxs-lookup"><span data-stu-id="ac811-127">&#8224;This metric is published.</span></span>

<span data-ttu-id="ac811-128">自 .NET Core SDK 2.0 SDK 起，收集以下新数据点：</span><span class="sxs-lookup"><span data-stu-id="ac811-128">Starting with .NET Core 2.0 SDK, new data points are collected:</span></span>

- <span data-ttu-id="ac811-129">`dotnet` 命令参数和选项：仅收集已知参数和选项（非任意字符串）。</span><span class="sxs-lookup"><span data-stu-id="ac811-129">`dotnet` command arguments and options: only known arguments and options are collected (not arbitrary strings).</span></span>
- <span data-ttu-id="ac811-130">SDK 是否在容器中运行。</span><span class="sxs-lookup"><span data-stu-id="ac811-130">Whether the SDK is running in a container.</span></span>
- <span data-ttu-id="ac811-131">目标框架。</span><span class="sxs-lookup"><span data-stu-id="ac811-131">Target frameworks.</span></span>
- <span data-ttu-id="ac811-132">经过哈希处理的 MAC 地址：计算机的加密 (SHA256) 匿名的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="ac811-132">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> <span data-ttu-id="ac811-133">此指标未发布。</span><span class="sxs-lookup"><span data-stu-id="ac811-133">This metric isn't published.</span></span>
- <span data-ttu-id="ac811-134">经过哈希处理的当前工作目录。</span><span class="sxs-lookup"><span data-stu-id="ac811-134">Hashed current working directory.</span></span>

<span data-ttu-id="ac811-135">此功能不收集用户名或电子邮件地址等个人数据。</span><span class="sxs-lookup"><span data-stu-id="ac811-135">The feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="ac811-136">也不会扫描代码，亦不会提取项目级敏感数据，如名称、存储库或作者。</span><span class="sxs-lookup"><span data-stu-id="ac811-136">It doesn't scan your code and doesn't extract sensitive project-level data, such as name, repo, or author.</span></span> <span data-ttu-id="ac811-137">数据通过 [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) 技术安全地发送到 Microsoft 服务器，提供对保留数据的受限访问权限，并在严格的安全控制下从安全 [Azure 存储](https://azure.microsoft.com/services/storage/)系统发布。</span><span class="sxs-lookup"><span data-stu-id="ac811-137">The data is sent securely to Microsoft servers using [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="ac811-138">.NET 团队需要知道工具使用情况及其是否在正常运行，而不是使用这些工具生成的内容。</span><span class="sxs-lookup"><span data-stu-id="ac811-138">The .NET team wants to know how the tools are used and if they're working well, not what you're building with the tools.</span></span> <span data-ttu-id="ac811-139">如果怀疑遥测在收集敏感数据，或认为我们处理数据的方式不安全或不恰当，请在 [dotnet/cli](https://github.com/dotnet/cli/issues) 存储库中记录问题以供调查。</span><span class="sxs-lookup"><span data-stu-id="ac811-139">If you suspect that the telemetry is collecting sensitive data or that the data is being insecurely or inappropriately handled, file an issue in the [dotnet/cli](https://github.com/dotnet/cli/issues) repository for investigation.</span></span>

## <a name="published-data"></a><span data-ttu-id="ac811-140">已发布的数据</span><span class="sxs-lookup"><span data-stu-id="ac811-140">Published data</span></span>

<span data-ttu-id="ac811-141">数据每季度发布一次，并在 [.NET Core SDK 使用情况数据](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)中列出。</span><span class="sxs-lookup"><span data-stu-id="ac811-141">Published data is available quarterly and are listed at [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span></span> <span data-ttu-id="ac811-142">数据文件列如下：</span><span class="sxs-lookup"><span data-stu-id="ac811-142">The columns of a data file are:</span></span>

- <span data-ttu-id="ac811-143">时间戳</span><span class="sxs-lookup"><span data-stu-id="ac811-143">Timestamp</span></span>
- <span data-ttu-id="ac811-144">Occurrences&#8224;</span><span class="sxs-lookup"><span data-stu-id="ac811-144">Occurrences&#8224;</span></span>
- <span data-ttu-id="ac811-145">命令</span><span class="sxs-lookup"><span data-stu-id="ac811-145">Command</span></span>
- <span data-ttu-id="ac811-146">Geography&#8225;</span><span class="sxs-lookup"><span data-stu-id="ac811-146">Geography&#8225;</span></span>
- <span data-ttu-id="ac811-147">OSFamily</span><span class="sxs-lookup"><span data-stu-id="ac811-147">OSFamily</span></span>
- <span data-ttu-id="ac811-148">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="ac811-148">RuntimeID</span></span>
- <span data-ttu-id="ac811-149">OSVersion</span><span class="sxs-lookup"><span data-stu-id="ac811-149">OSVersion</span></span>
- <span data-ttu-id="ac811-150">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="ac811-150">SDKVersion</span></span>

<span data-ttu-id="ac811-151">&#8224;Occurrences 列显示相应命令当天用于该行指标的总次数。</span><span class="sxs-lookup"><span data-stu-id="ac811-151">&#8224;The *Occurrences* column displays the aggregate count of that command's use for that row's metrics that day.</span></span>

<span data-ttu-id="ac811-152">&#8225;通常情况下，Geography 列显示国家/地区名称。</span><span class="sxs-lookup"><span data-stu-id="ac811-152">&#8225;Typically, the *Geography* column displays the name of a country.</span></span> <span data-ttu-id="ac811-153">在某些情况下，此列中会显示南极洲，要么是因为研究人员在南极洲使用 .NET Core，要么是因为位置数据不正确。</span><span class="sxs-lookup"><span data-stu-id="ac811-153">In some cases, the continent of Antarctica appears in this column, either due to researchers using .NET Core in Antarctica or incorrect location data.</span></span>

### <a name="example"></a><span data-ttu-id="ac811-154">示例</span><span class="sxs-lookup"><span data-stu-id="ac811-154">Example</span></span>

| <span data-ttu-id="ac811-155">时间戳</span><span class="sxs-lookup"><span data-stu-id="ac811-155">Timestamp</span></span>      | <span data-ttu-id="ac811-156">Occurrences</span><span class="sxs-lookup"><span data-stu-id="ac811-156">Occurrences</span></span> | <span data-ttu-id="ac811-157">命令</span><span class="sxs-lookup"><span data-stu-id="ac811-157">Command</span></span> | <span data-ttu-id="ac811-158">Geography</span><span class="sxs-lookup"><span data-stu-id="ac811-158">Geography</span></span> | <span data-ttu-id="ac811-159">OSFamily</span><span class="sxs-lookup"><span data-stu-id="ac811-159">OSFamily</span></span> | <span data-ttu-id="ac811-160">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="ac811-160">RuntimeID</span></span>     | <span data-ttu-id="ac811-161">OSVersion</span><span class="sxs-lookup"><span data-stu-id="ac811-161">OSVersion</span></span> | <span data-ttu-id="ac811-162">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="ac811-162">SDKVersion</span></span> |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| <span data-ttu-id="ac811-163">4/16/2017 0:00</span><span class="sxs-lookup"><span data-stu-id="ac811-163">4/16/2017 0:00</span></span> | <span data-ttu-id="ac811-164">8</span><span class="sxs-lookup"><span data-stu-id="ac811-164">8</span></span>           | <span data-ttu-id="ac811-165">运行</span><span class="sxs-lookup"><span data-stu-id="ac811-165">run</span></span>     | <span data-ttu-id="ac811-166">Uganda</span><span class="sxs-lookup"><span data-stu-id="ac811-166">Uganda</span></span>    | <span data-ttu-id="ac811-167">Darwin</span><span class="sxs-lookup"><span data-stu-id="ac811-167">Darwin</span></span>   | <span data-ttu-id="ac811-168">osx.10.12-x64</span><span class="sxs-lookup"><span data-stu-id="ac811-168">osx.10.12-x64</span></span> | <span data-ttu-id="ac811-169">10.12</span><span class="sxs-lookup"><span data-stu-id="ac811-169">10.12</span></span>     | <span data-ttu-id="ac811-170">1.0.1</span><span class="sxs-lookup"><span data-stu-id="ac811-170">1.0.1</span></span>      |

### <a name="datasets"></a><span data-ttu-id="ac811-171">数据集</span><span class="sxs-lookup"><span data-stu-id="ac811-171">Datasets</span></span>

[<span data-ttu-id="ac811-172">2016 - Q3</span><span class="sxs-lookup"><span data-stu-id="ac811-172">2016 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)  
[<span data-ttu-id="ac811-173">2016 - Q4</span><span class="sxs-lookup"><span data-stu-id="ac811-173">2016 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)  
[<span data-ttu-id="ac811-174">2017 - Q1</span><span class="sxs-lookup"><span data-stu-id="ac811-174">2017 - Q1</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)  
[<span data-ttu-id="ac811-175">2017 - Q2</span><span class="sxs-lookup"><span data-stu-id="ac811-175">2017 - Q2</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)  
[<span data-ttu-id="ac811-176">2017 - Q3</span><span class="sxs-lookup"><span data-stu-id="ac811-176">2017 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q3.tsv)  
[<span data-ttu-id="ac811-177">2017 - Q4</span><span class="sxs-lookup"><span data-stu-id="ac811-177">2017 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q4.tsv)  

<span data-ttu-id="ac811-178">其他数据集使用标准的 URL 格式进行发布。</span><span class="sxs-lookup"><span data-stu-id="ac811-178">Additional datasets are posted using a standard URL format.</span></span> <span data-ttu-id="ac811-179">请将 `<YEAR>` 替换为相应年份，并将 `<QUARTER>` 替换为相应季度（使用 `1`、`2`、`3` 或 `4`）。</span><span class="sxs-lookup"><span data-stu-id="ac811-179">Replace `<YEAR>` with the year and replace `<QUARTER>` with the quarter of the year (use `1`, `2`, `3`, or `4`).</span></span> <span data-ttu-id="ac811-180">文件采用制表符分隔值 (TSV) 格式。</span><span class="sxs-lookup"><span data-stu-id="ac811-180">The files are in tab-separated values (*TSV*) format.</span></span>

`https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv`

## <a name="license"></a><span data-ttu-id="ac811-181">许可证</span><span class="sxs-lookup"><span data-stu-id="ac811-181">License</span></span>

<span data-ttu-id="ac811-182">.NET Core 的 Microsoft 分发由 [MICROSOFT .NET LIBRARY EULA](https://aka.ms/dotnet-core-eula) 授权。</span><span class="sxs-lookup"><span data-stu-id="ac811-182">The Microsoft distribution of .NET Core is licensed with the [MICROSOFT .NET LIBRARY EULA](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="ac811-183">此许可证包括“DATA”部分，用于启用遥测（如下所示）。</span><span class="sxs-lookup"><span data-stu-id="ac811-183">This license includes the "DATA" section to enable telemetry (shown below).</span></span>

<span data-ttu-id="ac811-184">[.NET NuGet 包](https://www.nuget.org/profiles/dotnetframework)使用相同许可证，但不启用遥测（见[范围](#scope)）。</span><span class="sxs-lookup"><span data-stu-id="ac811-184">[.NET NuGet packages](https://www.nuget.org/profiles/dotnetframework) use the same license but don't enable telemetry (see [Scope](#scope)).</span></span>

> 2. <span data-ttu-id="ac811-185">DATA。</span><span class="sxs-lookup"><span data-stu-id="ac811-185">DATA.</span></span> <span data-ttu-id="ac811-186">此软件可能会收集并向 Microsoft 发送你的信息和软件使用信息。</span><span class="sxs-lookup"><span data-stu-id="ac811-186">The software may collect information about you and your use of the software, and send that to Microsoft.</span></span> <span data-ttu-id="ac811-187">Microsoft 可能会使用此类信息来改进我们的产品和服务。</span><span class="sxs-lookup"><span data-stu-id="ac811-187">Microsoft may use this information to improve our products and services.</span></span> <span data-ttu-id="ac811-188">可以参阅帮助文档和隐私声明 <http://go.microsoft.com/fwlink/?LinkId=528096> ，详细了解数据收集和使用。</span><span class="sxs-lookup"><span data-stu-id="ac811-188">You can learn more about data collection and use in the help documentation and the privacy statement at <http://go.microsoft.com/fwlink/?LinkId=528096>.</span></span> <span data-ttu-id="ac811-189">使用此软件即表示同意接受这些做法。</span><span class="sxs-lookup"><span data-stu-id="ac811-189">Your use of the software operates as your consent to these practices.</span></span>

## <a name="disclosure"></a><span data-ttu-id="ac811-190">公开</span><span class="sxs-lookup"><span data-stu-id="ac811-190">Disclosure</span></span>

<span data-ttu-id="ac811-191">首次运行其中一个 [.NET Core CLI 命令](index.md)（例如，`dotnet restore`）时，.NET Core SDK 工具显示以下文本。</span><span class="sxs-lookup"><span data-stu-id="ac811-191">The .NET Core SDK displays the following text when you first run one of the [.NET Core CLI commands](index.md) (for example, `dotnet restore`).</span></span> <span data-ttu-id="ac811-192">文本可能会因运行的 SDK 版本而略有不同。</span><span class="sxs-lookup"><span data-stu-id="ac811-192">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="ac811-193">此“首次运行”体验是 Microsoft 通知用户有关数据收集信息的方式。</span><span class="sxs-lookup"><span data-stu-id="ac811-193">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core: https://aka.ms/dotnet-docs
Use 'dotnet --help' to see available commands or visit: https://aka.ms/dotnet-cli-docs

Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience.
The data is anonymous and doesn't include command-line arguments.
The data is collected by Microsoft and shared with the community.
You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

## <a name="see-also"></a><span data-ttu-id="ac811-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac811-194">See also</span></span>

- [<span data-ttu-id="ac811-195">从 .NET Core SDK 遥测中所了解到的内容</span><span class="sxs-lookup"><span data-stu-id="ac811-195">What we've learned from .NET Core SDK Telemetry</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/)
- [<span data-ttu-id="ac811-196">遥测参考源（dotnet/cli 存储库）</span><span class="sxs-lookup"><span data-stu-id="ac811-196">Telemetry reference source (dotnet/cli repo)</span></span>](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)
- [<span data-ttu-id="ac811-197">.NET Core SDK 使用情况数据</span><span class="sxs-lookup"><span data-stu-id="ac811-197">.NET Core SDK Usage Data</span></span>](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)
