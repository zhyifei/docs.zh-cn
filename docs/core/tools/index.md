---
title: .NET Core CLI
titleSuffix: ''
description: .NET Core CLI 及其功能概述。
ms.date: 02/13/2020
ms.openlocfilehash: c491088f26a9aa1c065414e76fb0b80d554380b4
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77625977"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="13ed3-103">.NET Core CLI 概述</span><span class="sxs-lookup"><span data-stu-id="13ed3-103">.NET Core CLI overview</span></span>

<span data-ttu-id="13ed3-104">本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="13ed3-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="13ed3-105">.NET Core 命令行接口 (CLI) 工具是用于开发、生成、运行和发布 .NET Core 应用程序的跨平台工具链。</span><span class="sxs-lookup"><span data-stu-id="13ed3-105">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="13ed3-106">.NET Core CLI 包含在 [.NET Core SDK](../sdk.md) 中。</span><span class="sxs-lookup"><span data-stu-id="13ed3-106">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="13ed3-107">若要了解如何安装 .NET Core SDK，请参阅[安装 .NET Core SDK](../install/sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="13ed3-107">To learn how to install the .NET Core SDK, see [Install the .NET Core SDK](../install/sdk.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="13ed3-108">CLI 命令</span><span class="sxs-lookup"><span data-stu-id="13ed3-108">CLI commands</span></span>

<span data-ttu-id="13ed3-109">默认安装以下命令：</span><span class="sxs-lookup"><span data-stu-id="13ed3-109">The following commands are installed by default:</span></span>

### <a name="basic-commands"></a><span data-ttu-id="13ed3-110">基本命令</span><span class="sxs-lookup"><span data-stu-id="13ed3-110">Basic commands</span></span>

- [<span data-ttu-id="13ed3-111">new</span><span class="sxs-lookup"><span data-stu-id="13ed3-111">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="13ed3-112">restore</span><span class="sxs-lookup"><span data-stu-id="13ed3-112">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="13ed3-113">build</span><span class="sxs-lookup"><span data-stu-id="13ed3-113">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="13ed3-114">publish</span><span class="sxs-lookup"><span data-stu-id="13ed3-114">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="13ed3-115">run</span><span class="sxs-lookup"><span data-stu-id="13ed3-115">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="13ed3-116">test</span><span class="sxs-lookup"><span data-stu-id="13ed3-116">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="13ed3-117">vstest</span><span class="sxs-lookup"><span data-stu-id="13ed3-117">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="13ed3-118">pack</span><span class="sxs-lookup"><span data-stu-id="13ed3-118">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="13ed3-119">migrate</span><span class="sxs-lookup"><span data-stu-id="13ed3-119">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="13ed3-120">clean</span><span class="sxs-lookup"><span data-stu-id="13ed3-120">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="13ed3-121">sln</span><span class="sxs-lookup"><span data-stu-id="13ed3-121">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="13ed3-122">help</span><span class="sxs-lookup"><span data-stu-id="13ed3-122">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="13ed3-123">store</span><span class="sxs-lookup"><span data-stu-id="13ed3-123">store</span></span>](dotnet-store.md)

### <a name="project-modification-commands"></a><span data-ttu-id="13ed3-124">项目修改命令</span><span class="sxs-lookup"><span data-stu-id="13ed3-124">Project modification commands</span></span>

- [<span data-ttu-id="13ed3-125">add package</span><span class="sxs-lookup"><span data-stu-id="13ed3-125">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="13ed3-126">add reference</span><span class="sxs-lookup"><span data-stu-id="13ed3-126">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="13ed3-127">remove package</span><span class="sxs-lookup"><span data-stu-id="13ed3-127">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="13ed3-128">remove reference</span><span class="sxs-lookup"><span data-stu-id="13ed3-128">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="13ed3-129">list reference</span><span class="sxs-lookup"><span data-stu-id="13ed3-129">list reference</span></span>](dotnet-list-reference.md)

### <a name="advanced-commands"></a><span data-ttu-id="13ed3-130">高级命令</span><span class="sxs-lookup"><span data-stu-id="13ed3-130">Advanced commands</span></span>

