---
title: .NET Core 迁移到 csproj 格式
description: .NET Core project.json 到 csproj 的迁移
author: blackdwarf
ms.author: mairaw
ms.date: 07/19/2017
ms.openlocfilehash: da1995ed3b77cb802d1f3d04e6d741809de20927
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2018
ms.locfileid: "45597616"
---
# <a name="migrating-net-core-projects-to-the-csproj-format"></a><span data-ttu-id="3ea74-103">将 .NET Core 项目迁移到 .csproj 格式</span><span class="sxs-lookup"><span data-stu-id="3ea74-103">Migrating .NET Core projects to the .csproj format</span></span>

<span data-ttu-id="3ea74-104">本文档介绍 .NET Core 项目的迁移方案，并探讨以下三个迁移方案：</span><span class="sxs-lookup"><span data-stu-id="3ea74-104">This document will cover migration scenarios for .NET Core projects and will go over the following three migration scenarios:</span></span>

1. [<span data-ttu-id="3ea74-105">从 project.json 的一个最新有效架构迁移到 csproj</span><span class="sxs-lookup"><span data-stu-id="3ea74-105">Migration from a valid latest schema of *project.json* to *csproj*</span></span>](#migration-from-projectjson-to-csproj)
2. [<span data-ttu-id="3ea74-106">从 DNX 迁移到 csproj</span><span class="sxs-lookup"><span data-stu-id="3ea74-106">Migration from DNX to csproj</span></span>](#migration-from-dnx-to-csproj)
3. [<span data-ttu-id="3ea74-107">从 RC3 和以前的 .NET Core csproj 项目迁移到最终格式</span><span class="sxs-lookup"><span data-stu-id="3ea74-107">Migration from RC3 and previous .NET Core csproj projects to the final format</span></span>](#migration-from-earlier-net-core-csproj-formats-to-rtm-csproj)

## <a name="migration-from-projectjson-to-csproj"></a><span data-ttu-id="3ea74-108">从 project.json 迁移到 csproj</span><span class="sxs-lookup"><span data-stu-id="3ea74-108">Migration from project.json to csproj</span></span>

<span data-ttu-id="3ea74-109">可使用以下任一方法从 project.json 迁移到 .csproj：</span><span class="sxs-lookup"><span data-stu-id="3ea74-109">Migration from *project.json* to *.csproj* can be done using one of the following methods:</span></span>

- [<span data-ttu-id="3ea74-110">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="3ea74-110">Visual Studio 2017</span></span>](#visual-studio-2017)
- [<span data-ttu-id="3ea74-111">dotnet migrate 命令行工具</span><span class="sxs-lookup"><span data-stu-id="3ea74-111">dotnet migrate command-line tool</span></span>](#dotnet-migrate)

<span data-ttu-id="3ea74-112">这两种方法使用同一个基础引擎来迁移项目，因此，二者结果相同。</span><span class="sxs-lookup"><span data-stu-id="3ea74-112">Both methods use the same underlying engine to migrate the projects, so the results will be the same for both.</span></span> <span data-ttu-id="3ea74-113">在大多数情况下，只需使用这两种方法中的一种将 project.json 迁移到 csproj，而无需进一步对项目文件执行手动编辑。</span><span class="sxs-lookup"><span data-stu-id="3ea74-113">In most cases, using one of these two ways to migrate the *project.json* to *csproj* is the only thing that is needed and no further manual editing of the project file is necessary.</span></span> <span data-ttu-id="3ea74-114">生成的 .csproj 文件的名称与包含目录名称相同。</span><span class="sxs-lookup"><span data-stu-id="3ea74-114">The resulting *.csproj* file will be named the same as the containing directory name.</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="3ea74-115">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="3ea74-115">Visual Studio 2017</span></span>

<span data-ttu-id="3ea74-116">打开 .xproj 文件或打开引用 .xproj 文件的解决方案文件时，将显示“单向升级”对话框。</span><span class="sxs-lookup"><span data-stu-id="3ea74-116">When you open a *.xproj* file or a solution file which references *.xproj* files, the **One-way upgrade** dialog appears.</span></span> <span data-ttu-id="3ea74-117">该对话框将显示要迁移的项目。</span><span class="sxs-lookup"><span data-stu-id="3ea74-117">The dialog displays the projects to be migrated.</span></span>
<span data-ttu-id="3ea74-118">如果打开解决方案文件，则将列出解决方案文件中指定的所有项目。</span><span class="sxs-lookup"><span data-stu-id="3ea74-118">If you open a solution file, all the projects specified in the solution file will be listed.</span></span> <span data-ttu-id="3ea74-119">查看要迁移的项目的列表，然后选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="3ea74-119">Review the list of projects to be migrated and select **OK**.</span></span>

![单向升级对话框，其中显示要迁移的项目的列表](media/one-way-upgrade.jpg)

<span data-ttu-id="3ea74-121">Visual Studio 将迁移自动选择的项目。</span><span class="sxs-lookup"><span data-stu-id="3ea74-121">Visual Studio will migrate the projects chosen automatically.</span></span> <span data-ttu-id="3ea74-122">迁移解决方案时，如果不选择所有项目，会显示相同的对话框，要求升级该解决方案的其余项目。</span><span class="sxs-lookup"><span data-stu-id="3ea74-122">When migrating a solution, if you don't choose all projects, the same dialog will appear asking you to upgrade the remaining projects from that solution.</span></span> <span data-ttu-id="3ea74-123">迁移项目后，可通过在“解决方案资源管理器”窗口中右键单击该项目，并选择“编辑 \<项目名称 > .csproj”来查看和修改其内容。</span><span class="sxs-lookup"><span data-stu-id="3ea74-123">After the project is migrated, you can see and modify its contents by right-clicking the project in the **Solution Explorer** window and selecting **Edit \<project name>.csproj**.</span></span>

<span data-ttu-id="3ea74-124">已迁移的文件（project.json、global.json、.xproj 和解决方案文件）会移动到备份文件夹。</span><span class="sxs-lookup"><span data-stu-id="3ea74-124">Files that were migrated (*project.json*, *global.json*, *.xproj* and solution file) will be moved to a *Backup* folder.</span></span> <span data-ttu-id="3ea74-125">迁移的解决方案文件会升级到 Visual Studio 2017，将无法在先前版本的 Visual Studio 中打开该解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="3ea74-125">The solution file that is migrated will be upgraded to Visual Studio 2017 and you won't be able to open that solution file in previous versions of Visual Studio.</span></span>
<span data-ttu-id="3ea74-126">还会保存并自动打开名为 UpgradeLog.htm 的文件，该文件包含迁移报告。</span><span class="sxs-lookup"><span data-stu-id="3ea74-126">A file named *UpgradeLog.htm* is also saved and automatically opened that contains a migration report.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ea74-127">新工具在 Visual Studio 2015 中不可用，因此无法使用该版本的 Visual Studio 迁移项目。</span><span class="sxs-lookup"><span data-stu-id="3ea74-127">The new tooling is not available in Visual Studio 2015, so you cannot migrate your projects using that version of Visual Studio.</span></span>

### <a name="dotnet-migrate"></a><span data-ttu-id="3ea74-128">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="3ea74-128">dotnet migrate</span></span>

<span data-ttu-id="3ea74-129">在该命令行方案中，可以使用 [`dotnet migrate`](../tools/dotnet-migrate.md) 命令。</span><span class="sxs-lookup"><span data-stu-id="3ea74-129">In the command-line scenario, you can use the [`dotnet migrate`](../tools/dotnet-migrate.md) command.</span></span> <span data-ttu-id="3ea74-130">它会按顺序迁移项目、解决方案或一组文件夹，具体取决于所找到的项。</span><span class="sxs-lookup"><span data-stu-id="3ea74-130">It will migrate a project, a solution or a set of folders in that order, depending on which ones were found.</span></span>
<span data-ttu-id="3ea74-131">迁移项目时，将迁移项目及其所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="3ea74-131">When you migrate a project, the project and all its dependencies are migrated.</span></span>

<span data-ttu-id="3ea74-132">已迁移的文件（project.json、global.json 和 .xproj）会移动到备份文件夹。</span><span class="sxs-lookup"><span data-stu-id="3ea74-132">Files that were migrated (*project.json*, *global.json* and *.xproj*) will be moved to a *backup* folder.</span></span>

> [!NOTE]
> <span data-ttu-id="3ea74-133">如果使用的是 Visual Studio Code，`dotnet migrate` 命令不会修改 `tasks.json` 等 Visual Studio Code 专属文件。</span><span class="sxs-lookup"><span data-stu-id="3ea74-133">If you are using Visual Studio Code, the `dotnet migrate` command will not modify Visual Studio Code-specific files such as `tasks.json`.</span></span> <span data-ttu-id="3ea74-134">需要手动更改这些文件。</span><span class="sxs-lookup"><span data-stu-id="3ea74-134">These files need to be changed manually.</span></span>
> <span data-ttu-id="3ea74-135">如果使用 Project Ryder 或 Visual Studio 以外的任何编辑器或集成开发环境 (IDE)，也是如此。</span><span class="sxs-lookup"><span data-stu-id="3ea74-135">This is also true if you are using Project Ryder or any editor or Integrated Development Environment (IDE) other than Visual Studio.</span></span>

<span data-ttu-id="3ea74-136">请参阅 [project.json 和 csproj 属性之间的映射](../tools/project-json-to-csproj.md)，了解 project.json 和 csproj 格式的比较情况。</span><span class="sxs-lookup"><span data-stu-id="3ea74-136">See [A mapping between project.json and csproj properties](../tools/project-json-to-csproj.md) for a comparison of project.json and csproj formats.</span></span>

### <a name="common-issues"></a><span data-ttu-id="3ea74-137">常见问题</span><span class="sxs-lookup"><span data-stu-id="3ea74-137">Common issues</span></span>

- <span data-ttu-id="3ea74-138">如果收到错误：“未找到任何匹配命令 dotnet-migrate 的可执行文件”：</span><span class="sxs-lookup"><span data-stu-id="3ea74-138">If you get an error: "No executable found matching command dotnet-migrate":</span></span>

<span data-ttu-id="3ea74-139">请运行 `dotnet --version` 查看所使用的版本。</span><span class="sxs-lookup"><span data-stu-id="3ea74-139">Run `dotnet --version` to see which version you are using.</span></span> <span data-ttu-id="3ea74-140">[`dotnet migrate`](../tools/dotnet-migrate.md) 需要 .NET Core CLI RC3 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="3ea74-140">[`dotnet migrate`](../tools/dotnet-migrate.md) requires .NET Core CLI RC3 or higher.</span></span>
<span data-ttu-id="3ea74-141">如果当前目录或父级目录中有 global.json 文件，且 `sdk` 版本设置为较低版本，则会收到此错误。</span><span class="sxs-lookup"><span data-stu-id="3ea74-141">You’ll get this error if you have a *global.json* file in the current or parent directory and the `sdk` version is set to an older version.</span></span>

## <a name="migration-from-dnx-to-csproj"></a><span data-ttu-id="3ea74-142">从 DNX 迁移到 csproj</span><span class="sxs-lookup"><span data-stu-id="3ea74-142">Migration from DNX to csproj</span></span>

<span data-ttu-id="3ea74-143">如果仍在使用 DNX 进行 .NET Core 开发，则应分两个阶段完成迁移过程：</span><span class="sxs-lookup"><span data-stu-id="3ea74-143">If you are still using DNX for .NET Core development, your migration process should be done in two stages:</span></span>

1. <span data-ttu-id="3ea74-144">使用[现有 DNX 迁移指南](from-dnx.md)从 DNX 迁移到启用了 project-json 的 CLI。</span><span class="sxs-lookup"><span data-stu-id="3ea74-144">Use the [existing DNX migration guidance](from-dnx.md) to migrate from DNX to project-json enabled CLI.</span></span>
2. <span data-ttu-id="3ea74-145">请按照上一部分中的步骤，从 project.json 迁移到 .csproj。</span><span class="sxs-lookup"><span data-stu-id="3ea74-145">Follow the steps from the previous section to migrate from *project.json* to *.csproj*.</span></span>  

> [!NOTE]
> <span data-ttu-id="3ea74-146">已于 .NET Core CLI 的预览版 1 发布期间正式弃用 DNX。</span><span class="sxs-lookup"><span data-stu-id="3ea74-146">DNX has become officially deprecated during the Preview 1 release of the .NET Core CLI.</span></span>

## <a name="migration-from-earlier-net-core-csproj-formats-to-rtm-csproj"></a><span data-ttu-id="3ea74-147">从较早的 .NET Core csproj 格式迁移到 RTM csproj</span><span class="sxs-lookup"><span data-stu-id="3ea74-147">Migration from earlier .NET Core csproj formats to RTM csproj</span></span>

<span data-ttu-id="3ea74-148">随着工具的每个新的预发布版本的推出，.NET Core csproj 格式也在不断变化发展。</span><span class="sxs-lookup"><span data-stu-id="3ea74-148">The .NET Core csproj format has been changing and evolving with each new pre-release version of the tooling.</span></span> <span data-ttu-id="3ea74-149">没有工具可以将项目文件从早期版本的 csproj 迁移到最新版本，因此需要手动编辑项目文件。</span><span class="sxs-lookup"><span data-stu-id="3ea74-149">There is no tool that will migrate your project file from earlier versions of csproj to the latest, so you need to manually edit the project file.</span></span> <span data-ttu-id="3ea74-150">实际步骤取决于要迁移的项目文件的版本。</span><span class="sxs-lookup"><span data-stu-id="3ea74-150">The actual steps depend on the version of the project file you are migrating.</span></span> <span data-ttu-id="3ea74-151">根据版本之间的变化，需考虑以下指导信息：</span><span class="sxs-lookup"><span data-stu-id="3ea74-151">The following is some guidance to consider based on the changes that happened between versions:</span></span>

* <span data-ttu-id="3ea74-152">从 `<Project>` 元素中删除工具版本属性（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="3ea74-152">Remove the tools version property from the `<Project>` element, if it exists.</span></span>
* <span data-ttu-id="3ea74-153">从 `<Project>` 元素中删除 XML 命名空间 (`xmlns`)。</span><span class="sxs-lookup"><span data-stu-id="3ea74-153">Remove the XML namespace (`xmlns`) from the `<Project>` element.</span></span>
* <span data-ttu-id="3ea74-154">如果不存在，请将 `Sdk` 属性添加到 `<Project>` 元素，并将其设置为 `Microsoft.NET.Sdk` 或 `Microsoft.NET.Sdk.Web`。</span><span class="sxs-lookup"><span data-stu-id="3ea74-154">If it doesn't exist, add the `Sdk` attribute to the `<Project>` element and set it to `Microsoft.NET.Sdk` or `Microsoft.NET.Sdk.Web`.</span></span> <span data-ttu-id="3ea74-155">此属性指定项目使用要使用的 SDK。</span><span class="sxs-lookup"><span data-stu-id="3ea74-155">This attribute specifies that the project uses the SDK to be used.</span></span> <span data-ttu-id="3ea74-156">`Microsoft.NET.Sdk.Web` 用于 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="3ea74-156">`Microsoft.NET.Sdk.Web` is used for web apps.</span></span>
* <span data-ttu-id="3ea74-157">从项目的顶部和底部删除 `<Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />` 和 `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />` 语句。</span><span class="sxs-lookup"><span data-stu-id="3ea74-157">Remove the `<Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />` and `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />` statements from the top and bottom of the project.</span></span> <span data-ttu-id="3ea74-158">SDK 隐含这些 import 语句，因此项目中不需要这些语句。</span><span class="sxs-lookup"><span data-stu-id="3ea74-158">These import statements are implied by the SDK, so there is no need for them to be in the project.</span></span>
* <span data-ttu-id="3ea74-159">如果项目中含项 `Microsoft.NETCore.App` 或 `NETStandard.Library` `<PackageReference>`，应将其删除。</span><span class="sxs-lookup"><span data-stu-id="3ea74-159">If you have `Microsoft.NETCore.App` or `NETStandard.Library` `<PackageReference>` items in your project, you should remove them.</span></span> <span data-ttu-id="3ea74-160">[SDK 隐含](https://aka.ms/sdkimplicitrefs)这些包引用。</span><span class="sxs-lookup"><span data-stu-id="3ea74-160">These package references are [implied by the SDK](https://aka.ms/sdkimplicitrefs).</span></span>
* <span data-ttu-id="3ea74-161">删除 `Microsoft.NET.Sdk` `<PackageReference>` 元素（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="3ea74-161">Remove the `Microsoft.NET.Sdk` `<PackageReference>` element, if it exists.</span></span> <span data-ttu-id="3ea74-162">SDK 引用来自 `<Project>` 元素上的 `Sdk` 属性。</span><span class="sxs-lookup"><span data-stu-id="3ea74-162">The SDK reference comes through the `Sdk` attribute on the `<Project>` element.</span></span>
* <span data-ttu-id="3ea74-163">删除 [SDK](../tools/csproj.md#default-compilation-includes-in-net-core-projects) 隐含的 [glob](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="3ea74-163">Remove the [globs](https://en.wikipedia.org/wiki/Glob_(programming)) that are [implied by the SDK](../tools/csproj.md#default-compilation-includes-in-net-core-projects).</span></span> <span data-ttu-id="3ea74-164">在项目中留下这些 glob 会引发生成错误，因为编译项会发生重复。</span><span class="sxs-lookup"><span data-stu-id="3ea74-164">Leaving these globs in your project will cause an error on build because compile items will be duplicated.</span></span>

<span data-ttu-id="3ea74-165">完成这些步骤后，项目应与 RTM .NET Core csproj 格式完全兼容。</span><span class="sxs-lookup"><span data-stu-id="3ea74-165">After these steps your project should be fully compatible with the RTM .NET Core csproj format.</span></span>

<span data-ttu-id="3ea74-166">有关从旧的 csproj 格式迁移到新的 csproj 格式之前和之后情况的示例，请参阅 .NET 博客上的 [Updating Visual Studio 2017 RC – .NET Core Tooling improvements](https://blogs.msdn.microsoft.com/dotnet/2016/12/12/updating-visual-studio-2017-rc-net-core-tooling-improvements/)（更新 Visual Studio 2017 RC - .NET Core 工具改进）文章。</span><span class="sxs-lookup"><span data-stu-id="3ea74-166">For examples of before and after the migration from old csproj format to the new one, see the [Updating Visual Studio 2017 RC – .NET Core Tooling improvements](https://blogs.msdn.microsoft.com/dotnet/2016/12/12/updating-visual-studio-2017-rc-net-core-tooling-improvements/) article on the .NET blog.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ea74-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ea74-167">See also</span></span>

- [<span data-ttu-id="3ea74-168">移植、迁移和升级 Visual Studio 项目</span><span class="sxs-lookup"><span data-stu-id="3ea74-168">Port, Migrate, and Upgrade Visual Studio Projects</span></span>](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects)
