---
title: dotnet new 命令
description: dotnet new 命令可根据指定模板新建 .NET Core 项目。
ms.date: 10/24/2018
ms.openlocfilehash: 3a10aaa93af57e7beb86771e7d3b00b06fca14b2
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169675"
---
# <a name="dotnet-new"></a><span data-ttu-id="c5b51-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c5b51-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c5b51-104">name</span><span class="sxs-lookup"><span data-stu-id="c5b51-104">Name</span></span>

<span data-ttu-id="c5b51-105">`dotnet new` - 根据指定的模板，创建新的项目、配置文件或解决方案。</span><span class="sxs-lookup"><span data-stu-id="c5b51-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c5b51-106">摘要</span><span class="sxs-lookup"><span data-stu-id="c5b51-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c5b51-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c5b51-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c5b51-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c5b51-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c5b51-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c5b51-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="c5b51-110">说明</span><span class="sxs-lookup"><span data-stu-id="c5b51-110">Description</span></span>

<span data-ttu-id="c5b51-111">`dotnet new` 命令为初始化有效的 .NET Core 项目提供了便捷方法。</span><span class="sxs-lookup"><span data-stu-id="c5b51-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="c5b51-112">命令调用[模板引擎](https://github.com/dotnet/templating)，以根据指定的模板和选项在磁盘上创建项目。</span><span class="sxs-lookup"><span data-stu-id="c5b51-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="c5b51-113">自变量</span><span class="sxs-lookup"><span data-stu-id="c5b51-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="c5b51-114">调用命令时要实例化的模板。</span><span class="sxs-lookup"><span data-stu-id="c5b51-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="c5b51-115">每个模板可能具有可传递的特定选项。</span><span class="sxs-lookup"><span data-stu-id="c5b51-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="c5b51-116">有关详细信息，请参阅[模板选项](#template-options)。</span><span class="sxs-lookup"><span data-stu-id="c5b51-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c5b51-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c5b51-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="c5b51-118">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="c5b51-118">The command contains a default list of templates.</span></span> <span data-ttu-id="c5b51-119">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="c5b51-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="c5b51-120">下表列出了随 .NET Core SDK 2.1.300 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="c5b51-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="c5b51-121">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="c5b51-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="c5b51-122">模板描述</span><span class="sxs-lookup"><span data-stu-id="c5b51-122">Template description</span></span>                          | <span data-ttu-id="c5b51-123">模板名称</span><span class="sxs-lookup"><span data-stu-id="c5b51-123">Template name</span></span>    | <span data-ttu-id="c5b51-124">语言</span><span class="sxs-lookup"><span data-stu-id="c5b51-124">Languages</span></span>     |
|----------------------------------------------|------------------|---------------|
| <span data-ttu-id="c5b51-125">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="c5b51-125">Console application</span></span>                          | `console`        | <span data-ttu-id="c5b51-126">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="c5b51-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c5b51-127">类库</span><span class="sxs-lookup"><span data-stu-id="c5b51-127">Class library</span></span>                                | `classlib`       | <span data-ttu-id="c5b51-128">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="c5b51-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c5b51-129">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="c5b51-129">Unit test project</span></span>                            | `mstest`         | <span data-ttu-id="c5b51-130">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="c5b51-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c5b51-131">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="c5b51-131">xUnit test project</span></span>                           | `xunit`          | <span data-ttu-id="c5b51-132">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="c5b51-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c5b51-133">NUnit 试项目</span><span class="sxs-lookup"><span data-stu-id="c5b51-133">NUnit test project</span></span>                           | `nunit`          | <span data-ttu-id="c5b51-134">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="c5b51-134">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c5b51-135">Razor 页</span><span class="sxs-lookup"><span data-stu-id="c5b51-135">Razor page</span></span>                                   | `page`           | <span data-ttu-id="c5b51-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5b51-136">[C#]</span></span>          |
| <span data-ttu-id="c5b51-137">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="c5b51-137">MVC ViewImports</span></span>                              | `viewimports`    | <span data-ttu-id="c5b51-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5b51-138">[C#]</span></span>          |
| <span data-ttu-id="c5b51-139">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="c5b51-139">MVC ViewStart</span></span>                                | `viewstart`      | <span data-ttu-id="c5b51-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5b51-140">[C#]</span></span>          |
| <span data-ttu-id="c5b51-141">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="c5b51-141">ASP.NET Core empty</span></span>                           | `web`            | <span data-ttu-id="c5b51-142">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c5b51-142">[C#], F#</span></span>      |
| <span data-ttu-id="c5b51-143">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="c5b51-143">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`            | <span data-ttu-id="c5b51-144">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c5b51-144">[C#], F#</span></span>      |
| <span data-ttu-id="c5b51-145">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="c5b51-145">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="c5b51-146">`razor`， `webapp`</span><span class="sxs-lookup"><span data-stu-id="c5b51-146">`razor`, `webapp`</span></span>| <span data-ttu-id="c5b51-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5b51-147">[C#]</span></span>          |
| <span data-ttu-id="c5b51-148">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c5b51-148">ASP.NET Core with Angular</span></span>                    | `angular`        | <span data-ttu-id="c5b51-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5b51-149">[C#]</span></span>          |
| <span data-ttu-id="c5b51-150">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c5b51-150">ASP.NET Core with React.js</span></span>                   | `react`          | <span data-ttu-id="c5b51-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5b51-151">[C#]</span></span>          |
| <span data-ttu-id="c5b51-152">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c5b51-152">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`     | <span data-ttu-id="c5b51-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5b51-153">[C#]</span></span>          |
| <span data-ttu-id="c5b51-154">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="c5b51-154">ASP.NET Core Web API</span></span>                         | `webapi`         | <span data-ttu-id="c5b51-155">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c5b51-155">[C#], F#</span></span>      |
| <span data-ttu-id="c5b51-156">Razor 类库</span><span class="sxs-lookup"><span data-stu-id="c5b51-156">Razor class library</span></span>                          | `razorclasslib`  | <span data-ttu-id="c5b51-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5b51-157">[C#]</span></span>          |
| <span data-ttu-id="c5b51-158">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="c5b51-158">global.json file</span></span>                             | `globaljson`     |               |
| <span data-ttu-id="c5b51-159">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="c5b51-159">NuGet config</span></span>                                 | `nugetconfig`    |               |
| <span data-ttu-id="c5b51-160">Web 配置</span><span class="sxs-lookup"><span data-stu-id="c5b51-160">Web config</span></span>                                   | `webconfig`      |               |
| <span data-ttu-id="c5b51-161">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="c5b51-161">Solution file</span></span>                                | `sln`            |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c5b51-162">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c5b51-162">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="c5b51-163">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="c5b51-163">The command contains a default list of templates.</span></span> <span data-ttu-id="c5b51-164">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="c5b51-164">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="c5b51-165">下表列出了随 .NET Core SDK 2.0 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="c5b51-165">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="c5b51-166">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="c5b51-166">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="c5b51-167">模板描述</span><span class="sxs-lookup"><span data-stu-id="c5b51-167">Template description</span></span>                          | <span data-ttu-id="c5b51-168">模板名称</span><span class="sxs-lookup"><span data-stu-id="c5b51-168">Template name</span></span> | <span data-ttu-id="c5b51-169">语言</span><span class="sxs-lookup"><span data-stu-id="c5b51-169">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="c5b51-170">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="c5b51-170">Console application</span></span>                          | `console`     | <span data-ttu-id="c5b51-171">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="c5b51-171">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c5b51-172">类库</span><span class="sxs-lookup"><span data-stu-id="c5b51-172">Class library</span></span>                                | `classlib`    | <span data-ttu-id="c5b51-173">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="c5b51-173">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c5b51-174">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="c5b51-174">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="c5b51-175">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="c5b51-175">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c5b51-176">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="c5b51-176">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="c5b51-177">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="c5b51-177">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c5b51-178">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="c5b51-178">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="c5b51-179">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c5b51-179">[C#], F#</span></span>      |
| <span data-ttu-id="c5b51-180">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="c5b51-180">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="c5b51-181">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c5b51-181">[C#], F#</span></span>      |
| <span data-ttu-id="c5b51-182">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="c5b51-182">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="c5b51-183">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5b51-183">[C#]</span></span>          |
| <span data-ttu-id="c5b51-184">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c5b51-184">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="c5b51-185">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5b51-185">[C#]</span></span>          |
| <span data-ttu-id="c5b51-186">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c5b51-186">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="c5b51-187">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5b51-187">[C#]</span></span>          |
| <span data-ttu-id="c5b51-188">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c5b51-188">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="c5b51-189">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5b51-189">[C#]</span></span>          |
| <span data-ttu-id="c5b51-190">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="c5b51-190">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="c5b51-191">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c5b51-191">[C#], F#</span></span>      |
| <span data-ttu-id="c5b51-192">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="c5b51-192">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="c5b51-193">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="c5b51-193">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="c5b51-194">Web 配置</span><span class="sxs-lookup"><span data-stu-id="c5b51-194">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="c5b51-195">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="c5b51-195">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="c5b51-196">Razor 页</span><span class="sxs-lookup"><span data-stu-id="c5b51-196">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="c5b51-197">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="c5b51-197">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="c5b51-198">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="c5b51-198">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c5b51-199">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c5b51-199">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="c5b51-200">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="c5b51-200">The command contains a default list of templates.</span></span> <span data-ttu-id="c5b51-201">使用 `dotnet new -all` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="c5b51-201">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="c5b51-202">下表列出了随 .NET Core SDK 1.x 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="c5b51-202">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="c5b51-203">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="c5b51-203">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="c5b51-204">模板描述</span><span class="sxs-lookup"><span data-stu-id="c5b51-204">Template description</span></span>  | <span data-ttu-id="c5b51-205">模板名称</span><span class="sxs-lookup"><span data-stu-id="c5b51-205">Template name</span></span> | <span data-ttu-id="c5b51-206">语言</span><span class="sxs-lookup"><span data-stu-id="c5b51-206">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="c5b51-207">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="c5b51-207">Console application</span></span>  | `console`     | <span data-ttu-id="c5b51-208">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c5b51-208">[C#], F#</span></span>  |
| <span data-ttu-id="c5b51-209">类库</span><span class="sxs-lookup"><span data-stu-id="c5b51-209">Class library</span></span>        | `classlib`    | <span data-ttu-id="c5b51-210">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c5b51-210">[C#], F#</span></span>  |
| <span data-ttu-id="c5b51-211">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="c5b51-211">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="c5b51-212">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c5b51-212">[C#], F#</span></span>  |
| <span data-ttu-id="c5b51-213">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="c5b51-213">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="c5b51-214">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c5b51-214">[C#], F#</span></span>  |
| <span data-ttu-id="c5b51-215">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="c5b51-215">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="c5b51-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5b51-216">[C#]</span></span>      |
| <span data-ttu-id="c5b51-217">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="c5b51-217">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="c5b51-218">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="c5b51-218">[C#], F#</span></span>  |
| <span data-ttu-id="c5b51-219">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="c5b51-219">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="c5b51-220">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5b51-220">[C#]</span></span>      |
| <span data-ttu-id="c5b51-221">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="c5b51-221">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="c5b51-222">Web 配置</span><span class="sxs-lookup"><span data-stu-id="c5b51-222">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="c5b51-223">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="c5b51-223">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="c5b51-224">选项</span><span class="sxs-lookup"><span data-stu-id="c5b51-224">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c5b51-225">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c5b51-225">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="c5b51-226">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="c5b51-226">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="c5b51-227">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="c5b51-227">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="c5b51-228">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="c5b51-228">Prints out help for the command.</span></span> <span data-ttu-id="c5b51-229">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="c5b51-229">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="c5b51-230">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="c5b51-230">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="c5b51-231">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="c5b51-231">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="c5b51-232">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="c5b51-232">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="c5b51-233">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="c5b51-233">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="c5b51-234">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="c5b51-234">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="c5b51-235">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="c5b51-235">Lists templates containing the specified name.</span></span> <span data-ttu-id="c5b51-236">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="c5b51-236">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="c5b51-237">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="c5b51-237">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="c5b51-238">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="c5b51-238">The language of the template to create.</span></span> <span data-ttu-id="c5b51-239">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="c5b51-239">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c5b51-240">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="c5b51-240">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="c5b51-241">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="c5b51-241">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="c5b51-242">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-242">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="c5b51-243">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="c5b51-243">The name for the created output.</span></span> <span data-ttu-id="c5b51-244">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="c5b51-244">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="c5b51-245">指定在安装期间要使用的 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="c5b51-245">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c5b51-246">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="c5b51-246">Location to place the generated output.</span></span> <span data-ttu-id="c5b51-247">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="c5b51-247">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="c5b51-248">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="c5b51-248">Filters templates based on available types.</span></span> <span data-ttu-id="c5b51-249">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="c5b51-249">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="c5b51-250">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="c5b51-250">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="c5b51-251">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="c5b51-251">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="c5b51-252">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="c5b51-252">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="c5b51-253">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="c5b51-253">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c5b51-254">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c5b51-254">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="c5b51-255">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="c5b51-255">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="c5b51-256">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="c5b51-256">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="c5b51-257">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="c5b51-257">Prints out help for the command.</span></span> <span data-ttu-id="c5b51-258">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="c5b51-258">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="c5b51-259">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="c5b51-259">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="c5b51-260">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="c5b51-260">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="c5b51-261">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="c5b51-261">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="c5b51-262">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="c5b51-262">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="c5b51-263">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="c5b51-263">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="c5b51-264">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="c5b51-264">Lists templates containing the specified name.</span></span> <span data-ttu-id="c5b51-265">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="c5b51-265">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="c5b51-266">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="c5b51-266">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="c5b51-267">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="c5b51-267">The language of the template to create.</span></span> <span data-ttu-id="c5b51-268">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="c5b51-268">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c5b51-269">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="c5b51-269">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="c5b51-270">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="c5b51-270">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="c5b51-271">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-271">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="c5b51-272">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="c5b51-272">The name for the created output.</span></span> <span data-ttu-id="c5b51-273">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="c5b51-273">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c5b51-274">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="c5b51-274">Location to place the generated output.</span></span> <span data-ttu-id="c5b51-275">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="c5b51-275">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="c5b51-276">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="c5b51-276">Filters templates based on available types.</span></span> <span data-ttu-id="c5b51-277">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="c5b51-277">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="c5b51-278">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="c5b51-278">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="c5b51-279">若要使用源 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="c5b51-279">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="c5b51-280">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="c5b51-280">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="c5b51-281">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="c5b51-281">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="c5b51-282">如果无法确定卸载模板所需的 `PATH` 或 `NUGET_ID` 参数，则在没有参数的情况下运行 `dotnet new --uninstall` 将列出所有已安装的模板以及卸载它们所需的参数。</span><span class="sxs-lookup"><span data-stu-id="c5b51-282">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c5b51-283">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c5b51-283">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="c5b51-284">单独在 `dotnet new` 命令的上下文中运行时，显示特定类型的项目的所有模板。</span><span class="sxs-lookup"><span data-stu-id="c5b51-284">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="c5b51-285">在特定模板（如 `dotnet new web -all`）的上下文中运行时，`-all` 解释为一个强制创建标记。</span><span class="sxs-lookup"><span data-stu-id="c5b51-285">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="c5b51-286">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="c5b51-286">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="c5b51-287">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="c5b51-287">Prints out help for the command.</span></span> <span data-ttu-id="c5b51-288">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="c5b51-288">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="c5b51-289">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="c5b51-289">Lists templates containing the specified name.</span></span> <span data-ttu-id="c5b51-290">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="c5b51-290">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="c5b51-291">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="c5b51-291">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="c5b51-292">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="c5b51-292">The language of the template to create.</span></span> <span data-ttu-id="c5b51-293">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="c5b51-293">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c5b51-294">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="c5b51-294">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="c5b51-295">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="c5b51-295">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="c5b51-296">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-296">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="c5b51-297">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="c5b51-297">The name for the created output.</span></span> <span data-ttu-id="c5b51-298">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="c5b51-298">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c5b51-299">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="c5b51-299">Location to place the generated output.</span></span> <span data-ttu-id="c5b51-300">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="c5b51-300">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="c5b51-301">模板选项</span><span class="sxs-lookup"><span data-stu-id="c5b51-301">Template options</span></span>

<span data-ttu-id="c5b51-302">每个项目模板都可能有附加选项。</span><span class="sxs-lookup"><span data-stu-id="c5b51-302">Each project template may have additional options available.</span></span> <span data-ttu-id="c5b51-303">核心模板有以下附加选项：</span><span class="sxs-lookup"><span data-stu-id="c5b51-303">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c5b51-304">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c5b51-304">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="c5b51-305">console、angular、react、reactredux、razorclasslib</span><span class="sxs-lookup"><span data-stu-id="c5b51-305">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="c5b51-306">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c5b51-306">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c5b51-307">**classlib**</span><span class="sxs-lookup"><span data-stu-id="c5b51-307">**classlib**</span></span>

<span data-ttu-id="c5b51-308">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="c5b51-308">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c5b51-309">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="c5b51-309">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="c5b51-310">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-310">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="c5b51-311">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c5b51-311">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c5b51-312">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="c5b51-312">**mstest, xunit**</span></span>

<span data-ttu-id="c5b51-313">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="c5b51-313">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="c5b51-314">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c5b51-314">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c5b51-315">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="c5b51-315">**globaljson**</span></span>

<span data-ttu-id="c5b51-316">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="c5b51-316">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="c5b51-317">**web**</span><span class="sxs-lookup"><span data-stu-id="c5b51-317">**web**</span></span>

<span data-ttu-id="c5b51-318">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="c5b51-318">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="c5b51-319">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c5b51-319">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c5b51-320">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="c5b51-320">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="c5b51-321">此选项仅适用于未使用 `IndividualAuth` 或 `OrganizationalAuth` 的情况。</span><span class="sxs-lookup"><span data-stu-id="c5b51-321">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="c5b51-322">**webapi**</span><span class="sxs-lookup"><span data-stu-id="c5b51-322">**webapi**</span></span>

<span data-ttu-id="c5b51-323">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="c5b51-323">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c5b51-324">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="c5b51-324">The possible values are:</span></span>

- <span data-ttu-id="c5b51-325">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="c5b51-325">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c5b51-326">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-326">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c5b51-327">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-327">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c5b51-328">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-328">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c5b51-329">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="c5b51-329">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c5b51-330">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-330">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5b51-331">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-331">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="c5b51-332">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="c5b51-332">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c5b51-333">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-333">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c5b51-334">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="c5b51-334">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c5b51-335">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-335">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c5b51-336">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-336">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c5b51-337">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="c5b51-337">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c5b51-338">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-338">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="c5b51-339">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-339">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c5b51-340">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="c5b51-340">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c5b51-341">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-341">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5b51-342">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-342">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c5b51-343">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="c5b51-343">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c5b51-344">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-344">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c5b51-345">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-345">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c5b51-346">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="c5b51-346">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c5b51-347">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-347">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c5b51-348">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="c5b51-348">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="c5b51-349">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="c5b51-349">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c5b51-350">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-350">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c5b51-351">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c5b51-351">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c5b51-352">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="c5b51-352">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="c5b51-353">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="c5b51-353">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="c5b51-354">此选项仅适用于未使用 `Individual`、`IndividualB2C``SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="c5b51-354">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="c5b51-355">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="c5b51-355">**mvc, razor**</span></span>

<span data-ttu-id="c5b51-356">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="c5b51-356">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c5b51-357">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="c5b51-357">The possible values are:</span></span>

- <span data-ttu-id="c5b51-358">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="c5b51-358">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c5b51-359">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-359">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="c5b51-360">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-360">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c5b51-361">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-361">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c5b51-362">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-362">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="c5b51-363">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-363">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c5b51-364">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="c5b51-364">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c5b51-365">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-365">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5b51-366">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-366">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="c5b51-367">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="c5b51-367">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c5b51-368">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c5b51-369">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="c5b51-369">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="c5b51-370">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-370">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c5b51-371">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="c5b51-371">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="c5b51-372">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-372">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c5b51-373">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="c5b51-373">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c5b51-374">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-374">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="c5b51-375">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-375">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c5b51-376">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="c5b51-376">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c5b51-377">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-377">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="c5b51-378">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-378">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c5b51-379">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="c5b51-379">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c5b51-380">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-380">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5b51-381">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-381">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c5b51-382">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="c5b51-382">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c5b51-383">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-383">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c5b51-384">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-384">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c5b51-385">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="c5b51-385">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="c5b51-386">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-386">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5b51-387">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-387">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="c5b51-388">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="c5b51-388">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c5b51-389">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-389">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c5b51-390">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="c5b51-390">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="c5b51-391">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="c5b51-391">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="c5b51-392">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="c5b51-392">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c5b51-393">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-393">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c5b51-394">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c5b51-394">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c5b51-395">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="c5b51-395">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="c5b51-396">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="c5b51-396">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="c5b51-397">此选项仅适用于未使用 `Individual`、`IndividualB2C``SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="c5b51-397">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="c5b51-398">**page**</span><span class="sxs-lookup"><span data-stu-id="c5b51-398">**page**</span></span>

<span data-ttu-id="c5b51-399">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="c5b51-399">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c5b51-400">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-400">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="c5b51-401">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="c5b51-401">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="c5b51-402">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="c5b51-402">**viewimports**</span></span>

<span data-ttu-id="c5b51-403">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="c5b51-403">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c5b51-404">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-404">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c5b51-405">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c5b51-405">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="c5b51-406">**console、angular、react、reactredux**</span><span class="sxs-lookup"><span data-stu-id="c5b51-406">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="c5b51-407">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c5b51-407">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c5b51-408">**classlib**</span><span class="sxs-lookup"><span data-stu-id="c5b51-408">**classlib**</span></span>

<span data-ttu-id="c5b51-409">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="c5b51-409">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c5b51-410">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="c5b51-410">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="c5b51-411">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-411">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="c5b51-412">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c5b51-412">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c5b51-413">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="c5b51-413">**mstest, xunit**</span></span>

<span data-ttu-id="c5b51-414">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="c5b51-414">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="c5b51-415">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c5b51-415">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c5b51-416">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="c5b51-416">**globaljson**</span></span>

<span data-ttu-id="c5b51-417">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="c5b51-417">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="c5b51-418">**web**</span><span class="sxs-lookup"><span data-stu-id="c5b51-418">**web**</span></span>

<span data-ttu-id="c5b51-419">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="c5b51-419">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c5b51-420">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c5b51-420">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c5b51-421">**webapi**</span><span class="sxs-lookup"><span data-stu-id="c5b51-421">**webapi**</span></span>

<span data-ttu-id="c5b51-422">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="c5b51-422">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c5b51-423">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="c5b51-423">The possible values are:</span></span>

- <span data-ttu-id="c5b51-424">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="c5b51-424">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c5b51-425">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-425">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c5b51-426">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-426">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c5b51-427">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-427">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c5b51-428">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="c5b51-428">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c5b51-429">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-429">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5b51-430">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-430">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="c5b51-431">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="c5b51-431">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c5b51-432">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-432">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c5b51-433">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="c5b51-433">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c5b51-434">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-434">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c5b51-435">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-435">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c5b51-436">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="c5b51-436">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c5b51-437">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-437">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="c5b51-438">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-438">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c5b51-439">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="c5b51-439">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c5b51-440">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-440">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5b51-441">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-441">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c5b51-442">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="c5b51-442">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c5b51-443">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-443">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c5b51-444">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-444">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c5b51-445">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="c5b51-445">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c5b51-446">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-446">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c5b51-447">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="c5b51-447">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c5b51-448">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="c5b51-448">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c5b51-449">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-449">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c5b51-450">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c5b51-450">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c5b51-451">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="c5b51-451">**mvc, razor**</span></span>

<span data-ttu-id="c5b51-452">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="c5b51-452">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c5b51-453">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="c5b51-453">The possible values are:</span></span>

- <span data-ttu-id="c5b51-454">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="c5b51-454">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c5b51-455">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-455">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="c5b51-456">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-456">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c5b51-457">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-457">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c5b51-458">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-458">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="c5b51-459">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-459">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c5b51-460">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="c5b51-460">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c5b51-461">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-461">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5b51-462">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-462">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="c5b51-463">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="c5b51-463">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c5b51-464">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c5b51-465">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="c5b51-465">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="c5b51-466">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-466">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c5b51-467">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="c5b51-467">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="c5b51-468">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-468">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c5b51-469">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="c5b51-469">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c5b51-470">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-470">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="c5b51-471">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-471">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c5b51-472">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="c5b51-472">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c5b51-473">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-473">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="c5b51-474">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-474">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c5b51-475">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="c5b51-475">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c5b51-476">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-476">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5b51-477">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-477">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c5b51-478">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="c5b51-478">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c5b51-479">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-479">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c5b51-480">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-480">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c5b51-481">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="c5b51-481">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="c5b51-482">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b51-482">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5b51-483">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-483">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="c5b51-484">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="c5b51-484">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c5b51-485">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-485">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c5b51-486">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="c5b51-486">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c5b51-487">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="c5b51-487">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="c5b51-488">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="c5b51-488">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c5b51-489">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5b51-489">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c5b51-490">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c5b51-490">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c5b51-491">**page**</span><span class="sxs-lookup"><span data-stu-id="c5b51-491">**page**</span></span>

<span data-ttu-id="c5b51-492">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="c5b51-492">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c5b51-493">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-493">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="c5b51-494">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="c5b51-494">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="c5b51-495">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="c5b51-495">**viewimports**</span></span>

<span data-ttu-id="c5b51-496">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="c5b51-496">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c5b51-497">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-497">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c5b51-498">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c5b51-498">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="c5b51-499">**console、xunit、mstest、web、webapi**</span><span class="sxs-lookup"><span data-stu-id="c5b51-499">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="c5b51-500">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="c5b51-500">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c5b51-501">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-501">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="c5b51-502">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-502">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="c5b51-503">**classlib**</span><span class="sxs-lookup"><span data-stu-id="c5b51-503">**classlib**</span></span>

<span data-ttu-id="c5b51-504">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="c5b51-504">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c5b51-505">值：`netcoreapp1.0`、`netcoreapp1.1` 或 `netstandard1.0` 到 `netstandard1.6`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-505">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="c5b51-506">默认值为 `netstandard1.4`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-506">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="c5b51-507">**mvc**</span><span class="sxs-lookup"><span data-stu-id="c5b51-507">**mvc**</span></span>

<span data-ttu-id="c5b51-508">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="c5b51-508">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c5b51-509">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-509">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="c5b51-510">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-510">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="c5b51-511">`-au|--auth` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="c5b51-511">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="c5b51-512">值：`None` 或 `Individual`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-512">Values: `None` or `Individual`.</span></span> <span data-ttu-id="c5b51-513">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-513">The default value is `None`.</span></span>

<span data-ttu-id="c5b51-514">`-uld|--use-local-db` - 指定是否使用 LocalDB，而不是 SQLite。</span><span class="sxs-lookup"><span data-stu-id="c5b51-514">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="c5b51-515">值：`true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-515">Values: `true` or `false`.</span></span> <span data-ttu-id="c5b51-516">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="c5b51-516">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="c5b51-517">示例</span><span class="sxs-lookup"><span data-stu-id="c5b51-517">Examples</span></span>

<span data-ttu-id="c5b51-518">在当前目录中创建 F# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="c5b51-518">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="c5b51-519">在指定目录中创建 .NET Standard 类库项目（仅适用于 .NET Core SDK 2.0 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="c5b51-519">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="c5b51-520">在当前目录中新建没有设置身份验证的 ASP.NET Core C# MVC 应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="c5b51-520">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="c5b51-521">创建新的 xUnit 应用程序：</span><span class="sxs-lookup"><span data-stu-id="c5b51-521">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="c5b51-522">列出适用于 MVC 的所有模板：</span><span class="sxs-lookup"><span data-stu-id="c5b51-522">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="c5b51-523">安装适用于 ASP.NET Core 的单页应用程序模板 2.0 版（命令选项仅可用于 .NET Core SDK 1.1 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="c5b51-523">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="c5b51-524">在当前目录中创建 global.json，将 SDK 版本设为 2.0.0（仅适用于 .NET Core SDK 2.0 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="c5b51-524">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="c5b51-525">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5b51-525">See also</span></span>

* [<span data-ttu-id="c5b51-526">dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="c5b51-526">Custom templates for dotnet new</span></span>](custom-templates.md)  
* [<span data-ttu-id="c5b51-527">创建 dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="c5b51-527">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="c5b51-528">dotnet/dotnet-template-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="c5b51-528">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* [<span data-ttu-id="c5b51-529">dotnet new 可用模板</span><span class="sxs-lookup"><span data-stu-id="c5b51-529">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
