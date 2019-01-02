---
title: .NET Core 全局工具
description: 概述：介绍 .NET Core 全局工具及其适用的 .NET Core CLI 命令。
author: KathleenDollard
ms.date: 05/29/2018
ms.custom: seodec18
ms.openlocfilehash: 3bbf1e7953482dc07f05570443cf640a9fab6258
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170831"
---
# <a name="net-core-global-tools-overview"></a><span data-ttu-id="ec579-103">.NET Core 全局工具概述</span><span class="sxs-lookup"><span data-stu-id="ec579-103">.NET Core Global Tools overview</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

<span data-ttu-id="ec579-104">.NET Core 全局工具是一种特殊的 NuGet 包，其中包含控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="ec579-104">A .NET Core Global Tool is a special NuGet package that contains a console application.</span></span> <span data-ttu-id="ec579-105">全局工具可安装在计算机上的默认位置（包含在 PATH 环境变量中）或自定义位置。</span><span class="sxs-lookup"><span data-stu-id="ec579-105">A Global Tool can be installed on your machine on a default location that is included in the PATH environment variable or on a custom location.</span></span>

<span data-ttu-id="ec579-106">若要使用 .NET Core 全局工具，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ec579-106">If you want to use a .NET Core Global Tool:</span></span>

* <span data-ttu-id="ec579-107">查找该工具的相关信息（通常是一个网站或 GitHub 页面）。</span><span class="sxs-lookup"><span data-stu-id="ec579-107">Find information about the tool (usually a website or GitHub page).</span></span>
* <span data-ttu-id="ec579-108">在源的主页（通常为 NuGet.org）查看作者和统计信息。</span><span class="sxs-lookup"><span data-stu-id="ec579-108">Check the author and statistics in the home for the feed (usually NuGet.org).</span></span>
* <span data-ttu-id="ec579-109">安装该工具。</span><span class="sxs-lookup"><span data-stu-id="ec579-109">Install the tool.</span></span>
* <span data-ttu-id="ec579-110">调用该工具。</span><span class="sxs-lookup"><span data-stu-id="ec579-110">Call the tool.</span></span>
* <span data-ttu-id="ec579-111">更新该工具。</span><span class="sxs-lookup"><span data-stu-id="ec579-111">Update the tool.</span></span>
* <span data-ttu-id="ec579-112">卸载该工具。</span><span class="sxs-lookup"><span data-stu-id="ec579-112">Uninstall the tool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec579-113">.NET Core 全局工具在路径中显示，且以完全信任的方式运行。</span><span class="sxs-lookup"><span data-stu-id="ec579-113">.NET Core Global Tools appear on your path and run in full trust.</span></span> <span data-ttu-id="ec579-114">除非你信任工具作者，否则请勿安装 .NET Core 全局工具。</span><span class="sxs-lookup"><span data-stu-id="ec579-114">Do not install .NET Core Global Tools unless you trust the author.</span></span>

## <a name="find-a-net-core-global-tool"></a><span data-ttu-id="ec579-115">查找 .NET Core 全局工具</span><span class="sxs-lookup"><span data-stu-id="ec579-115">Find a .NET Core Global Tool</span></span>

<span data-ttu-id="ec579-116">目前，.NET Core 命令行接口 (CLI) 中没有全局工具搜索功能。</span><span class="sxs-lookup"><span data-stu-id="ec579-116">Currently, there isn't a Global Tool search feature in the .NET Core Command-line Interface (CLI).</span></span>

