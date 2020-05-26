---
title: dotnet new 命令
description: dotnet new 命令可根据指定模板新建 .NET Core 项目。
ms.date: 04/10/2020
ms.openlocfilehash: 1544f519f2a5f6a1a6e042c1db720eff45f5d98c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442236"
---
# <a name="dotnet-new"></a><span data-ttu-id="30c46-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="30c46-103">dotnet new</span></span>

<span data-ttu-id="30c46-104"> 本文适用于： ✔️ .NET Core 2.0 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="30c46-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="30c46-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="30c46-105">Name</span></span>

<span data-ttu-id="30c46-106">`dotnet new` - 根据指定的模板，创建新的项目、配置文件或解决方案。</span><span class="sxs-lookup"><span data-stu-id="30c46-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="30c46-107">摘要</span><span class="sxs-lookup"><span data-stu-id="30c46-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="30c46-108">描述</span><span class="sxs-lookup"><span data-stu-id="30c46-108">Description</span></span>

<span data-ttu-id="30c46-109">`dotnet new` 命令基于模板创建 .NET Core 项目或其他项目。</span><span class="sxs-lookup"><span data-stu-id="30c46-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="30c46-110">命令调用[模板引擎](https://github.com/dotnet/templating)，以根据指定的模板和选项在磁盘上创建项目。</span><span class="sxs-lookup"><span data-stu-id="30c46-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="30c46-111">隐式还原</span><span class="sxs-lookup"><span data-stu-id="30c46-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="30c46-112">自变量</span><span class="sxs-lookup"><span data-stu-id="30c46-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="30c46-113">调用命令时要实例化的模板。</span><span class="sxs-lookup"><span data-stu-id="30c46-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="30c46-114">每个模板可能具有可传递的特定选项。</span><span class="sxs-lookup"><span data-stu-id="30c46-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="30c46-115">有关详细信息，请参阅[模板选项](#template-options)。</span><span class="sxs-lookup"><span data-stu-id="30c46-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="30c46-116">可以运行 `dotnet new --list` 或 `dotnet new -l` 以查看所有已安装模板的列表。</span><span class="sxs-lookup"><span data-stu-id="30c46-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="30c46-117">如果 `TEMPLATE` 值与返回表中的“模板”  或“短名称”  列中的文本不完全匹配，则会对这两列执行 substring 匹配。</span><span class="sxs-lookup"><span data-stu-id="30c46-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="30c46-118">从 .NET Core 3.0 SDK 开始，当你在以下情况下调用 `dotnet new` 命令时，CLI 将在 NuGet.org 中搜索模板：</span><span class="sxs-lookup"><span data-stu-id="30c46-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="30c46-119">如果在调用 `dotnet new` 时 CLI 找不到模板匹配项，即使是部分匹配也不行。</span><span class="sxs-lookup"><span data-stu-id="30c46-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="30c46-120">如果有较新版本的模板可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="30c46-121">在这种情况下，将创建项目或工件，但 CLI 会就模板的更新版本发出警告。</span><span class="sxs-lookup"><span data-stu-id="30c46-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="30c46-122">下表显示了随 .NET Core SDK 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="30c46-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="30c46-123">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="30c46-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="30c46-124">单击短名称链接可查看特定的模板选项。</span><span class="sxs-lookup"><span data-stu-id="30c46-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="30c46-125">模板</span><span class="sxs-lookup"><span data-stu-id="30c46-125">Templates</span></span>                                    | <span data-ttu-id="30c46-126">短名称</span><span class="sxs-lookup"><span data-stu-id="30c46-126">Short name</span></span>                      | <span data-ttu-id="30c46-127">语言</span><span class="sxs-lookup"><span data-stu-id="30c46-127">Language</span></span>     | <span data-ttu-id="30c46-128">Tags</span><span class="sxs-lookup"><span data-stu-id="30c46-128">Tags</span></span>                                  | <span data-ttu-id="30c46-129">已引入</span><span class="sxs-lookup"><span data-stu-id="30c46-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="30c46-130">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="30c46-130">Console Application</span></span>                          | [<span data-ttu-id="30c46-131">控制台</span><span class="sxs-lookup"><span data-stu-id="30c46-131">console</span></span>](#console)             | <span data-ttu-id="30c46-132">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="30c46-132">[C#], F#, VB</span></span> | <span data-ttu-id="30c46-133">常用/控制台</span><span class="sxs-lookup"><span data-stu-id="30c46-133">Common/Console</span></span>                        | <span data-ttu-id="30c46-134">1.0</span><span class="sxs-lookup"><span data-stu-id="30c46-134">1.0</span></span>        |
| <span data-ttu-id="30c46-135">类库</span><span class="sxs-lookup"><span data-stu-id="30c46-135">Class library</span></span>                                | [<span data-ttu-id="30c46-136">classlib</span><span class="sxs-lookup"><span data-stu-id="30c46-136">classlib</span></span>](#classlib)           | <span data-ttu-id="30c46-137">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="30c46-137">[C#], F#, VB</span></span> | <span data-ttu-id="30c46-138">常用/库</span><span class="sxs-lookup"><span data-stu-id="30c46-138">Common/Library</span></span>                        | <span data-ttu-id="30c46-139">1.0</span><span class="sxs-lookup"><span data-stu-id="30c46-139">1.0</span></span>        |
| <span data-ttu-id="30c46-140">WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="30c46-140">WPF Application</span></span>                              | [<span data-ttu-id="30c46-141">wpf</span><span class="sxs-lookup"><span data-stu-id="30c46-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="30c46-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-142">[C#]</span></span>         | <span data-ttu-id="30c46-143">常用/WPF</span><span class="sxs-lookup"><span data-stu-id="30c46-143">Common/WPF</span></span>                            | <span data-ttu-id="30c46-144">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-144">3.0</span></span>        |
| <span data-ttu-id="30c46-145">WPF 类库</span><span class="sxs-lookup"><span data-stu-id="30c46-145">WPF Class library</span></span>                            | [<span data-ttu-id="30c46-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="30c46-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="30c46-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-147">[C#]</span></span>         | <span data-ttu-id="30c46-148">常用/WPF</span><span class="sxs-lookup"><span data-stu-id="30c46-148">Common/WPF</span></span>                            | <span data-ttu-id="30c46-149">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-149">3.0</span></span>        |
| <span data-ttu-id="30c46-150">WPF 自定义控件库</span><span class="sxs-lookup"><span data-stu-id="30c46-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="30c46-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="30c46-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="30c46-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-152">[C#]</span></span>         | <span data-ttu-id="30c46-153">常用/WPF</span><span class="sxs-lookup"><span data-stu-id="30c46-153">Common/WPF</span></span>                            | <span data-ttu-id="30c46-154">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-154">3.0</span></span>        |
| <span data-ttu-id="30c46-155">WPF 用户控件库</span><span class="sxs-lookup"><span data-stu-id="30c46-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="30c46-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="30c46-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="30c46-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-157">[C#]</span></span>         | <span data-ttu-id="30c46-158">常用/WPF</span><span class="sxs-lookup"><span data-stu-id="30c46-158">Common/WPF</span></span>                            | <span data-ttu-id="30c46-159">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-159">3.0</span></span>        |
| <span data-ttu-id="30c46-160">Windows 窗体 (WinForms) 应用程序</span><span class="sxs-lookup"><span data-stu-id="30c46-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="30c46-161">winforms</span><span class="sxs-lookup"><span data-stu-id="30c46-161">winforms</span></span>](#winforms)           | <span data-ttu-id="30c46-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-162">[C#]</span></span>         | <span data-ttu-id="30c46-163">常用/WinForms</span><span class="sxs-lookup"><span data-stu-id="30c46-163">Common/WinForms</span></span>                       | <span data-ttu-id="30c46-164">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-164">3.0</span></span>        |
| <span data-ttu-id="30c46-165">Windows 窗体 (WinForms) 类库</span><span class="sxs-lookup"><span data-stu-id="30c46-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="30c46-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="30c46-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="30c46-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-167">[C#]</span></span>         | <span data-ttu-id="30c46-168">常用/WinForms</span><span class="sxs-lookup"><span data-stu-id="30c46-168">Common/WinForms</span></span>                       | <span data-ttu-id="30c46-169">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-169">3.0</span></span>        |
| <span data-ttu-id="30c46-170">Worker Service</span><span class="sxs-lookup"><span data-stu-id="30c46-170">Worker Service</span></span>                               | [<span data-ttu-id="30c46-171">worker</span><span class="sxs-lookup"><span data-stu-id="30c46-171">worker</span></span>](#web-others)           | <span data-ttu-id="30c46-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-172">[C#]</span></span>         | <span data-ttu-id="30c46-173">常用/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="30c46-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="30c46-174">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-174">3.0</span></span>        |
| <span data-ttu-id="30c46-175">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="30c46-175">Unit Test Project</span></span>                            | [<span data-ttu-id="30c46-176">mstest</span><span class="sxs-lookup"><span data-stu-id="30c46-176">mstest</span></span>](#test)                 | <span data-ttu-id="30c46-177">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="30c46-177">[C#], F#, VB</span></span> | <span data-ttu-id="30c46-178">测试/MSTest</span><span class="sxs-lookup"><span data-stu-id="30c46-178">Test/MSTest</span></span>                           | <span data-ttu-id="30c46-179">1.0</span><span class="sxs-lookup"><span data-stu-id="30c46-179">1.0</span></span>        |
| <span data-ttu-id="30c46-180">NUnit 3 测试项目</span><span class="sxs-lookup"><span data-stu-id="30c46-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="30c46-181">nunit</span><span class="sxs-lookup"><span data-stu-id="30c46-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="30c46-182">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="30c46-182">[C#], F#, VB</span></span> | <span data-ttu-id="30c46-183">测试/NUnit</span><span class="sxs-lookup"><span data-stu-id="30c46-183">Test/NUnit</span></span>                            | <span data-ttu-id="30c46-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="30c46-184">2.1.400</span></span>    |
| <span data-ttu-id="30c46-185">NUnit 3 测试项</span><span class="sxs-lookup"><span data-stu-id="30c46-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="30c46-186">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="30c46-186">[C#], F#, VB</span></span> | <span data-ttu-id="30c46-187">测试/NUnit</span><span class="sxs-lookup"><span data-stu-id="30c46-187">Test/NUnit</span></span>                            | <span data-ttu-id="30c46-188">2.2</span><span class="sxs-lookup"><span data-stu-id="30c46-188">2.2</span></span>        |
| <span data-ttu-id="30c46-189">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="30c46-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="30c46-190">xunit</span><span class="sxs-lookup"><span data-stu-id="30c46-190">xunit</span></span>](#test)                  | <span data-ttu-id="30c46-191">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="30c46-191">[C#], F#, VB</span></span> | <span data-ttu-id="30c46-192">测试/xUnit</span><span class="sxs-lookup"><span data-stu-id="30c46-192">Test/xUnit</span></span>                            | <span data-ttu-id="30c46-193">1.0</span><span class="sxs-lookup"><span data-stu-id="30c46-193">1.0</span></span>        |
| <span data-ttu-id="30c46-194">Razor 组件</span><span class="sxs-lookup"><span data-stu-id="30c46-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="30c46-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-195">[C#]</span></span>         | <span data-ttu-id="30c46-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="30c46-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="30c46-197">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-197">3.0</span></span>        |
| <span data-ttu-id="30c46-198">Razor 页</span><span class="sxs-lookup"><span data-stu-id="30c46-198">Razor Page</span></span>                                   | [<span data-ttu-id="30c46-199">page</span><span class="sxs-lookup"><span data-stu-id="30c46-199">page</span></span>](#page)                   | <span data-ttu-id="30c46-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-200">[C#]</span></span>         | <span data-ttu-id="30c46-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="30c46-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="30c46-202">2.0</span><span class="sxs-lookup"><span data-stu-id="30c46-202">2.0</span></span>        |
| <span data-ttu-id="30c46-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="30c46-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="30c46-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="30c46-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="30c46-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-205">[C#]</span></span>         | <span data-ttu-id="30c46-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="30c46-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="30c46-207">2.0</span><span class="sxs-lookup"><span data-stu-id="30c46-207">2.0</span></span>        |
| <span data-ttu-id="30c46-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="30c46-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="30c46-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-209">[C#]</span></span>         | <span data-ttu-id="30c46-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="30c46-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="30c46-211">2.0</span><span class="sxs-lookup"><span data-stu-id="30c46-211">2.0</span></span>        |
| <span data-ttu-id="30c46-212">Blazor Server 应用</span><span class="sxs-lookup"><span data-stu-id="30c46-212">Blazor Server App</span></span>                            | [<span data-ttu-id="30c46-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="30c46-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="30c46-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-214">[C#]</span></span>         | <span data-ttu-id="30c46-215">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="30c46-215">Web/Blazor</span></span>                            | <span data-ttu-id="30c46-216">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-216">3.0</span></span>        |
| <span data-ttu-id="30c46-217">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="30c46-217">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="30c46-218">web</span><span class="sxs-lookup"><span data-stu-id="30c46-218">web</span></span>](#web)                     | <span data-ttu-id="30c46-219">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="30c46-219">[C#], F#</span></span>     | <span data-ttu-id="30c46-220">Web/空</span><span class="sxs-lookup"><span data-stu-id="30c46-220">Web/Empty</span></span>                             | <span data-ttu-id="30c46-221">1.0</span><span class="sxs-lookup"><span data-stu-id="30c46-221">1.0</span></span>        |
| <span data-ttu-id="30c46-222">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="30c46-222">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="30c46-223">mvc</span><span class="sxs-lookup"><span data-stu-id="30c46-223">mvc</span></span>](#web-options)             | <span data-ttu-id="30c46-224">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="30c46-224">[C#], F#</span></span>     | <span data-ttu-id="30c46-225">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="30c46-225">Web/MVC</span></span>                               | <span data-ttu-id="30c46-226">1.0</span><span class="sxs-lookup"><span data-stu-id="30c46-226">1.0</span></span>        |
| <span data-ttu-id="30c46-227">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="30c46-227">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="30c46-228">webapp、razor</span><span class="sxs-lookup"><span data-stu-id="30c46-228">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="30c46-229">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-229">[C#]</span></span>         | <span data-ttu-id="30c46-230">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="30c46-230">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="30c46-231">2.2、2.0</span><span class="sxs-lookup"><span data-stu-id="30c46-231">2.2, 2.0</span></span>   |
| <span data-ttu-id="30c46-232">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="30c46-232">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="30c46-233">angular</span><span class="sxs-lookup"><span data-stu-id="30c46-233">angular</span></span>](#spa)                 | <span data-ttu-id="30c46-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-234">[C#]</span></span>         | <span data-ttu-id="30c46-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="30c46-235">Web/MVC/SPA</span></span>                           | <span data-ttu-id="30c46-236">2.0</span><span class="sxs-lookup"><span data-stu-id="30c46-236">2.0</span></span>        |
| <span data-ttu-id="30c46-237">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="30c46-237">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="30c46-238">react</span><span class="sxs-lookup"><span data-stu-id="30c46-238">react</span></span>](#spa)                   | <span data-ttu-id="30c46-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-239">[C#]</span></span>         | <span data-ttu-id="30c46-240">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="30c46-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="30c46-241">2.0</span><span class="sxs-lookup"><span data-stu-id="30c46-241">2.0</span></span>        |
| <span data-ttu-id="30c46-242">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="30c46-242">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="30c46-243">reactredux</span><span class="sxs-lookup"><span data-stu-id="30c46-243">reactredux</span></span>](#reactredux)       | <span data-ttu-id="30c46-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-244">[C#]</span></span>         | <span data-ttu-id="30c46-245">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="30c46-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="30c46-246">2.0</span><span class="sxs-lookup"><span data-stu-id="30c46-246">2.0</span></span>        |
| <span data-ttu-id="30c46-247">Razor 类库</span><span class="sxs-lookup"><span data-stu-id="30c46-247">Razor Class Library</span></span>                          | [<span data-ttu-id="30c46-248">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="30c46-248">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="30c46-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-249">[C#]</span></span>         | <span data-ttu-id="30c46-250">Web/Razor/库/Razor 类库</span><span class="sxs-lookup"><span data-stu-id="30c46-250">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="30c46-251">2.1</span><span class="sxs-lookup"><span data-stu-id="30c46-251">2.1</span></span>        |
| <span data-ttu-id="30c46-252">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="30c46-252">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="30c46-253">webapi</span><span class="sxs-lookup"><span data-stu-id="30c46-253">webapi</span></span>](#webapi)               | <span data-ttu-id="30c46-254">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="30c46-254">[C#], F#</span></span>     | <span data-ttu-id="30c46-255">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="30c46-255">Web/WebAPI</span></span>                            | <span data-ttu-id="30c46-256">1.0</span><span class="sxs-lookup"><span data-stu-id="30c46-256">1.0</span></span>        |
| <span data-ttu-id="30c46-257">ASP.NET Core gRPC 服务</span><span class="sxs-lookup"><span data-stu-id="30c46-257">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="30c46-258">grpc</span><span class="sxs-lookup"><span data-stu-id="30c46-258">grpc</span></span>](#web-others)             | <span data-ttu-id="30c46-259">[C#]</span><span class="sxs-lookup"><span data-stu-id="30c46-259">[C#]</span></span>         | <span data-ttu-id="30c46-260">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="30c46-260">Web/gRPC</span></span>                              | <span data-ttu-id="30c46-261">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-261">3.0</span></span>        |
| <span data-ttu-id="30c46-262">dotnet gitignore 文件</span><span class="sxs-lookup"><span data-stu-id="30c46-262">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="30c46-263">配置</span><span class="sxs-lookup"><span data-stu-id="30c46-263">Config</span></span>                                | <span data-ttu-id="30c46-264">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-264">3.0</span></span>        |
| <span data-ttu-id="30c46-265">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="30c46-265">global.json file</span></span>                             | [<span data-ttu-id="30c46-266">globaljson</span><span class="sxs-lookup"><span data-stu-id="30c46-266">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="30c46-267">配置</span><span class="sxs-lookup"><span data-stu-id="30c46-267">Config</span></span>                                | <span data-ttu-id="30c46-268">2.0</span><span class="sxs-lookup"><span data-stu-id="30c46-268">2.0</span></span>        |
| <span data-ttu-id="30c46-269">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="30c46-269">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="30c46-270">配置</span><span class="sxs-lookup"><span data-stu-id="30c46-270">Config</span></span>                                | <span data-ttu-id="30c46-271">1.0</span><span class="sxs-lookup"><span data-stu-id="30c46-271">1.0</span></span>        |
| <span data-ttu-id="30c46-272">Dotnet 本地工具清单文件</span><span class="sxs-lookup"><span data-stu-id="30c46-272">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="30c46-273">配置</span><span class="sxs-lookup"><span data-stu-id="30c46-273">Config</span></span>                                | <span data-ttu-id="30c46-274">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-274">3.0</span></span>        |
| <span data-ttu-id="30c46-275">Web 配置</span><span class="sxs-lookup"><span data-stu-id="30c46-275">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="30c46-276">配置</span><span class="sxs-lookup"><span data-stu-id="30c46-276">Config</span></span>                                | <span data-ttu-id="30c46-277">1.0</span><span class="sxs-lookup"><span data-stu-id="30c46-277">1.0</span></span>        |
| <span data-ttu-id="30c46-278">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="30c46-278">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="30c46-279">解决方案</span><span class="sxs-lookup"><span data-stu-id="30c46-279">Solution</span></span>                              | <span data-ttu-id="30c46-280">1.0</span><span class="sxs-lookup"><span data-stu-id="30c46-280">1.0</span></span>        |
| <span data-ttu-id="30c46-281">协议缓冲区文件</span><span class="sxs-lookup"><span data-stu-id="30c46-281">Protocol Buffer File</span></span>                         | [<span data-ttu-id="30c46-282">proto</span><span class="sxs-lookup"><span data-stu-id="30c46-282">proto</span></span>](#namespace)             |              | <span data-ttu-id="30c46-283">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="30c46-283">Web/gRPC</span></span>                              | <span data-ttu-id="30c46-284">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-284">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="30c46-285">选项</span><span class="sxs-lookup"><span data-stu-id="30c46-285">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="30c46-286">显示有关以下内容的摘要：给定命令运行导致模板创建时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="30c46-286">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="30c46-287">自 .NET Core 2.2 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-287">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="30c46-288">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="30c46-288">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="30c46-289">当选择的模板将覆盖输出目录中的现有文件时，需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="30c46-289">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="30c46-290">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="30c46-290">Prints out help for the command.</span></span> <span data-ttu-id="30c46-291">可针对 `dotnet new` 命令本身或任何模板调用它。</span><span class="sxs-lookup"><span data-stu-id="30c46-291">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="30c46-292">例如 `dotnet new mvc --help`。</span><span class="sxs-lookup"><span data-stu-id="30c46-292">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="30c46-293">从提供的 `PATH` 或 `NUGET_ID` 安装模板包。</span><span class="sxs-lookup"><span data-stu-id="30c46-293">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="30c46-294">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="30c46-294">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="30c46-295">默认情况下，`dotnet new` 为该版本传递 \*，它表示最新的稳定包版本。</span><span class="sxs-lookup"><span data-stu-id="30c46-295">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="30c46-296">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="30c46-296">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="30c46-297">如果在运行此命令时已经安装了模板的某个版本，则该模板将更新到指定版本，如果没有指定版本，则将更新到最新的稳定版本。</span><span class="sxs-lookup"><span data-stu-id="30c46-297">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="30c46-298">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="30c46-298">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="30c46-299">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="30c46-299">Lists templates containing the specified name.</span></span> <span data-ttu-id="30c46-300">如果未指定名称，则列出所有模板。</span><span class="sxs-lookup"><span data-stu-id="30c46-300">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="30c46-301">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="30c46-301">The language of the template to create.</span></span> <span data-ttu-id="30c46-302">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="30c46-302">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="30c46-303">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="30c46-303">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="30c46-304">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="30c46-304">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="30c46-305">在这些情况下，请将语言参数值括在引号中。</span><span class="sxs-lookup"><span data-stu-id="30c46-305">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="30c46-306">例如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="30c46-306">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="30c46-307">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="30c46-307">The name for the created output.</span></span> <span data-ttu-id="30c46-308">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="30c46-308">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="30c46-309">指定在安装期间要使用的 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="30c46-309">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="30c46-310">自 .NET Core 2.1 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-310">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="30c46-311">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="30c46-311">Location to place the generated output.</span></span> <span data-ttu-id="30c46-312">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="30c46-312">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="30c46-313">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="30c46-313">Filters templates based on available types.</span></span> <span data-ttu-id="30c46-314">预定义的值为 `project`、`item` 和 `other`。</span><span class="sxs-lookup"><span data-stu-id="30c46-314">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="30c46-315">在提供的 `PATH` 或 `NUGET_ID` 中卸载模板包。</span><span class="sxs-lookup"><span data-stu-id="30c46-315">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="30c46-316">如果未指定 `<PATH|NUGET_ID>` 值，将显示所有当前安装的模板包及其关联的模板。</span><span class="sxs-lookup"><span data-stu-id="30c46-316">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="30c46-317">指定 `NUGET_ID` 时，请勿包含版本号。</span><span class="sxs-lookup"><span data-stu-id="30c46-317">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="30c46-318">如果未指定此选项的参数，该命令将列出已安装的模板及其详细信息。</span><span class="sxs-lookup"><span data-stu-id="30c46-318">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="30c46-319">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="30c46-319">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="30c46-320">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp  有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp  无效。</span><span class="sxs-lookup"><span data-stu-id="30c46-320">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="30c46-321">模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="30c46-321">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="30c46-322">检查是否有可用于当前安装的模板包的更新并安装这些更新。</span><span class="sxs-lookup"><span data-stu-id="30c46-322">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="30c46-323">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-323">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="30c46-324">检查是否有可用于当前安装的模板包的更新。</span><span class="sxs-lookup"><span data-stu-id="30c46-324">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="30c46-325">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-325">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="30c46-326">模板选项</span><span class="sxs-lookup"><span data-stu-id="30c46-326">Template options</span></span>

<span data-ttu-id="30c46-327">每个项目模板都可能有附加选项。</span><span class="sxs-lookup"><span data-stu-id="30c46-327">Each project template may have additional options available.</span></span> <span data-ttu-id="30c46-328">核心模板有以下附加选项：</span><span class="sxs-lookup"><span data-stu-id="30c46-328">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="30c46-329">控制台</span><span class="sxs-lookup"><span data-stu-id="30c46-329">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="30c46-330">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="30c46-330">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="30c46-331">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-331">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="30c46-332">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="30c46-332">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="30c46-333">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="30c46-333">SDK version</span></span> | <span data-ttu-id="30c46-334">默认值</span><span class="sxs-lookup"><span data-stu-id="30c46-334">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="30c46-335">3.1</span><span class="sxs-lookup"><span data-stu-id="30c46-335">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="30c46-336">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-336">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="30c46-337">在已创建的项目文件中设置 `LangVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="30c46-337">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="30c46-338">例如，使用 `--langVersion 7.3` 以使用 C# 7.3。</span><span class="sxs-lookup"><span data-stu-id="30c46-338">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="30c46-339">不支持 F#。</span><span class="sxs-lookup"><span data-stu-id="30c46-339">Not supported for F#.</span></span> <span data-ttu-id="30c46-340">自 .NET Core 2.2 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-340">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="30c46-341">有关默认的 C# 版本列表，请参阅[默认](../../csharp/language-reference/configure-language-version.md#defaults)。</span><span class="sxs-lookup"><span data-stu-id="30c46-341">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="30c46-342">如已指定，则在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="30c46-342">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="30c46-343">自 .NET Core 2.2 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-343">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="30c46-344">classlib</span><span class="sxs-lookup"><span data-stu-id="30c46-344">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="30c46-345">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="30c46-345">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="30c46-346">值：`netcoreapp<version>`（要创建 .NET Core 类库的话）或 `netstandard<version>`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="30c46-346">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="30c46-347">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="30c46-347">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="30c46-348">在已创建的项目文件中设置 `LangVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="30c46-348">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="30c46-349">例如，使用 `--langVersion 7.3` 以使用 C# 7.3。</span><span class="sxs-lookup"><span data-stu-id="30c46-349">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="30c46-350">不支持 F#。</span><span class="sxs-lookup"><span data-stu-id="30c46-350">Not supported for F#.</span></span> <span data-ttu-id="30c46-351">自 .NET Core 2.2 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-351">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="30c46-352">有关默认的 C# 版本列表，请参阅[默认](../../csharp/language-reference/configure-language-version.md#defaults)。</span><span class="sxs-lookup"><span data-stu-id="30c46-352">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="30c46-353">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="30c46-353">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="30c46-354">wpf、wpflib、wpfcustomcontrollib、wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="30c46-354">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="30c46-355">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="30c46-355">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="30c46-356">默认值为 `netcoreapp3.1`。</span><span class="sxs-lookup"><span data-stu-id="30c46-356">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="30c46-357">自 .NET Core 3.1 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-357">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="30c46-358">在已创建的项目文件中设置 `LangVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="30c46-358">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="30c46-359">例如，使用 `--langVersion 7.3` 以使用 C# 7.3。</span><span class="sxs-lookup"><span data-stu-id="30c46-359">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="30c46-360">有关默认的 C# 版本列表，请参阅[默认](../../csharp/language-reference/configure-language-version.md#defaults)。</span><span class="sxs-lookup"><span data-stu-id="30c46-360">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="30c46-361">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="30c46-361">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="30c46-362">winforms、winformslib</span><span class="sxs-lookup"><span data-stu-id="30c46-362">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="30c46-363">在已创建的项目文件中设置 `LangVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="30c46-363">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="30c46-364">例如，使用 `--langVersion 7.3` 以使用 C# 7.3。</span><span class="sxs-lookup"><span data-stu-id="30c46-364">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="30c46-365">有关默认的 C# 版本列表，请参阅[默认](../../csharp/language-reference/configure-language-version.md#defaults)。</span><span class="sxs-lookup"><span data-stu-id="30c46-365">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="30c46-366">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="30c46-366">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="30c46-367">worker、grpc</span><span class="sxs-lookup"><span data-stu-id="30c46-367">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="30c46-368">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="30c46-368">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="30c46-369">默认值为 `netcoreapp3.1`。</span><span class="sxs-lookup"><span data-stu-id="30c46-369">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="30c46-370">自 .NET Core 3.1 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-370">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="30c46-371">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="30c46-371">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="30c46-372">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="30c46-372">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="30c46-373">mstest、xunit</span><span class="sxs-lookup"><span data-stu-id="30c46-373">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="30c46-374">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="30c46-374">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="30c46-375">自 .NET Core 3.0 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="30c46-375">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="30c46-376">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="30c46-376">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="30c46-377">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="30c46-377">SDK version</span></span> | <span data-ttu-id="30c46-378">默认值</span><span class="sxs-lookup"><span data-stu-id="30c46-378">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="30c46-379">3.1</span><span class="sxs-lookup"><span data-stu-id="30c46-379">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="30c46-380">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-380">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="30c46-381">允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="30c46-381">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="30c46-382">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="30c46-382">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="30c46-383">nunit</span><span class="sxs-lookup"><span data-stu-id="30c46-383">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="30c46-384">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="30c46-384">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="30c46-385">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="30c46-385">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="30c46-386">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="30c46-386">SDK version</span></span> | <span data-ttu-id="30c46-387">默认值</span><span class="sxs-lookup"><span data-stu-id="30c46-387">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="30c46-388">3.1</span><span class="sxs-lookup"><span data-stu-id="30c46-388">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="30c46-389">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-389">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="30c46-390">2.2</span><span class="sxs-lookup"><span data-stu-id="30c46-390">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="30c46-391">2.1</span><span class="sxs-lookup"><span data-stu-id="30c46-391">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="30c46-392">允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="30c46-392">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="30c46-393">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="30c46-393">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="30c46-394">页</span><span class="sxs-lookup"><span data-stu-id="30c46-394">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="30c46-395">已生成代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="30c46-395">Namespace for the generated code.</span></span> <span data-ttu-id="30c46-396">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="30c46-396">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="30c46-397">创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="30c46-397">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="30c46-398">viewimports、proto</span><span class="sxs-lookup"><span data-stu-id="30c46-398">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="30c46-399">已生成代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="30c46-399">Namespace for the generated code.</span></span> <span data-ttu-id="30c46-400">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="30c46-400">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="30c46-401">blazorserver</span><span class="sxs-lookup"><span data-stu-id="30c46-401">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="30c46-402">要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="30c46-402">The type of authentication to use.</span></span> <span data-ttu-id="30c46-403">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="30c46-403">The possible values are:</span></span>

  - <span data-ttu-id="30c46-404">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="30c46-404">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="30c46-405">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-405">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="30c46-406">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-406">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="30c46-407">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-407">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="30c46-408">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-408">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="30c46-409">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-409">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="30c46-410">要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="30c46-410">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="30c46-411">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-411">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="30c46-412">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="30c46-412">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="30c46-413">此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="30c46-413">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="30c46-414">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-414">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="30c46-415">此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="30c46-415">The reset password policy ID for this project.</span></span> <span data-ttu-id="30c46-416">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-416">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="30c46-417">此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="30c46-417">The edit profile policy ID for this project.</span></span> <span data-ttu-id="30c46-418">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-418">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="30c46-419">要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="30c46-419">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="30c46-420">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-420">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="30c46-421">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="30c46-421">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="30c46-422">此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="30c46-422">The Client ID for this project.</span></span> <span data-ttu-id="30c46-423">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-423">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="30c46-424">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="30c46-424">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="30c46-425">目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="30c46-425">The domain for the directory tenant.</span></span> <span data-ttu-id="30c46-426">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-426">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="30c46-427">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="30c46-427">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="30c46-428">要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="30c46-428">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="30c46-429">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-429">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="30c46-430">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="30c46-430">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="30c46-431">重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="30c46-431">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="30c46-432">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-432">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="30c46-433">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="30c46-433">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="30c46-434">允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="30c46-434">Allows this application read-access to the directory.</span></span> <span data-ttu-id="30c46-435">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-435">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="30c46-436">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="30c46-436">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="30c46-437">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="30c46-437">Turns off HTTPS.</span></span> <span data-ttu-id="30c46-438">此选项仅适用于 `Individual`、`IndividualB2C`、`SingleOrg` 和 `MultiOrg` 未用于 `--auth` 的情况。</span><span class="sxs-lookup"><span data-stu-id="30c46-438">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="30c46-439">指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="30c46-439">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="30c46-440">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-440">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="30c46-441">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="30c46-441">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="30c46-442">Web</span><span class="sxs-lookup"><span data-stu-id="30c46-442">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="30c46-443">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="30c46-443">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="30c46-444">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="30c46-444">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="30c46-445">选项在 .NET Core 2.2 SDK 中不可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-445">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="30c46-446">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="30c46-446">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="30c46-447">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="30c46-447">SDK version</span></span> | <span data-ttu-id="30c46-448">默认值</span><span class="sxs-lookup"><span data-stu-id="30c46-448">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="30c46-449">3.1</span><span class="sxs-lookup"><span data-stu-id="30c46-449">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="30c46-450">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-450">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="30c46-451">2.1</span><span class="sxs-lookup"><span data-stu-id="30c46-451">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="30c46-452">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="30c46-452">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="30c46-453">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="30c46-453">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="30c46-454">mvc、webapp</span><span class="sxs-lookup"><span data-stu-id="30c46-454">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="30c46-455">要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="30c46-455">The type of authentication to use.</span></span> <span data-ttu-id="30c46-456">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="30c46-456">The possible values are:</span></span>

  - <span data-ttu-id="30c46-457">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="30c46-457">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="30c46-458">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-458">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="30c46-459">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-459">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="30c46-460">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-460">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="30c46-461">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-461">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="30c46-462">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-462">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="30c46-463">要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="30c46-463">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="30c46-464">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-464">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="30c46-465">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="30c46-465">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="30c46-466">此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="30c46-466">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="30c46-467">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-467">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="30c46-468">此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="30c46-468">The reset password policy ID for this project.</span></span> <span data-ttu-id="30c46-469">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-469">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="30c46-470">此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="30c46-470">The edit profile policy ID for this project.</span></span> <span data-ttu-id="30c46-471">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-471">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="30c46-472">要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="30c46-472">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="30c46-473">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-473">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="30c46-474">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="30c46-474">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="30c46-475">此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="30c46-475">The Client ID for this project.</span></span> <span data-ttu-id="30c46-476">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-476">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="30c46-477">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="30c46-477">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="30c46-478">目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="30c46-478">The domain for the directory tenant.</span></span> <span data-ttu-id="30c46-479">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-479">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="30c46-480">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="30c46-480">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="30c46-481">要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="30c46-481">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="30c46-482">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-482">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="30c46-483">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="30c46-483">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="30c46-484">重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="30c46-484">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="30c46-485">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-485">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="30c46-486">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="30c46-486">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="30c46-487">允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="30c46-487">Allows this application read-access to the directory.</span></span> <span data-ttu-id="30c46-488">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-488">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="30c46-489">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="30c46-489">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="30c46-490">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="30c46-490">Turns off HTTPS.</span></span> <span data-ttu-id="30c46-491">此选项仅适用于未使用 `Individual`、`IndividualB2C`、`SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="30c46-491">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="30c46-492">指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="30c46-492">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="30c46-493">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-493">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="30c46-494">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="30c46-494">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="30c46-495">自 .NET Core 3.0 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="30c46-495">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="30c46-496">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="30c46-496">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="30c46-497">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="30c46-497">SDK version</span></span> | <span data-ttu-id="30c46-498">默认值</span><span class="sxs-lookup"><span data-stu-id="30c46-498">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="30c46-499">3.1</span><span class="sxs-lookup"><span data-stu-id="30c46-499">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="30c46-500">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-500">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="30c46-501">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="30c46-501">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="30c46-502">在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="30c46-502">Includes BrowserLink in the project.</span></span> <span data-ttu-id="30c46-503">选项在 .NET Core 2.2 和 3.1 SDK 中不可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-503">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="30c46-504">确定项目是否配置为在调试生成中使用 [Razor 运行时编译](/aspnet/core/mvc/views/view-compilation#runtime-compilation)。</span><span class="sxs-lookup"><span data-stu-id="30c46-504">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="30c46-505">自 .NET Core 3.1.201 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="30c46-505">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="30c46-506">angular、react</span><span class="sxs-lookup"><span data-stu-id="30c46-506">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="30c46-507">要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="30c46-507">The type of authentication to use.</span></span> <span data-ttu-id="30c46-508">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-508">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="30c46-509">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="30c46-509">The possible values are:</span></span>

  - <span data-ttu-id="30c46-510">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="30c46-510">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="30c46-511">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-511">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="30c46-512">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="30c46-512">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="30c46-513">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="30c46-513">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="30c46-514">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="30c46-514">Turns off HTTPS.</span></span> <span data-ttu-id="30c46-515">仅当身份验证为 `None` 时，此选项才适用。</span><span class="sxs-lookup"><span data-stu-id="30c46-515">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="30c46-516">指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="30c46-516">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="30c46-517">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-517">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="30c46-518">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-518">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="30c46-519">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="30c46-519">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="30c46-520">选项在 .NET Core 2.2 SDK 中不可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-520">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="30c46-521">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="30c46-521">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="30c46-522">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="30c46-522">SDK version</span></span> | <span data-ttu-id="30c46-523">默认值</span><span class="sxs-lookup"><span data-stu-id="30c46-523">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="30c46-524">3.1</span><span class="sxs-lookup"><span data-stu-id="30c46-524">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="30c46-525">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-525">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="30c46-526">2.1</span><span class="sxs-lookup"><span data-stu-id="30c46-526">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="30c46-527">reactredux</span><span class="sxs-lookup"><span data-stu-id="30c46-527">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="30c46-528">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="30c46-528">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="30c46-529">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="30c46-529">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="30c46-530">选项在 .NET Core 2.2 SDK 中不可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-530">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="30c46-531">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="30c46-531">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="30c46-532">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="30c46-532">SDK version</span></span> | <span data-ttu-id="30c46-533">默认值</span><span class="sxs-lookup"><span data-stu-id="30c46-533">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="30c46-534">3.1</span><span class="sxs-lookup"><span data-stu-id="30c46-534">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="30c46-535">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-535">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="30c46-536">2.1</span><span class="sxs-lookup"><span data-stu-id="30c46-536">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="30c46-537">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="30c46-537">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="30c46-538">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="30c46-538">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="30c46-539">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="30c46-539">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="30c46-540">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="30c46-540">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="30c46-541">除了将组件添加到此库以外，还支持添加传统的 Razor 页面和视图。</span><span class="sxs-lookup"><span data-stu-id="30c46-541">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="30c46-542">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-542">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="30c46-543">webapi</span><span class="sxs-lookup"><span data-stu-id="30c46-543">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="30c46-544">要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="30c46-544">The type of authentication to use.</span></span> <span data-ttu-id="30c46-545">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="30c46-545">The possible values are:</span></span>

  - <span data-ttu-id="30c46-546">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="30c46-546">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="30c46-547">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-547">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="30c46-548">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-548">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="30c46-549">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-549">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="30c46-550">要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="30c46-550">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="30c46-551">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-551">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="30c46-552">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="30c46-552">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="30c46-553">此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="30c46-553">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="30c46-554">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-554">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="30c46-555">要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="30c46-555">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="30c46-556">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-556">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="30c46-557">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="30c46-557">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="30c46-558">此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="30c46-558">The Client ID for this project.</span></span> <span data-ttu-id="30c46-559">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-559">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="30c46-560">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="30c46-560">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="30c46-561">目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="30c46-561">The domain for the directory tenant.</span></span> <span data-ttu-id="30c46-562">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-562">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="30c46-563">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="30c46-563">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="30c46-564">要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="30c46-564">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="30c46-565">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="30c46-565">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="30c46-566">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="30c46-566">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="30c46-567">允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="30c46-567">Allows this application read-access to the directory.</span></span> <span data-ttu-id="30c46-568">仅适用于 `SingleOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-568">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="30c46-569">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="30c46-569">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="30c46-570">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="30c46-570">Turns off HTTPS.</span></span> <span data-ttu-id="30c46-571">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="30c46-571">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="30c46-572">此选项仅适用于 `IndividualB2C` 或 `SingleOrg` 未用于身份验证的情况。</span><span class="sxs-lookup"><span data-stu-id="30c46-572">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="30c46-573">指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="30c46-573">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="30c46-574">仅适用于 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="30c46-574">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="30c46-575">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="30c46-575">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="30c46-576">选项在 .NET Core 2.2 SDK 中不可用。</span><span class="sxs-lookup"><span data-stu-id="30c46-576">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="30c46-577">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="30c46-577">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="30c46-578">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="30c46-578">SDK version</span></span> | <span data-ttu-id="30c46-579">默认值</span><span class="sxs-lookup"><span data-stu-id="30c46-579">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="30c46-580">3.1</span><span class="sxs-lookup"><span data-stu-id="30c46-580">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="30c46-581">3.0</span><span class="sxs-lookup"><span data-stu-id="30c46-581">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="30c46-582">2.1</span><span class="sxs-lookup"><span data-stu-id="30c46-582">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="30c46-583">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="30c46-583">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="30c46-584">globaljson</span><span class="sxs-lookup"><span data-stu-id="30c46-584">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="30c46-585">指定要在 global.json  文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="30c46-585">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="30c46-586">示例</span><span class="sxs-lookup"><span data-stu-id="30c46-586">Examples</span></span>

- <span data-ttu-id="30c46-587">通过指定模板名称，创建 C# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="30c46-587">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="30c46-588">在当前目录中创建 F# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="30c46-588">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="30c46-589">在指定的目录中创建 .NET Standard 类库项目：</span><span class="sxs-lookup"><span data-stu-id="30c46-589">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="30c46-590">在当前目录中新建没有设置身份验证的 ASP.NET Core C# MVC 项目：</span><span class="sxs-lookup"><span data-stu-id="30c46-590">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="30c46-591">创建新的 xUnit 项目：</span><span class="sxs-lookup"><span data-stu-id="30c46-591">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="30c46-592">列出可用于单页应用程序 (SPA) 模板的所有模板：</span><span class="sxs-lookup"><span data-stu-id="30c46-592">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="30c46-593">列出与“we”子字符串匹配的所有模板  。</span><span class="sxs-lookup"><span data-stu-id="30c46-593">List all templates matching the *we* substring.</span></span> <span data-ttu-id="30c46-594">找不到完全匹配，因此子字符串匹配针对短名称和名称列运行。</span><span class="sxs-lookup"><span data-stu-id="30c46-594">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="30c46-595">尝试调用与 ng 匹配的模板  。</span><span class="sxs-lookup"><span data-stu-id="30c46-595">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="30c46-596">如果无法确定单个匹配项，请列出部分匹配项的模板。</span><span class="sxs-lookup"><span data-stu-id="30c46-596">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="30c46-597">安装 ASP.NET Core 的 SPA 模板 2.0 版：</span><span class="sxs-lookup"><span data-stu-id="30c46-597">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="30c46-598">列出已安装的模板及其详细信息，包括如何卸载它们：</span><span class="sxs-lookup"><span data-stu-id="30c46-598">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="30c46-599">在当前目录中创建 global.json  ，将 SDK 版本设置为 3.1.101：</span><span class="sxs-lookup"><span data-stu-id="30c46-599">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="30c46-600">请参阅</span><span class="sxs-lookup"><span data-stu-id="30c46-600">See also</span></span>

- [<span data-ttu-id="30c46-601">dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="30c46-601">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="30c46-602">创建 dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="30c46-602">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="30c46-603">dotnet/dotnet-template-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="30c46-603">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="30c46-604">dotnet new 可用模板</span><span class="sxs-lookup"><span data-stu-id="30c46-604">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
