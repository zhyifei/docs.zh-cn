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
ms.workload:
- dotnetcore
ms.openlocfilehash: ea94c875ae6fe82d0e5d35ba8ca3fd47971fbbe6
ms.sourcegitcommit: e2bf8e6bc365bd9a0e86fe81eeae7d14f85f48c1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2018
---
# <a name="dotnet-new"></a><span data-ttu-id="d500b-104">dotnet new</span><span class="sxs-lookup"><span data-stu-id="d500b-104">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d500b-105">name</span><span class="sxs-lookup"><span data-stu-id="d500b-105">Name</span></span>

<span data-ttu-id="d500b-106">`dotnet new` - 根据指定的模板，创建新的项目、配置文件或解决方案。</span><span class="sxs-lookup"><span data-stu-id="d500b-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d500b-107">摘要</span><span class="sxs-lookup"><span data-stu-id="d500b-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d500b-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d500b-108">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d500b-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d500b-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="d500b-110">描述</span><span class="sxs-lookup"><span data-stu-id="d500b-110">Description</span></span>

<span data-ttu-id="d500b-111">`dotnet new` 命令为初始化有效的 .NET Core 项目提供了便捷方法。</span><span class="sxs-lookup"><span data-stu-id="d500b-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="d500b-112">命令调用[模板引擎](https://github.com/dotnet/templating)，以根据指定的模板和选项在磁盘上创建项目。</span><span class="sxs-lookup"><span data-stu-id="d500b-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="d500b-113">自变量</span><span class="sxs-lookup"><span data-stu-id="d500b-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="d500b-114">调用命令时要实例化的模板。</span><span class="sxs-lookup"><span data-stu-id="d500b-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="d500b-115">每个模板可能具有可传递的特定选项。</span><span class="sxs-lookup"><span data-stu-id="d500b-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="d500b-116">有关详细信息，请参阅[模板选项](#template-options)。</span><span class="sxs-lookup"><span data-stu-id="d500b-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d500b-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d500b-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="d500b-118">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="d500b-118">The command contains a default list of templates.</span></span> <span data-ttu-id="d500b-119">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="d500b-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="d500b-120">下表列出了与 .NET Core 2.0 SDK 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="d500b-120">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="d500b-121">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="d500b-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="d500b-122">模板描述</span><span class="sxs-lookup"><span data-stu-id="d500b-122">Template description</span></span>                          | <span data-ttu-id="d500b-123">模板名称</span><span class="sxs-lookup"><span data-stu-id="d500b-123">Template name</span></span> | <span data-ttu-id="d500b-124">语言</span><span class="sxs-lookup"><span data-stu-id="d500b-124">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="d500b-125">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="d500b-125">Console application</span></span>                          | `console`     | <span data-ttu-id="d500b-126">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="d500b-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d500b-127">类库</span><span class="sxs-lookup"><span data-stu-id="d500b-127">Class library</span></span>                                | `classlib`    | <span data-ttu-id="d500b-128">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="d500b-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d500b-129">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="d500b-129">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="d500b-130">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="d500b-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d500b-131">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="d500b-131">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="d500b-132">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="d500b-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d500b-133">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="d500b-133">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="d500b-134">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="d500b-134">[C#], F#</span></span>      |
| <span data-ttu-id="d500b-135">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="d500b-135">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="d500b-136">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="d500b-136">[C#], F#</span></span>      |
| <span data-ttu-id="d500b-137">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="d500b-137">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="d500b-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="d500b-138">[C#]</span></span>          |
| <span data-ttu-id="d500b-139">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d500b-139">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="d500b-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="d500b-140">[C#]</span></span>          |
| <span data-ttu-id="d500b-141">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d500b-141">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="d500b-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="d500b-142">[C#]</span></span>          |
| <span data-ttu-id="d500b-143">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d500b-143">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="d500b-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="d500b-144">[C#]</span></span>          |
| <span data-ttu-id="d500b-145">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="d500b-145">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="d500b-146">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="d500b-146">[C#], F#</span></span>      |
| <span data-ttu-id="d500b-147">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="d500b-147">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="d500b-148">Nuget 配置</span><span class="sxs-lookup"><span data-stu-id="d500b-148">Nuget config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="d500b-149">Web 配置</span><span class="sxs-lookup"><span data-stu-id="d500b-149">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="d500b-150">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="d500b-150">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="d500b-151">Razor 页</span><span class="sxs-lookup"><span data-stu-id="d500b-151">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="d500b-152">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="d500b-152">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="d500b-153">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="d500b-153">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d500b-154">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d500b-154">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="d500b-155">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="d500b-155">The command contains a default list of templates.</span></span> <span data-ttu-id="d500b-156">使用 `dotnet new -all` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="d500b-156">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="d500b-157">下表列出了与 .NET Core 1.x SDK 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="d500b-157">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="d500b-158">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="d500b-158">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="d500b-159">模板描述</span><span class="sxs-lookup"><span data-stu-id="d500b-159">Template description</span></span>  | <span data-ttu-id="d500b-160">模板名称</span><span class="sxs-lookup"><span data-stu-id="d500b-160">Template name</span></span> | <span data-ttu-id="d500b-161">语言</span><span class="sxs-lookup"><span data-stu-id="d500b-161">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="d500b-162">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="d500b-162">Console application</span></span>  | `console`     | <span data-ttu-id="d500b-163">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="d500b-163">[C#], F#</span></span>  |
| <span data-ttu-id="d500b-164">类库</span><span class="sxs-lookup"><span data-stu-id="d500b-164">Class library</span></span>        | `classlib`    | <span data-ttu-id="d500b-165">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="d500b-165">[C#], F#</span></span>  |
| <span data-ttu-id="d500b-166">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="d500b-166">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="d500b-167">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="d500b-167">[C#], F#</span></span>  |
| <span data-ttu-id="d500b-168">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="d500b-168">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="d500b-169">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="d500b-169">[C#], F#</span></span>  |
| <span data-ttu-id="d500b-170">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="d500b-170">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="d500b-171">[C#]</span><span class="sxs-lookup"><span data-stu-id="d500b-171">[C#]</span></span>      |
| <span data-ttu-id="d500b-172">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="d500b-172">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="d500b-173">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="d500b-173">[C#], F#</span></span>  |
| <span data-ttu-id="d500b-174">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="d500b-174">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="d500b-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="d500b-175">[C#]</span></span>      |
| <span data-ttu-id="d500b-176">Nuget 配置</span><span class="sxs-lookup"><span data-stu-id="d500b-176">Nuget config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="d500b-177">Web 配置</span><span class="sxs-lookup"><span data-stu-id="d500b-177">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="d500b-178">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="d500b-178">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="d500b-179">选项</span><span class="sxs-lookup"><span data-stu-id="d500b-179">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d500b-180">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d500b-180">.NET Core 2.x</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="d500b-181">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="d500b-181">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="d500b-182">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="d500b-182">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="d500b-183">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="d500b-183">Prints out help for the command.</span></span> <span data-ttu-id="d500b-184">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="d500b-184">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="d500b-185">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="d500b-185">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="d500b-186">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="d500b-186">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="d500b-187">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="d500b-187">Lists templates containing the specified name.</span></span> <span data-ttu-id="d500b-188">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="d500b-188">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="d500b-189">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="d500b-189">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="d500b-190">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="d500b-190">The language of the template to create.</span></span> <span data-ttu-id="d500b-191">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="d500b-191">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="d500b-192">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="d500b-192">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="d500b-193">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="d500b-193">The name for the created output.</span></span> <span data-ttu-id="d500b-194">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="d500b-194">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d500b-195">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="d500b-195">Location to place the generated output.</span></span> <span data-ttu-id="d500b-196">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="d500b-196">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="d500b-197">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="d500b-197">Filters templates based on available types.</span></span> <span data-ttu-id="d500b-198">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="d500b-198">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="d500b-199">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="d500b-199">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="d500b-200">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="d500b-200">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="d500b-201">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="d500b-201">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="d500b-202">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="d500b-202">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d500b-203">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d500b-203">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="d500b-204">单独在 `dotnet new` 命令的上下文中运行时，显示特定类型的项目的所有模板。</span><span class="sxs-lookup"><span data-stu-id="d500b-204">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="d500b-205">在特定模板（如 `dotnet new web -all`）的上下文中运行时，`-all` 解释为一个强制创建标记。</span><span class="sxs-lookup"><span data-stu-id="d500b-205">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="d500b-206">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="d500b-206">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="d500b-207">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="d500b-207">Prints out help for the command.</span></span> <span data-ttu-id="d500b-208">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="d500b-208">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="d500b-209">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="d500b-209">Lists templates containing the specified name.</span></span> <span data-ttu-id="d500b-210">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="d500b-210">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="d500b-211">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="d500b-211">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="d500b-212">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="d500b-212">The language of the template to create.</span></span> <span data-ttu-id="d500b-213">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="d500b-213">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="d500b-214">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="d500b-214">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="d500b-215">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="d500b-215">The name for the created output.</span></span> <span data-ttu-id="d500b-216">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="d500b-216">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d500b-217">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="d500b-217">Location to place the generated output.</span></span> <span data-ttu-id="d500b-218">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="d500b-218">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="d500b-219">模板选项</span><span class="sxs-lookup"><span data-stu-id="d500b-219">Template options</span></span>

<span data-ttu-id="d500b-220">每个项目模板都可能有附加选项。</span><span class="sxs-lookup"><span data-stu-id="d500b-220">Each project template may have additional options available.</span></span> <span data-ttu-id="d500b-221">核心模板有以下附加选项：</span><span class="sxs-lookup"><span data-stu-id="d500b-221">The core templates have the following additional options:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d500b-222">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d500b-222">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="d500b-223">**console、angular、react、reactredux**</span><span class="sxs-lookup"><span data-stu-id="d500b-223">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="d500b-224">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="d500b-224">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d500b-225">**classlib**</span><span class="sxs-lookup"><span data-stu-id="d500b-225">**classlib**</span></span>

<span data-ttu-id="d500b-226">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="d500b-226">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d500b-227">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="d500b-227">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="d500b-228">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="d500b-228">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="d500b-229">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="d500b-229">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d500b-230">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="d500b-230">**mstest, xunit**</span></span>

<span data-ttu-id="d500b-231">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="d500b-231">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="d500b-232">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="d500b-232">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d500b-233">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="d500b-233">**globaljson**</span></span>

<span data-ttu-id="d500b-234">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="d500b-234">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="d500b-235">**web**</span><span class="sxs-lookup"><span data-stu-id="d500b-235">**web**</span></span>

<span data-ttu-id="d500b-236">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="d500b-236">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d500b-237">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="d500b-237">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d500b-238">**webapi**</span><span class="sxs-lookup"><span data-stu-id="d500b-238">**webapi**</span></span>

<span data-ttu-id="d500b-239">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="d500b-239">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="d500b-240">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="d500b-240">The possible values are:</span></span>

- <span data-ttu-id="d500b-241">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="d500b-241">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="d500b-242">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="d500b-242">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="d500b-243">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="d500b-243">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="d500b-244">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="d500b-244">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="d500b-245">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="d500b-245">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d500b-246">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d500b-246">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d500b-247">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="d500b-247">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="d500b-248">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="d500b-248">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d500b-249">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d500b-249">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d500b-250">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="d500b-250">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d500b-251">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d500b-251">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d500b-252">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="d500b-252">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="d500b-253">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="d500b-253">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="d500b-254">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d500b-254">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="d500b-255">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="d500b-255">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="d500b-256">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="d500b-256">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="d500b-257">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d500b-257">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d500b-258">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="d500b-258">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="d500b-259">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="d500b-259">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d500b-260">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d500b-260">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d500b-261">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="d500b-261">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="d500b-262">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="d500b-262">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="d500b-263">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="d500b-263">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="d500b-264">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="d500b-264">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d500b-265">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="d500b-265">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d500b-266">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="d500b-266">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d500b-267">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="d500b-267">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d500b-268">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="d500b-268">**mvc, razor**</span></span>

<span data-ttu-id="d500b-269">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="d500b-269">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="d500b-270">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="d500b-270">The possible values are:</span></span>

- <span data-ttu-id="d500b-271">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="d500b-271">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="d500b-272">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="d500b-272">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="d500b-273">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="d500b-273">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="d500b-274">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="d500b-274">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="d500b-275">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="d500b-275">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="d500b-276">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="d500b-276">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="d500b-277">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="d500b-277">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d500b-278">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d500b-278">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d500b-279">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="d500b-279">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="d500b-280">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="d500b-280">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d500b-281">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d500b-281">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d500b-282">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="d500b-282">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="d500b-283">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d500b-283">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d500b-284">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="d500b-284">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="d500b-285">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d500b-285">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d500b-286">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="d500b-286">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d500b-287">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d500b-287">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="d500b-288">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="d500b-288">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="d500b-289">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="d500b-289">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="d500b-290">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d500b-290">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="d500b-291">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="d500b-291">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="d500b-292">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="d500b-292">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="d500b-293">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d500b-293">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="d500b-294">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="d500b-294">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="d500b-295">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="d500b-295">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d500b-296">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d500b-296">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="d500b-297">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="d500b-297">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="d500b-298">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="d500b-298">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="d500b-299">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="d500b-299">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="d500b-300">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="d500b-300">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="d500b-301">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="d500b-301">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="d500b-302">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="d500b-302">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="d500b-303">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="d500b-303">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d500b-304">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="d500b-304">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="d500b-305">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="d500b-305">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d500b-306">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="d500b-306">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d500b-307">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="d500b-307">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d500b-308">**page**</span><span class="sxs-lookup"><span data-stu-id="d500b-308">**page**</span></span>

<span data-ttu-id="d500b-309">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d500b-309">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="d500b-310">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="d500b-310">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="d500b-311">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="d500b-311">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="d500b-312">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="d500b-312">**viewimports**</span></span>

<span data-ttu-id="d500b-313">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d500b-313">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="d500b-314">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="d500b-314">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d500b-315">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d500b-315">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="d500b-316">**console、xunit、mstest、web、webapi**</span><span class="sxs-lookup"><span data-stu-id="d500b-316">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="d500b-317">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="d500b-317">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d500b-318">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="d500b-318">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="d500b-319">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="d500b-319">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="d500b-320">**classlib**</span><span class="sxs-lookup"><span data-stu-id="d500b-320">**classlib**</span></span>

<span data-ttu-id="d500b-321">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="d500b-321">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d500b-322">值：`netcoreapp1.0`、`netcoreapp1.1` 或 `netstandard1.0` 到 `netstandard1.6`。</span><span class="sxs-lookup"><span data-stu-id="d500b-322">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="d500b-323">默认值为 `netstandard1.4`。</span><span class="sxs-lookup"><span data-stu-id="d500b-323">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="d500b-324">**mvc**</span><span class="sxs-lookup"><span data-stu-id="d500b-324">**mvc**</span></span>

<span data-ttu-id="d500b-325">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="d500b-325">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d500b-326">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="d500b-326">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="d500b-327">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="d500b-327">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="d500b-328">`-au|--auth` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="d500b-328">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="d500b-329">值：`None` 或 `Individual`。</span><span class="sxs-lookup"><span data-stu-id="d500b-329">Values: `None` or `Individual`.</span></span> <span data-ttu-id="d500b-330">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="d500b-330">The default value is `None`.</span></span>

<span data-ttu-id="d500b-331">`-uld|--use-local-db` - 指定是否使用 LocalDB，而不是 SQLite。</span><span class="sxs-lookup"><span data-stu-id="d500b-331">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="d500b-332">值：`true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="d500b-332">Values: `true` or `false`.</span></span> <span data-ttu-id="d500b-333">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="d500b-333">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="d500b-334">示例</span><span class="sxs-lookup"><span data-stu-id="d500b-334">Examples</span></span>

<span data-ttu-id="d500b-335">在当前目录中创建 F# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="d500b-335">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="d500b-336">在指定目录中创建 .NET Standard 类库项目（仅适用于 .NET Core 2.0 SDK 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="d500b-336">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="d500b-337">在当前目录中新建定目标到 .NET Core 2.0 且没有设置身份验证的 ASP.NET Core C# MVC 应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="d500b-337">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="d500b-338">新建定目标到 .NET Core 2.0 的 xUnit 应用程序：</span><span class="sxs-lookup"><span data-stu-id="d500b-338">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="d500b-339">列出适用于 MVC 的所有模板：</span><span class="sxs-lookup"><span data-stu-id="d500b-339">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

## <a name="see-also"></a><span data-ttu-id="d500b-340">请参阅</span><span class="sxs-lookup"><span data-stu-id="d500b-340">See also</span></span>

[<span data-ttu-id="d500b-341">dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="d500b-341">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="d500b-342">创建 dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="d500b-342">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="d500b-343">dotnet/dotnet-template-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="d500b-343">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="d500b-344">dotnet new 可用模板</span><span class="sxs-lookup"><span data-stu-id="d500b-344">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
