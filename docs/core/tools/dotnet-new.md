---
title: dotnet new 命令 - .NET Core CLI
description: dotnet new 命令可根据指定模板新建 .NET Core 项目。
author: mairaw
ms.author: mairaw
ms.date: 07/31/2018
ms.openlocfilehash: 2c82dda2d93225edb360316637e22964135cd5e4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512550"
---
# <a name="dotnet-new"></a><span data-ttu-id="02e29-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="02e29-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="02e29-104">name</span><span class="sxs-lookup"><span data-stu-id="02e29-104">Name</span></span>

<span data-ttu-id="02e29-105">`dotnet new` - 根据指定的模板，创建新的项目、配置文件或解决方案。</span><span class="sxs-lookup"><span data-stu-id="02e29-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="02e29-106">摘要</span><span class="sxs-lookup"><span data-stu-id="02e29-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="02e29-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="02e29-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="02e29-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="02e29-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="02e29-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="02e29-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="02e29-110">描述</span><span class="sxs-lookup"><span data-stu-id="02e29-110">Description</span></span>

<span data-ttu-id="02e29-111">`dotnet new` 命令为初始化有效的 .NET Core 项目提供了便捷方法。</span><span class="sxs-lookup"><span data-stu-id="02e29-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="02e29-112">命令调用[模板引擎](https://github.com/dotnet/templating)，以根据指定的模板和选项在磁盘上创建项目。</span><span class="sxs-lookup"><span data-stu-id="02e29-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="02e29-113">自变量</span><span class="sxs-lookup"><span data-stu-id="02e29-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="02e29-114">调用命令时要实例化的模板。</span><span class="sxs-lookup"><span data-stu-id="02e29-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="02e29-115">每个模板可能具有可传递的特定选项。</span><span class="sxs-lookup"><span data-stu-id="02e29-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="02e29-116">有关详细信息，请参阅[模板选项](#template-options)。</span><span class="sxs-lookup"><span data-stu-id="02e29-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="02e29-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="02e29-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="02e29-118">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="02e29-118">The command contains a default list of templates.</span></span> <span data-ttu-id="02e29-119">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="02e29-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="02e29-120">下表列出了随 .NET Core SDK 2.1.300 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="02e29-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="02e29-121">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="02e29-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="02e29-122">模板描述</span><span class="sxs-lookup"><span data-stu-id="02e29-122">Template description</span></span>                          | <span data-ttu-id="02e29-123">模板名称</span><span class="sxs-lookup"><span data-stu-id="02e29-123">Template name</span></span>   | <span data-ttu-id="02e29-124">语言</span><span class="sxs-lookup"><span data-stu-id="02e29-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="02e29-125">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="02e29-125">Console application</span></span>                          | `console`       | <span data-ttu-id="02e29-126">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="02e29-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="02e29-127">类库</span><span class="sxs-lookup"><span data-stu-id="02e29-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="02e29-128">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="02e29-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="02e29-129">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="02e29-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="02e29-130">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="02e29-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="02e29-131">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="02e29-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="02e29-132">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="02e29-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="02e29-133">Razor 页</span><span class="sxs-lookup"><span data-stu-id="02e29-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="02e29-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="02e29-134">[C#]</span></span>          |
| <span data-ttu-id="02e29-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="02e29-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="02e29-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="02e29-136">[C#]</span></span>          |
| <span data-ttu-id="02e29-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="02e29-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="02e29-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="02e29-138">[C#]</span></span>          |
| <span data-ttu-id="02e29-139">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="02e29-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="02e29-140">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="02e29-140">[C#], F#</span></span>      |
| <span data-ttu-id="02e29-141">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="02e29-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="02e29-142">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="02e29-142">[C#], F#</span></span>      |
| <span data-ttu-id="02e29-143">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="02e29-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="02e29-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="02e29-144">[C#]</span></span>          |
| <span data-ttu-id="02e29-145">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="02e29-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="02e29-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="02e29-146">[C#]</span></span>          |
| <span data-ttu-id="02e29-147">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="02e29-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="02e29-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="02e29-148">[C#]</span></span>          |
| <span data-ttu-id="02e29-149">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="02e29-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="02e29-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="02e29-150">[C#]</span></span>          |
| <span data-ttu-id="02e29-151">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="02e29-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="02e29-152">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="02e29-152">[C#], F#</span></span>      |
| <span data-ttu-id="02e29-153">Razor 类库</span><span class="sxs-lookup"><span data-stu-id="02e29-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="02e29-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="02e29-154">[C#]</span></span>          |
| <span data-ttu-id="02e29-155">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="02e29-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="02e29-156">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="02e29-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="02e29-157">Web 配置</span><span class="sxs-lookup"><span data-stu-id="02e29-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="02e29-158">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="02e29-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="02e29-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="02e29-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="02e29-160">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="02e29-160">The command contains a default list of templates.</span></span> <span data-ttu-id="02e29-161">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="02e29-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="02e29-162">下表列出了随 .NET Core SDK 2.0 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="02e29-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="02e29-163">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="02e29-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="02e29-164">模板描述</span><span class="sxs-lookup"><span data-stu-id="02e29-164">Template description</span></span>                          | <span data-ttu-id="02e29-165">模板名称</span><span class="sxs-lookup"><span data-stu-id="02e29-165">Template name</span></span> | <span data-ttu-id="02e29-166">语言</span><span class="sxs-lookup"><span data-stu-id="02e29-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="02e29-167">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="02e29-167">Console application</span></span>                          | `console`     | <span data-ttu-id="02e29-168">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="02e29-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="02e29-169">类库</span><span class="sxs-lookup"><span data-stu-id="02e29-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="02e29-170">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="02e29-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="02e29-171">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="02e29-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="02e29-172">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="02e29-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="02e29-173">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="02e29-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="02e29-174">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="02e29-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="02e29-175">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="02e29-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="02e29-176">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="02e29-176">[C#], F#</span></span>      |
| <span data-ttu-id="02e29-177">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="02e29-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="02e29-178">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="02e29-178">[C#], F#</span></span>      |
| <span data-ttu-id="02e29-179">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="02e29-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="02e29-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="02e29-180">[C#]</span></span>          |
| <span data-ttu-id="02e29-181">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="02e29-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="02e29-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="02e29-182">[C#]</span></span>          |
| <span data-ttu-id="02e29-183">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="02e29-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="02e29-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="02e29-184">[C#]</span></span>          |
| <span data-ttu-id="02e29-185">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="02e29-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="02e29-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="02e29-186">[C#]</span></span>          |
| <span data-ttu-id="02e29-187">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="02e29-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="02e29-188">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="02e29-188">[C#], F#</span></span>      |
| <span data-ttu-id="02e29-189">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="02e29-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="02e29-190">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="02e29-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="02e29-191">Web 配置</span><span class="sxs-lookup"><span data-stu-id="02e29-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="02e29-192">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="02e29-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="02e29-193">Razor 页</span><span class="sxs-lookup"><span data-stu-id="02e29-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="02e29-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="02e29-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="02e29-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="02e29-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="02e29-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="02e29-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="02e29-197">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="02e29-197">The command contains a default list of templates.</span></span> <span data-ttu-id="02e29-198">使用 `dotnet new -all` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="02e29-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="02e29-199">下表列出了随 .NET Core SDK 1.x 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="02e29-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="02e29-200">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="02e29-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="02e29-201">模板描述</span><span class="sxs-lookup"><span data-stu-id="02e29-201">Template description</span></span>  | <span data-ttu-id="02e29-202">模板名称</span><span class="sxs-lookup"><span data-stu-id="02e29-202">Template name</span></span> | <span data-ttu-id="02e29-203">语言</span><span class="sxs-lookup"><span data-stu-id="02e29-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="02e29-204">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="02e29-204">Console application</span></span>  | `console`     | <span data-ttu-id="02e29-205">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="02e29-205">[C#], F#</span></span>  |
| <span data-ttu-id="02e29-206">类库</span><span class="sxs-lookup"><span data-stu-id="02e29-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="02e29-207">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="02e29-207">[C#], F#</span></span>  |
| <span data-ttu-id="02e29-208">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="02e29-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="02e29-209">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="02e29-209">[C#], F#</span></span>  |
| <span data-ttu-id="02e29-210">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="02e29-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="02e29-211">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="02e29-211">[C#], F#</span></span>  |
| <span data-ttu-id="02e29-212">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="02e29-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="02e29-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="02e29-213">[C#]</span></span>      |
| <span data-ttu-id="02e29-214">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="02e29-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="02e29-215">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="02e29-215">[C#], F#</span></span>  |
| <span data-ttu-id="02e29-216">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="02e29-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="02e29-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="02e29-217">[C#]</span></span>      |
| <span data-ttu-id="02e29-218">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="02e29-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="02e29-219">Web 配置</span><span class="sxs-lookup"><span data-stu-id="02e29-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="02e29-220">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="02e29-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="02e29-221">选项</span><span class="sxs-lookup"><span data-stu-id="02e29-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="02e29-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="02e29-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="02e29-223">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="02e29-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="02e29-224">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="02e29-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="02e29-225">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="02e29-225">Prints out help for the command.</span></span> <span data-ttu-id="02e29-226">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="02e29-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="02e29-227">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="02e29-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="02e29-228">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="02e29-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="02e29-229">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="02e29-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="02e29-230">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="02e29-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="02e29-231">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="02e29-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="02e29-232">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="02e29-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="02e29-233">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="02e29-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="02e29-234">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="02e29-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="02e29-235">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="02e29-235">The language of the template to create.</span></span> <span data-ttu-id="02e29-236">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="02e29-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="02e29-237">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="02e29-237">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="02e29-238">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="02e29-238">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="02e29-239">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="02e29-239">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="02e29-240">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="02e29-240">The name for the created output.</span></span> <span data-ttu-id="02e29-241">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="02e29-241">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="02e29-242">指定在安装期间要使用的 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="02e29-242">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="02e29-243">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="02e29-243">Location to place the generated output.</span></span> <span data-ttu-id="02e29-244">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="02e29-244">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="02e29-245">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="02e29-245">Filters templates based on available types.</span></span> <span data-ttu-id="02e29-246">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="02e29-246">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="02e29-247">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="02e29-247">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="02e29-248">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="02e29-248">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="02e29-249">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="02e29-249">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="02e29-250">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="02e29-250">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="02e29-251">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="02e29-251">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="02e29-252">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="02e29-252">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="02e29-253">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="02e29-253">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="02e29-254">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="02e29-254">Prints out help for the command.</span></span> <span data-ttu-id="02e29-255">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="02e29-255">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="02e29-256">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="02e29-256">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="02e29-257">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="02e29-257">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="02e29-258">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="02e29-258">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="02e29-259">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="02e29-259">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="02e29-260">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="02e29-260">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="02e29-261">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="02e29-261">Lists templates containing the specified name.</span></span> <span data-ttu-id="02e29-262">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="02e29-262">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="02e29-263">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="02e29-263">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="02e29-264">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="02e29-264">The language of the template to create.</span></span> <span data-ttu-id="02e29-265">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="02e29-265">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="02e29-266">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="02e29-266">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="02e29-267">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="02e29-267">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="02e29-268">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="02e29-268">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="02e29-269">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="02e29-269">The name for the created output.</span></span> <span data-ttu-id="02e29-270">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="02e29-270">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="02e29-271">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="02e29-271">Location to place the generated output.</span></span> <span data-ttu-id="02e29-272">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="02e29-272">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="02e29-273">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="02e29-273">Filters templates based on available types.</span></span> <span data-ttu-id="02e29-274">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="02e29-274">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="02e29-275">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="02e29-275">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="02e29-276">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="02e29-276">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="02e29-277">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="02e29-277">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="02e29-278">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="02e29-278">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="02e29-279">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="02e29-279">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="02e29-280">单独在 `dotnet new` 命令的上下文中运行时，显示特定类型的项目的所有模板。</span><span class="sxs-lookup"><span data-stu-id="02e29-280">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="02e29-281">在特定模板（如 `dotnet new web -all`）的上下文中运行时，`-all` 解释为一个强制创建标记。</span><span class="sxs-lookup"><span data-stu-id="02e29-281">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="02e29-282">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="02e29-282">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="02e29-283">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="02e29-283">Prints out help for the command.</span></span> <span data-ttu-id="02e29-284">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="02e29-284">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="02e29-285">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="02e29-285">Lists templates containing the specified name.</span></span> <span data-ttu-id="02e29-286">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="02e29-286">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="02e29-287">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="02e29-287">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="02e29-288">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="02e29-288">The language of the template to create.</span></span> <span data-ttu-id="02e29-289">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="02e29-289">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="02e29-290">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="02e29-290">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="02e29-291">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="02e29-291">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="02e29-292">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="02e29-292">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="02e29-293">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="02e29-293">The name for the created output.</span></span> <span data-ttu-id="02e29-294">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="02e29-294">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="02e29-295">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="02e29-295">Location to place the generated output.</span></span> <span data-ttu-id="02e29-296">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="02e29-296">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="02e29-297">模板选项</span><span class="sxs-lookup"><span data-stu-id="02e29-297">Template options</span></span>

<span data-ttu-id="02e29-298">每个项目模板都可能有附加选项。</span><span class="sxs-lookup"><span data-stu-id="02e29-298">Each project template may have additional options available.</span></span> <span data-ttu-id="02e29-299">核心模板有以下附加选项：</span><span class="sxs-lookup"><span data-stu-id="02e29-299">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="02e29-300">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="02e29-300">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="02e29-301">console、angular、react、reactredux、razorclasslib</span><span class="sxs-lookup"><span data-stu-id="02e29-301">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="02e29-302">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="02e29-302">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="02e29-303">**classlib**</span><span class="sxs-lookup"><span data-stu-id="02e29-303">**classlib**</span></span>

<span data-ttu-id="02e29-304">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="02e29-304">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="02e29-305">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="02e29-305">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="02e29-306">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="02e29-306">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="02e29-307">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="02e29-307">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="02e29-308">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="02e29-308">**mstest, xunit**</span></span>

<span data-ttu-id="02e29-309">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="02e29-309">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="02e29-310">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="02e29-310">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="02e29-311">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="02e29-311">**globaljson**</span></span>

<span data-ttu-id="02e29-312">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="02e29-312">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="02e29-313">**web**</span><span class="sxs-lookup"><span data-stu-id="02e29-313">**web**</span></span>

<span data-ttu-id="02e29-314">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="02e29-314">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="02e29-315">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="02e29-315">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="02e29-316">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="02e29-316">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="02e29-317">此选项仅适用于未使用 `IndividualAuth` 或 `OrganizationalAuth` 的情况。</span><span class="sxs-lookup"><span data-stu-id="02e29-317">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="02e29-318">**webapi**</span><span class="sxs-lookup"><span data-stu-id="02e29-318">**webapi**</span></span>

<span data-ttu-id="02e29-319">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="02e29-319">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="02e29-320">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="02e29-320">The possible values are:</span></span>

- <span data-ttu-id="02e29-321">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="02e29-321">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="02e29-322">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-322">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="02e29-323">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-323">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="02e29-324">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-324">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="02e29-325">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="02e29-325">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="02e29-326">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-326">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="02e29-327">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="02e29-327">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="02e29-328">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="02e29-328">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="02e29-329">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-329">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="02e29-330">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="02e29-330">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="02e29-331">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-331">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="02e29-332">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="02e29-332">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="02e29-333">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="02e29-333">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="02e29-334">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-334">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="02e29-335">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="02e29-335">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="02e29-336">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="02e29-336">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="02e29-337">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-337">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="02e29-338">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="02e29-338">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="02e29-339">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="02e29-339">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="02e29-340">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-340">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="02e29-341">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="02e29-341">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="02e29-342">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="02e29-342">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="02e29-343">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-343">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="02e29-344">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="02e29-344">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="02e29-345">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="02e29-345">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="02e29-346">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-346">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="02e29-347">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="02e29-347">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="02e29-348">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="02e29-348">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="02e29-349">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="02e29-349">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="02e29-350">此选项仅适用于未使用 `Individual`、`IndividualB2C``SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="02e29-350">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="02e29-351">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="02e29-351">**mvc, razor**</span></span>

<span data-ttu-id="02e29-352">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="02e29-352">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="02e29-353">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="02e29-353">The possible values are:</span></span>

- <span data-ttu-id="02e29-354">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="02e29-354">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="02e29-355">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-355">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="02e29-356">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-356">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="02e29-357">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-357">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="02e29-358">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-358">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="02e29-359">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-359">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="02e29-360">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="02e29-360">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="02e29-361">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-361">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="02e29-362">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="02e29-362">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="02e29-363">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="02e29-363">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="02e29-364">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-364">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="02e29-365">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="02e29-365">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="02e29-366">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-366">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="02e29-367">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="02e29-367">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="02e29-368">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="02e29-369">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="02e29-369">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="02e29-370">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-370">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="02e29-371">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="02e29-371">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="02e29-372">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="02e29-372">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="02e29-373">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-373">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="02e29-374">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="02e29-374">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="02e29-375">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="02e29-375">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="02e29-376">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-376">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="02e29-377">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="02e29-377">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="02e29-378">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="02e29-378">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="02e29-379">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-379">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="02e29-380">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="02e29-380">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="02e29-381">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="02e29-381">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="02e29-382">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-382">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="02e29-383">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="02e29-383">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="02e29-384">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="02e29-384">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="02e29-385">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-385">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="02e29-386">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="02e29-386">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="02e29-387">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="02e29-387">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="02e29-388">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="02e29-388">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="02e29-389">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-389">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="02e29-390">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="02e29-390">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="02e29-391">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="02e29-391">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="02e29-392">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="02e29-392">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="02e29-393">此选项仅适用于未使用 `Individual`、`IndividualB2C``SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="02e29-393">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="02e29-394">**page**</span><span class="sxs-lookup"><span data-stu-id="02e29-394">**page**</span></span>

<span data-ttu-id="02e29-395">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="02e29-395">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="02e29-396">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="02e29-396">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="02e29-397">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="02e29-397">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="02e29-398">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="02e29-398">**viewimports**</span></span>

<span data-ttu-id="02e29-399">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="02e29-399">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="02e29-400">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="02e29-400">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="02e29-401">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="02e29-401">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="02e29-402">**console、angular、react、reactredux**</span><span class="sxs-lookup"><span data-stu-id="02e29-402">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="02e29-403">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="02e29-403">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="02e29-404">**classlib**</span><span class="sxs-lookup"><span data-stu-id="02e29-404">**classlib**</span></span>

<span data-ttu-id="02e29-405">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="02e29-405">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="02e29-406">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="02e29-406">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="02e29-407">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="02e29-407">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="02e29-408">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="02e29-408">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="02e29-409">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="02e29-409">**mstest, xunit**</span></span>

<span data-ttu-id="02e29-410">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="02e29-410">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="02e29-411">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="02e29-411">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="02e29-412">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="02e29-412">**globaljson**</span></span>

<span data-ttu-id="02e29-413">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="02e29-413">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="02e29-414">**web**</span><span class="sxs-lookup"><span data-stu-id="02e29-414">**web**</span></span>

<span data-ttu-id="02e29-415">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="02e29-415">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="02e29-416">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="02e29-416">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="02e29-417">**webapi**</span><span class="sxs-lookup"><span data-stu-id="02e29-417">**webapi**</span></span>

<span data-ttu-id="02e29-418">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="02e29-418">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="02e29-419">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="02e29-419">The possible values are:</span></span>

- <span data-ttu-id="02e29-420">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="02e29-420">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="02e29-421">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-421">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="02e29-422">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-422">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="02e29-423">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-423">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="02e29-424">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="02e29-424">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="02e29-425">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-425">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="02e29-426">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="02e29-426">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="02e29-427">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="02e29-427">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="02e29-428">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-428">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="02e29-429">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="02e29-429">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="02e29-430">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="02e29-431">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="02e29-431">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="02e29-432">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="02e29-432">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="02e29-433">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-433">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="02e29-434">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="02e29-434">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="02e29-435">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="02e29-435">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="02e29-436">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-436">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="02e29-437">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="02e29-437">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="02e29-438">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="02e29-438">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="02e29-439">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-439">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="02e29-440">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="02e29-440">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="02e29-441">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="02e29-441">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="02e29-442">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-442">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="02e29-443">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="02e29-443">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="02e29-444">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="02e29-444">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="02e29-445">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-445">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="02e29-446">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="02e29-446">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="02e29-447">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="02e29-447">**mvc, razor**</span></span>

<span data-ttu-id="02e29-448">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="02e29-448">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="02e29-449">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="02e29-449">The possible values are:</span></span>

- <span data-ttu-id="02e29-450">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="02e29-450">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="02e29-451">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-451">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="02e29-452">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-452">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="02e29-453">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-453">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="02e29-454">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-454">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="02e29-455">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-455">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="02e29-456">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="02e29-456">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="02e29-457">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-457">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="02e29-458">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="02e29-458">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="02e29-459">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="02e29-459">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="02e29-460">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-460">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="02e29-461">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="02e29-461">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="02e29-462">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-462">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="02e29-463">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="02e29-463">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="02e29-464">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="02e29-465">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="02e29-465">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="02e29-466">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-466">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="02e29-467">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="02e29-467">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="02e29-468">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="02e29-468">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="02e29-469">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-469">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="02e29-470">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="02e29-470">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="02e29-471">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="02e29-471">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="02e29-472">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-472">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="02e29-473">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="02e29-473">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="02e29-474">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="02e29-474">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="02e29-475">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-475">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="02e29-476">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="02e29-476">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="02e29-477">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="02e29-477">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="02e29-478">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="02e29-478">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="02e29-479">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="02e29-479">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="02e29-480">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="02e29-480">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="02e29-481">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-481">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="02e29-482">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="02e29-482">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="02e29-483">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="02e29-483">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="02e29-484">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="02e29-484">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="02e29-485">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="02e29-485">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="02e29-486">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="02e29-486">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="02e29-487">**page**</span><span class="sxs-lookup"><span data-stu-id="02e29-487">**page**</span></span>

<span data-ttu-id="02e29-488">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="02e29-488">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="02e29-489">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="02e29-489">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="02e29-490">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="02e29-490">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="02e29-491">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="02e29-491">**viewimports**</span></span>

<span data-ttu-id="02e29-492">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="02e29-492">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="02e29-493">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="02e29-493">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="02e29-494">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="02e29-494">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="02e29-495">**console、xunit、mstest、web、webapi**</span><span class="sxs-lookup"><span data-stu-id="02e29-495">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="02e29-496">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="02e29-496">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="02e29-497">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="02e29-497">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="02e29-498">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="02e29-498">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="02e29-499">**classlib**</span><span class="sxs-lookup"><span data-stu-id="02e29-499">**classlib**</span></span>

<span data-ttu-id="02e29-500">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="02e29-500">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="02e29-501">值：`netcoreapp1.0`、`netcoreapp1.1` 或 `netstandard1.0` 到 `netstandard1.6`。</span><span class="sxs-lookup"><span data-stu-id="02e29-501">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="02e29-502">默认值为 `netstandard1.4`。</span><span class="sxs-lookup"><span data-stu-id="02e29-502">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="02e29-503">**mvc**</span><span class="sxs-lookup"><span data-stu-id="02e29-503">**mvc**</span></span>

<span data-ttu-id="02e29-504">`-f|--framework` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="02e29-504">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="02e29-505">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="02e29-505">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="02e29-506">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="02e29-506">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="02e29-507">`-au|--auth` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="02e29-507">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="02e29-508">值：`None` 或 `Individual`。</span><span class="sxs-lookup"><span data-stu-id="02e29-508">Values: `None` or `Individual`.</span></span> <span data-ttu-id="02e29-509">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="02e29-509">The default value is `None`.</span></span>

<span data-ttu-id="02e29-510">`-uld|--use-local-db` - 指定是否使用 LocalDB，而不是 SQLite。</span><span class="sxs-lookup"><span data-stu-id="02e29-510">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="02e29-511">值：`true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="02e29-511">Values: `true` or `false`.</span></span> <span data-ttu-id="02e29-512">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="02e29-512">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="02e29-513">示例</span><span class="sxs-lookup"><span data-stu-id="02e29-513">Examples</span></span>

<span data-ttu-id="02e29-514">在当前目录中创建 F# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="02e29-514">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="02e29-515">在指定目录中创建 .NET Standard 类库项目（仅适用于 .NET Core SDK 2.0 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="02e29-515">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="02e29-516">在当前目录中新建没有设置身份验证的 ASP.NET Core C# MVC 应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="02e29-516">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="02e29-517">创建新的 xUnit 应用程序：</span><span class="sxs-lookup"><span data-stu-id="02e29-517">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="02e29-518">列出适用于 MVC 的所有模板：</span><span class="sxs-lookup"><span data-stu-id="02e29-518">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="02e29-519">安装适用于 ASP.NET Core 的单页应用程序模板 2.0 版（命令选项仅可用于 .NET Core SDK 1.1 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="02e29-519">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="02e29-520">在当前目录中创建 global.json，将 SDK 版本设为 2.0.0（仅适用于 .NET Core SDK 2.0 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="02e29-520">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="02e29-521">请参阅</span><span class="sxs-lookup"><span data-stu-id="02e29-521">See also</span></span>

* [<span data-ttu-id="02e29-522">dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="02e29-522">Custom templates for dotnet new</span></span>](custom-templates.md)  
* [<span data-ttu-id="02e29-523">创建 dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="02e29-523">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="02e29-524">dotnet/dotnet-template-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="02e29-524">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* [<span data-ttu-id="02e29-525">dotnet new 可用模板</span><span class="sxs-lookup"><span data-stu-id="02e29-525">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
