---
title: .NET Core 2.1 的新增功能
description: 了解 .NET Core 2.1 的新增功能。
author: rpetrusha
ms.author: ronpet
ms.date: 06/06/2018
ms.openlocfilehash: ec9a8d238dc47f604a1ac0ee7628bf079e89b9c2
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935574"
---
# <a name="whats-new-in-net-core-21"></a><span data-ttu-id="a22f5-103">.NET Core 2.1 的新增功能</span><span class="sxs-lookup"><span data-stu-id="a22f5-103">What's new in .NET Core 2.1</span></span>

<span data-ttu-id="a22f5-104">.NET Core 2.1 提供以下几个方面的增强功能和新功能：</span><span class="sxs-lookup"><span data-stu-id="a22f5-104">.NET Core 2.1 includes enhancements and new features in the following areas:</span></span>

- [<span data-ttu-id="a22f5-105">工具</span><span class="sxs-lookup"><span data-stu-id="a22f5-105">Tooling</span></span>](#tooling)
- [<span data-ttu-id="a22f5-106">前滚</span><span class="sxs-lookup"><span data-stu-id="a22f5-106">Roll forward</span></span>](#roll-forward)
- [<span data-ttu-id="a22f5-107">部署</span><span class="sxs-lookup"><span data-stu-id="a22f5-107">Deployment</span></span>](#deployment)
- [<span data-ttu-id="a22f5-108">Windows 兼容包</span><span class="sxs-lookup"><span data-stu-id="a22f5-108">Windows Compatibility Pack</span></span>](#windows-compatibility-pack)
- [<span data-ttu-id="a22f5-109">JIT 编译改进</span><span class="sxs-lookup"><span data-stu-id="a22f5-109">JIT compilation improvements</span></span>](#jit-compiler-improvements)
- [<span data-ttu-id="a22f5-110">API 更改</span><span class="sxs-lookup"><span data-stu-id="a22f5-110">API changes</span></span>](#api-changes)

## <a name="tooling"></a><span data-ttu-id="a22f5-111">工具</span><span class="sxs-lookup"><span data-stu-id="a22f5-111">Tooling</span></span>

<span data-ttu-id="a22f5-112">.NET Core 2.1 SDK (v 2.1.300)，该工具与 .NET Core 2.1 一起提供，包括以下更改和增强功能：</span><span class="sxs-lookup"><span data-stu-id="a22f5-112">The .NET Core 2.1 SDK (v 2.1.300), the tooling included with .NET Core 2.1, includes the following changes and enhancements:</span></span>

### <a name="build-performance-improvements"></a><span data-ttu-id="a22f5-113">生成性能改进</span><span class="sxs-lookup"><span data-stu-id="a22f5-113">Build performance improvements</span></span>

<span data-ttu-id="a22f5-114">.NET Core 2.1 的主要关注点是改进生成时性能，特别是增量生成。</span><span class="sxs-lookup"><span data-stu-id="a22f5-114">A major focus of .NET Core 2.1 is improving build-time performance, particularly for incremental builds.</span></span> <span data-ttu-id="a22f5-115">这些性能改进适用于使用 `dotnet build` 的两个命令行生成和 Visual Studio 中的生成。</span><span class="sxs-lookup"><span data-stu-id="a22f5-115">These performance improvements apply to both command-line builds using `dotnet build` and to builds in Visual Studio.</span></span> <span data-ttu-id="a22f5-116">一些个别的改进领域包括：</span><span class="sxs-lookup"><span data-stu-id="a22f5-116">Some individual areas of improvement include:</span></span>

- <span data-ttu-id="a22f5-117">对于包资产解决方法，只解决由生成使用的资产而不是所有资产。</span><span class="sxs-lookup"><span data-stu-id="a22f5-117">For package asset resolution, resolving only assets used by a build rather than all assets.</span></span>

- <span data-ttu-id="a22f5-118">程序集引用缓存。</span><span class="sxs-lookup"><span data-stu-id="a22f5-118">Caching of assembly references.</span></span>

- <span data-ttu-id="a22f5-119">使用长时间运行的 SDK 生成服务器，这些是跨各个 `dotnet build` 调用的过程。</span><span class="sxs-lookup"><span data-stu-id="a22f5-119">Use of long-running SDK build servers, which are processes that span across individual `dotnet build` invocations.</span></span> <span data-ttu-id="a22f5-120">每次 `dotnet build` 运行时不再需要 JIT 编译大量代码块。</span><span class="sxs-lookup"><span data-stu-id="a22f5-120">They eliminate the need to JIT-compile large blocks of code every time `dotnet build` is run.</span></span> <span data-ttu-id="a22f5-121">生成服务器进程可以使用以下命令自动终止：</span><span class="sxs-lookup"><span data-stu-id="a22f5-121">Build server processes can be automatically terminated with the following command:</span></span>

   ```console
   dotnet buildserver shutdown
   ```

### <a name="new-cli-commands"></a><span data-ttu-id="a22f5-122">新的 CLI 命令</span><span class="sxs-lookup"><span data-stu-id="a22f5-122">New CLI commands</span></span>

<span data-ttu-id="a22f5-123">许多使用 [`DotnetCliToolReference`](../tools/extensibility.md) 的仅在每个项目的基础上可用的工具现作为 .NET Core SDK 的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="a22f5-123">A number of tools that were available only on a per project basis using [`DotnetCliToolReference`](../tools/extensibility.md) are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="a22f5-124">这些工具包括：</span><span class="sxs-lookup"><span data-stu-id="a22f5-124">These tools include:</span></span>

- <span data-ttu-id="a22f5-125">`dotnet watch` 提供文件系统观察程序，该程序在执行指定的命令集之前会首先等待文件更改。</span><span class="sxs-lookup"><span data-stu-id="a22f5-125">`dotnet watch` provides a file system watcher that waits for a file to change before executing a designated set of commands.</span></span> <span data-ttu-id="a22f5-126">例如，下面的命令将自动重新生成当前项目，并在其中的文件发生更改时生成详细输出：</span><span class="sxs-lookup"><span data-stu-id="a22f5-126">For example, the following command automatically rebuilds the current project and generates verbose output whenever a file in it changes:</span></span>

   ```console
   dotnet watch -- --verbose build
   ```
  
   <span data-ttu-id="a22f5-127">请注意 `--verbose` 选项前面的 `--` 选项。</span><span class="sxs-lookup"><span data-stu-id="a22f5-127">Note the `--` option that precedes the `--verbose` option.</span></span> <span data-ttu-id="a22f5-128">它分隔从传递给子 `dotnet` 进程的参数直接传递到 `dotnet watch` 命令的选项。</span><span class="sxs-lookup"><span data-stu-id="a22f5-128">It delimits the options passed directly to the `dotnet watch` command from the arguments that are passed to the child `dotnet` process.</span></span> <span data-ttu-id="a22f5-129">如果没有该选项，`--verbose` 选项将适用于 `dotnet watch` 命令，而非 `dotnet build` 命令。</span><span class="sxs-lookup"><span data-stu-id="a22f5-129">Without it, the `--verbose` option applies to the `dotnet watch` command, not the `dotnet build` command.</span></span>
  
   <span data-ttu-id="a22f5-130">有关详细信息，请参阅[使用 dotnet watch 开发 ASP.NET Core 应用](/aspnet/core/tutorials/dotnet-watch)</span><span class="sxs-lookup"><span data-stu-id="a22f5-130">For more information, see [Develop ASP.NET Core apps using dotnet watch](/aspnet/core/tutorials/dotnet-watch)</span></span>

- <span data-ttu-id="a22f5-131">`dotnet dev-certs` 生成和管理在 ASP.NET Core 应用程序开发期间使用的证书。</span><span class="sxs-lookup"><span data-stu-id="a22f5-131">`dotnet dev-certs` generates and manages certificates used during development in ASP.NET Core applications.</span></span>

- <span data-ttu-id="a22f5-132">`dotnet user-secrets` 管理 ASP.NET Core 应用程序中用户机密库的机密。</span><span class="sxs-lookup"><span data-stu-id="a22f5-132">`dotnet user-secrets` manages the secrets in a user secret store in ASP.NET Core applications.</span></span>

- <span data-ttu-id="a22f5-133">`dotnet sql-cache` 在 Microsoft SQL Server 数据库中创建表和索引以用于分布式缓存。</span><span class="sxs-lookup"><span data-stu-id="a22f5-133">`dotnet sql-cache` creates a table and indexes in a Microsoft SQL Server database to be used for distributed caching.</span></span>

- <span data-ttu-id="a22f5-134">`dotnet ef` 是用于管理 Entity Framework Core 应用程序中数据库、<xref:Microsoft.EntityFrameworkCore.DbContext> 对象和迁移的工具。</span><span class="sxs-lookup"><span data-stu-id="a22f5-134">`dotnet ef` is a tool for managing databases, <xref:Microsoft.EntityFrameworkCore.DbContext> objects, and migrations in Entity Framework Core applications.</span></span> <span data-ttu-id="a22f5-135">有关详细信息，请参阅 [EF Core .NET 命令行工具](/ef/core/miscellaneous/cli/dotnet)。</span><span class="sxs-lookup"><span data-stu-id="a22f5-135">For more information, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

### <a name="global-tools"></a><span data-ttu-id="a22f5-136">全局工具</span><span class="sxs-lookup"><span data-stu-id="a22f5-136">Global Tools</span></span>

<span data-ttu-id="a22f5-137">.NET Core 2.1 支持全局工具，即，可通过命令行在全局范围内使用的自定义工具。</span><span class="sxs-lookup"><span data-stu-id="a22f5-137">.NET Core 2.1 supports *Global Tools* -- that is, custom tools that are available globally from the command line.</span></span> <span data-ttu-id="a22f5-138">以前版本的 .NET Core 中的扩展性模型只能通过使用 [`DotnetCliToolReference`](../tools/extensibility.md#consuming-per-project-tools) 在每个项目的基础上提供自定义工具。</span><span class="sxs-lookup"><span data-stu-id="a22f5-138">The extensibility model in previous versions of .NET Core made custom tools available on a per project basis only by using [`DotnetCliToolReference`](../tools/extensibility.md#consuming-per-project-tools).</span></span>

<span data-ttu-id="a22f5-139">若要安装全局工具，请使用 [dotnet tool install](..\tools\dotnet-tool-install.md) 命令。</span><span class="sxs-lookup"><span data-stu-id="a22f5-139">To install a Global Tool, you use the [dotnet tool install](..\tools\dotnet-tool-install.md) command.</span></span> <span data-ttu-id="a22f5-140">例如:</span><span class="sxs-lookup"><span data-stu-id="a22f5-140">For example:</span></span>

```console
dotnet tool install -g dotnetsay
```

<span data-ttu-id="a22f5-141">完成安装后，可以通过指定工具名称从命令行运行该工具。</span><span class="sxs-lookup"><span data-stu-id="a22f5-141">Once installed, the tool can be run from the command line by specifying the tool name.</span></span> <span data-ttu-id="a22f5-142">有关详细信息，请参阅 [.NET Core 工具概述](../tools/global-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="a22f5-142">For more information, see [.NET Core Global Tools overview](../tools/global-tools.md).</span></span>

### <a name="tool-management-with-the-dotnet-tool-command"></a><span data-ttu-id="a22f5-143">使用 `dotnet tool` 命令管理工具</span><span class="sxs-lookup"><span data-stu-id="a22f5-143">Tool management with the `dotnet tool` command</span></span>

<span data-ttu-id="a22f5-144">在.NET Core SDK 2.1 (v 2.1.300)，所有工具操作都使用 `dotnet tool` 命令。</span><span class="sxs-lookup"><span data-stu-id="a22f5-144">In .NET Core SDK 2.1 (v 2.1.300), all tools operations use the `dotnet tool` command.</span></span> <span data-ttu-id="a22f5-145">可用选项如下：</span><span class="sxs-lookup"><span data-stu-id="a22f5-145">The following options are available:</span></span>

- <span data-ttu-id="a22f5-146">[`dotnet tool install`](../tools/dotnet-tool-install.md) 安装工具。</span><span class="sxs-lookup"><span data-stu-id="a22f5-146">[`dotnet tool install`](../tools/dotnet-tool-install.md) to install a tool.</span></span>

- <span data-ttu-id="a22f5-147">[`dotnet tool update`](../tools/dotnet-tool-update.md) 卸载并重新安装工具，它将高效地对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="a22f5-147">[`dotnet tool update`](../tools/dotnet-tool-update.md) to uninstall and reinstall a tool, which effectively updates it.</span></span>

- <span data-ttu-id="a22f5-148">[`dotnet tool list`](../tools/dotnet-tool-list.md) 列出当前安装的工具。</span><span class="sxs-lookup"><span data-stu-id="a22f5-148">[`dotnet tool list`](../tools/dotnet-tool-list.md) to list currently installed tools.</span></span>

- <span data-ttu-id="a22f5-149">[`dotnet tool uninstall`](../tools/dotnet-tool-uninstall.md) 卸载当前安装的工具。</span><span class="sxs-lookup"><span data-stu-id="a22f5-149">[`dotnet tool uninstall`](../tools/dotnet-tool-uninstall.md) to uninstall currently installed tools.</span></span>

## <a name="roll-forward"></a><span data-ttu-id="a22f5-150">前滚</span><span class="sxs-lookup"><span data-stu-id="a22f5-150">Roll forward</span></span>

<span data-ttu-id="a22f5-151">从 .NET Core 2.0 开始，所有 .NET Core 应用程序都将自动前滚到系统上安装的最新次要版本。</span><span class="sxs-lookup"><span data-stu-id="a22f5-151">All .NET Core applications starting with the .NET Core 2.0 automatically roll forward to the latest *minor version* installed on a system.</span></span> 

<span data-ttu-id="a22f5-152">从 .NET Core 2.0 开始，如果在其中构建应用程序的 .NET Core 版本在运行时不存在，应用程序将针对最新安装的次要版本的 .NET Core 自动运行。</span><span class="sxs-lookup"><span data-stu-id="a22f5-152">Starting with .NET Core 2.0, if the version of .NET Core that an application was built with is not present at runtime, the application automatically runs against the latest installed *minor version* of .NET Core.</span></span> <span data-ttu-id="a22f5-153">换而言之，如果应用程序在 .NET Core 2.0 中生成，而主机系统未安装 .NET Core 2.0 但安装了 .NET Core 2.1，则应用程序将通过 .NET Core 2.1 运行。</span><span class="sxs-lookup"><span data-stu-id="a22f5-153">In other words, if an application is built with .NET Core 2.0, and .NET Core 2.0 is not present on the host system but .NET Core 2.1 is, the application runs with .NET Core 2.1.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a22f5-154">此前滚行为不适用于预览版本。</span><span class="sxs-lookup"><span data-stu-id="a22f5-154">This roll-forward behavior doesn't apply to preview releases.</span></span> <span data-ttu-id="a22f5-155">也不适用于主要版本。</span><span class="sxs-lookup"><span data-stu-id="a22f5-155">Nor does it apply to major releases.</span></span> <span data-ttu-id="a22f5-156">例如，.NET Core 1.0 应用程序不会将前滚到 .NET Core 2.0 或 .NET Core 2.1。</span><span class="sxs-lookup"><span data-stu-id="a22f5-156">For example, a .NET Core 1.0 application wouldn't roll forward to .NET Core 2.0 or .NET Core 2.1.</span></span>

<span data-ttu-id="a22f5-157">你也可以通过以下任意三种方式禁用次要版本前滚：</span><span class="sxs-lookup"><span data-stu-id="a22f5-157">You can also disable minor version roll forward in any of three ways:</span></span>

- <span data-ttu-id="a22f5-158">将 `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` 环境变量设置为 0。</span><span class="sxs-lookup"><span data-stu-id="a22f5-158">Set the `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` environment variable to 0.</span></span>

- <span data-ttu-id="a22f5-159">将以下行添加到 runtimeconfig.json 文件：</span><span class="sxs-lookup"><span data-stu-id="a22f5-159">Add the following line to the runtimeconfig.json file:</span></span>

   ```json
   "rollForwardOnNoCandidateFx" : 0
   ```

- <span data-ttu-id="a22f5-160">使用 [.NET Core CLI 工具](../tools/index.md)时，请使用 .NET Core 命令（如 `run`）包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="a22f5-160">When using [.NET Core CLI tools](../tools/index.md), include the following option with a .NET Core command such as `run`:</span></span>

   ```console
   dotnet run --rollForwardOnNoCandidateFx=0
   ```

## <a name="deployment"></a><span data-ttu-id="a22f5-161">部署</span><span class="sxs-lookup"><span data-stu-id="a22f5-161">Deployment</span></span>

### <a name="self-contained-application-servicing"></a><span data-ttu-id="a22f5-162">自包含应用程序服务</span><span class="sxs-lookup"><span data-stu-id="a22f5-162">Self-contained application servicing</span></span>

<span data-ttu-id="a22f5-163">`dotnet publish` 现发布服务运行时版本的自包含应用程序。</span><span class="sxs-lookup"><span data-stu-id="a22f5-163">`dotnet publish` now publishes self-contained applications with a serviced runtime version.</span></span> <span data-ttu-id="a22f5-164">当你使用 .NET Core 2.1 SDK (v 2.1.300) 发布自包含应用程序时，你的应用程序将包括此 SDK 已知的最新服务运行时版本。</span><span class="sxs-lookup"><span data-stu-id="a22f5-164">When you publish a self-contained application with the .NET Core 2.1 SDK (v 2.1.300), your application includes the latest serviced runtime version known by that SDK.</span></span> <span data-ttu-id="a22f5-165">当升级到最新的 SDK，将发布最新的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="a22f5-165">When you upgrade to the latest SDK, you’ll publish with the latest .NET Core runtime version.</span></span> <span data-ttu-id="a22f5-166">这适用于 .NET Core 1.0 运行时以及更高版本。</span><span class="sxs-lookup"><span data-stu-id="a22f5-166">This applies for .NET Core 1.0 runtimes and later.</span></span>

<span data-ttu-id="a22f5-167">自包含发布依赖于 NuGet.org 上的运行时版本。计算机上不需要有服务运行时。</span><span class="sxs-lookup"><span data-stu-id="a22f5-167">Self-contained publishing relies on runtime versions on NuGet.org. You do not need to have the serviced runtime on your machine.</span></span>

<span data-ttu-id="a22f5-168">使用 .NET Core 2.0 SDK，自包含应用程序将通过 .NET Core 2.0.0 运行时发布，除非通过 `RuntimeFrameworkVersion` 属性指定不同版本。</span><span class="sxs-lookup"><span data-stu-id="a22f5-168">Using the .NET Core 2.0 SDK, self-contained applications are published with the .NET Core 2.0.0 runtime unless a different version is specified via the `RuntimeFrameworkVersion` property.</span></span> <span data-ttu-id="a22f5-169">借助此新行为，你将不再需要设置此属性便可为自包含的应用程序选择更高版本的运行时。</span><span class="sxs-lookup"><span data-stu-id="a22f5-169">With this new behavior, you’ll no longer need to set this property to select a higher runtime version for a self-contained application.</span></span> <span data-ttu-id="a22f5-170">最简单的方法是始终通过 .NET Core 2.1 SDK (v 2.1.300) 发布。</span><span class="sxs-lookup"><span data-stu-id="a22f5-170">The easiest approach going forward is to always publish with .NET Core 2.1 SDK (v 2.1.300).</span></span>

## <a name="windows-compatibility-pack"></a><span data-ttu-id="a22f5-171">Windows 兼容包</span><span class="sxs-lookup"><span data-stu-id="a22f5-171">Windows Compatibility Pack</span></span>

<span data-ttu-id="a22f5-172">当你将现有代码从 .NET Framework 转移到 .NET Core 时，可以使用 [Windows 兼容包](https://www.nuget.org/packages/Microsoft.Windows.Compatibility)。</span><span class="sxs-lookup"><span data-stu-id="a22f5-172">When you port existing code from the .NET Framework to .NET Core, you can use the [Windows Compatibility Pack](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span> <span data-ttu-id="a22f5-173">除了 .NET Core 中提供的 API，它使你还能够访问额外的 20,000 多个 API。</span><span class="sxs-lookup"><span data-stu-id="a22f5-173">It provides access to 20,000 more APIs than are available in .NET Core.</span></span> <span data-ttu-id="a22f5-174">这些 API 包括 <xref:System.Drawing?displayProperty=nameWithType> 命名空间中的类型、<xref:System.Diagnostics.EventLog> 类、WMI、性能计数器、Windows 服务以及 Windows 注册表类型和成员。</span><span class="sxs-lookup"><span data-stu-id="a22f5-174">These APIs include types in the <xref:System.Drawing?displayProperty=nameWithType> namespace, the <xref:System.Diagnostics.EventLog> class, WMI, Performance Counters, Windows Services, and the Windows registry types and members.</span></span>

## <a name="jit-compiler-improvements"></a><span data-ttu-id="a22f5-175">JIT 编译器改进</span><span class="sxs-lookup"><span data-stu-id="a22f5-175">JIT compiler improvements</span></span>

<span data-ttu-id="a22f5-176">.NET Core 包含新的 JIT 编译器技术，称为“分层编译”（也称为“自适应优化”），可以显著提高性能。</span><span class="sxs-lookup"><span data-stu-id="a22f5-176">.NET Core incorporates a new JIT compiler technology called *tiered compilation* (also known as *adaptive optimization*) that can significantly improve performance.</span></span> <span data-ttu-id="a22f5-177">分层编译是一个可选设置。</span><span class="sxs-lookup"><span data-stu-id="a22f5-177">Tiered compilation is an opt-in setting.</span></span>

<span data-ttu-id="a22f5-178">由 JIT 编译器执行的重要任务之一是优化代码执行。</span><span class="sxs-lookup"><span data-stu-id="a22f5-178">One of the important tasks performed by the JIT compiler is optimizing code execution.</span></span> <span data-ttu-id="a22f5-179">然而，对于很少使用的代码路径，相比运行未优化代码所花费的运行时，编译器可能需要更多的时间来优化代码。</span><span class="sxs-lookup"><span data-stu-id="a22f5-179">For little-used code paths, however, the compiler may spend more time optimizing code than the runtime spends running unoptimized code.</span></span> <span data-ttu-id="a22f5-180">分层编译介绍了 JIT 编译中的两个阶段：</span><span class="sxs-lookup"><span data-stu-id="a22f5-180">Tiered compilation introduces two stages in JIT compilation:</span></span>

- <span data-ttu-id="a22f5-181">第一层，将尽可能快地生成代码。</span><span class="sxs-lookup"><span data-stu-id="a22f5-181">A **first tier**, which generates code as quickly as possible.</span></span>

- <span data-ttu-id="a22f5-182">第二层，将为那些频繁执行的方法生成优化代码。</span><span class="sxs-lookup"><span data-stu-id="a22f5-182">A **second tier**, which generates optimized code for those methods that are executed frequently.</span></span> <span data-ttu-id="a22f5-183">为了增强性能，第二层编译并行执行。</span><span class="sxs-lookup"><span data-stu-id="a22f5-183">The second tier of compilation is performed in parallel for enhanced performance.</span></span>

<span data-ttu-id="a22f5-184">可以通过这两种方法之一选择加入分层编译。</span><span class="sxs-lookup"><span data-stu-id="a22f5-184">You can opt into tiered compilation in either of two ways.</span></span>

- <span data-ttu-id="a22f5-185">若要在所有使用 .NET Core 2.1 SDK 的项目中使用分层编译，请设置以下环境变量：</span><span class="sxs-lookup"><span data-stu-id="a22f5-185">To use tiered compilation in all projects that use the .NET Core 2.1 SDK, set the following environment variable:</span></span>

  ```console
  COMPlus_TieredCompilation="1"
  ```

- <span data-ttu-id="a22f5-186">若要在每个项目的基础上使用分层编译，将 `<TieredCompilation>` 属性添加到 MSBuild 项目文件的 `<PropertyGroup>` 部分，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="a22f5-186">To use tiered compilation on a per-project basis, add the `<TieredCompilation>` property to the `<PropertyGroup>` section of the MSBuild project file, as the following example shows:</span></span>

   ```xml
   <PropertyGroup>
      <!-- other property definitions -->

      <TieredCompilation>true</TieredCompilation>
   </PropertyGroup>
   ```

## <a name="api-changes"></a><span data-ttu-id="a22f5-187">API 更改</span><span class="sxs-lookup"><span data-stu-id="a22f5-187">API changes</span></span>

### <a name="spant-and-memoryt"></a><span data-ttu-id="a22f5-188">`Span<T>` 和 `Memory<T>`</span><span class="sxs-lookup"><span data-stu-id="a22f5-188">`Span<T>` and `Memory<T>`</span></span>

<span data-ttu-id="a22f5-189">.NET Core 2.1 包括一些新类型，使得在使用数组和其他类型内存方面要高效得多。</span><span class="sxs-lookup"><span data-stu-id="a22f5-189">.NET Core 2.1 includes some new types that make working with arrays and other types of memory much more efficient.</span></span> <span data-ttu-id="a22f5-190">新类型包括：</span><span class="sxs-lookup"><span data-stu-id="a22f5-190">The new types include:</span></span>

- <span data-ttu-id="a22f5-191"><xref:System.Span%601?displayProperty=nameWithType> 和 <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="a22f5-191"><xref:System.Span%601?displayProperty=nameWithType> and <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="a22f5-192"><xref:System.Memory%601?displayProperty=nameWithType> 和 <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="a22f5-192"><xref:System.Memory%601?displayProperty=nameWithType> and <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="a22f5-193">如果没有这些类型，那么在作为数组的一部分或内存缓冲区的一部分传递此类项时，必须在将数据的某些部分传递给方法之前复制该数据部分。</span><span class="sxs-lookup"><span data-stu-id="a22f5-193">Without these types, when passing such items as a portion of an array or a section of a memory buffer, you have to make a copy of some portion of the data before passing it to a method.</span></span> <span data-ttu-id="a22f5-194">这些类型提供了该数据的虚拟视图，无需额外的内存分配和复制操作。</span><span class="sxs-lookup"><span data-stu-id="a22f5-194">These types provide a virtual view of that data that eliminates the need for the additional memory allocation and copy operations.</span></span>

<span data-ttu-id="a22f5-195">下面的示例使用 <xref:System.Span%601> 实例来提供一个数组 10 个元素的虚拟视图。</span><span class="sxs-lookup"><span data-stu-id="a22f5-195">The following example uses a <xref:System.Span%601> instance to provide a virtual view of 10 elements of an array.</span></span>

[!CODE-csharp[Span\<T>](~/samples/core/whats-new/whats-new-in-21/cs/program.cs)]

### <a name="brotli-compression"></a><span data-ttu-id="a22f5-196">Brotli 压缩</span><span class="sxs-lookup"><span data-stu-id="a22f5-196">Brotli compression</span></span>

<span data-ttu-id="a22f5-197">.NET Core 2.1 添加了对 Brotli 压缩和解压缩的支持。</span><span class="sxs-lookup"><span data-stu-id="a22f5-197">.NET Core 2.1 adds support for Brotli compression and decompression.</span></span> <span data-ttu-id="a22f5-198">Brotli 是在 [RFC 7932](https://www.ietf.org/rfc/rfc7932.txt) 中定义的通用无损压缩算法，并且大多数 Web 浏览器和主 Web 服务器都提供支持。</span><span class="sxs-lookup"><span data-stu-id="a22f5-198">Brotli is a general-purpose lossless compression algorithm that is defined in [RFC 7932](https://www.ietf.org/rfc/rfc7932.txt) and is supported by most web browsers and major web servers.</span></span> <span data-ttu-id="a22f5-199">可以使用基于流的 <xref:System.IO.Compression.BrotliStream?displayProperty=nameWithType> 类或基于范围的高性能 <xref:System.IO.Compression.BrotliEncoder?displayProperty=nameWithType> 和 <xref:System.IO.Compression.BrotliDecoder?displayProperty=nameWithType> 类。</span><span class="sxs-lookup"><span data-stu-id="a22f5-199">You can use the stream-based <xref:System.IO.Compression.BrotliStream?displayProperty=nameWithType> class or the high-performance span-based <xref:System.IO.Compression.BrotliEncoder?displayProperty=nameWithType> and <xref:System.IO.Compression.BrotliDecoder?displayProperty=nameWithType> classes.</span></span> <span data-ttu-id="a22f5-200">下面的示例用 <xref:System.IO.Compression.BrotliStream> 类演示压缩：</span><span class="sxs-lookup"><span data-stu-id="a22f5-200">The following example illustrates compression with the <xref:System.IO.Compression.BrotliStream> class:</span></span>

[!CODE-csharp[Brotli compression](~/samples/core/whats-new/whats-new-in-21/cs/brotli.cs#1)]

<span data-ttu-id="a22f5-201"><xref:System.IO.Compression.BrotliStream> 行为等同于 <xref:System.IO.Compression.DeflateStream> 和 <xref:System.IO.Compression.GZipStream>，这样就可以轻松地将调用这些 API 的代码转换为 <xref:System.IO.Compression.BrotliStream>。</span><span class="sxs-lookup"><span data-stu-id="a22f5-201">The <xref:System.IO.Compression.BrotliStream> behavior is the same as <xref:System.IO.Compression.DeflateStream> and <xref:System.IO.Compression.GZipStream>, which makes it easy to convert code that calls these APIs to <xref:System.IO.Compression.BrotliStream>.</span></span>

### <a name="new-cryptography-apis-and-cryptography-improvements"></a><span data-ttu-id="a22f5-202">新加密 API 和加密改进</span><span class="sxs-lookup"><span data-stu-id="a22f5-202">New cryptography APIs and cryptography improvements</span></span>

<span data-ttu-id="a22f5-203">.NET Core 2.1 包括加密 API 的许多增强功能：</span><span class="sxs-lookup"><span data-stu-id="a22f5-203">.NET Core 2.1 includes numerous enhancements to the cryptography APIs:</span></span>

- <span data-ttu-id="a22f5-204"><xref:System.Security.Cryptography.Pkcs.SignedCms?displayProperty=nameWithType> 在 System.Security.Cryptography.Pkcs 包中提供。</span><span class="sxs-lookup"><span data-stu-id="a22f5-204"><xref:System.Security.Cryptography.Pkcs.SignedCms?displayProperty=nameWithType> is available in the System.Security.Cryptography.Pkcs package.</span></span> <span data-ttu-id="a22f5-205">其实现与 .NET Framework 中的 <xref:System.Security.Cryptography.Pkcs.SignedCms> 类相同。</span><span class="sxs-lookup"><span data-stu-id="a22f5-205">The implementation is the same as the <xref:System.Security.Cryptography.Pkcs.SignedCms> class in the .NET Framework.</span></span>

- <span data-ttu-id="a22f5-206"><xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHash%2A?displayProperty=nameWithType> 和 <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHashString%2A?displayProperty=nameWithType> 方法的新重载接受一个哈希算法标识符，使调用方能够使用除 SHA-1 以外的算法获得证书指纹值。</span><span class="sxs-lookup"><span data-stu-id="a22f5-206">New overloads of the <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHash%2A?displayProperty=nameWithType> and <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHashString%2A?displayProperty=nameWithType> methods accept a hash algorithm identifier to enable callers to get certificate thumbprint values using algorithms other than SHA-1.</span></span>

- <span data-ttu-id="a22f5-207">新的基于 <xref:System.Span%601> 的加密 API 可用于哈希、HMAC、加密随机数生成、非对称签名生成、非对称签名处理和 RSA 加密。</span><span class="sxs-lookup"><span data-stu-id="a22f5-207">New <xref:System.Span%601>-based cryptography APIs are available for hashing, HMAC, cryptographic random number generation, asymmetric signature generation, asymmetric signature processing, and RSA encryption.</span></span>

- <span data-ttu-id="a22f5-208">通过使用基于 <xref:System.Span%601> 的实现，<xref:System.Security.Cryptography.Rfc2898DeriveBytes?displayProperty=nameWithType> 的性能提高了大约 15%。</span><span class="sxs-lookup"><span data-stu-id="a22f5-208">The performance of <xref:System.Security.Cryptography.Rfc2898DeriveBytes?displayProperty=nameWithType> has improved by about 15% by using a <xref:System.Span%601>-based implementation.</span></span>

- <span data-ttu-id="a22f5-209">新 <xref:System.Security.Cryptography.CryptographicOperations?displayProperty=nameWithType> 类包括两个新方法：</span><span class="sxs-lookup"><span data-stu-id="a22f5-209">The new <xref:System.Security.Cryptography.CryptographicOperations?displayProperty=nameWithType> class includes two new methods:</span></span>

  - <span data-ttu-id="a22f5-210"><xref:System.Security.Cryptography.CryptographicOperations.FixedTimeEquals%2A> 需要固定时间来返回任意两个长度相同的输入，这使得它适用于加密验证，从而避免提供计时旁道信息。</span><span class="sxs-lookup"><span data-stu-id="a22f5-210"><xref:System.Security.Cryptography.CryptographicOperations.FixedTimeEquals%2A> takes a fixed amount of time to return for any two inputs of the same length, which makes it suitable for use in cryptographic verification to avoid contributing to timing side-channel information.</span></span>

  - <span data-ttu-id="a22f5-211"><xref:System.Security.Cryptography.CryptographicOperations.ZeroMemory%2A> 是不能进行优化的内存清理例程。</span><span class="sxs-lookup"><span data-stu-id="a22f5-211"><xref:System.Security.Cryptography.CryptographicOperations.ZeroMemory%2A> is a memory-clearing routine that cannot be optimized.</span></span>

- <span data-ttu-id="a22f5-212">静态 <xref:System.Security.Cryptography.RandomNumberGenerator.Fill%2A?displayProperty=nameWithType> 方法用随机值填充 <xref:System.Span%601>。</span><span class="sxs-lookup"><span data-stu-id="a22f5-212">The static <xref:System.Security.Cryptography.RandomNumberGenerator.Fill%2A?displayProperty=nameWithType> method fills a <xref:System.Span%601> with random values.</span></span>

- <span data-ttu-id="a22f5-213"><xref:System.Security.Cryptography.Pkcs.EnvelopedCms?displayProperty=nameWithType> 现在在 Linux 和 maxOS 上受支持。</span><span class="sxs-lookup"><span data-stu-id="a22f5-213">The <xref:System.Security.Cryptography.Pkcs.EnvelopedCms?displayProperty=nameWithType> is now supported on Linux and maxOS.</span></span>

- <span data-ttu-id="a22f5-214"><xref:System.Security.Cryptography.ECDiffieHellman?displayProperty=nameWithType> 类系列现提供椭圆曲线 Diffie-Hellman (ECDH)。</span><span class="sxs-lookup"><span data-stu-id="a22f5-214">Elliptic-Curve Diffie-Hellman (ECDH) is now available in the <xref:System.Security.Cryptography.ECDiffieHellman?displayProperty=nameWithType> class family.</span></span> <span data-ttu-id="a22f5-215">外围应用与 .NET Framework 中相同。</span><span class="sxs-lookup"><span data-stu-id="a22f5-215">The surface area is the same as in the .NET Framework.</span></span>

- <span data-ttu-id="a22f5-216"><xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> 返回的实例可以使用 SHA-2 摘要对 OAEP 进行加密或解密，并使用 RSA-PSS 生成或验证签名。</span><span class="sxs-lookup"><span data-stu-id="a22f5-216">The instance returned by <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> can encrypt or decrypt with OAEP using a SHA-2 digest, as well as generate or validate signatures using RSA-PSS.</span></span>

### <a name="sockets-improvements"></a><span data-ttu-id="a22f5-217">套接字改进</span><span class="sxs-lookup"><span data-stu-id="a22f5-217">Sockets improvements</span></span>

<span data-ttu-id="a22f5-218">.NET Core 包括一个新类型 <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> 和重写的 <xref:System.Net.Http.HttpMessageHandler?displayProperty=nameWithType>，两者构成了更高级别网络 API 的基础。</span><span class="sxs-lookup"><span data-stu-id="a22f5-218">.NET Core includes a new type, <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>, and a rewritten <xref:System.Net.Http.HttpMessageHandler?displayProperty=nameWithType>, that form the basis of higher-level networking APIs.</span></span>  <span data-ttu-id="a22f5-219">例如，<xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> 是 <xref:System.Net.Http.HttpClient> 实现的基础。</span><span class="sxs-lookup"><span data-stu-id="a22f5-219"><xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>, for example, is the basis of the <xref:System.Net.Http.HttpClient> implementation.</span></span> <span data-ttu-id="a22f5-220">在以前版本的 .NET Core 中，更高级别的 API 基于本机网络实现。</span><span class="sxs-lookup"><span data-stu-id="a22f5-220">In previous versions of .NET Core, higher-level APIs were based on native networking implementations.</span></span>

<span data-ttu-id="a22f5-221">.NET Core 2.1 中引入的套接字实现具有很多优点：</span><span class="sxs-lookup"><span data-stu-id="a22f5-221">The sockets implementation introduced in .NET Core 2.1 has a number of advantages:</span></span>

- <span data-ttu-id="a22f5-222">对照以前的实现，可以看到显著的性能改进。</span><span class="sxs-lookup"><span data-stu-id="a22f5-222">A significant performance improvement when compared with the previous implementation.</span></span>

- <span data-ttu-id="a22f5-223">消除平台依赖项，从而简化部署和维护。</span><span class="sxs-lookup"><span data-stu-id="a22f5-223">Elimination of platform dependencies, which simplifies deployment and servicing.</span></span>

- <span data-ttu-id="a22f5-224">在所有 .NET Core 平台之间保持行为一致。</span><span class="sxs-lookup"><span data-stu-id="a22f5-224">Consistent behavior across all .NET Core platforms.</span></span>

<span data-ttu-id="a22f5-225"><xref:System.Net.Http.SocketsHttpHandler> 是 .NET Core 2.1 中的默认实现。</span><span class="sxs-lookup"><span data-stu-id="a22f5-225"><xref:System.Net.Http.SocketsHttpHandler> is the default implementation in .NET Core 2.1.</span></span> <span data-ttu-id="a22f5-226">但是，你可以通过调用 <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 方法配置应用程序以使用较旧的 <xref:System.Net.Http.HttpClientHandler> 类：</span><span class="sxs-lookup"><span data-stu-id="a22f5-226">However, you can configure your application to use the older <xref:System.Net.Http.HttpClientHandler> class by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method:</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.UseSocketsHttpHandler", false);
```

```vb
AppContext.SetSwitch("System.Net.Http.UseSocketsHttpHandler", False)
```

<span data-ttu-id="a22f5-227">还可以使用环境变量选择退出使用基于 <xref:System.Net.Http.SocketsHttpHandler> 的套接字实现。</span><span class="sxs-lookup"><span data-stu-id="a22f5-227">You can also use an environment variable to opt out of using sockets implementations based on <xref:System.Net.Http.SocketsHttpHandler>.</span></span> <span data-ttu-id="a22f5-228">为此，需要将 `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` 设置为 `false` 或 0。</span><span class="sxs-lookup"><span data-stu-id="a22f5-228">To do this, set the `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` to either `false` or 0.</span></span>

<span data-ttu-id="a22f5-229">在 Windows 上，还可以选择使用 <xref:System.Net.Http.WinHttpHandler?displayProperty=nameWithType>后者依赖于本机实现），或者通过将类实例传递到 <xref:System.Net.Http.HttpClient> 构造函数来使用 <xref:System.Net.Http.SocketsHttpHandler> 类。</span><span class="sxs-lookup"><span data-stu-id="a22f5-229">On Windows, you can also choose to use <xref:System.Net.Http.WinHttpHandler?displayProperty=nameWithType>, which relies on a native implementation, or the <xref:System.Net.Http.SocketsHttpHandler> class by passing an instance of the class to the <xref:System.Net.Http.HttpClient> constructor.</span></span>

<span data-ttu-id="a22f5-230">在 Linux 和 macOS 上，可以在每个进程的基础上仅配置 <xref:System.Net.Http.HttpClient>。</span><span class="sxs-lookup"><span data-stu-id="a22f5-230">On Linux and macOS, you can only configure <xref:System.Net.Http.HttpClient> on a per-process basis.</span></span> <span data-ttu-id="a22f5-231">在 Linux 上，如果想要使用旧的 <xref:System.Net.Http.HttpClient> 实现，则需要部署 [libcurl](https://curl.haxx.se/libcurl/)。</span><span class="sxs-lookup"><span data-stu-id="a22f5-231">On Linux, you need to deploy [libcurl](https://curl.haxx.se/libcurl/) if you want to use the old <xref:System.Net.Http.HttpClient> implementation.</span></span> <span data-ttu-id="a22f5-232">（它随 .NET Core 2.0 一起安装。）</span><span class="sxs-lookup"><span data-stu-id="a22f5-232">(It is installed with .NET Core 2.0.)</span></span>

## <a name="see-also"></a><span data-ttu-id="a22f5-233">请参阅</span><span class="sxs-lookup"><span data-stu-id="a22f5-233">See also</span></span>

[<span data-ttu-id="a22f5-234">.NET Core 的新增功能</span><span class="sxs-lookup"><span data-stu-id="a22f5-234">What's new in .NET Core</span></span>](index.md)  
[<span data-ttu-id="a22f5-235">EF Core 2.1 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="a22f5-235">New features in EF Core 2.1</span></span>](/ef/core/what-is-new/ef-core-2.1)  
[<span data-ttu-id="a22f5-236">ASP.NET Core 2.1 的新增功能</span><span class="sxs-lookup"><span data-stu-id="a22f5-236">What's new in ASP.NET Core 2.1</span></span>](/aspnet/core/aspnetcore-2.1)
