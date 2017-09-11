---
title: "dotnet-new 命令 - .NET Core CLI"
description: "dotnet-new 命令可在当前目录中创建新的 .NET Core 项目。"
keywords: "dotnet-new, CLI, CLI 命令, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 56033295b2448b045d5a51dbd84d5429aed77451
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-new"></a><span data-ttu-id="2087c-104">dotnet-new</span><span class="sxs-lookup"><span data-stu-id="2087c-104">dotnet-new</span></span>

## <a name="name"></a><span data-ttu-id="2087c-105">名称</span><span class="sxs-lookup"><span data-stu-id="2087c-105">Name</span></span>

<span data-ttu-id="2087c-106">`dotnet-new` - 根据指定的模板，创建新的项目、配置文件或解决方案。</span><span class="sxs-lookup"><span data-stu-id="2087c-106">`dotnet-new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2087c-107">摘要</span><span class="sxs-lookup"><span data-stu-id="2087c-107">Synopsis</span></span>

```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

## <a name="description"></a><span data-ttu-id="2087c-108">说明</span><span class="sxs-lookup"><span data-stu-id="2087c-108">Description</span></span>

<span data-ttu-id="2087c-109">`dotnet new` 命令为初始化有效的 .NET Core 项目提供了便捷方法。</span><span class="sxs-lookup"><span data-stu-id="2087c-109">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="2087c-110">命令调用[模板引擎](https://github.com/dotnet/templating)，以根据指定的模板和选项在磁盘上创建项目。</span><span class="sxs-lookup"><span data-stu-id="2087c-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="2087c-111">参数</span><span class="sxs-lookup"><span data-stu-id="2087c-111">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="2087c-112">调用命令时要实例化的模板。</span><span class="sxs-lookup"><span data-stu-id="2087c-112">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="2087c-113">每个模板可能具有可传递的特定选项。</span><span class="sxs-lookup"><span data-stu-id="2087c-113">Each template might have specific options you can pass.</span></span> <span data-ttu-id="2087c-114">有关详细信息，请参阅[模板选项](#template-options)。</span><span class="sxs-lookup"><span data-stu-id="2087c-114">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="2087c-115">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="2087c-115">The command contains a default list of templates.</span></span> <span data-ttu-id="2087c-116">使用 `dotnet new -all` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="2087c-116">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="2087c-117">下表显示随 SDK 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="2087c-117">The following table shows the templates that come pre-installed with the SDK.</span></span> <span data-ttu-id="2087c-118">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="2087c-118">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="2087c-119">模板描述</span><span class="sxs-lookup"><span data-stu-id="2087c-119">Template description</span></span>  | <span data-ttu-id="2087c-120">模板名称</span><span class="sxs-lookup"><span data-stu-id="2087c-120">Template name</span></span>  | <span data-ttu-id="2087c-121">语言</span><span class="sxs-lookup"><span data-stu-id="2087c-121">Languages</span></span> |
|----------------------|----------------|-----------|
| <span data-ttu-id="2087c-122">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="2087c-122">Console application</span></span>  | <span data-ttu-id="2087c-123">控制台</span><span class="sxs-lookup"><span data-stu-id="2087c-123">console</span></span>        | <span data-ttu-id="2087c-124">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="2087c-124">[C#], F#</span></span>  |
| <span data-ttu-id="2087c-125">类库</span><span class="sxs-lookup"><span data-stu-id="2087c-125">Class library</span></span>        | <span data-ttu-id="2087c-126">classlib</span><span class="sxs-lookup"><span data-stu-id="2087c-126">classlib</span></span>       | <span data-ttu-id="2087c-127">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="2087c-127">[C#], F#</span></span>  |
| <span data-ttu-id="2087c-128">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="2087c-128">Unit test project</span></span>    | <span data-ttu-id="2087c-129">mstest</span><span class="sxs-lookup"><span data-stu-id="2087c-129">mstest</span></span>         | <span data-ttu-id="2087c-130">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="2087c-130">[C#], F#</span></span>  |
| <span data-ttu-id="2087c-131">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="2087c-131">xUnit test project</span></span>   | <span data-ttu-id="2087c-132">xunit</span><span class="sxs-lookup"><span data-stu-id="2087c-132">xunit</span></span>          | <span data-ttu-id="2087c-133">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="2087c-133">[C#], F#</span></span>  |
| <span data-ttu-id="2087c-134">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="2087c-134">ASP.NET Core empty</span></span>   | <span data-ttu-id="2087c-135">Web</span><span class="sxs-lookup"><span data-stu-id="2087c-135">web</span></span>            | <span data-ttu-id="2087c-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="2087c-136">[C#]</span></span>      |
| <span data-ttu-id="2087c-137">ASP.NET Core Web 应用</span><span class="sxs-lookup"><span data-stu-id="2087c-137">ASP.NET Core web app</span></span> | <span data-ttu-id="2087c-138">mvc</span><span class="sxs-lookup"><span data-stu-id="2087c-138">mvc</span></span>            | <span data-ttu-id="2087c-139">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="2087c-139">[C#], F#</span></span>  |
| <span data-ttu-id="2087c-140">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="2087c-140">ASP.NET Core web api</span></span> | <span data-ttu-id="2087c-141">webapi</span><span class="sxs-lookup"><span data-stu-id="2087c-141">webapi</span></span>         | <span data-ttu-id="2087c-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="2087c-142">[C#]</span></span>      |
| <span data-ttu-id="2087c-143">Nuget 配置</span><span class="sxs-lookup"><span data-stu-id="2087c-143">Nuget config</span></span>         | <span data-ttu-id="2087c-144">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="2087c-144">nugetconfig</span></span>    |           |
| <span data-ttu-id="2087c-145">Web 配置</span><span class="sxs-lookup"><span data-stu-id="2087c-145">Web config</span></span>           | <span data-ttu-id="2087c-146">webconfig</span><span class="sxs-lookup"><span data-stu-id="2087c-146">webconfig</span></span>      |           |
| <span data-ttu-id="2087c-147">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="2087c-147">Solution file</span></span>        | <span data-ttu-id="2087c-148">sln</span><span class="sxs-lookup"><span data-stu-id="2087c-148">sln</span></span>            |           |

## <a name="options"></a><span data-ttu-id="2087c-149">选项</span><span class="sxs-lookup"><span data-stu-id="2087c-149">Options</span></span>

`-h|--help`

<span data-ttu-id="2087c-150">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="2087c-150">Prints out help for the command.</span></span> <span data-ttu-id="2087c-151">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="2087c-151">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="2087c-152">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="2087c-152">Lists templates containing the specified name.</span></span> <span data-ttu-id="2087c-153">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="2087c-153">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="2087c-154">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="2087c-154">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="2087c-155">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="2087c-155">The language of the template to create.</span></span> <span data-ttu-id="2087c-156">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="2087c-156">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="2087c-157">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="2087c-157">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="2087c-158">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="2087c-158">The name for the created output.</span></span> <span data-ttu-id="2087c-159">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="2087c-159">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="2087c-160">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="2087c-160">Location to place the generated output.</span></span> <span data-ttu-id="2087c-161">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="2087c-161">The default is the current directory.</span></span>

`-all|--show-all`

<span data-ttu-id="2087c-162">单独在 `dotnet new` 命令的上下文中运行时，显示特定类型的项目的所有模板。</span><span class="sxs-lookup"><span data-stu-id="2087c-162">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="2087c-163">在特定模板（如 `dotnet new web -all`）的上下文中运行时，`-all` 解释为一个强制创建标记。</span><span class="sxs-lookup"><span data-stu-id="2087c-163">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="2087c-164">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="2087c-164">This is required when the output directory already contains a project.</span></span>

## <a name="template-options"></a><span data-ttu-id="2087c-165">模板选项</span><span class="sxs-lookup"><span data-stu-id="2087c-165">Template options</span></span>

<span data-ttu-id="2087c-166">每个项目模板都可能有附加选项。</span><span class="sxs-lookup"><span data-stu-id="2087c-166">Each project template may have additional options available.</span></span> <span data-ttu-id="2087c-167">核心模板有以下选项：</span><span class="sxs-lookup"><span data-stu-id="2087c-167">The core templates have the following options:</span></span>

<span data-ttu-id="2087c-168">**console、xunit、mstest、web、webapi**</span><span class="sxs-lookup"><span data-stu-id="2087c-168">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="2087c-169">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="2087c-169">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2087c-170">值：`netcoreapp1.0` 或 `netcoreapp1.1`（默认：`netcoreapp1.0`）</span><span class="sxs-lookup"><span data-stu-id="2087c-170">Values: `netcoreapp1.0` or `netcoreapp1.1` (Default: `netcoreapp1.0`)</span></span>

<span data-ttu-id="2087c-171">**mvc**</span><span class="sxs-lookup"><span data-stu-id="2087c-171">**mvc**</span></span>

<span data-ttu-id="2087c-172">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="2087c-172">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2087c-173">值：`netcoreapp1.0` 或 `netcoreapp1.1`（`Default: netcoreapp1.0`）</span><span class="sxs-lookup"><span data-stu-id="2087c-173">Values: `netcoreapp1.0` or `netcoreapp1.1` (`Default: netcoreapp1.0`)</span></span>

<span data-ttu-id="2087c-174">`-au|--auth` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="2087c-174">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="2087c-175">值：`None` 或 `Individual`（默认：`None`）</span><span class="sxs-lookup"><span data-stu-id="2087c-175">Values: `None` or `Individual` (Default: `None`)</span></span>

<span data-ttu-id="2087c-176">`-uld|--use-local-db` - 指定是否使用 LocalDB，而不是 SQLite。</span><span class="sxs-lookup"><span data-stu-id="2087c-176">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="2087c-177">值：`true` 或 `false`（默认：`false`）</span><span class="sxs-lookup"><span data-stu-id="2087c-177">Values: `true` or `false` (Default: `false`)</span></span>

<span data-ttu-id="2087c-178">**classlib**</span><span class="sxs-lookup"><span data-stu-id="2087c-178">**classlib**</span></span>

<span data-ttu-id="2087c-179">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="2087c-179">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2087c-180">值：`netcoreapp1.0`、`netcoreapp1.1` 或 `netstandard1.0` 到 `netstandard1.6`（默认：`netstandard1.4`）</span><span class="sxs-lookup"><span data-stu-id="2087c-180">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6` (Default: `netstandard1.4`)</span></span>

## <a name="examples"></a><span data-ttu-id="2087c-181">示例</span><span class="sxs-lookup"><span data-stu-id="2087c-181">Examples</span></span>

<span data-ttu-id="2087c-182">在当前目录中创建 F# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="2087c-182">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#` 
   
<span data-ttu-id="2087c-183">在当前目录中新建定位 .NET Core 1.0 且没有设置身份验证的 ASP.NET Core C# MVC 应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="2087c-183">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 1.0:</span></span>  

`dotnet new mvc -au None -f netcoreapp1.0`
 
<span data-ttu-id="2087c-184">新建定位 .NET Core 1.1 的 xUnit 应用程序：</span><span class="sxs-lookup"><span data-stu-id="2087c-184">Create a new xUnit application targeting .NET Core 1.1:</span></span>

`dotnet new xunit --framework netcoreapp1.1`

<span data-ttu-id="2087c-185">列出适用于 MVC 的所有模板：</span><span class="sxs-lookup"><span data-stu-id="2087c-185">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

