---
title: "dotnet new 命令 - .NET Core CLI"
description: "dotnet new 命令可根据指定模板新建 .NET Core 项目。"
keywords: "dotnet-new, CLI, CLI 命令, .NET Core"
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
ms.workload: dotnetcore
ms.openlocfilehash: cf65dc80f135badcb1580726a12a9ae9d94ae3d7
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2018
---
# <a name="dotnet-new"></a><span data-ttu-id="d4303-104">dotnet new</span><span class="sxs-lookup"><span data-stu-id="d4303-104">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d4303-105">name</span><span class="sxs-lookup"><span data-stu-id="d4303-105">Name</span></span>

<span data-ttu-id="d4303-106">`dotnet new` - 根据指定的模板，创建新的项目、配置文件或解决方案。</span><span class="sxs-lookup"><span data-stu-id="d4303-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d4303-107">摘要</span><span class="sxs-lookup"><span data-stu-id="d4303-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d4303-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d4303-108">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d4303-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d4303-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="d4303-110">描述</span><span class="sxs-lookup"><span data-stu-id="d4303-110">Description</span></span>

<span data-ttu-id="d4303-111">`dotnet new` 命令为初始化有效的 .NET Core 项目提供了便捷方法。</span><span class="sxs-lookup"><span data-stu-id="d4303-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="d4303-112">命令调用[模板引擎](https://github.com/dotnet/templating)，以根据指定的模板和选项在磁盘上创建项目。</span><span class="sxs-lookup"><span data-stu-id="d4303-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="d4303-113">自变量</span><span class="sxs-lookup"><span data-stu-id="d4303-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="d4303-114">调用命令时要实例化的模板。</span><span class="sxs-lookup"><span data-stu-id="d4303-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="d4303-115">每个模板可能具有可传递的特定选项。</span><span class="sxs-lookup"><span data-stu-id="d4303-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="d4303-116">有关详细信息，请参阅[模板选项](#template-options)。</span><span class="sxs-lookup"><span data-stu-id="d4303-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d4303-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d4303-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="d4303-118">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="d4303-118">The command contains a default list of templates.</span></span> <span data-ttu-id="d4303-119">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="d4303-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="d4303-120">下表列出了与 .NET Core 2.0 SDK 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="d4303-120">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="d4303-121">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="d4303-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="d4303-122">模板描述</span><span class="sxs-lookup"><span data-stu-id="d4303-122">Template description</span></span>                          | <span data-ttu-id="d4303-123">模板名称</span><span class="sxs-lookup"><span data-stu-id="d4303-123">Template name</span></span> | <span data-ttu-id="d4303-124">语言</span><span class="sxs-lookup"><span data-stu-id="d4303-124">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="d4303-125">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="d4303-125">Console application</span></span>                          | `console`     | <span data-ttu-id="d4303-126">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="d4303-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d4303-127">类库</span><span class="sxs-lookup"><span data-stu-id="d4303-127">Class library</span></span>                                | `classlib`    | <span data-ttu-id="d4303-128">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="d4303-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d4303-129">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="d4303-129">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="d4303-130">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="d4303-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d4303-131">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="d4303-131">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="d4303-132">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="d4303-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d4303-133">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="d4303-133">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="d4303-134">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="d4303-134">[C#], F#</span></span>      |
| <span data-ttu-id="d4303-135">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="d4303-135">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="d4303-136">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="d4303-136">[C#], F#</span></span>      |
| <span data-ttu-id="d4303-137">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="d4303-137">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="d4303-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="d4303-138">[C#]</span></span>          |
| <span data-ttu-id="d4303-139">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d4303-139">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="d4303-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="d4303-140">[C#]</span></span>          |
| <span data-ttu-id="d4303-141">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d4303-141">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="d4303-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="d4303-142">[C#]</span></span>          |
| <span data-ttu-id="d4303-143">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d4303-143">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="d4303-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="d4303-144">[C#]</span></span>          |
| <span data-ttu-id="d4303-145">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="d4303-145">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="d4303-146">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="d4303-146">[C#], F#</span></span>      |
| <span data-ttu-id="d4303-147">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="d4303-147">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="d4303-148">Nuget 配置</span><span class="sxs-lookup"><span data-stu-id="d4303-148">Nuget config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="d4303-149">Web 配置</span><span class="sxs-lookup"><span data-stu-id="d4303-149">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="d4303-150">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="d4303-150">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="d4303-151">Razor 页</span><span class="sxs-lookup"><span data-stu-id="d4303-151">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="d4303-152">MVC/ViewImports</span><span class="sxs-lookup"><span data-stu-id="d4303-152">MVC/ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="d4303-153">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="d4303-153">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d4303-154">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d4303-154">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="d4303-155">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="d4303-155">The command contains a default list of templates.</span></span> <span data-ttu-id="d4303-156">使用 `dotnet new -all` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="d4303-156">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="d4303-157">下表列出了与 .NET Core 1.x SDK 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="d4303-157">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="d4303-158">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="d4303-158">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="d4303-159">模板描述</span><span class="sxs-lookup"><span data-stu-id="d4303-159">Template description</span></span>  | <span data-ttu-id="d4303-160">模板名称</span><span class="sxs-lookup"><span data-stu-id="d4303-160">Template name</span></span> | <span data-ttu-id="d4303-161">语言</span><span class="sxs-lookup"><span data-stu-id="d4303-161">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="d4303-162">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="d4303-162">Console application</span></span>  | `console`     | <span data-ttu-id="d4303-163">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="d4303-163">[C#], F#</span></span>  |
| <span data-ttu-id="d4303-164">类库</span><span class="sxs-lookup"><span data-stu-id="d4303-164">Class library</span></span>        | `classlib`    | <span data-ttu-id="d4303-165">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="d4303-165">[C#], F#</span></span>  |
| <span data-ttu-id="d4303-166">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="d4303-166">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="d4303-167">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="d4303-167">[C#], F#</span></span>  |
| <span data-ttu-id="d4303-168">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="d4303-168">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="d4303-169">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="d4303-169">[C#], F#</span></span>  |
| <span data-ttu-id="d4303-170">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="d4303-170">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="d4303-171">[C#]</span><span class="sxs-lookup"><span data-stu-id="d4303-171">[C#]</span></span>      |
| <span data-ttu-id="d4303-172">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="d4303-172">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="d4303-173">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="d4303-173">[C#], F#</span></span>  |
| <span data-ttu-id="d4303-174">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="d4303-174">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="d4303-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="d4303-175">[C#]</span></span>      |
| <span data-ttu-id="d4303-176">Nuget 配置</span><span class="sxs-lookup"><span data-stu-id="d4303-176">Nuget config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="d4303-177">Web 配置</span><span class="sxs-lookup"><span data-stu-id="d4303-177">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="d4303-178">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="d4303-178">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="d4303-179">选项</span><span class="sxs-lookup"><span data-stu-id="d4303-179">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d4303-180">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d4303-180">.NET Core 2.x</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="d4303-181">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="d4303-181">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="d4303-182">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="d4303-182">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="d4303-183">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="d4303-183">Prints out help for the command.</span></span> <span data-ttu-id="d4303-184">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="d4303-184">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="d4303-185">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="d4303-185">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="d4303-186">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="d4303-186">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="d4303-187">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="d4303-187">Lists templates containing the specified name.</span></span> <span data-ttu-id="d4303-188">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="d4303-188">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="d4303-189">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="d4303-189">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="d4303-190">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="d4303-190">The language of the template to create.</span></span> <span data-ttu-id="d4303-191">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="d4303-191">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="d4303-192">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="d4303-192">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="d4303-193">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="d4303-193">The name for the created output.</span></span> <span data-ttu-id="d4303-194">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="d4303-194">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d4303-195">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="d4303-195">Location to place the generated output.</span></span> <span data-ttu-id="d4303-196">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="d4303-196">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="d4303-197">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="d4303-197">Filters templates based on available types.</span></span> <span data-ttu-id="d4303-198">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="d4303-198">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="d4303-199">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="d4303-199">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="d4303-200">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="d4303-200">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="d4303-201">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="d4303-201">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="d4303-202">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="d4303-202">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d4303-203">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d4303-203">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="d4303-204">单独在 `dotnet new` 命令的上下文中运行时，显示特定类型的项目的所有模板。</span><span class="sxs-lookup"><span data-stu-id="d4303-204">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="d4303-205">在特定模板（如 `dotnet new web -all`）的上下文中运行时，`-all` 解释为一个强制创建标记。</span><span class="sxs-lookup"><span data-stu-id="d4303-205">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="d4303-206">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="d4303-206">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="d4303-207">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="d4303-207">Prints out help for the command.</span></span> <span data-ttu-id="d4303-208">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="d4303-208">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="d4303-209">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="d4303-209">Lists templates containing the specified name.</span></span> <span data-ttu-id="d4303-210">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="d4303-210">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="d4303-211">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="d4303-211">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="d4303-212">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="d4303-212">The language of the template to create.</span></span> <span data-ttu-id="d4303-213">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="d4303-213">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="d4303-214">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="d4303-214">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="d4303-215">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="d4303-215">The name for the created output.</span></span> <span data-ttu-id="d4303-216">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="d4303-216">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d4303-217">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="d4303-217">Location to place the generated output.</span></span> <span data-ttu-id="d4303-218">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="d4303-218">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="d4303-219">模板选项</span><span class="sxs-lookup"><span data-stu-id="d4303-219">Template options</span></span>

<span data-ttu-id="d4303-220">每个项目模板都可能有附加选项。</span><span class="sxs-lookup"><span data-stu-id="d4303-220">Each project template may have additional options available.</span></span> <span data-ttu-id="d4303-221">核心模板有以下附加选项：</span><span class="sxs-lookup"><span data-stu-id="d4303-221">The core templates have the following additional options:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d4303-222">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d4303-222">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="d4303-223">**console、angular、react、reactredux**</span><span class="sxs-lookup"><span data-stu-id="d4303-223">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="d4303-224">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="d4303-224">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d4303-225">**classlib**</span><span class="sxs-lookup"><span data-stu-id="d4303-225">**classlib**</span></span>

<span data-ttu-id="d4303-226">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="d4303-226">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d4303-227">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="d4303-227">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="d4303-228">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="d4303-228">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="d4303-229">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="d4303-229">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d4303-230">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="d4303-230">**mstest, xunit**</span></span>

<span data-ttu-id="d4303-231">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="d4303-231">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="d4303-232">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="d4303-232">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d4303-233">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="d4303-233">**globaljson**</span></span>

<span data-ttu-id="d4303-234">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="d4303-234">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="d4303-235">**web**</span><span class="sxs-lookup"><span data-stu-id="d4303-235">**web**</span></span>

<span data-ttu-id="d4303-236">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="d4303-236">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d4303-237">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="d4303-237">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d4303-238">**webapi**</span><span class="sxs-lookup"><span data-stu-id="d4303-238">**webapi**</span></span>

<span data-ttu-id="d4303-239">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="d4303-239">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="d4303-240">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="d4303-240">The possible values are:</span></span>

- <span data-ttu-id="d4303-241">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="d4303-241">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="d4303-242">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="d4303-242">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="d4303-243">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="d4303-243">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="d4303-244">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="d4303-244">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="d4303-245">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="d4303-245">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d4303-246">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d4303-246">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d4303-247">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="d4303-247">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="d4303-248">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="d4303-248">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d4303-249">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d4303-249">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d4303-250">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="d4303-250">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d4303-251">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d4303-251">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d4303-252">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="d4303-252">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="d4303-253">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="d4303-253">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="d4303-254">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d4303-254">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="d4303-255">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="d4303-255">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="d4303-256">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="d4303-256">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="d4303-257">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d4303-257">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d4303-258">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="d4303-258">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="d4303-259">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="d4303-259">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d4303-260">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d4303-260">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d4303-261">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="d4303-261">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="d4303-262">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="d4303-262">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="d4303-263">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="d4303-263">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="d4303-264">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="d4303-264">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d4303-265">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="d4303-265">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d4303-266">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="d4303-266">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d4303-267">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="d4303-267">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d4303-268">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="d4303-268">**mvc, razor**</span></span>

<span data-ttu-id="d4303-269">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="d4303-269">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="d4303-270">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="d4303-270">The possible values are:</span></span>

- <span data-ttu-id="d4303-271">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="d4303-271">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="d4303-272">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="d4303-272">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="d4303-273">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="d4303-273">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="d4303-274">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="d4303-274">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="d4303-275">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="d4303-275">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="d4303-276">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="d4303-276">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="d4303-277">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="d4303-277">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d4303-278">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d4303-278">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d4303-279">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="d4303-279">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="d4303-280">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="d4303-280">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d4303-281">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d4303-281">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d4303-282">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="d4303-282">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="d4303-283">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d4303-283">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d4303-284">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="d4303-284">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="d4303-285">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d4303-285">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d4303-286">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="d4303-286">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d4303-287">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d4303-287">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="d4303-288">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="d4303-288">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="d4303-289">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="d4303-289">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="d4303-290">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d4303-290">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="d4303-291">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="d4303-291">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="d4303-292">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="d4303-292">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="d4303-293">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d4303-293">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="d4303-294">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="d4303-294">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="d4303-295">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="d4303-295">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d4303-296">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d4303-296">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="d4303-297">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="d4303-297">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="d4303-298">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="d4303-298">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="d4303-299">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d4303-299">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="d4303-300">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="d4303-300">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="d4303-301">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="d4303-301">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="d4303-302">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="d4303-302">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="d4303-303">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="d4303-303">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d4303-304">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="d4303-304">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="d4303-305">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="d4303-305">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d4303-306">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="d4303-306">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d4303-307">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="d4303-307">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d4303-308">**page**</span><span class="sxs-lookup"><span data-stu-id="d4303-308">**page**</span></span>

<span data-ttu-id="d4303-309">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d4303-309">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="d4303-310">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="d4303-310">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="d4303-311">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="d4303-311">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="d4303-312">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="d4303-312">**viewimports**</span></span>

<span data-ttu-id="d4303-313">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d4303-313">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="d4303-314">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="d4303-314">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d4303-315">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d4303-315">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="d4303-316">**console、xunit、mstest、web、webapi**</span><span class="sxs-lookup"><span data-stu-id="d4303-316">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="d4303-317">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="d4303-317">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d4303-318">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="d4303-318">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="d4303-319">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="d4303-319">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="d4303-320">**classlib**</span><span class="sxs-lookup"><span data-stu-id="d4303-320">**classlib**</span></span>

<span data-ttu-id="d4303-321">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="d4303-321">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d4303-322">值：`netcoreapp1.0`、`netcoreapp1.1` 或 `netstandard1.0` 到 `netstandard1.6`。</span><span class="sxs-lookup"><span data-stu-id="d4303-322">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="d4303-323">默认值为 `netstandard1.4`。</span><span class="sxs-lookup"><span data-stu-id="d4303-323">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="d4303-324">**mvc**</span><span class="sxs-lookup"><span data-stu-id="d4303-324">**mvc**</span></span>

<span data-ttu-id="d4303-325">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="d4303-325">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d4303-326">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="d4303-326">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="d4303-327">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="d4303-327">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="d4303-328">`-au|--auth` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="d4303-328">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="d4303-329">值：`None` 或 `Individual`。</span><span class="sxs-lookup"><span data-stu-id="d4303-329">Values: `None` or `Individual`.</span></span> <span data-ttu-id="d4303-330">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="d4303-330">The default value is `None`.</span></span>

<span data-ttu-id="d4303-331">`-uld|--use-local-db` - 指定是否使用 LocalDB，而不是 SQLite。</span><span class="sxs-lookup"><span data-stu-id="d4303-331">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="d4303-332">值：`true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="d4303-332">Values: `true` or `false`.</span></span> <span data-ttu-id="d4303-333">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="d4303-333">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="d4303-334">示例</span><span class="sxs-lookup"><span data-stu-id="d4303-334">Examples</span></span>

<span data-ttu-id="d4303-335">在当前目录中创建 F# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="d4303-335">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="d4303-336">在指定目录中创建 .NET Standard 类库项目（仅适用于 .NET Core 2.0 SDK 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="d4303-336">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="d4303-337">在当前目录中新建定目标到 .NET Core 2.0 且没有设置身份验证的 ASP.NET Core C# MVC 应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="d4303-337">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="d4303-338">新建定目标到 .NET Core 2.0 的 xUnit 应用程序：</span><span class="sxs-lookup"><span data-stu-id="d4303-338">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="d4303-339">列出适用于 MVC 的所有模板：</span><span class="sxs-lookup"><span data-stu-id="d4303-339">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

## <a name="see-also"></a><span data-ttu-id="d4303-340">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4303-340">See also</span></span>

[<span data-ttu-id="d4303-341">dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="d4303-341">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="d4303-342">创建 dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="d4303-342">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="d4303-343">dotnet/dotnet-template-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="d4303-343">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="d4303-344">dotnet new 可用模板</span><span class="sxs-lookup"><span data-stu-id="d4303-344">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
