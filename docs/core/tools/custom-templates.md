---
title: dotnet new 自定义模板
description: 了解任意类型 .NET 项目或文件的自定义模板。
author: guardrex
ms.date: 08/11/2017
ms.openlocfilehash: 60ae9a6f0af7e75ba721a739ec51d77c59d7792e
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169416"
---
# <a name="custom-templates-for-dotnet-new"></a><span data-ttu-id="aa6d7-103">dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="aa6d7-103">Custom templates for dotnet new</span></span>

<span data-ttu-id="aa6d7-104">[.NET Core SDK](https://www.microsoft.com/net/download/core) 附带许多预安装的模板，与 [`dotnet new` 命令](dotnet-new.md)结合使用。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-104">The [.NET Core SDK](https://www.microsoft.com/net/download/core) comes with many templates pre-installed to use with the [`dotnet new` command](dotnet-new.md).</span></span> <span data-ttu-id="aa6d7-105">自.NET Core 2.0 起，可以为任何类型的项目（如应用程序、服务、工具或类库）创建自己的自定义模板。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-105">Starting with .NET Core 2.0, you can create your own custom templates for any type of project, such as an app, service, tool, or class library.</span></span> <span data-ttu-id="aa6d7-106">甚至可以创建输出一个或多个独立文件（如配置文件）的模板。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-106">You can even create a template that outputs one or more independent files, such as a configuration file.</span></span>

<span data-ttu-id="aa6d7-107">可以从任何 NuGet 源上的 NuGet 包安装自定义模板，具体方法是直接引用 NuGet nupkg 文件，或指定包含模板的文件系统目录。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-107">You can install custom templates from a NuGet package on any NuGet feed, by referencing a NuGet *nupkg* file directly, or by specifying a file system directory that contains the template.</span></span> <span data-ttu-id="aa6d7-108">借助模板引擎提供的功能，可以替换值、添加和排除文件和文件区域，并在使用模板时执行自定义处理操作。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-108">The template engine offers features that allow you to replace values, include and exclude files and regions of files, and execute custom processing operations when your template is used.</span></span>

<span data-ttu-id="aa6d7-109">模板引擎是开放源代码，在线代码存储库位于 GitHub 上的 [dotnet/templating](https://github.com/dotnet/templating/)。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-109">The template engine is open source, and the online code repository is at [dotnet/templating](https://github.com/dotnet/templating/) on GitHub.</span></span> <span data-ttu-id="aa6d7-110">有关模板示例，请访问 [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) 存储库。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-110">Visit the [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) repo for samples of templates.</span></span> <span data-ttu-id="aa6d7-111">GitHub 上的 [dotnet new 可用模板](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)收录了更多模板，包括第三方模板。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-111">More templates, including templates from third parties, are found at [Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) on GitHub.</span></span> <span data-ttu-id="aa6d7-112">若要详细了解如何创建和使用自定义模板，请参阅[如何创建自己的 dotnet new 模板](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)和 [dotnet/templating GitHub 存储库 Wiki](https://github.com/dotnet/templating/wiki)。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-112">For more information about creating and using custom templates, see [How to create your own templates for dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/) and the [dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="aa6d7-113">若要按照演示步骤操作并创建模板，请参阅[创建 dotnet new 自定义模板](~/docs/core/tutorials/create-custom-template.md)教程。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-113">To follow a walkthrough and create a template, see the [Create a custom template for dotnet new](~/docs/core/tutorials/create-custom-template.md) tutorial.</span></span>

## <a name="configuration"></a><span data-ttu-id="aa6d7-114">配置</span><span class="sxs-lookup"><span data-stu-id="aa6d7-114">Configuration</span></span>

<span data-ttu-id="aa6d7-115">模板由以下部分组成：</span><span class="sxs-lookup"><span data-stu-id="aa6d7-115">A template is composed of the following components:</span></span>

- <span data-ttu-id="aa6d7-116">源文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="aa6d7-116">Source files and folders</span></span>
- <span data-ttu-id="aa6d7-117">配置文件 (template.json)</span><span class="sxs-lookup"><span data-stu-id="aa6d7-117">A configuration file (*template.json*)</span></span>

### <a name="source-files-and-folders"></a><span data-ttu-id="aa6d7-118">源文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="aa6d7-118">Source files and folders</span></span>

<span data-ttu-id="aa6d7-119">源文件和文件夹包含执行 `dotnet new <TEMPLATE>` 命令时用户希望模板引擎使用的任何文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-119">The source files and folders include whatever files and folders you want the template engine to use when the `dotnet new <TEMPLATE>` command is executed.</span></span> <span data-ttu-id="aa6d7-120">模板引擎旨在将可运行项目用作源代码，以生成项目。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-120">The template engine is designed to use *runnable projects* as source code to produce projects.</span></span> <span data-ttu-id="aa6d7-121">这样做有以下几个好处：</span><span class="sxs-lookup"><span data-stu-id="aa6d7-121">This has several benefits:</span></span>

- <span data-ttu-id="aa6d7-122">模板引擎不要求用户将特殊令牌注入项目的源代码。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-122">The template engine doesn't require you to inject special tokens into your project's source code.</span></span>
- <span data-ttu-id="aa6d7-123">代码文件不必是特殊文件，也不必以任何方式进行修改，即可与模板引擎配合使用。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-123">The code files aren't special files or modified in any way to work with the template engine.</span></span> <span data-ttu-id="aa6d7-124">因此，处理项目时通常使用的工具也适用于模板内容。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-124">So, the tools you normally use when working with projects also work with template content.</span></span>
- <span data-ttu-id="aa6d7-125">生成、运行和调试模板项目，就像生成、运行和调试其他任何项目一样。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-125">You build, run, and debug your template projects just like you do for any of your other projects.</span></span>
- <span data-ttu-id="aa6d7-126">只需将 template.json 配置文件添加到项目，即可通过现有项目快速创建模板。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-126">You can quickly create a template from an existing project just by adding a *template.json* configuration file to the project.</span></span>

<span data-ttu-id="aa6d7-127">模板中存储的文件和文件夹并不限于正式的 .NET 项目类型，如 .NET Core 或 .NET Framework 解决方案。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-127">Files and folders stored in the template aren't limited to formal .NET project types, such as .NET Core or .NET Framework solutions.</span></span> <span data-ttu-id="aa6d7-128">源文件和文件夹可能包含用户希望在使用模板时创建的任何内容，即使模板引擎仅输出一个文件（如配置文件或解决方案文件），也不例外。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-128">Source files and folders may consist of any content that you wish to create when the template is used, even if the template engine produces just one file for its output, such as a configuration file or a solution file.</span></span> <span data-ttu-id="aa6d7-129">例如，可以创建包含 web.config 源文件的模板，并在使用模板时为项目创建经过修改的 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-129">For example, you can create a template that contains a *web.config* source file and creates a modified *web.config* file for projects where the template is used.</span></span> <span data-ttu-id="aa6d7-130">源文件修改依据为用户在 template.json 配置文件中提供的逻辑和设置，以及用户提供的作为选项传递到 `dotnet new <TEMPLATE>` 命令的值。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-130">The modifications to source files are based on logic and settings you've provided in the *template.json* configuration file along with values provided by the user passed as options to the `dotnet new <TEMPLATE>` command.</span></span>

### <a name="templatejson"></a><span data-ttu-id="aa6d7-131">template.json</span><span class="sxs-lookup"><span data-stu-id="aa6d7-131">template.json</span></span>

<span data-ttu-id="aa6d7-132">template.json 文件位于模板根目录中的 .template.config 文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-132">The *template.json* file is placed in a *.template.config* folder in the root directory of the template.</span></span> <span data-ttu-id="aa6d7-133">此文件向模板引擎提供配置信息。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-133">The file provides configuration information to the template engine.</span></span> <span data-ttu-id="aa6d7-134">最低配置必须包含下表中列出的成员，这足以创建功能模板。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-134">The minimum configuration requires the members shown in the following table, which is sufficient to create a functional template.</span></span>

| <span data-ttu-id="aa6d7-135">成员</span><span class="sxs-lookup"><span data-stu-id="aa6d7-135">Member</span></span>            | <span data-ttu-id="aa6d7-136">类型</span><span class="sxs-lookup"><span data-stu-id="aa6d7-136">Type</span></span>          | <span data-ttu-id="aa6d7-137">说明</span><span class="sxs-lookup"><span data-stu-id="aa6d7-137">Description</span></span> |
| ----------------- | ------------- | ----------- |
| `$schema`         | <span data-ttu-id="aa6d7-138">URI</span><span class="sxs-lookup"><span data-stu-id="aa6d7-138">URI</span></span>           | <span data-ttu-id="aa6d7-139">template.json 文件的 JSON 架构。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-139">The JSON schema for the *template.json* file.</span></span> <span data-ttu-id="aa6d7-140">如果指定架构，支持 JSON 架构的编辑器启用 JSON 编辑功能。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-140">Editors that support JSON schemas enable JSON-editing features when the schema is specified.</span></span> <span data-ttu-id="aa6d7-141">例如，[Visual Studio Code](https://code.visualstudio.com/) 要求此成员启用 IntelliSense。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-141">For example, [Visual Studio Code](https://code.visualstudio.com/) requires this member to enable IntelliSense.</span></span> <span data-ttu-id="aa6d7-142">使用值 `http://json.schemastore.org/template`。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-142">Use a value of `http://json.schemastore.org/template`.</span></span> |
| `author`          | <span data-ttu-id="aa6d7-143">字符串</span><span class="sxs-lookup"><span data-stu-id="aa6d7-143">string</span></span>        | <span data-ttu-id="aa6d7-144">模板创建者。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-144">The author of the template.</span></span> |
| `classifications` | <span data-ttu-id="aa6d7-145">array(string)</span><span class="sxs-lookup"><span data-stu-id="aa6d7-145">array(string)</span></span> | <span data-ttu-id="aa6d7-146">为了找到模板，用户可能会在搜索模板时使用的 0 个或多个模板特征。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-146">Zero or more characteristics of the template that a user might use to find the template when searching for it.</span></span> <span data-ttu-id="aa6d7-147">如果出现在使用 <code>dotnet new -l&#124;--list</code> 命令生成的模板列表中，classifications 还会出现在“Tags”列中。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-147">The classifications also appear in the *Tags* column when it appears in a list of templates produced by using the <code>dotnet new -l&#124;--list</code> command.</span></span> |
| `identity`        | <span data-ttu-id="aa6d7-148">字符串</span><span class="sxs-lookup"><span data-stu-id="aa6d7-148">string</span></span>        | <span data-ttu-id="aa6d7-149">此模板的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-149">A unique name for this template.</span></span> |
| `name`            | <span data-ttu-id="aa6d7-150">字符串</span><span class="sxs-lookup"><span data-stu-id="aa6d7-150">string</span></span>        | <span data-ttu-id="aa6d7-151">用户应看到的模板名称。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-151">The name for the template that users should see.</span></span> |
| `shortName`       | <span data-ttu-id="aa6d7-152">字符串</span><span class="sxs-lookup"><span data-stu-id="aa6d7-152">string</span></span>        | <span data-ttu-id="aa6d7-153">方便用户选择模板的默认速记属性，适用于模板名称由用户指定（而不是通过 GUI 选择）的环境。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-153">A default shorthand for selecting the template that applies to environments where the template name is specified by the user, not selected via a GUI.</span></span> <span data-ttu-id="aa6d7-154">例如，通过命令提示符和 CLI 命令使用模板时，短名称非常有用。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-154">For example, the short name is useful when using templates from a command prompt with CLI commands.</span></span> |

#### <a name="example"></a><span data-ttu-id="aa6d7-155">示例:</span><span class="sxs-lookup"><span data-stu-id="aa6d7-155">Example:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Catalina Garcia",
  "classifications": [ "Common", "Console" ],
  "identity": "GarciaSoftware.ConsoleTemplate.CSharp",
  "name": "Garcia Software Console Application",
  "shortName": "garciaconsole"
}
```

<span data-ttu-id="aa6d7-156">template.json 文件的完整架构位于 [JSON 架构存储](http://json.schemastore.org/template)。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-156">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span>

## <a name="net-default-templates"></a><span data-ttu-id="aa6d7-157">.NET 默认模板</span><span class="sxs-lookup"><span data-stu-id="aa6d7-157">.NET default templates</span></span>

<span data-ttu-id="aa6d7-158">安装 [.NET Core SDK](https://www.microsoft.com/net/download/core) 时，将获取十多个用于创建项目和文件的内置模板，包括控制台应用程序、类库、单元测试项目、ASP.NET Core 应用程序（包括 [Angular](https://angular.io/) 和 [React](https://facebook.github.io/react/) 项目）和配置文件。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-158">When you install the [.NET Core SDK](https://www.microsoft.com/net/download/core), you receive over a dozen built-in templates for creating projects and files, including console apps, class libraries, unit test projects, ASP.NET Core apps (including [Angular](https://angular.io/) and [React](https://facebook.github.io/react/) projects), and configuration files.</span></span> <span data-ttu-id="aa6d7-159">若要列出内置模板，请执行 `dotnet new` 命令和 `-l|--list` 选项：</span><span class="sxs-lookup"><span data-stu-id="aa6d7-159">To list the built-in templates, execute the `dotnet new` command with the `-l|--list` option:</span></span>

```console
dotnet new -l
```

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a><span data-ttu-id="aa6d7-160">将模板打包到 NuGet 包（nupkg 文件）</span><span class="sxs-lookup"><span data-stu-id="aa6d7-160">Packing a template into a NuGet package (nupkg file)</span></span>

<span data-ttu-id="aa6d7-161">目前，在 Windows 上使用 [nuget.exe](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe)（而不是 [dotnet pack](dotnet-pack.md)）打包自定义模板。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-161">Currently, a custom template is packed on Windows with [nuget.exe](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe) (not [dotnet pack](dotnet-pack.md)).</span></span> <span data-ttu-id="aa6d7-162">若要进行跨平台打包，请考虑使用 [NuGetizer 3000](https://github.com/NuGet/Home/wiki/NuGetizer-3000)。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-162">For cross-platform packaging, consider using [NuGetizer 3000](https://github.com/NuGet/Home/wiki/NuGetizer-3000).</span></span>

<span data-ttu-id="aa6d7-163">将项目文件夹的内容连同 .template.config/template.json 文件一起放入 content 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-163">The contents of the project folder, together with its *.template.config/template.json* file, are placed into a folder named *content*.</span></span> <span data-ttu-id="aa6d7-164">在 content 文件夹旁边，添加 [nuspec 文件](/nuget/create-packages/creating-a-package)。这是一个 XML 清单文件，用于描述包内容，并促进创建 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-164">Next to the *content* folder, add a [*nuspec* file](/nuget/create-packages/creating-a-package), which is an XML manifest file that describes a package's contents and drives the process of creating the NuGet package.</span></span> <span data-ttu-id="aa6d7-165">在 nuspec文件的 \<packageTypes> 元素中，添加 `name` 属性值为 `Template` 的 \<packageType> 元素。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-165">Inside of a **\<packageTypes>** element in the *nuspec* file, include a **\<packageType>** element with a `name` attribute value of `Template`.</span></span> <span data-ttu-id="aa6d7-166">content 文件夹和 nuspec 文件应位于同一目录。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-166">Both the *content* folder and the *nuspec* file should reside in the same directory.</span></span> <span data-ttu-id="aa6d7-167">下表列出了将模板生成为 NuGet 包至少所需的 nuspec 文件元素。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-167">The table shows the minimum *nuspec* file elements required to produce a template as a NuGet package.</span></span>

| <span data-ttu-id="aa6d7-168">元素</span><span class="sxs-lookup"><span data-stu-id="aa6d7-168">Element</span></span>            | <span data-ttu-id="aa6d7-169">类型</span><span class="sxs-lookup"><span data-stu-id="aa6d7-169">Type</span></span>   | <span data-ttu-id="aa6d7-170">说明</span><span class="sxs-lookup"><span data-stu-id="aa6d7-170">Description</span></span> |
| ------------------ | ------ | ----------- |
| <span data-ttu-id="aa6d7-171">**\<authors>**</span><span class="sxs-lookup"><span data-stu-id="aa6d7-171">**\<authors>**</span></span>     | <span data-ttu-id="aa6d7-172">字符串</span><span class="sxs-lookup"><span data-stu-id="aa6d7-172">string</span></span> | <span data-ttu-id="aa6d7-173">包创建者的逗号分隔列表，与 nuget.org 上的配置文件名称一致。创建者显示在 nuget.org 上的 NuGet 库中，用于交叉引用同一创建者的包。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-173">A comma-separated list of packages authors, matching the profile names on nuget.org. Authors are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span> |
| <span data-ttu-id="aa6d7-174">**\<description>**</span><span class="sxs-lookup"><span data-stu-id="aa6d7-174">**\<description>**</span></span> | <span data-ttu-id="aa6d7-175">字符串</span><span class="sxs-lookup"><span data-stu-id="aa6d7-175">string</span></span> | <span data-ttu-id="aa6d7-176">用于 UI 显示的包的详细说明。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-176">A long description of the package for UI display.</span></span> |
| <span data-ttu-id="aa6d7-177">**\<id>**</span><span class="sxs-lookup"><span data-stu-id="aa6d7-177">**\<id>**</span></span>          | <span data-ttu-id="aa6d7-178">字符串</span><span class="sxs-lookup"><span data-stu-id="aa6d7-178">string</span></span> | <span data-ttu-id="aa6d7-179">不区分大小写的包标识符，在 nuget.org 或包驻留的任意库中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-179">The case-insensitive package identifier, which must be unique across nuget.org or whatever gallery the package will reside in.</span></span> <span data-ttu-id="aa6d7-180">ID 不得包含空格或对 URL 无效的字符，通常遵循 .NET 命名空间规则。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-180">IDs may not contain spaces or characters that are not valid for a URL and generally follow .NET namespace rules.</span></span> <span data-ttu-id="aa6d7-181">有关指南，请参阅[选择唯一包标识符并设置版本号](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number)。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-181">See [Choosing a unique package identifier and setting the version number](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number) for guidance.</span></span> |
| <span data-ttu-id="aa6d7-182">**\<packageType>**</span><span class="sxs-lookup"><span data-stu-id="aa6d7-182">**\<packageType>**</span></span> | <span data-ttu-id="aa6d7-183">字符串</span><span class="sxs-lookup"><span data-stu-id="aa6d7-183">string</span></span> | <span data-ttu-id="aa6d7-184">将此元素置于 \<metadata> 元素之间的 \<packageTypes> 元素内。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-184">Place this element inside a **\<packageTypes>** element among the **\<metadata>** elements.</span></span> <span data-ttu-id="aa6d7-185">将 \<packageType> 元素的 `name` 属性设置为 `Template`。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-185">Set the `name` attribute of the **\<packageType>** element to `Template`.</span></span> |
| <span data-ttu-id="aa6d7-186">**\<version>**</span><span class="sxs-lookup"><span data-stu-id="aa6d7-186">**\<version>**</span></span>     | <span data-ttu-id="aa6d7-187">字符串</span><span class="sxs-lookup"><span data-stu-id="aa6d7-187">string</span></span> | <span data-ttu-id="aa6d7-188">遵循 major.minor.patch 模式的包版本。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-188">The version of the package, following the major.minor.patch pattern.</span></span> <span data-ttu-id="aa6d7-189">版本号可能包括预发布后缀，如[预发布版本](/nuget/create-packages/prerelease-packages#semantic-versioning)主题中所述。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-189">Version numbers may include a pre-release suffix as described in the [Pre-release versions](/nuget/create-packages/prerelease-packages#semantic-versioning) topic.</span></span> |

<span data-ttu-id="aa6d7-190">有关完整的 nuspec 文件架构，请参阅 [.nuspec 参考](/nuget/schema/nuspec)。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-190">See the [.nuspec reference](/nuget/schema/nuspec) for the complete *nuspec* file schema.</span></span> <span data-ttu-id="aa6d7-191">[创建 dotnet new 自定义模板](~/docs/core/tutorials/create-custom-template.md)教程中展示了模板的示例 nuspec 文件。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-191">An example *nuspec* file for a template appears in the [Create a custom template for dotnet new](~/docs/core/tutorials/create-custom-template.md) tutorial.</span></span>

<span data-ttu-id="aa6d7-192">使用 `nuget pack <PATH_TO_NUSPEC_FILE>` 命令[创建包](/nuget/create-packages/creating-a-package#creating-the-package)。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-192">[Create a package](/nuget/create-packages/creating-a-package#creating-the-package) using the `nuget pack <PATH_TO_NUSPEC_FILE>` command.</span></span>

## <a name="installing-a-template"></a><span data-ttu-id="aa6d7-193">安装模板</span><span class="sxs-lookup"><span data-stu-id="aa6d7-193">Installing a template</span></span>

<span data-ttu-id="aa6d7-194">从任何 NuGet 源上的 NuGet 包安装自定义模板，具体方法是直接引用 nupkg 文件，或指定包含模板配置的文件系统目录。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-194">Install a custom template from a NuGet package on any NuGet feed by referencing a *nupkg* file directly or by specifying a file system directory that contains a templating configuration.</span></span> <span data-ttu-id="aa6d7-195">结合使用 `-i|--install` 选项和 [dotnet new](dotnet-new.md) 命令。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-195">Use the `-i|--install` option with the [dotnet new](dotnet-new.md) command.</span></span>

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="aa6d7-196">从 nuget.org 中存储的 NuGet 包安装模板的具体步骤</span><span class="sxs-lookup"><span data-stu-id="aa6d7-196">To install a template from a NuGet package stored at nuget.org</span></span>

```console
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a><span data-ttu-id="aa6d7-197">从本地 nupkg 文件安装模板的具体步骤</span><span class="sxs-lookup"><span data-stu-id="aa6d7-197">To install a template from a local nupkg file</span></span>

```console
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a><span data-ttu-id="aa6d7-198">从文件系统目录安装模板的具体步骤</span><span class="sxs-lookup"><span data-stu-id="aa6d7-198">To install a template from a file system directory</span></span>

<span data-ttu-id="aa6d7-199">`FILE_SYSTEM_DIRECTORY` 是包含项目和 .template.config 文件夹的项目文件夹：</span><span class="sxs-lookup"><span data-stu-id="aa6d7-199">The `FILE_SYSTEM_DIRECTORY` is the project folder containing the project and the *.template.config* folder:</span></span>

```console
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="uninstalling-a-template"></a><span data-ttu-id="aa6d7-200">卸载模板</span><span class="sxs-lookup"><span data-stu-id="aa6d7-200">Uninstalling a template</span></span>

<span data-ttu-id="aa6d7-201">卸载自定义模板的方法是，按 `id` 引用 NuGet 包，或指定包含模板配置的文件系统目录。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-201">Uninstall a custom template by referencing a NuGet package by its `id` or by specifying a file system directory that contains a templating configuration.</span></span> <span data-ttu-id="aa6d7-202">结合使用 `-u|--uninstall` 安装选项和 [dotnet new](dotnet-new.md) 命令。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-202">Use the `-u|--uninstall` install option with the [dotnet new](dotnet-new.md) command.</span></span>

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="aa6d7-203">从 nuget.org 中存储的 NuGet 包卸载模板的具体步骤</span><span class="sxs-lookup"><span data-stu-id="aa6d7-203">To uninstall a template from a NuGet package stored at nuget.org</span></span>

```console
dotnet new -u <NUGET_PACKAGE_ID>
```

### <a name="to-uninstall-a-template-from-a-local-nupkg-file"></a><span data-ttu-id="aa6d7-204">从本地 nupkg 文件卸载模板的具体步骤</span><span class="sxs-lookup"><span data-stu-id="aa6d7-204">To uninstall a template from a local nupkg file</span></span>

<span data-ttu-id="aa6d7-205">若要卸载模板，请勿尝试使用 nupkg 文件路径。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-205">To uninstall the template, don't attempt to use the path to the *nupkg* file.</span></span> <span data-ttu-id="aa6d7-206">无法尝试使用 `dotnet new -u <PATH_TO_NUPKG_FILE>` 卸载模板。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-206">Attempting to uninstall a template using `dotnet new -u <PATH_TO_NUPKG_FILE>` fails.</span></span> <span data-ttu-id="aa6d7-207">按 `id` 引用包：</span><span class="sxs-lookup"><span data-stu-id="aa6d7-207">Reference the package by its `id`:</span></span>

```console
dotnet new -u <NUGET_PACKAGE_ID>
```

### <a name="to-uninstall-a-template-from-a-file-system-directory"></a><span data-ttu-id="aa6d7-208">从文件系统目录卸载模板的具体步骤</span><span class="sxs-lookup"><span data-stu-id="aa6d7-208">To uninstall a template from a file system directory</span></span>

<span data-ttu-id="aa6d7-209">`FILE_SYSTEM_DIRECTORY` 是包含项目和 .template.config 文件夹的项目文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-209">The `FILE_SYSTEM_DIRECTORY` is the project folder containing the project and the *.template.config* folder.</span></span> <span data-ttu-id="aa6d7-210">提供的路径必须是绝对路径。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-210">The path provided needs to be the absolute path.</span></span> <span data-ttu-id="aa6d7-211">无法尝试使用相对路径卸载模板。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-211">Attempting to uninstall a template using a relative path fails.</span></span> <span data-ttu-id="aa6d7-212">有关详细信息，请查看 [dotnet new](dotnet-new.md) 一文。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-212">For more information, see the [dotnet new](dotnet-new.md) article.</span></span>

```console
dotnet new -u <FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a><span data-ttu-id="aa6d7-213">使用自定义模板创建项目</span><span class="sxs-lookup"><span data-stu-id="aa6d7-213">Create a project using a custom template</span></span>

<span data-ttu-id="aa6d7-214">安装模板后，通过执行 `dotnet new <TEMPLATE>` 命令来使用模板，就像使用其他任何预安装模板一样。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-214">After a template is installed, use the template by executing the `dotnet new <TEMPLATE>` command as you would with any other pre-installed template.</span></span> <span data-ttu-id="aa6d7-215">还可以为 `dotnet new` 命令指定[选项](dotnet-new.md#options)，包括在模板设置中配置的模板专用选项。</span><span class="sxs-lookup"><span data-stu-id="aa6d7-215">You can also specify [options](dotnet-new.md#options) to the `dotnet new` command, including template specific options you configured in the template settings.</span></span> <span data-ttu-id="aa6d7-216">直接向命令提供模板的短名称：</span><span class="sxs-lookup"><span data-stu-id="aa6d7-216">Supply the template's short name directly to the command:</span></span>

```console
dotnet new <TEMPLATE>
```

## <a name="see-also"></a><span data-ttu-id="aa6d7-217">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa6d7-217">See also</span></span>

* [<span data-ttu-id="aa6d7-218">创建 dotnet new 自定义模板（教程）</span><span class="sxs-lookup"><span data-stu-id="aa6d7-218">Create a custom template for dotnet new (tutorial)</span></span>](../tutorials/create-custom-template.md)
* [<span data-ttu-id="aa6d7-219">dotnet/templating GitHub 存储库 Wiki</span><span class="sxs-lookup"><span data-stu-id="aa6d7-219">dotnet/templating GitHub repo Wiki</span></span>](https://github.com/dotnet/templating/wiki)
* [<span data-ttu-id="aa6d7-220">dotnet/dotnet-template-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="aa6d7-220">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
* [<span data-ttu-id="aa6d7-221">如何创建自己的 dotnet new 模板</span><span class="sxs-lookup"><span data-stu-id="aa6d7-221">How to create your own templates for dotnet new</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)
* [<span data-ttu-id="aa6d7-222">JSON 架构存储中的 template.json 架构</span><span class="sxs-lookup"><span data-stu-id="aa6d7-222">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)
