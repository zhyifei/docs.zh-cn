---
title: .NET Core SDK 遥测
description: 了解可收集使用情况信息以供分析的 .NET Core SDK 遥测功能、收集哪些数据，以及如何禁用遥测。
author: richlander
ms.date: 06/20/2018
ms.custom: seodec18
ms.openlocfilehash: 82410863c81faa95edfb120c95ec6bc186ed1328
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751673"
---
# <a name="net-core-sdk-telemetry"></a><span data-ttu-id="5d8af-103">.NET Core SDK 遥测</span><span class="sxs-lookup"><span data-stu-id="5d8af-103">.NET Core SDK telemetry</span></span>

<span data-ttu-id="5d8af-104">[.NET Core SDK](index.md) 包括可收集使用情况信息的[遥测功能](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)。</span><span class="sxs-lookup"><span data-stu-id="5d8af-104">The [.NET Core SDK](index.md) includes a [telemetry feature](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry) that collects usage information.</span></span> <span data-ttu-id="5d8af-105">请务必让 .NET 团队了解到工具使用情况，以便我们对其做出改进。</span><span class="sxs-lookup"><span data-stu-id="5d8af-105">It's important that the .NET Team understands how the tools are used so they can be improved.</span></span> <span data-ttu-id="5d8af-106">有关详细信息，请参阅[从 .NET Core SDK 遥测中所了解到的内容](https://devblogs.microsoft.com/dotnet/what-weve-learned-from-net-core-sdk-telemetry/)。</span><span class="sxs-lookup"><span data-stu-id="5d8af-106">For more information, see [What we've learned from .NET Core SDK Telemetry](https://devblogs.microsoft.com/dotnet/what-weve-learned-from-net-core-sdk-telemetry/).</span></span>

<span data-ttu-id="5d8af-107">数据为匿名收集，并以汇总形式发布，以供 Microsoft 和社区根据 [Creative Commons Attribution 许可证](https://creativecommons.org/licenses/by/4.0/)使用。</span><span class="sxs-lookup"><span data-stu-id="5d8af-107">The collected data is anonymous and published in an aggregated form for use by both Microsoft and the community under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="5d8af-108">范围</span><span class="sxs-lookup"><span data-stu-id="5d8af-108">Scope</span></span>

<span data-ttu-id="5d8af-109">`dotnet` 命令用于启动应用程序和 .NET Core CLI。</span><span class="sxs-lookup"><span data-stu-id="5d8af-109">The `dotnet` command is used to launch both apps and the .NET Core CLI.</span></span> <span data-ttu-id="5d8af-110">`dotnet` 命令本身不收集遥测数据。</span><span class="sxs-lookup"><span data-stu-id="5d8af-110">The `dotnet` command itself doesn't collect telemetry.</span></span> <span data-ttu-id="5d8af-111">`dotnet` 命令运行的 .NET Core CLI 命令收集遥测数据。</span><span class="sxs-lookup"><span data-stu-id="5d8af-111">The .NET Core CLI commands run by the `dotnet` command collect the telemetry.</span></span>

<span data-ttu-id="5d8af-112">使用 `dotnet` 命令本身且没有附加任何命令时，不会启用遥测：</span><span class="sxs-lookup"><span data-stu-id="5d8af-112">Telemetry *isn't enabled* when using the `dotnet` command itself, with no command attached:</span></span>

- `dotnet`
- `dotnet [path-to-app]`

<span data-ttu-id="5d8af-113">使用 [.NET Core CLI 命令](index.md)时，就会启用遥测，如：</span><span class="sxs-lookup"><span data-stu-id="5d8af-113">Telemetry *is enabled* when using the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

## <a name="how-to-opt-out"></a><span data-ttu-id="5d8af-114">如何选择退出</span><span class="sxs-lookup"><span data-stu-id="5d8af-114">How to opt out</span></span>

<span data-ttu-id="5d8af-115">.NET Core SDK 遥测功能默认处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="5d8af-115">The .NET Core SDK telemetry feature is enabled by default.</span></span> <span data-ttu-id="5d8af-116">通过将 `DOTNET_CLI_TELEMETRY_OPTOUT` 环境变量设置为 `1` 或 `true`，可以选择退出遥测功能。</span><span class="sxs-lookup"><span data-stu-id="5d8af-116">Opt out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

## <a name="data-points"></a><span data-ttu-id="5d8af-117">数据点</span><span class="sxs-lookup"><span data-stu-id="5d8af-117">Data points</span></span>

<span data-ttu-id="5d8af-118">此功能收集以下数据：</span><span class="sxs-lookup"><span data-stu-id="5d8af-118">The feature collects the following data:</span></span>

- <span data-ttu-id="5d8af-119">调用时间戳&#8224;</span><span class="sxs-lookup"><span data-stu-id="5d8af-119">Timestamp of invocation&#8224;</span></span>
- <span data-ttu-id="5d8af-120">调用的命令（例如，“build”）&#8224;</span><span class="sxs-lookup"><span data-stu-id="5d8af-120">Command invoked (for example, "build")&#8224;</span></span>
- <span data-ttu-id="5d8af-121">用于确定地理位置的三个八进制数 IP 地址&#8224;</span><span class="sxs-lookup"><span data-stu-id="5d8af-121">Three octet IP address used to determine geographical location&#8224;</span></span>
- <span data-ttu-id="5d8af-122">命令的 `ExitCode`</span><span class="sxs-lookup"><span data-stu-id="5d8af-122">`ExitCode` of the command</span></span>
- <span data-ttu-id="5d8af-123">测试运行程序（对于测试项目）</span><span class="sxs-lookup"><span data-stu-id="5d8af-123">Test runner (for test projects)</span></span>
- <span data-ttu-id="5d8af-124">操作系统和版本&#8224;</span><span class="sxs-lookup"><span data-stu-id="5d8af-124">Operating system and version&#8224;</span></span>
- <span data-ttu-id="5d8af-125">“运行时”节点中是否有运行时 ID</span><span class="sxs-lookup"><span data-stu-id="5d8af-125">Whether runtime IDs are present in the runtimes node</span></span>
- <span data-ttu-id="5d8af-126">.NET Core SDK 版本&#8224;</span><span class="sxs-lookup"><span data-stu-id="5d8af-126">.NET Core SDK version&#8224;</span></span>

<span data-ttu-id="5d8af-127">&#8224;此指标已发布。</span><span class="sxs-lookup"><span data-stu-id="5d8af-127">&#8224;This metric is published.</span></span>

<span data-ttu-id="5d8af-128">自 .NET Core SDK 2.0 SDK 起，收集以下新数据点：</span><span class="sxs-lookup"><span data-stu-id="5d8af-128">Starting with .NET Core 2.0 SDK, new data points are collected:</span></span>

- <span data-ttu-id="5d8af-129">`dotnet` 命令参数和选项：仅收集已知参数和选项（非任意字符串）。</span><span class="sxs-lookup"><span data-stu-id="5d8af-129">`dotnet` command arguments and options: only known arguments and options are collected (not arbitrary strings).</span></span>
- <span data-ttu-id="5d8af-130">SDK 是否在容器中运行。</span><span class="sxs-lookup"><span data-stu-id="5d8af-130">Whether the SDK is running in a container.</span></span>
- <span data-ttu-id="5d8af-131">目标框架。</span><span class="sxs-lookup"><span data-stu-id="5d8af-131">Target frameworks.</span></span>
- <span data-ttu-id="5d8af-132">经过哈希处理的 MAC 地址：计算机的加密 (SHA256) 匿名的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="5d8af-132">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> <span data-ttu-id="5d8af-133">此指标未发布。</span><span class="sxs-lookup"><span data-stu-id="5d8af-133">This metric isn't published.</span></span>
- <span data-ttu-id="5d8af-134">经过哈希处理的当前工作目录。</span><span class="sxs-lookup"><span data-stu-id="5d8af-134">Hashed current working directory.</span></span>

<span data-ttu-id="5d8af-135">此功能不收集用户名或电子邮件地址等个人数据。</span><span class="sxs-lookup"><span data-stu-id="5d8af-135">The feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="5d8af-136">也不会扫描代码，亦不会提取项目级敏感数据，如名称、存储库或作者。</span><span class="sxs-lookup"><span data-stu-id="5d8af-136">It doesn't scan your code and doesn't extract sensitive project-level data, such as name, repo, or author.</span></span> <span data-ttu-id="5d8af-137">数据通过 [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) 技术安全地发送到 Microsoft 服务器，提供对保留数据的受限访问权限，并在严格的安全控制下从安全 [Azure 存储](https://azure.microsoft.com/services/storage/)系统发布。</span><span class="sxs-lookup"><span data-stu-id="5d8af-137">The data is sent securely to Microsoft servers using [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="5d8af-138">.NET 团队需要知道工具使用情况及其是否在正常运行，而不是使用这些工具生成的内容。</span><span class="sxs-lookup"><span data-stu-id="5d8af-138">The .NET team wants to know how the tools are used and if they're working well, not what you're building with the tools.</span></span> <span data-ttu-id="5d8af-139">如果怀疑遥测在收集敏感数据，或认为我们处理数据的方式不安全或不恰当，请在 [dotnet/cli](https://github.com/dotnet/cli/issues) 存储库中记录问题以供调查。</span><span class="sxs-lookup"><span data-stu-id="5d8af-139">If you suspect that the telemetry is collecting sensitive data or that the data is being insecurely or inappropriately handled, file an issue in the [dotnet/cli](https://github.com/dotnet/cli/issues) repository for investigation.</span></span>

## <a name="published-data"></a><span data-ttu-id="5d8af-140">已发布的数据</span><span class="sxs-lookup"><span data-stu-id="5d8af-140">Published data</span></span>

<span data-ttu-id="5d8af-141">数据每季度发布一次，并在 [.NET Core SDK 使用情况数据](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)中列出。</span><span class="sxs-lookup"><span data-stu-id="5d8af-141">Published data is available quarterly and are listed at [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span></span> <span data-ttu-id="5d8af-142">数据文件列如下：</span><span class="sxs-lookup"><span data-stu-id="5d8af-142">The columns of a data file are:</span></span>

- <span data-ttu-id="5d8af-143">时间戳</span><span class="sxs-lookup"><span data-stu-id="5d8af-143">Timestamp</span></span>
- <span data-ttu-id="5d8af-144">Occurrences&#8224;</span><span class="sxs-lookup"><span data-stu-id="5d8af-144">Occurrences&#8224;</span></span>
- <span data-ttu-id="5d8af-145">命令</span><span class="sxs-lookup"><span data-stu-id="5d8af-145">Command</span></span>
- <span data-ttu-id="5d8af-146">Geography&#8225;</span><span class="sxs-lookup"><span data-stu-id="5d8af-146">Geography&#8225;</span></span>
- <span data-ttu-id="5d8af-147">OSFamily</span><span class="sxs-lookup"><span data-stu-id="5d8af-147">OSFamily</span></span>
- <span data-ttu-id="5d8af-148">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="5d8af-148">RuntimeID</span></span>
- <span data-ttu-id="5d8af-149">OSVersion</span><span class="sxs-lookup"><span data-stu-id="5d8af-149">OSVersion</span></span>
- <span data-ttu-id="5d8af-150">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="5d8af-150">SDKVersion</span></span>

<span data-ttu-id="5d8af-151">&#8224;Occurrences 列显示相应命令当天用于该行指标的总次数。</span><span class="sxs-lookup"><span data-stu-id="5d8af-151">&#8224;The *Occurrences* column displays the aggregate count of that command's use for that row's metrics that day.</span></span>

<span data-ttu-id="5d8af-152">&#8225;通常情况下，Geography 列显示国家/地区名称。</span><span class="sxs-lookup"><span data-stu-id="5d8af-152">&#8225;Typically, the *Geography* column displays the name of a country.</span></span> <span data-ttu-id="5d8af-153">在某些情况下，此列中会显示南极洲，要么是因为研究人员在南极洲使用 .NET Core，要么是因为位置数据不正确。</span><span class="sxs-lookup"><span data-stu-id="5d8af-153">In some cases, the continent of Antarctica appears in this column, either due to researchers using .NET Core in Antarctica or incorrect location data.</span></span>

### <a name="example"></a><span data-ttu-id="5d8af-154">示例</span><span class="sxs-lookup"><span data-stu-id="5d8af-154">Example</span></span>

| <span data-ttu-id="5d8af-155">时间戳</span><span class="sxs-lookup"><span data-stu-id="5d8af-155">Timestamp</span></span>      | <span data-ttu-id="5d8af-156">Occurrences</span><span class="sxs-lookup"><span data-stu-id="5d8af-156">Occurrences</span></span> | <span data-ttu-id="5d8af-157">命令</span><span class="sxs-lookup"><span data-stu-id="5d8af-157">Command</span></span> | <span data-ttu-id="5d8af-158">Geography</span><span class="sxs-lookup"><span data-stu-id="5d8af-158">Geography</span></span> | <span data-ttu-id="5d8af-159">OSFamily</span><span class="sxs-lookup"><span data-stu-id="5d8af-159">OSFamily</span></span> | <span data-ttu-id="5d8af-160">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="5d8af-160">RuntimeID</span></span>     | <span data-ttu-id="5d8af-161">OSVersion</span><span class="sxs-lookup"><span data-stu-id="5d8af-161">OSVersion</span></span> | <span data-ttu-id="5d8af-162">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="5d8af-162">SDKVersion</span></span> |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| <span data-ttu-id="5d8af-163">4/16/2017 0:00</span><span class="sxs-lookup"><span data-stu-id="5d8af-163">4/16/2017 0:00</span></span> | <span data-ttu-id="5d8af-164">8</span><span class="sxs-lookup"><span data-stu-id="5d8af-164">8</span></span>           | <span data-ttu-id="5d8af-165">运行</span><span class="sxs-lookup"><span data-stu-id="5d8af-165">run</span></span>     | <span data-ttu-id="5d8af-166">Uganda</span><span class="sxs-lookup"><span data-stu-id="5d8af-166">Uganda</span></span>    | <span data-ttu-id="5d8af-167">Darwin</span><span class="sxs-lookup"><span data-stu-id="5d8af-167">Darwin</span></span>   | <span data-ttu-id="5d8af-168">osx.10.12-x64</span><span class="sxs-lookup"><span data-stu-id="5d8af-168">osx.10.12-x64</span></span> | <span data-ttu-id="5d8af-169">10.12</span><span class="sxs-lookup"><span data-stu-id="5d8af-169">10.12</span></span>     | <span data-ttu-id="5d8af-170">1.0.1</span><span class="sxs-lookup"><span data-stu-id="5d8af-170">1.0.1</span></span>      |

### <a name="datasets"></a><span data-ttu-id="5d8af-171">数据集</span><span class="sxs-lookup"><span data-stu-id="5d8af-171">Datasets</span></span>

- [<span data-ttu-id="5d8af-172">2016 - Q3</span><span class="sxs-lookup"><span data-stu-id="5d8af-172">2016 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)
- [<span data-ttu-id="5d8af-173">2016 - Q4</span><span class="sxs-lookup"><span data-stu-id="5d8af-173">2016 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)
- [<span data-ttu-id="5d8af-174">2017 - Q1</span><span class="sxs-lookup"><span data-stu-id="5d8af-174">2017 - Q1</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)
- [<span data-ttu-id="5d8af-175">2017 - Q2</span><span class="sxs-lookup"><span data-stu-id="5d8af-175">2017 - Q2</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)
- [<span data-ttu-id="5d8af-176">2017 - Q3</span><span class="sxs-lookup"><span data-stu-id="5d8af-176">2017 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q3.tsv)
- [<span data-ttu-id="5d8af-177">2017 - Q4</span><span class="sxs-lookup"><span data-stu-id="5d8af-177">2017 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q4.tsv)

<span data-ttu-id="5d8af-178">其他数据集使用标准的 URL 格式进行发布。</span><span class="sxs-lookup"><span data-stu-id="5d8af-178">Additional datasets are posted using a standard URL format.</span></span> <span data-ttu-id="5d8af-179">请将 `<YEAR>` 替换为相应年份，并将 `<QUARTER>` 替换为相应季度（使用 `1`、`2`、`3` 或 `4`）。</span><span class="sxs-lookup"><span data-stu-id="5d8af-179">Replace `<YEAR>` with the year and replace `<QUARTER>` with the quarter of the year (use `1`, `2`, `3`, or `4`).</span></span> <span data-ttu-id="5d8af-180">文件采用制表符分隔值 (TSV) 格式。</span><span class="sxs-lookup"><span data-stu-id="5d8af-180">The files are in tab-separated values (*TSV*) format.</span></span>

`https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv`

## <a name="license"></a><span data-ttu-id="5d8af-181">许可证</span><span class="sxs-lookup"><span data-stu-id="5d8af-181">License</span></span>

<span data-ttu-id="5d8af-182">.NET Core 的 Microsoft 分发由 [Microsoft 软件许可条款：Mirosoft .NET 库](https://aka.ms/dotnet-core-eula)授权。</span><span class="sxs-lookup"><span data-stu-id="5d8af-182">The Microsoft distribution of .NET Core is licensed with the [Microsoft Software License Terms: Mirosoft .NET Library](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="5d8af-183">有关数据收集和处理的详细信息，请参阅标题为“数据”的部分。</span><span class="sxs-lookup"><span data-stu-id="5d8af-183">For details on data collection and processing, see the section entitled "Data."</span></span>

<span data-ttu-id="5d8af-184">[.NET NuGet 包](https://www.nuget.org/profiles/dotnetframework)使用相同许可证，但不启用遥测（见[范围](#scope)）。</span><span class="sxs-lookup"><span data-stu-id="5d8af-184">[.NET NuGet packages](https://www.nuget.org/profiles/dotnetframework) use the same license but don't enable telemetry (see [Scope](#scope)).</span></span>

## <a name="disclosure"></a><span data-ttu-id="5d8af-185">公开</span><span class="sxs-lookup"><span data-stu-id="5d8af-185">Disclosure</span></span>

<span data-ttu-id="5d8af-186">首次运行其中一个 [.NET Core CLI 命令](index.md)（例如，`dotnet restore`）时，.NET Core SDK 工具显示以下文本。</span><span class="sxs-lookup"><span data-stu-id="5d8af-186">The .NET Core SDK displays the following text when you first run one of the [.NET Core CLI commands](index.md) (for example, `dotnet restore`).</span></span> <span data-ttu-id="5d8af-187">文本可能会因运行的 SDK 版本而略有不同。</span><span class="sxs-lookup"><span data-stu-id="5d8af-187">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="5d8af-188">此“首次运行”体验是 Microsoft 通知用户有关数据收集信息的方式。</span><span class="sxs-lookup"><span data-stu-id="5d8af-188">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5d8af-189">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d8af-189">See also</span></span>

- [<span data-ttu-id="5d8af-190">从 .NET Core SDK 遥测中所了解到的内容</span><span class="sxs-lookup"><span data-stu-id="5d8af-190">What we've learned from .NET Core SDK Telemetry</span></span>](https://devblogs.microsoft.com/dotnet/what-weve-learned-from-net-core-sdk-telemetry/)
- [<span data-ttu-id="5d8af-191">遥测参考源（dotnet/cli 存储库）</span><span class="sxs-lookup"><span data-stu-id="5d8af-191">Telemetry reference source (dotnet/cli repo)</span></span>](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)
- [<span data-ttu-id="5d8af-192">.NET Core SDK 使用情况数据</span><span class="sxs-lookup"><span data-stu-id="5d8af-192">.NET Core SDK Usage Data</span></span>](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)
