---
title: ".NET Core 工具遥测"
description: "了解可收集使用情况信息以供分析使用的 .NET Core 工具遥测功能。"
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 480df976-7568-4df4-9d26-9911357b5a31
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1816b9fbad1f671820c9f970674c8af2147a230e
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="net-core-tools-telemetry"></a><span data-ttu-id="0361c-104">.NET Core 工具遥测</span><span class="sxs-lookup"><span data-stu-id="0361c-104">.NET Core Tools Telemetry</span></span>

<span data-ttu-id="0361c-105">.NET Core 工具包括可收集使用情况信息的[遥测功能](https://github.com/dotnet/cli/pull/2145)。</span><span class="sxs-lookup"><span data-stu-id="0361c-105">The .NET Core Tools include a [telemetry feature](https://github.com/dotnet/cli/pull/2145) that collects usage information.</span></span> <span data-ttu-id="0361c-106">让 .NET 团队了解工具的使用情况非常重要，我们可由此对其做出改进。</span><span class="sxs-lookup"><span data-stu-id="0361c-106">It’s important that the .NET Team understands how the tools are being used so that we can improve them.</span></span>

<span data-ttu-id="0361c-107">收集的数据是匿名的，并以聚合形式发布，供 Microsoft 和社区工程师在 [Creative Commons Attribution 许可证](https://creativecommons.org/licenses/by/4.0/)下使用。</span><span class="sxs-lookup"><span data-stu-id="0361c-107">The data collected is anonymous and will be published in an aggregated form for use by both Microsoft and community engineers under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="0361c-108">范围</span><span class="sxs-lookup"><span data-stu-id="0361c-108">Scope</span></span>

<span data-ttu-id="0361c-109">`dotnet` 命令用于启动应用和 .NET Core 工具。</span><span class="sxs-lookup"><span data-stu-id="0361c-109">The `dotnet` command is used to launch both apps and the .NET Core Tools.</span></span> <span data-ttu-id="0361c-110">`dotnet` 命令本身不会收集遥测数据。</span><span class="sxs-lookup"><span data-stu-id="0361c-110">The `dotnet` command itself does not collect telemetry.</span></span> <span data-ttu-id="0361c-111">而是通过 `dotnet` 命令运行的 .NET Core 工具收集遥测数据。</span><span class="sxs-lookup"><span data-stu-id="0361c-111">It is the .NET Core Tools that are run via the `dotnet` command that collect telemetry.</span></span>

<span data-ttu-id="0361c-112">.NET Core 命令（未启用遥测）：</span><span class="sxs-lookup"><span data-stu-id="0361c-112">.NET Core commands (telemetry is not enabled):</span></span>

- `dotnet`
- `dotnet [path-to-app]`

<span data-ttu-id="0361c-113">.NET Core 工具[命令](index.md)（已启用遥测），如：</span><span class="sxs-lookup"><span data-stu-id="0361c-113">.NET Core Tools [commands](index.md) (telemetry is enabled), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

## <a name="behavior"></a><span data-ttu-id="0361c-114">行为</span><span class="sxs-lookup"><span data-stu-id="0361c-114">Behavior</span></span>

<span data-ttu-id="0361c-115">默认启用 .NET Core 工具遥测功能。</span><span class="sxs-lookup"><span data-stu-id="0361c-115">The .NET Core Tools telemetry feature is enabled by default.</span></span> <span data-ttu-id="0361c-116">可通过将环境变量 DOTNET_CLI_TELEMETRY_OPTOUT（例如，macOS/Linux 上的 `export`，Windows 上的 `set`）设置为 true（例如“true”, 1），选择退出遥测功能。</span><span class="sxs-lookup"><span data-stu-id="0361c-116">You can opt-out of the telemetry feature by setting an environment variable DOTNET_CLI_TELEMETRY_OPTOUT (for example, `export` on macOS/Linux, `set` on Windows) to true (for example, "true", 1).</span></span>

## <a name="data-points"></a><span data-ttu-id="0361c-117">数据点</span><span class="sxs-lookup"><span data-stu-id="0361c-117">Data Points</span></span>

<span data-ttu-id="0361c-118">该功能收集以下数据块：</span><span class="sxs-lookup"><span data-stu-id="0361c-118">The feature collects the following pieces of data:</span></span>

- <span data-ttu-id="0361c-119">正在使用的命令（例如，“生成”、“还原”）</span><span class="sxs-lookup"><span data-stu-id="0361c-119">The command being used (for example, "build", "restore")</span></span>
- <span data-ttu-id="0361c-120">命令的 ExitCode</span><span class="sxs-lookup"><span data-stu-id="0361c-120">The ExitCode of the command</span></span>
- <span data-ttu-id="0361c-121">对于测试项目，正在使用的测试运行程序</span><span class="sxs-lookup"><span data-stu-id="0361c-121">For test projects, the test runner being used</span></span>
- <span data-ttu-id="0361c-122">调用的时间戳</span><span class="sxs-lookup"><span data-stu-id="0361c-122">The timestamp of invocation</span></span>
- <span data-ttu-id="0361c-123">使用的框架</span><span class="sxs-lookup"><span data-stu-id="0361c-123">The framework used</span></span>
- <span data-ttu-id="0361c-124">“运行时”节点中是否存在运行时 ID</span><span class="sxs-lookup"><span data-stu-id="0361c-124">Whether runtime IDs are present in the "runtimes" node</span></span>
- <span data-ttu-id="0361c-125">正在使用的 CLI 版本</span><span class="sxs-lookup"><span data-stu-id="0361c-125">The CLI version being used</span></span>

<span data-ttu-id="0361c-126">该功能不会收集任何个人数据，如用户名或电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0361c-126">The feature will not collect any personal data, such as usernames or emails.</span></span> <span data-ttu-id="0361c-127">它不会扫描代码，也不会提取被视为敏感信息的项目级别数据，例如名称、存储库或作者（如果在 project.json 中进行了这些设置）。</span><span class="sxs-lookup"><span data-stu-id="0361c-127">It will not scan your code and not extract any project-level data that can be considered sensitive, such as name, repo or author (if you set those in your project.json).</span></span> <span data-ttu-id="0361c-128">我们想知道这些工具的使用方式，而不是用户通过这些工具构建的内容。</span><span class="sxs-lookup"><span data-stu-id="0361c-128">We want to know how the tools are used, not what you are building with the tools.</span></span> <span data-ttu-id="0361c-129">如果发现正在收集敏感数据，则那是一个 bug。</span><span class="sxs-lookup"><span data-stu-id="0361c-129">If you find sensitive data being collected, that’s a bug.</span></span> <span data-ttu-id="0361c-130">请[提出问题](https://github.com/dotnet/cli/issues)，此问题将会得到解决。</span><span class="sxs-lookup"><span data-stu-id="0361c-130">Please [file an issue](https://github.com/dotnet/cli/issues) and it will be fixed.</span></span>

## <a name="license"></a><span data-ttu-id="0361c-131">许可证</span><span class="sxs-lookup"><span data-stu-id="0361c-131">License</span></span>

<span data-ttu-id="0361c-132">.NET Core 的 Microsoft 分发由 [MICROSOFT .NET LIBRARY EULA](https://aka.ms/dotnet-core-eula) 授权。</span><span class="sxs-lookup"><span data-stu-id="0361c-132">The Microsoft distribution of .NET Core is licensed with the [MICROSOFT .NET LIBRARY EULA](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="0361c-133">这包括以下重新打印的“DATA”部分，用于启用遥测。</span><span class="sxs-lookup"><span data-stu-id="0361c-133">This includes the "DATA" section re-printed below, to enable telemetry.</span></span>

<span data-ttu-id="0361c-134">[.NET NuGet 包](https://www.nuget.org/profiles/dotnetframework)使用此相同的许可证，但不启用遥测（请参阅上方的[范围](#scope)）。</span><span class="sxs-lookup"><span data-stu-id="0361c-134">[.NET NuGet packages](https://www.nuget.org/profiles/dotnetframework) use this same license but do not enable telemetry (see [Scope](#scope) above).</span></span>

> 2. <span data-ttu-id="0361c-135">DATA。</span><span class="sxs-lookup"><span data-stu-id="0361c-135">DATA.</span></span> <span data-ttu-id="0361c-136">此软件可能会收集并向 Microsoft 发送你的信息和软件使用信息。</span><span class="sxs-lookup"><span data-stu-id="0361c-136">The software may collect information about you and your use of the software, and send that to Microsoft.</span></span> <span data-ttu-id="0361c-137">Microsoft 可能会使用此类信息来改进我们的产品和服务。</span><span class="sxs-lookup"><span data-stu-id="0361c-137">Microsoft may use this information to improve our products and services.</span></span> <span data-ttu-id="0361c-138">可以参阅帮助文档和隐私声明 (http://go.microsoft.com/fwlink/?LinkId=528096)，详细了解数据收集和使用。</span><span class="sxs-lookup"><span data-stu-id="0361c-138">You can learn more about data collection and use in the help documentation and the privacy statement at http://go.microsoft.com/fwlink/?LinkId=528096.</span></span> <span data-ttu-id="0361c-139">使用此软件即表示同意接受这些做法。</span><span class="sxs-lookup"><span data-stu-id="0361c-139">Your use of the software operates as your consent to these practices.</span></span>

## <a name="disclosure"></a><span data-ttu-id="0361c-140">公开</span><span class="sxs-lookup"><span data-stu-id="0361c-140">Disclosure</span></span>

<span data-ttu-id="0361c-141">首次运行其中一个命令（例如 `dotnet restore`）时，.NET Core 工具显示以下文本。</span><span class="sxs-lookup"><span data-stu-id="0361c-141">The .NET Core Tools display the following text when you first run one of the commands (for example, `dotnet restore`).</span></span> <span data-ttu-id="0361c-142">此“首次运行”体验是 Microsoft 通知用户有关数据收集信息的方式。</span><span class="sxs-lookup"><span data-stu-id="0361c-142">This "first run" experience is how Microsoft notifies you about data collection.</span></span> <span data-ttu-id="0361c-143">此相同体验最初也使用 .NET Core SDK 中的库填充 NuGet 缓存，从而避免针对这些库的对 NuGet.org（或其他 NuGet 源）的请求。</span><span class="sxs-lookup"><span data-stu-id="0361c-143">This same experience also initially populates your NuGet cache with the libraries in the .NET Core SDK, avoiding requests to NuGet.org (or other NuGet feed) for these libraries.</span></span>

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core @ https://aka.ms/dotnet-docs. Use dotnet --help to see available commands or go to https://aka.ms/dotnet-cli-docs.

Telemetry
--------------
The .NET Core tools collect usage data in order to improve your experience.
The data is anonymous and does not include command-line arguments. The data is collected by Microsoft and shared with the community.
You can opt out of telemetry by setting a DOTNET_CLI_TELEMETRY_OPTOUT environment variable to 1 using your favorite shell.
You can read more about .NET Core tools telemetry @ https://aka.ms/dotnet-cli-telemetry.

Configuring...
-------------------
A command is running to initially populate your local package cache, to improve restore speed and enable offline access. This command will take up to a minute to complete and will only happen once.
```

