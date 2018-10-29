---
title: dotnet new 命令 - .NET Core CLI
description: dotnet new 命令可根据指定模板新建 .NET Core 项目。
author: mairaw
ms.author: mairaw
ms.date: 10/24/2018
ms.openlocfilehash: 56d76f1dd54097f9cf20129d74057235290c273c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188192"
---
# <a name="dotnet-new"></a><span data-ttu-id="0aa97-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="0aa97-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="0aa97-104">name</span><span class="sxs-lookup"><span data-stu-id="0aa97-104">Name</span></span>

<span data-ttu-id="0aa97-105">`dotnet new` - 根据指定的模板，创建新的项目、配置文件或解决方案。</span><span class="sxs-lookup"><span data-stu-id="0aa97-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0aa97-106">摘要</span><span class="sxs-lookup"><span data-stu-id="0aa97-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="0aa97-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0aa97-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="0aa97-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="0aa97-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0aa97-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0aa97-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="0aa97-110">描述</span><span class="sxs-lookup"><span data-stu-id="0aa97-110">Description</span></span>

<span data-ttu-id="0aa97-111">`dotnet new` 命令为初始化有效的 .NET Core 项目提供了便捷方法。</span><span class="sxs-lookup"><span data-stu-id="0aa97-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="0aa97-112">命令调用[模板引擎](https://github.com/dotnet/templating)，以根据指定的模板和选项在磁盘上创建项目。</span><span class="sxs-lookup"><span data-stu-id="0aa97-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="0aa97-113">自变量</span><span class="sxs-lookup"><span data-stu-id="0aa97-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="0aa97-114">调用命令时要实例化的模板。</span><span class="sxs-lookup"><span data-stu-id="0aa97-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="0aa97-115">每个模板可能具有可传递的特定选项。</span><span class="sxs-lookup"><span data-stu-id="0aa97-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="0aa97-116">有关详细信息，请参阅[模板选项](#template-options)。</span><span class="sxs-lookup"><span data-stu-id="0aa97-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="0aa97-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0aa97-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="0aa97-118">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="0aa97-118">The command contains a default list of templates.</span></span> <span data-ttu-id="0aa97-119">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="0aa97-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="0aa97-120">下表列出了随 .NET Core SDK 2.1.300 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="0aa97-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="0aa97-121">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="0aa97-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="0aa97-122">模板描述</span><span class="sxs-lookup"><span data-stu-id="0aa97-122">Template description</span></span>                          | <span data-ttu-id="0aa97-123">模板名称</span><span class="sxs-lookup"><span data-stu-id="0aa97-123">Template name</span></span>    | <span data-ttu-id="0aa97-124">语言</span><span class="sxs-lookup"><span data-stu-id="0aa97-124">Languages</span></span>     |
|----------------------------------------------|------------------|---------------|
| <span data-ttu-id="0aa97-125">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="0aa97-125">Console application</span></span>                          | `console`        | <span data-ttu-id="0aa97-126">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="0aa97-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0aa97-127">类库</span><span class="sxs-lookup"><span data-stu-id="0aa97-127">Class library</span></span>                                | `classlib`       | <span data-ttu-id="0aa97-128">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="0aa97-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0aa97-129">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="0aa97-129">Unit test project</span></span>                            | `mstest`         | <span data-ttu-id="0aa97-130">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="0aa97-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0aa97-131">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="0aa97-131">xUnit test project</span></span>                           | `xunit`          | <span data-ttu-id="0aa97-132">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="0aa97-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0aa97-133">Razor 页</span><span class="sxs-lookup"><span data-stu-id="0aa97-133">Razor page</span></span>                                   | `page`           | <span data-ttu-id="0aa97-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="0aa97-134">[C#]</span></span>          |
| <span data-ttu-id="0aa97-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="0aa97-135">MVC ViewImports</span></span>                              | `viewimports`    | <span data-ttu-id="0aa97-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="0aa97-136">[C#]</span></span>          |
| <span data-ttu-id="0aa97-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="0aa97-137">MVC ViewStart</span></span>                                | `viewstart`      | <span data-ttu-id="0aa97-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="0aa97-138">[C#]</span></span>          |
| <span data-ttu-id="0aa97-139">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="0aa97-139">ASP.NET Core empty</span></span>                           | `web`            | <span data-ttu-id="0aa97-140">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="0aa97-140">[C#], F#</span></span>      |
| <span data-ttu-id="0aa97-141">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="0aa97-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`            | <span data-ttu-id="0aa97-142">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="0aa97-142">[C#], F#</span></span>      |
| <span data-ttu-id="0aa97-143">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="0aa97-143">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="0aa97-144">`razor`， `webapp`</span><span class="sxs-lookup"><span data-stu-id="0aa97-144">`razor`, `webapp`</span></span>| <span data-ttu-id="0aa97-145">[C#]</span><span class="sxs-lookup"><span data-stu-id="0aa97-145">[C#]</span></span>          |
| <span data-ttu-id="0aa97-146">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0aa97-146">ASP.NET Core with Angular</span></span>                    | `angular`        | <span data-ttu-id="0aa97-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="0aa97-147">[C#]</span></span>          |
| <span data-ttu-id="0aa97-148">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0aa97-148">ASP.NET Core with React.js</span></span>                   | `react`          | <span data-ttu-id="0aa97-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="0aa97-149">[C#]</span></span>          |
| <span data-ttu-id="0aa97-150">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0aa97-150">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`     | <span data-ttu-id="0aa97-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="0aa97-151">[C#]</span></span>          |
| <span data-ttu-id="0aa97-152">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="0aa97-152">ASP.NET Core Web API</span></span>                         | `webapi`         | <span data-ttu-id="0aa97-153">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="0aa97-153">[C#], F#</span></span>      |
| <span data-ttu-id="0aa97-154">Razor 类库</span><span class="sxs-lookup"><span data-stu-id="0aa97-154">Razor class library</span></span>                          | `razorclasslib`  | <span data-ttu-id="0aa97-155">[C#]</span><span class="sxs-lookup"><span data-stu-id="0aa97-155">[C#]</span></span>          |
| <span data-ttu-id="0aa97-156">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="0aa97-156">global.json file</span></span>                             | `globaljson`     |               |
| <span data-ttu-id="0aa97-157">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="0aa97-157">NuGet config</span></span>                                 | `nugetconfig`    |               |
| <span data-ttu-id="0aa97-158">Web 配置</span><span class="sxs-lookup"><span data-stu-id="0aa97-158">Web config</span></span>                                   | `webconfig`      |               |
| <span data-ttu-id="0aa97-159">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="0aa97-159">Solution file</span></span>                                | `sln`            |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="0aa97-160">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="0aa97-160">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="0aa97-161">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="0aa97-161">The command contains a default list of templates.</span></span> <span data-ttu-id="0aa97-162">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="0aa97-162">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="0aa97-163">下表列出了随 .NET Core SDK 2.0 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="0aa97-163">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="0aa97-164">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="0aa97-164">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="0aa97-165">模板描述</span><span class="sxs-lookup"><span data-stu-id="0aa97-165">Template description</span></span>                          | <span data-ttu-id="0aa97-166">模板名称</span><span class="sxs-lookup"><span data-stu-id="0aa97-166">Template name</span></span> | <span data-ttu-id="0aa97-167">语言</span><span class="sxs-lookup"><span data-stu-id="0aa97-167">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="0aa97-168">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="0aa97-168">Console application</span></span>                          | `console`     | <span data-ttu-id="0aa97-169">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="0aa97-169">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0aa97-170">类库</span><span class="sxs-lookup"><span data-stu-id="0aa97-170">Class library</span></span>                                | `classlib`    | <span data-ttu-id="0aa97-171">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="0aa97-171">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0aa97-172">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="0aa97-172">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="0aa97-173">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="0aa97-173">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0aa97-174">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="0aa97-174">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="0aa97-175">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="0aa97-175">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0aa97-176">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="0aa97-176">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="0aa97-177">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="0aa97-177">[C#], F#</span></span>      |
| <span data-ttu-id="0aa97-178">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="0aa97-178">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="0aa97-179">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="0aa97-179">[C#], F#</span></span>      |
| <span data-ttu-id="0aa97-180">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="0aa97-180">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="0aa97-181">[C#]</span><span class="sxs-lookup"><span data-stu-id="0aa97-181">[C#]</span></span>          |
| <span data-ttu-id="0aa97-182">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0aa97-182">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="0aa97-183">[C#]</span><span class="sxs-lookup"><span data-stu-id="0aa97-183">[C#]</span></span>          |
| <span data-ttu-id="0aa97-184">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0aa97-184">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="0aa97-185">[C#]</span><span class="sxs-lookup"><span data-stu-id="0aa97-185">[C#]</span></span>          |
| <span data-ttu-id="0aa97-186">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0aa97-186">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="0aa97-187">[C#]</span><span class="sxs-lookup"><span data-stu-id="0aa97-187">[C#]</span></span>          |
| <span data-ttu-id="0aa97-188">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="0aa97-188">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="0aa97-189">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="0aa97-189">[C#], F#</span></span>      |
| <span data-ttu-id="0aa97-190">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="0aa97-190">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="0aa97-191">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="0aa97-191">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="0aa97-192">Web 配置</span><span class="sxs-lookup"><span data-stu-id="0aa97-192">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="0aa97-193">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="0aa97-193">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="0aa97-194">Razor 页</span><span class="sxs-lookup"><span data-stu-id="0aa97-194">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="0aa97-195">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="0aa97-195">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="0aa97-196">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="0aa97-196">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0aa97-197">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0aa97-197">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="0aa97-198">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="0aa97-198">The command contains a default list of templates.</span></span> <span data-ttu-id="0aa97-199">使用 `dotnet new -all` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="0aa97-199">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="0aa97-200">下表列出了随 .NET Core SDK 1.x 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="0aa97-200">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="0aa97-201">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="0aa97-201">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="0aa97-202">模板描述</span><span class="sxs-lookup"><span data-stu-id="0aa97-202">Template description</span></span>  | <span data-ttu-id="0aa97-203">模板名称</span><span class="sxs-lookup"><span data-stu-id="0aa97-203">Template name</span></span> | <span data-ttu-id="0aa97-204">语言</span><span class="sxs-lookup"><span data-stu-id="0aa97-204">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="0aa97-205">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="0aa97-205">Console application</span></span>  | `console`     | <span data-ttu-id="0aa97-206">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="0aa97-206">[C#], F#</span></span>  |
| <span data-ttu-id="0aa97-207">类库</span><span class="sxs-lookup"><span data-stu-id="0aa97-207">Class library</span></span>        | `classlib`    | <span data-ttu-id="0aa97-208">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="0aa97-208">[C#], F#</span></span>  |
| <span data-ttu-id="0aa97-209">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="0aa97-209">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="0aa97-210">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="0aa97-210">[C#], F#</span></span>  |
| <span data-ttu-id="0aa97-211">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="0aa97-211">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="0aa97-212">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="0aa97-212">[C#], F#</span></span>  |
| <span data-ttu-id="0aa97-213">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="0aa97-213">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="0aa97-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="0aa97-214">[C#]</span></span>      |
| <span data-ttu-id="0aa97-215">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="0aa97-215">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="0aa97-216">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="0aa97-216">[C#], F#</span></span>  |
| <span data-ttu-id="0aa97-217">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="0aa97-217">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="0aa97-218">[C#]</span><span class="sxs-lookup"><span data-stu-id="0aa97-218">[C#]</span></span>      |
| <span data-ttu-id="0aa97-219">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="0aa97-219">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="0aa97-220">Web 配置</span><span class="sxs-lookup"><span data-stu-id="0aa97-220">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="0aa97-221">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="0aa97-221">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="0aa97-222">选项</span><span class="sxs-lookup"><span data-stu-id="0aa97-222">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="0aa97-223">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0aa97-223">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="0aa97-224">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="0aa97-224">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="0aa97-225">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="0aa97-225">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="0aa97-226">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="0aa97-226">Prints out help for the command.</span></span> <span data-ttu-id="0aa97-227">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="0aa97-227">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="0aa97-228">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="0aa97-228">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="0aa97-229">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="0aa97-229">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="0aa97-230">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="0aa97-230">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="0aa97-231">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="0aa97-231">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="0aa97-232">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="0aa97-232">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="0aa97-233">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="0aa97-233">Lists templates containing the specified name.</span></span> <span data-ttu-id="0aa97-234">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="0aa97-234">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="0aa97-235">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="0aa97-235">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="0aa97-236">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="0aa97-236">The language of the template to create.</span></span> <span data-ttu-id="0aa97-237">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="0aa97-237">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="0aa97-238">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="0aa97-238">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="0aa97-239">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="0aa97-239">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="0aa97-240">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-240">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="0aa97-241">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="0aa97-241">The name for the created output.</span></span> <span data-ttu-id="0aa97-242">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="0aa97-242">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="0aa97-243">指定在安装期间要使用的 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="0aa97-243">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="0aa97-244">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="0aa97-244">Location to place the generated output.</span></span> <span data-ttu-id="0aa97-245">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="0aa97-245">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="0aa97-246">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="0aa97-246">Filters templates based on available types.</span></span> <span data-ttu-id="0aa97-247">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="0aa97-247">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="0aa97-248">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="0aa97-248">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="0aa97-249">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="0aa97-249">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="0aa97-250">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="0aa97-250">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="0aa97-251">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="0aa97-251">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="0aa97-252">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="0aa97-252">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="0aa97-253">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="0aa97-253">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="0aa97-254">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="0aa97-254">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="0aa97-255">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="0aa97-255">Prints out help for the command.</span></span> <span data-ttu-id="0aa97-256">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="0aa97-256">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="0aa97-257">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="0aa97-257">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="0aa97-258">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="0aa97-258">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="0aa97-259">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="0aa97-259">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="0aa97-260">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="0aa97-260">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="0aa97-261">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="0aa97-261">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="0aa97-262">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="0aa97-262">Lists templates containing the specified name.</span></span> <span data-ttu-id="0aa97-263">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="0aa97-263">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="0aa97-264">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="0aa97-264">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="0aa97-265">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="0aa97-265">The language of the template to create.</span></span> <span data-ttu-id="0aa97-266">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="0aa97-266">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="0aa97-267">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="0aa97-267">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="0aa97-268">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="0aa97-268">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="0aa97-269">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-269">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="0aa97-270">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="0aa97-270">The name for the created output.</span></span> <span data-ttu-id="0aa97-271">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="0aa97-271">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="0aa97-272">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="0aa97-272">Location to place the generated output.</span></span> <span data-ttu-id="0aa97-273">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="0aa97-273">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="0aa97-274">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="0aa97-274">Filters templates based on available types.</span></span> <span data-ttu-id="0aa97-275">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="0aa97-275">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="0aa97-276">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="0aa97-276">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="0aa97-277">若要使用源 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="0aa97-277">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="0aa97-278">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="0aa97-278">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="0aa97-279">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="0aa97-279">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="0aa97-280">如果无法确定卸载模板所需的 `PATH` 或 `NUGET_ID` 参数，则在没有参数的情况下运行 `dotnet new --uninstall` 将列出所有已安装的模板以及卸载它们所需的参数。</span><span class="sxs-lookup"><span data-stu-id="0aa97-280">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0aa97-281">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0aa97-281">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="0aa97-282">单独在 `dotnet new` 命令的上下文中运行时，显示特定类型的项目的所有模板。</span><span class="sxs-lookup"><span data-stu-id="0aa97-282">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="0aa97-283">在特定模板（如 `dotnet new web -all`）的上下文中运行时，`-all` 解释为一个强制创建标记。</span><span class="sxs-lookup"><span data-stu-id="0aa97-283">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="0aa97-284">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="0aa97-284">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="0aa97-285">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="0aa97-285">Prints out help for the command.</span></span> <span data-ttu-id="0aa97-286">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="0aa97-286">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="0aa97-287">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="0aa97-287">Lists templates containing the specified name.</span></span> <span data-ttu-id="0aa97-288">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="0aa97-288">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="0aa97-289">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="0aa97-289">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="0aa97-290">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="0aa97-290">The language of the template to create.</span></span> <span data-ttu-id="0aa97-291">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="0aa97-291">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="0aa97-292">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="0aa97-292">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="0aa97-293">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="0aa97-293">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="0aa97-294">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-294">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="0aa97-295">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="0aa97-295">The name for the created output.</span></span> <span data-ttu-id="0aa97-296">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="0aa97-296">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="0aa97-297">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="0aa97-297">Location to place the generated output.</span></span> <span data-ttu-id="0aa97-298">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="0aa97-298">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="0aa97-299">模板选项</span><span class="sxs-lookup"><span data-stu-id="0aa97-299">Template options</span></span>

<span data-ttu-id="0aa97-300">每个项目模板都可能有附加选项。</span><span class="sxs-lookup"><span data-stu-id="0aa97-300">Each project template may have additional options available.</span></span> <span data-ttu-id="0aa97-301">核心模板有以下附加选项：</span><span class="sxs-lookup"><span data-stu-id="0aa97-301">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="0aa97-302">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0aa97-302">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="0aa97-303">console、angular、react、reactredux、razorclasslib</span><span class="sxs-lookup"><span data-stu-id="0aa97-303">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="0aa97-304">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="0aa97-304">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0aa97-305">**classlib**</span><span class="sxs-lookup"><span data-stu-id="0aa97-305">**classlib**</span></span>

<span data-ttu-id="0aa97-306">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="0aa97-306">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0aa97-307">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="0aa97-307">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="0aa97-308">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-308">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="0aa97-309">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="0aa97-309">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0aa97-310">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="0aa97-310">**mstest, xunit**</span></span>

<span data-ttu-id="0aa97-311">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="0aa97-311">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="0aa97-312">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="0aa97-312">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0aa97-313">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="0aa97-313">**globaljson**</span></span>

<span data-ttu-id="0aa97-314">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="0aa97-314">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="0aa97-315">**web**</span><span class="sxs-lookup"><span data-stu-id="0aa97-315">**web**</span></span>

<span data-ttu-id="0aa97-316">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="0aa97-316">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="0aa97-317">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="0aa97-317">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0aa97-318">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="0aa97-318">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="0aa97-319">此选项仅适用于未使用 `IndividualAuth` 或 `OrganizationalAuth` 的情况。</span><span class="sxs-lookup"><span data-stu-id="0aa97-319">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="0aa97-320">**webapi**</span><span class="sxs-lookup"><span data-stu-id="0aa97-320">**webapi**</span></span>

<span data-ttu-id="0aa97-321">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="0aa97-321">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="0aa97-322">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="0aa97-322">The possible values are:</span></span>

- <span data-ttu-id="0aa97-323">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="0aa97-323">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="0aa97-324">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-324">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="0aa97-325">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-325">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="0aa97-326">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-326">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="0aa97-327">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="0aa97-327">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="0aa97-328">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-328">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="0aa97-329">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-329">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="0aa97-330">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="0aa97-330">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="0aa97-331">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-331">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0aa97-332">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="0aa97-332">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="0aa97-333">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-333">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0aa97-334">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-334">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="0aa97-335">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="0aa97-335">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="0aa97-336">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-336">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="0aa97-337">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-337">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="0aa97-338">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="0aa97-338">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="0aa97-339">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-339">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0aa97-340">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-340">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="0aa97-341">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="0aa97-341">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="0aa97-342">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-342">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0aa97-343">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-343">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="0aa97-344">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="0aa97-344">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="0aa97-345">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-345">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="0aa97-346">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="0aa97-346">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="0aa97-347">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="0aa97-347">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="0aa97-348">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-348">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0aa97-349">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="0aa97-349">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0aa97-350">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="0aa97-350">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="0aa97-351">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="0aa97-351">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="0aa97-352">此选项仅适用于未使用 `Individual`、`IndividualB2C``SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="0aa97-352">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="0aa97-353">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="0aa97-353">**mvc, razor**</span></span>

<span data-ttu-id="0aa97-354">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="0aa97-354">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="0aa97-355">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="0aa97-355">The possible values are:</span></span>

- <span data-ttu-id="0aa97-356">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="0aa97-356">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="0aa97-357">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-357">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="0aa97-358">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-358">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="0aa97-359">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-359">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="0aa97-360">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-360">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="0aa97-361">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-361">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="0aa97-362">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="0aa97-362">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="0aa97-363">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-363">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="0aa97-364">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-364">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="0aa97-365">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="0aa97-365">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="0aa97-366">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-366">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0aa97-367">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="0aa97-367">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="0aa97-368">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0aa97-369">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="0aa97-369">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="0aa97-370">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-370">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0aa97-371">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="0aa97-371">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="0aa97-372">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-372">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="0aa97-373">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-373">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="0aa97-374">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="0aa97-374">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="0aa97-375">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-375">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="0aa97-376">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-376">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="0aa97-377">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="0aa97-377">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="0aa97-378">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-378">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0aa97-379">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-379">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="0aa97-380">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="0aa97-380">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="0aa97-381">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-381">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0aa97-382">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-382">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="0aa97-383">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="0aa97-383">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="0aa97-384">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-384">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0aa97-385">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-385">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="0aa97-386">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="0aa97-386">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="0aa97-387">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-387">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="0aa97-388">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="0aa97-388">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="0aa97-389">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="0aa97-389">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="0aa97-390">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="0aa97-390">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="0aa97-391">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-391">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0aa97-392">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="0aa97-392">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0aa97-393">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="0aa97-393">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="0aa97-394">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="0aa97-394">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="0aa97-395">此选项仅适用于未使用 `Individual`、`IndividualB2C``SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="0aa97-395">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="0aa97-396">**page**</span><span class="sxs-lookup"><span data-stu-id="0aa97-396">**page**</span></span>

<span data-ttu-id="0aa97-397">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="0aa97-397">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="0aa97-398">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-398">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="0aa97-399">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="0aa97-399">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="0aa97-400">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="0aa97-400">**viewimports**</span></span>

<span data-ttu-id="0aa97-401">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="0aa97-401">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="0aa97-402">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-402">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="0aa97-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="0aa97-403">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="0aa97-404">**console、angular、react、reactredux**</span><span class="sxs-lookup"><span data-stu-id="0aa97-404">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="0aa97-405">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="0aa97-405">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0aa97-406">**classlib**</span><span class="sxs-lookup"><span data-stu-id="0aa97-406">**classlib**</span></span>

<span data-ttu-id="0aa97-407">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="0aa97-407">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0aa97-408">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="0aa97-408">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="0aa97-409">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-409">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="0aa97-410">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="0aa97-410">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0aa97-411">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="0aa97-411">**mstest, xunit**</span></span>

<span data-ttu-id="0aa97-412">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="0aa97-412">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="0aa97-413">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="0aa97-413">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0aa97-414">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="0aa97-414">**globaljson**</span></span>

<span data-ttu-id="0aa97-415">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="0aa97-415">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="0aa97-416">**web**</span><span class="sxs-lookup"><span data-stu-id="0aa97-416">**web**</span></span>

<span data-ttu-id="0aa97-417">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="0aa97-417">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="0aa97-418">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="0aa97-418">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0aa97-419">**webapi**</span><span class="sxs-lookup"><span data-stu-id="0aa97-419">**webapi**</span></span>

<span data-ttu-id="0aa97-420">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="0aa97-420">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="0aa97-421">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="0aa97-421">The possible values are:</span></span>

- <span data-ttu-id="0aa97-422">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="0aa97-422">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="0aa97-423">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-423">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="0aa97-424">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-424">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="0aa97-425">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-425">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="0aa97-426">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="0aa97-426">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="0aa97-427">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-427">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="0aa97-428">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-428">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="0aa97-429">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="0aa97-429">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="0aa97-430">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-430">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0aa97-431">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="0aa97-431">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="0aa97-432">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-432">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0aa97-433">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-433">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="0aa97-434">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="0aa97-434">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="0aa97-435">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-435">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="0aa97-436">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-436">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="0aa97-437">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="0aa97-437">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="0aa97-438">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-438">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0aa97-439">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-439">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="0aa97-440">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="0aa97-440">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="0aa97-441">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-441">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0aa97-442">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-442">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="0aa97-443">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="0aa97-443">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="0aa97-444">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-444">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="0aa97-445">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="0aa97-445">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="0aa97-446">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="0aa97-446">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="0aa97-447">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-447">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0aa97-448">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="0aa97-448">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0aa97-449">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="0aa97-449">**mvc, razor**</span></span>

<span data-ttu-id="0aa97-450">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="0aa97-450">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="0aa97-451">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="0aa97-451">The possible values are:</span></span>

- <span data-ttu-id="0aa97-452">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="0aa97-452">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="0aa97-453">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-453">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="0aa97-454">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-454">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="0aa97-455">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-455">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="0aa97-456">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-456">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="0aa97-457">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-457">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="0aa97-458">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="0aa97-458">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="0aa97-459">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-459">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="0aa97-460">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-460">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="0aa97-461">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="0aa97-461">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="0aa97-462">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-462">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0aa97-463">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="0aa97-463">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="0aa97-464">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0aa97-465">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="0aa97-465">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="0aa97-466">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-466">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0aa97-467">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="0aa97-467">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="0aa97-468">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-468">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="0aa97-469">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-469">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="0aa97-470">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="0aa97-470">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="0aa97-471">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-471">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="0aa97-472">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-472">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="0aa97-473">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="0aa97-473">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="0aa97-474">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-474">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0aa97-475">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-475">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="0aa97-476">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="0aa97-476">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="0aa97-477">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-477">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0aa97-478">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-478">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="0aa97-479">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="0aa97-479">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="0aa97-480">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="0aa97-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0aa97-481">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-481">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="0aa97-482">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="0aa97-482">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="0aa97-483">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-483">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="0aa97-484">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="0aa97-484">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="0aa97-485">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="0aa97-485">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="0aa97-486">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="0aa97-486">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="0aa97-487">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="0aa97-487">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0aa97-488">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="0aa97-488">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0aa97-489">**page**</span><span class="sxs-lookup"><span data-stu-id="0aa97-489">**page**</span></span>

<span data-ttu-id="0aa97-490">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="0aa97-490">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="0aa97-491">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-491">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="0aa97-492">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="0aa97-492">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="0aa97-493">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="0aa97-493">**viewimports**</span></span>

<span data-ttu-id="0aa97-494">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="0aa97-494">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="0aa97-495">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-495">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0aa97-496">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0aa97-496">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="0aa97-497">**console、xunit、mstest、web、webapi**</span><span class="sxs-lookup"><span data-stu-id="0aa97-497">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="0aa97-498">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="0aa97-498">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0aa97-499">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-499">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="0aa97-500">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-500">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="0aa97-501">**classlib**</span><span class="sxs-lookup"><span data-stu-id="0aa97-501">**classlib**</span></span>

<span data-ttu-id="0aa97-502">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="0aa97-502">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0aa97-503">值：`netcoreapp1.0`、`netcoreapp1.1` 或 `netstandard1.0` 到 `netstandard1.6`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-503">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="0aa97-504">默认值为 `netstandard1.4`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-504">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="0aa97-505">**mvc**</span><span class="sxs-lookup"><span data-stu-id="0aa97-505">**mvc**</span></span>

<span data-ttu-id="0aa97-506">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="0aa97-506">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0aa97-507">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-507">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="0aa97-508">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-508">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="0aa97-509">`-au|--auth` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="0aa97-509">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="0aa97-510">值：`None` 或 `Individual`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-510">Values: `None` or `Individual`.</span></span> <span data-ttu-id="0aa97-511">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-511">The default value is `None`.</span></span>

<span data-ttu-id="0aa97-512">`-uld|--use-local-db` - 指定是否使用 LocalDB，而不是 SQLite。</span><span class="sxs-lookup"><span data-stu-id="0aa97-512">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="0aa97-513">值：`true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-513">Values: `true` or `false`.</span></span> <span data-ttu-id="0aa97-514">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="0aa97-514">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="0aa97-515">示例</span><span class="sxs-lookup"><span data-stu-id="0aa97-515">Examples</span></span>

<span data-ttu-id="0aa97-516">在当前目录中创建 F# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="0aa97-516">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="0aa97-517">在指定目录中创建 .NET Standard 类库项目（仅适用于 .NET Core SDK 2.0 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="0aa97-517">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="0aa97-518">在当前目录中新建没有设置身份验证的 ASP.NET Core C# MVC 应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="0aa97-518">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="0aa97-519">创建新的 xUnit 应用程序：</span><span class="sxs-lookup"><span data-stu-id="0aa97-519">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="0aa97-520">列出适用于 MVC 的所有模板：</span><span class="sxs-lookup"><span data-stu-id="0aa97-520">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="0aa97-521">安装适用于 ASP.NET Core 的单页应用程序模板 2.0 版（命令选项仅可用于 .NET Core SDK 1.1 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="0aa97-521">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="0aa97-522">在当前目录中创建 global.json，将 SDK 版本设为 2.0.0（仅适用于 .NET Core SDK 2.0 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="0aa97-522">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="0aa97-523">请参阅</span><span class="sxs-lookup"><span data-stu-id="0aa97-523">See also</span></span>

* [<span data-ttu-id="0aa97-524">dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="0aa97-524">Custom templates for dotnet new</span></span>](custom-templates.md)  
* [<span data-ttu-id="0aa97-525">创建 dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="0aa97-525">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="0aa97-526">dotnet/dotnet-template-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="0aa97-526">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* [<span data-ttu-id="0aa97-527">dotnet new 可用模板</span><span class="sxs-lookup"><span data-stu-id="0aa97-527">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
