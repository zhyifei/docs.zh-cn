---
title: ".NET Core 命令行工具体系结构"
description: "了解 .NET Core 工具层及最新版本中的更改。"
keywords: ".NET Core, MSBuild, 体系结构"
author: blackdwarf
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 7fff0f61-ac23-42f0-9661-72a7240a4456
ms.openlocfilehash: ad34faa0c2577bd5e3a0ba339b19a9ad387e015a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="high-level-overview-of-changes-in-the-net-core-tools"></a><span data-ttu-id="a3697-104">.NET Core 工具中变更的高级概述</span><span class="sxs-lookup"><span data-stu-id="a3697-104">High-level overview of changes in the .NET Core tools</span></span>

<span data-ttu-id="a3697-105">此文档介绍了与从 project.json 移动到 MSBuild 和 csproj 项目系统有关的更改，其中包含关于 .NET Core 工具的分层和 CLI 命令的实现的更改的信息。</span><span class="sxs-lookup"><span data-stu-id="a3697-105">This document describes the changes associated with moving from *project.json* to MSBuild and the *csproj* project system with information on the changes to the layering of the .NET Core tooling and the implementation of the CLI commands.</span></span> <span data-ttu-id="a3697-106">这些更改与 2017 年 3 月 7 日 .NET Core SDK 1.0 和 Visual Studio 2017 的发布同时发生（请参阅[通知](https://blogs.msdn.microsoft.com/dotnet/2017/03/07/announcing-net-core-tools-1-0/)），但是最初是在 .NET Core SDK 预览 3 版本中实现的。</span><span class="sxs-lookup"><span data-stu-id="a3697-106">These changes occurred with the release of .NET Core SDK 1.0 and Visual Studio 2017 on March 7, 2017 (see the [announcement](https://blogs.msdn.microsoft.com/dotnet/2017/03/07/announcing-net-core-tools-1-0/)) but were initially implemented with the release of the .NET Core SDK Preview 3.</span></span>

## <a name="moving-away-from-projectjson"></a><span data-ttu-id="a3697-107">弃用 project.json</span><span class="sxs-lookup"><span data-stu-id="a3697-107">Moving away from project.json</span></span>
<span data-ttu-id="a3697-108">.NET Core 工具的最大变更无疑是[弃用 project.json，改用 csproj](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/) 作为项目系统。</span><span class="sxs-lookup"><span data-stu-id="a3697-108">The biggest change in the tooling for .NET Core is certainly the [move away from project.json to csproj](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/) as the project system.</span></span> <span data-ttu-id="a3697-109">最新版本的命令行工具不支持 *project.json* 文件。</span><span class="sxs-lookup"><span data-stu-id="a3697-109">The latest versions of the command-line tools don't support *project.json* files.</span></span> <span data-ttu-id="a3697-110">这意味着它不能用于生成、运行或发布基于 project.json 的应用程序和库。</span><span class="sxs-lookup"><span data-stu-id="a3697-110">That means that it cannot be used to build, run or publish project.json based applications and libraries.</span></span> <span data-ttu-id="a3697-111">若要使用此版本的工具，需要迁移现有项目或启动新的项目。</span><span class="sxs-lookup"><span data-stu-id="a3697-111">In order to use this version of the tools, you will need to migrate your existing projects or start new ones.</span></span> 

<span data-ttu-id="a3697-112">作为此次移动的一部分，开发用于生成 project.json 项目的自定义生成引擎被替换为一个功能完整的成熟生成引擎，即 [MSBuild](https://github.com/Microsoft/msbuild)。</span><span class="sxs-lookup"><span data-stu-id="a3697-112">As part of this move, the custom build engine that was developed to build project.json projects was replaced with a mature and fully capable build engine called [MSBuild](https://github.com/Microsoft/msbuild).</span></span> <span data-ttu-id="a3697-113">MSBuild 是.NET 社区中的知名引擎，因为自该平台首个版本以来，它一直作为一项关键技术。</span><span class="sxs-lookup"><span data-stu-id="a3697-113">MSBuild is a well-known engine in the .NET community, since it has been a key technology since the platform's first release.</span></span> <span data-ttu-id="a3697-114">当然，因为它需要生成 .NET Core 应用程序，所以 MSBuild 已经移植到 .NET Core，并可在 .NET Core 运行的任何平台上使用。</span><span class="sxs-lookup"><span data-stu-id="a3697-114">Of course, because it needs to build .NET Core applications, MSBuild has been ported to .NET Core and can be used on any platform that .NET Core runs on.</span></span> <span data-ttu-id="a3697-115">.NET Core 的一个主要的好处是跨平台开发堆栈，我们已确保本次迁移不会破坏此好处。</span><span class="sxs-lookup"><span data-stu-id="a3697-115">One of the main promises of .NET Core is that of a cross-platform development stack, and we have made sure that this move does not break that promise.</span></span>

> [!NOTE]
> <span data-ttu-id="a3697-116">如果还不熟悉 MSBuild，并且想要了解相关详细信息，可参阅 [MSBuild 概念](/visualstudio/msbuild/msbuild-concepts)一文。</span><span class="sxs-lookup"><span data-stu-id="a3697-116">If you are new to MSBuild and would like to learn more about it, you can start by reading the [MSBuild Concepts](/visualstudio/msbuild/msbuild-concepts) article.</span></span> 

## <a name="the-tooling-layers"></a><span data-ttu-id="a3697-117">工具层</span><span class="sxs-lookup"><span data-stu-id="a3697-117">The tooling layers</span></span>
<span data-ttu-id="a3697-118">随着弃用现有项目系统以及改换生成引擎，自然会出现一个疑问：这些更改会改变整体 .NET Core 工具生态系统的整体“分层”吗？</span><span class="sxs-lookup"><span data-stu-id="a3697-118">With the move away from the existing project system as well as with building engine switches, the question that naturally follows is do any of these changes change the overall "layering" of the whole .NET Core tooling ecosystem?</span></span> <span data-ttu-id="a3697-119">是否有新的位和组件？</span><span class="sxs-lookup"><span data-stu-id="a3697-119">Are there new bits and components?</span></span>

<span data-ttu-id="a3697-120">首先来简要介绍下预览版 2 分层，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="a3697-120">Let's start with a quick refresher on Preview 2 layering as shown in the following picture:</span></span>

![预览版 2 工具高级体系结构](media/cli-msbuild-architecture/p2-arch.png)

<span data-ttu-id="a3697-122">这些工具的分层非常简单。</span><span class="sxs-lookup"><span data-stu-id="a3697-122">The layering of the tools is quite simple.</span></span> <span data-ttu-id="a3697-123">在底部，我们将 .NET Core 命令行工具作为基础。</span><span class="sxs-lookup"><span data-stu-id="a3697-123">At the bottom we have the .NET Core Command Line tools as a foundation.</span></span> <span data-ttu-id="a3697-124">其他所有高级工具（如 Visual Studio 或 Visual Studio Code）依靠 CLI 来生成项目、还原依赖项以及完成其他操作。</span><span class="sxs-lookup"><span data-stu-id="a3697-124">All other, higher-level tools such as Visual Studio or Visual Studio Code, depend and rely on the CLI to build projects, restore dependencies and so on.</span></span> <span data-ttu-id="a3697-125">这意味着，例如，如果 Visual Studio 想要执行还原操作，它会调入`dotnet restore`([请参阅备注](#dotnet-restore-note)) 在 CLI 命令。</span><span class="sxs-lookup"><span data-stu-id="a3697-125">This meant that, for example, if Visual Studio wanted to perform a restore operation, it would call into `dotnet restore` ([see note](#dotnet-restore-note)) command in the CLI.</span></span> 

<span data-ttu-id="a3697-126">随着迁移到新的项目系统，之前的图表会更改：</span><span class="sxs-lookup"><span data-stu-id="a3697-126">With the move to the new project system, the previous diagram changes:</span></span> 

![.NET Core SDK 1.0.0 高级体系结构](media/cli-msbuild-architecture/p3-arch.png)

<span data-ttu-id="a3697-128">主要区别在于 CLI 不再作为基础层；现由“共享 SDK 组件”充当此角色。</span><span class="sxs-lookup"><span data-stu-id="a3697-128">The main difference is that the CLI is not the foundational layer anymore; this role is now filled by the "shared SDK component".</span></span> <span data-ttu-id="a3697-129">共享 SDK 组件是一组负责编译代码、发布代码、打包 NuGet 包等操作的目标和关联任务。SDK 本身是一个开源代码，可在 GitHub 上的 [SDK 存储库](https://github.com/dotnet/sdk)中获得。</span><span class="sxs-lookup"><span data-stu-id="a3697-129">This shared SDK component is a set of targets and associated tasks that are responsible for compiling your code, publishing it, packing NuGet packages etc. The SDK itself is open-source and is available on GitHub on the [SDK repo](https://github.com/dotnet/sdk).</span></span> 

> [!NOTE]
> <span data-ttu-id="a3697-130">“目标”是一个表示 MSBuild 可调用的已命名操作的 MSBuild 术语。</span><span class="sxs-lookup"><span data-stu-id="a3697-130">A "target" is a MSBuild term that indicates a named operation that MSBuild can invoke.</span></span> <span data-ttu-id="a3697-131">其通常伴随着执行此目标应执行的某个逻辑的一个或多个任务。</span><span class="sxs-lookup"><span data-stu-id="a3697-131">It is usually coupled with one or more tasks that execute some logic that the target is supposed to do.</span></span> <span data-ttu-id="a3697-132">MSBuild 支持多个现成的目标，如 `Copy` 或 `Execute`；它还允许用户使用托管代码编写自己的任务，并定义要执行这些任务的目标。</span><span class="sxs-lookup"><span data-stu-id="a3697-132">MSBuild supports many ready-made targets such as `Copy` or `Execute`; it also allows users to write their own tasks using managed code and define targets to execute those tasks.</span></span> <span data-ttu-id="a3697-133">有关详细信息，请参阅 [MSBuild 任务](/visualstudio/msbuild/msbuild-tasks)。</span><span class="sxs-lookup"><span data-stu-id="a3697-133">For more information, see [MSBuild tasks](/visualstudio/msbuild/msbuild-tasks).</span></span> 

<span data-ttu-id="a3697-134">现在所有工具集使用共享 SDK 组件及其目标，包括 CLI。</span><span class="sxs-lookup"><span data-stu-id="a3697-134">All the toolsets now consume the shared SDK component and its targets, CLI included.</span></span> <span data-ttu-id="a3697-135">例如下, 一版本的 Visual Studio 将不得调入`dotnet restore`([请参阅备注](#dotnet-restore-note)) 命令还原.NET 核心项目的依赖关系，则它将直接使用"还原"目标。</span><span class="sxs-lookup"><span data-stu-id="a3697-135">For example, the next version of Visual Studio will not call into `dotnet restore` ([see note](#dotnet-restore-note)) command to restore dependencies for .NET Core projects, it will use the "Restore" target directly.</span></span> <span data-ttu-id="a3697-136">由于这些皆是 MSBuild 目标，因此你也可通过 [dotnet msbuild](dotnet-msbuild.md) 命令使用原始 MSBuild 来执行。</span><span class="sxs-lookup"><span data-stu-id="a3697-136">Since these are MSBuild targets, you can also use raw MSBuild to execute them using the [dotnet msbuild](dotnet-msbuild.md) command.</span></span> 

### <a name="cli-commands"></a><span data-ttu-id="a3697-137">CLI 命令</span><span class="sxs-lookup"><span data-stu-id="a3697-137">CLI commands</span></span>
<span data-ttu-id="a3697-138">共享 SDK 组件意味着大部分现有 CLI 命令已重新实现为 MSBuild 任务和目标。</span><span class="sxs-lookup"><span data-stu-id="a3697-138">The shared SDK component means that the majority of existing CLI commands have been re-implemented as MSBuild tasks and targets.</span></span> <span data-ttu-id="a3697-139">这对 CLI 命令和工具集的使用意味着什么？</span><span class="sxs-lookup"><span data-stu-id="a3697-139">What does this mean for the CLI commands and your usage of the toolset?</span></span> 

<span data-ttu-id="a3697-140">从使用角度而言，它不会更改使用 CLI 的方式。</span><span class="sxs-lookup"><span data-stu-id="a3697-140">From an usage perspective, it doesn't change the way you use the CLI.</span></span> <span data-ttu-id="a3697-141">CLI 仍具有预览 2 版本中存在的核心命令：</span><span class="sxs-lookup"><span data-stu-id="a3697-141">The CLI still has the core commands that exist in Preview 2 release:</span></span>

* `new`
* `restore`
* `run` 
* `build`
* `publish`
* `test`
* `pack` 

<span data-ttu-id="a3697-142">这些命令的作用没有发生改变（仍可新建项目、生成项目、发布项目、打包项目等等）。</span><span class="sxs-lookup"><span data-stu-id="a3697-142">These commands still do what you expect them to do (new up a project, build it, publish it, pack it and so on).</span></span> <span data-ttu-id="a3697-143">大部分选项并未更改，仍和以前一样。可以使用 `dotnet <command> --help` 查看相应命令的帮助屏幕，也可以参阅此网站上的文档来熟悉所有更改。</span><span class="sxs-lookup"><span data-stu-id="a3697-143">Majority of the options are not changed, and are still there, and you can consult either the commands' help screens (using `dotnet <command> --help`) or documentation on this site to get familiar with any changes.</span></span> 

<span data-ttu-id="a3697-144">从执行角度而言，CLI 命令会采用其参数并构造对“原始”MSBuild 的调用，从而设置所需属性和运行所需目标。</span><span class="sxs-lookup"><span data-stu-id="a3697-144">From an execution perspective, the CLI commands will take their parameters and construct a call to "raw" MSBuild that will set the needed properties and run the desired target.</span></span> <span data-ttu-id="a3697-145">为更好的说明这点，请参考下面的命令：</span><span class="sxs-lookup"><span data-stu-id="a3697-145">To better illustrate this, consider the following command:</span></span> 

   `dotnet publish -o pub -c Release`
    
<span data-ttu-id="a3697-146">此命令会使用“发布”配置将应用程序发布到 `pub` 文件夹。</span><span class="sxs-lookup"><span data-stu-id="a3697-146">This command is publishing an application into a `pub` folder using the "Release" configuration.</span></span> <span data-ttu-id="a3697-147">在内部，此命令会转换成下面的 MSBuild 调用：</span><span class="sxs-lookup"><span data-stu-id="a3697-147">Internally, this command gets translated into the following MSBuild invocation:</span></span> 

   `dotnet msbuild /t:Publish /p:OutputPath=pub /p:Configuration=Release`

<span data-ttu-id="a3697-148">此规则值得注意的例外是 `new` 和 `run` 命令，因为它们未实现为 MSBuild 目标。</span><span class="sxs-lookup"><span data-stu-id="a3697-148">The notable exception to this rule are `new` and `run` commands, as they have not been implemented as MSBuild targets.</span></span>

<span data-ttu-id="a3697-149"><a name="dotnet-restore-note"></a> [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]</span><span class="sxs-lookup"><span data-stu-id="a3697-149"><a name="dotnet-restore-note"></a> [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]</span></span>