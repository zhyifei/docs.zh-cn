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
ms.openlocfilehash: f5815e1ad2a36a8ef3279f6ff83465dba9ec5d50
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-new"></a><span data-ttu-id="39cb2-104">dotnet new</span><span class="sxs-lookup"><span data-stu-id="39cb2-104">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="39cb2-105">name</span><span class="sxs-lookup"><span data-stu-id="39cb2-105">Name</span></span>

<span data-ttu-id="39cb2-106">`dotnet new` - 根据指定的模板，创建新的项目、配置文件或解决方案。</span><span class="sxs-lookup"><span data-stu-id="39cb2-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="39cb2-107">摘要</span><span class="sxs-lookup"><span data-stu-id="39cb2-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="39cb2-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="39cb2-108">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="39cb2-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="39cb2-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="39cb2-110">描述</span><span class="sxs-lookup"><span data-stu-id="39cb2-110">Description</span></span>

<span data-ttu-id="39cb2-111">`dotnet new` 命令为初始化有效的 .NET Core 项目提供了便捷方法。</span><span class="sxs-lookup"><span data-stu-id="39cb2-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="39cb2-112">命令调用[模板引擎](https://github.com/dotnet/templating)，以根据指定的模板和选项在磁盘上创建项目。</span><span class="sxs-lookup"><span data-stu-id="39cb2-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="39cb2-113">自变量</span><span class="sxs-lookup"><span data-stu-id="39cb2-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="39cb2-114">调用命令时要实例化的模板。</span><span class="sxs-lookup"><span data-stu-id="39cb2-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="39cb2-115">每个模板可能具有可传递的特定选项。</span><span class="sxs-lookup"><span data-stu-id="39cb2-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="39cb2-116">有关详细信息，请参阅[模板选项](#template-options)。</span><span class="sxs-lookup"><span data-stu-id="39cb2-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="39cb2-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="39cb2-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="39cb2-118">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="39cb2-118">The command contains a default list of templates.</span></span> <span data-ttu-id="39cb2-119">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="39cb2-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="39cb2-120">下表列出了与 .NET Core 2.0 SDK 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="39cb2-120">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="39cb2-121">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="39cb2-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="39cb2-122">模板描述</span><span class="sxs-lookup"><span data-stu-id="39cb2-122">Template description</span></span>                          | <span data-ttu-id="39cb2-123">模板名称</span><span class="sxs-lookup"><span data-stu-id="39cb2-123">Template name</span></span>  | <span data-ttu-id="39cb2-124">语言</span><span class="sxs-lookup"><span data-stu-id="39cb2-124">Languages</span></span>     |
|----------------------------------------------|----------------|---------------|
| <span data-ttu-id="39cb2-125">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="39cb2-125">Console application</span></span>                          | <span data-ttu-id="39cb2-126">控制台</span><span class="sxs-lookup"><span data-stu-id="39cb2-126">console</span></span>        | <span data-ttu-id="39cb2-127">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="39cb2-127">[C#], F#, VB</span></span>  |
| <span data-ttu-id="39cb2-128">类库</span><span class="sxs-lookup"><span data-stu-id="39cb2-128">Class library</span></span>                                | <span data-ttu-id="39cb2-129">classlib</span><span class="sxs-lookup"><span data-stu-id="39cb2-129">classlib</span></span>       | <span data-ttu-id="39cb2-130">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="39cb2-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="39cb2-131">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="39cb2-131">Unit test project</span></span>                            | <span data-ttu-id="39cb2-132">mstest</span><span class="sxs-lookup"><span data-stu-id="39cb2-132">mstest</span></span>         | <span data-ttu-id="39cb2-133">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="39cb2-133">[C#], F#, VB</span></span>  |
| <span data-ttu-id="39cb2-134">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="39cb2-134">xUnit test project</span></span>                           | <span data-ttu-id="39cb2-135">xunit</span><span class="sxs-lookup"><span data-stu-id="39cb2-135">xunit</span></span>          | <span data-ttu-id="39cb2-136">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="39cb2-136">[C#], F#, VB</span></span>  |
| <span data-ttu-id="39cb2-137">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="39cb2-137">ASP.NET Core empty</span></span>                           | <span data-ttu-id="39cb2-138">Web</span><span class="sxs-lookup"><span data-stu-id="39cb2-138">web</span></span>            | <span data-ttu-id="39cb2-139">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="39cb2-139">[C#], F#</span></span>      |
| <span data-ttu-id="39cb2-140">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="39cb2-140">ASP.NET Core Web App (Model-View-Controller)</span></span> | <span data-ttu-id="39cb2-141">mvc</span><span class="sxs-lookup"><span data-stu-id="39cb2-141">mvc</span></span>            | <span data-ttu-id="39cb2-142">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="39cb2-142">[C#], F#</span></span>      |
| <span data-ttu-id="39cb2-143">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="39cb2-143">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="39cb2-144">razor</span><span class="sxs-lookup"><span data-stu-id="39cb2-144">razor</span></span>          | <span data-ttu-id="39cb2-145">[C#]</span><span class="sxs-lookup"><span data-stu-id="39cb2-145">[C#]</span></span>          |
| <span data-ttu-id="39cb2-146">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="39cb2-146">ASP.NET Core with Angular</span></span>                    | <span data-ttu-id="39cb2-147">angular</span><span class="sxs-lookup"><span data-stu-id="39cb2-147">angular</span></span>        | <span data-ttu-id="39cb2-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="39cb2-148">[C#]</span></span>          |
| <span data-ttu-id="39cb2-149">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="39cb2-149">ASP.NET Core with React.js</span></span>                   | <span data-ttu-id="39cb2-150">react</span><span class="sxs-lookup"><span data-stu-id="39cb2-150">react</span></span>          | <span data-ttu-id="39cb2-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="39cb2-151">[C#]</span></span>          |
| <span data-ttu-id="39cb2-152">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="39cb2-152">ASP.NET Core with React.js and Redux</span></span>         | <span data-ttu-id="39cb2-153">reactredux</span><span class="sxs-lookup"><span data-stu-id="39cb2-153">reactredux</span></span>     | <span data-ttu-id="39cb2-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="39cb2-154">[C#]</span></span>          |
| <span data-ttu-id="39cb2-155">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="39cb2-155">ASP.NET Core Web API</span></span>                         | <span data-ttu-id="39cb2-156">webapi</span><span class="sxs-lookup"><span data-stu-id="39cb2-156">webapi</span></span>         | <span data-ttu-id="39cb2-157">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="39cb2-157">[C#], F#</span></span>      |
| <span data-ttu-id="39cb2-158">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="39cb2-158">global.json file</span></span>                             | <span data-ttu-id="39cb2-159">globaljson</span><span class="sxs-lookup"><span data-stu-id="39cb2-159">globaljson</span></span>     |               |
| <span data-ttu-id="39cb2-160">Nuget 配置</span><span class="sxs-lookup"><span data-stu-id="39cb2-160">Nuget config</span></span>                                 | <span data-ttu-id="39cb2-161">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="39cb2-161">nugetconfig</span></span>    |               |
| <span data-ttu-id="39cb2-162">Web 配置</span><span class="sxs-lookup"><span data-stu-id="39cb2-162">Web config</span></span>                                   | <span data-ttu-id="39cb2-163">webconfig</span><span class="sxs-lookup"><span data-stu-id="39cb2-163">webconfig</span></span>      |               |
| <span data-ttu-id="39cb2-164">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="39cb2-164">Solution file</span></span>                                | <span data-ttu-id="39cb2-165">sln</span><span class="sxs-lookup"><span data-stu-id="39cb2-165">sln</span></span>            |               |
| <span data-ttu-id="39cb2-166">Razor 页</span><span class="sxs-lookup"><span data-stu-id="39cb2-166">Razor page</span></span>                                   | <span data-ttu-id="39cb2-167">页</span><span class="sxs-lookup"><span data-stu-id="39cb2-167">page</span></span>           |               |
| <span data-ttu-id="39cb2-168">MVC/ViewImports</span><span class="sxs-lookup"><span data-stu-id="39cb2-168">MVC/ViewImports</span></span>                              | <span data-ttu-id="39cb2-169">viewimports</span><span class="sxs-lookup"><span data-stu-id="39cb2-169">viewimports</span></span>    |               |
| <span data-ttu-id="39cb2-170">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="39cb2-170">MVC ViewStart</span></span>                                | <span data-ttu-id="39cb2-171">viewstart</span><span class="sxs-lookup"><span data-stu-id="39cb2-171">viewstart</span></span>      |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="39cb2-172">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="39cb2-172">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="39cb2-173">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="39cb2-173">The command contains a default list of templates.</span></span> <span data-ttu-id="39cb2-174">使用 `dotnet new -all` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="39cb2-174">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="39cb2-175">下表列出了与 .NET Core 1.x SDK 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="39cb2-175">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="39cb2-176">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="39cb2-176">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="39cb2-177">模板描述</span><span class="sxs-lookup"><span data-stu-id="39cb2-177">Template description</span></span>  | <span data-ttu-id="39cb2-178">模板名称</span><span class="sxs-lookup"><span data-stu-id="39cb2-178">Template name</span></span>  | <span data-ttu-id="39cb2-179">语言</span><span class="sxs-lookup"><span data-stu-id="39cb2-179">Languages</span></span> |
|----------------------|----------------|-----------|
| <span data-ttu-id="39cb2-180">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="39cb2-180">Console application</span></span>  | <span data-ttu-id="39cb2-181">控制台</span><span class="sxs-lookup"><span data-stu-id="39cb2-181">console</span></span>        | <span data-ttu-id="39cb2-182">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="39cb2-182">[C#], F#</span></span>  |
| <span data-ttu-id="39cb2-183">类库</span><span class="sxs-lookup"><span data-stu-id="39cb2-183">Class library</span></span>        | <span data-ttu-id="39cb2-184">classlib</span><span class="sxs-lookup"><span data-stu-id="39cb2-184">classlib</span></span>       | <span data-ttu-id="39cb2-185">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="39cb2-185">[C#], F#</span></span>  |
| <span data-ttu-id="39cb2-186">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="39cb2-186">Unit test project</span></span>    | <span data-ttu-id="39cb2-187">mstest</span><span class="sxs-lookup"><span data-stu-id="39cb2-187">mstest</span></span>         | <span data-ttu-id="39cb2-188">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="39cb2-188">[C#], F#</span></span>  |
| <span data-ttu-id="39cb2-189">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="39cb2-189">xUnit test project</span></span>   | <span data-ttu-id="39cb2-190">xunit</span><span class="sxs-lookup"><span data-stu-id="39cb2-190">xunit</span></span>          | <span data-ttu-id="39cb2-191">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="39cb2-191">[C#], F#</span></span>  |
| <span data-ttu-id="39cb2-192">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="39cb2-192">ASP.NET Core empty</span></span>   | <span data-ttu-id="39cb2-193">Web</span><span class="sxs-lookup"><span data-stu-id="39cb2-193">web</span></span>            | <span data-ttu-id="39cb2-194">[C#]</span><span class="sxs-lookup"><span data-stu-id="39cb2-194">[C#]</span></span>      |
| <span data-ttu-id="39cb2-195">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="39cb2-195">ASP.NET Core Web App</span></span> | <span data-ttu-id="39cb2-196">mvc</span><span class="sxs-lookup"><span data-stu-id="39cb2-196">mvc</span></span>            | <span data-ttu-id="39cb2-197">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="39cb2-197">[C#], F#</span></span>  |
| <span data-ttu-id="39cb2-198">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="39cb2-198">ASP.NET Core Web API</span></span> | <span data-ttu-id="39cb2-199">webapi</span><span class="sxs-lookup"><span data-stu-id="39cb2-199">webapi</span></span>         | <span data-ttu-id="39cb2-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="39cb2-200">[C#]</span></span>      |
| <span data-ttu-id="39cb2-201">Nuget 配置</span><span class="sxs-lookup"><span data-stu-id="39cb2-201">Nuget config</span></span>         | <span data-ttu-id="39cb2-202">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="39cb2-202">nugetconfig</span></span>    |           |
| <span data-ttu-id="39cb2-203">Web 配置</span><span class="sxs-lookup"><span data-stu-id="39cb2-203">Web config</span></span>           | <span data-ttu-id="39cb2-204">webconfig</span><span class="sxs-lookup"><span data-stu-id="39cb2-204">webconfig</span></span>      |           |
| <span data-ttu-id="39cb2-205">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="39cb2-205">Solution file</span></span>        | <span data-ttu-id="39cb2-206">sln</span><span class="sxs-lookup"><span data-stu-id="39cb2-206">sln</span></span>            |           |

---

## <a name="options"></a><span data-ttu-id="39cb2-207">选项</span><span class="sxs-lookup"><span data-stu-id="39cb2-207">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="39cb2-208">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="39cb2-208">.NET Core 2.x</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="39cb2-209">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="39cb2-209">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="39cb2-210">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="39cb2-210">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="39cb2-211">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="39cb2-211">Prints out help for the command.</span></span> <span data-ttu-id="39cb2-212">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="39cb2-212">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="39cb2-213">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="39cb2-213">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="39cb2-214">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="39cb2-214">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="39cb2-215">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="39cb2-215">Lists templates containing the specified name.</span></span> <span data-ttu-id="39cb2-216">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="39cb2-216">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="39cb2-217">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="39cb2-217">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="39cb2-218">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="39cb2-218">The language of the template to create.</span></span> <span data-ttu-id="39cb2-219">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="39cb2-219">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="39cb2-220">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="39cb2-220">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="39cb2-221">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="39cb2-221">The name for the created output.</span></span> <span data-ttu-id="39cb2-222">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="39cb2-222">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="39cb2-223">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="39cb2-223">Location to place the generated output.</span></span> <span data-ttu-id="39cb2-224">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="39cb2-224">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="39cb2-225">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="39cb2-225">Filters templates based on available types.</span></span> <span data-ttu-id="39cb2-226">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="39cb2-226">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="39cb2-227">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="39cb2-227">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="39cb2-228">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="39cb2-228">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="39cb2-229">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="39cb2-229">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="39cb2-230">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="39cb2-230">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="39cb2-231">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="39cb2-231">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="39cb2-232">单独在 `dotnet new` 命令的上下文中运行时，显示特定类型的项目的所有模板。</span><span class="sxs-lookup"><span data-stu-id="39cb2-232">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="39cb2-233">在特定模板（如 `dotnet new web -all`）的上下文中运行时，`-all` 解释为一个强制创建标记。</span><span class="sxs-lookup"><span data-stu-id="39cb2-233">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="39cb2-234">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="39cb2-234">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="39cb2-235">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="39cb2-235">Prints out help for the command.</span></span> <span data-ttu-id="39cb2-236">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="39cb2-236">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="39cb2-237">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="39cb2-237">Lists templates containing the specified name.</span></span> <span data-ttu-id="39cb2-238">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="39cb2-238">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="39cb2-239">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="39cb2-239">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="39cb2-240">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="39cb2-240">The language of the template to create.</span></span> <span data-ttu-id="39cb2-241">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="39cb2-241">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="39cb2-242">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="39cb2-242">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="39cb2-243">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="39cb2-243">The name for the created output.</span></span> <span data-ttu-id="39cb2-244">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="39cb2-244">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="39cb2-245">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="39cb2-245">Location to place the generated output.</span></span> <span data-ttu-id="39cb2-246">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="39cb2-246">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="39cb2-247">模板选项</span><span class="sxs-lookup"><span data-stu-id="39cb2-247">Template options</span></span>

<span data-ttu-id="39cb2-248">每个项目模板都可能有附加选项。</span><span class="sxs-lookup"><span data-stu-id="39cb2-248">Each project template may have additional options available.</span></span> <span data-ttu-id="39cb2-249">核心模板有以下附加选项：</span><span class="sxs-lookup"><span data-stu-id="39cb2-249">The core templates have the following additional options:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="39cb2-250">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="39cb2-250">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="39cb2-251">**console、angular、react、reactredux**</span><span class="sxs-lookup"><span data-stu-id="39cb2-251">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="39cb2-252">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="39cb2-252">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="39cb2-253">**classlib**</span><span class="sxs-lookup"><span data-stu-id="39cb2-253">**classlib**</span></span>

<span data-ttu-id="39cb2-254">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="39cb2-254">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="39cb2-255">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="39cb2-255">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="39cb2-256">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-256">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="39cb2-257">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="39cb2-257">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="39cb2-258">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="39cb2-258">**mstest, xunit**</span></span>

<span data-ttu-id="39cb2-259">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="39cb2-259">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="39cb2-260">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="39cb2-260">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="39cb2-261">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="39cb2-261">**globaljson**</span></span>

<span data-ttu-id="39cb2-262">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="39cb2-262">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="39cb2-263">**web**</span><span class="sxs-lookup"><span data-stu-id="39cb2-263">**web**</span></span>

<span data-ttu-id="39cb2-264">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="39cb2-264">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="39cb2-265">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="39cb2-265">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="39cb2-266">**webapi**</span><span class="sxs-lookup"><span data-stu-id="39cb2-266">**webapi**</span></span>

<span data-ttu-id="39cb2-267">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="39cb2-267">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="39cb2-268">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="39cb2-268">The possible values are:</span></span>

- <span data-ttu-id="39cb2-269">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="39cb2-269">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="39cb2-270">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="39cb2-270">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="39cb2-271">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="39cb2-271">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="39cb2-272">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="39cb2-272">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="39cb2-273">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="39cb2-273">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="39cb2-274">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="39cb2-274">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="39cb2-275">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-275">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="39cb2-276">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="39cb2-276">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="39cb2-277">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="39cb2-277">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="39cb2-278">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="39cb2-278">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="39cb2-279">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="39cb2-279">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="39cb2-280">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-280">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="39cb2-281">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="39cb2-281">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="39cb2-282">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="39cb2-282">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="39cb2-283">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-283">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="39cb2-284">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="39cb2-284">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="39cb2-285">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="39cb2-285">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="39cb2-286">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-286">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="39cb2-287">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="39cb2-287">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="39cb2-288">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="39cb2-288">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="39cb2-289">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-289">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="39cb2-290">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="39cb2-290">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="39cb2-291">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="39cb2-291">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="39cb2-292">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="39cb2-292">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="39cb2-293">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="39cb2-293">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="39cb2-294">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="39cb2-294">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="39cb2-295">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="39cb2-295">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="39cb2-296">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="39cb2-296">**mvc, razor**</span></span>

<span data-ttu-id="39cb2-297">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="39cb2-297">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="39cb2-298">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="39cb2-298">The possible values are:</span></span>

- <span data-ttu-id="39cb2-299">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="39cb2-299">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="39cb2-300">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="39cb2-300">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="39cb2-301">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="39cb2-301">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="39cb2-302">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="39cb2-302">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="39cb2-303">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="39cb2-303">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="39cb2-304">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="39cb2-304">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="39cb2-305">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="39cb2-305">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="39cb2-306">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="39cb2-306">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="39cb2-307">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-307">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="39cb2-308">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="39cb2-308">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="39cb2-309">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="39cb2-309">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="39cb2-310">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="39cb2-310">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="39cb2-311">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="39cb2-311">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="39cb2-312">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="39cb2-312">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="39cb2-313">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="39cb2-313">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="39cb2-314">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="39cb2-314">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="39cb2-315">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="39cb2-315">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="39cb2-316">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-316">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="39cb2-317">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="39cb2-317">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="39cb2-318">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="39cb2-318">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="39cb2-319">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-319">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="39cb2-320">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="39cb2-320">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="39cb2-321">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="39cb2-321">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="39cb2-322">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-322">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="39cb2-323">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="39cb2-323">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="39cb2-324">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="39cb2-324">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="39cb2-325">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-325">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="39cb2-326">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="39cb2-326">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="39cb2-327">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="39cb2-327">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="39cb2-328">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-328">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="39cb2-329">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="39cb2-329">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="39cb2-330">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="39cb2-330">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="39cb2-331">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="39cb2-331">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="39cb2-332">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="39cb2-332">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="39cb2-333">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="39cb2-333">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="39cb2-334">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="39cb2-334">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="39cb2-335">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="39cb2-335">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="39cb2-336">**page**</span><span class="sxs-lookup"><span data-stu-id="39cb2-336">**page**</span></span>

<span data-ttu-id="39cb2-337">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="39cb2-337">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="39cb2-338">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-338">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="39cb2-339">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="39cb2-339">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="39cb2-340">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="39cb2-340">**viewimports**</span></span>

<span data-ttu-id="39cb2-341">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="39cb2-341">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="39cb2-342">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-342">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="39cb2-343">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="39cb2-343">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="39cb2-344">**console、xunit、mstest、web、webapi**</span><span class="sxs-lookup"><span data-stu-id="39cb2-344">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="39cb2-345">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="39cb2-345">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="39cb2-346">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-346">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="39cb2-347">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-347">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="39cb2-348">**classlib**</span><span class="sxs-lookup"><span data-stu-id="39cb2-348">**classlib**</span></span>

<span data-ttu-id="39cb2-349">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="39cb2-349">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="39cb2-350">值：`netcoreapp1.0`、`netcoreapp1.1` 或 `netstandard1.0` 到 `netstandard1.6`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-350">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="39cb2-351">默认值为 `netstandard1.4`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-351">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="39cb2-352">**mvc**</span><span class="sxs-lookup"><span data-stu-id="39cb2-352">**mvc**</span></span>

<span data-ttu-id="39cb2-353">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="39cb2-353">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="39cb2-354">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-354">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="39cb2-355">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-355">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="39cb2-356">`-au|--auth` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="39cb2-356">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="39cb2-357">值：`None` 或 `Individual`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-357">Values: `None` or `Individual`.</span></span> <span data-ttu-id="39cb2-358">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-358">The default value is `None`.</span></span>

<span data-ttu-id="39cb2-359">`-uld|--use-local-db` - 指定是否使用 LocalDB，而不是 SQLite。</span><span class="sxs-lookup"><span data-stu-id="39cb2-359">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="39cb2-360">值：`true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-360">Values: `true` or `false`.</span></span> <span data-ttu-id="39cb2-361">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="39cb2-361">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="39cb2-362">示例</span><span class="sxs-lookup"><span data-stu-id="39cb2-362">Examples</span></span>

<span data-ttu-id="39cb2-363">在当前目录中创建 F# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="39cb2-363">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="39cb2-364">在指定目录中创建 .NET Standard 类库项目（仅适用于 .NET Core 2.0 SDK 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="39cb2-364">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="39cb2-365">在当前目录中新建定目标到 .NET Core 2.0 且没有设置身份验证的 ASP.NET Core C# MVC 应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="39cb2-365">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="39cb2-366">新建定目标到 .NET Core 2.0 的 xUnit 应用程序：</span><span class="sxs-lookup"><span data-stu-id="39cb2-366">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="39cb2-367">列出适用于 MVC 的所有模板：</span><span class="sxs-lookup"><span data-stu-id="39cb2-367">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

## <a name="see-also"></a><span data-ttu-id="39cb2-368">请参阅</span><span class="sxs-lookup"><span data-stu-id="39cb2-368">See also</span></span>

[<span data-ttu-id="39cb2-369">dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="39cb2-369">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="39cb2-370">创建 dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="39cb2-370">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="39cb2-371">dotnet/dotnet-template-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="39cb2-371">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="39cb2-372">dotnet new 可用模板</span><span class="sxs-lookup"><span data-stu-id="39cb2-372">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
