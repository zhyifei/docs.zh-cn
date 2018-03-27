---
title: dotnet new 命令 - .NET Core CLI
description: dotnet new 命令可根据指定模板新建 .NET Core 项目。
author: mairaw
ms.author: mairaw
ms.date: 03/21/2018
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 2cbd42195d0ec713d2ccb4af823075ece950ceff
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="dotnet-new"></a><span data-ttu-id="60bf4-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="60bf4-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="60bf4-104">name</span><span class="sxs-lookup"><span data-stu-id="60bf4-104">Name</span></span>

<span data-ttu-id="60bf4-105">`dotnet new` - 根据指定的模板，创建新的项目、配置文件或解决方案。</span><span class="sxs-lookup"><span data-stu-id="60bf4-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="60bf4-106">摘要</span><span class="sxs-lookup"><span data-stu-id="60bf4-106">Synopsis</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="60bf4-107">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="60bf4-107">.NET Core 2.0</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="60bf4-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="60bf4-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="60bf4-109">描述</span><span class="sxs-lookup"><span data-stu-id="60bf4-109">Description</span></span>

<span data-ttu-id="60bf4-110">`dotnet new` 命令为初始化有效的 .NET Core 项目提供了便捷方法。</span><span class="sxs-lookup"><span data-stu-id="60bf4-110">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="60bf4-111">命令调用[模板引擎](https://github.com/dotnet/templating)，以根据指定的模板和选项在磁盘上创建项目。</span><span class="sxs-lookup"><span data-stu-id="60bf4-111">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="60bf4-112">自变量</span><span class="sxs-lookup"><span data-stu-id="60bf4-112">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="60bf4-113">调用命令时要实例化的模板。</span><span class="sxs-lookup"><span data-stu-id="60bf4-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="60bf4-114">每个模板可能具有可传递的特定选项。</span><span class="sxs-lookup"><span data-stu-id="60bf4-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="60bf4-115">有关详细信息，请参阅[模板选项](#template-options)。</span><span class="sxs-lookup"><span data-stu-id="60bf4-115">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="60bf4-116">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="60bf4-116">.NET Core 2.0</span></span>](#tab/netcore2x)

<span data-ttu-id="60bf4-117">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="60bf4-117">The command contains a default list of templates.</span></span> <span data-ttu-id="60bf4-118">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="60bf4-118">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="60bf4-119">下表列出了与 .NET Core 2.0 SDK 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="60bf4-119">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="60bf4-120">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="60bf4-120">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="60bf4-121">模板描述</span><span class="sxs-lookup"><span data-stu-id="60bf4-121">Template description</span></span>                          | <span data-ttu-id="60bf4-122">模板名称</span><span class="sxs-lookup"><span data-stu-id="60bf4-122">Template name</span></span> | <span data-ttu-id="60bf4-123">语言</span><span class="sxs-lookup"><span data-stu-id="60bf4-123">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="60bf4-124">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="60bf4-124">Console application</span></span>                          | `console`     | <span data-ttu-id="60bf4-125">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="60bf4-125">[C#], F#, VB</span></span>  |
| <span data-ttu-id="60bf4-126">类库</span><span class="sxs-lookup"><span data-stu-id="60bf4-126">Class library</span></span>                                | `classlib`    | <span data-ttu-id="60bf4-127">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="60bf4-127">[C#], F#, VB</span></span>  |
| <span data-ttu-id="60bf4-128">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="60bf4-128">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="60bf4-129">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="60bf4-129">[C#], F#, VB</span></span>  |
| <span data-ttu-id="60bf4-130">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="60bf4-130">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="60bf4-131">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="60bf4-131">[C#], F#, VB</span></span>  |
| <span data-ttu-id="60bf4-132">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="60bf4-132">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="60bf4-133">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="60bf4-133">[C#], F#</span></span>      |
| <span data-ttu-id="60bf4-134">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="60bf4-134">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="60bf4-135">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="60bf4-135">[C#], F#</span></span>      |
| <span data-ttu-id="60bf4-136">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="60bf4-136">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="60bf4-137">[C#]</span><span class="sxs-lookup"><span data-stu-id="60bf4-137">[C#]</span></span>          |
| <span data-ttu-id="60bf4-138">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="60bf4-138">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="60bf4-139">[C#]</span><span class="sxs-lookup"><span data-stu-id="60bf4-139">[C#]</span></span>          |
| <span data-ttu-id="60bf4-140">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="60bf4-140">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="60bf4-141">[C#]</span><span class="sxs-lookup"><span data-stu-id="60bf4-141">[C#]</span></span>          |
| <span data-ttu-id="60bf4-142">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="60bf4-142">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="60bf4-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="60bf4-143">[C#]</span></span>          |
| <span data-ttu-id="60bf4-144">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="60bf4-144">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="60bf4-145">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="60bf4-145">[C#], F#</span></span>      |
| <span data-ttu-id="60bf4-146">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="60bf4-146">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="60bf4-147">Nuget 配置</span><span class="sxs-lookup"><span data-stu-id="60bf4-147">Nuget config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="60bf4-148">Web 配置</span><span class="sxs-lookup"><span data-stu-id="60bf4-148">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="60bf4-149">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="60bf4-149">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="60bf4-150">Razor 页</span><span class="sxs-lookup"><span data-stu-id="60bf4-150">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="60bf4-151">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="60bf4-151">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="60bf4-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="60bf4-152">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="60bf4-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="60bf4-153">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="60bf4-154">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="60bf4-154">The command contains a default list of templates.</span></span> <span data-ttu-id="60bf4-155">使用 `dotnet new -all` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="60bf4-155">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="60bf4-156">下表列出了与 .NET Core 1.x SDK 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="60bf4-156">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="60bf4-157">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="60bf4-157">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="60bf4-158">模板描述</span><span class="sxs-lookup"><span data-stu-id="60bf4-158">Template description</span></span>  | <span data-ttu-id="60bf4-159">模板名称</span><span class="sxs-lookup"><span data-stu-id="60bf4-159">Template name</span></span> | <span data-ttu-id="60bf4-160">语言</span><span class="sxs-lookup"><span data-stu-id="60bf4-160">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="60bf4-161">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="60bf4-161">Console application</span></span>  | `console`     | <span data-ttu-id="60bf4-162">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="60bf4-162">[C#], F#</span></span>  |
| <span data-ttu-id="60bf4-163">类库</span><span class="sxs-lookup"><span data-stu-id="60bf4-163">Class library</span></span>        | `classlib`    | <span data-ttu-id="60bf4-164">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="60bf4-164">[C#], F#</span></span>  |
| <span data-ttu-id="60bf4-165">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="60bf4-165">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="60bf4-166">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="60bf4-166">[C#], F#</span></span>  |
| <span data-ttu-id="60bf4-167">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="60bf4-167">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="60bf4-168">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="60bf4-168">[C#], F#</span></span>  |
| <span data-ttu-id="60bf4-169">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="60bf4-169">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="60bf4-170">[C#]</span><span class="sxs-lookup"><span data-stu-id="60bf4-170">[C#]</span></span>      |
| <span data-ttu-id="60bf4-171">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="60bf4-171">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="60bf4-172">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="60bf4-172">[C#], F#</span></span>  |
| <span data-ttu-id="60bf4-173">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="60bf4-173">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="60bf4-174">[C#]</span><span class="sxs-lookup"><span data-stu-id="60bf4-174">[C#]</span></span>      |
| <span data-ttu-id="60bf4-175">Nuget 配置</span><span class="sxs-lookup"><span data-stu-id="60bf4-175">Nuget config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="60bf4-176">Web 配置</span><span class="sxs-lookup"><span data-stu-id="60bf4-176">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="60bf4-177">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="60bf4-177">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="60bf4-178">选项</span><span class="sxs-lookup"><span data-stu-id="60bf4-178">Options</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="60bf4-179">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="60bf4-179">.NET Core 2.0</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="60bf4-180">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="60bf4-180">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="60bf4-181">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="60bf4-181">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="60bf4-182">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="60bf4-182">Prints out help for the command.</span></span> <span data-ttu-id="60bf4-183">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="60bf4-183">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="60bf4-184">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="60bf4-184">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="60bf4-185">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="60bf4-185">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="60bf4-186">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="60bf4-186">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="60bf4-187">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="60bf4-187">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="60bf4-188">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="60bf4-188">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="60bf4-189">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="60bf4-189">Lists templates containing the specified name.</span></span> <span data-ttu-id="60bf4-190">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="60bf4-190">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="60bf4-191">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="60bf4-191">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="60bf4-192">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="60bf4-192">The language of the template to create.</span></span> <span data-ttu-id="60bf4-193">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="60bf4-193">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="60bf4-194">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="60bf4-194">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="60bf4-195">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="60bf4-195">The name for the created output.</span></span> <span data-ttu-id="60bf4-196">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="60bf4-196">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="60bf4-197">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="60bf4-197">Location to place the generated output.</span></span> <span data-ttu-id="60bf4-198">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="60bf4-198">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="60bf4-199">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="60bf4-199">Filters templates based on available types.</span></span> <span data-ttu-id="60bf4-200">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="60bf4-200">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="60bf4-201">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="60bf4-201">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="60bf4-202">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="60bf4-202">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="60bf4-203">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="60bf4-203">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="60bf4-204">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="60bf4-204">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="60bf4-205">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="60bf4-205">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="60bf4-206">单独在 `dotnet new` 命令的上下文中运行时，显示特定类型的项目的所有模板。</span><span class="sxs-lookup"><span data-stu-id="60bf4-206">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="60bf4-207">在特定模板（如 `dotnet new web -all`）的上下文中运行时，`-all` 解释为一个强制创建标记。</span><span class="sxs-lookup"><span data-stu-id="60bf4-207">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="60bf4-208">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="60bf4-208">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="60bf4-209">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="60bf4-209">Prints out help for the command.</span></span> <span data-ttu-id="60bf4-210">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="60bf4-210">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="60bf4-211">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="60bf4-211">Lists templates containing the specified name.</span></span> <span data-ttu-id="60bf4-212">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="60bf4-212">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="60bf4-213">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="60bf4-213">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="60bf4-214">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="60bf4-214">The language of the template to create.</span></span> <span data-ttu-id="60bf4-215">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="60bf4-215">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="60bf4-216">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="60bf4-216">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="60bf4-217">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="60bf4-217">The name for the created output.</span></span> <span data-ttu-id="60bf4-218">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="60bf4-218">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="60bf4-219">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="60bf4-219">Location to place the generated output.</span></span> <span data-ttu-id="60bf4-220">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="60bf4-220">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="60bf4-221">模板选项</span><span class="sxs-lookup"><span data-stu-id="60bf4-221">Template options</span></span>

<span data-ttu-id="60bf4-222">每个项目模板都可能有附加选项。</span><span class="sxs-lookup"><span data-stu-id="60bf4-222">Each project template may have additional options available.</span></span> <span data-ttu-id="60bf4-223">核心模板有以下附加选项：</span><span class="sxs-lookup"><span data-stu-id="60bf4-223">The core templates have the following additional options:</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="60bf4-224">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="60bf4-224">.NET Core 2.0</span></span>](#tab/netcore2x)

<span data-ttu-id="60bf4-225">**console、angular、react、reactredux**</span><span class="sxs-lookup"><span data-stu-id="60bf4-225">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="60bf4-226">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="60bf4-226">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="60bf4-227">**classlib**</span><span class="sxs-lookup"><span data-stu-id="60bf4-227">**classlib**</span></span>

<span data-ttu-id="60bf4-228">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="60bf4-228">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="60bf4-229">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="60bf4-229">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="60bf4-230">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-230">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="60bf4-231">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="60bf4-231">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="60bf4-232">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="60bf4-232">**mstest, xunit**</span></span>

<span data-ttu-id="60bf4-233">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="60bf4-233">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="60bf4-234">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="60bf4-234">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="60bf4-235">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="60bf4-235">**globaljson**</span></span>

<span data-ttu-id="60bf4-236">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="60bf4-236">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="60bf4-237">**web**</span><span class="sxs-lookup"><span data-stu-id="60bf4-237">**web**</span></span>

<span data-ttu-id="60bf4-238">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="60bf4-238">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="60bf4-239">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="60bf4-239">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="60bf4-240">**webapi**</span><span class="sxs-lookup"><span data-stu-id="60bf4-240">**webapi**</span></span>

<span data-ttu-id="60bf4-241">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="60bf4-241">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="60bf4-242">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="60bf4-242">The possible values are:</span></span>

- <span data-ttu-id="60bf4-243">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="60bf4-243">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="60bf4-244">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="60bf4-244">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="60bf4-245">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="60bf4-245">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="60bf4-246">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="60bf4-246">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="60bf4-247">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="60bf4-247">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="60bf4-248">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="60bf4-248">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="60bf4-249">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-249">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="60bf4-250">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="60bf4-250">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="60bf4-251">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="60bf4-251">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="60bf4-252">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="60bf4-252">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="60bf4-253">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="60bf4-253">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="60bf4-254">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-254">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="60bf4-255">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="60bf4-255">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="60bf4-256">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="60bf4-256">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="60bf4-257">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-257">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="60bf4-258">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="60bf4-258">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="60bf4-259">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="60bf4-259">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="60bf4-260">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-260">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="60bf4-261">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="60bf4-261">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="60bf4-262">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="60bf4-262">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="60bf4-263">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-263">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="60bf4-264">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="60bf4-264">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="60bf4-265">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="60bf4-265">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="60bf4-266">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="60bf4-266">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="60bf4-267">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="60bf4-267">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="60bf4-268">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="60bf4-268">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="60bf4-269">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="60bf4-269">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="60bf4-270">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="60bf4-270">**mvc, razor**</span></span>

<span data-ttu-id="60bf4-271">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="60bf4-271">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="60bf4-272">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="60bf4-272">The possible values are:</span></span>

- <span data-ttu-id="60bf4-273">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="60bf4-273">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="60bf4-274">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="60bf4-274">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="60bf4-275">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="60bf4-275">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="60bf4-276">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="60bf4-276">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="60bf4-277">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="60bf4-277">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="60bf4-278">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="60bf4-278">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="60bf4-279">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="60bf4-279">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="60bf4-280">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="60bf4-280">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="60bf4-281">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-281">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="60bf4-282">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="60bf4-282">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="60bf4-283">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="60bf4-283">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="60bf4-284">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="60bf4-284">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="60bf4-285">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="60bf4-285">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="60bf4-286">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="60bf4-286">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="60bf4-287">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="60bf4-287">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="60bf4-288">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="60bf4-288">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="60bf4-289">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="60bf4-289">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="60bf4-290">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-290">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="60bf4-291">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="60bf4-291">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="60bf4-292">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="60bf4-292">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="60bf4-293">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-293">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="60bf4-294">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="60bf4-294">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="60bf4-295">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="60bf4-295">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="60bf4-296">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-296">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="60bf4-297">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="60bf4-297">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="60bf4-298">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="60bf4-298">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="60bf4-299">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-299">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="60bf4-300">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="60bf4-300">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="60bf4-301">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="60bf4-301">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="60bf4-302">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-302">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="60bf4-303">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="60bf4-303">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="60bf4-304">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="60bf4-304">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="60bf4-305">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="60bf4-305">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="60bf4-306">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="60bf4-306">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="60bf4-307">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="60bf4-307">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="60bf4-308">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="60bf4-308">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="60bf4-309">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="60bf4-309">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="60bf4-310">**page**</span><span class="sxs-lookup"><span data-stu-id="60bf4-310">**page**</span></span>

<span data-ttu-id="60bf4-311">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="60bf4-311">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="60bf4-312">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-312">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="60bf4-313">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="60bf4-313">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="60bf4-314">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="60bf4-314">**viewimports**</span></span>

<span data-ttu-id="60bf4-315">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="60bf4-315">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="60bf4-316">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-316">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="60bf4-317">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="60bf4-317">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="60bf4-318">**console、xunit、mstest、web、webapi**</span><span class="sxs-lookup"><span data-stu-id="60bf4-318">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="60bf4-319">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="60bf4-319">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="60bf4-320">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-320">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="60bf4-321">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-321">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="60bf4-322">**classlib**</span><span class="sxs-lookup"><span data-stu-id="60bf4-322">**classlib**</span></span>

<span data-ttu-id="60bf4-323">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="60bf4-323">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="60bf4-324">值：`netcoreapp1.0`、`netcoreapp1.1` 或 `netstandard1.0` 到 `netstandard1.6`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-324">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="60bf4-325">默认值为 `netstandard1.4`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-325">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="60bf4-326">**mvc**</span><span class="sxs-lookup"><span data-stu-id="60bf4-326">**mvc**</span></span>

<span data-ttu-id="60bf4-327">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="60bf4-327">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="60bf4-328">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-328">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="60bf4-329">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-329">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="60bf4-330">`-au|--auth` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="60bf4-330">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="60bf4-331">值：`None` 或 `Individual`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-331">Values: `None` or `Individual`.</span></span> <span data-ttu-id="60bf4-332">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-332">The default value is `None`.</span></span>

<span data-ttu-id="60bf4-333">`-uld|--use-local-db` - 指定是否使用 LocalDB，而不是 SQLite。</span><span class="sxs-lookup"><span data-stu-id="60bf4-333">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="60bf4-334">值：`true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-334">Values: `true` or `false`.</span></span> <span data-ttu-id="60bf4-335">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="60bf4-335">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="60bf4-336">示例</span><span class="sxs-lookup"><span data-stu-id="60bf4-336">Examples</span></span>

<span data-ttu-id="60bf4-337">在当前目录中创建 F# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="60bf4-337">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="60bf4-338">在指定目录中创建 .NET Standard 类库项目（仅适用于 .NET Core 2.0 SDK 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="60bf4-338">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="60bf4-339">在当前目录中新建定目标到 .NET Core 2.0 且没有设置身份验证的 ASP.NET Core C# MVC 应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="60bf4-339">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="60bf4-340">新建定目标到 .NET Core 2.0 的 xUnit 应用程序：</span><span class="sxs-lookup"><span data-stu-id="60bf4-340">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="60bf4-341">列出适用于 MVC 的所有模板：</span><span class="sxs-lookup"><span data-stu-id="60bf4-341">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="60bf4-342">安装适用于 ASP.NET Core 的单页应用程序模板 2.0 版（命令选项仅可用于 .NET Core SDK 1.1 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="60bf4-342">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

## <a name="see-also"></a><span data-ttu-id="60bf4-343">请参阅</span><span class="sxs-lookup"><span data-stu-id="60bf4-343">See also</span></span>

[<span data-ttu-id="60bf4-344">dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="60bf4-344">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="60bf4-345">创建 dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="60bf4-345">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="60bf4-346">dotnet/dotnet-template-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="60bf4-346">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="60bf4-347">dotnet new 可用模板</span><span class="sxs-lookup"><span data-stu-id="60bf4-347">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
