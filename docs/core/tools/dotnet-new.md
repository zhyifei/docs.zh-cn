---
title: dotnet new 命令 - .NET Core CLI
description: dotnet new 命令可根据指定模板新建 .NET Core 项目。
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: ae24c4145cc67ca863c07e4d22af8a1c2c2dd732
ms.sourcegitcommit: 3540f614fc94f77ca4ab58df66db2d0f4d52dfee
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2018
ms.locfileid: "34570458"
---
# <a name="dotnet-new"></a><span data-ttu-id="1b7f5-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="1b7f5-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="1b7f5-104">name</span><span class="sxs-lookup"><span data-stu-id="1b7f5-104">Name</span></span>

<span data-ttu-id="1b7f5-105">`dotnet new` - 根据指定的模板，创建新的项目、配置文件或解决方案。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1b7f5-106">摘要</span><span class="sxs-lookup"><span data-stu-id="1b7f5-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="1b7f5-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1b7f5-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="1b7f5-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="1b7f5-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1b7f5-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1b7f5-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="1b7f5-110">描述</span><span class="sxs-lookup"><span data-stu-id="1b7f5-110">Description</span></span>

<span data-ttu-id="1b7f5-111">`dotnet new` 命令为初始化有效的 .NET Core 项目提供了便捷方法。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="1b7f5-112">命令调用[模板引擎](https://github.com/dotnet/templating)，以根据指定的模板和选项在磁盘上创建项目。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="1b7f5-113">自变量</span><span class="sxs-lookup"><span data-stu-id="1b7f5-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="1b7f5-114">调用命令时要实例化的模板。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="1b7f5-115">每个模板可能具有可传递的特定选项。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="1b7f5-116">有关详细信息，请参阅[模板选项](#template-options)。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="1b7f5-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1b7f5-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="1b7f5-118">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-118">The command contains a default list of templates.</span></span> <span data-ttu-id="1b7f5-119">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="1b7f5-120">下表列出了随 .NET Core SDK 2.1.300 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="1b7f5-121">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="1b7f5-122">模板描述</span><span class="sxs-lookup"><span data-stu-id="1b7f5-122">Template description</span></span>                          | <span data-ttu-id="1b7f5-123">模板名称</span><span class="sxs-lookup"><span data-stu-id="1b7f5-123">Template name</span></span>   | <span data-ttu-id="1b7f5-124">语言</span><span class="sxs-lookup"><span data-stu-id="1b7f5-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="1b7f5-125">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="1b7f5-125">Console application</span></span>                          | `console`       | <span data-ttu-id="1b7f5-126">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="1b7f5-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="1b7f5-127">类库</span><span class="sxs-lookup"><span data-stu-id="1b7f5-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="1b7f5-128">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="1b7f5-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="1b7f5-129">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="1b7f5-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="1b7f5-130">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="1b7f5-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="1b7f5-131">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="1b7f5-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="1b7f5-132">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="1b7f5-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="1b7f5-133">Razor 页</span><span class="sxs-lookup"><span data-stu-id="1b7f5-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="1b7f5-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="1b7f5-134">[C#]</span></span>          |
| <span data-ttu-id="1b7f5-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="1b7f5-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="1b7f5-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="1b7f5-136">[C#]</span></span>          |
| <span data-ttu-id="1b7f5-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="1b7f5-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="1b7f5-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="1b7f5-138">[C#]</span></span>          |
| <span data-ttu-id="1b7f5-139">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="1b7f5-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="1b7f5-140">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="1b7f5-140">[C#], F#</span></span>      |
| <span data-ttu-id="1b7f5-141">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="1b7f5-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="1b7f5-142">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="1b7f5-142">[C#], F#</span></span>      |
| <span data-ttu-id="1b7f5-143">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="1b7f5-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="1b7f5-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="1b7f5-144">[C#]</span></span>          |
| <span data-ttu-id="1b7f5-145">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1b7f5-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="1b7f5-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="1b7f5-146">[C#]</span></span>          |
| <span data-ttu-id="1b7f5-147">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1b7f5-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="1b7f5-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="1b7f5-148">[C#]</span></span>          |
| <span data-ttu-id="1b7f5-149">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1b7f5-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="1b7f5-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="1b7f5-150">[C#]</span></span>          |
| <span data-ttu-id="1b7f5-151">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="1b7f5-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="1b7f5-152">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="1b7f5-152">[C#], F#</span></span>      |
| <span data-ttu-id="1b7f5-153">Razor 类库</span><span class="sxs-lookup"><span data-stu-id="1b7f5-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="1b7f5-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="1b7f5-154">[C#]</span></span>          |
| <span data-ttu-id="1b7f5-155">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="1b7f5-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="1b7f5-156">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="1b7f5-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="1b7f5-157">Web 配置</span><span class="sxs-lookup"><span data-stu-id="1b7f5-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="1b7f5-158">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="1b7f5-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="1b7f5-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="1b7f5-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="1b7f5-160">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-160">The command contains a default list of templates.</span></span> <span data-ttu-id="1b7f5-161">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="1b7f5-162">下表列出了随 .NET Core SDK 2.0 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="1b7f5-163">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="1b7f5-164">模板描述</span><span class="sxs-lookup"><span data-stu-id="1b7f5-164">Template description</span></span>                          | <span data-ttu-id="1b7f5-165">模板名称</span><span class="sxs-lookup"><span data-stu-id="1b7f5-165">Template name</span></span> | <span data-ttu-id="1b7f5-166">语言</span><span class="sxs-lookup"><span data-stu-id="1b7f5-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="1b7f5-167">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="1b7f5-167">Console application</span></span>                          | `console`     | <span data-ttu-id="1b7f5-168">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="1b7f5-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="1b7f5-169">类库</span><span class="sxs-lookup"><span data-stu-id="1b7f5-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="1b7f5-170">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="1b7f5-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="1b7f5-171">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="1b7f5-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="1b7f5-172">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="1b7f5-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="1b7f5-173">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="1b7f5-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="1b7f5-174">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="1b7f5-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="1b7f5-175">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="1b7f5-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="1b7f5-176">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="1b7f5-176">[C#], F#</span></span>      |
| <span data-ttu-id="1b7f5-177">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="1b7f5-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="1b7f5-178">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="1b7f5-178">[C#], F#</span></span>      |
| <span data-ttu-id="1b7f5-179">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="1b7f5-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="1b7f5-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="1b7f5-180">[C#]</span></span>          |
| <span data-ttu-id="1b7f5-181">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1b7f5-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="1b7f5-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="1b7f5-182">[C#]</span></span>          |
| <span data-ttu-id="1b7f5-183">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1b7f5-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="1b7f5-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="1b7f5-184">[C#]</span></span>          |
| <span data-ttu-id="1b7f5-185">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1b7f5-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="1b7f5-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="1b7f5-186">[C#]</span></span>          |
| <span data-ttu-id="1b7f5-187">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="1b7f5-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="1b7f5-188">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="1b7f5-188">[C#], F#</span></span>      |
| <span data-ttu-id="1b7f5-189">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="1b7f5-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="1b7f5-190">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="1b7f5-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="1b7f5-191">Web 配置</span><span class="sxs-lookup"><span data-stu-id="1b7f5-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="1b7f5-192">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="1b7f5-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="1b7f5-193">Razor 页</span><span class="sxs-lookup"><span data-stu-id="1b7f5-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="1b7f5-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="1b7f5-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="1b7f5-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="1b7f5-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1b7f5-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1b7f5-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="1b7f5-197">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-197">The command contains a default list of templates.</span></span> <span data-ttu-id="1b7f5-198">使用 `dotnet new -all` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="1b7f5-199">下表列出了随 .NET Core SDK 1.x 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="1b7f5-200">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="1b7f5-201">模板描述</span><span class="sxs-lookup"><span data-stu-id="1b7f5-201">Template description</span></span>  | <span data-ttu-id="1b7f5-202">模板名称</span><span class="sxs-lookup"><span data-stu-id="1b7f5-202">Template name</span></span> | <span data-ttu-id="1b7f5-203">语言</span><span class="sxs-lookup"><span data-stu-id="1b7f5-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="1b7f5-204">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="1b7f5-204">Console application</span></span>  | `console`     | <span data-ttu-id="1b7f5-205">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="1b7f5-205">[C#], F#</span></span>  |
| <span data-ttu-id="1b7f5-206">类库</span><span class="sxs-lookup"><span data-stu-id="1b7f5-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="1b7f5-207">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="1b7f5-207">[C#], F#</span></span>  |
| <span data-ttu-id="1b7f5-208">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="1b7f5-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="1b7f5-209">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="1b7f5-209">[C#], F#</span></span>  |
| <span data-ttu-id="1b7f5-210">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="1b7f5-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="1b7f5-211">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="1b7f5-211">[C#], F#</span></span>  |
| <span data-ttu-id="1b7f5-212">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="1b7f5-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="1b7f5-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="1b7f5-213">[C#]</span></span>      |
| <span data-ttu-id="1b7f5-214">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="1b7f5-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="1b7f5-215">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="1b7f5-215">[C#], F#</span></span>  |
| <span data-ttu-id="1b7f5-216">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="1b7f5-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="1b7f5-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="1b7f5-217">[C#]</span></span>      |
| <span data-ttu-id="1b7f5-218">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="1b7f5-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="1b7f5-219">Web 配置</span><span class="sxs-lookup"><span data-stu-id="1b7f5-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="1b7f5-220">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="1b7f5-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="1b7f5-221">选项</span><span class="sxs-lookup"><span data-stu-id="1b7f5-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="1b7f5-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1b7f5-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="1b7f5-223">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="1b7f5-224">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="1b7f5-225">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-225">Prints out help for the command.</span></span> <span data-ttu-id="1b7f5-226">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="1b7f5-227">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="1b7f5-228">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="1b7f5-229">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="1b7f5-230">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="1b7f5-231">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="1b7f5-232">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="1b7f5-233">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="1b7f5-234">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="1b7f5-235">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-235">The language of the template to create.</span></span> <span data-ttu-id="1b7f5-236">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="1b7f5-237">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-237">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="1b7f5-238">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-238">The name for the created output.</span></span> <span data-ttu-id="1b7f5-239">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-239">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="1b7f5-240">指定在安装期间要使用的 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-240">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="1b7f5-241">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-241">Location to place the generated output.</span></span> <span data-ttu-id="1b7f5-242">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-242">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="1b7f5-243">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-243">Filters templates based on available types.</span></span> <span data-ttu-id="1b7f5-244">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-244">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="1b7f5-245">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-245">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="1b7f5-246">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-246">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="1b7f5-247">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-247">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="1b7f5-248">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-248">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="1b7f5-249">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="1b7f5-249">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="1b7f5-250">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-250">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="1b7f5-251">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-251">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="1b7f5-252">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-252">Prints out help for the command.</span></span> <span data-ttu-id="1b7f5-253">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-253">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="1b7f5-254">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-254">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="1b7f5-255">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-255">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="1b7f5-256">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-256">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="1b7f5-257">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-257">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="1b7f5-258">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-258">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="1b7f5-259">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-259">Lists templates containing the specified name.</span></span> <span data-ttu-id="1b7f5-260">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-260">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="1b7f5-261">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-261">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="1b7f5-262">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-262">The language of the template to create.</span></span> <span data-ttu-id="1b7f5-263">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-263">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="1b7f5-264">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-264">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="1b7f5-265">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-265">The name for the created output.</span></span> <span data-ttu-id="1b7f5-266">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-266">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="1b7f5-267">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-267">Location to place the generated output.</span></span> <span data-ttu-id="1b7f5-268">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-268">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="1b7f5-269">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-269">Filters templates based on available types.</span></span> <span data-ttu-id="1b7f5-270">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-270">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="1b7f5-271">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-271">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="1b7f5-272">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-272">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="1b7f5-273">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-273">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="1b7f5-274">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-274">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1b7f5-275">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1b7f5-275">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="1b7f5-276">单独在 `dotnet new` 命令的上下文中运行时，显示特定类型的项目的所有模板。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-276">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="1b7f5-277">在特定模板（如 `dotnet new web -all`）的上下文中运行时，`-all` 解释为一个强制创建标记。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-277">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="1b7f5-278">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-278">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="1b7f5-279">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-279">Prints out help for the command.</span></span> <span data-ttu-id="1b7f5-280">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-280">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="1b7f5-281">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-281">Lists templates containing the specified name.</span></span> <span data-ttu-id="1b7f5-282">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-282">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="1b7f5-283">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-283">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="1b7f5-284">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-284">The language of the template to create.</span></span> <span data-ttu-id="1b7f5-285">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-285">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="1b7f5-286">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-286">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="1b7f5-287">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-287">The name for the created output.</span></span> <span data-ttu-id="1b7f5-288">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-288">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="1b7f5-289">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-289">Location to place the generated output.</span></span> <span data-ttu-id="1b7f5-290">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-290">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="1b7f5-291">模板选项</span><span class="sxs-lookup"><span data-stu-id="1b7f5-291">Template options</span></span>

<span data-ttu-id="1b7f5-292">每个项目模板都可能有附加选项。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-292">Each project template may have additional options available.</span></span> <span data-ttu-id="1b7f5-293">核心模板有以下附加选项：</span><span class="sxs-lookup"><span data-stu-id="1b7f5-293">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="1b7f5-294">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1b7f5-294">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="1b7f5-295">console、angular、react、reactredux、razorclasslib</span><span class="sxs-lookup"><span data-stu-id="1b7f5-295">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="1b7f5-296">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-296">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="1b7f5-297">**classlib**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-297">**classlib**</span></span>

<span data-ttu-id="1b7f5-298">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-298">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1b7f5-299">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-299">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="1b7f5-300">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-300">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="1b7f5-301">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-301">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="1b7f5-302">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-302">**mstest, xunit**</span></span>

<span data-ttu-id="1b7f5-303">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-303">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="1b7f5-304">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-304">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="1b7f5-305">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-305">**globaljson**</span></span>

<span data-ttu-id="1b7f5-306">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-306">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="1b7f5-307">**web**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-307">**web**</span></span>

<span data-ttu-id="1b7f5-308">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-308">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="1b7f5-309">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-309">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="1b7f5-310">**webapi**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-310">**webapi**</span></span>

<span data-ttu-id="1b7f5-311">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-311">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="1b7f5-312">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="1b7f5-312">The possible values are:</span></span>

- <span data-ttu-id="1b7f5-313">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-313">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="1b7f5-314">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-314">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="1b7f5-315">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-315">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="1b7f5-316">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-316">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="1b7f5-317">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-317">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="1b7f5-318">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-318">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="1b7f5-319">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-319">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="1b7f5-320">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-320">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="1b7f5-321">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-321">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="1b7f5-322">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-322">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="1b7f5-323">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-323">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1b7f5-324">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-324">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="1b7f5-325">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-325">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="1b7f5-326">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-326">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="1b7f5-327">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-327">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="1b7f5-328">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-328">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="1b7f5-329">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-329">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1b7f5-330">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-330">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="1b7f5-331">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-331">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="1b7f5-332">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-332">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1b7f5-333">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-333">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="1b7f5-334">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-334">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="1b7f5-335">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-335">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="1b7f5-336">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-336">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="1b7f5-337">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-337">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="1b7f5-338">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-338">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="1b7f5-339">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-339">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="1b7f5-340">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-340">**mvc, razor**</span></span>

<span data-ttu-id="1b7f5-341">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-341">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="1b7f5-342">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="1b7f5-342">The possible values are:</span></span>

- <span data-ttu-id="1b7f5-343">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-343">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="1b7f5-344">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-344">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="1b7f5-345">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-345">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="1b7f5-346">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-346">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="1b7f5-347">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-347">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="1b7f5-348">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-348">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="1b7f5-349">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-349">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="1b7f5-350">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-350">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="1b7f5-351">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-351">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="1b7f5-352">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-352">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="1b7f5-353">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-353">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="1b7f5-354">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-354">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="1b7f5-355">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-355">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="1b7f5-356">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-356">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="1b7f5-357">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-357">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="1b7f5-358">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-358">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="1b7f5-359">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-359">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="1b7f5-360">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-360">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="1b7f5-361">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-361">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="1b7f5-362">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-362">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="1b7f5-363">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-363">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="1b7f5-364">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-364">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="1b7f5-365">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-365">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1b7f5-366">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-366">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="1b7f5-367">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-367">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="1b7f5-368">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-368">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1b7f5-369">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-369">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="1b7f5-370">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-370">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="1b7f5-371">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-371">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1b7f5-372">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-372">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="1b7f5-373">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-373">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="1b7f5-374">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-374">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="1b7f5-375">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-375">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="1b7f5-376">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-376">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="1b7f5-377">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-377">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="1b7f5-378">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-378">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="1b7f5-379">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-379">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="1b7f5-380">**page**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-380">**page**</span></span>

<span data-ttu-id="1b7f5-381">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-381">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="1b7f5-382">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-382">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="1b7f5-383">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-383">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="1b7f5-384">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-384">**viewimports**</span></span>

<span data-ttu-id="1b7f5-385">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-385">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="1b7f5-386">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-386">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="1b7f5-387">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="1b7f5-387">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="1b7f5-388">**console、angular、react、reactredux**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-388">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="1b7f5-389">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-389">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="1b7f5-390">**classlib**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-390">**classlib**</span></span>

<span data-ttu-id="1b7f5-391">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-391">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1b7f5-392">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-392">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="1b7f5-393">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-393">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="1b7f5-394">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-394">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="1b7f5-395">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-395">**mstest, xunit**</span></span>

<span data-ttu-id="1b7f5-396">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-396">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="1b7f5-397">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-397">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="1b7f5-398">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-398">**globaljson**</span></span>

<span data-ttu-id="1b7f5-399">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-399">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="1b7f5-400">**web**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-400">**web**</span></span>

<span data-ttu-id="1b7f5-401">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-401">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="1b7f5-402">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-402">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="1b7f5-403">**webapi**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-403">**webapi**</span></span>

<span data-ttu-id="1b7f5-404">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-404">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="1b7f5-405">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="1b7f5-405">The possible values are:</span></span>

- <span data-ttu-id="1b7f5-406">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-406">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="1b7f5-407">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="1b7f5-408">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="1b7f5-409">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-409">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="1b7f5-410">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-410">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="1b7f5-411">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-411">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="1b7f5-412">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-412">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="1b7f5-413">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-413">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="1b7f5-414">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-414">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="1b7f5-415">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-415">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="1b7f5-416">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-416">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1b7f5-417">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-417">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="1b7f5-418">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-418">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="1b7f5-419">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-419">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="1b7f5-420">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-420">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="1b7f5-421">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-421">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="1b7f5-422">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-422">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1b7f5-423">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-423">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="1b7f5-424">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-424">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="1b7f5-425">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-425">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1b7f5-426">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-426">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="1b7f5-427">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-427">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="1b7f5-428">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-428">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="1b7f5-429">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-429">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="1b7f5-430">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-430">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="1b7f5-431">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-431">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="1b7f5-432">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-432">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="1b7f5-433">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-433">**mvc, razor**</span></span>

<span data-ttu-id="1b7f5-434">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-434">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="1b7f5-435">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="1b7f5-435">The possible values are:</span></span>

- <span data-ttu-id="1b7f5-436">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-436">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="1b7f5-437">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-437">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="1b7f5-438">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-438">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="1b7f5-439">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-439">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="1b7f5-440">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-440">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="1b7f5-441">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-441">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="1b7f5-442">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-442">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="1b7f5-443">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-443">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="1b7f5-444">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-444">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="1b7f5-445">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-445">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="1b7f5-446">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-446">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="1b7f5-447">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-447">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="1b7f5-448">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-448">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="1b7f5-449">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-449">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="1b7f5-450">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-450">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="1b7f5-451">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-451">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="1b7f5-452">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-452">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="1b7f5-453">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-453">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="1b7f5-454">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-454">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="1b7f5-455">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-455">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="1b7f5-456">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-456">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="1b7f5-457">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-457">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="1b7f5-458">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-458">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1b7f5-459">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-459">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="1b7f5-460">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-460">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="1b7f5-461">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-461">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1b7f5-462">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-462">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="1b7f5-463">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-463">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="1b7f5-464">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-464">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1b7f5-465">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-465">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="1b7f5-466">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-466">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="1b7f5-467">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-467">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="1b7f5-468">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-468">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="1b7f5-469">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-469">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="1b7f5-470">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-470">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="1b7f5-471">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-471">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="1b7f5-472">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-472">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="1b7f5-473">**page**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-473">**page**</span></span>

<span data-ttu-id="1b7f5-474">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-474">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="1b7f5-475">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-475">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="1b7f5-476">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-476">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="1b7f5-477">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-477">**viewimports**</span></span>

<span data-ttu-id="1b7f5-478">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-478">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="1b7f5-479">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-479">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1b7f5-480">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1b7f5-480">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="1b7f5-481">**console、xunit、mstest、web、webapi**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-481">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="1b7f5-482">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-482">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1b7f5-483">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-483">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="1b7f5-484">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-484">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="1b7f5-485">**classlib**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-485">**classlib**</span></span>

<span data-ttu-id="1b7f5-486">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-486">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1b7f5-487">值：`netcoreapp1.0`、`netcoreapp1.1` 或 `netstandard1.0` 到 `netstandard1.6`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-487">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="1b7f5-488">默认值为 `netstandard1.4`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-488">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="1b7f5-489">**mvc**</span><span class="sxs-lookup"><span data-stu-id="1b7f5-489">**mvc**</span></span>

<span data-ttu-id="1b7f5-490">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-490">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1b7f5-491">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-491">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="1b7f5-492">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-492">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="1b7f5-493">`-au|--auth` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-493">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="1b7f5-494">值：`None` 或 `Individual`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-494">Values: `None` or `Individual`.</span></span> <span data-ttu-id="1b7f5-495">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-495">The default value is `None`.</span></span>

<span data-ttu-id="1b7f5-496">`-uld|--use-local-db` - 指定是否使用 LocalDB，而不是 SQLite。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-496">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="1b7f5-497">值：`true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-497">Values: `true` or `false`.</span></span> <span data-ttu-id="1b7f5-498">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="1b7f5-498">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="1b7f5-499">示例</span><span class="sxs-lookup"><span data-stu-id="1b7f5-499">Examples</span></span>

<span data-ttu-id="1b7f5-500">在当前目录中创建 F# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="1b7f5-500">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="1b7f5-501">在指定目录中创建 .NET Standard 类库项目（仅适用于 .NET Core SDK 2.0 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="1b7f5-501">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="1b7f5-502">在当前目录中新建定目标到 .NET Core 2.0 且没有设置身份验证的 ASP.NET Core C# MVC 应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="1b7f5-502">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="1b7f5-503">新建定目标到 .NET Core 2.0 的 xUnit 应用程序：</span><span class="sxs-lookup"><span data-stu-id="1b7f5-503">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="1b7f5-504">列出适用于 MVC 的所有模板：</span><span class="sxs-lookup"><span data-stu-id="1b7f5-504">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="1b7f5-505">安装适用于 ASP.NET Core 的单页应用程序模板 2.0 版（命令选项仅可用于 .NET Core SDK 1.1 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="1b7f5-505">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="1b7f5-506">在当前目录中创建 global.json，将 SDK 版本设为 2.0.0（仅适用于 .NET Core SDK 2.0 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="1b7f5-506">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="1b7f5-507">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b7f5-507">See also</span></span>

[<span data-ttu-id="1b7f5-508">dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="1b7f5-508">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="1b7f5-509">创建 dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="1b7f5-509">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="1b7f5-510">dotnet/dotnet-template-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="1b7f5-510">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="1b7f5-511">dotnet new 可用模板</span><span class="sxs-lookup"><span data-stu-id="1b7f5-511">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)