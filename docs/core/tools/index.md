---
title: .NET Core 命令行接口 (CLI) 工具
description: 概述了 .NET Core 命令行接口 (CLI) 工具和功能。
ms.date: 08/14/2017
ms.custom: seodec18
ms.openlocfilehash: e174867ce06e573fc85579183df0196d8276fb37
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826309"
---
# <a name="net-core-command-line-interface-cli-tools"></a><span data-ttu-id="674b4-103">.NET Core 命令行接口 (CLI) 工具</span><span class="sxs-lookup"><span data-stu-id="674b4-103">.NET Core command-line interface (CLI) tools</span></span>

<span data-ttu-id="674b4-104">.NET Core 命令行接口 (CLI) 工具是用于开发 .NET 应用程序的新型跨平台工具链。</span><span class="sxs-lookup"><span data-stu-id="674b4-104">The .NET Core command-line interface (CLI) is a new cross-platform toolchain for developing .NET applications.</span></span> <span data-ttu-id="674b4-105">CLI 是更高级别的工具（如集成开发环境 (IDE)、编辑器和生成协调程序）可以驻留的基础。</span><span class="sxs-lookup"><span data-stu-id="674b4-105">The CLI is a foundation upon which higher-level tools, such as Integrated Development Environments (IDEs), editors, and build orchestrators, can rest.</span></span>

## <a name="installation"></a><span data-ttu-id="674b4-106">安装</span><span class="sxs-lookup"><span data-stu-id="674b4-106">Installation</span></span>

<span data-ttu-id="674b4-107">使用本机安装程序或使用安装 shell 脚本：</span><span class="sxs-lookup"><span data-stu-id="674b4-107">Either use the native installers or use the installation shell scripts:</span></span>

