---
title: dotnet new 命令
description: dotnet new 命令可根据指定模板新建 .NET Core 项目。
ms.date: 02/13/2020
ms.openlocfilehash: d3c609419596b123f5bfb3ca85cf292a61154a70
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398027"
---
# <a name="dotnet-new"></a><span data-ttu-id="ce0ee-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ce0ee-103">dotnet new</span></span>

<span data-ttu-id="ce0ee-104"> 本文适用于： ✔️ .NET Core 2.0 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="ce0ee-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="ce0ee-105">名称</span><span class="sxs-lookup"><span data-stu-id="ce0ee-105">Name</span></span>

<span data-ttu-id="ce0ee-106">`dotnet new` - 根据指定的模板，创建新的项目、配置文件或解决方案。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ce0ee-107">摘要</span><span class="sxs-lookup"><span data-stu-id="ce0ee-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name]
    [--nuget-source] [-o|--output] [-u|--uninstall] [--update-apply] [--update-check] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

## <a name="description"></a><span data-ttu-id="ce0ee-108">说明</span><span class="sxs-lookup"><span data-stu-id="ce0ee-108">Description</span></span>

<span data-ttu-id="ce0ee-109">`dotnet new` 命令基于模板创建 .NET Core 项目或其他项目。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="ce0ee-110">命令调用[模板引擎](https://github.com/dotnet/templating)，以根据指定的模板和选项在磁盘上创建项目。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="ce0ee-111">参数</span><span class="sxs-lookup"><span data-stu-id="ce0ee-111">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="ce0ee-112">调用命令时要实例化的模板。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-112">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="ce0ee-113">每个模板可能具有可传递的特定选项。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-113">Each template might have specific options you can pass.</span></span> <span data-ttu-id="ce0ee-114">有关详细信息，请参阅[模板选项](#template-options)。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-114">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="ce0ee-115">可以运行 `dotnet new --list` 以查看所有已安装模板的列表。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-115">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="ce0ee-116">如果 `TEMPLATE` 值与返回表中的“模板”  或“短名称”  列中的文本不完全匹配，则会对这两列执行 substring 匹配。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-116">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="ce0ee-117">从 .NET Core 3.0 SDK 开始，当你在以下情况下调用 `dotnet new` 命令时，CLI 将在 NuGet.org 中搜索模板：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-117">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="ce0ee-118">如果在调用 `dotnet new` 时 CLI 找不到模板匹配项，即使是部分匹配也不行。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-118">If the CLI can’t find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="ce0ee-119">如果有较新版本的模板可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-119">If there’s a newer version of the template available.</span></span> <span data-ttu-id="ce0ee-120">在这种情况下，将创建项目或工件，但 CLI 会就模板的更新版本发出警告。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-120">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="ce0ee-121">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-121">The command contains a default list of templates.</span></span> <span data-ttu-id="ce0ee-122">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-122">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="ce0ee-123">下表显示了随 .NET Core SDK 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-123">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="ce0ee-124">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-124">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="ce0ee-125">单击短名称链接可查看特定的模板选项。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-125">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="ce0ee-126">模板</span><span class="sxs-lookup"><span data-stu-id="ce0ee-126">Templates</span></span>                                    | <span data-ttu-id="ce0ee-127">短名称</span><span class="sxs-lookup"><span data-stu-id="ce0ee-127">Short name</span></span>                      | <span data-ttu-id="ce0ee-128">语言</span><span class="sxs-lookup"><span data-stu-id="ce0ee-128">Language</span></span>     | <span data-ttu-id="ce0ee-129">Tags</span><span class="sxs-lookup"><span data-stu-id="ce0ee-129">Tags</span></span>                                  | <span data-ttu-id="ce0ee-130">已引入</span><span class="sxs-lookup"><span data-stu-id="ce0ee-130">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="ce0ee-131">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="ce0ee-131">Console Application</span></span>                          | [<span data-ttu-id="ce0ee-132">控制台</span><span class="sxs-lookup"><span data-stu-id="ce0ee-132">console</span></span>](#console)             | <span data-ttu-id="ce0ee-133">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="ce0ee-133">[C#], F#, VB</span></span> | <span data-ttu-id="ce0ee-134">常用/控制台</span><span class="sxs-lookup"><span data-stu-id="ce0ee-134">Common/Console</span></span>                        | <span data-ttu-id="ce0ee-135">1.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-135">1.0</span></span>        |
| <span data-ttu-id="ce0ee-136">类库</span><span class="sxs-lookup"><span data-stu-id="ce0ee-136">Class library</span></span>                                | [<span data-ttu-id="ce0ee-137">classlib</span><span class="sxs-lookup"><span data-stu-id="ce0ee-137">classlib</span></span>](#classlib)           | <span data-ttu-id="ce0ee-138">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="ce0ee-138">[C#], F#, VB</span></span> | <span data-ttu-id="ce0ee-139">常用/库</span><span class="sxs-lookup"><span data-stu-id="ce0ee-139">Common/Library</span></span>                        | <span data-ttu-id="ce0ee-140">1.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-140">1.0</span></span>        |
| <span data-ttu-id="ce0ee-141">WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="ce0ee-141">WPF Application</span></span>                              | [<span data-ttu-id="ce0ee-142">wpf</span><span class="sxs-lookup"><span data-stu-id="ce0ee-142">wpf</span></span>](#wpf)                     | <span data-ttu-id="ce0ee-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-143">[C#]</span></span>         | <span data-ttu-id="ce0ee-144">常用/WPF</span><span class="sxs-lookup"><span data-stu-id="ce0ee-144">Common/WPF</span></span>                            | <span data-ttu-id="ce0ee-145">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-145">3.0</span></span>        |
| <span data-ttu-id="ce0ee-146">WPF 类库</span><span class="sxs-lookup"><span data-stu-id="ce0ee-146">WPF Class library</span></span>                            | [<span data-ttu-id="ce0ee-147">wpflib</span><span class="sxs-lookup"><span data-stu-id="ce0ee-147">wpflib</span></span>](#wpf)                  | <span data-ttu-id="ce0ee-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-148">[C#]</span></span>         | <span data-ttu-id="ce0ee-149">常用/WPF</span><span class="sxs-lookup"><span data-stu-id="ce0ee-149">Common/WPF</span></span>                            | <span data-ttu-id="ce0ee-150">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-150">3.0</span></span>        |
| <span data-ttu-id="ce0ee-151">WPF 自定义控件库</span><span class="sxs-lookup"><span data-stu-id="ce0ee-151">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="ce0ee-152">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="ce0ee-152">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="ce0ee-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-153">[C#]</span></span>         | <span data-ttu-id="ce0ee-154">常用/WPF</span><span class="sxs-lookup"><span data-stu-id="ce0ee-154">Common/WPF</span></span>                            | <span data-ttu-id="ce0ee-155">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-155">3.0</span></span>        |
| <span data-ttu-id="ce0ee-156">WPF 用户控件库</span><span class="sxs-lookup"><span data-stu-id="ce0ee-156">WPF User Control Library</span></span>                     | [<span data-ttu-id="ce0ee-157">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="ce0ee-157">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="ce0ee-158">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-158">[C#]</span></span>         | <span data-ttu-id="ce0ee-159">常用/WPF</span><span class="sxs-lookup"><span data-stu-id="ce0ee-159">Common/WPF</span></span>                            | <span data-ttu-id="ce0ee-160">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-160">3.0</span></span>        |
| <span data-ttu-id="ce0ee-161">Windows 窗体 (WinForms) 应用程序</span><span class="sxs-lookup"><span data-stu-id="ce0ee-161">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="ce0ee-162">winforms</span><span class="sxs-lookup"><span data-stu-id="ce0ee-162">winforms</span></span>](#winforms)           | <span data-ttu-id="ce0ee-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-163">[C#]</span></span>         | <span data-ttu-id="ce0ee-164">常用/WinForms</span><span class="sxs-lookup"><span data-stu-id="ce0ee-164">Common/WinForms</span></span>                       | <span data-ttu-id="ce0ee-165">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-165">3.0</span></span>        |
| <span data-ttu-id="ce0ee-166">Windows 窗体 (WinForms) 类库</span><span class="sxs-lookup"><span data-stu-id="ce0ee-166">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="ce0ee-167">winformslib</span><span class="sxs-lookup"><span data-stu-id="ce0ee-167">winformslib</span></span>](#winforms)        | <span data-ttu-id="ce0ee-168">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-168">[C#]</span></span>         | <span data-ttu-id="ce0ee-169">常用/WinForms</span><span class="sxs-lookup"><span data-stu-id="ce0ee-169">Common/WinForms</span></span>                       | <span data-ttu-id="ce0ee-170">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-170">3.0</span></span>        |
| <span data-ttu-id="ce0ee-171">Worker Service</span><span class="sxs-lookup"><span data-stu-id="ce0ee-171">Worker Service</span></span>                               | [<span data-ttu-id="ce0ee-172">worker</span><span class="sxs-lookup"><span data-stu-id="ce0ee-172">worker</span></span>](#web-others)           | <span data-ttu-id="ce0ee-173">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-173">[C#]</span></span>         | <span data-ttu-id="ce0ee-174">常用/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="ce0ee-174">Common/Worker/Web</span></span>                     | <span data-ttu-id="ce0ee-175">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-175">3.0</span></span>        |
| <span data-ttu-id="ce0ee-176">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="ce0ee-176">Unit Test Project</span></span>                            | [<span data-ttu-id="ce0ee-177">mstest</span><span class="sxs-lookup"><span data-stu-id="ce0ee-177">mstest</span></span>](#test)                 | <span data-ttu-id="ce0ee-178">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="ce0ee-178">[C#], F#, VB</span></span> | <span data-ttu-id="ce0ee-179">测试/MSTest</span><span class="sxs-lookup"><span data-stu-id="ce0ee-179">Test/MSTest</span></span>                           | <span data-ttu-id="ce0ee-180">1.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-180">1.0</span></span>        |
| <span data-ttu-id="ce0ee-181">NUnit 3 测试项目</span><span class="sxs-lookup"><span data-stu-id="ce0ee-181">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="ce0ee-182">nunit</span><span class="sxs-lookup"><span data-stu-id="ce0ee-182">nunit</span></span>](#nunit)                  | <span data-ttu-id="ce0ee-183">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="ce0ee-183">[C#], F#, VB</span></span> | <span data-ttu-id="ce0ee-184">测试/NUnit</span><span class="sxs-lookup"><span data-stu-id="ce0ee-184">Test/NUnit</span></span>                            | <span data-ttu-id="ce0ee-185">2.1.400</span><span class="sxs-lookup"><span data-stu-id="ce0ee-185">2.1.400</span></span>    |
| <span data-ttu-id="ce0ee-186">NUnit 3 测试项</span><span class="sxs-lookup"><span data-stu-id="ce0ee-186">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="ce0ee-187">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="ce0ee-187">[C#], F#, VB</span></span> | <span data-ttu-id="ce0ee-188">测试/NUnit</span><span class="sxs-lookup"><span data-stu-id="ce0ee-188">Test/NUnit</span></span>                            | <span data-ttu-id="ce0ee-189">2.2</span><span class="sxs-lookup"><span data-stu-id="ce0ee-189">2.2</span></span>        |
| <span data-ttu-id="ce0ee-190">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="ce0ee-190">xUnit Test Project</span></span>                           | [<span data-ttu-id="ce0ee-191">xunit</span><span class="sxs-lookup"><span data-stu-id="ce0ee-191">xunit</span></span>](#test)                  | <span data-ttu-id="ce0ee-192">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="ce0ee-192">[C#], F#, VB</span></span> | <span data-ttu-id="ce0ee-193">测试/xUnit</span><span class="sxs-lookup"><span data-stu-id="ce0ee-193">Test/xUnit</span></span>                            | <span data-ttu-id="ce0ee-194">1.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-194">1.0</span></span>        |
| <span data-ttu-id="ce0ee-195">Razor 组件</span><span class="sxs-lookup"><span data-stu-id="ce0ee-195">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="ce0ee-196">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-196">[C#]</span></span>         | <span data-ttu-id="ce0ee-197">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ce0ee-197">Web/ASP.NET</span></span>                           | <span data-ttu-id="ce0ee-198">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-198">3.0</span></span>        |
| <span data-ttu-id="ce0ee-199">Razor 页</span><span class="sxs-lookup"><span data-stu-id="ce0ee-199">Razor Page</span></span>                                   | [<span data-ttu-id="ce0ee-200">page</span><span class="sxs-lookup"><span data-stu-id="ce0ee-200">page</span></span>](#page)                   | <span data-ttu-id="ce0ee-201">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-201">[C#]</span></span>         | <span data-ttu-id="ce0ee-202">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ce0ee-202">Web/ASP.NET</span></span>                           | <span data-ttu-id="ce0ee-203">2.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-203">2.0</span></span>        |
| <span data-ttu-id="ce0ee-204">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="ce0ee-204">MVC ViewImports</span></span>                              | [<span data-ttu-id="ce0ee-205">viewimports</span><span class="sxs-lookup"><span data-stu-id="ce0ee-205">viewimports</span></span>](#namespace)       | <span data-ttu-id="ce0ee-206">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-206">[C#]</span></span>         | <span data-ttu-id="ce0ee-207">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ce0ee-207">Web/ASP.NET</span></span>                           | <span data-ttu-id="ce0ee-208">2.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-208">2.0</span></span>        |
| <span data-ttu-id="ce0ee-209">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="ce0ee-209">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="ce0ee-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-210">[C#]</span></span>         | <span data-ttu-id="ce0ee-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ce0ee-211">Web/ASP.NET</span></span>                           | <span data-ttu-id="ce0ee-212">2.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-212">2.0</span></span>        |
| <span data-ttu-id="ce0ee-213">Blazor Server 应用</span><span class="sxs-lookup"><span data-stu-id="ce0ee-213">Blazor Server App</span></span>                            | [<span data-ttu-id="ce0ee-214">blazorserver</span><span class="sxs-lookup"><span data-stu-id="ce0ee-214">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="ce0ee-215">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-215">[C#]</span></span>         | <span data-ttu-id="ce0ee-216">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="ce0ee-216">Web/Blazor</span></span>                            | <span data-ttu-id="ce0ee-217">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-217">3.0</span></span>        |
| <span data-ttu-id="ce0ee-218">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="ce0ee-218">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="ce0ee-219">web</span><span class="sxs-lookup"><span data-stu-id="ce0ee-219">web</span></span>](#web)                     | <span data-ttu-id="ce0ee-220">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="ce0ee-220">[C#], F#</span></span>     | <span data-ttu-id="ce0ee-221">Web/空</span><span class="sxs-lookup"><span data-stu-id="ce0ee-221">Web/Empty</span></span>                             | <span data-ttu-id="ce0ee-222">1.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-222">1.0</span></span>        |
| <span data-ttu-id="ce0ee-223">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="ce0ee-223">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="ce0ee-224">mvc</span><span class="sxs-lookup"><span data-stu-id="ce0ee-224">mvc</span></span>](#web-options)             | <span data-ttu-id="ce0ee-225">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="ce0ee-225">[C#], F#</span></span>     | <span data-ttu-id="ce0ee-226">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="ce0ee-226">Web/MVC</span></span>                               | <span data-ttu-id="ce0ee-227">1.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-227">1.0</span></span>        |
| <span data-ttu-id="ce0ee-228">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="ce0ee-228">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="ce0ee-229">webapp、razor</span><span class="sxs-lookup"><span data-stu-id="ce0ee-229">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="ce0ee-230">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-230">[C#]</span></span>         | <span data-ttu-id="ce0ee-231">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="ce0ee-231">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="ce0ee-232">2.2、2.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-232">2.2, 2.0</span></span>   |
| <span data-ttu-id="ce0ee-233">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ce0ee-233">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="ce0ee-234">angular</span><span class="sxs-lookup"><span data-stu-id="ce0ee-234">angular</span></span>](#spa)                 | <span data-ttu-id="ce0ee-235">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-235">[C#]</span></span>         | <span data-ttu-id="ce0ee-236">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="ce0ee-236">Web/MVC/SPA</span></span>                           | <span data-ttu-id="ce0ee-237">2.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-237">2.0</span></span>        |
| <span data-ttu-id="ce0ee-238">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ce0ee-238">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="ce0ee-239">react</span><span class="sxs-lookup"><span data-stu-id="ce0ee-239">react</span></span>](#spa)                   | <span data-ttu-id="ce0ee-240">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-240">[C#]</span></span>         | <span data-ttu-id="ce0ee-241">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="ce0ee-241">Web/MVC/SPA</span></span>                           | <span data-ttu-id="ce0ee-242">2.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-242">2.0</span></span>        |
| <span data-ttu-id="ce0ee-243">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ce0ee-243">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="ce0ee-244">reactredux</span><span class="sxs-lookup"><span data-stu-id="ce0ee-244">reactredux</span></span>](#reactredux)       | <span data-ttu-id="ce0ee-245">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-245">[C#]</span></span>         | <span data-ttu-id="ce0ee-246">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="ce0ee-246">Web/MVC/SPA</span></span>                           | <span data-ttu-id="ce0ee-247">2.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-247">2.0</span></span>        |
| <span data-ttu-id="ce0ee-248">Razor 类库</span><span class="sxs-lookup"><span data-stu-id="ce0ee-248">Razor Class Library</span></span>                          | [<span data-ttu-id="ce0ee-249">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="ce0ee-249">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="ce0ee-250">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-250">[C#]</span></span>         | <span data-ttu-id="ce0ee-251">Web/Razor/库/Razor 类库</span><span class="sxs-lookup"><span data-stu-id="ce0ee-251">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="ce0ee-252">2.1</span><span class="sxs-lookup"><span data-stu-id="ce0ee-252">2.1</span></span>        |
| <span data-ttu-id="ce0ee-253">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="ce0ee-253">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="ce0ee-254">webapi</span><span class="sxs-lookup"><span data-stu-id="ce0ee-254">webapi</span></span>](#webapi)               | <span data-ttu-id="ce0ee-255">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="ce0ee-255">[C#], F#</span></span>     | <span data-ttu-id="ce0ee-256">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="ce0ee-256">Web/WebAPI</span></span>                            | <span data-ttu-id="ce0ee-257">1.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-257">1.0</span></span>        |
| <span data-ttu-id="ce0ee-258">ASP.NET Core gRPC 服务</span><span class="sxs-lookup"><span data-stu-id="ce0ee-258">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="ce0ee-259">grpc</span><span class="sxs-lookup"><span data-stu-id="ce0ee-259">grpc</span></span>](#web-others)             | <span data-ttu-id="ce0ee-260">[C#]</span><span class="sxs-lookup"><span data-stu-id="ce0ee-260">[C#]</span></span>         | <span data-ttu-id="ce0ee-261">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="ce0ee-261">Web/gRPC</span></span>                              | <span data-ttu-id="ce0ee-262">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-262">3.0</span></span>        |
| <span data-ttu-id="ce0ee-263">协议缓冲区文件</span><span class="sxs-lookup"><span data-stu-id="ce0ee-263">Protocol Buffer File</span></span>                         | [<span data-ttu-id="ce0ee-264">proto</span><span class="sxs-lookup"><span data-stu-id="ce0ee-264">proto</span></span>](#namespace)             |              | <span data-ttu-id="ce0ee-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="ce0ee-265">Web/gRPC</span></span>                              | <span data-ttu-id="ce0ee-266">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-266">3.0</span></span>        |
| <span data-ttu-id="ce0ee-267">dotnet gitignore 文件</span><span class="sxs-lookup"><span data-stu-id="ce0ee-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="ce0ee-268">配置</span><span class="sxs-lookup"><span data-stu-id="ce0ee-268">Config</span></span>                                | <span data-ttu-id="ce0ee-269">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-269">3.0</span></span>        |
| <span data-ttu-id="ce0ee-270">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="ce0ee-270">global.json file</span></span>                             | [<span data-ttu-id="ce0ee-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="ce0ee-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="ce0ee-272">配置</span><span class="sxs-lookup"><span data-stu-id="ce0ee-272">Config</span></span>                                | <span data-ttu-id="ce0ee-273">2.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-273">2.0</span></span>        |
| <span data-ttu-id="ce0ee-274">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="ce0ee-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="ce0ee-275">配置</span><span class="sxs-lookup"><span data-stu-id="ce0ee-275">Config</span></span>                                | <span data-ttu-id="ce0ee-276">1.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-276">1.0</span></span>        |
| <span data-ttu-id="ce0ee-277">dotnet 本地工具清单文件</span><span class="sxs-lookup"><span data-stu-id="ce0ee-277">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="ce0ee-278">配置</span><span class="sxs-lookup"><span data-stu-id="ce0ee-278">Config</span></span>                                | <span data-ttu-id="ce0ee-279">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-279">3.0</span></span>        |
| <span data-ttu-id="ce0ee-280">Web 配置</span><span class="sxs-lookup"><span data-stu-id="ce0ee-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="ce0ee-281">配置</span><span class="sxs-lookup"><span data-stu-id="ce0ee-281">Config</span></span>                                | <span data-ttu-id="ce0ee-282">1.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-282">1.0</span></span>        |
| <span data-ttu-id="ce0ee-283">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="ce0ee-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="ce0ee-284">解决方案</span><span class="sxs-lookup"><span data-stu-id="ce0ee-284">Solution</span></span>                              | <span data-ttu-id="ce0ee-285">1.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-285">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="ce0ee-286">选项</span><span class="sxs-lookup"><span data-stu-id="ce0ee-286">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="ce0ee-287">显示有关以下内容的摘要：给定命令运行时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-287">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="ce0ee-288">自 .NET Core 2.2 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-288">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="ce0ee-289">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-289">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="ce0ee-290">当选择的模板将覆盖输出目录中的现有文件时，需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-290">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="ce0ee-291">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-291">Prints out help for the command.</span></span> <span data-ttu-id="ce0ee-292">可针对 `dotnet new` 命令本身或任何模板调用它。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-292">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="ce0ee-293">例如，`dotnet new mvc --help` 。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-293">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="ce0ee-294">从提供的 `PATH` 或 `NUGET_ID` 安装模板包。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-294">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="ce0ee-295">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-295">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="ce0ee-296">默认情况下，`dotnet new` 为该版本传递 \*，它表示最新的稳定包版本。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-296">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="ce0ee-297">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-297">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="ce0ee-298">如果在运行此命令时已经安装了模板的某个版本，则该模板将更新到指定版本，如果没有指定版本，则将更新到最新的稳定版本。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-298">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="ce0ee-299">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-299">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="ce0ee-300">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-300">Lists templates containing the specified name.</span></span> <span data-ttu-id="ce0ee-301">如果未指定名称，则列出所有模板。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-301">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="ce0ee-302">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-302">The language of the template to create.</span></span> <span data-ttu-id="ce0ee-303">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-303">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="ce0ee-304">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-304">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ce0ee-305">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-305">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="ce0ee-306">在这些情况下，请将语言参数值括在引号中。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-306">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="ce0ee-307">例如，`dotnet new console -lang "F#"` 。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-307">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="ce0ee-308">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-308">The name for the created output.</span></span> <span data-ttu-id="ce0ee-309">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-309">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source`**

  <span data-ttu-id="ce0ee-310">指定在安装期间要使用的 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-310">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="ce0ee-311">自 .NET Core 2.1 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-311">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="ce0ee-312">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-312">Location to place the generated output.</span></span> <span data-ttu-id="ce0ee-313">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-313">The default is the current directory.</span></span>

- **`--type`**

  <span data-ttu-id="ce0ee-314">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-314">Filters templates based on available types.</span></span> <span data-ttu-id="ce0ee-315">预定义的值为“项目”、“项”或“其他”。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-315">Predefined values are "project", "item", or "other".</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="ce0ee-316">在提供的 `PATH` 或 `NUGET_ID` 中卸载模板包。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-316">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="ce0ee-317">如果未指定 `<PATH|NUGET_ID>` 值，将显示所有当前安装的模板包及其关联的模板。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-317">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="ce0ee-318">指定 `NUGET_ID` 时，请勿包含版本号。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-318">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="ce0ee-319">如果未指定此选项的参数，该命令将列出已安装的模板及其详细信息。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-319">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ce0ee-320">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-320">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="ce0ee-321">例如，C:/Users/*USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp\<* 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp  无效。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-321">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="ce0ee-322">模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-322">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="ce0ee-323">检查是否有可用于当前安装的模板包的更新并安装这些更新。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-323">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="ce0ee-324">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-324">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="ce0ee-325">检查是否有可用于当前安装的模板包的更新。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-325">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="ce0ee-326">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-326">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="ce0ee-327">模板选项</span><span class="sxs-lookup"><span data-stu-id="ce0ee-327">Template options</span></span>

<span data-ttu-id="ce0ee-328">每个项目模板都可能有附加选项。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-328">Each project template may have additional options available.</span></span> <span data-ttu-id="ce0ee-329">核心模板有以下附加选项：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-329">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="ce0ee-330">控制台</span><span class="sxs-lookup"><span data-stu-id="ce0ee-330">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ce0ee-331">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-331">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ce0ee-332">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-332">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="ce0ee-333">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-333">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ce0ee-334">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="ce0ee-334">SDK version</span></span> | <span data-ttu-id="ce0ee-335">默认值</span><span class="sxs-lookup"><span data-stu-id="ce0ee-335">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ce0ee-336">3.1</span><span class="sxs-lookup"><span data-stu-id="ce0ee-336">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ce0ee-337">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-337">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="ce0ee-338">在已创建的项目文件中设置 `LangVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-338">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="ce0ee-339">例如，使用 `--langVersion 7.3` 以使用 C# 7.3。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-339">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="ce0ee-340">不支持 F#。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-340">Not supported for F#.</span></span> <span data-ttu-id="ce0ee-341">自 .NET Core 2.2 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-341">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ce0ee-342">有关默认的 C# 版本列表，请参阅[默认](../../csharp/language-reference/configure-language-version.md#defaults)。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-342">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="ce0ee-343">如已指定，则在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-343">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="ce0ee-344">自 .NET Core 2.2 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-344">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="ce0ee-345">classlib</span><span class="sxs-lookup"><span data-stu-id="ce0ee-345">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ce0ee-346">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-346">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ce0ee-347">值：`netcoreapp<version>`（要创建 .NET Core 类库的话）或 `netstandard<version>`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-347">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="ce0ee-348">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-348">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="ce0ee-349">在已创建的项目文件中设置 `LangVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-349">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="ce0ee-350">例如，使用 `--langVersion 7.3` 以使用 C# 7.3。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-350">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="ce0ee-351">不支持 F#。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-351">Not supported for F#.</span></span> <span data-ttu-id="ce0ee-352">自 .NET Core 2.2 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-352">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ce0ee-353">有关默认的 C# 版本列表，请参阅[默认](../../csharp/language-reference/configure-language-version.md#defaults)。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-353">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="ce0ee-354">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-354">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf"></a> <span data-ttu-id="ce0ee-355">wpf、wpflib、wpfcustomcontrollib、wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="ce0ee-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ce0ee-356">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-356">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ce0ee-357">默认值为 `netcoreapp3.1`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-357">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="ce0ee-358">自 .NET Core 3.1 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-358">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="ce0ee-359">在已创建的项目文件中设置 `LangVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-359">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="ce0ee-360">例如，使用 `--langVersion 7.3` 以使用 C# 7.3。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-360">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="ce0ee-361">有关默认的 C# 版本列表，请参阅[默认](../../csharp/language-reference/configure-language-version.md#defaults)。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-361">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="ce0ee-362">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-362">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms"></a> <span data-ttu-id="ce0ee-363">winforms、winformslib</span><span class="sxs-lookup"><span data-stu-id="ce0ee-363">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="ce0ee-364">在已创建的项目文件中设置 `LangVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-364">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="ce0ee-365">例如，使用 `--langVersion 7.3` 以使用 C# 7.3。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-365">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="ce0ee-366">有关默认的 C# 版本列表，请参阅[默认](../../csharp/language-reference/configure-language-version.md#defaults)。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-366">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="ce0ee-367">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-367">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web-others"></a> <span data-ttu-id="ce0ee-368">worker、grpc</span><span class="sxs-lookup"><span data-stu-id="ce0ee-368">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ce0ee-369">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-369">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ce0ee-370">默认值为 `netcoreapp3.1`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-370">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="ce0ee-371">自 .NET Core 3.1 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-371">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ce0ee-372">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-372">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="ce0ee-373">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-373">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="test"></a> <span data-ttu-id="ce0ee-374">mstest、xunit</span><span class="sxs-lookup"><span data-stu-id="ce0ee-374">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ce0ee-375">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-375">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ce0ee-376">自 .NET Core 3.0 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-376">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="ce0ee-377">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-377">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ce0ee-378">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="ce0ee-378">SDK version</span></span> | <span data-ttu-id="ce0ee-379">默认值</span><span class="sxs-lookup"><span data-stu-id="ce0ee-379">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ce0ee-380">3.1</span><span class="sxs-lookup"><span data-stu-id="ce0ee-380">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ce0ee-381">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-381">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="ce0ee-382">允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-382">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="ce0ee-383">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-383">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="ce0ee-384">nunit</span><span class="sxs-lookup"><span data-stu-id="ce0ee-384">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ce0ee-385">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-385">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="ce0ee-386">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-386">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ce0ee-387">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="ce0ee-387">SDK version</span></span> | <span data-ttu-id="ce0ee-388">默认值</span><span class="sxs-lookup"><span data-stu-id="ce0ee-388">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ce0ee-389">3.1</span><span class="sxs-lookup"><span data-stu-id="ce0ee-389">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ce0ee-390">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-390">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="ce0ee-391">2.2</span><span class="sxs-lookup"><span data-stu-id="ce0ee-391">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="ce0ee-392">2.1</span><span class="sxs-lookup"><span data-stu-id="ce0ee-392">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="ce0ee-393">允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-393">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="ce0ee-394">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-394">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="ce0ee-395">页</span><span class="sxs-lookup"><span data-stu-id="ce0ee-395">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="ce0ee-396">已生成代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-396">Namespace for the generated code.</span></span> <span data-ttu-id="ce0ee-397">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-397">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="ce0ee-398">创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-398">Creates the page without a PageModel.</span></span>

***

### <a name="namespace"></a> <span data-ttu-id="ce0ee-399">viewimports、proto</span><span class="sxs-lookup"><span data-stu-id="ce0ee-399">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="ce0ee-400">已生成代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-400">Namespace for the generated code.</span></span> <span data-ttu-id="ce0ee-401">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-401">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="ce0ee-402">blazorserver</span><span class="sxs-lookup"><span data-stu-id="ce0ee-402">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="ce0ee-403">要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-403">The type of authentication to use.</span></span> <span data-ttu-id="ce0ee-404">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-404">The possible values are:</span></span>

  - <span data-ttu-id="ce0ee-405">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-405">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="ce0ee-406">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-406">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="ce0ee-407">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="ce0ee-408">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="ce0ee-409">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-409">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="ce0ee-410">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-410">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="ce0ee-411">要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-411">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="ce0ee-412">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-412">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="ce0ee-413">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-413">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="ce0ee-414">此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-414">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="ce0ee-415">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-415">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="ce0ee-416">此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-416">The reset password policy ID for this project.</span></span> <span data-ttu-id="ce0ee-417">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-417">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="ce0ee-418">此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-418">The edit profile policy ID for this project.</span></span> <span data-ttu-id="ce0ee-419">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-419">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="ce0ee-420">要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-420">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="ce0ee-421">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-421">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="ce0ee-422">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-422">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="ce0ee-423">此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-423">The Client ID for this project.</span></span> <span data-ttu-id="ce0ee-424">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-424">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="ce0ee-425">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-425">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="ce0ee-426">目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-426">The domain for the directory tenant.</span></span> <span data-ttu-id="ce0ee-427">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-427">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ce0ee-428">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-428">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="ce0ee-429">要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-429">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="ce0ee-430">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ce0ee-431">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-431">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="ce0ee-432">重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-432">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="ce0ee-433">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-433">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ce0ee-434">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-434">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="ce0ee-435">允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-435">Allows this application read-access to the directory.</span></span> <span data-ttu-id="ce0ee-436">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-436">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ce0ee-437">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-437">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="ce0ee-438">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-438">Turns off HTTPS.</span></span> <span data-ttu-id="ce0ee-439">此选项仅适用于 `Individual`、`IndividualB2C`、`SingleOrg` 和 `MultiOrg` 未用于 `--auth` 的情况。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-439">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="ce0ee-440">指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-440">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="ce0ee-441">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-441">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="ce0ee-442">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-442">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="ce0ee-443">Web</span><span class="sxs-lookup"><span data-stu-id="ce0ee-443">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ce0ee-444">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-444">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ce0ee-445">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-445">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ce0ee-446">选项在 .NET Core 2.2 SDK 中不可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-446">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ce0ee-447">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-447">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ce0ee-448">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="ce0ee-448">SDK version</span></span> | <span data-ttu-id="ce0ee-449">默认值</span><span class="sxs-lookup"><span data-stu-id="ce0ee-449">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ce0ee-450">3.1</span><span class="sxs-lookup"><span data-stu-id="ce0ee-450">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ce0ee-451">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-451">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="ce0ee-452">2.1</span><span class="sxs-lookup"><span data-stu-id="ce0ee-452">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="ce0ee-453">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-453">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="ce0ee-454">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-454">Turns off HTTPS.</span></span>

***

### <a name="web-options"></a> <span data-ttu-id="ce0ee-455">mvc、webapp</span><span class="sxs-lookup"><span data-stu-id="ce0ee-455">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="ce0ee-456">要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-456">The type of authentication to use.</span></span> <span data-ttu-id="ce0ee-457">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-457">The possible values are:</span></span>

  - <span data-ttu-id="ce0ee-458">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-458">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="ce0ee-459">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-459">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="ce0ee-460">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-460">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="ce0ee-461">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-461">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="ce0ee-462">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-462">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="ce0ee-463">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-463">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="ce0ee-464">要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-464">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="ce0ee-465">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-465">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="ce0ee-466">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-466">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="ce0ee-467">此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-467">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="ce0ee-468">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-468">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="ce0ee-469">此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-469">The reset password policy ID for this project.</span></span> <span data-ttu-id="ce0ee-470">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-470">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="ce0ee-471">此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-471">The edit profile policy ID for this project.</span></span> <span data-ttu-id="ce0ee-472">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-472">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="ce0ee-473">要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-473">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="ce0ee-474">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-474">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="ce0ee-475">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-475">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="ce0ee-476">此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-476">The Client ID for this project.</span></span> <span data-ttu-id="ce0ee-477">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-477">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="ce0ee-478">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-478">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="ce0ee-479">目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-479">The domain for the directory tenant.</span></span> <span data-ttu-id="ce0ee-480">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ce0ee-481">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-481">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="ce0ee-482">要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-482">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="ce0ee-483">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-483">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ce0ee-484">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-484">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="ce0ee-485">重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-485">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="ce0ee-486">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-486">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ce0ee-487">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-487">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="ce0ee-488">允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-488">Allows this application read-access to the directory.</span></span> <span data-ttu-id="ce0ee-489">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-489">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ce0ee-490">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-490">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="ce0ee-491">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-491">Turns off HTTPS.</span></span> <span data-ttu-id="ce0ee-492">此选项仅适用于未使用 `Individual`、`IndividualB2C``SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-492">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="ce0ee-493">指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-493">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="ce0ee-494">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-494">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ce0ee-495">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-495">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ce0ee-496">自 .NET Core 3.0 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-496">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="ce0ee-497">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-497">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ce0ee-498">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="ce0ee-498">SDK version</span></span> | <span data-ttu-id="ce0ee-499">默认值</span><span class="sxs-lookup"><span data-stu-id="ce0ee-499">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ce0ee-500">3.1</span><span class="sxs-lookup"><span data-stu-id="ce0ee-500">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ce0ee-501">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-501">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="ce0ee-502">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-502">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="ce0ee-503">在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-503">Includes BrowserLink in the project.</span></span> <span data-ttu-id="ce0ee-504">选项在 .NET Core 2.2 和 3.1 SDK 中不可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-504">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

***

### <a name="spa"></a> <span data-ttu-id="ce0ee-505">angular、react</span><span class="sxs-lookup"><span data-stu-id="ce0ee-505">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="ce0ee-506">要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-506">The type of authentication to use.</span></span> <span data-ttu-id="ce0ee-507">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-507">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="ce0ee-508">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-508">The possible values are:</span></span>

  - <span data-ttu-id="ce0ee-509">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-509">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="ce0ee-510">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-510">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ce0ee-511">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-511">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="ce0ee-512">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-512">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="ce0ee-513">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-513">Turns off HTTPS.</span></span> <span data-ttu-id="ce0ee-514">仅当身份验证为 `None` 时，此选项才适用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-514">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="ce0ee-515">指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-515">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="ce0ee-516">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-516">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ce0ee-517">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-517">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ce0ee-518">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-518">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ce0ee-519">选项在 .NET Core 2.2 SDK 中不可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-519">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ce0ee-520">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-520">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ce0ee-521">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="ce0ee-521">SDK version</span></span> | <span data-ttu-id="ce0ee-522">默认值</span><span class="sxs-lookup"><span data-stu-id="ce0ee-522">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ce0ee-523">3.1</span><span class="sxs-lookup"><span data-stu-id="ce0ee-523">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ce0ee-524">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-524">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="ce0ee-525">2.1</span><span class="sxs-lookup"><span data-stu-id="ce0ee-525">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="ce0ee-526">reactredux</span><span class="sxs-lookup"><span data-stu-id="ce0ee-526">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ce0ee-527">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-527">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ce0ee-528">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-528">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ce0ee-529">选项在 .NET Core 2.2 SDK 中不可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-529">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ce0ee-530">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-530">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ce0ee-531">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="ce0ee-531">SDK version</span></span> | <span data-ttu-id="ce0ee-532">默认值</span><span class="sxs-lookup"><span data-stu-id="ce0ee-532">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ce0ee-533">3.1</span><span class="sxs-lookup"><span data-stu-id="ce0ee-533">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ce0ee-534">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-534">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="ce0ee-535">2.1</span><span class="sxs-lookup"><span data-stu-id="ce0ee-535">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="ce0ee-536">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-536">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="ce0ee-537">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-537">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="ce0ee-538">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="ce0ee-538">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="ce0ee-539">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="ce0ee-540">除了将组件添加到此库以外，还支持添加传统的 Razor 页面和视图。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-540">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="ce0ee-541">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-541">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="ce0ee-542">webapi</span><span class="sxs-lookup"><span data-stu-id="ce0ee-542">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="ce0ee-543">要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-543">The type of authentication to use.</span></span> <span data-ttu-id="ce0ee-544">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-544">The possible values are:</span></span>

  - <span data-ttu-id="ce0ee-545">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-545">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="ce0ee-546">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-546">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="ce0ee-547">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-547">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="ce0ee-548">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-548">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="ce0ee-549">要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-549">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="ce0ee-550">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-550">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="ce0ee-551">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-551">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="ce0ee-552">此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-552">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="ce0ee-553">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-553">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="ce0ee-554">要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-554">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="ce0ee-555">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-555">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ce0ee-556">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-556">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="ce0ee-557">此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-557">The Client ID for this project.</span></span> <span data-ttu-id="ce0ee-558">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-558">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="ce0ee-559">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-559">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="ce0ee-560">目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-560">The domain for the directory tenant.</span></span> <span data-ttu-id="ce0ee-561">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-561">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="ce0ee-562">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-562">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="ce0ee-563">要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-563">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="ce0ee-564">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-564">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ce0ee-565">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-565">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="ce0ee-566">允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-566">Allows this application read-access to the directory.</span></span> <span data-ttu-id="ce0ee-567">仅适用于 `SingleOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-567">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ce0ee-568">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-568">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="ce0ee-569">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-569">Turns off HTTPS.</span></span> <span data-ttu-id="ce0ee-570">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-570">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="ce0ee-571">此选项仅适用于 `IndividualB2C` 或 `SingleOrg` 未用于身份验证的情况。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-571">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="ce0ee-572">指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-572">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="ce0ee-573">仅适用于 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-573">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ce0ee-574">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-574">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ce0ee-575">选项在 .NET Core 2.2 SDK 中不可用。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-575">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ce0ee-576">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-576">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ce0ee-577">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="ce0ee-577">SDK version</span></span> | <span data-ttu-id="ce0ee-578">默认值</span><span class="sxs-lookup"><span data-stu-id="ce0ee-578">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ce0ee-579">3.1</span><span class="sxs-lookup"><span data-stu-id="ce0ee-579">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ce0ee-580">3.0</span><span class="sxs-lookup"><span data-stu-id="ce0ee-580">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="ce0ee-581">2.1</span><span class="sxs-lookup"><span data-stu-id="ce0ee-581">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="ce0ee-582">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-582">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="ce0ee-583">globaljson</span><span class="sxs-lookup"><span data-stu-id="ce0ee-583">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="ce0ee-584">指定要在 global.json  文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-584">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="ce0ee-585">示例</span><span class="sxs-lookup"><span data-stu-id="ce0ee-585">Examples</span></span>

- <span data-ttu-id="ce0ee-586">通过指定模板名称，创建 C# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-586">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="ce0ee-587">在当前目录中创建 F# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-587">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="ce0ee-588">在指定的目录中创建 .NET Standard 类库项目：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-588">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="ce0ee-589">在当前目录中新建没有设置身份验证的 ASP.NET Core C# MVC 项目：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-589">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="ce0ee-590">创建新的 xUnit 项目：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-590">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="ce0ee-591">列出可用于单页应用程序 (SPA) 模板的所有模板：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-591">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="ce0ee-592">列出与“we”子字符串匹配的所有模板  。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-592">List all templates matching the *we* substring.</span></span> <span data-ttu-id="ce0ee-593">找不到完全匹配，因此子字符串匹配针对短名称和名称列运行。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-593">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="ce0ee-594">尝试调用与 ng 匹配的模板  。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-594">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="ce0ee-595">如果无法确定单个匹配项，请列出部分匹配项的模板。</span><span class="sxs-lookup"><span data-stu-id="ce0ee-595">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="ce0ee-596">安装 ASP.NET Core 的 SPA 模板 2.0 版：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-596">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="ce0ee-597">列出已安装的模板及其详细信息，包括如何卸载它们：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-597">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="ce0ee-598">在当前目录中创建 global.json  ，将 SDK 版本设置为 3.1.101：</span><span class="sxs-lookup"><span data-stu-id="ce0ee-598">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="ce0ee-599">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce0ee-599">See also</span></span>

- [<span data-ttu-id="ce0ee-600">dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="ce0ee-600">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="ce0ee-601">创建 dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="ce0ee-601">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="ce0ee-602">dotnet/dotnet-template-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="ce0ee-602">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="ce0ee-603">dotnet new 可用模板</span><span class="sxs-lookup"><span data-stu-id="ce0ee-603">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
