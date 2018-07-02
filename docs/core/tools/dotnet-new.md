---
title: dotnet new 命令 - .NET Core CLI
description: dotnet new 命令可根据指定模板新建 .NET Core 项目。
author: mairaw
ms.author: mairaw
ms.date: 06/12/2018
ms.openlocfilehash: f0ef91361dfbc2c2ba5532fbd607786289e98c69
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207757"
---
# <a name="dotnet-new"></a><span data-ttu-id="c393a-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c393a-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c393a-104">name</span><span class="sxs-lookup"><span data-stu-id="c393a-104">Name</span></span>

<span data-ttu-id="c393a-105">`dotnet new` - 根据指定的模板，创建新的项目、配置文件或解决方案。</span><span class="sxs-lookup"><span data-stu-id="c393a-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c393a-106">摘要</span><span class="sxs-lookup"><span data-stu-id="c393a-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c393a-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c393a-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c393a-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c393a-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c393a-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c393a-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="c393a-110">描述</span><span class="sxs-lookup"><span data-stu-id="c393a-110">Description</span></span>

<span data-ttu-id="c393a-111">`dotnet new` 命令为初始化有效的 .NET Core 项目提供了便捷方法。</span><span class="sxs-lookup"><span data-stu-id="c393a-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="c393a-112">命令调用[模板引擎](https://github.com/dotnet/templating)，以根据指定的模板和选项在磁盘上创建项目。</span><span class="sxs-lookup"><span data-stu-id="c393a-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="c393a-113">自变量</span><span class="sxs-lookup"><span data-stu-id="c393a-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="c393a-114">调用命令时要实例化的模板。</span><span class="sxs-lookup"><span data-stu-id="c393a-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="c393a-115">每个模板可能具有可传递的特定选项。</span><span class="sxs-lookup"><span data-stu-id="c393a-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="c393a-116">有关详细信息，请参阅[模板选项](#template-options)。</span><span class="sxs-lookup"><span data-stu-id="c393a-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c393a-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c393a-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="c393a-118">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="c393a-118">The command contains a default list of templates.</span></span> <span data-ttu-id="c393a-119">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="c393a-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="c393a-120">下表列出了随 .NET Core SDK 2.1.300 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="c393a-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="c393a-121">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="c393a-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="c393a-122">模板描述</span><span class="sxs-lookup"><span data-stu-id="c393a-122">Template description</span></span>                          | <span data-ttu-id="c393a-123">模板名称</span><span class="sxs-lookup"><span data-stu-id="c393a-123">Template name</span></span>   | <span data-ttu-id="c393a-124">语言</span><span class="sxs-lookup"><span data-stu-id="c393a-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="c393a-125">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="c393a-125">Console application</span></span>                          | `console`       | <span data-ttu-id="c393a-126">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="c393a-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c393a-127">类库</span><span class="sxs-lookup"><span data-stu-id="c393a-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="c393a-128">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="c393a-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c393a-129">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="c393a-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="c393a-130">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="c393a-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c393a-131">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="c393a-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="c393a-132">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="c393a-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c393a-133">Razor 页</span><span class="sxs-lookup"><span data-stu-id="c393a-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="c393a-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="c393a-134">[C#]</span></span>          |
| <span data-ttu-id="c393a-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="c393a-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="c393a-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="c393a-136">[C#]</span></span>          |
| <span data-ttu-id="c393a-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="c393a-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="c393a-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="c393a-138">[C#]</span></span>          |
| <span data-ttu-id="c393a-139">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="c393a-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="c393a-140">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c393a-140">[C#], F#</span></span>      |
| <span data-ttu-id="c393a-141">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="c393a-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="c393a-142">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c393a-142">[C#], F#</span></span>      |
| <span data-ttu-id="c393a-143">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="c393a-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="c393a-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="c393a-144">[C#]</span></span>          |
| <span data-ttu-id="c393a-145">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c393a-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="c393a-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="c393a-146">[C#]</span></span>          |
| <span data-ttu-id="c393a-147">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c393a-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="c393a-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="c393a-148">[C#]</span></span>          |
| <span data-ttu-id="c393a-149">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c393a-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="c393a-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="c393a-150">[C#]</span></span>          |
| <span data-ttu-id="c393a-151">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="c393a-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="c393a-152">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c393a-152">[C#], F#</span></span>      |
| <span data-ttu-id="c393a-153">Razor 类库</span><span class="sxs-lookup"><span data-stu-id="c393a-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="c393a-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="c393a-154">[C#]</span></span>          |
| <span data-ttu-id="c393a-155">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="c393a-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="c393a-156">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="c393a-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="c393a-157">Web 配置</span><span class="sxs-lookup"><span data-stu-id="c393a-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="c393a-158">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="c393a-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c393a-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c393a-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="c393a-160">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="c393a-160">The command contains a default list of templates.</span></span> <span data-ttu-id="c393a-161">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="c393a-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="c393a-162">下表列出了随 .NET Core SDK 2.0 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="c393a-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="c393a-163">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="c393a-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="c393a-164">模板描述</span><span class="sxs-lookup"><span data-stu-id="c393a-164">Template description</span></span>                          | <span data-ttu-id="c393a-165">模板名称</span><span class="sxs-lookup"><span data-stu-id="c393a-165">Template name</span></span> | <span data-ttu-id="c393a-166">语言</span><span class="sxs-lookup"><span data-stu-id="c393a-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="c393a-167">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="c393a-167">Console application</span></span>                          | `console`     | <span data-ttu-id="c393a-168">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="c393a-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c393a-169">类库</span><span class="sxs-lookup"><span data-stu-id="c393a-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="c393a-170">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="c393a-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c393a-171">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="c393a-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="c393a-172">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="c393a-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c393a-173">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="c393a-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="c393a-174">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="c393a-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c393a-175">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="c393a-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="c393a-176">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c393a-176">[C#], F#</span></span>      |
| <span data-ttu-id="c393a-177">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="c393a-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="c393a-178">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c393a-178">[C#], F#</span></span>      |
| <span data-ttu-id="c393a-179">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="c393a-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="c393a-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="c393a-180">[C#]</span></span>          |
| <span data-ttu-id="c393a-181">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c393a-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="c393a-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="c393a-182">[C#]</span></span>          |
| <span data-ttu-id="c393a-183">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c393a-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="c393a-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="c393a-184">[C#]</span></span>          |
| <span data-ttu-id="c393a-185">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c393a-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="c393a-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="c393a-186">[C#]</span></span>          |
| <span data-ttu-id="c393a-187">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="c393a-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="c393a-188">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c393a-188">[C#], F#</span></span>      |
| <span data-ttu-id="c393a-189">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="c393a-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="c393a-190">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="c393a-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="c393a-191">Web 配置</span><span class="sxs-lookup"><span data-stu-id="c393a-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="c393a-192">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="c393a-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="c393a-193">Razor 页</span><span class="sxs-lookup"><span data-stu-id="c393a-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="c393a-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="c393a-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="c393a-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="c393a-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c393a-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c393a-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="c393a-197">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="c393a-197">The command contains a default list of templates.</span></span> <span data-ttu-id="c393a-198">使用 `dotnet new -all` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="c393a-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="c393a-199">下表列出了随 .NET Core SDK 1.x 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="c393a-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="c393a-200">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="c393a-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="c393a-201">模板描述</span><span class="sxs-lookup"><span data-stu-id="c393a-201">Template description</span></span>  | <span data-ttu-id="c393a-202">模板名称</span><span class="sxs-lookup"><span data-stu-id="c393a-202">Template name</span></span> | <span data-ttu-id="c393a-203">语言</span><span class="sxs-lookup"><span data-stu-id="c393a-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="c393a-204">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="c393a-204">Console application</span></span>  | `console`     | <span data-ttu-id="c393a-205">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c393a-205">[C#], F#</span></span>  |
| <span data-ttu-id="c393a-206">类库</span><span class="sxs-lookup"><span data-stu-id="c393a-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="c393a-207">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c393a-207">[C#], F#</span></span>  |
| <span data-ttu-id="c393a-208">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="c393a-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="c393a-209">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c393a-209">[C#], F#</span></span>  |
| <span data-ttu-id="c393a-210">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="c393a-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="c393a-211">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c393a-211">[C#], F#</span></span>  |
| <span data-ttu-id="c393a-212">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="c393a-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="c393a-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="c393a-213">[C#]</span></span>      |
| <span data-ttu-id="c393a-214">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="c393a-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="c393a-215">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c393a-215">[C#], F#</span></span>  |
| <span data-ttu-id="c393a-216">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="c393a-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="c393a-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="c393a-217">[C#]</span></span>      |
| <span data-ttu-id="c393a-218">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="c393a-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="c393a-219">Web 配置</span><span class="sxs-lookup"><span data-stu-id="c393a-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="c393a-220">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="c393a-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="c393a-221">选项</span><span class="sxs-lookup"><span data-stu-id="c393a-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c393a-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c393a-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="c393a-223">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="c393a-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="c393a-224">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="c393a-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="c393a-225">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="c393a-225">Prints out help for the command.</span></span> <span data-ttu-id="c393a-226">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="c393a-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="c393a-227">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="c393a-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="c393a-228">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="c393a-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="c393a-229">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="c393a-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="c393a-230">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="c393a-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="c393a-231">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="c393a-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="c393a-232">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="c393a-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="c393a-233">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="c393a-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="c393a-234">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="c393a-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="c393a-235">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="c393a-235">The language of the template to create.</span></span> <span data-ttu-id="c393a-236">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="c393a-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c393a-237">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="c393a-237">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="c393a-238">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="c393a-238">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="c393a-239">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="c393a-239">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="c393a-240">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="c393a-240">The name for the created output.</span></span> <span data-ttu-id="c393a-241">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="c393a-241">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="c393a-242">指定在安装期间要使用的 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="c393a-242">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c393a-243">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="c393a-243">Location to place the generated output.</span></span> <span data-ttu-id="c393a-244">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="c393a-244">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="c393a-245">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="c393a-245">Filters templates based on available types.</span></span> <span data-ttu-id="c393a-246">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="c393a-246">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="c393a-247">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="c393a-247">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="c393a-248">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="c393a-248">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="c393a-249">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="c393a-249">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="c393a-250">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="c393a-250">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c393a-251">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c393a-251">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="c393a-252">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="c393a-252">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="c393a-253">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="c393a-253">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="c393a-254">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="c393a-254">Prints out help for the command.</span></span> <span data-ttu-id="c393a-255">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="c393a-255">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="c393a-256">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="c393a-256">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="c393a-257">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="c393a-257">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="c393a-258">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="c393a-258">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="c393a-259">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="c393a-259">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="c393a-260">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="c393a-260">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="c393a-261">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="c393a-261">Lists templates containing the specified name.</span></span> <span data-ttu-id="c393a-262">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="c393a-262">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="c393a-263">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="c393a-263">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="c393a-264">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="c393a-264">The language of the template to create.</span></span> <span data-ttu-id="c393a-265">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="c393a-265">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c393a-266">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="c393a-266">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="c393a-267">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="c393a-267">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="c393a-268">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="c393a-268">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="c393a-269">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="c393a-269">The name for the created output.</span></span> <span data-ttu-id="c393a-270">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="c393a-270">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c393a-271">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="c393a-271">Location to place the generated output.</span></span> <span data-ttu-id="c393a-272">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="c393a-272">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="c393a-273">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="c393a-273">Filters templates based on available types.</span></span> <span data-ttu-id="c393a-274">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="c393a-274">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="c393a-275">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="c393a-275">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="c393a-276">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="c393a-276">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="c393a-277">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="c393a-277">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="c393a-278">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="c393a-278">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c393a-279">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c393a-279">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="c393a-280">单独在 `dotnet new` 命令的上下文中运行时，显示特定类型的项目的所有模板。</span><span class="sxs-lookup"><span data-stu-id="c393a-280">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="c393a-281">在特定模板（如 `dotnet new web -all`）的上下文中运行时，`-all` 解释为一个强制创建标记。</span><span class="sxs-lookup"><span data-stu-id="c393a-281">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="c393a-282">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="c393a-282">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="c393a-283">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="c393a-283">Prints out help for the command.</span></span> <span data-ttu-id="c393a-284">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="c393a-284">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="c393a-285">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="c393a-285">Lists templates containing the specified name.</span></span> <span data-ttu-id="c393a-286">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="c393a-286">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="c393a-287">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="c393a-287">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="c393a-288">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="c393a-288">The language of the template to create.</span></span> <span data-ttu-id="c393a-289">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="c393a-289">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c393a-290">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="c393a-290">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="c393a-291">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="c393a-291">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="c393a-292">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="c393a-292">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="c393a-293">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="c393a-293">The name for the created output.</span></span> <span data-ttu-id="c393a-294">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="c393a-294">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c393a-295">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="c393a-295">Location to place the generated output.</span></span> <span data-ttu-id="c393a-296">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="c393a-296">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="c393a-297">模板选项</span><span class="sxs-lookup"><span data-stu-id="c393a-297">Template options</span></span>

<span data-ttu-id="c393a-298">每个项目模板都可能有附加选项。</span><span class="sxs-lookup"><span data-stu-id="c393a-298">Each project template may have additional options available.</span></span> <span data-ttu-id="c393a-299">核心模板有以下附加选项：</span><span class="sxs-lookup"><span data-stu-id="c393a-299">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c393a-300">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c393a-300">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="c393a-301">console、angular、react、reactredux、razorclasslib</span><span class="sxs-lookup"><span data-stu-id="c393a-301">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="c393a-302">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c393a-302">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c393a-303">**classlib**</span><span class="sxs-lookup"><span data-stu-id="c393a-303">**classlib**</span></span>

<span data-ttu-id="c393a-304">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="c393a-304">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c393a-305">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="c393a-305">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="c393a-306">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="c393a-306">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="c393a-307">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c393a-307">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c393a-308">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="c393a-308">**mstest, xunit**</span></span>

<span data-ttu-id="c393a-309">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="c393a-309">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="c393a-310">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c393a-310">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c393a-311">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="c393a-311">**globaljson**</span></span>

<span data-ttu-id="c393a-312">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="c393a-312">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="c393a-313">**web**</span><span class="sxs-lookup"><span data-stu-id="c393a-313">**web**</span></span>

<span data-ttu-id="c393a-314">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="c393a-314">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c393a-315">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c393a-315">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c393a-316">**webapi**</span><span class="sxs-lookup"><span data-stu-id="c393a-316">**webapi**</span></span>

<span data-ttu-id="c393a-317">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="c393a-317">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c393a-318">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="c393a-318">The possible values are:</span></span>

- <span data-ttu-id="c393a-319">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="c393a-319">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c393a-320">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-320">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c393a-321">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-321">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c393a-322">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-322">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c393a-323">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="c393a-323">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c393a-324">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-324">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c393a-325">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="c393a-325">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="c393a-326">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="c393a-326">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c393a-327">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-327">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c393a-328">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="c393a-328">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c393a-329">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-329">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c393a-330">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="c393a-330">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c393a-331">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="c393a-331">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c393a-332">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-332">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="c393a-333">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="c393a-333">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c393a-334">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="c393a-334">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c393a-335">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-335">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c393a-336">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="c393a-336">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c393a-337">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="c393a-337">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c393a-338">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-338">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c393a-339">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="c393a-339">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c393a-340">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="c393a-340">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c393a-341">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-341">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c393a-342">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="c393a-342">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c393a-343">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="c393a-343">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c393a-344">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-344">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c393a-345">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c393a-345">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c393a-346">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="c393a-346">**mvc, razor**</span></span>

<span data-ttu-id="c393a-347">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="c393a-347">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c393a-348">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="c393a-348">The possible values are:</span></span>

- <span data-ttu-id="c393a-349">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="c393a-349">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c393a-350">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-350">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="c393a-351">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-351">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c393a-352">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-352">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c393a-353">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-353">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="c393a-354">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-354">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c393a-355">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="c393a-355">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c393a-356">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-356">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c393a-357">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="c393a-357">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="c393a-358">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="c393a-358">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c393a-359">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-359">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c393a-360">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="c393a-360">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="c393a-361">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-361">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c393a-362">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="c393a-362">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="c393a-363">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-363">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c393a-364">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="c393a-364">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c393a-365">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-365">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="c393a-366">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="c393a-366">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c393a-367">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="c393a-367">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c393a-368">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-368">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="c393a-369">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="c393a-369">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c393a-370">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="c393a-370">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c393a-371">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-371">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c393a-372">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="c393a-372">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c393a-373">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="c393a-373">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c393a-374">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-374">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c393a-375">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="c393a-375">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c393a-376">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="c393a-376">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="c393a-377">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-377">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c393a-378">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="c393a-378">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="c393a-379">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="c393a-379">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c393a-380">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-380">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c393a-381">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="c393a-381">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c393a-382">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="c393a-382">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="c393a-383">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="c393a-383">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c393a-384">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-384">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c393a-385">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c393a-385">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c393a-386">**page**</span><span class="sxs-lookup"><span data-stu-id="c393a-386">**page**</span></span>

<span data-ttu-id="c393a-387">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="c393a-387">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c393a-388">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="c393a-388">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="c393a-389">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="c393a-389">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="c393a-390">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="c393a-390">**viewimports**</span></span>

<span data-ttu-id="c393a-391">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="c393a-391">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c393a-392">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="c393a-392">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c393a-393">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c393a-393">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="c393a-394">**console、angular、react、reactredux**</span><span class="sxs-lookup"><span data-stu-id="c393a-394">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="c393a-395">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c393a-395">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c393a-396">**classlib**</span><span class="sxs-lookup"><span data-stu-id="c393a-396">**classlib**</span></span>

<span data-ttu-id="c393a-397">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="c393a-397">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c393a-398">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="c393a-398">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="c393a-399">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="c393a-399">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="c393a-400">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c393a-400">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c393a-401">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="c393a-401">**mstest, xunit**</span></span>

<span data-ttu-id="c393a-402">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="c393a-402">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="c393a-403">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c393a-403">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c393a-404">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="c393a-404">**globaljson**</span></span>

<span data-ttu-id="c393a-405">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="c393a-405">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="c393a-406">**web**</span><span class="sxs-lookup"><span data-stu-id="c393a-406">**web**</span></span>

<span data-ttu-id="c393a-407">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="c393a-407">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c393a-408">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c393a-408">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c393a-409">**webapi**</span><span class="sxs-lookup"><span data-stu-id="c393a-409">**webapi**</span></span>

<span data-ttu-id="c393a-410">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="c393a-410">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c393a-411">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="c393a-411">The possible values are:</span></span>

- <span data-ttu-id="c393a-412">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="c393a-412">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c393a-413">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-413">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c393a-414">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-414">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c393a-415">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-415">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c393a-416">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="c393a-416">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c393a-417">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-417">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c393a-418">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="c393a-418">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="c393a-419">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="c393a-419">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c393a-420">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-420">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c393a-421">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="c393a-421">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c393a-422">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-422">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c393a-423">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="c393a-423">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c393a-424">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="c393a-424">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c393a-425">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-425">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="c393a-426">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="c393a-426">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c393a-427">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="c393a-427">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c393a-428">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-428">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c393a-429">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="c393a-429">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c393a-430">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="c393a-430">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c393a-431">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c393a-432">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="c393a-432">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c393a-433">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="c393a-433">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c393a-434">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-434">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c393a-435">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="c393a-435">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c393a-436">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="c393a-436">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c393a-437">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-437">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c393a-438">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c393a-438">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c393a-439">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="c393a-439">**mvc, razor**</span></span>

<span data-ttu-id="c393a-440">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="c393a-440">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c393a-441">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="c393a-441">The possible values are:</span></span>

- <span data-ttu-id="c393a-442">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="c393a-442">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c393a-443">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-443">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="c393a-444">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-444">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c393a-445">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-445">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c393a-446">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-446">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="c393a-447">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-447">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c393a-448">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="c393a-448">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c393a-449">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-449">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c393a-450">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="c393a-450">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="c393a-451">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="c393a-451">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c393a-452">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-452">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c393a-453">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="c393a-453">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="c393a-454">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-454">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c393a-455">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="c393a-455">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="c393a-456">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-456">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c393a-457">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="c393a-457">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c393a-458">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-458">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="c393a-459">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="c393a-459">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c393a-460">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="c393a-460">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c393a-461">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-461">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="c393a-462">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="c393a-462">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c393a-463">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="c393a-463">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c393a-464">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-464">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c393a-465">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="c393a-465">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c393a-466">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="c393a-466">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c393a-467">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-467">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c393a-468">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="c393a-468">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c393a-469">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="c393a-469">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="c393a-470">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c393a-470">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c393a-471">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="c393a-471">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="c393a-472">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="c393a-472">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c393a-473">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-473">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c393a-474">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="c393a-474">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c393a-475">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="c393a-475">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="c393a-476">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="c393a-476">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c393a-477">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c393a-477">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c393a-478">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c393a-478">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c393a-479">**page**</span><span class="sxs-lookup"><span data-stu-id="c393a-479">**page**</span></span>

<span data-ttu-id="c393a-480">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="c393a-480">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c393a-481">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="c393a-481">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="c393a-482">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="c393a-482">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="c393a-483">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="c393a-483">**viewimports**</span></span>

<span data-ttu-id="c393a-484">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="c393a-484">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c393a-485">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="c393a-485">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c393a-486">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c393a-486">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="c393a-487">**console、xunit、mstest、web、webapi**</span><span class="sxs-lookup"><span data-stu-id="c393a-487">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="c393a-488">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="c393a-488">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c393a-489">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="c393a-489">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="c393a-490">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="c393a-490">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="c393a-491">**classlib**</span><span class="sxs-lookup"><span data-stu-id="c393a-491">**classlib**</span></span>

<span data-ttu-id="c393a-492">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="c393a-492">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c393a-493">值：`netcoreapp1.0`、`netcoreapp1.1` 或 `netstandard1.0` 到 `netstandard1.6`。</span><span class="sxs-lookup"><span data-stu-id="c393a-493">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="c393a-494">默认值为 `netstandard1.4`。</span><span class="sxs-lookup"><span data-stu-id="c393a-494">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="c393a-495">**mvc**</span><span class="sxs-lookup"><span data-stu-id="c393a-495">**mvc**</span></span>

<span data-ttu-id="c393a-496">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="c393a-496">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c393a-497">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="c393a-497">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="c393a-498">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="c393a-498">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="c393a-499">`-au|--auth` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="c393a-499">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="c393a-500">值：`None` 或 `Individual`。</span><span class="sxs-lookup"><span data-stu-id="c393a-500">Values: `None` or `Individual`.</span></span> <span data-ttu-id="c393a-501">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="c393a-501">The default value is `None`.</span></span>

<span data-ttu-id="c393a-502">`-uld|--use-local-db` - 指定是否使用 LocalDB，而不是 SQLite。</span><span class="sxs-lookup"><span data-stu-id="c393a-502">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="c393a-503">值：`true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="c393a-503">Values: `true` or `false`.</span></span> <span data-ttu-id="c393a-504">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="c393a-504">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="c393a-505">示例</span><span class="sxs-lookup"><span data-stu-id="c393a-505">Examples</span></span>

<span data-ttu-id="c393a-506">在当前目录中创建 F# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="c393a-506">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="c393a-507">在指定目录中创建 .NET Standard 类库项目（仅适用于 .NET Core SDK 2.0 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="c393a-507">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="c393a-508">在当前目录中新建没有设置身份验证的 ASP.NET Core C# MVC 应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="c393a-508">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="c393a-509">创建新的 xUnit 应用程序：</span><span class="sxs-lookup"><span data-stu-id="c393a-509">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="c393a-510">列出适用于 MVC 的所有模板：</span><span class="sxs-lookup"><span data-stu-id="c393a-510">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="c393a-511">安装适用于 ASP.NET Core 的单页应用程序模板 2.0 版（命令选项仅可用于 .NET Core SDK 1.1 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="c393a-511">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="c393a-512">在当前目录中创建 global.json，将 SDK 版本设为 2.0.0（仅适用于 .NET Core SDK 2.0 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="c393a-512">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="c393a-513">请参阅</span><span class="sxs-lookup"><span data-stu-id="c393a-513">See also</span></span>

[<span data-ttu-id="c393a-514">dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="c393a-514">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="c393a-515">创建 dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="c393a-515">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="c393a-516">dotnet/dotnet-template-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="c393a-516">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="c393a-517">dotnet new 可用模板</span><span class="sxs-lookup"><span data-stu-id="c393a-517">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
