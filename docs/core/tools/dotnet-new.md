---
title: dotnet new 命令 - .NET Core CLI
description: dotnet new 命令可根据指定模板新建 .NET Core 项目。
author: mairaw
ms.author: mairaw
ms.date: 07/31/2018
ms.openlocfilehash: 396c4ddf09854fa4582226bdb1422f8c929e459b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2018
ms.locfileid: "47208628"
---
# <a name="dotnet-new"></a><span data-ttu-id="b7c08-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="b7c08-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b7c08-104">name</span><span class="sxs-lookup"><span data-stu-id="b7c08-104">Name</span></span>

<span data-ttu-id="b7c08-105">`dotnet new` - 根据指定的模板，创建新的项目、配置文件或解决方案。</span><span class="sxs-lookup"><span data-stu-id="b7c08-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b7c08-106">摘要</span><span class="sxs-lookup"><span data-stu-id="b7c08-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b7c08-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b7c08-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b7c08-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b7c08-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b7c08-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b7c08-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="b7c08-110">描述</span><span class="sxs-lookup"><span data-stu-id="b7c08-110">Description</span></span>

<span data-ttu-id="b7c08-111">`dotnet new` 命令为初始化有效的 .NET Core 项目提供了便捷方法。</span><span class="sxs-lookup"><span data-stu-id="b7c08-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="b7c08-112">命令调用[模板引擎](https://github.com/dotnet/templating)，以根据指定的模板和选项在磁盘上创建项目。</span><span class="sxs-lookup"><span data-stu-id="b7c08-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="b7c08-113">自变量</span><span class="sxs-lookup"><span data-stu-id="b7c08-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="b7c08-114">调用命令时要实例化的模板。</span><span class="sxs-lookup"><span data-stu-id="b7c08-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="b7c08-115">每个模板可能具有可传递的特定选项。</span><span class="sxs-lookup"><span data-stu-id="b7c08-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="b7c08-116">有关详细信息，请参阅[模板选项](#template-options)。</span><span class="sxs-lookup"><span data-stu-id="b7c08-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b7c08-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b7c08-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="b7c08-118">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="b7c08-118">The command contains a default list of templates.</span></span> <span data-ttu-id="b7c08-119">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="b7c08-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="b7c08-120">下表列出了随 .NET Core SDK 2.1.300 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="b7c08-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="b7c08-121">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="b7c08-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="b7c08-122">模板描述</span><span class="sxs-lookup"><span data-stu-id="b7c08-122">Template description</span></span>                          | <span data-ttu-id="b7c08-123">模板名称</span><span class="sxs-lookup"><span data-stu-id="b7c08-123">Template name</span></span>   | <span data-ttu-id="b7c08-124">语言</span><span class="sxs-lookup"><span data-stu-id="b7c08-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="b7c08-125">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="b7c08-125">Console application</span></span>                          | `console`       | <span data-ttu-id="b7c08-126">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="b7c08-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b7c08-127">类库</span><span class="sxs-lookup"><span data-stu-id="b7c08-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="b7c08-128">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="b7c08-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b7c08-129">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="b7c08-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="b7c08-130">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="b7c08-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b7c08-131">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="b7c08-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="b7c08-132">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="b7c08-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b7c08-133">Razor 页</span><span class="sxs-lookup"><span data-stu-id="b7c08-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="b7c08-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7c08-134">[C#]</span></span>          |
| <span data-ttu-id="b7c08-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="b7c08-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="b7c08-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7c08-136">[C#]</span></span>          |
| <span data-ttu-id="b7c08-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="b7c08-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="b7c08-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7c08-138">[C#]</span></span>          |
| <span data-ttu-id="b7c08-139">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="b7c08-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="b7c08-140">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="b7c08-140">[C#], F#</span></span>      |
| <span data-ttu-id="b7c08-141">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="b7c08-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="b7c08-142">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="b7c08-142">[C#], F#</span></span>      |
| <span data-ttu-id="b7c08-143">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="b7c08-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="b7c08-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7c08-144">[C#]</span></span>          |
| <span data-ttu-id="b7c08-145">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7c08-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="b7c08-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7c08-146">[C#]</span></span>          |
| <span data-ttu-id="b7c08-147">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7c08-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="b7c08-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7c08-148">[C#]</span></span>          |
| <span data-ttu-id="b7c08-149">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7c08-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="b7c08-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7c08-150">[C#]</span></span>          |
| <span data-ttu-id="b7c08-151">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="b7c08-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="b7c08-152">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="b7c08-152">[C#], F#</span></span>      |
| <span data-ttu-id="b7c08-153">Razor 类库</span><span class="sxs-lookup"><span data-stu-id="b7c08-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="b7c08-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7c08-154">[C#]</span></span>          |
| <span data-ttu-id="b7c08-155">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="b7c08-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="b7c08-156">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="b7c08-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="b7c08-157">Web 配置</span><span class="sxs-lookup"><span data-stu-id="b7c08-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="b7c08-158">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="b7c08-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b7c08-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b7c08-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="b7c08-160">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="b7c08-160">The command contains a default list of templates.</span></span> <span data-ttu-id="b7c08-161">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="b7c08-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="b7c08-162">下表列出了随 .NET Core SDK 2.0 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="b7c08-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="b7c08-163">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="b7c08-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="b7c08-164">模板描述</span><span class="sxs-lookup"><span data-stu-id="b7c08-164">Template description</span></span>                          | <span data-ttu-id="b7c08-165">模板名称</span><span class="sxs-lookup"><span data-stu-id="b7c08-165">Template name</span></span> | <span data-ttu-id="b7c08-166">语言</span><span class="sxs-lookup"><span data-stu-id="b7c08-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="b7c08-167">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="b7c08-167">Console application</span></span>                          | `console`     | <span data-ttu-id="b7c08-168">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="b7c08-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b7c08-169">类库</span><span class="sxs-lookup"><span data-stu-id="b7c08-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="b7c08-170">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="b7c08-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b7c08-171">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="b7c08-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="b7c08-172">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="b7c08-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b7c08-173">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="b7c08-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="b7c08-174">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="b7c08-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b7c08-175">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="b7c08-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="b7c08-176">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="b7c08-176">[C#], F#</span></span>      |
| <span data-ttu-id="b7c08-177">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="b7c08-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="b7c08-178">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="b7c08-178">[C#], F#</span></span>      |
| <span data-ttu-id="b7c08-179">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="b7c08-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="b7c08-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7c08-180">[C#]</span></span>          |
| <span data-ttu-id="b7c08-181">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7c08-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="b7c08-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7c08-182">[C#]</span></span>          |
| <span data-ttu-id="b7c08-183">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7c08-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="b7c08-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7c08-184">[C#]</span></span>          |
| <span data-ttu-id="b7c08-185">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7c08-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="b7c08-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7c08-186">[C#]</span></span>          |
| <span data-ttu-id="b7c08-187">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="b7c08-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="b7c08-188">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="b7c08-188">[C#], F#</span></span>      |
| <span data-ttu-id="b7c08-189">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="b7c08-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="b7c08-190">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="b7c08-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="b7c08-191">Web 配置</span><span class="sxs-lookup"><span data-stu-id="b7c08-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="b7c08-192">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="b7c08-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="b7c08-193">Razor 页</span><span class="sxs-lookup"><span data-stu-id="b7c08-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="b7c08-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="b7c08-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="b7c08-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="b7c08-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b7c08-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b7c08-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="b7c08-197">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="b7c08-197">The command contains a default list of templates.</span></span> <span data-ttu-id="b7c08-198">使用 `dotnet new -all` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="b7c08-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="b7c08-199">下表列出了随 .NET Core SDK 1.x 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="b7c08-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="b7c08-200">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="b7c08-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="b7c08-201">模板描述</span><span class="sxs-lookup"><span data-stu-id="b7c08-201">Template description</span></span>  | <span data-ttu-id="b7c08-202">模板名称</span><span class="sxs-lookup"><span data-stu-id="b7c08-202">Template name</span></span> | <span data-ttu-id="b7c08-203">语言</span><span class="sxs-lookup"><span data-stu-id="b7c08-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="b7c08-204">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="b7c08-204">Console application</span></span>  | `console`     | <span data-ttu-id="b7c08-205">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="b7c08-205">[C#], F#</span></span>  |
| <span data-ttu-id="b7c08-206">类库</span><span class="sxs-lookup"><span data-stu-id="b7c08-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="b7c08-207">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="b7c08-207">[C#], F#</span></span>  |
| <span data-ttu-id="b7c08-208">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="b7c08-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="b7c08-209">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="b7c08-209">[C#], F#</span></span>  |
| <span data-ttu-id="b7c08-210">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="b7c08-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="b7c08-211">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="b7c08-211">[C#], F#</span></span>  |
| <span data-ttu-id="b7c08-212">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="b7c08-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="b7c08-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7c08-213">[C#]</span></span>      |
| <span data-ttu-id="b7c08-214">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="b7c08-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="b7c08-215">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="b7c08-215">[C#], F#</span></span>  |
| <span data-ttu-id="b7c08-216">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="b7c08-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="b7c08-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7c08-217">[C#]</span></span>      |
| <span data-ttu-id="b7c08-218">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="b7c08-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="b7c08-219">Web 配置</span><span class="sxs-lookup"><span data-stu-id="b7c08-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="b7c08-220">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="b7c08-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="b7c08-221">选项</span><span class="sxs-lookup"><span data-stu-id="b7c08-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b7c08-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b7c08-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="b7c08-223">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="b7c08-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="b7c08-224">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="b7c08-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="b7c08-225">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="b7c08-225">Prints out help for the command.</span></span> <span data-ttu-id="b7c08-226">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="b7c08-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="b7c08-227">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="b7c08-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="b7c08-228">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="b7c08-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="b7c08-229">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="b7c08-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="b7c08-230">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="b7c08-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="b7c08-231">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="b7c08-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="b7c08-232">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="b7c08-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="b7c08-233">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="b7c08-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="b7c08-234">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="b7c08-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="b7c08-235">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="b7c08-235">The language of the template to create.</span></span> <span data-ttu-id="b7c08-236">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="b7c08-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="b7c08-237">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="b7c08-237">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="b7c08-238">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="b7c08-238">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="b7c08-239">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-239">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="b7c08-240">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="b7c08-240">The name for the created output.</span></span> <span data-ttu-id="b7c08-241">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="b7c08-241">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="b7c08-242">指定在安装期间要使用的 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="b7c08-242">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b7c08-243">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="b7c08-243">Location to place the generated output.</span></span> <span data-ttu-id="b7c08-244">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="b7c08-244">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="b7c08-245">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="b7c08-245">Filters templates based on available types.</span></span> <span data-ttu-id="b7c08-246">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="b7c08-246">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="b7c08-247">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="b7c08-247">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="b7c08-248">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="b7c08-248">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="b7c08-249">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="b7c08-249">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="b7c08-250">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="b7c08-250">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b7c08-251">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b7c08-251">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="b7c08-252">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="b7c08-252">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="b7c08-253">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="b7c08-253">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="b7c08-254">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="b7c08-254">Prints out help for the command.</span></span> <span data-ttu-id="b7c08-255">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="b7c08-255">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="b7c08-256">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="b7c08-256">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="b7c08-257">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="b7c08-257">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="b7c08-258">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="b7c08-258">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="b7c08-259">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="b7c08-259">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="b7c08-260">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="b7c08-260">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="b7c08-261">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="b7c08-261">Lists templates containing the specified name.</span></span> <span data-ttu-id="b7c08-262">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="b7c08-262">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="b7c08-263">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="b7c08-263">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="b7c08-264">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="b7c08-264">The language of the template to create.</span></span> <span data-ttu-id="b7c08-265">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="b7c08-265">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="b7c08-266">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="b7c08-266">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="b7c08-267">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="b7c08-267">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="b7c08-268">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-268">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="b7c08-269">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="b7c08-269">The name for the created output.</span></span> <span data-ttu-id="b7c08-270">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="b7c08-270">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b7c08-271">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="b7c08-271">Location to place the generated output.</span></span> <span data-ttu-id="b7c08-272">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="b7c08-272">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="b7c08-273">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="b7c08-273">Filters templates based on available types.</span></span> <span data-ttu-id="b7c08-274">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="b7c08-274">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="b7c08-275">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="b7c08-275">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="b7c08-276">若要使用源 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="b7c08-276">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="b7c08-277">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="b7c08-277">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="b7c08-278">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="b7c08-278">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="b7c08-279">如果无法确定卸载模板所需的 `PATH` 或 `NUGET_ID` 参数，则在没有参数的情况下运行 `dotnet new --uninstall` 将列出所有已安装的模板以及卸载它们所需的参数。</span><span class="sxs-lookup"><span data-stu-id="b7c08-279">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b7c08-280">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b7c08-280">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="b7c08-281">单独在 `dotnet new` 命令的上下文中运行时，显示特定类型的项目的所有模板。</span><span class="sxs-lookup"><span data-stu-id="b7c08-281">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="b7c08-282">在特定模板（如 `dotnet new web -all`）的上下文中运行时，`-all` 解释为一个强制创建标记。</span><span class="sxs-lookup"><span data-stu-id="b7c08-282">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="b7c08-283">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="b7c08-283">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="b7c08-284">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="b7c08-284">Prints out help for the command.</span></span> <span data-ttu-id="b7c08-285">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="b7c08-285">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="b7c08-286">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="b7c08-286">Lists templates containing the specified name.</span></span> <span data-ttu-id="b7c08-287">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="b7c08-287">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="b7c08-288">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="b7c08-288">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="b7c08-289">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="b7c08-289">The language of the template to create.</span></span> <span data-ttu-id="b7c08-290">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="b7c08-290">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="b7c08-291">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="b7c08-291">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="b7c08-292">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="b7c08-292">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="b7c08-293">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-293">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="b7c08-294">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="b7c08-294">The name for the created output.</span></span> <span data-ttu-id="b7c08-295">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="b7c08-295">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b7c08-296">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="b7c08-296">Location to place the generated output.</span></span> <span data-ttu-id="b7c08-297">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="b7c08-297">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="b7c08-298">模板选项</span><span class="sxs-lookup"><span data-stu-id="b7c08-298">Template options</span></span>

<span data-ttu-id="b7c08-299">每个项目模板都可能有附加选项。</span><span class="sxs-lookup"><span data-stu-id="b7c08-299">Each project template may have additional options available.</span></span> <span data-ttu-id="b7c08-300">核心模板有以下附加选项：</span><span class="sxs-lookup"><span data-stu-id="b7c08-300">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b7c08-301">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b7c08-301">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="b7c08-302">console、angular、react、reactredux、razorclasslib</span><span class="sxs-lookup"><span data-stu-id="b7c08-302">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="b7c08-303">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="b7c08-303">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7c08-304">**classlib**</span><span class="sxs-lookup"><span data-stu-id="b7c08-304">**classlib**</span></span>

<span data-ttu-id="b7c08-305">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="b7c08-305">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b7c08-306">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="b7c08-306">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="b7c08-307">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-307">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="b7c08-308">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="b7c08-308">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7c08-309">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="b7c08-309">**mstest, xunit**</span></span>

<span data-ttu-id="b7c08-310">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="b7c08-310">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="b7c08-311">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="b7c08-311">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7c08-312">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="b7c08-312">**globaljson**</span></span>

<span data-ttu-id="b7c08-313">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="b7c08-313">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="b7c08-314">**web**</span><span class="sxs-lookup"><span data-stu-id="b7c08-314">**web**</span></span>

<span data-ttu-id="b7c08-315">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="b7c08-315">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="b7c08-316">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="b7c08-316">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7c08-317">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="b7c08-317">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="b7c08-318">此选项仅适用于未使用 `IndividualAuth` 或 `OrganizationalAuth` 的情况。</span><span class="sxs-lookup"><span data-stu-id="b7c08-318">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="b7c08-319">**webapi**</span><span class="sxs-lookup"><span data-stu-id="b7c08-319">**webapi**</span></span>

<span data-ttu-id="b7c08-320">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="b7c08-320">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b7c08-321">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="b7c08-321">The possible values are:</span></span>

- <span data-ttu-id="b7c08-322">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="b7c08-322">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b7c08-323">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-323">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b7c08-324">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-324">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b7c08-325">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-325">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b7c08-326">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="b7c08-326">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b7c08-327">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-327">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7c08-328">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-328">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b7c08-329">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="b7c08-329">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b7c08-330">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-330">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7c08-331">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="b7c08-331">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b7c08-332">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-332">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b7c08-333">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-333">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b7c08-334">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="b7c08-334">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b7c08-335">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-335">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="b7c08-336">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-336">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b7c08-337">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="b7c08-337">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b7c08-338">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-338">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7c08-339">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-339">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b7c08-340">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="b7c08-340">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b7c08-341">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-341">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b7c08-342">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-342">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b7c08-343">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="b7c08-343">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b7c08-344">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-344">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b7c08-345">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="b7c08-345">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="b7c08-346">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="b7c08-346">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b7c08-347">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-347">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7c08-348">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="b7c08-348">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7c08-349">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="b7c08-349">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="b7c08-350">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="b7c08-350">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="b7c08-351">此选项仅适用于未使用 `Individual`、`IndividualB2C``SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="b7c08-351">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="b7c08-352">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="b7c08-352">**mvc, razor**</span></span>

<span data-ttu-id="b7c08-353">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="b7c08-353">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b7c08-354">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="b7c08-354">The possible values are:</span></span>

- <span data-ttu-id="b7c08-355">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="b7c08-355">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b7c08-356">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-356">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="b7c08-357">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-357">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b7c08-358">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-358">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b7c08-359">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-359">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="b7c08-360">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-360">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b7c08-361">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="b7c08-361">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b7c08-362">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-362">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7c08-363">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-363">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b7c08-364">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="b7c08-364">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b7c08-365">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-365">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7c08-366">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="b7c08-366">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="b7c08-367">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-367">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7c08-368">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="b7c08-368">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="b7c08-369">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-369">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7c08-370">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="b7c08-370">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b7c08-371">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-371">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="b7c08-372">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-372">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b7c08-373">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="b7c08-373">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b7c08-374">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-374">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="b7c08-375">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-375">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b7c08-376">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="b7c08-376">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b7c08-377">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-377">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7c08-378">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-378">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b7c08-379">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="b7c08-379">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b7c08-380">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-380">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b7c08-381">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-381">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b7c08-382">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="b7c08-382">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="b7c08-383">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-383">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7c08-384">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-384">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="b7c08-385">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="b7c08-385">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b7c08-386">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-386">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b7c08-387">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="b7c08-387">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="b7c08-388">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="b7c08-388">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="b7c08-389">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="b7c08-389">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b7c08-390">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-390">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7c08-391">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="b7c08-391">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7c08-392">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="b7c08-392">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="b7c08-393">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="b7c08-393">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="b7c08-394">此选项仅适用于未使用 `Individual`、`IndividualB2C``SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="b7c08-394">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="b7c08-395">**page**</span><span class="sxs-lookup"><span data-stu-id="b7c08-395">**page**</span></span>

<span data-ttu-id="b7c08-396">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="b7c08-396">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="b7c08-397">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-397">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="b7c08-398">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="b7c08-398">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="b7c08-399">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="b7c08-399">**viewimports**</span></span>

<span data-ttu-id="b7c08-400">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="b7c08-400">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="b7c08-401">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-401">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b7c08-402">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b7c08-402">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="b7c08-403">**console、angular、react、reactredux**</span><span class="sxs-lookup"><span data-stu-id="b7c08-403">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="b7c08-404">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="b7c08-404">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7c08-405">**classlib**</span><span class="sxs-lookup"><span data-stu-id="b7c08-405">**classlib**</span></span>

<span data-ttu-id="b7c08-406">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="b7c08-406">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b7c08-407">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="b7c08-407">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="b7c08-408">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-408">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="b7c08-409">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="b7c08-409">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7c08-410">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="b7c08-410">**mstest, xunit**</span></span>

<span data-ttu-id="b7c08-411">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="b7c08-411">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="b7c08-412">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="b7c08-412">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7c08-413">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="b7c08-413">**globaljson**</span></span>

<span data-ttu-id="b7c08-414">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="b7c08-414">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="b7c08-415">**web**</span><span class="sxs-lookup"><span data-stu-id="b7c08-415">**web**</span></span>

<span data-ttu-id="b7c08-416">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="b7c08-416">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="b7c08-417">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="b7c08-417">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7c08-418">**webapi**</span><span class="sxs-lookup"><span data-stu-id="b7c08-418">**webapi**</span></span>

<span data-ttu-id="b7c08-419">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="b7c08-419">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b7c08-420">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="b7c08-420">The possible values are:</span></span>

- <span data-ttu-id="b7c08-421">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="b7c08-421">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b7c08-422">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-422">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b7c08-423">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-423">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b7c08-424">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-424">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b7c08-425">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="b7c08-425">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b7c08-426">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-426">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7c08-427">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-427">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b7c08-428">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="b7c08-428">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b7c08-429">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-429">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7c08-430">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="b7c08-430">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b7c08-431">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b7c08-432">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-432">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b7c08-433">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="b7c08-433">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b7c08-434">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-434">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="b7c08-435">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-435">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b7c08-436">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="b7c08-436">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b7c08-437">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-437">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7c08-438">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-438">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b7c08-439">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="b7c08-439">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b7c08-440">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-440">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b7c08-441">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-441">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b7c08-442">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="b7c08-442">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b7c08-443">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-443">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b7c08-444">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="b7c08-444">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="b7c08-445">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="b7c08-445">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b7c08-446">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-446">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7c08-447">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="b7c08-447">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7c08-448">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="b7c08-448">**mvc, razor**</span></span>

<span data-ttu-id="b7c08-449">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="b7c08-449">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b7c08-450">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="b7c08-450">The possible values are:</span></span>

- <span data-ttu-id="b7c08-451">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="b7c08-451">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b7c08-452">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-452">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="b7c08-453">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-453">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b7c08-454">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-454">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b7c08-455">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-455">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="b7c08-456">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-456">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b7c08-457">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="b7c08-457">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b7c08-458">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-458">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7c08-459">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-459">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b7c08-460">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="b7c08-460">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b7c08-461">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-461">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7c08-462">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="b7c08-462">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="b7c08-463">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-463">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7c08-464">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="b7c08-464">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="b7c08-465">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-465">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7c08-466">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="b7c08-466">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b7c08-467">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-467">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="b7c08-468">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-468">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b7c08-469">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="b7c08-469">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b7c08-470">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-470">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="b7c08-471">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-471">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b7c08-472">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="b7c08-472">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b7c08-473">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-473">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7c08-474">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-474">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b7c08-475">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="b7c08-475">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b7c08-476">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-476">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b7c08-477">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-477">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b7c08-478">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="b7c08-478">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="b7c08-479">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="b7c08-479">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7c08-480">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-480">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="b7c08-481">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="b7c08-481">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b7c08-482">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-482">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b7c08-483">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="b7c08-483">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="b7c08-484">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="b7c08-484">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="b7c08-485">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="b7c08-485">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b7c08-486">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7c08-486">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7c08-487">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="b7c08-487">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7c08-488">**page**</span><span class="sxs-lookup"><span data-stu-id="b7c08-488">**page**</span></span>

<span data-ttu-id="b7c08-489">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="b7c08-489">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="b7c08-490">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-490">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="b7c08-491">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="b7c08-491">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="b7c08-492">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="b7c08-492">**viewimports**</span></span>

<span data-ttu-id="b7c08-493">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="b7c08-493">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="b7c08-494">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-494">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b7c08-495">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b7c08-495">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="b7c08-496">**console、xunit、mstest、web、webapi**</span><span class="sxs-lookup"><span data-stu-id="b7c08-496">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="b7c08-497">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="b7c08-497">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b7c08-498">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-498">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="b7c08-499">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-499">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="b7c08-500">**classlib**</span><span class="sxs-lookup"><span data-stu-id="b7c08-500">**classlib**</span></span>

<span data-ttu-id="b7c08-501">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="b7c08-501">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b7c08-502">值：`netcoreapp1.0`、`netcoreapp1.1` 或 `netstandard1.0` 到 `netstandard1.6`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-502">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="b7c08-503">默认值为 `netstandard1.4`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-503">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="b7c08-504">**mvc**</span><span class="sxs-lookup"><span data-stu-id="b7c08-504">**mvc**</span></span>

<span data-ttu-id="b7c08-505">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="b7c08-505">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b7c08-506">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-506">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="b7c08-507">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-507">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="b7c08-508">`-au|--auth` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="b7c08-508">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="b7c08-509">值：`None` 或 `Individual`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-509">Values: `None` or `Individual`.</span></span> <span data-ttu-id="b7c08-510">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-510">The default value is `None`.</span></span>

<span data-ttu-id="b7c08-511">`-uld|--use-local-db` - 指定是否使用 LocalDB，而不是 SQLite。</span><span class="sxs-lookup"><span data-stu-id="b7c08-511">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="b7c08-512">值：`true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-512">Values: `true` or `false`.</span></span> <span data-ttu-id="b7c08-513">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="b7c08-513">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="b7c08-514">示例</span><span class="sxs-lookup"><span data-stu-id="b7c08-514">Examples</span></span>

<span data-ttu-id="b7c08-515">在当前目录中创建 F# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="b7c08-515">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="b7c08-516">在指定目录中创建 .NET Standard 类库项目（仅适用于 .NET Core SDK 2.0 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="b7c08-516">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="b7c08-517">在当前目录中新建没有设置身份验证的 ASP.NET Core C# MVC 应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="b7c08-517">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="b7c08-518">创建新的 xUnit 应用程序：</span><span class="sxs-lookup"><span data-stu-id="b7c08-518">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="b7c08-519">列出适用于 MVC 的所有模板：</span><span class="sxs-lookup"><span data-stu-id="b7c08-519">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="b7c08-520">安装适用于 ASP.NET Core 的单页应用程序模板 2.0 版（命令选项仅可用于 .NET Core SDK 1.1 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="b7c08-520">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="b7c08-521">在当前目录中创建 global.json，将 SDK 版本设为 2.0.0（仅适用于 .NET Core SDK 2.0 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="b7c08-521">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="b7c08-522">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7c08-522">See also</span></span>

* [<span data-ttu-id="b7c08-523">dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="b7c08-523">Custom templates for dotnet new</span></span>](custom-templates.md)  
* [<span data-ttu-id="b7c08-524">创建 dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="b7c08-524">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="b7c08-525">dotnet/dotnet-template-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="b7c08-525">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* [<span data-ttu-id="b7c08-526">dotnet new 可用模板</span><span class="sxs-lookup"><span data-stu-id="b7c08-526">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
