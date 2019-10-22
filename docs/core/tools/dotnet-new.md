---
title: dotnet new 命令
description: dotnet new 命令可根据指定模板新建 .NET Core 项目。
ms.date: 05/06/2019
ms.openlocfilehash: b61b5fd53f470c30b636026fa19ebfad834d6354
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117662"
---
# <a name="dotnet-new"></a><span data-ttu-id="55fc3-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="55fc3-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="55fc3-104">name</span><span class="sxs-lookup"><span data-stu-id="55fc3-104">Name</span></span>

<span data-ttu-id="55fc3-105">`dotnet new` - 根据指定的模板，创建新的项目、配置文件或解决方案。</span><span class="sxs-lookup"><span data-stu-id="55fc3-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="55fc3-106">摘要</span><span class="sxs-lookup"><span data-stu-id="55fc3-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="55fc3-107">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="55fc3-107">.NET Core 2.2</span></span>](#tab/netcore22)

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="55fc3-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="55fc3-108">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="55fc3-109">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="55fc3-109">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="55fc3-110">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="55fc3-110">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="55fc3-111">说明</span><span class="sxs-lookup"><span data-stu-id="55fc3-111">Description</span></span>

<span data-ttu-id="55fc3-112">`dotnet new` 命令为初始化有效的 .NET Core 项目提供了便捷方法。</span><span class="sxs-lookup"><span data-stu-id="55fc3-112">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="55fc3-113">命令调用[模板引擎](https://github.com/dotnet/templating)，以根据指定的模板和选项在磁盘上创建项目。</span><span class="sxs-lookup"><span data-stu-id="55fc3-113">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="55fc3-114">自变量</span><span class="sxs-lookup"><span data-stu-id="55fc3-114">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="55fc3-115">调用命令时要实例化的模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-115">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="55fc3-116">每个模板可能具有可传递的特定选项。</span><span class="sxs-lookup"><span data-stu-id="55fc3-116">Each template might have specific options you can pass.</span></span> <span data-ttu-id="55fc3-117">有关详细信息，请参阅[模板选项](#template-options)。</span><span class="sxs-lookup"><span data-stu-id="55fc3-117">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="55fc3-118">如果 `TEMPLATE` 值与“模板”或“短名称”列中的文本不完全匹配，则会对这两列执行 substring 匹配   。</span><span class="sxs-lookup"><span data-stu-id="55fc3-118">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column, a substring match is performed on those two columns.</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="55fc3-119">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="55fc3-119">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="55fc3-120">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="55fc3-120">The command contains a default list of templates.</span></span> <span data-ttu-id="55fc3-121">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="55fc3-121">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="55fc3-122">下表显示了随 .NET Core SDK 2.2.100 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-122">The following table shows the templates that come pre-installed with the .NET Core SDK 2.2.100.</span></span> <span data-ttu-id="55fc3-123">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="55fc3-123">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="55fc3-124">模板</span><span class="sxs-lookup"><span data-stu-id="55fc3-124">Templates</span></span>                                    | <span data-ttu-id="55fc3-125">短名称</span><span class="sxs-lookup"><span data-stu-id="55fc3-125">Short Name</span></span>        | <span data-ttu-id="55fc3-126">语言</span><span class="sxs-lookup"><span data-stu-id="55fc3-126">Language</span></span>     | <span data-ttu-id="55fc3-127">Tags</span><span class="sxs-lookup"><span data-stu-id="55fc3-127">Tags</span></span>                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| <span data-ttu-id="55fc3-128">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="55fc3-128">Console Application</span></span>                          | `console`         | <span data-ttu-id="55fc3-129">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="55fc3-129">[C#], F#, VB</span></span> | <span data-ttu-id="55fc3-130">常用/控制台</span><span class="sxs-lookup"><span data-stu-id="55fc3-130">Common/Console</span></span>                        |
| <span data-ttu-id="55fc3-131">类库</span><span class="sxs-lookup"><span data-stu-id="55fc3-131">Class library</span></span>                                | `classlib`        | <span data-ttu-id="55fc3-132">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="55fc3-132">[C#], F#, VB</span></span> | <span data-ttu-id="55fc3-133">常用/库</span><span class="sxs-lookup"><span data-stu-id="55fc3-133">Common/Library</span></span>                        |
| <span data-ttu-id="55fc3-134">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="55fc3-134">Unit Test Project</span></span>                            | `mstest`          | <span data-ttu-id="55fc3-135">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="55fc3-135">[C#], F#, VB</span></span> | <span data-ttu-id="55fc3-136">测试/MSTest</span><span class="sxs-lookup"><span data-stu-id="55fc3-136">Test/MSTest</span></span>                           |
| <span data-ttu-id="55fc3-137">NUnit 3 测试项目</span><span class="sxs-lookup"><span data-stu-id="55fc3-137">NUnit 3 Test Project</span></span>                         | `nunit`           | <span data-ttu-id="55fc3-138">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="55fc3-138">[C#], F#, VB</span></span> | <span data-ttu-id="55fc3-139">测试/NUnit</span><span class="sxs-lookup"><span data-stu-id="55fc3-139">Test/NUnit</span></span>                            |
| <span data-ttu-id="55fc3-140">NUnit 3 测试项</span><span class="sxs-lookup"><span data-stu-id="55fc3-140">NUnit 3 Test Item</span></span>                            | `nunit-test`      | <span data-ttu-id="55fc3-141">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="55fc3-141">[C#], F#, VB</span></span> | <span data-ttu-id="55fc3-142">测试/NUnit</span><span class="sxs-lookup"><span data-stu-id="55fc3-142">Test/NUnit</span></span>                            |
| <span data-ttu-id="55fc3-143">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="55fc3-143">xUnit Test Project</span></span>                           | `xunit`           | <span data-ttu-id="55fc3-144">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="55fc3-144">[C#], F#, VB</span></span> | <span data-ttu-id="55fc3-145">测试/xUnit</span><span class="sxs-lookup"><span data-stu-id="55fc3-145">Test/xUnit</span></span>                            |
| <span data-ttu-id="55fc3-146">Razor 页</span><span class="sxs-lookup"><span data-stu-id="55fc3-146">Razor Page</span></span>                                   | `page`            | <span data-ttu-id="55fc3-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-147">[C#]</span></span>         | <span data-ttu-id="55fc3-148">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="55fc3-148">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="55fc3-149">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="55fc3-149">MVC ViewImports</span></span>                              | `viewimports`     | <span data-ttu-id="55fc3-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-150">[C#]</span></span>         | <span data-ttu-id="55fc3-151">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="55fc3-151">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="55fc3-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="55fc3-152">MVC ViewStart</span></span>                                | `viewstart`       | <span data-ttu-id="55fc3-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-153">[C#]</span></span>         | <span data-ttu-id="55fc3-154">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="55fc3-154">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="55fc3-155">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="55fc3-155">ASP.NET Core Empty</span></span>                           | `web`             | <span data-ttu-id="55fc3-156">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="55fc3-156">[C#], F#</span></span>     | <span data-ttu-id="55fc3-157">Web/空</span><span class="sxs-lookup"><span data-stu-id="55fc3-157">Web/Empty</span></span>                             |
| <span data-ttu-id="55fc3-158">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="55fc3-158">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`             | <span data-ttu-id="55fc3-159">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="55fc3-159">[C#], F#</span></span>     | <span data-ttu-id="55fc3-160">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="55fc3-160">Web/MVC</span></span>                               |
| <span data-ttu-id="55fc3-161">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="55fc3-161">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="55fc3-162">`webapp`， `razor`</span><span class="sxs-lookup"><span data-stu-id="55fc3-162">`webapp`, `razor`</span></span> | <span data-ttu-id="55fc3-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-163">[C#]</span></span>         | <span data-ttu-id="55fc3-164">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="55fc3-164">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="55fc3-165">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="55fc3-165">ASP.NET Core with Angular</span></span>                    | `angular`         | <span data-ttu-id="55fc3-166">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-166">[C#]</span></span>         | <span data-ttu-id="55fc3-167">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="55fc3-167">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="55fc3-168">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="55fc3-168">ASP.NET Core with React.js</span></span>                   | `react`           | <span data-ttu-id="55fc3-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-169">[C#]</span></span>         | <span data-ttu-id="55fc3-170">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="55fc3-170">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="55fc3-171">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="55fc3-171">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`      | <span data-ttu-id="55fc3-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-172">[C#]</span></span>         | <span data-ttu-id="55fc3-173">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="55fc3-173">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="55fc3-174">Razor 类库</span><span class="sxs-lookup"><span data-stu-id="55fc3-174">Razor Class Library</span></span>                          | `razorclasslib`   | <span data-ttu-id="55fc3-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-175">[C#]</span></span>         | <span data-ttu-id="55fc3-176">Web/Razor/库/Razor 类库</span><span class="sxs-lookup"><span data-stu-id="55fc3-176">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="55fc3-177">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="55fc3-177">ASP.NET Core Web API</span></span>                         | `webapi`          | <span data-ttu-id="55fc3-178">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="55fc3-178">[C#], F#</span></span>     | <span data-ttu-id="55fc3-179">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="55fc3-179">Web/WebAPI</span></span>                            |
| <span data-ttu-id="55fc3-180">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="55fc3-180">global.json file</span></span>                             | `globaljson`      |              | <span data-ttu-id="55fc3-181">配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-181">Config</span></span>                                |
| <span data-ttu-id="55fc3-182">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-182">NuGet Config</span></span>                                 | `nugetconfig`     |              | <span data-ttu-id="55fc3-183">配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-183">Config</span></span>                                |
| <span data-ttu-id="55fc3-184">Web 配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-184">Web Config</span></span>                                   | `webconfig`       |              | <span data-ttu-id="55fc3-185">配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-185">Config</span></span>                                |
| <span data-ttu-id="55fc3-186">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="55fc3-186">Solution File</span></span>                                | `sln`             |              | <span data-ttu-id="55fc3-187">解决方案</span><span class="sxs-lookup"><span data-stu-id="55fc3-187">Solution</span></span>                              |

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="55fc3-188">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="55fc3-188">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="55fc3-189">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="55fc3-189">The command contains a default list of templates.</span></span> <span data-ttu-id="55fc3-190">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="55fc3-190">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="55fc3-191">下表列出了随 .NET Core SDK 2.1.300 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-191">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="55fc3-192">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="55fc3-192">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="55fc3-193">模板</span><span class="sxs-lookup"><span data-stu-id="55fc3-193">Templates</span></span>                                    | <span data-ttu-id="55fc3-194">短名称</span><span class="sxs-lookup"><span data-stu-id="55fc3-194">Short Name</span></span>      | <span data-ttu-id="55fc3-195">语言</span><span class="sxs-lookup"><span data-stu-id="55fc3-195">Language</span></span>     | <span data-ttu-id="55fc3-196">Tags</span><span class="sxs-lookup"><span data-stu-id="55fc3-196">Tags</span></span>                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| <span data-ttu-id="55fc3-197">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="55fc3-197">Console Application</span></span>                          | `console`       | <span data-ttu-id="55fc3-198">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="55fc3-198">[C#], F#, VB</span></span> | <span data-ttu-id="55fc3-199">常用/控制台</span><span class="sxs-lookup"><span data-stu-id="55fc3-199">Common/Console</span></span>                        |
| <span data-ttu-id="55fc3-200">类库</span><span class="sxs-lookup"><span data-stu-id="55fc3-200">Class library</span></span>                                | `classlib`      | <span data-ttu-id="55fc3-201">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="55fc3-201">[C#], F#, VB</span></span> | <span data-ttu-id="55fc3-202">常用/库</span><span class="sxs-lookup"><span data-stu-id="55fc3-202">Common/Library</span></span>                        |
| <span data-ttu-id="55fc3-203">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="55fc3-203">Unit Test Project</span></span>                            | `mstest`        | <span data-ttu-id="55fc3-204">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="55fc3-204">[C#], F#, VB</span></span> | <span data-ttu-id="55fc3-205">测试/MSTest</span><span class="sxs-lookup"><span data-stu-id="55fc3-205">Test/MSTest</span></span>                           |
| <span data-ttu-id="55fc3-206">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="55fc3-206">xUnit Test Project</span></span>                           | `xunit`         | <span data-ttu-id="55fc3-207">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="55fc3-207">[C#], F#, VB</span></span> | <span data-ttu-id="55fc3-208">测试/xUnit</span><span class="sxs-lookup"><span data-stu-id="55fc3-208">Test/xUnit</span></span>                            |
| <span data-ttu-id="55fc3-209">Razor 页</span><span class="sxs-lookup"><span data-stu-id="55fc3-209">Razor Page</span></span>                                   | `page`          | <span data-ttu-id="55fc3-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-210">[C#]</span></span>         | <span data-ttu-id="55fc3-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="55fc3-211">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="55fc3-212">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="55fc3-212">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="55fc3-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-213">[C#]</span></span>         | <span data-ttu-id="55fc3-214">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="55fc3-214">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="55fc3-215">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="55fc3-215">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="55fc3-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-216">[C#]</span></span>         | <span data-ttu-id="55fc3-217">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="55fc3-217">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="55fc3-218">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="55fc3-218">ASP.NET Core Empty</span></span>                           | `web`           | <span data-ttu-id="55fc3-219">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="55fc3-219">[C#], F#</span></span>     | <span data-ttu-id="55fc3-220">Web/空</span><span class="sxs-lookup"><span data-stu-id="55fc3-220">Web/Empty</span></span>                             |
| <span data-ttu-id="55fc3-221">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="55fc3-221">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="55fc3-222">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="55fc3-222">[C#], F#</span></span>     | <span data-ttu-id="55fc3-223">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="55fc3-223">Web/MVC</span></span>                               |
| <span data-ttu-id="55fc3-224">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="55fc3-224">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="55fc3-225">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-225">[C#]</span></span>         | <span data-ttu-id="55fc3-226">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="55fc3-226">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="55fc3-227">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="55fc3-227">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="55fc3-228">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-228">[C#]</span></span>         | <span data-ttu-id="55fc3-229">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="55fc3-229">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="55fc3-230">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="55fc3-230">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="55fc3-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-231">[C#]</span></span>         | <span data-ttu-id="55fc3-232">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="55fc3-232">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="55fc3-233">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="55fc3-233">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="55fc3-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-234">[C#]</span></span>         | <span data-ttu-id="55fc3-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="55fc3-235">Web/MVC/SPA</span></span>                           | 
| <span data-ttu-id="55fc3-236">Razor 类库</span><span class="sxs-lookup"><span data-stu-id="55fc3-236">Razor Class Library</span></span>                          | `razorclasslib` | <span data-ttu-id="55fc3-237">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-237">[C#]</span></span>         | <span data-ttu-id="55fc3-238">Web/Razor/库/Razor 类库</span><span class="sxs-lookup"><span data-stu-id="55fc3-238">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="55fc3-239">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="55fc3-239">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="55fc3-240">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="55fc3-240">[C#], F#</span></span>     | <span data-ttu-id="55fc3-241">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="55fc3-241">Web/WebAPI</span></span>                            |
| <span data-ttu-id="55fc3-242">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="55fc3-242">global.json file</span></span>                             | `globaljson`    |              | <span data-ttu-id="55fc3-243">配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-243">Config</span></span>                                |
| <span data-ttu-id="55fc3-244">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-244">NuGet Config</span></span>                                 | `nugetconfig`   |              | <span data-ttu-id="55fc3-245">配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-245">Config</span></span>                                |
| <span data-ttu-id="55fc3-246">Web 配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-246">Web Config</span></span>                                   | `webconfig`     |              | <span data-ttu-id="55fc3-247">配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-247">Config</span></span>                                |
| <span data-ttu-id="55fc3-248">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="55fc3-248">Solution File</span></span>                                | `sln`           |              | <span data-ttu-id="55fc3-249">解决方案</span><span class="sxs-lookup"><span data-stu-id="55fc3-249">Solution</span></span>                              |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="55fc3-250">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="55fc3-250">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="55fc3-251">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="55fc3-251">The command contains a default list of templates.</span></span> <span data-ttu-id="55fc3-252">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="55fc3-252">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="55fc3-253">下表显示了随 .NET Core SDK 2.0.0 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-253">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.0.</span></span> <span data-ttu-id="55fc3-254">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="55fc3-254">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="55fc3-255">模板</span><span class="sxs-lookup"><span data-stu-id="55fc3-255">Templates</span></span>                                    | <span data-ttu-id="55fc3-256">短名称</span><span class="sxs-lookup"><span data-stu-id="55fc3-256">Short Name</span></span>    | <span data-ttu-id="55fc3-257">语言</span><span class="sxs-lookup"><span data-stu-id="55fc3-257">Language</span></span>     | <span data-ttu-id="55fc3-258">Tags</span><span class="sxs-lookup"><span data-stu-id="55fc3-258">Tags</span></span>                |
|----------------------------------------------|---------------|--------------|---------------------|
| <span data-ttu-id="55fc3-259">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="55fc3-259">Console Application</span></span>                          | `console`     | <span data-ttu-id="55fc3-260">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="55fc3-260">[C#], F#, VB</span></span> | <span data-ttu-id="55fc3-261">常用/控制台</span><span class="sxs-lookup"><span data-stu-id="55fc3-261">Common/Console</span></span>      |
| <span data-ttu-id="55fc3-262">类库</span><span class="sxs-lookup"><span data-stu-id="55fc3-262">Class library</span></span>                                | `classlib`    | <span data-ttu-id="55fc3-263">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="55fc3-263">[C#], F#, VB</span></span> | <span data-ttu-id="55fc3-264">常用/库</span><span class="sxs-lookup"><span data-stu-id="55fc3-264">Common/Library</span></span>      |
| <span data-ttu-id="55fc3-265">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="55fc3-265">Unit Test Project</span></span>                            | `mstest`      | <span data-ttu-id="55fc3-266">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="55fc3-266">[C#], F#, VB</span></span> | <span data-ttu-id="55fc3-267">测试/MSTest</span><span class="sxs-lookup"><span data-stu-id="55fc3-267">Test/MSTest</span></span>         |
| <span data-ttu-id="55fc3-268">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="55fc3-268">xUnit Test Project</span></span>                           | `xunit`       | <span data-ttu-id="55fc3-269">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="55fc3-269">[C#], F#, VB</span></span> | <span data-ttu-id="55fc3-270">测试/xUnit</span><span class="sxs-lookup"><span data-stu-id="55fc3-270">Test/xUnit</span></span>          |
| <span data-ttu-id="55fc3-271">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="55fc3-271">ASP.NET Core Empty</span></span>                           | `web`         | <span data-ttu-id="55fc3-272">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="55fc3-272">[C#], F#</span></span>     | <span data-ttu-id="55fc3-273">Web/空</span><span class="sxs-lookup"><span data-stu-id="55fc3-273">Web/Empty</span></span>           |
| <span data-ttu-id="55fc3-274">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="55fc3-274">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="55fc3-275">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="55fc3-275">[C#], F#</span></span>     | <span data-ttu-id="55fc3-276">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="55fc3-276">Web/MVC</span></span>             |
| <span data-ttu-id="55fc3-277">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="55fc3-277">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="55fc3-278">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-278">[C#]</span></span>         | <span data-ttu-id="55fc3-279">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="55fc3-279">Web/MVC/Razor Pages</span></span> |
| <span data-ttu-id="55fc3-280">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="55fc3-280">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="55fc3-281">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-281">[C#]</span></span>         | <span data-ttu-id="55fc3-282">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="55fc3-282">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="55fc3-283">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="55fc3-283">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="55fc3-284">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-284">[C#]</span></span>         | <span data-ttu-id="55fc3-285">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="55fc3-285">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="55fc3-286">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="55fc3-286">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="55fc3-287">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-287">[C#]</span></span>         | <span data-ttu-id="55fc3-288">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="55fc3-288">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="55fc3-289">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="55fc3-289">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="55fc3-290">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="55fc3-290">[C#], F#</span></span>     | <span data-ttu-id="55fc3-291">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="55fc3-291">Web/WebAPI</span></span>          |
| <span data-ttu-id="55fc3-292">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="55fc3-292">global.json file</span></span>                             | `globaljson`  |              | <span data-ttu-id="55fc3-293">配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-293">Config</span></span>              |
| <span data-ttu-id="55fc3-294">Nuget 配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-294">Nuget Config</span></span>                                 | `nugetconfig` |              | <span data-ttu-id="55fc3-295">配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-295">Config</span></span>              |
| <span data-ttu-id="55fc3-296">Web 配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-296">Web Config</span></span>                                   | `webconfig`   |              | <span data-ttu-id="55fc3-297">配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-297">Config</span></span>              |
| <span data-ttu-id="55fc3-298">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="55fc3-298">Solution File</span></span>                                | `sln`         |              | <span data-ttu-id="55fc3-299">解决方案</span><span class="sxs-lookup"><span data-stu-id="55fc3-299">Solution</span></span>            |
| <span data-ttu-id="55fc3-300">Razor 页</span><span class="sxs-lookup"><span data-stu-id="55fc3-300">Razor Page</span></span>                                   | `page`        |              | <span data-ttu-id="55fc3-301">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="55fc3-301">Web/ASP.NET</span></span>         |
| <span data-ttu-id="55fc3-302">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="55fc3-302">MVC ViewImports</span></span>                              | `viewimports` |              | <span data-ttu-id="55fc3-303">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="55fc3-303">Web/ASP.NET</span></span>         |
| <span data-ttu-id="55fc3-304">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="55fc3-304">MVC ViewStart</span></span>                                | `viewstart`   |              | <span data-ttu-id="55fc3-305">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="55fc3-305">Web/ASP.NET</span></span>         |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="55fc3-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="55fc3-306">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="55fc3-307">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="55fc3-307">The command contains a default list of templates.</span></span> <span data-ttu-id="55fc3-308">使用 `dotnet new -all` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="55fc3-308">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="55fc3-309">下表显示了随 .NET Core SDK 1.0.1 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-309">The following table shows the templates that come pre-installed with the .NET Core SDK 1.0.1.</span></span> <span data-ttu-id="55fc3-310">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="55fc3-310">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="55fc3-311">模板</span><span class="sxs-lookup"><span data-stu-id="55fc3-311">Templates</span></span>            | <span data-ttu-id="55fc3-312">短名称</span><span class="sxs-lookup"><span data-stu-id="55fc3-312">Short Name</span></span>    | <span data-ttu-id="55fc3-313">语言</span><span class="sxs-lookup"><span data-stu-id="55fc3-313">Language</span></span> | <span data-ttu-id="55fc3-314">Tags</span><span class="sxs-lookup"><span data-stu-id="55fc3-314">Tags</span></span>           |
|----------------------|---------------|----------|----------------|
| <span data-ttu-id="55fc3-315">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="55fc3-315">Console Application</span></span>  | `console`     | <span data-ttu-id="55fc3-316">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="55fc3-316">[C#], F#</span></span> | <span data-ttu-id="55fc3-317">常用/控制台</span><span class="sxs-lookup"><span data-stu-id="55fc3-317">Common/Console</span></span> |
| <span data-ttu-id="55fc3-318">类库</span><span class="sxs-lookup"><span data-stu-id="55fc3-318">Class library</span></span>        | `classlib`    | <span data-ttu-id="55fc3-319">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="55fc3-319">[C#], F#</span></span> | <span data-ttu-id="55fc3-320">常用/库</span><span class="sxs-lookup"><span data-stu-id="55fc3-320">Common/Library</span></span> |
| <span data-ttu-id="55fc3-321">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="55fc3-321">Unit Test Project</span></span>    | `mstest`      | <span data-ttu-id="55fc3-322">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="55fc3-322">[C#], F#</span></span> | <span data-ttu-id="55fc3-323">测试/MSTest</span><span class="sxs-lookup"><span data-stu-id="55fc3-323">Test/MSTest</span></span>    |
| <span data-ttu-id="55fc3-324">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="55fc3-324">xUnit Test Project</span></span>   | `xunit`       | <span data-ttu-id="55fc3-325">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="55fc3-325">[C#], F#</span></span> | <span data-ttu-id="55fc3-326">测试/xUnit</span><span class="sxs-lookup"><span data-stu-id="55fc3-326">Test/xUnit</span></span>     |
| <span data-ttu-id="55fc3-327">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="55fc3-327">ASP.NET Core Empty</span></span>   | `web`         | <span data-ttu-id="55fc3-328">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-328">[C#]</span></span>     | <span data-ttu-id="55fc3-329">Web/空</span><span class="sxs-lookup"><span data-stu-id="55fc3-329">Web/Empty</span></span>      |
| <span data-ttu-id="55fc3-330">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="55fc3-330">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="55fc3-331">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="55fc3-331">[C#], F#</span></span> | <span data-ttu-id="55fc3-332">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="55fc3-332">Web/MVC</span></span>        |
| <span data-ttu-id="55fc3-333">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="55fc3-333">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="55fc3-334">[C#]</span><span class="sxs-lookup"><span data-stu-id="55fc3-334">[C#]</span></span>     | <span data-ttu-id="55fc3-335">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="55fc3-335">Web/WebAPI</span></span>     |
| <span data-ttu-id="55fc3-336">Nuget 配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-336">Nuget Config</span></span>         | `nugetconfig` |          | <span data-ttu-id="55fc3-337">配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-337">Config</span></span>         |
| <span data-ttu-id="55fc3-338">Web 配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-338">Web Config</span></span>           | `webconfig`   |          | <span data-ttu-id="55fc3-339">配置</span><span class="sxs-lookup"><span data-stu-id="55fc3-339">Config</span></span>         |
| <span data-ttu-id="55fc3-340">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="55fc3-340">Solution File</span></span>        | `sln`         |          | <span data-ttu-id="55fc3-341">解决方案</span><span class="sxs-lookup"><span data-stu-id="55fc3-341">Solution</span></span>       |

---

## <a name="options"></a><span data-ttu-id="55fc3-342">选项</span><span class="sxs-lookup"><span data-stu-id="55fc3-342">Options</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="55fc3-343">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="55fc3-343">.NET Core 2.2</span></span>](#tab/netcore22)

`--dry-run`

<span data-ttu-id="55fc3-344">显示有关以下内容的摘要：给定命令运行导致模板创建时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="55fc3-344">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span>

`--force`

<span data-ttu-id="55fc3-345">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="55fc3-345">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="55fc3-346">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="55fc3-346">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="55fc3-347">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="55fc3-347">Prints out help for the command.</span></span> <span data-ttu-id="55fc3-348">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="55fc3-348">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="55fc3-349">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="55fc3-349">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="55fc3-350">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="55fc3-350">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="55fc3-351">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="55fc3-351">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="55fc3-352">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="55fc3-352">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="55fc3-353">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="55fc3-353">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="55fc3-354">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-354">Lists templates containing the specified name.</span></span> <span data-ttu-id="55fc3-355">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-355">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="55fc3-356">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-356">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="55fc3-357">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="55fc3-357">The language of the template to create.</span></span> <span data-ttu-id="55fc3-358">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="55fc3-358">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="55fc3-359">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="55fc3-359">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="55fc3-360">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="55fc3-360">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="55fc3-361">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-361">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="55fc3-362">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="55fc3-362">The name for the created output.</span></span> <span data-ttu-id="55fc3-363">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="55fc3-363">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="55fc3-364">指定在安装期间要使用的 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="55fc3-364">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="55fc3-365">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="55fc3-365">Location to place the generated output.</span></span> <span data-ttu-id="55fc3-366">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="55fc3-366">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="55fc3-367">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-367">Filters templates based on available types.</span></span> <span data-ttu-id="55fc3-368">预定义的值为“项目”、“项”或“其他”。</span><span class="sxs-lookup"><span data-stu-id="55fc3-368">Predefined values are "project", "item", or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="55fc3-369">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="55fc3-369">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="55fc3-370">如果排除 `<PATH|NUGET_ID>` 值，将显示所有当前安装的模板包及其关联的模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-370">When excluding the `<PATH|NUGET_ID>` value, all currently installed template packs and their associated templates are displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="55fc3-371">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="55fc3-371">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="55fc3-372">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp  有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp  无效。</span><span class="sxs-lookup"><span data-stu-id="55fc3-372">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="55fc3-373">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="55fc3-373">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="55fc3-374">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="55fc3-374">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="55fc3-375">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="55fc3-375">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="55fc3-376">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="55fc3-376">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="55fc3-377">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="55fc3-377">Prints out help for the command.</span></span> <span data-ttu-id="55fc3-378">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="55fc3-378">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="55fc3-379">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="55fc3-379">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="55fc3-380">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="55fc3-380">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="55fc3-381">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="55fc3-381">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="55fc3-382">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="55fc3-382">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="55fc3-383">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="55fc3-383">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="55fc3-384">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-384">Lists templates containing the specified name.</span></span> <span data-ttu-id="55fc3-385">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-385">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="55fc3-386">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-386">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="55fc3-387">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="55fc3-387">The language of the template to create.</span></span> <span data-ttu-id="55fc3-388">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="55fc3-388">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="55fc3-389">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="55fc3-389">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="55fc3-390">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="55fc3-390">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="55fc3-391">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-391">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="55fc3-392">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="55fc3-392">The name for the created output.</span></span> <span data-ttu-id="55fc3-393">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="55fc3-393">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="55fc3-394">指定在安装期间要使用的 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="55fc3-394">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="55fc3-395">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="55fc3-395">Location to place the generated output.</span></span> <span data-ttu-id="55fc3-396">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="55fc3-396">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="55fc3-397">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-397">Filters templates based on available types.</span></span> <span data-ttu-id="55fc3-398">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="55fc3-398">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="55fc3-399">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="55fc3-399">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="55fc3-400">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="55fc3-400">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="55fc3-401">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp  有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp  无效。</span><span class="sxs-lookup"><span data-stu-id="55fc3-401">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="55fc3-402">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="55fc3-402">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="55fc3-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="55fc3-403">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="55fc3-404">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="55fc3-404">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="55fc3-405">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="55fc3-405">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="55fc3-406">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="55fc3-406">Prints out help for the command.</span></span> <span data-ttu-id="55fc3-407">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="55fc3-407">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="55fc3-408">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="55fc3-408">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="55fc3-409">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="55fc3-409">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="55fc3-410">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="55fc3-410">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="55fc3-411">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="55fc3-411">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="55fc3-412">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="55fc3-412">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="55fc3-413">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-413">Lists templates containing the specified name.</span></span> <span data-ttu-id="55fc3-414">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-414">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="55fc3-415">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-415">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="55fc3-416">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="55fc3-416">The language of the template to create.</span></span> <span data-ttu-id="55fc3-417">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="55fc3-417">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="55fc3-418">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="55fc3-418">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="55fc3-419">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="55fc3-419">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="55fc3-420">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-420">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="55fc3-421">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="55fc3-421">The name for the created output.</span></span> <span data-ttu-id="55fc3-422">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="55fc3-422">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="55fc3-423">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="55fc3-423">Location to place the generated output.</span></span> <span data-ttu-id="55fc3-424">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="55fc3-424">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="55fc3-425">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-425">Filters templates based on available types.</span></span> <span data-ttu-id="55fc3-426">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="55fc3-426">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="55fc3-427">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="55fc3-427">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="55fc3-428">若要使用源 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="55fc3-428">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="55fc3-429">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp  有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp  无效。</span><span class="sxs-lookup"><span data-stu-id="55fc3-429">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="55fc3-430">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="55fc3-430">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="55fc3-431">如果无法确定卸载模板所需的 `PATH` 或 `NUGET_ID` 参数，则在没有参数的情况下运行 `dotnet new --uninstall` 将列出所有已安装的模板以及卸载它们所需的参数。</span><span class="sxs-lookup"><span data-stu-id="55fc3-431">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="55fc3-432">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="55fc3-432">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="55fc3-433">单独在 `dotnet new` 命令的上下文中运行时，显示特定类型的项目的所有模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-433">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="55fc3-434">在特定模板（如 `dotnet new web -all`）的上下文中运行时，`-all` 解释为一个强制创建标记。</span><span class="sxs-lookup"><span data-stu-id="55fc3-434">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="55fc3-435">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="55fc3-435">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="55fc3-436">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="55fc3-436">Prints out help for the command.</span></span> <span data-ttu-id="55fc3-437">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="55fc3-437">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="55fc3-438">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-438">Lists templates containing the specified name.</span></span> <span data-ttu-id="55fc3-439">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-439">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="55fc3-440">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-440">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="55fc3-441">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="55fc3-441">The language of the template to create.</span></span> <span data-ttu-id="55fc3-442">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="55fc3-442">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="55fc3-443">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="55fc3-443">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="55fc3-444">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="55fc3-444">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="55fc3-445">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-445">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="55fc3-446">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="55fc3-446">The name for the created output.</span></span> <span data-ttu-id="55fc3-447">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="55fc3-447">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="55fc3-448">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="55fc3-448">Location to place the generated output.</span></span> <span data-ttu-id="55fc3-449">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="55fc3-449">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="55fc3-450">模板选项</span><span class="sxs-lookup"><span data-stu-id="55fc3-450">Template options</span></span>

<span data-ttu-id="55fc3-451">每个项目模板都可能有附加选项。</span><span class="sxs-lookup"><span data-stu-id="55fc3-451">Each project template may have additional options available.</span></span> <span data-ttu-id="55fc3-452">核心模板有以下附加选项：</span><span class="sxs-lookup"><span data-stu-id="55fc3-452">The core templates have the following additional options:</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="55fc3-453">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="55fc3-453">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="55fc3-454">**控制台**</span><span class="sxs-lookup"><span data-stu-id="55fc3-454">**console**</span></span>

<span data-ttu-id="55fc3-455">`--langVersion <VERSION_NUMBER>` - 在已创建的项目文件中设置 `LangVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="55fc3-455">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="55fc3-456">例如，使用 `--langVersion 7.3` 以使用 C# 7.3。</span><span class="sxs-lookup"><span data-stu-id="55fc3-456">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="55fc3-457">不支持 F#。</span><span class="sxs-lookup"><span data-stu-id="55fc3-457">Not supported for F#.</span></span>

<span data-ttu-id="55fc3-458">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-458">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-459">**angular、react、reactredux**</span><span class="sxs-lookup"><span data-stu-id="55fc3-459">**angular, react, reactredux**</span></span>

<span data-ttu-id="55fc3-460">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="55fc3-460">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="55fc3-461">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-461">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-462">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="55fc3-462">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="55fc3-463">此选项仅适用于未使用 `IndividualAuth` 或 `OrganizationalAuth` 的情况。</span><span class="sxs-lookup"><span data-stu-id="55fc3-463">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="55fc3-464">**razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="55fc3-464">**razorclasslib**</span></span>

<span data-ttu-id="55fc3-465">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-465">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-466">**classlib**</span><span class="sxs-lookup"><span data-stu-id="55fc3-466">**classlib**</span></span>

<span data-ttu-id="55fc3-467">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="55fc3-467">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="55fc3-468">值：`netcoreapp2.2`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="55fc3-468">Values: `netcoreapp2.2` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="55fc3-469">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-469">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="55fc3-470">`--langVersion <VERSION_NUMBER>` - 在已创建的项目文件中设置 `LangVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="55fc3-470">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="55fc3-471">例如，使用 `--langVersion 7.3` 以使用 C# 7.3。</span><span class="sxs-lookup"><span data-stu-id="55fc3-471">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="55fc3-472">不支持 F#。</span><span class="sxs-lookup"><span data-stu-id="55fc3-472">Not supported for F#.</span></span>

<span data-ttu-id="55fc3-473">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-473">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-474">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="55fc3-474">**mstest, xunit**</span></span>

<span data-ttu-id="55fc3-475">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="55fc3-475">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="55fc3-476">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-476">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-477">**nunit**</span><span class="sxs-lookup"><span data-stu-id="55fc3-477">**nunit**</span></span>

<span data-ttu-id="55fc3-478">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="55fc3-478">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="55fc3-479">默认值为 `netcoreapp2.1`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-479">The default value is `netcoreapp2.1`.</span></span>

<span data-ttu-id="55fc3-480">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="55fc3-480">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="55fc3-481">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-481">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-482">**page**</span><span class="sxs-lookup"><span data-stu-id="55fc3-482">**page**</span></span>

<span data-ttu-id="55fc3-483">`-na|--namespace <NAMESPACE_NAME>` - 已生成代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="55fc3-483">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="55fc3-484">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-484">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="55fc3-485">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="55fc3-485">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="55fc3-486">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="55fc3-486">**viewimports**</span></span>

<span data-ttu-id="55fc3-487">`-na|--namespace <NAMESPACE_NAME>` - 已生成代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="55fc3-487">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="55fc3-488">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-488">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="55fc3-489">**web**</span><span class="sxs-lookup"><span data-stu-id="55fc3-489">**web**</span></span>

<span data-ttu-id="55fc3-490">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="55fc3-490">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="55fc3-491">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-491">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-492">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="55fc3-492">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="55fc3-493">此选项仅适用于未使用 `IndividualAuth` 或 `OrganizationalAuth` 的情况。</span><span class="sxs-lookup"><span data-stu-id="55fc3-493">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="55fc3-494">**mvc、webapp**</span><span class="sxs-lookup"><span data-stu-id="55fc3-494">**mvc, webapp**</span></span>

<span data-ttu-id="55fc3-495">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="55fc3-495">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="55fc3-496">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="55fc3-496">The possible values are:</span></span>

- <span data-ttu-id="55fc3-497">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="55fc3-497">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="55fc3-498">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-498">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="55fc3-499">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-499">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="55fc3-500">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-500">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="55fc3-501">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-501">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="55fc3-502">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-502">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="55fc3-503">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="55fc3-503">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="55fc3-504">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-504">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="55fc3-505">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-505">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="55fc3-506">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-506">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="55fc3-507">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-507">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-508">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-508">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="55fc3-509">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-509">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-510">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-510">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="55fc3-511">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-511">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-512">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="55fc3-512">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="55fc3-513">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-513">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="55fc3-514">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-514">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="55fc3-515">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-515">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="55fc3-516">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-516">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="55fc3-517">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-517">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="55fc3-518">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="55fc3-518">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="55fc3-519">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="55fc3-520">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-520">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="55fc3-521">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-521">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="55fc3-522">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-522">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="55fc3-523">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-523">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="55fc3-524">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="55fc3-524">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="55fc3-525">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-525">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="55fc3-526">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-526">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="55fc3-527">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="55fc3-527">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="55fc3-528">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-528">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="55fc3-529">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="55fc3-529">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="55fc3-530">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="55fc3-530">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="55fc3-531">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="55fc3-531">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="55fc3-532">此选项仅适用于未使用 `Individual`、`IndividualB2C`、`SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="55fc3-532">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="55fc3-533">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="55fc3-533">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="55fc3-534">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-534">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-535">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-535">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-536">**webapi**</span><span class="sxs-lookup"><span data-stu-id="55fc3-536">**webapi**</span></span>

<span data-ttu-id="55fc3-537">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="55fc3-537">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="55fc3-538">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="55fc3-538">The possible values are:</span></span>

- <span data-ttu-id="55fc3-539">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="55fc3-539">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="55fc3-540">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-540">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="55fc3-541">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-541">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="55fc3-542">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-542">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="55fc3-543">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="55fc3-543">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="55fc3-544">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-544">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="55fc3-545">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-545">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="55fc3-546">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-546">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="55fc3-547">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-547">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-548">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="55fc3-548">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="55fc3-549">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-549">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="55fc3-550">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-550">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="55fc3-551">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-551">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="55fc3-552">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-552">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="55fc3-553">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-553">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="55fc3-554">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="55fc3-554">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="55fc3-555">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-555">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="55fc3-556">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-556">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="55fc3-557">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-557">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="55fc3-558">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="55fc3-559">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-559">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="55fc3-560">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="55fc3-560">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="55fc3-561">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-561">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="55fc3-562">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="55fc3-562">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="55fc3-563">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="55fc3-563">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="55fc3-564">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="55fc3-564">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="55fc3-565">此选项仅适用于未使用 `Individual`、`IndividualB2C`、`SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="55fc3-565">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="55fc3-566">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="55fc3-566">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="55fc3-567">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-567">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-568">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-568">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-569">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="55fc3-569">**globaljson**</span></span>

<span data-ttu-id="55fc3-570">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json  文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="55fc3-570">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="55fc3-571">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="55fc3-571">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="55fc3-572">console、angular、react、reactredux、razorclasslib </span><span class="sxs-lookup"><span data-stu-id="55fc3-572">**console, angular, react, reactredux, razorclasslib**</span></span>

<span data-ttu-id="55fc3-573">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-573">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-574">**classlib**</span><span class="sxs-lookup"><span data-stu-id="55fc3-574">**classlib**</span></span>

<span data-ttu-id="55fc3-575">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="55fc3-575">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="55fc3-576">值：`netcoreapp2.1`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="55fc3-576">Values: `netcoreapp2.1` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="55fc3-577">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-577">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="55fc3-578">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-578">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-579">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="55fc3-579">**mstest, xunit**</span></span>

<span data-ttu-id="55fc3-580">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="55fc3-580">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="55fc3-581">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-581">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-582">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="55fc3-582">**globaljson**</span></span>

<span data-ttu-id="55fc3-583">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json  文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="55fc3-583">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="55fc3-584">**web**</span><span class="sxs-lookup"><span data-stu-id="55fc3-584">**web**</span></span>

<span data-ttu-id="55fc3-585">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="55fc3-585">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="55fc3-586">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-586">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-587">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="55fc3-587">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="55fc3-588">此选项仅适用于未使用 `IndividualAuth` 或 `OrganizationalAuth` 的情况。</span><span class="sxs-lookup"><span data-stu-id="55fc3-588">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="55fc3-589">**webapi**</span><span class="sxs-lookup"><span data-stu-id="55fc3-589">**webapi**</span></span>

<span data-ttu-id="55fc3-590">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="55fc3-590">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="55fc3-591">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="55fc3-591">The possible values are:</span></span>

- <span data-ttu-id="55fc3-592">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="55fc3-592">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="55fc3-593">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-593">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="55fc3-594">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-594">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="55fc3-595">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-595">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="55fc3-596">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="55fc3-596">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="55fc3-597">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-597">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="55fc3-598">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-598">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="55fc3-599">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-599">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="55fc3-600">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-600">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-601">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="55fc3-601">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="55fc3-602">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-602">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="55fc3-603">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-603">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="55fc3-604">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-604">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="55fc3-605">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-605">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="55fc3-606">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-606">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="55fc3-607">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="55fc3-607">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="55fc3-608">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-608">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="55fc3-609">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-609">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="55fc3-610">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-610">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="55fc3-611">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-611">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="55fc3-612">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-612">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="55fc3-613">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="55fc3-613">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="55fc3-614">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-614">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="55fc3-615">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="55fc3-615">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="55fc3-616">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="55fc3-616">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="55fc3-617">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-617">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-618">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-618">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-619">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="55fc3-619">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="55fc3-620">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="55fc3-620">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="55fc3-621">此选项仅适用于未使用 `Individual`、`IndividualB2C`、`SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="55fc3-621">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="55fc3-622">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="55fc3-622">**mvc, razor**</span></span>

<span data-ttu-id="55fc3-623">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="55fc3-623">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="55fc3-624">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="55fc3-624">The possible values are:</span></span>

- <span data-ttu-id="55fc3-625">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="55fc3-625">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="55fc3-626">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-626">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="55fc3-627">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-627">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="55fc3-628">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-628">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="55fc3-629">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-629">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="55fc3-630">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-630">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="55fc3-631">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="55fc3-631">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="55fc3-632">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-632">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="55fc3-633">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-633">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="55fc3-634">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-634">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="55fc3-635">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-635">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-636">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-636">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="55fc3-637">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-637">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-638">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-638">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="55fc3-639">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-639">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-640">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="55fc3-640">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="55fc3-641">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-641">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="55fc3-642">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-642">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="55fc3-643">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-643">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="55fc3-644">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-644">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="55fc3-645">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-645">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="55fc3-646">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="55fc3-646">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="55fc3-647">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-647">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="55fc3-648">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-648">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="55fc3-649">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-649">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="55fc3-650">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-650">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="55fc3-651">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-651">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="55fc3-652">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="55fc3-652">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="55fc3-653">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-653">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="55fc3-654">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-654">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="55fc3-655">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="55fc3-655">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="55fc3-656">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-656">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="55fc3-657">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="55fc3-657">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="55fc3-658">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="55fc3-658">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="55fc3-659">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="55fc3-659">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="55fc3-660">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-660">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-661">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-661">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-662">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="55fc3-662">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="55fc3-663">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="55fc3-663">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="55fc3-664">此选项仅适用于未使用 `Individual`、`IndividualB2C`、`SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="55fc3-664">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="55fc3-665">**page**</span><span class="sxs-lookup"><span data-stu-id="55fc3-665">**page**</span></span>

<span data-ttu-id="55fc3-666">`-na|--namespace <NAMESPACE_NAME>` - 已生成代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="55fc3-666">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="55fc3-667">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-667">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="55fc3-668">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="55fc3-668">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="55fc3-669">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="55fc3-669">**viewimports**</span></span>

<span data-ttu-id="55fc3-670">`-na|--namespace <NAMESPACE_NAME>` - 已生成代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="55fc3-670">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="55fc3-671">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-671">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="55fc3-672">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="55fc3-672">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="55fc3-673">**console、angular、react、reactredux**</span><span class="sxs-lookup"><span data-stu-id="55fc3-673">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="55fc3-674">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-674">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-675">**classlib**</span><span class="sxs-lookup"><span data-stu-id="55fc3-675">**classlib**</span></span>

<span data-ttu-id="55fc3-676">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="55fc3-676">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="55fc3-677">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="55fc3-677">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="55fc3-678">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-678">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="55fc3-679">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-679">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-680">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="55fc3-680">**mstest, xunit**</span></span>

<span data-ttu-id="55fc3-681">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="55fc3-681">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="55fc3-682">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-682">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-683">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="55fc3-683">**globaljson**</span></span>

<span data-ttu-id="55fc3-684">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json  文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="55fc3-684">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="55fc3-685">**web**</span><span class="sxs-lookup"><span data-stu-id="55fc3-685">**web**</span></span>

<span data-ttu-id="55fc3-686">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="55fc3-686">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="55fc3-687">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-687">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-688">**webapi**</span><span class="sxs-lookup"><span data-stu-id="55fc3-688">**webapi**</span></span>

<span data-ttu-id="55fc3-689">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="55fc3-689">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="55fc3-690">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="55fc3-690">The possible values are:</span></span>

- <span data-ttu-id="55fc3-691">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="55fc3-691">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="55fc3-692">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-692">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="55fc3-693">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-693">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="55fc3-694">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-694">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="55fc3-695">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="55fc3-695">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="55fc3-696">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-696">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="55fc3-697">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-697">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="55fc3-698">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-698">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="55fc3-699">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-699">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-700">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="55fc3-700">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="55fc3-701">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-701">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="55fc3-702">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-702">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="55fc3-703">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-703">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="55fc3-704">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-704">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="55fc3-705">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-705">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="55fc3-706">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="55fc3-706">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="55fc3-707">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-707">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="55fc3-708">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-708">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="55fc3-709">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-709">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="55fc3-710">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-710">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="55fc3-711">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-711">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="55fc3-712">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="55fc3-712">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="55fc3-713">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-713">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="55fc3-714">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="55fc3-714">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="55fc3-715">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="55fc3-715">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="55fc3-716">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-716">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-717">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-717">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-718">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="55fc3-718">**mvc, razor**</span></span>

<span data-ttu-id="55fc3-719">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="55fc3-719">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="55fc3-720">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="55fc3-720">The possible values are:</span></span>

- <span data-ttu-id="55fc3-721">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="55fc3-721">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="55fc3-722">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-722">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="55fc3-723">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-723">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="55fc3-724">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-724">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="55fc3-725">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-725">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="55fc3-726">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-726">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="55fc3-727">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="55fc3-727">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="55fc3-728">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-728">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="55fc3-729">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-729">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="55fc3-730">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-730">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="55fc3-731">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-731">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-732">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-732">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="55fc3-733">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-733">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-734">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-734">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="55fc3-735">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-735">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-736">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="55fc3-736">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="55fc3-737">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-737">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="55fc3-738">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-738">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="55fc3-739">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-739">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="55fc3-740">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-740">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="55fc3-741">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-741">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="55fc3-742">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="55fc3-742">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="55fc3-743">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-743">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="55fc3-744">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-744">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="55fc3-745">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="55fc3-745">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="55fc3-746">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-746">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="55fc3-747">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-747">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="55fc3-748">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="55fc3-748">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="55fc3-749">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="55fc3-749">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="55fc3-750">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-750">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="55fc3-751">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="55fc3-751">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="55fc3-752">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-752">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="55fc3-753">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="55fc3-753">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="55fc3-754">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="55fc3-754">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="55fc3-755">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="55fc3-755">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="55fc3-756">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55fc3-756">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="55fc3-757">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="55fc3-757">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="55fc3-758">**page**</span><span class="sxs-lookup"><span data-stu-id="55fc3-758">**page**</span></span>

<span data-ttu-id="55fc3-759">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="55fc3-759">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="55fc3-760">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-760">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="55fc3-761">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="55fc3-761">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="55fc3-762">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="55fc3-762">**viewimports**</span></span>

<span data-ttu-id="55fc3-763">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="55fc3-763">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="55fc3-764">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-764">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="55fc3-765">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="55fc3-765">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="55fc3-766">**console、xunit、mstest、web、webapi**</span><span class="sxs-lookup"><span data-stu-id="55fc3-766">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="55fc3-767">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="55fc3-767">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="55fc3-768">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-768">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="55fc3-769">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-769">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="55fc3-770">**classlib**</span><span class="sxs-lookup"><span data-stu-id="55fc3-770">**classlib**</span></span>

<span data-ttu-id="55fc3-771">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="55fc3-771">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="55fc3-772">值：`netcoreapp1.0`、`netcoreapp1.1` 或 `netstandard1.0` 到 `netstandard1.6`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-772">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="55fc3-773">默认值为 `netstandard1.4`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-773">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="55fc3-774">**mvc**</span><span class="sxs-lookup"><span data-stu-id="55fc3-774">**mvc**</span></span>

<span data-ttu-id="55fc3-775">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="55fc3-775">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="55fc3-776">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-776">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="55fc3-777">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-777">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="55fc3-778">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="55fc3-778">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="55fc3-779">值：`None` 或 `Individual`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-779">Values: `None` or `Individual`.</span></span> <span data-ttu-id="55fc3-780">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-780">The default value is `None`.</span></span>

<span data-ttu-id="55fc3-781">`-uld|--use-local-db` - 指定是否使用 LocalDB，而不是 SQLite。</span><span class="sxs-lookup"><span data-stu-id="55fc3-781">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="55fc3-782">值：`true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-782">Values: `true` or `false`.</span></span> <span data-ttu-id="55fc3-783">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="55fc3-783">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="55fc3-784">示例</span><span class="sxs-lookup"><span data-stu-id="55fc3-784">Examples</span></span>

<span data-ttu-id="55fc3-785">通过指定模板名称，创建 C# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="55fc3-785">Create a C# console application project by specifying the template name:</span></span>

`dotnet new "Console Application"`

<span data-ttu-id="55fc3-786">在当前目录中创建 F# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="55fc3-786">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="55fc3-787">在指定目录中创建 .NET Standard 类库项目（仅适用于 .NET Core SDK 2.0 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="55fc3-787">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="55fc3-788">在当前目录中新建没有设置身份验证的 ASP.NET Core C# MVC 项目：</span><span class="sxs-lookup"><span data-stu-id="55fc3-788">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="55fc3-789">创建新的 xUnit 项目：</span><span class="sxs-lookup"><span data-stu-id="55fc3-789">Create a new xUnit project:</span></span>

`dotnet new xunit`

<span data-ttu-id="55fc3-790">列出适用于 MVC 的所有模板：</span><span class="sxs-lookup"><span data-stu-id="55fc3-790">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="55fc3-791">列出与“we”子字符串匹配的所有模板  。</span><span class="sxs-lookup"><span data-stu-id="55fc3-791">List all templates matching the *we* substring.</span></span> <span data-ttu-id="55fc3-792">找不到完全匹配，因此子字符串匹配针对短名称和名称列运行。</span><span class="sxs-lookup"><span data-stu-id="55fc3-792">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

`dotnet new we -l`

<span data-ttu-id="55fc3-793">尝试调用与 ng 匹配的模板  。</span><span class="sxs-lookup"><span data-stu-id="55fc3-793">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="55fc3-794">如果无法确定单个匹配项，请列出部分匹配项的模板。</span><span class="sxs-lookup"><span data-stu-id="55fc3-794">If a single match can't be determined, list the templates that are partial matches.</span></span>

`dotnet new ng`

<span data-ttu-id="55fc3-795">安装适用于 ASP.NET Core 的单页应用程序模板 2.0 版（命令选项仅可用于 .NET Core SDK 1.1 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="55fc3-795">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="55fc3-796">在当前目录中创建 global.json，将 SDK 版本设为 2.0.0（仅适用于 .NET Core SDK 2.0 或更高版本）  ：</span><span class="sxs-lookup"><span data-stu-id="55fc3-796">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="55fc3-797">请参阅</span><span class="sxs-lookup"><span data-stu-id="55fc3-797">See also</span></span>

- [<span data-ttu-id="55fc3-798">dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="55fc3-798">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="55fc3-799">创建 dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="55fc3-799">Create a custom template for dotnet new</span></span>](../tutorials/create-custom-template.md)
- [<span data-ttu-id="55fc3-800">dotnet/dotnet-template-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="55fc3-800">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="55fc3-801">dotnet new 可用模板</span><span class="sxs-lookup"><span data-stu-id="55fc3-801">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
