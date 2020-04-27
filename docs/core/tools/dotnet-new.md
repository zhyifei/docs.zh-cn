---
title: dotnet new 命令
description: dotnet new 命令可根据指定模板新建 .NET Core 项目。
ms.date: 04/10/2020
ms.openlocfilehash: 1979f98a6005a414acc64c5eaa086a88aca9f033
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102822"
---
# <a name="dotnet-new"></a><span data-ttu-id="37b43-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="37b43-103">dotnet new</span></span>

<span data-ttu-id="37b43-104"> 本文适用于： ✔️ .NET Core 2.0 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="37b43-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="37b43-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="37b43-105">Name</span></span>

<span data-ttu-id="37b43-106">`dotnet new` - 根据指定的模板，创建新的项目、配置文件或解决方案。</span><span class="sxs-lookup"><span data-stu-id="37b43-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="37b43-107">摘要</span><span class="sxs-lookup"><span data-stu-id="37b43-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {C#|F#|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="37b43-108">描述</span><span class="sxs-lookup"><span data-stu-id="37b43-108">Description</span></span>

<span data-ttu-id="37b43-109">`dotnet new` 命令基于模板创建 .NET Core 项目或其他项目。</span><span class="sxs-lookup"><span data-stu-id="37b43-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="37b43-110">命令调用[模板引擎](https://github.com/dotnet/templating)，以根据指定的模板和选项在磁盘上创建项目。</span><span class="sxs-lookup"><span data-stu-id="37b43-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="37b43-111">隐式还原</span><span class="sxs-lookup"><span data-stu-id="37b43-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="37b43-112">自变量</span><span class="sxs-lookup"><span data-stu-id="37b43-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="37b43-113">调用命令时要实例化的模板。</span><span class="sxs-lookup"><span data-stu-id="37b43-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="37b43-114">每个模板可能具有可传递的特定选项。</span><span class="sxs-lookup"><span data-stu-id="37b43-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="37b43-115">有关详细信息，请参阅[模板选项](#template-options)。</span><span class="sxs-lookup"><span data-stu-id="37b43-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="37b43-116">可以运行 `dotnet new --list` 以查看所有已安装模板的列表。</span><span class="sxs-lookup"><span data-stu-id="37b43-116">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="37b43-117">如果 `TEMPLATE` 值与返回表中的“模板”  或“短名称”  列中的文本不完全匹配，则会对这两列执行 substring 匹配。</span><span class="sxs-lookup"><span data-stu-id="37b43-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="37b43-118">从 .NET Core 3.0 SDK 开始，当你在以下情况下调用 `dotnet new` 命令时，CLI 将在 NuGet.org 中搜索模板：</span><span class="sxs-lookup"><span data-stu-id="37b43-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="37b43-119">如果在调用 `dotnet new` 时 CLI 找不到模板匹配项，即使是部分匹配也不行。</span><span class="sxs-lookup"><span data-stu-id="37b43-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="37b43-120">如果有较新版本的模板可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="37b43-121">在这种情况下，将创建项目或工件，但 CLI 会就模板的更新版本发出警告。</span><span class="sxs-lookup"><span data-stu-id="37b43-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="37b43-122">此命令包含默认的模板列表。</span><span class="sxs-lookup"><span data-stu-id="37b43-122">The command contains a default list of templates.</span></span> <span data-ttu-id="37b43-123">使用 `dotnet new -l` 获取可用模板的列表。</span><span class="sxs-lookup"><span data-stu-id="37b43-123">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="37b43-124">下表显示了随 .NET Core SDK 一起预安装的模板。</span><span class="sxs-lookup"><span data-stu-id="37b43-124">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="37b43-125">模板的默认语言显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="37b43-125">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="37b43-126">单击短名称链接可查看特定的模板选项。</span><span class="sxs-lookup"><span data-stu-id="37b43-126">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="37b43-127">模板</span><span class="sxs-lookup"><span data-stu-id="37b43-127">Templates</span></span>                                    | <span data-ttu-id="37b43-128">短名称</span><span class="sxs-lookup"><span data-stu-id="37b43-128">Short name</span></span>                      | <span data-ttu-id="37b43-129">语言</span><span class="sxs-lookup"><span data-stu-id="37b43-129">Language</span></span>     | <span data-ttu-id="37b43-130">Tags</span><span class="sxs-lookup"><span data-stu-id="37b43-130">Tags</span></span>                                  | <span data-ttu-id="37b43-131">已引入</span><span class="sxs-lookup"><span data-stu-id="37b43-131">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="37b43-132">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="37b43-132">Console Application</span></span>                          | [<span data-ttu-id="37b43-133">控制台</span><span class="sxs-lookup"><span data-stu-id="37b43-133">console</span></span>](#console)             | <span data-ttu-id="37b43-134">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="37b43-134">[C#], F#, VB</span></span> | <span data-ttu-id="37b43-135">常用/控制台</span><span class="sxs-lookup"><span data-stu-id="37b43-135">Common/Console</span></span>                        | <span data-ttu-id="37b43-136">1.0</span><span class="sxs-lookup"><span data-stu-id="37b43-136">1.0</span></span>        |
| <span data-ttu-id="37b43-137">类库</span><span class="sxs-lookup"><span data-stu-id="37b43-137">Class library</span></span>                                | [<span data-ttu-id="37b43-138">classlib</span><span class="sxs-lookup"><span data-stu-id="37b43-138">classlib</span></span>](#classlib)           | <span data-ttu-id="37b43-139">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="37b43-139">[C#], F#, VB</span></span> | <span data-ttu-id="37b43-140">常用/库</span><span class="sxs-lookup"><span data-stu-id="37b43-140">Common/Library</span></span>                        | <span data-ttu-id="37b43-141">1.0</span><span class="sxs-lookup"><span data-stu-id="37b43-141">1.0</span></span>        |
| <span data-ttu-id="37b43-142">WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="37b43-142">WPF Application</span></span>                              | [<span data-ttu-id="37b43-143">wpf</span><span class="sxs-lookup"><span data-stu-id="37b43-143">wpf</span></span>](#wpf)                     | <span data-ttu-id="37b43-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-144">[C#]</span></span>         | <span data-ttu-id="37b43-145">常用/WPF</span><span class="sxs-lookup"><span data-stu-id="37b43-145">Common/WPF</span></span>                            | <span data-ttu-id="37b43-146">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-146">3.0</span></span>        |
| <span data-ttu-id="37b43-147">WPF 类库</span><span class="sxs-lookup"><span data-stu-id="37b43-147">WPF Class library</span></span>                            | [<span data-ttu-id="37b43-148">wpflib</span><span class="sxs-lookup"><span data-stu-id="37b43-148">wpflib</span></span>](#wpf)                  | <span data-ttu-id="37b43-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-149">[C#]</span></span>         | <span data-ttu-id="37b43-150">常用/WPF</span><span class="sxs-lookup"><span data-stu-id="37b43-150">Common/WPF</span></span>                            | <span data-ttu-id="37b43-151">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-151">3.0</span></span>        |
| <span data-ttu-id="37b43-152">WPF 自定义控件库</span><span class="sxs-lookup"><span data-stu-id="37b43-152">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="37b43-153">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="37b43-153">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="37b43-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-154">[C#]</span></span>         | <span data-ttu-id="37b43-155">常用/WPF</span><span class="sxs-lookup"><span data-stu-id="37b43-155">Common/WPF</span></span>                            | <span data-ttu-id="37b43-156">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-156">3.0</span></span>        |
| <span data-ttu-id="37b43-157">WPF 用户控件库</span><span class="sxs-lookup"><span data-stu-id="37b43-157">WPF User Control Library</span></span>                     | [<span data-ttu-id="37b43-158">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="37b43-158">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="37b43-159">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-159">[C#]</span></span>         | <span data-ttu-id="37b43-160">常用/WPF</span><span class="sxs-lookup"><span data-stu-id="37b43-160">Common/WPF</span></span>                            | <span data-ttu-id="37b43-161">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-161">3.0</span></span>        |
| <span data-ttu-id="37b43-162">Windows 窗体 (WinForms) 应用程序</span><span class="sxs-lookup"><span data-stu-id="37b43-162">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="37b43-163">winforms</span><span class="sxs-lookup"><span data-stu-id="37b43-163">winforms</span></span>](#winforms)           | <span data-ttu-id="37b43-164">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-164">[C#]</span></span>         | <span data-ttu-id="37b43-165">常用/WinForms</span><span class="sxs-lookup"><span data-stu-id="37b43-165">Common/WinForms</span></span>                       | <span data-ttu-id="37b43-166">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-166">3.0</span></span>        |
| <span data-ttu-id="37b43-167">Windows 窗体 (WinForms) 类库</span><span class="sxs-lookup"><span data-stu-id="37b43-167">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="37b43-168">winformslib</span><span class="sxs-lookup"><span data-stu-id="37b43-168">winformslib</span></span>](#winforms)        | <span data-ttu-id="37b43-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-169">[C#]</span></span>         | <span data-ttu-id="37b43-170">常用/WinForms</span><span class="sxs-lookup"><span data-stu-id="37b43-170">Common/WinForms</span></span>                       | <span data-ttu-id="37b43-171">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-171">3.0</span></span>        |
| <span data-ttu-id="37b43-172">Worker Service</span><span class="sxs-lookup"><span data-stu-id="37b43-172">Worker Service</span></span>                               | [<span data-ttu-id="37b43-173">worker</span><span class="sxs-lookup"><span data-stu-id="37b43-173">worker</span></span>](#web-others)           | <span data-ttu-id="37b43-174">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-174">[C#]</span></span>         | <span data-ttu-id="37b43-175">常用/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="37b43-175">Common/Worker/Web</span></span>                     | <span data-ttu-id="37b43-176">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-176">3.0</span></span>        |
| <span data-ttu-id="37b43-177">单元测试项目</span><span class="sxs-lookup"><span data-stu-id="37b43-177">Unit Test Project</span></span>                            | [<span data-ttu-id="37b43-178">mstest</span><span class="sxs-lookup"><span data-stu-id="37b43-178">mstest</span></span>](#test)                 | <span data-ttu-id="37b43-179">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="37b43-179">[C#], F#, VB</span></span> | <span data-ttu-id="37b43-180">测试/MSTest</span><span class="sxs-lookup"><span data-stu-id="37b43-180">Test/MSTest</span></span>                           | <span data-ttu-id="37b43-181">1.0</span><span class="sxs-lookup"><span data-stu-id="37b43-181">1.0</span></span>        |
| <span data-ttu-id="37b43-182">NUnit 3 测试项目</span><span class="sxs-lookup"><span data-stu-id="37b43-182">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="37b43-183">nunit</span><span class="sxs-lookup"><span data-stu-id="37b43-183">nunit</span></span>](#nunit)                  | <span data-ttu-id="37b43-184">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="37b43-184">[C#], F#, VB</span></span> | <span data-ttu-id="37b43-185">测试/NUnit</span><span class="sxs-lookup"><span data-stu-id="37b43-185">Test/NUnit</span></span>                            | <span data-ttu-id="37b43-186">2.1.400</span><span class="sxs-lookup"><span data-stu-id="37b43-186">2.1.400</span></span>    |
| <span data-ttu-id="37b43-187">NUnit 3 测试项</span><span class="sxs-lookup"><span data-stu-id="37b43-187">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="37b43-188">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="37b43-188">[C#], F#, VB</span></span> | <span data-ttu-id="37b43-189">测试/NUnit</span><span class="sxs-lookup"><span data-stu-id="37b43-189">Test/NUnit</span></span>                            | <span data-ttu-id="37b43-190">2.2</span><span class="sxs-lookup"><span data-stu-id="37b43-190">2.2</span></span>        |
| <span data-ttu-id="37b43-191">xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="37b43-191">xUnit Test Project</span></span>                           | [<span data-ttu-id="37b43-192">xunit</span><span class="sxs-lookup"><span data-stu-id="37b43-192">xunit</span></span>](#test)                  | <span data-ttu-id="37b43-193">[C#]、F#、VB</span><span class="sxs-lookup"><span data-stu-id="37b43-193">[C#], F#, VB</span></span> | <span data-ttu-id="37b43-194">测试/xUnit</span><span class="sxs-lookup"><span data-stu-id="37b43-194">Test/xUnit</span></span>                            | <span data-ttu-id="37b43-195">1.0</span><span class="sxs-lookup"><span data-stu-id="37b43-195">1.0</span></span>        |
| <span data-ttu-id="37b43-196">Razor 组件</span><span class="sxs-lookup"><span data-stu-id="37b43-196">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="37b43-197">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-197">[C#]</span></span>         | <span data-ttu-id="37b43-198">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="37b43-198">Web/ASP.NET</span></span>                           | <span data-ttu-id="37b43-199">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-199">3.0</span></span>        |
| <span data-ttu-id="37b43-200">Razor 页</span><span class="sxs-lookup"><span data-stu-id="37b43-200">Razor Page</span></span>                                   | [<span data-ttu-id="37b43-201">page</span><span class="sxs-lookup"><span data-stu-id="37b43-201">page</span></span>](#page)                   | <span data-ttu-id="37b43-202">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-202">[C#]</span></span>         | <span data-ttu-id="37b43-203">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="37b43-203">Web/ASP.NET</span></span>                           | <span data-ttu-id="37b43-204">2.0</span><span class="sxs-lookup"><span data-stu-id="37b43-204">2.0</span></span>        |
| <span data-ttu-id="37b43-205">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="37b43-205">MVC ViewImports</span></span>                              | [<span data-ttu-id="37b43-206">viewimports</span><span class="sxs-lookup"><span data-stu-id="37b43-206">viewimports</span></span>](#namespace)       | <span data-ttu-id="37b43-207">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-207">[C#]</span></span>         | <span data-ttu-id="37b43-208">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="37b43-208">Web/ASP.NET</span></span>                           | <span data-ttu-id="37b43-209">2.0</span><span class="sxs-lookup"><span data-stu-id="37b43-209">2.0</span></span>        |
| <span data-ttu-id="37b43-210">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="37b43-210">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="37b43-211">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-211">[C#]</span></span>         | <span data-ttu-id="37b43-212">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="37b43-212">Web/ASP.NET</span></span>                           | <span data-ttu-id="37b43-213">2.0</span><span class="sxs-lookup"><span data-stu-id="37b43-213">2.0</span></span>        |
| <span data-ttu-id="37b43-214">Blazor Server 应用</span><span class="sxs-lookup"><span data-stu-id="37b43-214">Blazor Server App</span></span>                            | [<span data-ttu-id="37b43-215">blazorserver</span><span class="sxs-lookup"><span data-stu-id="37b43-215">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="37b43-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-216">[C#]</span></span>         | <span data-ttu-id="37b43-217">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="37b43-217">Web/Blazor</span></span>                            | <span data-ttu-id="37b43-218">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-218">3.0</span></span>        |
| <span data-ttu-id="37b43-219">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="37b43-219">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="37b43-220">web</span><span class="sxs-lookup"><span data-stu-id="37b43-220">web</span></span>](#web)                     | <span data-ttu-id="37b43-221">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="37b43-221">[C#], F#</span></span>     | <span data-ttu-id="37b43-222">Web/空</span><span class="sxs-lookup"><span data-stu-id="37b43-222">Web/Empty</span></span>                             | <span data-ttu-id="37b43-223">1.0</span><span class="sxs-lookup"><span data-stu-id="37b43-223">1.0</span></span>        |
| <span data-ttu-id="37b43-224">ASP.NET Core Web 应用程序 (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="37b43-224">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="37b43-225">mvc</span><span class="sxs-lookup"><span data-stu-id="37b43-225">mvc</span></span>](#web-options)             | <span data-ttu-id="37b43-226">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="37b43-226">[C#], F#</span></span>     | <span data-ttu-id="37b43-227">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="37b43-227">Web/MVC</span></span>                               | <span data-ttu-id="37b43-228">1.0</span><span class="sxs-lookup"><span data-stu-id="37b43-228">1.0</span></span>        |
| <span data-ttu-id="37b43-229">ASP.NET Core Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="37b43-229">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="37b43-230">webapp、razor</span><span class="sxs-lookup"><span data-stu-id="37b43-230">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="37b43-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-231">[C#]</span></span>         | <span data-ttu-id="37b43-232">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="37b43-232">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="37b43-233">2.2、2.0</span><span class="sxs-lookup"><span data-stu-id="37b43-233">2.2, 2.0</span></span>   |
| <span data-ttu-id="37b43-234">含 Angular 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="37b43-234">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="37b43-235">angular</span><span class="sxs-lookup"><span data-stu-id="37b43-235">angular</span></span>](#spa)                 | <span data-ttu-id="37b43-236">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-236">[C#]</span></span>         | <span data-ttu-id="37b43-237">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="37b43-237">Web/MVC/SPA</span></span>                           | <span data-ttu-id="37b43-238">2.0</span><span class="sxs-lookup"><span data-stu-id="37b43-238">2.0</span></span>        |
| <span data-ttu-id="37b43-239">含 React.js 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="37b43-239">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="37b43-240">react</span><span class="sxs-lookup"><span data-stu-id="37b43-240">react</span></span>](#spa)                   | <span data-ttu-id="37b43-241">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-241">[C#]</span></span>         | <span data-ttu-id="37b43-242">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="37b43-242">Web/MVC/SPA</span></span>                           | <span data-ttu-id="37b43-243">2.0</span><span class="sxs-lookup"><span data-stu-id="37b43-243">2.0</span></span>        |
| <span data-ttu-id="37b43-244">含 React.js 和 Redux 的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="37b43-244">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="37b43-245">reactredux</span><span class="sxs-lookup"><span data-stu-id="37b43-245">reactredux</span></span>](#reactredux)       | <span data-ttu-id="37b43-246">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-246">[C#]</span></span>         | <span data-ttu-id="37b43-247">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="37b43-247">Web/MVC/SPA</span></span>                           | <span data-ttu-id="37b43-248">2.0</span><span class="sxs-lookup"><span data-stu-id="37b43-248">2.0</span></span>        |
| <span data-ttu-id="37b43-249">Razor 类库</span><span class="sxs-lookup"><span data-stu-id="37b43-249">Razor Class Library</span></span>                          | [<span data-ttu-id="37b43-250">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="37b43-250">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="37b43-251">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-251">[C#]</span></span>         | <span data-ttu-id="37b43-252">Web/Razor/库/Razor 类库</span><span class="sxs-lookup"><span data-stu-id="37b43-252">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="37b43-253">2.1</span><span class="sxs-lookup"><span data-stu-id="37b43-253">2.1</span></span>        |
| <span data-ttu-id="37b43-254">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="37b43-254">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="37b43-255">webapi</span><span class="sxs-lookup"><span data-stu-id="37b43-255">webapi</span></span>](#webapi)               | <span data-ttu-id="37b43-256">[C#]，F#</span><span class="sxs-lookup"><span data-stu-id="37b43-256">[C#], F#</span></span>     | <span data-ttu-id="37b43-257">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="37b43-257">Web/WebAPI</span></span>                            | <span data-ttu-id="37b43-258">1.0</span><span class="sxs-lookup"><span data-stu-id="37b43-258">1.0</span></span>        |
| <span data-ttu-id="37b43-259">ASP.NET Core gRPC 服务</span><span class="sxs-lookup"><span data-stu-id="37b43-259">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="37b43-260">grpc</span><span class="sxs-lookup"><span data-stu-id="37b43-260">grpc</span></span>](#web-others)             | <span data-ttu-id="37b43-261">[C#]</span><span class="sxs-lookup"><span data-stu-id="37b43-261">[C#]</span></span>         | <span data-ttu-id="37b43-262">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="37b43-262">Web/gRPC</span></span>                              | <span data-ttu-id="37b43-263">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-263">3.0</span></span>        |
| <span data-ttu-id="37b43-264">协议缓冲区文件</span><span class="sxs-lookup"><span data-stu-id="37b43-264">Protocol Buffer File</span></span>                         | [<span data-ttu-id="37b43-265">proto</span><span class="sxs-lookup"><span data-stu-id="37b43-265">proto</span></span>](#namespace)             |              | <span data-ttu-id="37b43-266">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="37b43-266">Web/gRPC</span></span>                              | <span data-ttu-id="37b43-267">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-267">3.0</span></span>        |
| <span data-ttu-id="37b43-268">dotnet gitignore 文件</span><span class="sxs-lookup"><span data-stu-id="37b43-268">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="37b43-269">配置</span><span class="sxs-lookup"><span data-stu-id="37b43-269">Config</span></span>                                | <span data-ttu-id="37b43-270">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-270">3.0</span></span>        |
| <span data-ttu-id="37b43-271">global.json 文件</span><span class="sxs-lookup"><span data-stu-id="37b43-271">global.json file</span></span>                             | [<span data-ttu-id="37b43-272">globaljson</span><span class="sxs-lookup"><span data-stu-id="37b43-272">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="37b43-273">配置</span><span class="sxs-lookup"><span data-stu-id="37b43-273">Config</span></span>                                | <span data-ttu-id="37b43-274">2.0</span><span class="sxs-lookup"><span data-stu-id="37b43-274">2.0</span></span>        |
| <span data-ttu-id="37b43-275">NuGet 配置</span><span class="sxs-lookup"><span data-stu-id="37b43-275">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="37b43-276">配置</span><span class="sxs-lookup"><span data-stu-id="37b43-276">Config</span></span>                                | <span data-ttu-id="37b43-277">1.0</span><span class="sxs-lookup"><span data-stu-id="37b43-277">1.0</span></span>        |
| <span data-ttu-id="37b43-278">dotnet 本地工具清单文件</span><span class="sxs-lookup"><span data-stu-id="37b43-278">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="37b43-279">配置</span><span class="sxs-lookup"><span data-stu-id="37b43-279">Config</span></span>                                | <span data-ttu-id="37b43-280">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-280">3.0</span></span>        |
| <span data-ttu-id="37b43-281">Web 配置</span><span class="sxs-lookup"><span data-stu-id="37b43-281">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="37b43-282">配置</span><span class="sxs-lookup"><span data-stu-id="37b43-282">Config</span></span>                                | <span data-ttu-id="37b43-283">1.0</span><span class="sxs-lookup"><span data-stu-id="37b43-283">1.0</span></span>        |
| <span data-ttu-id="37b43-284">解决方案文件</span><span class="sxs-lookup"><span data-stu-id="37b43-284">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="37b43-285">解决方案</span><span class="sxs-lookup"><span data-stu-id="37b43-285">Solution</span></span>                              | <span data-ttu-id="37b43-286">1.0</span><span class="sxs-lookup"><span data-stu-id="37b43-286">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="37b43-287">选项</span><span class="sxs-lookup"><span data-stu-id="37b43-287">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="37b43-288">显示有关以下内容的摘要：给定命令运行时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="37b43-288">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="37b43-289">自 .NET Core 2.2 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-289">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="37b43-290">强制生成内容，即使会更改现有文件，也不例外。</span><span class="sxs-lookup"><span data-stu-id="37b43-290">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="37b43-291">当选择的模板将覆盖输出目录中的现有文件时，需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="37b43-291">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="37b43-292">打印命令帮助。</span><span class="sxs-lookup"><span data-stu-id="37b43-292">Prints out help for the command.</span></span> <span data-ttu-id="37b43-293">可针对 `dotnet new` 命令本身或任何模板调用它。</span><span class="sxs-lookup"><span data-stu-id="37b43-293">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="37b43-294">例如 `dotnet new mvc --help`。</span><span class="sxs-lookup"><span data-stu-id="37b43-294">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="37b43-295">从提供的 `PATH` 或 `NUGET_ID` 安装模板包。</span><span class="sxs-lookup"><span data-stu-id="37b43-295">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="37b43-296">若要安装模板包的预发布版本，需要以 `<package-name>::<package-version>` 格式指定该版本。</span><span class="sxs-lookup"><span data-stu-id="37b43-296">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="37b43-297">默认情况下，`dotnet new` 为该版本传递 \*，它表示最新的稳定包版本。</span><span class="sxs-lookup"><span data-stu-id="37b43-297">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="37b43-298">请在[示例](#examples)部分查看示例。</span><span class="sxs-lookup"><span data-stu-id="37b43-298">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="37b43-299">如果在运行此命令时已经安装了模板的某个版本，则该模板将更新到指定版本，如果没有指定版本，则将更新到最新的稳定版本。</span><span class="sxs-lookup"><span data-stu-id="37b43-299">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="37b43-300">若要了解如何创建自定义模板，请参阅 [dotnet new 自定义模板](custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="37b43-300">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="37b43-301">列出包含指定名称的模板。</span><span class="sxs-lookup"><span data-stu-id="37b43-301">Lists templates containing the specified name.</span></span> <span data-ttu-id="37b43-302">如果未指定名称，则列出所有模板。</span><span class="sxs-lookup"><span data-stu-id="37b43-302">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="37b43-303">要创建的模板的语言。</span><span class="sxs-lookup"><span data-stu-id="37b43-303">The language of the template to create.</span></span> <span data-ttu-id="37b43-304">接受的语言因模板而异（请参阅[参数](#arguments)部分中的默认值）。</span><span class="sxs-lookup"><span data-stu-id="37b43-304">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="37b43-305">对于某些模板无效。</span><span class="sxs-lookup"><span data-stu-id="37b43-305">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="37b43-306">某些 shell 将 `#` 解释为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="37b43-306">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="37b43-307">在这些情况下，请将语言参数值括在引号中。</span><span class="sxs-lookup"><span data-stu-id="37b43-307">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="37b43-308">例如 `dotnet new console -lang "F#"`。</span><span class="sxs-lookup"><span data-stu-id="37b43-308">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="37b43-309">所创建的输出的名称。</span><span class="sxs-lookup"><span data-stu-id="37b43-309">The name for the created output.</span></span> <span data-ttu-id="37b43-310">如果未指定名称，使用的是当前目录的名称。</span><span class="sxs-lookup"><span data-stu-id="37b43-310">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="37b43-311">指定在安装期间要使用的 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="37b43-311">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="37b43-312">自 .NET Core 2.1 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-312">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="37b43-313">用于放置生成的输出的位置。</span><span class="sxs-lookup"><span data-stu-id="37b43-313">Location to place the generated output.</span></span> <span data-ttu-id="37b43-314">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="37b43-314">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="37b43-315">根据可用类型筛选模板。</span><span class="sxs-lookup"><span data-stu-id="37b43-315">Filters templates based on available types.</span></span> <span data-ttu-id="37b43-316">预定义的值为 `project`、`item` 或 `other`。</span><span class="sxs-lookup"><span data-stu-id="37b43-316">Predefined values are `project`, `item`, or `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="37b43-317">在提供的 `PATH` 或 `NUGET_ID` 中卸载模板包。</span><span class="sxs-lookup"><span data-stu-id="37b43-317">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="37b43-318">如果未指定 `<PATH|NUGET_ID>` 值，将显示所有当前安装的模板包及其关联的模板。</span><span class="sxs-lookup"><span data-stu-id="37b43-318">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="37b43-319">指定 `NUGET_ID` 时，请勿包含版本号。</span><span class="sxs-lookup"><span data-stu-id="37b43-319">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="37b43-320">如果未指定此选项的参数，该命令将列出已安装的模板及其详细信息。</span><span class="sxs-lookup"><span data-stu-id="37b43-320">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="37b43-321">若要使用 `PATH` 卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="37b43-321">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="37b43-322">例如，C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp  有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp  无效。</span><span class="sxs-lookup"><span data-stu-id="37b43-322">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="37b43-323">模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="37b43-323">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="37b43-324">检查是否有可用于当前安装的模板包的更新并安装这些更新。</span><span class="sxs-lookup"><span data-stu-id="37b43-324">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="37b43-325">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-325">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="37b43-326">检查是否有可用于当前安装的模板包的更新。</span><span class="sxs-lookup"><span data-stu-id="37b43-326">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="37b43-327">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-327">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="37b43-328">模板选项</span><span class="sxs-lookup"><span data-stu-id="37b43-328">Template options</span></span>

<span data-ttu-id="37b43-329">每个项目模板都可能有附加选项。</span><span class="sxs-lookup"><span data-stu-id="37b43-329">Each project template may have additional options available.</span></span> <span data-ttu-id="37b43-330">核心模板有以下附加选项：</span><span class="sxs-lookup"><span data-stu-id="37b43-330">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="37b43-331">控制台</span><span class="sxs-lookup"><span data-stu-id="37b43-331">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="37b43-332">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="37b43-332">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="37b43-333">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-333">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="37b43-334">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="37b43-334">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="37b43-335">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="37b43-335">SDK version</span></span> | <span data-ttu-id="37b43-336">默认值</span><span class="sxs-lookup"><span data-stu-id="37b43-336">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="37b43-337">3.1</span><span class="sxs-lookup"><span data-stu-id="37b43-337">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="37b43-338">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-338">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="37b43-339">在已创建的项目文件中设置 `LangVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="37b43-339">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="37b43-340">例如，使用 `--langVersion 7.3` 以使用 C# 7.3。</span><span class="sxs-lookup"><span data-stu-id="37b43-340">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="37b43-341">不支持 F#。</span><span class="sxs-lookup"><span data-stu-id="37b43-341">Not supported for F#.</span></span> <span data-ttu-id="37b43-342">自 .NET Core 2.2 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-342">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="37b43-343">有关默认的 C# 版本列表，请参阅[默认](../../csharp/language-reference/configure-language-version.md#defaults)。</span><span class="sxs-lookup"><span data-stu-id="37b43-343">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="37b43-344">如已指定，则在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="37b43-344">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="37b43-345">自 .NET Core 2.2 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-345">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="37b43-346">classlib</span><span class="sxs-lookup"><span data-stu-id="37b43-346">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="37b43-347">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="37b43-347">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="37b43-348">值：`netcoreapp<version>`（要创建 .NET Core 类库的话）或 `netstandard<version>`（要创建 .NET Standard 类库的话）。</span><span class="sxs-lookup"><span data-stu-id="37b43-348">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="37b43-349">默认值为 `netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="37b43-349">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="37b43-350">在已创建的项目文件中设置 `LangVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="37b43-350">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="37b43-351">例如，使用 `--langVersion 7.3` 以使用 C# 7.3。</span><span class="sxs-lookup"><span data-stu-id="37b43-351">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="37b43-352">不支持 F#。</span><span class="sxs-lookup"><span data-stu-id="37b43-352">Not supported for F#.</span></span> <span data-ttu-id="37b43-353">自 .NET Core 2.2 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-353">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="37b43-354">有关默认的 C# 版本列表，请参阅[默认](../../csharp/language-reference/configure-language-version.md#defaults)。</span><span class="sxs-lookup"><span data-stu-id="37b43-354">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="37b43-355">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="37b43-355">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="37b43-356">wpf、wpflib、wpfcustomcontrollib、wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="37b43-356">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="37b43-357">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="37b43-357">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="37b43-358">默认值为 `netcoreapp3.1`。</span><span class="sxs-lookup"><span data-stu-id="37b43-358">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="37b43-359">自 .NET Core 3.1 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-359">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="37b43-360">在已创建的项目文件中设置 `LangVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="37b43-360">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="37b43-361">例如，使用 `--langVersion 7.3` 以使用 C# 7.3。</span><span class="sxs-lookup"><span data-stu-id="37b43-361">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="37b43-362">有关默认的 C# 版本列表，请参阅[默认](../../csharp/language-reference/configure-language-version.md#defaults)。</span><span class="sxs-lookup"><span data-stu-id="37b43-362">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="37b43-363">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="37b43-363">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="37b43-364">winforms、winformslib</span><span class="sxs-lookup"><span data-stu-id="37b43-364">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="37b43-365">在已创建的项目文件中设置 `LangVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="37b43-365">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="37b43-366">例如，使用 `--langVersion 7.3` 以使用 C# 7.3。</span><span class="sxs-lookup"><span data-stu-id="37b43-366">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="37b43-367">有关默认的 C# 版本列表，请参阅[默认](../../csharp/language-reference/configure-language-version.md#defaults)。</span><span class="sxs-lookup"><span data-stu-id="37b43-367">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="37b43-368">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="37b43-368">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="37b43-369">worker、grpc</span><span class="sxs-lookup"><span data-stu-id="37b43-369">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="37b43-370">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="37b43-370">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="37b43-371">默认值为 `netcoreapp3.1`。</span><span class="sxs-lookup"><span data-stu-id="37b43-371">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="37b43-372">自 .NET Core 3.1 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-372">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="37b43-373">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="37b43-373">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="37b43-374">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="37b43-374">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="37b43-375">mstest、xunit</span><span class="sxs-lookup"><span data-stu-id="37b43-375">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="37b43-376">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="37b43-376">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="37b43-377">自 .NET Core 3.0 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="37b43-377">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="37b43-378">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="37b43-378">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="37b43-379">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="37b43-379">SDK version</span></span> | <span data-ttu-id="37b43-380">默认值</span><span class="sxs-lookup"><span data-stu-id="37b43-380">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="37b43-381">3.1</span><span class="sxs-lookup"><span data-stu-id="37b43-381">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="37b43-382">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-382">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="37b43-383">允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="37b43-383">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="37b43-384">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="37b43-384">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="37b43-385">nunit</span><span class="sxs-lookup"><span data-stu-id="37b43-385">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="37b43-386">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="37b43-386">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="37b43-387">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="37b43-387">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="37b43-388">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="37b43-388">SDK version</span></span> | <span data-ttu-id="37b43-389">默认值</span><span class="sxs-lookup"><span data-stu-id="37b43-389">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="37b43-390">3.1</span><span class="sxs-lookup"><span data-stu-id="37b43-390">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="37b43-391">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-391">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="37b43-392">2.2</span><span class="sxs-lookup"><span data-stu-id="37b43-392">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="37b43-393">2.1</span><span class="sxs-lookup"><span data-stu-id="37b43-393">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="37b43-394">允许使用 [dotnet pack](dotnet-pack.md) 为项目打包。</span><span class="sxs-lookup"><span data-stu-id="37b43-394">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="37b43-395">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="37b43-395">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="37b43-396">页</span><span class="sxs-lookup"><span data-stu-id="37b43-396">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="37b43-397">已生成代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="37b43-397">Namespace for the generated code.</span></span> <span data-ttu-id="37b43-398">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="37b43-398">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="37b43-399">创建不含 PageModel 的页。</span><span class="sxs-lookup"><span data-stu-id="37b43-399">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="37b43-400">viewimports、proto</span><span class="sxs-lookup"><span data-stu-id="37b43-400">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="37b43-401">已生成代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="37b43-401">Namespace for the generated code.</span></span> <span data-ttu-id="37b43-402">默认值为 `MyApp.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="37b43-402">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="37b43-403">blazorserver</span><span class="sxs-lookup"><span data-stu-id="37b43-403">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="37b43-404">要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="37b43-404">The type of authentication to use.</span></span> <span data-ttu-id="37b43-405">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="37b43-405">The possible values are:</span></span>

  - <span data-ttu-id="37b43-406">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="37b43-406">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="37b43-407">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-407">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="37b43-408">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-408">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="37b43-409">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-409">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="37b43-410">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-410">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="37b43-411">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-411">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="37b43-412">要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="37b43-412">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="37b43-413">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-413">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="37b43-414">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="37b43-414">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="37b43-415">此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="37b43-415">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="37b43-416">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-416">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="37b43-417">此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="37b43-417">The reset password policy ID for this project.</span></span> <span data-ttu-id="37b43-418">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-418">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="37b43-419">此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="37b43-419">The edit profile policy ID for this project.</span></span> <span data-ttu-id="37b43-420">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-420">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="37b43-421">要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="37b43-421">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="37b43-422">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-422">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="37b43-423">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="37b43-423">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="37b43-424">此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="37b43-424">The Client ID for this project.</span></span> <span data-ttu-id="37b43-425">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-425">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="37b43-426">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="37b43-426">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="37b43-427">目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="37b43-427">The domain for the directory tenant.</span></span> <span data-ttu-id="37b43-428">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-428">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="37b43-429">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="37b43-429">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="37b43-430">要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="37b43-430">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="37b43-431">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="37b43-432">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="37b43-432">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="37b43-433">重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="37b43-433">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="37b43-434">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-434">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="37b43-435">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="37b43-435">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="37b43-436">允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="37b43-436">Allows this application read-access to the directory.</span></span> <span data-ttu-id="37b43-437">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-437">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="37b43-438">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="37b43-438">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="37b43-439">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="37b43-439">Turns off HTTPS.</span></span> <span data-ttu-id="37b43-440">此选项仅适用于 `Individual`、`IndividualB2C`、`SingleOrg` 和 `MultiOrg` 未用于 `--auth` 的情况。</span><span class="sxs-lookup"><span data-stu-id="37b43-440">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="37b43-441">指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="37b43-441">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="37b43-442">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-442">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="37b43-443">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="37b43-443">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="37b43-444">Web</span><span class="sxs-lookup"><span data-stu-id="37b43-444">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="37b43-445">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="37b43-445">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="37b43-446">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="37b43-446">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="37b43-447">选项在 .NET Core 2.2 SDK 中不可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-447">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="37b43-448">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="37b43-448">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="37b43-449">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="37b43-449">SDK version</span></span> | <span data-ttu-id="37b43-450">默认值</span><span class="sxs-lookup"><span data-stu-id="37b43-450">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="37b43-451">3.1</span><span class="sxs-lookup"><span data-stu-id="37b43-451">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="37b43-452">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-452">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="37b43-453">2.1</span><span class="sxs-lookup"><span data-stu-id="37b43-453">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="37b43-454">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="37b43-454">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="37b43-455">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="37b43-455">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="37b43-456">mvc、webapp</span><span class="sxs-lookup"><span data-stu-id="37b43-456">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="37b43-457">要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="37b43-457">The type of authentication to use.</span></span> <span data-ttu-id="37b43-458">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="37b43-458">The possible values are:</span></span>

  - <span data-ttu-id="37b43-459">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="37b43-459">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="37b43-460">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-460">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="37b43-461">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-461">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="37b43-462">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-462">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="37b43-463">`MultiOrg` - 对多个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-463">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="37b43-464">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-464">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="37b43-465">要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="37b43-465">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="37b43-466">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-466">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="37b43-467">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="37b43-467">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="37b43-468">此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="37b43-468">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="37b43-469">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-469">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="37b43-470">此项目的重置密码策略 ID。</span><span class="sxs-lookup"><span data-stu-id="37b43-470">The reset password policy ID for this project.</span></span> <span data-ttu-id="37b43-471">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-471">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="37b43-472">此项目的编辑配置文件策略 ID。</span><span class="sxs-lookup"><span data-stu-id="37b43-472">The edit profile policy ID for this project.</span></span> <span data-ttu-id="37b43-473">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-473">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="37b43-474">要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="37b43-474">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="37b43-475">与 `SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-475">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="37b43-476">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="37b43-476">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="37b43-477">此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="37b43-477">The Client ID for this project.</span></span> <span data-ttu-id="37b43-478">与 `IndividualB2C`、`SingleOrg` 或 `MultiOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-478">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="37b43-479">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="37b43-479">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="37b43-480">目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="37b43-480">The domain for the directory tenant.</span></span> <span data-ttu-id="37b43-481">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-481">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="37b43-482">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="37b43-482">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="37b43-483">要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="37b43-483">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="37b43-484">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-484">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="37b43-485">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="37b43-485">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="37b43-486">重定向 URI 的应用程序基路径中的请求路径。</span><span class="sxs-lookup"><span data-stu-id="37b43-486">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="37b43-487">与 `SingleOrg` 或 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-487">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="37b43-488">默认值为 `/signin-oidc`。</span><span class="sxs-lookup"><span data-stu-id="37b43-488">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="37b43-489">允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="37b43-489">Allows this application read-access to the directory.</span></span> <span data-ttu-id="37b43-490">仅适用于 `SingleOrg` 或 `MultiOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-490">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="37b43-491">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="37b43-491">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="37b43-492">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="37b43-492">Turns off HTTPS.</span></span> <span data-ttu-id="37b43-493">此选项仅适用于未使用 `Individual`、`IndividualB2C`、`SingleOrg` 和 `MultiOrg` 的情况。</span><span class="sxs-lookup"><span data-stu-id="37b43-493">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="37b43-494">指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="37b43-494">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="37b43-495">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-495">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="37b43-496">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="37b43-496">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="37b43-497">自 .NET Core 3.0 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="37b43-497">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="37b43-498">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="37b43-498">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="37b43-499">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="37b43-499">SDK version</span></span> | <span data-ttu-id="37b43-500">默认值</span><span class="sxs-lookup"><span data-stu-id="37b43-500">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="37b43-501">3.1</span><span class="sxs-lookup"><span data-stu-id="37b43-501">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="37b43-502">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-502">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="37b43-503">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="37b43-503">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="37b43-504">在项目中添加 BrowserLink。</span><span class="sxs-lookup"><span data-stu-id="37b43-504">Includes BrowserLink in the project.</span></span> <span data-ttu-id="37b43-505">选项在 .NET Core 2.2 和 3.1 SDK 中不可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-505">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="37b43-506">确定项目是否配置为在调试生成中使用 [Razor 运行时编译](/aspnet/core/mvc/views/view-compilation#runtime-compilation)。</span><span class="sxs-lookup"><span data-stu-id="37b43-506">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="37b43-507">自 .NET Core 3.1 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="37b43-507">Option available since .NET Core 3.1 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="37b43-508">angular、react</span><span class="sxs-lookup"><span data-stu-id="37b43-508">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="37b43-509">要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="37b43-509">The type of authentication to use.</span></span> <span data-ttu-id="37b43-510">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-510">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="37b43-511">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="37b43-511">The possible values are:</span></span>

  - <span data-ttu-id="37b43-512">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="37b43-512">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="37b43-513">`Individual` - 个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-513">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="37b43-514">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="37b43-514">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="37b43-515">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="37b43-515">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="37b43-516">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="37b43-516">Turns off HTTPS.</span></span> <span data-ttu-id="37b43-517">仅当身份验证为 `None` 时，此选项才适用。</span><span class="sxs-lookup"><span data-stu-id="37b43-517">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="37b43-518">指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="37b43-518">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="37b43-519">仅适用于 `Individual` 或 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-519">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="37b43-520">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-520">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="37b43-521">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="37b43-521">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="37b43-522">选项在 .NET Core 2.2 SDK 中不可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-522">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="37b43-523">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="37b43-523">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="37b43-524">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="37b43-524">SDK version</span></span> | <span data-ttu-id="37b43-525">默认值</span><span class="sxs-lookup"><span data-stu-id="37b43-525">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="37b43-526">3.1</span><span class="sxs-lookup"><span data-stu-id="37b43-526">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="37b43-527">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-527">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="37b43-528">2.1</span><span class="sxs-lookup"><span data-stu-id="37b43-528">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="37b43-529">reactredux</span><span class="sxs-lookup"><span data-stu-id="37b43-529">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="37b43-530">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="37b43-530">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="37b43-531">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="37b43-531">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="37b43-532">选项在 .NET Core 2.2 SDK 中不可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-532">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="37b43-533">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="37b43-533">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="37b43-534">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="37b43-534">SDK version</span></span> | <span data-ttu-id="37b43-535">默认值</span><span class="sxs-lookup"><span data-stu-id="37b43-535">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="37b43-536">3.1</span><span class="sxs-lookup"><span data-stu-id="37b43-536">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="37b43-537">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-537">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="37b43-538">2.1</span><span class="sxs-lookup"><span data-stu-id="37b43-538">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="37b43-539">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="37b43-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="37b43-540">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="37b43-540">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="37b43-541">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="37b43-541">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="37b43-542">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="37b43-542">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="37b43-543">除了将组件添加到此库以外，还支持添加传统的 Razor 页面和视图。</span><span class="sxs-lookup"><span data-stu-id="37b43-543">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="37b43-544">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-544">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="37b43-545">webapi</span><span class="sxs-lookup"><span data-stu-id="37b43-545">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="37b43-546">要使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="37b43-546">The type of authentication to use.</span></span> <span data-ttu-id="37b43-547">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="37b43-547">The possible values are:</span></span>

  - <span data-ttu-id="37b43-548">`None` - 不进行身份验证（默认）。</span><span class="sxs-lookup"><span data-stu-id="37b43-548">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="37b43-549">`IndividualB2C` - 使用 Azure AD B2C 进行个人身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-549">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="37b43-550">`SingleOrg` - 对一个租户进行组织身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-550">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="37b43-551">`Windows` - Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-551">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="37b43-552">要连接到的 Azure Active Directory B2C 实例。</span><span class="sxs-lookup"><span data-stu-id="37b43-552">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="37b43-553">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-553">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="37b43-554">默认值为 `https://login.microsoftonline.com/tfp/`。</span><span class="sxs-lookup"><span data-stu-id="37b43-554">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="37b43-555">此项目的登录和注册策略 ID。</span><span class="sxs-lookup"><span data-stu-id="37b43-555">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="37b43-556">与 `IndividualB2C` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-556">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="37b43-557">要连接到的 Azure Active Directory 实例。</span><span class="sxs-lookup"><span data-stu-id="37b43-557">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="37b43-558">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="37b43-559">默认值为 `https://login.microsoftonline.com/`。</span><span class="sxs-lookup"><span data-stu-id="37b43-559">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="37b43-560">此项目的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="37b43-560">The Client ID for this project.</span></span> <span data-ttu-id="37b43-561">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-561">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="37b43-562">默认值为 `11111111-1111-1111-11111111111111111`。</span><span class="sxs-lookup"><span data-stu-id="37b43-562">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="37b43-563">目录租户的域。</span><span class="sxs-lookup"><span data-stu-id="37b43-563">The domain for the directory tenant.</span></span> <span data-ttu-id="37b43-564">与 `IndividualB2C` 或 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-564">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="37b43-565">默认值为 `qualified.domain.name`。</span><span class="sxs-lookup"><span data-stu-id="37b43-565">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="37b43-566">要连接到的目录的 TenantId ID。</span><span class="sxs-lookup"><span data-stu-id="37b43-566">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="37b43-567">与 `SingleOrg` 身份验证结合使用。</span><span class="sxs-lookup"><span data-stu-id="37b43-567">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="37b43-568">默认值为 `22222222-2222-2222-2222-222222222222`。</span><span class="sxs-lookup"><span data-stu-id="37b43-568">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="37b43-569">允许此应用程序对目录进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="37b43-569">Allows this application read-access to the directory.</span></span> <span data-ttu-id="37b43-570">仅适用于 `SingleOrg` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-570">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="37b43-571">从生成的模板中排除 launchSettings.json  。</span><span class="sxs-lookup"><span data-stu-id="37b43-571">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="37b43-572">关闭 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="37b43-572">Turns off HTTPS.</span></span> <span data-ttu-id="37b43-573">`app.UseHsts` 和 `app.UseHttpsRedirection` 未添加到 `Startup.Configure` 中。</span><span class="sxs-lookup"><span data-stu-id="37b43-573">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="37b43-574">此选项仅适用于 `IndividualB2C` 或 `SingleOrg` 未用于身份验证的情况。</span><span class="sxs-lookup"><span data-stu-id="37b43-574">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="37b43-575">指定应使用 LocalDB，而不使用 SQLite。</span><span class="sxs-lookup"><span data-stu-id="37b43-575">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="37b43-576">仅适用于 `IndividualB2C` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b43-576">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="37b43-577">指定目标[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="37b43-577">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="37b43-578">选项在 .NET Core 2.2 SDK 中不可用。</span><span class="sxs-lookup"><span data-stu-id="37b43-578">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="37b43-579">下表根据所使用的 SDK 版本号列出了默认值：</span><span class="sxs-lookup"><span data-stu-id="37b43-579">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="37b43-580">SDK 版本</span><span class="sxs-lookup"><span data-stu-id="37b43-580">SDK version</span></span> | <span data-ttu-id="37b43-581">默认值</span><span class="sxs-lookup"><span data-stu-id="37b43-581">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="37b43-582">3.1</span><span class="sxs-lookup"><span data-stu-id="37b43-582">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="37b43-583">3.0</span><span class="sxs-lookup"><span data-stu-id="37b43-583">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="37b43-584">2.1</span><span class="sxs-lookup"><span data-stu-id="37b43-584">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="37b43-585">在项目创建期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="37b43-585">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="37b43-586">globaljson</span><span class="sxs-lookup"><span data-stu-id="37b43-586">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="37b43-587">指定要在 global.json  文件中使用的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="37b43-587">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="37b43-588">示例</span><span class="sxs-lookup"><span data-stu-id="37b43-588">Examples</span></span>

- <span data-ttu-id="37b43-589">通过指定模板名称，创建 C# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="37b43-589">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="37b43-590">在当前目录中创建 F# 控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="37b43-590">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="37b43-591">在指定的目录中创建 .NET Standard 类库项目：</span><span class="sxs-lookup"><span data-stu-id="37b43-591">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="37b43-592">在当前目录中新建没有设置身份验证的 ASP.NET Core C# MVC 项目：</span><span class="sxs-lookup"><span data-stu-id="37b43-592">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="37b43-593">创建新的 xUnit 项目：</span><span class="sxs-lookup"><span data-stu-id="37b43-593">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="37b43-594">列出可用于单页应用程序 (SPA) 模板的所有模板：</span><span class="sxs-lookup"><span data-stu-id="37b43-594">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="37b43-595">列出与“we”子字符串匹配的所有模板  。</span><span class="sxs-lookup"><span data-stu-id="37b43-595">List all templates matching the *we* substring.</span></span> <span data-ttu-id="37b43-596">找不到完全匹配，因此子字符串匹配针对短名称和名称列运行。</span><span class="sxs-lookup"><span data-stu-id="37b43-596">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="37b43-597">尝试调用与 ng 匹配的模板  。</span><span class="sxs-lookup"><span data-stu-id="37b43-597">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="37b43-598">如果无法确定单个匹配项，请列出部分匹配项的模板。</span><span class="sxs-lookup"><span data-stu-id="37b43-598">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="37b43-599">安装 ASP.NET Core 的 SPA 模板 2.0 版：</span><span class="sxs-lookup"><span data-stu-id="37b43-599">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="37b43-600">列出已安装的模板及其详细信息，包括如何卸载它们：</span><span class="sxs-lookup"><span data-stu-id="37b43-600">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="37b43-601">在当前目录中创建 global.json  ，将 SDK 版本设置为 3.1.101：</span><span class="sxs-lookup"><span data-stu-id="37b43-601">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="37b43-602">请参阅</span><span class="sxs-lookup"><span data-stu-id="37b43-602">See also</span></span>

- [<span data-ttu-id="37b43-603">dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="37b43-603">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="37b43-604">创建 dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="37b43-604">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="37b43-605">dotnet/dotnet-template-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="37b43-605">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="37b43-606">dotnet new 可用模板</span><span class="sxs-lookup"><span data-stu-id="37b43-606">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
