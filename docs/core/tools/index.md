---
title: .NET Core CLI
titleSuffix: ''
description: .NET Core CLI 及其功能概述。
ms.date: 08/14/2017
ms.openlocfilehash: b0a8e0dd8cf77bb6f7567c27e9972f62515ec0f2
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920485"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="f8b77-103">.NET Core CLI 概述</span><span class="sxs-lookup"><span data-stu-id="f8b77-103">.NET Core CLI overview</span></span>

<span data-ttu-id="f8b77-104">.NET Core 命令行接口 (CLI) 工具是用于开发、生成、运行和发布 .NET Core 应用程序的跨平台工具链。</span><span class="sxs-lookup"><span data-stu-id="f8b77-104">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="f8b77-105">.NET Core CLI 包含在 [.NET Core SDK](../sdk.md) 中。</span><span class="sxs-lookup"><span data-stu-id="f8b77-105">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="f8b77-106">若要了解如何安装 .NET Core SDK，请参阅[安装 .NET Core SDK](../install/sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="f8b77-106">To learn how to install the .NET Core SDK, see [Install the .NET Core SDK](../install/sdk.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="f8b77-107">CLI 命令</span><span class="sxs-lookup"><span data-stu-id="f8b77-107">CLI commands</span></span>

<span data-ttu-id="f8b77-108">默认安装以下命令：</span><span class="sxs-lookup"><span data-stu-id="f8b77-108">The following commands are installed by default:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f8b77-109">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f8b77-109">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="f8b77-110">**基本命令**</span><span class="sxs-lookup"><span data-stu-id="f8b77-110">**Basic commands**</span></span>

- [<span data-ttu-id="f8b77-111">new</span><span class="sxs-lookup"><span data-stu-id="f8b77-111">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="f8b77-112">restore</span><span class="sxs-lookup"><span data-stu-id="f8b77-112">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="f8b77-113">build</span><span class="sxs-lookup"><span data-stu-id="f8b77-113">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="f8b77-114">publish</span><span class="sxs-lookup"><span data-stu-id="f8b77-114">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="f8b77-115">run</span><span class="sxs-lookup"><span data-stu-id="f8b77-115">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="f8b77-116">test</span><span class="sxs-lookup"><span data-stu-id="f8b77-116">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="f8b77-117">vstest</span><span class="sxs-lookup"><span data-stu-id="f8b77-117">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="f8b77-118">pack</span><span class="sxs-lookup"><span data-stu-id="f8b77-118">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="f8b77-119">migrate</span><span class="sxs-lookup"><span data-stu-id="f8b77-119">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="f8b77-120">clean</span><span class="sxs-lookup"><span data-stu-id="f8b77-120">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="f8b77-121">sln</span><span class="sxs-lookup"><span data-stu-id="f8b77-121">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="f8b77-122">help</span><span class="sxs-lookup"><span data-stu-id="f8b77-122">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="f8b77-123">store</span><span class="sxs-lookup"><span data-stu-id="f8b77-123">store</span></span>](dotnet-store.md)

<span data-ttu-id="f8b77-124">**项目修改命令**</span><span class="sxs-lookup"><span data-stu-id="f8b77-124">**Project modification commands**</span></span>

- [<span data-ttu-id="f8b77-125">add package</span><span class="sxs-lookup"><span data-stu-id="f8b77-125">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="f8b77-126">add reference</span><span class="sxs-lookup"><span data-stu-id="f8b77-126">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="f8b77-127">remove package</span><span class="sxs-lookup"><span data-stu-id="f8b77-127">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="f8b77-128">remove reference</span><span class="sxs-lookup"><span data-stu-id="f8b77-128">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="f8b77-129">list reference</span><span class="sxs-lookup"><span data-stu-id="f8b77-129">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="f8b77-130">**高级命令**</span><span class="sxs-lookup"><span data-stu-id="f8b77-130">**Advanced commands**</span></span>

- [<span data-ttu-id="f8b77-131">nuget delete</span><span class="sxs-lookup"><span data-stu-id="f8b77-131">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="f8b77-132">nuget locals</span><span class="sxs-lookup"><span data-stu-id="f8b77-132">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="f8b77-133">nuget push</span><span class="sxs-lookup"><span data-stu-id="f8b77-133">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="f8b77-134">msbuild</span><span class="sxs-lookup"><span data-stu-id="f8b77-134">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="f8b77-135">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="f8b77-135">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f8b77-136">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f8b77-136">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="f8b77-137">**基本命令**</span><span class="sxs-lookup"><span data-stu-id="f8b77-137">**Basic commands**</span></span>

- [<span data-ttu-id="f8b77-138">new</span><span class="sxs-lookup"><span data-stu-id="f8b77-138">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="f8b77-139">restore</span><span class="sxs-lookup"><span data-stu-id="f8b77-139">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="f8b77-140">build</span><span class="sxs-lookup"><span data-stu-id="f8b77-140">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="f8b77-141">publish</span><span class="sxs-lookup"><span data-stu-id="f8b77-141">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="f8b77-142">run</span><span class="sxs-lookup"><span data-stu-id="f8b77-142">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="f8b77-143">test</span><span class="sxs-lookup"><span data-stu-id="f8b77-143">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="f8b77-144">vstest</span><span class="sxs-lookup"><span data-stu-id="f8b77-144">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="f8b77-145">pack</span><span class="sxs-lookup"><span data-stu-id="f8b77-145">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="f8b77-146">migrate</span><span class="sxs-lookup"><span data-stu-id="f8b77-146">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="f8b77-147">clean</span><span class="sxs-lookup"><span data-stu-id="f8b77-147">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="f8b77-148">sln</span><span class="sxs-lookup"><span data-stu-id="f8b77-148">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="f8b77-149">**项目修改命令**</span><span class="sxs-lookup"><span data-stu-id="f8b77-149">**Project modification commands**</span></span>

- [<span data-ttu-id="f8b77-150">add package</span><span class="sxs-lookup"><span data-stu-id="f8b77-150">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="f8b77-151">add reference</span><span class="sxs-lookup"><span data-stu-id="f8b77-151">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="f8b77-152">remove package</span><span class="sxs-lookup"><span data-stu-id="f8b77-152">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="f8b77-153">remove reference</span><span class="sxs-lookup"><span data-stu-id="f8b77-153">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="f8b77-154">list reference</span><span class="sxs-lookup"><span data-stu-id="f8b77-154">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="f8b77-155">**高级命令**</span><span class="sxs-lookup"><span data-stu-id="f8b77-155">**Advanced commands**</span></span>

- [<span data-ttu-id="f8b77-156">nuget delete</span><span class="sxs-lookup"><span data-stu-id="f8b77-156">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="f8b77-157">nuget locals</span><span class="sxs-lookup"><span data-stu-id="f8b77-157">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="f8b77-158">nuget push</span><span class="sxs-lookup"><span data-stu-id="f8b77-158">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="f8b77-159">msbuild</span><span class="sxs-lookup"><span data-stu-id="f8b77-159">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="f8b77-160">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="f8b77-160">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="f8b77-161">CLI 采用可使你为项目指定其他工具的扩展性模型。</span><span class="sxs-lookup"><span data-stu-id="f8b77-161">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="f8b77-162">有关详细信息，请参阅 [.NET Core CLI 扩展性模型](extensibility.md)主题。</span><span class="sxs-lookup"><span data-stu-id="f8b77-162">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="f8b77-163">命令结构</span><span class="sxs-lookup"><span data-stu-id="f8b77-163">Command structure</span></span>

<span data-ttu-id="f8b77-164">CLI 命令结构包含[驱动程序（“dotnet”）](#driver)和[命令](#command)，还可能包含命令[参数](#arguments)和[选项](#options)。</span><span class="sxs-lookup"><span data-stu-id="f8b77-164">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="f8b77-165">在大部分 CLI 操作中可看到此模式，例如创建新控制台应用并从命令行运行该应用，因为从名为 *my_app* 的目录中执行时，显示以下命令：</span><span class="sxs-lookup"><span data-stu-id="f8b77-165">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f8b77-166">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f8b77-166">.NET Core 2.x</span></span>](#tab/netcore2x)

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f8b77-167">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f8b77-167">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="f8b77-168">驱动程序</span><span class="sxs-lookup"><span data-stu-id="f8b77-168">Driver</span></span>

<span data-ttu-id="f8b77-169">驱动程序名为 [dotnet](dotnet.md)，并具有两项职责，即运行[依赖于框架的应用](../deploying/index.md)或执行命令。</span><span class="sxs-lookup"><span data-stu-id="f8b77-169">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="f8b77-170">若要运行依赖于框架的应用，请在驱动程序后指定应用，例如，`dotnet /path/to/my_app.dll`。</span><span class="sxs-lookup"><span data-stu-id="f8b77-170">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="f8b77-171">从应用的 DLL 驻留的文件夹执行命令时，只需执行 `dotnet my_app.dll` 即可。</span><span class="sxs-lookup"><span data-stu-id="f8b77-171">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="f8b77-172">如果要使用特定版本的 .NET Core 运行时，请使用 `--fx-version <VERSION>` 选项（请参阅 [dotnet 命令](dotnet.md)参考）。</span><span class="sxs-lookup"><span data-stu-id="f8b77-172">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="f8b77-173">为驱动程序提供命令时，`dotnet.exe` 启动 CLI 命令执行过程。</span><span class="sxs-lookup"><span data-stu-id="f8b77-173">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="f8b77-174">例如：</span><span class="sxs-lookup"><span data-stu-id="f8b77-174">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="f8b77-175">首先，驱动程序确定要使用的 SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="f8b77-175">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="f8b77-176">如果没有任何[“global.json”](global-json.md)，则使用可用的最新版本 SDK。</span><span class="sxs-lookup"><span data-stu-id="f8b77-176">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="f8b77-177">这有可能是预览版或稳定版，具体取决于计算机上的最新版本。</span><span class="sxs-lookup"><span data-stu-id="f8b77-177">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="f8b77-178">确定 SDK 版本后，它便会执行命令。</span><span class="sxs-lookup"><span data-stu-id="f8b77-178">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="f8b77-179">命令</span><span class="sxs-lookup"><span data-stu-id="f8b77-179">Command</span></span>

<span data-ttu-id="f8b77-180">由命令执行操作。</span><span class="sxs-lookup"><span data-stu-id="f8b77-180">The command performs an action.</span></span> <span data-ttu-id="f8b77-181">例如，`dotnet build` 生成代码。</span><span class="sxs-lookup"><span data-stu-id="f8b77-181">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="f8b77-182">`dotnet publish` 发布代码。</span><span class="sxs-lookup"><span data-stu-id="f8b77-182">`dotnet publish` publishes code.</span></span> <span data-ttu-id="f8b77-183">使用 `dotnet {command}` 约定将命令作为控制台应用程序实现。</span><span class="sxs-lookup"><span data-stu-id="f8b77-183">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="f8b77-184">自变量</span><span class="sxs-lookup"><span data-stu-id="f8b77-184">Arguments</span></span>

<span data-ttu-id="f8b77-185">在命令行上传递的参数是被调用的命令的参数。</span><span class="sxs-lookup"><span data-stu-id="f8b77-185">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="f8b77-186">例如，执行 `dotnet publish my_app.csproj` 时，`my_app.csproj` 参数指示要发布的项目，并被传递到 `publish` 命令。</span><span class="sxs-lookup"><span data-stu-id="f8b77-186">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="f8b77-187">选项</span><span class="sxs-lookup"><span data-stu-id="f8b77-187">Options</span></span>

<span data-ttu-id="f8b77-188">在命令行上传递的选项是被调用的命令的选项。</span><span class="sxs-lookup"><span data-stu-id="f8b77-188">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="f8b77-189">例如，执行 `dotnet publish --output /build_output` 时，`--output` 选项及其值被传递到 `publish` 命令。</span><span class="sxs-lookup"><span data-stu-id="f8b77-189">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="f8b77-190">从 project.json 迁移</span><span class="sxs-lookup"><span data-stu-id="f8b77-190">Migration from project.json</span></span>

<span data-ttu-id="f8b77-191">如果使用预览版 2 工具生成基于 *project.json* 的项目，请查阅 [dotnet 迁移](dotnet-migrate.md)主题，了解将你的项目迁移到 MSBuild/ *.csproj* 以使用版本工具的信息。</span><span class="sxs-lookup"><span data-stu-id="f8b77-191">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="f8b77-192">对于预览版 2 工具发布之前所创建的 .NET Core 项目，请按照[从 DNX 迁移到 .NET Core CLI (project.json)](../migration/from-dnx.md) 中的指南手动更新项目，然后使用 `dotnet migrate` 或直接升级项目。</span><span class="sxs-lookup"><span data-stu-id="f8b77-192">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8b77-193">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8b77-193">See also</span></span>

- [<span data-ttu-id="f8b77-194">dotnet/sdk GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="f8b77-194">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- [<span data-ttu-id="f8b77-195">.NET Core 安装指南</span><span class="sxs-lookup"><span data-stu-id="f8b77-195">.NET Core installation guide</span></span>](https://aka.ms/dotnetcoregs)