* <span data-ttu-id="674b4-108">本机安装程序主要用于开发人员的计算机，并使用每个受支持的平台的本机安装机制，例如，Ubuntu 上的 DEB 程序包或 Windows 上的 MSI 捆绑包。</span><span class="sxs-lookup"><span data-stu-id="674b4-108">The native installers are primarily used on developer's machines and use each supported platform's native install mechanism, for instance, DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="674b4-109">这些安装程序安装并配置环境，供开发人员立即使用，但是需要具有该计算机上的管理权限。</span><span class="sxs-lookup"><span data-stu-id="674b4-109">These installers install and configure the environment for immediate use by the developer but require administrative privileges on the machine.</span></span> <span data-ttu-id="674b4-110">可以在 [.NET Core 安装指南](https://aka.ms/dotnetcoregs)中查看安装说明。</span><span class="sxs-lookup"><span data-stu-id="674b4-110">You can view the installation instructions in the [.NET Core installation guide](https://aka.ms/dotnetcoregs).</span></span>
* <span data-ttu-id="674b4-111">Shell 脚本主要用于设置生成服务器或希望安装工具但没有管理权限的情况。</span><span class="sxs-lookup"><span data-stu-id="674b4-111">Shell scripts are primarily used for setting up build servers or when you wish to install the tools without administrative privileges.</span></span> <span data-ttu-id="674b4-112">安装脚本不会在计算机上安装先决条件，必须手动安装它。</span><span class="sxs-lookup"><span data-stu-id="674b4-112">Install scripts don't install prerequisites on the machine, which must be installed manually.</span></span> <span data-ttu-id="674b4-113">有关详细信息，请参阅[安装脚本引用主题](dotnet-install-script.md)。</span><span class="sxs-lookup"><span data-stu-id="674b4-113">For more information, see the [install script reference topic](dotnet-install-script.md).</span></span> <span data-ttu-id="674b4-114">有关如何在你的持续集成 (CI) 生成服务器上设置 CLI 的信息，请参阅[在持续集成 (CI) 中使用 .NET Core SDK 和工具](using-ci-with-cli.md)。</span><span class="sxs-lookup"><span data-stu-id="674b4-114">For information on how to set up CLI on your continuous integration (CI) build server, see [Using .NET Core SDK and tools in Continuous Integration (CI)](using-ci-with-cli.md).</span></span>

<span data-ttu-id="674b4-115">在默认情况下，SLI 以并行 (SxS) 方式安装，因此，因此，CLI 工具的多个版本可以在一个计算机上共存。</span><span class="sxs-lookup"><span data-stu-id="674b4-115">By default, the CLI installs in a side-by-side (SxS) manner, so multiple versions of the CLI tools can coexist on a single machine.</span></span> <span data-ttu-id="674b4-116">有关确定在安装了多个版本的计算机上所使用的版本的类型，在[驱动程序](#driver)部分中对此有更详尽的介绍。</span><span class="sxs-lookup"><span data-stu-id="674b4-116">Determining which version is used on a machine where multiple versions are installed is explained in more detail in the [Driver](#driver) section.</span></span>

## <a name="cli-commands"></a><span data-ttu-id="674b4-117">CLI 命令</span><span class="sxs-lookup"><span data-stu-id="674b4-117">CLI commands</span></span>

<span data-ttu-id="674b4-118">默认安装以下命令：</span><span class="sxs-lookup"><span data-stu-id="674b4-118">The following commands are installed by default:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="674b4-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="674b4-119">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="674b4-120">**基本命令**</span><span class="sxs-lookup"><span data-stu-id="674b4-120">**Basic commands**</span></span>

* [<span data-ttu-id="674b4-121">new</span><span class="sxs-lookup"><span data-stu-id="674b4-121">new</span></span>](dotnet-new.md)
* [<span data-ttu-id="674b4-122">restore</span><span class="sxs-lookup"><span data-stu-id="674b4-122">restore</span></span>](dotnet-restore.md)
* [<span data-ttu-id="674b4-123">build</span><span class="sxs-lookup"><span data-stu-id="674b4-123">build</span></span>](dotnet-build.md)
* [<span data-ttu-id="674b4-124">publish</span><span class="sxs-lookup"><span data-stu-id="674b4-124">publish</span></span>](dotnet-publish.md)
* [<span data-ttu-id="674b4-125">run</span><span class="sxs-lookup"><span data-stu-id="674b4-125">run</span></span>](dotnet-run.md)
* [<span data-ttu-id="674b4-126">test</span><span class="sxs-lookup"><span data-stu-id="674b4-126">test</span></span>](dotnet-test.md)
* [<span data-ttu-id="674b4-127">vstest</span><span class="sxs-lookup"><span data-stu-id="674b4-127">vstest</span></span>](dotnet-vstest.md)
* [<span data-ttu-id="674b4-128">pack</span><span class="sxs-lookup"><span data-stu-id="674b4-128">pack</span></span>](dotnet-pack.md)
* [<span data-ttu-id="674b4-129">migrate</span><span class="sxs-lookup"><span data-stu-id="674b4-129">migrate</span></span>](dotnet-migrate.md)
* [<span data-ttu-id="674b4-130">clean</span><span class="sxs-lookup"><span data-stu-id="674b4-130">clean</span></span>](dotnet-clean.md)
* [<span data-ttu-id="674b4-131">sln</span><span class="sxs-lookup"><span data-stu-id="674b4-131">sln</span></span>](dotnet-sln.md)
* [<span data-ttu-id="674b4-132">help</span><span class="sxs-lookup"><span data-stu-id="674b4-132">help</span></span>](dotnet-help.md)
* [<span data-ttu-id="674b4-133">store</span><span class="sxs-lookup"><span data-stu-id="674b4-133">store</span></span>](dotnet-store.md)

<span data-ttu-id="674b4-134">**项目修改命令**</span><span class="sxs-lookup"><span data-stu-id="674b4-134">**Project modification commands**</span></span>

* [<span data-ttu-id="674b4-135">add package</span><span class="sxs-lookup"><span data-stu-id="674b4-135">add package</span></span>](dotnet-add-package.md)
* [<span data-ttu-id="674b4-136">add reference</span><span class="sxs-lookup"><span data-stu-id="674b4-136">add reference</span></span>](dotnet-add-reference.md)
* [<span data-ttu-id="674b4-137">remove package</span><span class="sxs-lookup"><span data-stu-id="674b4-137">remove package</span></span>](dotnet-remove-package.md)
* [<span data-ttu-id="674b4-138">remove reference</span><span class="sxs-lookup"><span data-stu-id="674b4-138">remove reference</span></span>](dotnet-remove-reference.md)
* [<span data-ttu-id="674b4-139">list reference</span><span class="sxs-lookup"><span data-stu-id="674b4-139">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="674b4-140">**高级命令**</span><span class="sxs-lookup"><span data-stu-id="674b4-140">**Advanced commands**</span></span>

* [<span data-ttu-id="674b4-141">nuget delete</span><span class="sxs-lookup"><span data-stu-id="674b4-141">nuget delete</span></span>](dotnet-nuget-delete.md)
* [<span data-ttu-id="674b4-142">nuget locals</span><span class="sxs-lookup"><span data-stu-id="674b4-142">nuget locals</span></span>](dotnet-nuget-locals.md)
* [<span data-ttu-id="674b4-143">nuget push</span><span class="sxs-lookup"><span data-stu-id="674b4-143">nuget push</span></span>](dotnet-nuget-push.md)
* [<span data-ttu-id="674b4-144">msbuild</span><span class="sxs-lookup"><span data-stu-id="674b4-144">msbuild</span></span>](dotnet-msbuild.md)
* [<span data-ttu-id="674b4-145">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="674b4-145">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="674b4-146">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="674b4-146">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="674b4-147">**基本命令**</span><span class="sxs-lookup"><span data-stu-id="674b4-147">**Basic commands**</span></span>

* [<span data-ttu-id="674b4-148">new</span><span class="sxs-lookup"><span data-stu-id="674b4-148">new</span></span>](dotnet-new.md)
* [<span data-ttu-id="674b4-149">restore</span><span class="sxs-lookup"><span data-stu-id="674b4-149">restore</span></span>](dotnet-restore.md)
* [<span data-ttu-id="674b4-150">build</span><span class="sxs-lookup"><span data-stu-id="674b4-150">build</span></span>](dotnet-build.md)
* [<span data-ttu-id="674b4-151">publish</span><span class="sxs-lookup"><span data-stu-id="674b4-151">publish</span></span>](dotnet-publish.md)
* [<span data-ttu-id="674b4-152">run</span><span class="sxs-lookup"><span data-stu-id="674b4-152">run</span></span>](dotnet-run.md)
* [<span data-ttu-id="674b4-153">test</span><span class="sxs-lookup"><span data-stu-id="674b4-153">test</span></span>](dotnet-test.md)
* [<span data-ttu-id="674b4-154">vstest</span><span class="sxs-lookup"><span data-stu-id="674b4-154">vstest</span></span>](dotnet-vstest.md)
* [<span data-ttu-id="674b4-155">pack</span><span class="sxs-lookup"><span data-stu-id="674b4-155">pack</span></span>](dotnet-pack.md)
* [<span data-ttu-id="674b4-156">migrate</span><span class="sxs-lookup"><span data-stu-id="674b4-156">migrate</span></span>](dotnet-migrate.md)
* [<span data-ttu-id="674b4-157">clean</span><span class="sxs-lookup"><span data-stu-id="674b4-157">clean</span></span>](dotnet-clean.md)
* [<span data-ttu-id="674b4-158">sln</span><span class="sxs-lookup"><span data-stu-id="674b4-158">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="674b4-159">**项目修改命令**</span><span class="sxs-lookup"><span data-stu-id="674b4-159">**Project modification commands**</span></span>

* [<span data-ttu-id="674b4-160">add package</span><span class="sxs-lookup"><span data-stu-id="674b4-160">add package</span></span>](dotnet-add-package.md)
* [<span data-ttu-id="674b4-161">add reference</span><span class="sxs-lookup"><span data-stu-id="674b4-161">add reference</span></span>](dotnet-add-reference.md)
* [<span data-ttu-id="674b4-162">remove package</span><span class="sxs-lookup"><span data-stu-id="674b4-162">remove package</span></span>](dotnet-remove-package.md)
* [<span data-ttu-id="674b4-163">remove reference</span><span class="sxs-lookup"><span data-stu-id="674b4-163">remove reference</span></span>](dotnet-remove-reference.md)
* [<span data-ttu-id="674b4-164">list reference</span><span class="sxs-lookup"><span data-stu-id="674b4-164">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="674b4-165">**高级命令**</span><span class="sxs-lookup"><span data-stu-id="674b4-165">**Advanced commands**</span></span>

* [<span data-ttu-id="674b4-166">nuget delete</span><span class="sxs-lookup"><span data-stu-id="674b4-166">nuget delete</span></span>](dotnet-nuget-delete.md)
* [<span data-ttu-id="674b4-167">nuget locals</span><span class="sxs-lookup"><span data-stu-id="674b4-167">nuget locals</span></span>](dotnet-nuget-locals.md)
* [<span data-ttu-id="674b4-168">nuget push</span><span class="sxs-lookup"><span data-stu-id="674b4-168">nuget push</span></span>](dotnet-nuget-push.md)
* [<span data-ttu-id="674b4-169">msbuild</span><span class="sxs-lookup"><span data-stu-id="674b4-169">msbuild</span></span>](dotnet-msbuild.md)
* [<span data-ttu-id="674b4-170">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="674b4-170">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="674b4-171">CLI 采用可使你为项目指定其他工具的扩展性模型。</span><span class="sxs-lookup"><span data-stu-id="674b4-171">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="674b4-172">有关详细信息，请参阅 [.NET Core CLI 扩展性模型](extensibility.md)主题。</span><span class="sxs-lookup"><span data-stu-id="674b4-172">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="674b4-173">命令结构</span><span class="sxs-lookup"><span data-stu-id="674b4-173">Command structure</span></span>

<span data-ttu-id="674b4-174">CLI 命令结构包含[驱动程序（“dotnet”）](#driver)、[命令（或“谓词”）](#command-verb)，或可能的命令[参数](#arguments)和[选项](#options)。</span><span class="sxs-lookup"><span data-stu-id="674b4-174">CLI command structure consists of [the driver ("dotnet")](#driver), [the command (or "verb")](#command-verb), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="674b4-175">在大部分 CLI 操作中可看到此模式，例如创建新控制台应用并从命令行运行该应用，因为从名为 *my_app* 的目录中执行时，显示以下命令：</span><span class="sxs-lookup"><span data-stu-id="674b4-175">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="674b4-176">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="674b4-176">.NET Core 2.x</span></span>](#tab/netcore2x)

```console
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="674b4-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="674b4-177">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="674b4-178">驱动程序</span><span class="sxs-lookup"><span data-stu-id="674b4-178">Driver</span></span>

<span data-ttu-id="674b4-179">驱动程序名为 [dotnet](dotnet.md)，并具有两项职责，即运行[依赖于框架的应用](../deploying/index.md)或执行命令。</span><span class="sxs-lookup"><span data-stu-id="674b4-179">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="674b4-180">若要运行依赖于框架的应用，请在驱动程序后指定应用，例如，`dotnet /path/to/my_app.dll`。</span><span class="sxs-lookup"><span data-stu-id="674b4-180">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="674b4-181">从应用的 DLL 驻留的文件夹执行命令时，只需执行 `dotnet my_app.dll` 即可。</span><span class="sxs-lookup"><span data-stu-id="674b4-181">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="674b4-182">如果要使用特定版本的 .NET Core 运行时，请使用 `--fx-version <VERSION>` 选项（请参阅 [dotnet 命令](dotnet.md)参考）。</span><span class="sxs-lookup"><span data-stu-id="674b4-182">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="674b4-183">为驱动程序提供命令时，`dotnet.exe` 启动 CLI 命令执行过程。</span><span class="sxs-lookup"><span data-stu-id="674b4-183">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="674b4-184">例如:</span><span class="sxs-lookup"><span data-stu-id="674b4-184">For example:</span></span>

```bash
> dotnet build
```

<span data-ttu-id="674b4-185">首先，驱动程序确定要使用的 SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="674b4-185">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="674b4-186">如果没有任何[“global.json”](global-json.md)，则使用可用的最新版本 SDK。</span><span class="sxs-lookup"><span data-stu-id="674b4-186">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="674b4-187">这有可能是预览版或稳定版，具体取决于计算机上的最新版本。</span><span class="sxs-lookup"><span data-stu-id="674b4-187">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="674b4-188">确定 SDK 版本后，它便会执行命令。</span><span class="sxs-lookup"><span data-stu-id="674b4-188">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command-verb"></a><span data-ttu-id="674b4-189">命令（“谓词”）</span><span class="sxs-lookup"><span data-stu-id="674b4-189">Command ("verb")</span></span>

<span data-ttu-id="674b4-190">命令（或“谓词”）仅仅是执行操作的命令。</span><span class="sxs-lookup"><span data-stu-id="674b4-190">The command (or "verb") is simply a command that performs an action.</span></span> <span data-ttu-id="674b4-191">例如，`dotnet build` 生成代码。</span><span class="sxs-lookup"><span data-stu-id="674b4-191">For example, `dotnet build` builds your code.</span></span> <span data-ttu-id="674b4-192">`dotnet publish` 发布代码。</span><span class="sxs-lookup"><span data-stu-id="674b4-192">`dotnet publish` publishes your code.</span></span> <span data-ttu-id="674b4-193">使用 `dotnet {verb}` 约定将命令作为控制台应用程序实现。</span><span class="sxs-lookup"><span data-stu-id="674b4-193">The commands are implemented as a console application using a `dotnet {verb}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="674b4-194">自变量</span><span class="sxs-lookup"><span data-stu-id="674b4-194">Arguments</span></span>

<span data-ttu-id="674b4-195">在命令行上传递的参数是被调用的命令的参数。</span><span class="sxs-lookup"><span data-stu-id="674b4-195">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="674b4-196">例如，执行 `dotnet publish my_app.csproj` 时，`my_app.csproj` 参数指示要发布的项目，并被传递到 `publish` 命令。</span><span class="sxs-lookup"><span data-stu-id="674b4-196">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="674b4-197">选项</span><span class="sxs-lookup"><span data-stu-id="674b4-197">Options</span></span>

<span data-ttu-id="674b4-198">在命令行上传递的选项是被调用的命令的选项。</span><span class="sxs-lookup"><span data-stu-id="674b4-198">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="674b4-199">例如，执行 `dotnet publish --output /build_output` 时，`--output` 选项及其值被传递到 `publish` 命令。</span><span class="sxs-lookup"><span data-stu-id="674b4-199">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="674b4-200">从 project.json 迁移</span><span class="sxs-lookup"><span data-stu-id="674b4-200">Migration from project.json</span></span>

<span data-ttu-id="674b4-201">如果使用预览版 2 工具生成基于 *project.json* 的项目，请查阅 [dotnet 迁移](dotnet-migrate.md)主题，了解将你的项目迁移到 MSBuild/*.csproj* 以使用版本工具的信息。</span><span class="sxs-lookup"><span data-stu-id="674b4-201">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="674b4-202">对于预览版 2 工具发布之前所创建的 .NET Core 项目，请按照[从 DNX 迁移到 .NET Core CLI (project.json)](../migration/from-dnx.md) 中的指南手动更新项目，然后使用 `dotnet migrate` 或直接升级项目。</span><span class="sxs-lookup"><span data-stu-id="674b4-202">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="674b4-203">请参阅</span><span class="sxs-lookup"><span data-stu-id="674b4-203">See also</span></span>

- [<span data-ttu-id="674b4-204">dotnet/CLI GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="674b4-204">dotnet/CLI GitHub Repository</span></span>](https://github.com/dotnet/cli/)
- [<span data-ttu-id="674b4-205">.NET Core 安装指南</span><span class="sxs-lookup"><span data-stu-id="674b4-205">.NET Core installation guide</span></span>](https://aka.ms/dotnetcoregs)