<span data-ttu-id="ec579-117">可在 [NuGet](https://www.nuget.org) 上查找 .NET Core 全局工具。</span><span class="sxs-lookup"><span data-stu-id="ec579-117">You can find .NET Core Global Tools on [NuGet](https://www.nuget.org).</span></span> <span data-ttu-id="ec579-118">但是 NuGet 尚不能专门针对 .NET Core 全局工具进行搜索。</span><span class="sxs-lookup"><span data-stu-id="ec579-118">However, NuGet doesn't yet allow you to search specifically for .NET Core Global Tools.</span></span>

<span data-ttu-id="ec579-119">还可在博客文章或 [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub 存储库中找到工具建议。</span><span class="sxs-lookup"><span data-stu-id="ec579-119">You may also find tool recommendations in blog posts or in the [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub repository.</span></span>

<span data-ttu-id="ec579-120">也可以在 [aspnet/DotNetTools](https://github.com/aspnet/DotNetTools/) GitHub 存储库查看 ASP.NET 团队创建的全局工具的源代码。</span><span class="sxs-lookup"><span data-stu-id="ec579-120">You can also see the source code for the Global Tools created by the ASP.NET team at the [aspnet/DotNetTools](https://github.com/aspnet/DotNetTools/) GitHub repository.</span></span>

## <a name="check-the-author-and-statistics"></a><span data-ttu-id="ec579-121">查看作者和统计信息</span><span class="sxs-lookup"><span data-stu-id="ec579-121">Check the author and statistics</span></span>

<span data-ttu-id="ec579-122">由于 .NET Core 全局工具以完全信任的方式运行且通常安装在你的路径中，所以它们的作用会很强大。</span><span class="sxs-lookup"><span data-stu-id="ec579-122">Since .NET Core Global Tools run in full trust and are generally installed on your path, they can be very powerful.</span></span> <span data-ttu-id="ec579-123">请勿下载不信任的人提供的工具。</span><span class="sxs-lookup"><span data-stu-id="ec579-123">Don't download tools from people you don't trust.</span></span>

<span data-ttu-id="ec579-124">如果该工具在 NuGet 中托管，可以通过搜索该工具来查看作者和统计信息。</span><span class="sxs-lookup"><span data-stu-id="ec579-124">If the tool is hosted on NuGet, you can check the author and statistics by searching for the tool.</span></span>

## <a name="install-a-global-tool"></a><span data-ttu-id="ec579-125">安装全局工具</span><span class="sxs-lookup"><span data-stu-id="ec579-125">Install a Global Tool</span></span>

<span data-ttu-id="ec579-126">若要安装全局工具，请使用 [dotnet tool install](dotnet-tool-install.md) .NET Core CLI 命令。</span><span class="sxs-lookup"><span data-stu-id="ec579-126">To install a Global Tool, you use the [dotnet tool install](dotnet-tool-install.md) .NET Core CLI command.</span></span> <span data-ttu-id="ec579-127">下面的示例演示如何在默认位置安装全局工具：</span><span class="sxs-lookup"><span data-stu-id="ec579-127">The following example shows how to install a Global Tool in the default location:</span></span>

```console
dotnet tool install -g dotnetsay
```

<span data-ttu-id="ec579-128">如果无法安装该工具，则会显示错误消息。</span><span class="sxs-lookup"><span data-stu-id="ec579-128">If the tool can't be installed, error messages are displayed.</span></span> <span data-ttu-id="ec579-129">检查所需源是否正在被检查。</span><span class="sxs-lookup"><span data-stu-id="ec579-129">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="ec579-130">如果想安装工具的预发布版本或特定版本，可以采用以下格式指定版本号：</span><span class="sxs-lookup"><span data-stu-id="ec579-130">If you're trying to install a pre-release version or a specific version of the tool, you can specify the version number using the following format:</span></span>

```console
dotnet tool install -g <package-name> --version <version-number>
```

<span data-ttu-id="ec579-131">如果安装成功，会出现一条消息，显示用于调用工具的命令以及所安装的版本，类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="ec579-131">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.0.0') was successfully installed.
```

<span data-ttu-id="ec579-132">全局工具可安装在默认目录或特定位置中。</span><span class="sxs-lookup"><span data-stu-id="ec579-132">Global Tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="ec579-133">默认目录为：</span><span class="sxs-lookup"><span data-stu-id="ec579-133">The default directories are:</span></span>

| <span data-ttu-id="ec579-134">(OS)</span><span class="sxs-lookup"><span data-stu-id="ec579-134">OS</span></span>          | <span data-ttu-id="ec579-135">路径</span><span class="sxs-lookup"><span data-stu-id="ec579-135">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="ec579-136">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="ec579-136">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="ec579-137">Windows</span><span class="sxs-lookup"><span data-stu-id="ec579-137">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="ec579-138">这些位置在首次运行 SDK 时添加到用户的路径，所以可以直接调用安装在这里的全局工具。</span><span class="sxs-lookup"><span data-stu-id="ec579-138">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="ec579-139">请注意，全局工具是特定于用户的，而不是针对计算机全局的。</span><span class="sxs-lookup"><span data-stu-id="ec579-139">Note that the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="ec579-140">特定于用户的意思是无法在一台计算机上安装所有用户都可用的全局工具。</span><span class="sxs-lookup"><span data-stu-id="ec579-140">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="ec579-141">只有安装了该工具的用户配置文件才能使用它。</span><span class="sxs-lookup"><span data-stu-id="ec579-141">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="ec579-142">也可在特定目录安装全局工具。</span><span class="sxs-lookup"><span data-stu-id="ec579-142">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="ec579-143">如果在特定目录安装全局工具，用户必须确保命令是可用的，方法是将该目录添加至路径、使用指定目录调用命令或从特定目录调用该工具。</span><span class="sxs-lookup"><span data-stu-id="ec579-143">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="ec579-144">在这种情况下，.NET Core CLI 不将此地址自动添加至 PATH 环境变量。</span><span class="sxs-lookup"><span data-stu-id="ec579-144">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="use-the-tool"></a><span data-ttu-id="ec579-145">使用该工具</span><span class="sxs-lookup"><span data-stu-id="ec579-145">Use the tool</span></span>

<span data-ttu-id="ec579-146">安装工具后，可以使用它的命令来调用它。</span><span class="sxs-lookup"><span data-stu-id="ec579-146">Once the tool is installed, you can call it by using its command.</span></span> <span data-ttu-id="ec579-147">注意，该命令可能和包名称不同。</span><span class="sxs-lookup"><span data-stu-id="ec579-147">Note that the command may not be the same as the package name.</span></span>

<span data-ttu-id="ec579-148">如果该命令为 `dotnetsay`，可以使用以下内容调用它：</span><span class="sxs-lookup"><span data-stu-id="ec579-148">If the command is `dotnetsay`, you call it with:</span></span>

```console
dotnetsay
```

<span data-ttu-id="ec579-149">如果工具作者希望工具出现在 `dotnet` 提示符的上下文中，他们可能采用称为 `dotnet <command>` 的方式进行编写，例如：</span><span class="sxs-lookup"><span data-stu-id="ec579-149">If the tool author wanted the tool to appear in the context of the `dotnet` prompt, they may have written it in a way that you call it as `dotnet <command>`, such as:</span></span>

```console
dotnet doc
```

<span data-ttu-id="ec579-150">若要查找安装的全局工具包中包含哪些工具，可以使用 [dotnet tool list](dotnet-tool-list.md) 命令列出安装的包。</span><span class="sxs-lookup"><span data-stu-id="ec579-150">You can find which tools are included in an installed Global Tool package by listing the installed packages using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

<span data-ttu-id="ec579-151">若要查看使用说明，可以访问工具的网站或键入下列命令之一：</span><span class="sxs-lookup"><span data-stu-id="ec579-151">You can also look for usage instructions at the tool's website or by typing one of the following commands:</span></span>

```console
<command> --help
dotnet <command> --help
```

### <a name="what-could-go-wrong"></a><span data-ttu-id="ec579-152">可能出现的问题</span><span class="sxs-lookup"><span data-stu-id="ec579-152">What could go wrong</span></span>

<span data-ttu-id="ec579-153">全局工具是[依赖框架的应用程序](../deploying/index.md#framework-dependent-deployments-fdd)，也就是说它们依赖于计算机上安装的 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="ec579-153">Global Tools are [framework-dependent applications](../deploying/index.md#framework-dependent-deployments-fdd), which means they rely on a .NET Core runtime installed on your machine.</span></span> <span data-ttu-id="ec579-154">如果没有找到所需的运行时，则遵循常规的 .NET Core 运行时前滚规则，例如：</span><span class="sxs-lookup"><span data-stu-id="ec579-154">If the expected runtime is not found, they follow normal .NET Core runtime roll-forward rules such as:</span></span>

* <span data-ttu-id="ec579-155">应用程序前滚至指定的主要版本和次要版本的最高修补程序版本。</span><span class="sxs-lookup"><span data-stu-id="ec579-155">An application rolls forward to the highest patch release of the specified major and minor version.</span></span>
* <span data-ttu-id="ec579-156">如果主要版本号和次要版本号没有匹配的运行时，则使用下一个较高的次要版本。</span><span class="sxs-lookup"><span data-stu-id="ec579-156">If there is no matching runtime with a matching major and minor version number, the next higher minor version is used.</span></span>
* <span data-ttu-id="ec579-157">前滚不会发生在运行时的预览版之间，也不会发生在预览版和发行版之间。</span><span class="sxs-lookup"><span data-stu-id="ec579-157">Roll forward doesn't occur between preview versions of the runtime or between preview versions and release versions.</span></span> <span data-ttu-id="ec579-158">因此，使用预览版创建的全局工具必须由作者重新生成和重新发布，再重新安装。</span><span class="sxs-lookup"><span data-stu-id="ec579-158">Thus, Global Tools created using preview versions must be rebuilt and republished by the author and reinstalled.</span></span>
* <span data-ttu-id="ec579-159">在 .NET Core 2.1 Preview 1 中创建的全局工具可能会出现其他问题。</span><span class="sxs-lookup"><span data-stu-id="ec579-159">Additional issues can occur with Global Tools created in .NET Core 2.1 Preview 1.</span></span> <span data-ttu-id="ec579-160">有关详细信息，请参阅 [.NET Core 2.1 Preview 2 已知的问题](https://github.com/dotnet/core/blob/master/release-notes/2.1/Preview/2.1.0-preview2-known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="ec579-160">For more information, see [.NET Core 2.1 Preview 2 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/2.1/Preview/2.1.0-preview2-known-issues.md).</span></span>

<span data-ttu-id="ec579-161">如果应用程序无法找到合适的运行时，它就无法运行并报告错误。</span><span class="sxs-lookup"><span data-stu-id="ec579-161">If an application cannot find an appropriate runtime, it fails to run and reports an error.</span></span>

<span data-ttu-id="ec579-162">另一个可能出现的问题是，在较早预览版中创建的全局工具不能在当前安装的 .NET Core 运行时中运行。</span><span class="sxs-lookup"><span data-stu-id="ec579-162">Another issue that might happen is that a Global Tool that was created during an earlier preview may not run with your currently installed .NET Core runtimes.</span></span> <span data-ttu-id="ec579-163">若要查看计算机上安装了哪些运行时，可以使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="ec579-163">You can see which runtimes are installed on your machine using the following command:</span></span>

```console
dotnet --list-runtimes
```

<span data-ttu-id="ec579-164">与全局工具的作者联系，看看他们是否能重新编译工具包，并将更新了版本号的工具包重新发布至 NuGet。</span><span class="sxs-lookup"><span data-stu-id="ec579-164">Contact the author of the Global Tool and see if they can recompile and republish their tool package to NuGet with an updated version number.</span></span> <span data-ttu-id="ec579-165">如果作者更新了 NuGet 上的包，用户便可更新副本。</span><span class="sxs-lookup"><span data-stu-id="ec579-165">Once they have updated the package on NuGet, you can update your copy.</span></span>

<span data-ttu-id="ec579-166">.NET Core CLI 在首次使用时尝试将默认位置添加到 PATH 环境变量。</span><span class="sxs-lookup"><span data-stu-id="ec579-166">The .NET Core CLI tries to add the default locations to the PATH environment variable on its first usage.</span></span> <span data-ttu-id="ec579-167">但是，在某些情况下，位置不会自动添加至 PATH，例如：</span><span class="sxs-lookup"><span data-stu-id="ec579-167">However, there are a couple of scenarios where the location might not be added to PATH automatically, such as:</span></span>

* <span data-ttu-id="ec579-168">如果已设置 `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` 环境变量。</span><span class="sxs-lookup"><span data-stu-id="ec579-168">If you've set the `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` environment variable.</span></span>
* <span data-ttu-id="ec579-169">如果已在 macOS 上使用 .tar.gz 文件（而不是 .pkg）安装了 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="ec579-169">On macOS, if you've installed the .NET Core SDK using *.tar.gz* files and not *.pkg*.</span></span>
* <span data-ttu-id="ec579-170">在 Linux 上，需要编辑 shell 环境文件来配置 PATH。</span><span class="sxs-lookup"><span data-stu-id="ec579-170">On Linux, you need to edit the shell environment file to configure the PATH.</span></span>

## <a name="other-cli-commands"></a><span data-ttu-id="ec579-171">其他 CLI 命令</span><span class="sxs-lookup"><span data-stu-id="ec579-171">Other CLI commands</span></span>

<span data-ttu-id="ec579-172">.NET Core SDK 包含支持 .NET Core 全局工具的其他命令。</span><span class="sxs-lookup"><span data-stu-id="ec579-172">The .NET Core SDK contains other commands that support .NET Core Global Tools.</span></span> <span data-ttu-id="ec579-173">将 `dotnet tool` 命令用于以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="ec579-173">Use any of the `dotnet tool` commands with one of the following options:</span></span>

* <span data-ttu-id="ec579-174">`--global` 或 `-g` 指定命令用于用户范围的全局工具。</span><span class="sxs-lookup"><span data-stu-id="ec579-174">`--global` or `-g` specifies that the command is applicable to user-wide Global Tools.</span></span>
* <span data-ttu-id="ec579-175">`--tool-path` 指定全局工具的自定义位置。</span><span class="sxs-lookup"><span data-stu-id="ec579-175">`--tool-path` specifies a custom location for Global Tools.</span></span>

<span data-ttu-id="ec579-176">若要了解哪些命令可用于全局工具：</span><span class="sxs-lookup"><span data-stu-id="ec579-176">To find out which commands are available for Global Tools:</span></span>

```console
dotnet tool --help
```

<span data-ttu-id="ec579-177">更新全局工具涉及卸载该工具并重新安装它的最新稳定版。</span><span class="sxs-lookup"><span data-stu-id="ec579-177">Updating a Global Tool involves uninstalling and reinstalling it with the latest stable version.</span></span> <span data-ttu-id="ec579-178">若要更新全局工具，请使用 [dotnet tool update](dotnet-tool-update.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="ec579-178">To update a Global Tool, use the [dotnet tool update](dotnet-tool-update.md) command:</span></span>

```console
dotnet tool update -g <packagename>
```

<span data-ttu-id="ec579-179">使用 [dotnet tool uninstall](dotnet-tool-uninstall.md) 命令删除全局工具：</span><span class="sxs-lookup"><span data-stu-id="ec579-179">Remove a Global Tool using the [dotnet tool uninstall](dotnet-tool-uninstall.md):</span></span>

```console
dotnet tool uninstall -g <packagename>
```

<span data-ttu-id="ec579-180">若要显示计算机上目前安装的所有全局工具及其版本和命令，请使用 [dotnet tool list](dotnet-tool-list.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="ec579-180">To display all of the Global Tools currently installed on the machine, along with their version and commands, use the [dotnet tool list](dotnet-tool-list.md) command:</span></span>

```console
dotnet tool list -g
```