- [<span data-ttu-id="13ed3-131">nuget delete</span><span class="sxs-lookup"><span data-stu-id="13ed3-131">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="13ed3-132">nuget locals</span><span class="sxs-lookup"><span data-stu-id="13ed3-132">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="13ed3-133">nuget push</span><span class="sxs-lookup"><span data-stu-id="13ed3-133">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="13ed3-134">msbuild</span><span class="sxs-lookup"><span data-stu-id="13ed3-134">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="13ed3-135">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="13ed3-135">dotnet install script</span></span>](dotnet-install-script.md)

### <a name="tool-management-commands"></a><span data-ttu-id="13ed3-136">工具管理命令</span><span class="sxs-lookup"><span data-stu-id="13ed3-136">Tool management commands</span></span>

- [<span data-ttu-id="13ed3-137">tool install</span><span class="sxs-lookup"><span data-stu-id="13ed3-137">tool install</span></span>](dotnet-tool-install.md)
- [<span data-ttu-id="13ed3-138">tool list</span><span class="sxs-lookup"><span data-stu-id="13ed3-138">tool list</span></span>](dotnet-tool-list.md)
- [<span data-ttu-id="13ed3-139">tool update</span><span class="sxs-lookup"><span data-stu-id="13ed3-139">tool update</span></span>](dotnet-tool-update.md)
- <span data-ttu-id="13ed3-140">[tool restore](global-tools.md#install-a-local-tool) 自 .NET Core SDK 3.0 起可用</span><span class="sxs-lookup"><span data-stu-id="13ed3-140">[tool restore](global-tools.md#install-a-local-tool) **Available starting with .NET Core SDK 3.0**</span></span>
- <span data-ttu-id="13ed3-141">[tool run](global-tools.md#invoke-a-local-tool) 自 .NET Core SDK 3.0 起可用</span><span class="sxs-lookup"><span data-stu-id="13ed3-141">[tool run](global-tools.md#invoke-a-local-tool) **Available starting with .NET Core SDK 3.0**</span></span>
- [<span data-ttu-id="13ed3-142">tool uninstall</span><span class="sxs-lookup"><span data-stu-id="13ed3-142">tool uninstall</span></span>](dotnet-tool-uninstall.md)

<span data-ttu-id="13ed3-143">工具是控制台应用程序，它们从 NuGet 包中安装并从命令提示符处进行调用。</span><span class="sxs-lookup"><span data-stu-id="13ed3-143">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="13ed3-144">你可自行编写工具，也可安装由第三方编写的工具。</span><span class="sxs-lookup"><span data-stu-id="13ed3-144">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="13ed3-145">工具也称为全局工具、工具路径工具和本地工具。</span><span class="sxs-lookup"><span data-stu-id="13ed3-145">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="13ed3-146">有关详细信息，请参阅 [.NET Core 工具概述](global-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="13ed3-146">For more information, see [.NET Core tools overview](global-tools.md).</span></span>

## <a name="command-structure"></a><span data-ttu-id="13ed3-147">命令结构</span><span class="sxs-lookup"><span data-stu-id="13ed3-147">Command structure</span></span>

<span data-ttu-id="13ed3-148">CLI 命令结构包含[驱动程序（“dotnet”）](#driver)和[命令](#command)，还可能包含命令[参数](#arguments)和[选项](#options)。</span><span class="sxs-lookup"><span data-stu-id="13ed3-148">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="13ed3-149">在大部分 CLI 操作中可看到此模式，例如创建新控制台应用并从命令行运行该应用，因为从名为 *my_app* 的目录中执行时，显示以下命令：</span><span class="sxs-lookup"><span data-stu-id="13ed3-149">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a><span data-ttu-id="13ed3-150">驱动程序</span><span class="sxs-lookup"><span data-stu-id="13ed3-150">Driver</span></span>

<span data-ttu-id="13ed3-151">驱动程序名为 [dotnet](dotnet.md)，并具有两项职责，即运行[依赖于框架的应用](../deploying/index.md)或执行命令。</span><span class="sxs-lookup"><span data-stu-id="13ed3-151">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="13ed3-152">若要运行依赖于框架的应用，请在驱动程序后指定应用，例如，`dotnet /path/to/my_app.dll`。</span><span class="sxs-lookup"><span data-stu-id="13ed3-152">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="13ed3-153">从应用的 DLL 驻留的文件夹执行命令时，只需执行 `dotnet my_app.dll` 即可。</span><span class="sxs-lookup"><span data-stu-id="13ed3-153">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="13ed3-154">如果要使用特定版本的 .NET Core 运行时，请使用 `--fx-version <VERSION>` 选项（请参阅 [dotnet 命令](dotnet.md)参考）。</span><span class="sxs-lookup"><span data-stu-id="13ed3-154">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="13ed3-155">为驱动程序提供命令时，`dotnet.exe` 启动 CLI 命令执行过程。</span><span class="sxs-lookup"><span data-stu-id="13ed3-155">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="13ed3-156">例如：</span><span class="sxs-lookup"><span data-stu-id="13ed3-156">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="13ed3-157">首先，驱动程序确定要使用的 SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="13ed3-157">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="13ed3-158">如果没有 [global.json](global-json.md) 文件，则使用可用的最新版本 SDK。</span><span class="sxs-lookup"><span data-stu-id="13ed3-158">If there is no [global.json](global-json.md) file, the latest version of the SDK available is used.</span></span> <span data-ttu-id="13ed3-159">这有可能是预览版或稳定版，具体取决于计算机上的最新版本。</span><span class="sxs-lookup"><span data-stu-id="13ed3-159">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="13ed3-160">确定 SDK 版本后，它便会执行命令。</span><span class="sxs-lookup"><span data-stu-id="13ed3-160">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="13ed3-161">命令</span><span class="sxs-lookup"><span data-stu-id="13ed3-161">Command</span></span>

<span data-ttu-id="13ed3-162">由命令执行操作。</span><span class="sxs-lookup"><span data-stu-id="13ed3-162">The command performs an action.</span></span> <span data-ttu-id="13ed3-163">例如，`dotnet build` 生成代码。</span><span class="sxs-lookup"><span data-stu-id="13ed3-163">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="13ed3-164">`dotnet publish` 发布代码。</span><span class="sxs-lookup"><span data-stu-id="13ed3-164">`dotnet publish` publishes code.</span></span> <span data-ttu-id="13ed3-165">使用 `dotnet {command}` 约定将命令作为控制台应用程序实现。</span><span class="sxs-lookup"><span data-stu-id="13ed3-165">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="13ed3-166">自变量</span><span class="sxs-lookup"><span data-stu-id="13ed3-166">Arguments</span></span>

<span data-ttu-id="13ed3-167">在命令行上传递的参数是被调用的命令的参数。</span><span class="sxs-lookup"><span data-stu-id="13ed3-167">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="13ed3-168">例如，执行 `dotnet publish my_app.csproj` 时，`my_app.csproj` 参数指示要发布的项目，并被传递到 `publish` 命令。</span><span class="sxs-lookup"><span data-stu-id="13ed3-168">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="13ed3-169">选项</span><span class="sxs-lookup"><span data-stu-id="13ed3-169">Options</span></span>

<span data-ttu-id="13ed3-170">在命令行上传递的选项是被调用的命令的选项。</span><span class="sxs-lookup"><span data-stu-id="13ed3-170">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="13ed3-171">例如，执行 `dotnet publish --output /build_output` 时，`--output` 选项及其值被传递到 `publish` 命令。</span><span class="sxs-lookup"><span data-stu-id="13ed3-171">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="see-also"></a><span data-ttu-id="13ed3-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="13ed3-172">See also</span></span>

- [<span data-ttu-id="13ed3-173">dotnet/sdk GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="13ed3-173">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- [<span data-ttu-id="13ed3-174">.NET Core 安装指南</span><span class="sxs-lookup"><span data-stu-id="13ed3-174">.NET Core installation guide</span></span>](../install/sdk.md)
