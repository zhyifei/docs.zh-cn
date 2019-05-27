---
title: dotnet new 命令
description: dotnet new 命令可根据指定模板新建 .NET Core 项目。
ms.date: 05/06/2019
ms.openlocfilehash: f8bc8cb59ae6e421f4e9bd05925376399939056d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65878319"
---
# <a name="dotnet-new"></a><span data-ttu-id="3f27e-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="3f27e-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="3f27e-104">name</span><span class="sxs-lookup"><span data-stu-id="3f27e-104">Name</span></span>

<span data-ttu-id="3f27e-105">`dotnet new` - 根据指定的模板，创建新的项目、配置文件或解决方案。</span><span class="sxs-lookup"><span data-stu-id="3f27e-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3f27e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="3f27e-106">Synopsis</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="3f27e-107">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="3f27e-107">.NET Core 2.2</span></span>](#tab/netcore22)

```console
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="3f27e-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3f27e-108">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="3f27e-109">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3f27e-109">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3f27e-110">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3f27e-110">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="3f27e-111">说明</span><span class="sxs-lookup"><span data-stu-id="3f27e-111">Description</span></span>

<span data-ttu-id="3f27e-112">`dotnet new` 命令为初始化有效的 .NET Core 项目提供了便捷方法。</span><span class="sxs-lookup"><span data-stu-id="3f27e-112">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="3f27e-113">命令调用[模板引擎](https://github.com/dotnet/templating)，以根据指定的模板和选项在磁盘上创建项目。</span><span class="sxs-lookup"><span data-stu-id="3f27e-113">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="3f27e-114">自变量</span><span class="sxs-lookup"><span data-stu-id="3f27e-114">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="3f27e-115">调用命令时要实例化的模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-115">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="3f27e-116">每个模板可能具有可传递的特定选项。</span><span class="sxs-lookup"><span data-stu-id="3f27e-116">Each template might have specific options you can pass.</span></span> <span data-ttu-id="3f27e-117">有关详细信息，请参阅[模板选项](#template-options)。</span><span class="sxs-lookup"><span data-stu-id="3f27e-117">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="3f27e-118">如果 `TEMPLATE` 值与“模板”或“短名称”列中的文本不完全匹配，则会对这两列执行 substring 匹配。</span><span class="sxs-lookup"><span data-stu-id="3f27e-118">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column, a substring match is performed on those two columns.</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="3f27e-119">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="3f27e-119">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="3f27e-120">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="3f27e-120">The command contains a default list of templates.</span></span> <span data-ttu-id="3f27e-121">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="3f27e-121">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="3f27e-122">下表显示了随 .NET Core SDK 2.2.100 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-122">The following table shows the templates that come pre-installed with the .NET Core SDK 2.2.100.</span></span> <span data-ttu-id="3f27e-123">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="3f27e-123">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="3f27e-124">模板</span><span class="sxs-lookup"><span data-stu-id="3f27e-124">Templates</span></span>                                    | <span data-ttu-id="3f27e-125">短名称</span><span class="sxs-lookup"><span data-stu-id="3f27e-125">Short Name</span></span>        | <span data-ttu-id="3f27e-126">语言</span><span class="sxs-lookup"><span data-stu-id="3f27e-126">Language</span></span>     | <span data-ttu-id="3f27e-127">Tags</span><span class="sxs-lookup"><span data-stu-id="3f27e-127">Tags</span></span>                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| <span data-ttu-id="3f27e-128">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="3f27e-128">Console Application</span></span>                          | `console`         | <span data-ttu-id="3f27e-129">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="3f27e-129">[C#], F#, VB</span></span> | <span data-ttu-id="3f27e-130">常用/控制台</span><span class="sxs-lookup"><span data-stu-id="3f27e-130">Common/Console</span></span>                        |
| <span data-ttu-id="3f27e-131">类库</span><span class="sxs-lookup"><span data-stu-id="3f27e-131">Class library</span></span>                                | `classlib`        | <span data-ttu-id="3f27e-132">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="3f27e-132">[C#], F#, VB</span></span> | <span data-ttu-id="3f27e-133">常用/库</span><span class="sxs-lookup"><span data-stu-id="3f27e-133">Common/Library</span></span>                        |
| <span data-ttu-id="3f27e-134">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="3f27e-134">Unit Test Project</span></span>                            | `mstest`          | <span data-ttu-id="3f27e-135">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="3f27e-135">[C#], F#, VB</span></span> | <span data-ttu-id="3f27e-136">测试/MSTest</span><span class="sxs-lookup"><span data-stu-id="3f27e-136">Test/MSTest</span></span>                           |
| <span data-ttu-id="3f27e-137">NUnit 3 测试项目</span><span class="sxs-lookup"><span data-stu-id="3f27e-137">NUnit 3 Test Project</span></span>                         | `nunit`           | <span data-ttu-id="3f27e-138">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="3f27e-138">[C#], F#, VB</span></span> | <span data-ttu-id="3f27e-139">测试/NUnit</span><span class="sxs-lookup"><span data-stu-id="3f27e-139">Test/NUnit</span></span>                            |
| <span data-ttu-id="3f27e-140">NUnit 3 测试项</span><span class="sxs-lookup"><span data-stu-id="3f27e-140">NUnit 3 Test Item</span></span>                            | `nunit-test`      | <span data-ttu-id="3f27e-141">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="3f27e-141">[C#], F#, VB</span></span> | <span data-ttu-id="3f27e-142">测试/NUnit</span><span class="sxs-lookup"><span data-stu-id="3f27e-142">Test/NUnit</span></span>                            |
| <span data-ttu-id="3f27e-143">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="3f27e-143">xUnit Test Project</span></span>                           | `xunit`           | <span data-ttu-id="3f27e-144">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="3f27e-144">[C#], F#, VB</span></span> | <span data-ttu-id="3f27e-145">测试/xUnit</span><span class="sxs-lookup"><span data-stu-id="3f27e-145">Test/xUnit</span></span>                            |
| <span data-ttu-id="3f27e-146">Razor 页</span><span class="sxs-lookup"><span data-stu-id="3f27e-146">Razor Page</span></span>                                   | `page`            | <span data-ttu-id="3f27e-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-147">[C#]</span></span>         | <span data-ttu-id="3f27e-148">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3f27e-148">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="3f27e-149">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="3f27e-149">MVC ViewImports</span></span>                              | `viewimports`     | <span data-ttu-id="3f27e-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-150">[C#]</span></span>         | <span data-ttu-id="3f27e-151">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3f27e-151">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="3f27e-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="3f27e-152">MVC ViewStart</span></span>                                | `viewstart`       | <span data-ttu-id="3f27e-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-153">[C#]</span></span>         | <span data-ttu-id="3f27e-154">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3f27e-154">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="3f27e-155">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="3f27e-155">ASP.NET Core Empty</span></span>                           | `web`             | <span data-ttu-id="3f27e-156">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="3f27e-156">[C#], F#</span></span>     | <span data-ttu-id="3f27e-157">Web/空</span><span class="sxs-lookup"><span data-stu-id="3f27e-157">Web/Empty</span></span>                             |
| <span data-ttu-id="3f27e-158">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="3f27e-158">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`             | <span data-ttu-id="3f27e-159">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="3f27e-159">[C#], F#</span></span>     | <span data-ttu-id="3f27e-160">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="3f27e-160">Web/MVC</span></span>                               |
| <span data-ttu-id="3f27e-161">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="3f27e-161">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="3f27e-162">`webapp`， `razor`</span><span class="sxs-lookup"><span data-stu-id="3f27e-162">`webapp`, `razor`</span></span> | <span data-ttu-id="3f27e-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-163">[C#]</span></span>         | <span data-ttu-id="3f27e-164">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="3f27e-164">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="3f27e-165">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3f27e-165">ASP.NET Core with Angular</span></span>                    | `angular`         | <span data-ttu-id="3f27e-166">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-166">[C#]</span></span>         | <span data-ttu-id="3f27e-167">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="3f27e-167">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="3f27e-168">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3f27e-168">ASP.NET Core with React.js</span></span>                   | `react`           | <span data-ttu-id="3f27e-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-169">[C#]</span></span>         | <span data-ttu-id="3f27e-170">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="3f27e-170">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="3f27e-171">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3f27e-171">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`      | <span data-ttu-id="3f27e-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-172">[C#]</span></span>         | <span data-ttu-id="3f27e-173">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="3f27e-173">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="3f27e-174">Razor 类库</span><span class="sxs-lookup"><span data-stu-id="3f27e-174">Razor Class Library</span></span>                          | `razorclasslib`   | <span data-ttu-id="3f27e-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-175">[C#]</span></span>         | <span data-ttu-id="3f27e-176">Web/Razor/库/Razor 类库</span><span class="sxs-lookup"><span data-stu-id="3f27e-176">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="3f27e-177">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="3f27e-177">ASP.NET Core Web API</span></span>                         | `webapi`          | <span data-ttu-id="3f27e-178">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="3f27e-178">[C#], F#</span></span>     | <span data-ttu-id="3f27e-179">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="3f27e-179">Web/WebAPI</span></span>                            |
| <span data-ttu-id="3f27e-180">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="3f27e-180">global.json file</span></span>                             | `globaljson`      |              | <span data-ttu-id="3f27e-181">配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-181">Config</span></span>                                |
| <span data-ttu-id="3f27e-182">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-182">NuGet Config</span></span>                                 | `nugetconfig`     |              | <span data-ttu-id="3f27e-183">配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-183">Config</span></span>                                |
| <span data-ttu-id="3f27e-184">Web 配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-184">Web Config</span></span>                                   | `webconfig`       |              | <span data-ttu-id="3f27e-185">配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-185">Config</span></span>                                |
| <span data-ttu-id="3f27e-186">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="3f27e-186">Solution File</span></span>                                | `sln`             |              | <span data-ttu-id="3f27e-187">解决方案</span><span class="sxs-lookup"><span data-stu-id="3f27e-187">Solution</span></span>                              |

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="3f27e-188">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3f27e-188">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="3f27e-189">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="3f27e-189">The command contains a default list of templates.</span></span> <span data-ttu-id="3f27e-190">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="3f27e-190">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="3f27e-191">下表列出了随 .NET Core SDK 2.1.300 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-191">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="3f27e-192">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="3f27e-192">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="3f27e-193">模板</span><span class="sxs-lookup"><span data-stu-id="3f27e-193">Templates</span></span>                                    | <span data-ttu-id="3f27e-194">短名称</span><span class="sxs-lookup"><span data-stu-id="3f27e-194">Short Name</span></span>      | <span data-ttu-id="3f27e-195">语言</span><span class="sxs-lookup"><span data-stu-id="3f27e-195">Language</span></span>     | <span data-ttu-id="3f27e-196">Tags</span><span class="sxs-lookup"><span data-stu-id="3f27e-196">Tags</span></span>                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| <span data-ttu-id="3f27e-197">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="3f27e-197">Console Application</span></span>                          | `console`       | <span data-ttu-id="3f27e-198">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="3f27e-198">[C#], F#, VB</span></span> | <span data-ttu-id="3f27e-199">常用/控制台</span><span class="sxs-lookup"><span data-stu-id="3f27e-199">Common/Console</span></span>                        |
| <span data-ttu-id="3f27e-200">类库</span><span class="sxs-lookup"><span data-stu-id="3f27e-200">Class library</span></span>                                | `classlib`      | <span data-ttu-id="3f27e-201">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="3f27e-201">[C#], F#, VB</span></span> | <span data-ttu-id="3f27e-202">常用/库</span><span class="sxs-lookup"><span data-stu-id="3f27e-202">Common/Library</span></span>                        |
| <span data-ttu-id="3f27e-203">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="3f27e-203">Unit Test Project</span></span>                            | `mstest`        | <span data-ttu-id="3f27e-204">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="3f27e-204">[C#], F#, VB</span></span> | <span data-ttu-id="3f27e-205">测试/MSTest</span><span class="sxs-lookup"><span data-stu-id="3f27e-205">Test/MSTest</span></span>                           |
| <span data-ttu-id="3f27e-206">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="3f27e-206">xUnit Test Project</span></span>                           | `xunit`         | <span data-ttu-id="3f27e-207">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="3f27e-207">[C#], F#, VB</span></span> | <span data-ttu-id="3f27e-208">测试/xUnit</span><span class="sxs-lookup"><span data-stu-id="3f27e-208">Test/xUnit</span></span>                            |
| <span data-ttu-id="3f27e-209">Razor 页</span><span class="sxs-lookup"><span data-stu-id="3f27e-209">Razor Page</span></span>                                   | `page`          | <span data-ttu-id="3f27e-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-210">[C#]</span></span>         | <span data-ttu-id="3f27e-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3f27e-211">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="3f27e-212">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="3f27e-212">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="3f27e-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-213">[C#]</span></span>         | <span data-ttu-id="3f27e-214">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3f27e-214">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="3f27e-215">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="3f27e-215">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="3f27e-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-216">[C#]</span></span>         | <span data-ttu-id="3f27e-217">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3f27e-217">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="3f27e-218">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="3f27e-218">ASP.NET Core Empty</span></span>                           | `web`           | <span data-ttu-id="3f27e-219">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="3f27e-219">[C#], F#</span></span>     | <span data-ttu-id="3f27e-220">Web/空</span><span class="sxs-lookup"><span data-stu-id="3f27e-220">Web/Empty</span></span>                             |
| <span data-ttu-id="3f27e-221">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="3f27e-221">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="3f27e-222">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="3f27e-222">[C#], F#</span></span>     | <span data-ttu-id="3f27e-223">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="3f27e-223">Web/MVC</span></span>                               |
| <span data-ttu-id="3f27e-224">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="3f27e-224">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="3f27e-225">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-225">[C#]</span></span>         | <span data-ttu-id="3f27e-226">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="3f27e-226">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="3f27e-227">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3f27e-227">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="3f27e-228">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-228">[C#]</span></span>         | <span data-ttu-id="3f27e-229">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="3f27e-229">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="3f27e-230">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3f27e-230">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="3f27e-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-231">[C#]</span></span>         | <span data-ttu-id="3f27e-232">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="3f27e-232">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="3f27e-233">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3f27e-233">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="3f27e-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-234">[C#]</span></span>         | <span data-ttu-id="3f27e-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="3f27e-235">Web/MVC/SPA</span></span>                           | 
| <span data-ttu-id="3f27e-236">Razor 类库</span><span class="sxs-lookup"><span data-stu-id="3f27e-236">Razor Class Library</span></span>                          | `razorclasslib` | <span data-ttu-id="3f27e-237">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-237">[C#]</span></span>         | <span data-ttu-id="3f27e-238">Web/Razor/库/Razor 类库</span><span class="sxs-lookup"><span data-stu-id="3f27e-238">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="3f27e-239">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="3f27e-239">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="3f27e-240">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="3f27e-240">[C#], F#</span></span>     | <span data-ttu-id="3f27e-241">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="3f27e-241">Web/WebAPI</span></span>                            |
| <span data-ttu-id="3f27e-242">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="3f27e-242">global.json file</span></span>                             | `globaljson`    |              | <span data-ttu-id="3f27e-243">配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-243">Config</span></span>                                |
| <span data-ttu-id="3f27e-244">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-244">NuGet Config</span></span>                                 | `nugetconfig`   |              | <span data-ttu-id="3f27e-245">配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-245">Config</span></span>                                |
| <span data-ttu-id="3f27e-246">Web 配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-246">Web Config</span></span>                                   | `webconfig`     |              | <span data-ttu-id="3f27e-247">配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-247">Config</span></span>                                |
| <span data-ttu-id="3f27e-248">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="3f27e-248">Solution File</span></span>                                | `sln`           |              | <span data-ttu-id="3f27e-249">解决方案</span><span class="sxs-lookup"><span data-stu-id="3f27e-249">Solution</span></span>                              |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="3f27e-250">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3f27e-250">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="3f27e-251">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="3f27e-251">The command contains a default list of templates.</span></span> <span data-ttu-id="3f27e-252">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="3f27e-252">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="3f27e-253">下表显示了随 .NET Core SDK 2.0.0 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-253">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.0.</span></span> <span data-ttu-id="3f27e-254">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="3f27e-254">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="3f27e-255">模板</span><span class="sxs-lookup"><span data-stu-id="3f27e-255">Templates</span></span>                                    | <span data-ttu-id="3f27e-256">短名称</span><span class="sxs-lookup"><span data-stu-id="3f27e-256">Short Name</span></span>    | <span data-ttu-id="3f27e-257">语言</span><span class="sxs-lookup"><span data-stu-id="3f27e-257">Language</span></span>     | <span data-ttu-id="3f27e-258">Tags</span><span class="sxs-lookup"><span data-stu-id="3f27e-258">Tags</span></span>                |
|----------------------------------------------|---------------|--------------|---------------------|
| <span data-ttu-id="3f27e-259">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="3f27e-259">Console Application</span></span>                          | `console`     | <span data-ttu-id="3f27e-260">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="3f27e-260">[C#], F#, VB</span></span> | <span data-ttu-id="3f27e-261">常用/控制台</span><span class="sxs-lookup"><span data-stu-id="3f27e-261">Common/Console</span></span>      |
| <span data-ttu-id="3f27e-262">类库</span><span class="sxs-lookup"><span data-stu-id="3f27e-262">Class library</span></span>                                | `classlib`    | <span data-ttu-id="3f27e-263">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="3f27e-263">[C#], F#, VB</span></span> | <span data-ttu-id="3f27e-264">常用/库</span><span class="sxs-lookup"><span data-stu-id="3f27e-264">Common/Library</span></span>      |
| <span data-ttu-id="3f27e-265">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="3f27e-265">Unit Test Project</span></span>                            | `mstest`      | <span data-ttu-id="3f27e-266">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="3f27e-266">[C#], F#, VB</span></span> | <span data-ttu-id="3f27e-267">测试/MSTest</span><span class="sxs-lookup"><span data-stu-id="3f27e-267">Test/MSTest</span></span>         |
| <span data-ttu-id="3f27e-268">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="3f27e-268">xUnit Test Project</span></span>                           | `xunit`       | <span data-ttu-id="3f27e-269">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="3f27e-269">[C#], F#, VB</span></span> | <span data-ttu-id="3f27e-270">测试/xUnit</span><span class="sxs-lookup"><span data-stu-id="3f27e-270">Test/xUnit</span></span>          |
| <span data-ttu-id="3f27e-271">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="3f27e-271">ASP.NET Core Empty</span></span>                           | `web`         | <span data-ttu-id="3f27e-272">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="3f27e-272">[C#], F#</span></span>     | <span data-ttu-id="3f27e-273">Web/空</span><span class="sxs-lookup"><span data-stu-id="3f27e-273">Web/Empty</span></span>           |
| <span data-ttu-id="3f27e-274">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="3f27e-274">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="3f27e-275">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="3f27e-275">[C#], F#</span></span>     | <span data-ttu-id="3f27e-276">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="3f27e-276">Web/MVC</span></span>             |
| <span data-ttu-id="3f27e-277">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="3f27e-277">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="3f27e-278">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-278">[C#]</span></span>         | <span data-ttu-id="3f27e-279">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="3f27e-279">Web/MVC/Razor Pages</span></span> |
| <span data-ttu-id="3f27e-280">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3f27e-280">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="3f27e-281">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-281">[C#]</span></span>         | <span data-ttu-id="3f27e-282">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="3f27e-282">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="3f27e-283">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3f27e-283">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="3f27e-284">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-284">[C#]</span></span>         | <span data-ttu-id="3f27e-285">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="3f27e-285">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="3f27e-286">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3f27e-286">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="3f27e-287">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-287">[C#]</span></span>         | <span data-ttu-id="3f27e-288">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="3f27e-288">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="3f27e-289">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="3f27e-289">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="3f27e-290">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="3f27e-290">[C#], F#</span></span>     | <span data-ttu-id="3f27e-291">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="3f27e-291">Web/WebAPI</span></span>          |
| <span data-ttu-id="3f27e-292">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="3f27e-292">global.json file</span></span>                             | `globaljson`  |              | <span data-ttu-id="3f27e-293">配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-293">Config</span></span>              |
| <span data-ttu-id="3f27e-294">Nuget 配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-294">Nuget Config</span></span>                                 | `nugetconfig` |              | <span data-ttu-id="3f27e-295">配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-295">Config</span></span>              |
| <span data-ttu-id="3f27e-296">Web 配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-296">Web Config</span></span>                                   | `webconfig`   |              | <span data-ttu-id="3f27e-297">配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-297">Config</span></span>              |
| <span data-ttu-id="3f27e-298">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="3f27e-298">Solution File</span></span>                                | `sln`         |              | <span data-ttu-id="3f27e-299">解决方案</span><span class="sxs-lookup"><span data-stu-id="3f27e-299">Solution</span></span>            |
| <span data-ttu-id="3f27e-300">Razor 页</span><span class="sxs-lookup"><span data-stu-id="3f27e-300">Razor Page</span></span>                                   | `page`        |              | <span data-ttu-id="3f27e-301">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3f27e-301">Web/ASP.NET</span></span>         |
| <span data-ttu-id="3f27e-302">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="3f27e-302">MVC ViewImports</span></span>                              | `viewimports` |              | <span data-ttu-id="3f27e-303">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3f27e-303">Web/ASP.NET</span></span>         |
| <span data-ttu-id="3f27e-304">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="3f27e-304">MVC ViewStart</span></span>                                | `viewstart`   |              | <span data-ttu-id="3f27e-305">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3f27e-305">Web/ASP.NET</span></span>         |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3f27e-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3f27e-306">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="3f27e-307">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="3f27e-307">The command contains a default list of templates.</span></span> <span data-ttu-id="3f27e-308">使用 `dotnet new -all` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="3f27e-308">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="3f27e-309">下表显示了随 .NET Core SDK 1.0.1 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-309">The following table shows the templates that come pre-installed with the .NET Core SDK 1.0.1.</span></span> <span data-ttu-id="3f27e-310">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="3f27e-310">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="3f27e-311">模板</span><span class="sxs-lookup"><span data-stu-id="3f27e-311">Templates</span></span>            | <span data-ttu-id="3f27e-312">短名称</span><span class="sxs-lookup"><span data-stu-id="3f27e-312">Short Name</span></span>    | <span data-ttu-id="3f27e-313">语言</span><span class="sxs-lookup"><span data-stu-id="3f27e-313">Language</span></span> | <span data-ttu-id="3f27e-314">Tags</span><span class="sxs-lookup"><span data-stu-id="3f27e-314">Tags</span></span>           |
|----------------------|---------------|----------|----------------|
| <span data-ttu-id="3f27e-315">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="3f27e-315">Console Application</span></span>  | `console`     | <span data-ttu-id="3f27e-316">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="3f27e-316">[C#], F#</span></span> | <span data-ttu-id="3f27e-317">常用/控制台</span><span class="sxs-lookup"><span data-stu-id="3f27e-317">Common/Console</span></span> |
| <span data-ttu-id="3f27e-318">类库</span><span class="sxs-lookup"><span data-stu-id="3f27e-318">Class library</span></span>        | `classlib`    | <span data-ttu-id="3f27e-319">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="3f27e-319">[C#], F#</span></span> | <span data-ttu-id="3f27e-320">常用/库</span><span class="sxs-lookup"><span data-stu-id="3f27e-320">Common/Library</span></span> |
| <span data-ttu-id="3f27e-321">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="3f27e-321">Unit Test Project</span></span>    | `mstest`      | <span data-ttu-id="3f27e-322">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="3f27e-322">[C#], F#</span></span> | <span data-ttu-id="3f27e-323">测试/MSTest</span><span class="sxs-lookup"><span data-stu-id="3f27e-323">Test/MSTest</span></span>    |
| <span data-ttu-id="3f27e-324">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="3f27e-324">xUnit Test Project</span></span>   | `xunit`       | <span data-ttu-id="3f27e-325">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="3f27e-325">[C#], F#</span></span> | <span data-ttu-id="3f27e-326">测试/xUnit</span><span class="sxs-lookup"><span data-stu-id="3f27e-326">Test/xUnit</span></span>     |
| <span data-ttu-id="3f27e-327">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="3f27e-327">ASP.NET Core Empty</span></span>   | `web`         | <span data-ttu-id="3f27e-328">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-328">[C#]</span></span>     | <span data-ttu-id="3f27e-329">Web/空</span><span class="sxs-lookup"><span data-stu-id="3f27e-329">Web/Empty</span></span>      |
| <span data-ttu-id="3f27e-330">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="3f27e-330">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="3f27e-331">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="3f27e-331">[C#], F#</span></span> | <span data-ttu-id="3f27e-332">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="3f27e-332">Web/MVC</span></span>        |
| <span data-ttu-id="3f27e-333">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="3f27e-333">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="3f27e-334">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f27e-334">[C#]</span></span>     | <span data-ttu-id="3f27e-335">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="3f27e-335">Web/WebAPI</span></span>     |
| <span data-ttu-id="3f27e-336">Nuget 配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-336">Nuget Config</span></span>         | `nugetconfig` |          | <span data-ttu-id="3f27e-337">配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-337">Config</span></span>         |
| <span data-ttu-id="3f27e-338">Web 配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-338">Web Config</span></span>           | `webconfig`   |          | <span data-ttu-id="3f27e-339">配置</span><span class="sxs-lookup"><span data-stu-id="3f27e-339">Config</span></span>         |
| <span data-ttu-id="3f27e-340">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="3f27e-340">Solution File</span></span>        | `sln`         |          | <span data-ttu-id="3f27e-341">解决方案</span><span class="sxs-lookup"><span data-stu-id="3f27e-341">Solution</span></span>       |

---

## <a name="options"></a><span data-ttu-id="3f27e-342">选项</span><span class="sxs-lookup"><span data-stu-id="3f27e-342">Options</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="3f27e-343">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="3f27e-343">.NET Core 2.2</span></span>](#tab/netcore22)

`--dry-run`

<span data-ttu-id="3f27e-344">显示有关以下内容的摘要：给定命令运行导致模板创建时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="3f27e-344">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span>

`--force`

<span data-ttu-id="3f27e-345">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="3f27e-345">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="3f27e-346">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="3f27e-346">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="3f27e-347">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="3f27e-347">Prints out help for the command.</span></span> <span data-ttu-id="3f27e-348">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="3f27e-348">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="3f27e-349">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="3f27e-349">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="3f27e-350">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="3f27e-350">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="3f27e-351">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="3f27e-351">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="3f27e-352">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="3f27e-352">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="3f27e-353">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="3f27e-353">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="3f27e-354">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-354">Lists templates containing the specified name.</span></span> <span data-ttu-id="3f27e-355">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-355">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="3f27e-356">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-356">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="3f27e-357">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="3f27e-357">The language of the template to create.</span></span> <span data-ttu-id="3f27e-358">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="3f27e-358">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="3f27e-359">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="3f27e-359">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="3f27e-360">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="3f27e-360">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="3f27e-361">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-361">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="3f27e-362">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="3f27e-362">The name for the created output.</span></span> <span data-ttu-id="3f27e-363">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="3f27e-363">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="3f27e-364">指定在安装期间要使用的 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="3f27e-364">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="3f27e-365">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="3f27e-365">Location to place the generated output.</span></span> <span data-ttu-id="3f27e-366">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="3f27e-366">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="3f27e-367">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-367">Filters templates based on available types.</span></span> <span data-ttu-id="3f27e-368">预定义的值为“项目”、“项”或“其他”。</span><span class="sxs-lookup"><span data-stu-id="3f27e-368">Predefined values are "project", "item", or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="3f27e-369">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="3f27e-369">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="3f27e-370">如果排除 `<PATH|NUGET_ID>` 值，将显示所有当前安装的模板包及其关联的模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-370">When excluding the `<PATH|NUGET_ID>` value, all currently installed template packs and their associated templates are displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="3f27e-371">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="3f27e-371">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="3f27e-372">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="3f27e-372">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="3f27e-373">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="3f27e-373">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="3f27e-374">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3f27e-374">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="3f27e-375">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="3f27e-375">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="3f27e-376">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="3f27e-376">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="3f27e-377">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="3f27e-377">Prints out help for the command.</span></span> <span data-ttu-id="3f27e-378">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="3f27e-378">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="3f27e-379">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="3f27e-379">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="3f27e-380">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="3f27e-380">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="3f27e-381">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="3f27e-381">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="3f27e-382">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="3f27e-382">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="3f27e-383">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="3f27e-383">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="3f27e-384">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-384">Lists templates containing the specified name.</span></span> <span data-ttu-id="3f27e-385">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-385">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="3f27e-386">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-386">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="3f27e-387">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="3f27e-387">The language of the template to create.</span></span> <span data-ttu-id="3f27e-388">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="3f27e-388">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="3f27e-389">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="3f27e-389">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="3f27e-390">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="3f27e-390">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="3f27e-391">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-391">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="3f27e-392">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="3f27e-392">The name for the created output.</span></span> <span data-ttu-id="3f27e-393">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="3f27e-393">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="3f27e-394">指定在安装期间要使用的 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="3f27e-394">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="3f27e-395">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="3f27e-395">Location to place the generated output.</span></span> <span data-ttu-id="3f27e-396">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="3f27e-396">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="3f27e-397">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-397">Filters templates based on available types.</span></span> <span data-ttu-id="3f27e-398">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="3f27e-398">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="3f27e-399">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="3f27e-399">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="3f27e-400">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="3f27e-400">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="3f27e-401">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="3f27e-401">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="3f27e-402">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="3f27e-402">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="3f27e-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3f27e-403">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="3f27e-404">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="3f27e-404">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="3f27e-405">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="3f27e-405">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="3f27e-406">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="3f27e-406">Prints out help for the command.</span></span> <span data-ttu-id="3f27e-407">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="3f27e-407">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="3f27e-408">从提供的 `PATH` 或 `NUGET_ID` 安装源或模板包。</span><span class="sxs-lookup"><span data-stu-id="3f27e-408">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="3f27e-409">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="3f27e-409">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="3f27e-410">默认情况下，`dotnet new` 为该版本传递 \*，表示最后一个稳定的包版本。</span><span class="sxs-lookup"><span data-stu-id="3f27e-410">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="3f27e-411">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="3f27e-411">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="3f27e-412">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="3f27e-412">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="3f27e-413">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-413">Lists templates containing the specified name.</span></span> <span data-ttu-id="3f27e-414">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-414">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="3f27e-415">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-415">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="3f27e-416">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="3f27e-416">The language of the template to create.</span></span> <span data-ttu-id="3f27e-417">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="3f27e-417">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="3f27e-418">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="3f27e-418">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="3f27e-419">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="3f27e-419">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="3f27e-420">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-420">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="3f27e-421">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="3f27e-421">The name for the created output.</span></span> <span data-ttu-id="3f27e-422">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="3f27e-422">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="3f27e-423">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="3f27e-423">Location to place the generated output.</span></span> <span data-ttu-id="3f27e-424">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="3f27e-424">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="3f27e-425">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-425">Filters templates based on available types.</span></span> <span data-ttu-id="3f27e-426">预定义值为“project”、“item”或“other”。</span><span class="sxs-lookup"><span data-stu-id="3f27e-426">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="3f27e-427">从提供的 `PATH` 或 `NUGET_ID` 卸载源或模板包。</span><span class="sxs-lookup"><span data-stu-id="3f27e-427">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="3f27e-428">若要使用源 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="3f27e-428">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="3f27e-429">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="3f27e-429">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="3f27e-430">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="3f27e-430">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="3f27e-431">如果无法确定卸载模板所需的 `PATH` 或 `NUGET_ID` 参数，则在没有参数的情况下运行 `dotnet new --uninstall` 将列出所有已安装的模板以及卸载它们所需的参数。</span><span class="sxs-lookup"><span data-stu-id="3f27e-431">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3f27e-432">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3f27e-432">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="3f27e-433">单独在 `dotnet new` 命令的上下文中运行时，显示特定类型的项目的所有模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-433">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="3f27e-434">在特定模板（如 `dotnet new web -all`）的上下文中运行时，`-all` 解释为一个强制创建标记。</span><span class="sxs-lookup"><span data-stu-id="3f27e-434">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="3f27e-435">输出目录已包含一个项目时，可能需要此操作。</span><span class="sxs-lookup"><span data-stu-id="3f27e-435">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="3f27e-436">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="3f27e-436">Prints out help for the command.</span></span> <span data-ttu-id="3f27e-437">可针对 `dotnet new` 命令本身或任何模板（如 `dotnet new mvc --help`）调用它。</span><span class="sxs-lookup"><span data-stu-id="3f27e-437">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="3f27e-438">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-438">Lists templates containing the specified name.</span></span> <span data-ttu-id="3f27e-439">如果针对 `dotnet new` 命令调用，则它列出可能对给定的目录可用的模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-439">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="3f27e-440">例如，如果该目录已包含一个项目，则它不会列出所有项目模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-440">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="3f27e-441">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="3f27e-441">The language of the template to create.</span></span> <span data-ttu-id="3f27e-442">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="3f27e-442">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="3f27e-443">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="3f27e-443">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="3f27e-444">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="3f27e-444">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="3f27e-445">在这些情况下，需要括住语言参数值，如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-445">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="3f27e-446">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="3f27e-446">The name for the created output.</span></span> <span data-ttu-id="3f27e-447">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="3f27e-447">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="3f27e-448">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="3f27e-448">Location to place the generated output.</span></span> <span data-ttu-id="3f27e-449">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="3f27e-449">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="3f27e-450">模板选项</span><span class="sxs-lookup"><span data-stu-id="3f27e-450">Template options</span></span>

<span data-ttu-id="3f27e-451">每个项目模板都可能有附加选项。</span><span class="sxs-lookup"><span data-stu-id="3f27e-451">Each project template may have additional options available.</span></span> <span data-ttu-id="3f27e-452">核心模板有以下附加选项：</span><span class="sxs-lookup"><span data-stu-id="3f27e-452">The core templates have the following additional options:</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="3f27e-453">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="3f27e-453">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="3f27e-454">**控制台**</span><span class="sxs-lookup"><span data-stu-id="3f27e-454">**console**</span></span>

<span data-ttu-id="3f27e-455">`--langVersion <VERSION_NUMBER>` - 在已创建的项目文件中设置 `LangVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="3f27e-455">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="3f27e-456">例如，使用 `--langVersion 7.3` 以使用 C# 7.3。</span><span class="sxs-lookup"><span data-stu-id="3f27e-456">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="3f27e-457">不支持 F#。</span><span class="sxs-lookup"><span data-stu-id="3f27e-457">Not supported for F#.</span></span>

<span data-ttu-id="3f27e-458">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-458">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-459">**angular、react、reactredux**</span><span class="sxs-lookup"><span data-stu-id="3f27e-459">**angular, react, reactredux**</span></span>

<span data-ttu-id="3f27e-460">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="3f27e-460">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="3f27e-461">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-461">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-462">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="3f27e-462">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="3f27e-463">此选项仅适用于未使用 `IndividualAuth` 或 `OrganizationalAuth` 的情况。</span><span class="sxs-lookup"><span data-stu-id="3f27e-463">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="3f27e-464">**razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="3f27e-464">**razorclasslib**</span></span>

<span data-ttu-id="3f27e-465">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-465">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-466">**classlib**</span><span class="sxs-lookup"><span data-stu-id="3f27e-466">**classlib**</span></span>

<span data-ttu-id="3f27e-467">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="3f27e-467">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3f27e-468">值：`netcoreapp2.2`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="3f27e-468">Values: `netcoreapp2.2` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="3f27e-469">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-469">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="3f27e-470">`--langVersion <VERSION_NUMBER>` - 在已创建的项目文件中设置 `LangVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="3f27e-470">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="3f27e-471">例如，使用 `--langVersion 7.3` 以使用 C# 7.3。</span><span class="sxs-lookup"><span data-stu-id="3f27e-471">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="3f27e-472">不支持 F#。</span><span class="sxs-lookup"><span data-stu-id="3f27e-472">Not supported for F#.</span></span>

<span data-ttu-id="3f27e-473">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-473">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-474">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="3f27e-474">**mstest, xunit**</span></span>

<span data-ttu-id="3f27e-475">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="3f27e-475">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="3f27e-476">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-476">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-477">**nunit**</span><span class="sxs-lookup"><span data-stu-id="3f27e-477">**nunit**</span></span>

<span data-ttu-id="3f27e-478">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="3f27e-478">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3f27e-479">默认值为 `netcoreapp2.1`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-479">The default value is `netcoreapp2.1`.</span></span>

<span data-ttu-id="3f27e-480">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="3f27e-480">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="3f27e-481">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-481">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-482">**page**</span><span class="sxs-lookup"><span data-stu-id="3f27e-482">**page**</span></span>

<span data-ttu-id="3f27e-483">`-na|--namespace <NAMESPACE_NAME>` - 已生成代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3f27e-483">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="3f27e-484">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-484">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="3f27e-485">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="3f27e-485">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="3f27e-486">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="3f27e-486">**viewimports**</span></span>

<span data-ttu-id="3f27e-487">`-na|--namespace <NAMESPACE_NAME>` - 已生成代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3f27e-487">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="3f27e-488">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-488">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="3f27e-489">**web**</span><span class="sxs-lookup"><span data-stu-id="3f27e-489">**web**</span></span>

<span data-ttu-id="3f27e-490">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="3f27e-490">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="3f27e-491">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-491">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-492">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="3f27e-492">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="3f27e-493">此选项仅适用于未使用 `IndividualAuth` 或 `OrganizationalAuth` 的情况。</span><span class="sxs-lookup"><span data-stu-id="3f27e-493">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="3f27e-494">**mvc、webapp**</span><span class="sxs-lookup"><span data-stu-id="3f27e-494">**mvc, webapp**</span></span>

<span data-ttu-id="3f27e-495">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="3f27e-495">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="3f27e-496">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="3f27e-496">The possible values are:</span></span>

- <span data-ttu-id="3f27e-497">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="3f27e-497">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="3f27e-498">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-498">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="3f27e-499">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-499">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="3f27e-500">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-500">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="3f27e-501">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-501">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="3f27e-502">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-502">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="3f27e-503">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="3f27e-503">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="3f27e-504">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-504">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="3f27e-505">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-505">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="3f27e-506">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-506">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="3f27e-507">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-507">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-508">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-508">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="3f27e-509">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-509">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-510">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-510">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="3f27e-511">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-511">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-512">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="3f27e-512">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="3f27e-513">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-513">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="3f27e-514">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-514">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="3f27e-515">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-515">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="3f27e-516">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-516">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="3f27e-517">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-517">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="3f27e-518">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="3f27e-518">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="3f27e-519">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3f27e-520">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-520">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="3f27e-521">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-521">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="3f27e-522">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-522">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3f27e-523">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-523">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="3f27e-524">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="3f27e-524">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="3f27e-525">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-525">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3f27e-526">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-526">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="3f27e-527">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="3f27e-527">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="3f27e-528">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-528">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="3f27e-529">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="3f27e-529">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="3f27e-530">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="3f27e-530">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="3f27e-531">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="3f27e-531">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="3f27e-532">此选项仅适用于未使用 `Individual`、`IndividualB2C``SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="3f27e-532">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="3f27e-533">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="3f27e-533">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3f27e-534">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-534">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-535">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-535">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-536">**webapi**</span><span class="sxs-lookup"><span data-stu-id="3f27e-536">**webapi**</span></span>

<span data-ttu-id="3f27e-537">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="3f27e-537">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="3f27e-538">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="3f27e-538">The possible values are:</span></span>

- <span data-ttu-id="3f27e-539">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="3f27e-539">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="3f27e-540">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-540">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="3f27e-541">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-541">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="3f27e-542">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-542">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="3f27e-543">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="3f27e-543">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="3f27e-544">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-544">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="3f27e-545">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-545">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="3f27e-546">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-546">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="3f27e-547">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-547">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-548">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="3f27e-548">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="3f27e-549">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-549">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3f27e-550">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-550">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="3f27e-551">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-551">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="3f27e-552">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-552">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="3f27e-553">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-553">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="3f27e-554">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="3f27e-554">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="3f27e-555">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-555">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3f27e-556">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-556">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="3f27e-557">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-557">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="3f27e-558">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3f27e-559">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-559">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="3f27e-560">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="3f27e-560">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="3f27e-561">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-561">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="3f27e-562">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="3f27e-562">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="3f27e-563">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="3f27e-563">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="3f27e-564">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="3f27e-564">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="3f27e-565">此选项仅适用于未使用 `Individual`、`IndividualB2C``SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="3f27e-565">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="3f27e-566">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="3f27e-566">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3f27e-567">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-567">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-568">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-568">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-569">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="3f27e-569">**globaljson**</span></span>

<span data-ttu-id="3f27e-570">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="3f27e-570">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="3f27e-571">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3f27e-571">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="3f27e-572">console、angular、react、reactredux、razorclasslib</span><span class="sxs-lookup"><span data-stu-id="3f27e-572">**console, angular, react, reactredux, razorclasslib**</span></span>

<span data-ttu-id="3f27e-573">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-573">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-574">**classlib**</span><span class="sxs-lookup"><span data-stu-id="3f27e-574">**classlib**</span></span>

<span data-ttu-id="3f27e-575">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="3f27e-575">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3f27e-576">值：`netcoreapp2.1`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="3f27e-576">Values: `netcoreapp2.1` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="3f27e-577">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-577">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="3f27e-578">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-578">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-579">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="3f27e-579">**mstest, xunit**</span></span>

<span data-ttu-id="3f27e-580">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="3f27e-580">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="3f27e-581">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-581">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-582">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="3f27e-582">**globaljson**</span></span>

<span data-ttu-id="3f27e-583">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="3f27e-583">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="3f27e-584">**web**</span><span class="sxs-lookup"><span data-stu-id="3f27e-584">**web**</span></span>

<span data-ttu-id="3f27e-585">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="3f27e-585">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="3f27e-586">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-586">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-587">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="3f27e-587">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="3f27e-588">此选项仅适用于未使用 `IndividualAuth` 或 `OrganizationalAuth` 的情况。</span><span class="sxs-lookup"><span data-stu-id="3f27e-588">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="3f27e-589">**webapi**</span><span class="sxs-lookup"><span data-stu-id="3f27e-589">**webapi**</span></span>

<span data-ttu-id="3f27e-590">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="3f27e-590">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="3f27e-591">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="3f27e-591">The possible values are:</span></span>

- <span data-ttu-id="3f27e-592">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="3f27e-592">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="3f27e-593">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-593">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="3f27e-594">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-594">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="3f27e-595">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-595">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="3f27e-596">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="3f27e-596">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="3f27e-597">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-597">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="3f27e-598">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-598">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="3f27e-599">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-599">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="3f27e-600">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-600">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-601">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="3f27e-601">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="3f27e-602">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-602">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3f27e-603">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-603">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="3f27e-604">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-604">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="3f27e-605">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-605">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="3f27e-606">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-606">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="3f27e-607">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="3f27e-607">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="3f27e-608">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-608">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3f27e-609">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-609">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="3f27e-610">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-610">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="3f27e-611">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-611">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3f27e-612">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-612">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="3f27e-613">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="3f27e-613">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="3f27e-614">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-614">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="3f27e-615">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="3f27e-615">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="3f27e-616">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="3f27e-616">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3f27e-617">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-617">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-618">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-618">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-619">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="3f27e-619">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="3f27e-620">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="3f27e-620">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="3f27e-621">此选项仅适用于未使用 `Individual`、`IndividualB2C``SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="3f27e-621">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="3f27e-622">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="3f27e-622">**mvc, razor**</span></span>

<span data-ttu-id="3f27e-623">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="3f27e-623">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="3f27e-624">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="3f27e-624">The possible values are:</span></span>

- <span data-ttu-id="3f27e-625">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="3f27e-625">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="3f27e-626">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-626">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="3f27e-627">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-627">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="3f27e-628">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-628">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="3f27e-629">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-629">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="3f27e-630">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-630">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="3f27e-631">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="3f27e-631">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="3f27e-632">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-632">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="3f27e-633">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-633">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="3f27e-634">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-634">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="3f27e-635">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-635">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-636">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-636">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="3f27e-637">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-637">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-638">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-638">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="3f27e-639">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-639">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-640">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="3f27e-640">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="3f27e-641">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-641">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="3f27e-642">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-642">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="3f27e-643">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-643">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="3f27e-644">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-644">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="3f27e-645">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-645">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="3f27e-646">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="3f27e-646">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="3f27e-647">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-647">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3f27e-648">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-648">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="3f27e-649">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-649">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="3f27e-650">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-650">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3f27e-651">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-651">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="3f27e-652">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="3f27e-652">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="3f27e-653">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-653">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3f27e-654">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-654">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="3f27e-655">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="3f27e-655">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="3f27e-656">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-656">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="3f27e-657">`--exclude-launch-settings` - 从生成的模板中排除 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="3f27e-657">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="3f27e-658">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="3f27e-658">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="3f27e-659">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="3f27e-659">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3f27e-660">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-660">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-661">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-661">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-662">`--no-https` - 项目不需要 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="3f27e-662">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="3f27e-663">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="3f27e-663">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="3f27e-664">此选项仅适用于未使用 `Individual`、`IndividualB2C``SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="3f27e-664">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="3f27e-665">**page**</span><span class="sxs-lookup"><span data-stu-id="3f27e-665">**page**</span></span>

<span data-ttu-id="3f27e-666">`-na|--namespace <NAMESPACE_NAME>` - 已生成代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3f27e-666">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="3f27e-667">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-667">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="3f27e-668">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="3f27e-668">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="3f27e-669">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="3f27e-669">**viewimports**</span></span>

<span data-ttu-id="3f27e-670">`-na|--namespace <NAMESPACE_NAME>` - 已生成代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3f27e-670">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="3f27e-671">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-671">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="3f27e-672">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3f27e-672">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="3f27e-673">**console、angular、react、reactredux**</span><span class="sxs-lookup"><span data-stu-id="3f27e-673">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="3f27e-674">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-674">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-675">**classlib**</span><span class="sxs-lookup"><span data-stu-id="3f27e-675">**classlib**</span></span>

<span data-ttu-id="3f27e-676">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="3f27e-676">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3f27e-677">值：`netcoreapp2.0`（要创建 .NET Core 类库的话）或 `netstandard2.0`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="3f27e-677">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="3f27e-678">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-678">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="3f27e-679">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-679">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-680">**mstest、xunit**</span><span class="sxs-lookup"><span data-stu-id="3f27e-680">**mstest, xunit**</span></span>

<span data-ttu-id="3f27e-681">`-p|--enable-pack` - 允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="3f27e-681">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="3f27e-682">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-682">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-683">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="3f27e-683">**globaljson**</span></span>

<span data-ttu-id="3f27e-684">`--sdk-version <VERSION_NUMBER>` - 指定要在 global.json 文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="3f27e-684">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="3f27e-685">**web**</span><span class="sxs-lookup"><span data-stu-id="3f27e-685">**web**</span></span>

<span data-ttu-id="3f27e-686">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="3f27e-686">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="3f27e-687">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-687">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-688">**webapi**</span><span class="sxs-lookup"><span data-stu-id="3f27e-688">**webapi**</span></span>

<span data-ttu-id="3f27e-689">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="3f27e-689">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="3f27e-690">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="3f27e-690">The possible values are:</span></span>

- <span data-ttu-id="3f27e-691">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="3f27e-691">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="3f27e-692">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-692">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="3f27e-693">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-693">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="3f27e-694">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-694">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="3f27e-695">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="3f27e-695">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="3f27e-696">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-696">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="3f27e-697">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-697">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="3f27e-698">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-698">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="3f27e-699">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-699">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-700">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="3f27e-700">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="3f27e-701">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-701">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3f27e-702">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-702">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="3f27e-703">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-703">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="3f27e-704">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-704">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="3f27e-705">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-705">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="3f27e-706">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="3f27e-706">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="3f27e-707">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-707">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3f27e-708">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-708">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="3f27e-709">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-709">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="3f27e-710">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-710">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3f27e-711">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-711">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="3f27e-712">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="3f27e-712">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="3f27e-713">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-713">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="3f27e-714">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="3f27e-714">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="3f27e-715">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="3f27e-715">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3f27e-716">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-716">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-717">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-717">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-718">**mvc、razor**</span><span class="sxs-lookup"><span data-stu-id="3f27e-718">**mvc, razor**</span></span>

<span data-ttu-id="3f27e-719">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="3f27e-719">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="3f27e-720">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="3f27e-720">The possible values are:</span></span>

- <span data-ttu-id="3f27e-721">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="3f27e-721">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="3f27e-722">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-722">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="3f27e-723">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-723">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="3f27e-724">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-724">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="3f27e-725">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-725">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="3f27e-726">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-726">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="3f27e-727">`--aad-b2c-instance <INSTANCE>` - 要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="3f27e-727">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="3f27e-728">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-728">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="3f27e-729">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-729">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="3f27e-730">`-ssp|--susi-policy-id <ID>` - 此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-730">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="3f27e-731">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-731">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-732">`-rp|--reset-password-policy-id <ID>` - 此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-732">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="3f27e-733">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-733">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-734">`-ep|--edit-profile-policy-id <ID>` - 此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-734">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="3f27e-735">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-735">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-736">`--aad-instance <INSTANCE>` - 要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="3f27e-736">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="3f27e-737">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-737">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="3f27e-738">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-738">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="3f27e-739">`--client-id <ID>` - 此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-739">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="3f27e-740">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-740">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="3f27e-741">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-741">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="3f27e-742">`--domain <DOMAIN>` - 目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="3f27e-742">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="3f27e-743">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-743">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3f27e-744">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-744">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="3f27e-745">`--tenant-id <ID>` - 要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="3f27e-745">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="3f27e-746">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-746">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3f27e-747">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-747">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="3f27e-748">`--callback-path <PATH>` - 重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="3f27e-748">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="3f27e-749">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="3f27e-749">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3f27e-750">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-750">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="3f27e-751">`-r|--org-read-access` - 允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="3f27e-751">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="3f27e-752">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-752">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="3f27e-753">`--use-launch-settings` - 在生成的模板输出中添加 launchSettings.json。</span><span class="sxs-lookup"><span data-stu-id="3f27e-753">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="3f27e-754">`--use-browserlink` - 在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="3f27e-754">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="3f27e-755">`-uld|--use-local-db` - 指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="3f27e-755">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3f27e-756">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3f27e-756">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3f27e-757">`--no-restore` - 在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="3f27e-757">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3f27e-758">**page**</span><span class="sxs-lookup"><span data-stu-id="3f27e-758">**page**</span></span>

<span data-ttu-id="3f27e-759">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3f27e-759">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="3f27e-760">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-760">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="3f27e-761">`-np|--no-pagemodel` - 创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="3f27e-761">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="3f27e-762">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="3f27e-762">**viewimports**</span></span>

<span data-ttu-id="3f27e-763">`-na|--namespace <NAMESPACE_NAME>` - 生成的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3f27e-763">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="3f27e-764">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-764">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3f27e-765">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3f27e-765">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="3f27e-766">**console、xunit、mstest、web、webapi**</span><span class="sxs-lookup"><span data-stu-id="3f27e-766">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="3f27e-767">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="3f27e-767">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3f27e-768">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-768">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="3f27e-769">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-769">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="3f27e-770">**classlib**</span><span class="sxs-lookup"><span data-stu-id="3f27e-770">**classlib**</span></span>

<span data-ttu-id="3f27e-771">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="3f27e-771">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3f27e-772">值：`netcoreapp1.0`、`netcoreapp1.1` 或 `netstandard1.0` 到 `netstandard1.6`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-772">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="3f27e-773">默认值为 `netstandard1.4`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-773">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="3f27e-774">**mvc**</span><span class="sxs-lookup"><span data-stu-id="3f27e-774">**mvc**</span></span>

<span data-ttu-id="3f27e-775">`-f|--framework <FRAMEWORK>` - 指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="3f27e-775">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3f27e-776">值：`netcoreapp1.0` 或 `netcoreapp1.1`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-776">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="3f27e-777">默认值为 `netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-777">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="3f27e-778">`-au|--auth <AUTHENTICATION_TYPE>` - 要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="3f27e-778">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="3f27e-779">值：`None` 或 `Individual`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-779">Values: `None` or `Individual`.</span></span> <span data-ttu-id="3f27e-780">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-780">The default value is `None`.</span></span>

<span data-ttu-id="3f27e-781">`-uld|--use-local-db` - 指定是否使用 LocalDB，而不是 SQLite。</span><span class="sxs-lookup"><span data-stu-id="3f27e-781">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="3f27e-782">值：`true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-782">Values: `true` or `false`.</span></span> <span data-ttu-id="3f27e-783">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="3f27e-783">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="3f27e-784">示例</span><span class="sxs-lookup"><span data-stu-id="3f27e-784">Examples</span></span>

<span data-ttu-id="3f27e-785">通过指定模板名称，创建 C# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="3f27e-785">Create a C# console application project by specifying the template name:</span></span>

`dotnet new "Console Application"`

<span data-ttu-id="3f27e-786">在当前目录中创建 F# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="3f27e-786">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="3f27e-787">在指定目录中创建 .NET Standard 类库项目（仅适用于 .NET Core SDK 2.0 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="3f27e-787">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="3f27e-788">在当前目录中新建没有设置身份验证的 ASP.NET Core C# MVC 项目：</span><span class="sxs-lookup"><span data-stu-id="3f27e-788">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="3f27e-789">创建新的 xUnit 项目：</span><span class="sxs-lookup"><span data-stu-id="3f27e-789">Create a new xUnit project:</span></span>

`dotnet new xunit`

<span data-ttu-id="3f27e-790">列出适用于 MVC 的所有模板：</span><span class="sxs-lookup"><span data-stu-id="3f27e-790">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="3f27e-791">列出与“we”子字符串匹配的所有模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-791">List all templates matching the *we* substring.</span></span> <span data-ttu-id="3f27e-792">找不到完全匹配，因此子字符串匹配针对短名称和名称列运行。</span><span class="sxs-lookup"><span data-stu-id="3f27e-792">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

`dotnet new we -l`

<span data-ttu-id="3f27e-793">尝试调用与 ng 匹配的模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-793">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="3f27e-794">如果无法确定单个匹配项，请列出部分匹配项的模板。</span><span class="sxs-lookup"><span data-stu-id="3f27e-794">If a single match can't be determined, list the templates that are partial matches.</span></span>

`dotnet new ng`

<span data-ttu-id="3f27e-795">安装适用于 ASP.NET Core 的单页应用程序模板 2.0 版（命令选项仅可用于 .NET Core SDK 1.1 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="3f27e-795">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="3f27e-796">在当前目录中创建 global.json，将 SDK 版本设为 2.0.0（仅适用于 .NET Core SDK 2.0 或更高版本）：</span><span class="sxs-lookup"><span data-stu-id="3f27e-796">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="3f27e-797">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f27e-797">See also</span></span>

- [<span data-ttu-id="3f27e-798">dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="3f27e-798">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="3f27e-799">创建 dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="3f27e-799">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)
- [<span data-ttu-id="3f27e-800">dotnet/dotnet-template-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="3f27e-800">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="3f27e-801">dotnet new 可用模板</span><span class="sxs-lookup"><span data-stu-id="3f27e-801">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
