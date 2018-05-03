---
title: .NET Core 命令行工具体系结构
description: 了解 .NET Core 工具层及最新版本中的更改。
author: blackdwarf
ms.date: 03/06/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 909e3ba088a3eabededf008fa07a51ac7d677fa2
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="high-level-overview-of-changes-in-the-net-core-tools"></a><span data-ttu-id="e2287-103">.NET Core 工具中变更的高级概述</span><span class="sxs-lookup"><span data-stu-id="e2287-103">High-level overview of changes in the .NET Core tools</span></span>

<span data-ttu-id="e2287-104">此文档介绍了与从 project.json 移动到 MSBuild 和 csproj 项目系统有关的更改，其中包含关于 .NET Core 工具的分层和 CLI 命令的实现的更改的信息。</span><span class="sxs-lookup"><span data-stu-id="e2287-104">This document describes the changes associated with moving from *project.json* to MSBuild and the *csproj* project system with information on the changes to the layering of the .NET Core tooling and the implementation of the CLI commands.</span></span> <span data-ttu-id="e2287-105">这些更改与 2017 年 3 月 7 日 .NET Core SDK 1.0 和 Visual Studio 2017 的发布同时发生（请参阅[通知](https://blogs.msdn.microsoft.com/dotnet/2017/03/07/announcing-net-core-tools-1-0/)），但是最初是在 .NET Core SDK 预览 3 版本中实现的。</span><span class="sxs-lookup"><span data-stu-id="e2287-105">These changes occurred with the release of .NET Core SDK 1.0 and Visual Studio 2017 on March 7, 2017 (see the [announcement](https://blogs.msdn.microsoft.com/dotnet/2017/03/07/announcing-net-core-tools-1-0/)) but were initially implemented with the release of the .NET Core SDK Preview 3.</span></span>

## <a name="moving-away-from-projectjson"></a><span data-ttu-id="e2287-106">弃用 project.json</span><span class="sxs-lookup"><span data-stu-id="e2287-106">Moving away from project.json</span></span>
<span data-ttu-id="e2287-107">.NET Core 工具的最大变更无疑是[弃用 project.json，改用 csproj](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/) 作为项目系统。</span><span class="sxs-lookup"><span data-stu-id="e2287-107">The biggest change in the tooling for .NET Core is certainly the [move away from project.json to csproj](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/) as the project system.</span></span> <span data-ttu-id="e2287-108">最新版本的命令行工具不支持 *project.json* 文件。</span><span class="sxs-lookup"><span data-stu-id="e2287-108">The latest versions of the command-line tools don't support *project.json* files.</span></span> <span data-ttu-id="e2287-109">这意味着它不能用于生成、运行或发布基于 project.json 的应用程序和库。</span><span class="sxs-lookup"><span data-stu-id="e2287-109">That means that it cannot be used to build, run or publish project.json based applications and libraries.</span></span> <span data-ttu-id="e2287-110">若要使用此版本的工具，需要迁移现有项目或启动新的项目。</span><span class="sxs-lookup"><span data-stu-id="e2287-110">In order to use this version of the tools, you will need to migrate your existing projects or start new ones.</span></span> 

<span data-ttu-id="e2287-111">作为此次移动的一部分，开发用于生成 project.json 项目的自定义生成引擎被替换为一个功能完整的成熟生成引擎，即 [MSBuild](https://github.com/Microsoft/msbuild)。</span><span class="sxs-lookup"><span data-stu-id="e2287-111">As part of this move, the custom build engine that was developed to build project.json projects was replaced with a mature and fully capable build engine called [MSBuild](https://github.com/Microsoft/msbuild).</span></span> <span data-ttu-id="e2287-112">MSBuild 是.NET 社区中的知名引擎，因为自该平台首个版本以来，它一直作为一项关键技术。</span><span class="sxs-lookup"><span data-stu-id="e2287-112">MSBuild is a well-known engine in the .NET community, since it has been a key technology since the platform's first release.</span></span> <span data-ttu-id="e2287-113">当然，因为它需要生成 .NET Core 应用程序，所以 MSBuild 已经移植到 .NET Core，并可在 .NET Core 运行的任何平台上使用。</span><span class="sxs-lookup"><span data-stu-id="e2287-113">Of course, because it needs to build .NET Core applications, MSBuild has been ported to .NET Core and can be used on any platform that .NET Core runs on.</span></span> <span data-ttu-id="e2287-114">.NET Core 的一个主要的好处是跨平台开发堆栈，我们已确保本次迁移不会破坏此好处。</span><span class="sxs-lookup"><span data-stu-id="e2287-114">One of the main promises of .NET Core is that of a cross-platform development stack, and we have made sure that this move does not break that promise.</span></span>

> [!NOTE]
> <span data-ttu-id="e2287-115">如果还不熟悉 MSBuild，并且想要了解相关详细信息，可参阅 [MSBuild 概念](/visualstudio/msbuild/msbuild-concepts)一文。</span><span class="sxs-lookup"><span data-stu-id="e2287-115">If you are new to MSBuild and would like to learn more about it, you can start by reading the [MSBuild Concepts](/visualstudio/msbuild/msbuild-concepts) article.</span></span> 

## <a name="the-tooling-layers"></a><span data-ttu-id="e2287-116">工具层</span><span class="sxs-lookup"><span data-stu-id="e2287-116">The tooling layers</span></span>
<span data-ttu-id="e2287-117">随着弃用现有项目系统以及改换生成引擎，自然会出现一个疑问：这些更改会改变整体 .NET Core 工具生态系统的整体“分层”吗？</span><span class="sxs-lookup"><span data-stu-id="e2287-117">With the move away from the existing project system as well as with building engine switches, the question that naturally follows is do any of these changes change the overall "layering" of the whole .NET Core tooling ecosystem?</span></span> <span data-ttu-id="e2287-118">是否有新的位和组件？</span><span class="sxs-lookup"><span data-stu-id="e2287-118">Are there new bits and components?</span></span>

<span data-ttu-id="e2287-119">首先来简要介绍下预览版 2 分层，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="e2287-119">Let's start with a quick refresher on Preview 2 layering as shown in the following picture:</span></span>

![预览版 2 工具高级体系结构](media/cli-msbuild-architecture/p2-arch.png)

<span data-ttu-id="e2287-121">这些工具的分层非常简单。</span><span class="sxs-lookup"><span data-stu-id="e2287-121">The layering of the tools is quite simple.</span></span> <span data-ttu-id="e2287-122">在底部，我们将 .NET Core 命令行工具作为基础。</span><span class="sxs-lookup"><span data-stu-id="e2287-122">At the bottom we have the .NET Core Command Line tools as a foundation.</span></span> <span data-ttu-id="e2287-123">其他所有高级工具（如 Visual Studio 或 Visual Studio Code）依靠 CLI 来生成项目、还原依赖项以及完成其他操作。</span><span class="sxs-lookup"><span data-stu-id="e2287-123">All other, higher-level tools such as Visual Studio or Visual Studio Code, depend and rely on the CLI to build projects, restore dependencies and so on.</span></span> <span data-ttu-id="e2287-124">也就是说，例如，如果 Visual Studio 要执行还原操作，它会在 CLI 中调用 `dotnet restore`（[见备注](#dotnet-restore-note)）命令。</span><span class="sxs-lookup"><span data-stu-id="e2287-124">This meant that, for example, if Visual Studio wanted to perform a restore operation, it would call into `dotnet restore` ([see note](#dotnet-restore-note)) command in the CLI.</span></span> 

<span data-ttu-id="e2287-125">随着迁移到新的项目系统，之前的图表会更改：</span><span class="sxs-lookup"><span data-stu-id="e2287-125">With the move to the new project system, the previous diagram changes:</span></span> 

![.NET Core SDK 1.0.0 高级体系结构](media/cli-msbuild-architecture/p3-arch.png)

<span data-ttu-id="e2287-127">主要区别在于 CLI 不再作为基础层；现由“共享 SDK 组件”充当此角色。</span><span class="sxs-lookup"><span data-stu-id="e2287-127">The main difference is that the CLI is not the foundational layer anymore; this role is now filled by the "shared SDK component".</span></span> <span data-ttu-id="e2287-128">共享 SDK 组件是一组负责编译代码、发布代码、打包 NuGet 包等操作的目标和关联任务。SDK 本身是一个开源代码，可在 GitHub 上的 [SDK 存储库](https://github.com/dotnet/sdk)中获得。</span><span class="sxs-lookup"><span data-stu-id="e2287-128">This shared SDK component is a set of targets and associated tasks that are responsible for compiling your code, publishing it, packing NuGet packages etc. The SDK itself is open-source and is available on GitHub on the [SDK repo](https://github.com/dotnet/sdk).</span></span> 

> [!NOTE]
> <span data-ttu-id="e2287-129">“目标”是一个表示 MSBuild 可调用的已命名操作的 MSBuild 术语。</span><span class="sxs-lookup"><span data-stu-id="e2287-129">A "target" is a MSBuild term that indicates a named operation that MSBuild can invoke.</span></span> <span data-ttu-id="e2287-130">其通常伴随着执行此目标应执行的某个逻辑的一个或多个任务。</span><span class="sxs-lookup"><span data-stu-id="e2287-130">It is usually coupled with one or more tasks that execute some logic that the target is supposed to do.</span></span> <span data-ttu-id="e2287-131">MSBuild 支持多个现成的目标，如 `Copy` 或 `Execute`；它还允许用户使用托管代码编写自己的任务，并定义要执行这些任务的目标。</span><span class="sxs-lookup"><span data-stu-id="e2287-131">MSBuild supports many ready-made targets such as `Copy` or `Execute`; it also allows users to write their own tasks using managed code and define targets to execute those tasks.</span></span> <span data-ttu-id="e2287-132">有关详细信息，请参阅 [MSBuild 任务](/visualstudio/msbuild/msbuild-tasks)。</span><span class="sxs-lookup"><span data-stu-id="e2287-132">For more information, see [MSBuild tasks](/visualstudio/msbuild/msbuild-tasks).</span></span> 

<span data-ttu-id="e2287-133">现在所有工具集使用共享 SDK 组件及其目标，包括 CLI。</span><span class="sxs-lookup"><span data-stu-id="e2287-133">All the toolsets now consume the shared SDK component and its targets, CLI included.</span></span> <span data-ttu-id="e2287-134">例如，下一版 Visual Studio 不会调用 `dotnet restore`（[见备注](#dotnet-restore-note)）命令来还原 .NET Core 项目的依赖关系，而是直接使用“还原”目标。</span><span class="sxs-lookup"><span data-stu-id="e2287-134">For example, the next version of Visual Studio will not call into `dotnet restore` ([see note](#dotnet-restore-note)) command to restore dependencies for .NET Core projects, it will use the "Restore" target directly.</span></span> <span data-ttu-id="e2287-135">由于这些皆是 MSBuild 目标，因此你也可通过 [dotnet msbuild](dotnet-msbuild.md) 命令使用原始 MSBuild 来执行。</span><span class="sxs-lookup"><span data-stu-id="e2287-135">Since these are MSBuild targets, you can also use raw MSBuild to execute them using the [dotnet msbuild](dotnet-msbuild.md) command.</span></span> 

### <a name="cli-commands"></a><span data-ttu-id="e2287-136">CLI 命令</span><span class="sxs-lookup"><span data-stu-id="e2287-136">CLI commands</span></span>
<span data-ttu-id="e2287-137">共享 SDK 组件意味着大部分现有 CLI 命令已重新实现为 MSBuild 任务和目标。</span><span class="sxs-lookup"><span data-stu-id="e2287-137">The shared SDK component means that the majority of existing CLI commands have been re-implemented as MSBuild tasks and targets.</span></span> <span data-ttu-id="e2287-138">这对 CLI 命令和工具集的使用意味着什么？</span><span class="sxs-lookup"><span data-stu-id="e2287-138">What does this mean for the CLI commands and your usage of the toolset?</span></span> 

<span data-ttu-id="e2287-139">从使用角度而言，它不会更改使用 CLI 的方式。</span><span class="sxs-lookup"><span data-stu-id="e2287-139">From an usage perspective, it doesn't change the way you use the CLI.</span></span> <span data-ttu-id="e2287-140">CLI 仍具有预览 2 版本中存在的核心命令：</span><span class="sxs-lookup"><span data-stu-id="e2287-140">The CLI still has the core commands that exist in Preview 2 release:</span></span>

* `new`
* `restore`
* `run` 
* `build`
* `publish`
* `test`
* `pack` 

<span data-ttu-id="e2287-141">这些命令的作用没有发生改变（仍可新建项目、生成项目、发布项目、打包项目等等）。</span><span class="sxs-lookup"><span data-stu-id="e2287-141">These commands still do what you expect them to do (new up a project, build it, publish it, pack it and so on).</span></span> <span data-ttu-id="e2287-142">大部分选项并未更改，仍和以前一样。可以使用 `dotnet <command> --help` 查看相应命令的帮助屏幕，也可以参阅此网站上的文档来熟悉所有更改。</span><span class="sxs-lookup"><span data-stu-id="e2287-142">Majority of the options are not changed, and are still there, and you can consult either the commands' help screens (using `dotnet <command> --help`) or documentation on this site to get familiar with any changes.</span></span> 

<span data-ttu-id="e2287-143">从执行角度而言，CLI 命令会采用其参数并构造对“原始”MSBuild 的调用，从而设置所需属性和运行所需目标。</span><span class="sxs-lookup"><span data-stu-id="e2287-143">From an execution perspective, the CLI commands will take their parameters and construct a call to "raw" MSBuild that will set the needed properties and run the desired target.</span></span> <span data-ttu-id="e2287-144">为更好的说明这点，请参考下面的命令：</span><span class="sxs-lookup"><span data-stu-id="e2287-144">To better illustrate this, consider the following command:</span></span> 

   `dotnet publish -o pub -c Release`
    
<span data-ttu-id="e2287-145">此命令会使用“发布”配置将应用程序发布到 `pub` 文件夹。</span><span class="sxs-lookup"><span data-stu-id="e2287-145">This command is publishing an application into a `pub` folder using the "Release" configuration.</span></span> <span data-ttu-id="e2287-146">在内部，此命令会转换成下面的 MSBuild 调用：</span><span class="sxs-lookup"><span data-stu-id="e2287-146">Internally, this command gets translated into the following MSBuild invocation:</span></span> 

   `dotnet msbuild /t:Publish /p:OutputPath=pub /p:Configuration=Release`

<span data-ttu-id="e2287-147">此规则值得注意的例外是 `new` 和 `run` 命令，因为它们未实现为 MSBuild 目标。</span><span class="sxs-lookup"><span data-stu-id="e2287-147">The notable exception to this rule are `new` and `run` commands, as they have not been implemented as MSBuild targets.</span></span>

<a name="dotnet-restore-note"></a> <span data-ttu-id="e2287-148">[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]</span><span class="sxs-lookup"><span data-stu-id="e2287-148">[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]</span></span>