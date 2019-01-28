---
title: 创建 dotnet new 自定义模板
description: 在本趣味性教程中，了解如何创建 dotnet new 命令的自定义模板。
author: guardrex
ms.date: 08/12/2017
ms.custom: seodec18
ms.openlocfilehash: 72cafab774187cf8c59b2a00d8adcc5028974c88
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714053"
---
# <a name="create-a-custom-template-for-dotnet-new"></a><span data-ttu-id="6fd76-103">创建 dotnet new 自定义模板</span><span class="sxs-lookup"><span data-stu-id="6fd76-103">Create a custom template for dotnet new</span></span>

<span data-ttu-id="6fd76-104">本教程介绍了如何：</span><span class="sxs-lookup"><span data-stu-id="6fd76-104">This tutorial shows you how to:</span></span>

- <span data-ttu-id="6fd76-105">通过现有项目或新控制台应用程序项目创建基本模板。</span><span class="sxs-lookup"><span data-stu-id="6fd76-105">Create a basic template from an existing project or a new console app project.</span></span>
- <span data-ttu-id="6fd76-106">从 nuget.org 或本地 nupkg 文件打包模板以供分发。</span><span class="sxs-lookup"><span data-stu-id="6fd76-106">Pack the template for distribution at nuget.org or from a local *nupkg* file.</span></span>
- <span data-ttu-id="6fd76-107">从 nuget.org、本地 nupkg 文件或本地文件系统安装模板。</span><span class="sxs-lookup"><span data-stu-id="6fd76-107">Install the template from nuget.org, a local *nupkg* file, or the local file system.</span></span>
- <span data-ttu-id="6fd76-108">卸载模板。</span><span class="sxs-lookup"><span data-stu-id="6fd76-108">Uninstall the template.</span></span>

<span data-ttu-id="6fd76-109">若要通过完整示例继续学习本教程，请下载[示例项目模板](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package)。</span><span class="sxs-lookup"><span data-stu-id="6fd76-109">If you prefer to proceed through the tutorial with a complete sample, download the [sample project template](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package).</span></span> <span data-ttu-id="6fd76-110">示例模板针对 NuGet 分发进行了配置。</span><span class="sxs-lookup"><span data-stu-id="6fd76-110">The sample template is configured for NuGet distribution.</span></span>

<span data-ttu-id="6fd76-111">若要将下载的示例与文件系统分发相结合，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="6fd76-111">If you wish to use the downloaded sample with file system distribution, do the following:</span></span>

- <span data-ttu-id="6fd76-112">将示例中 content 文件夹的内容移到上一级 GarciaSoftware.ConsoleTemplate.CSharp 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6fd76-112">Move the contents of the *content* folder of the sample up one level into the *GarciaSoftware.ConsoleTemplate.CSharp* folder.</span></span>
- <span data-ttu-id="6fd76-113">删除空的 content 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6fd76-113">Delete the empty *content* folder.</span></span>
- <span data-ttu-id="6fd76-114">删除 nuspec 文件。</span><span class="sxs-lookup"><span data-stu-id="6fd76-114">Delete the *nuspec* file.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6fd76-115">系统必备</span><span class="sxs-lookup"><span data-stu-id="6fd76-115">Prerequisites</span></span>

- <span data-ttu-id="6fd76-116">安装 [.NET Core 2.0 SDK](https://www.microsoft.com/net/core) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="6fd76-116">Install the [.NET Core 2.0 SDK](https://www.microsoft.com/net/core) or later versions.</span></span>
- <span data-ttu-id="6fd76-117">阅读参考主题 [dotnet new 自定义模板](../tools/custom-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="6fd76-117">Read the reference topic [Custom templates for dotnet new](../tools/custom-templates.md).</span></span>

## <a name="create-a-template-from-a-project"></a><span data-ttu-id="6fd76-118">通过项目创建模板</span><span class="sxs-lookup"><span data-stu-id="6fd76-118">Create a template from a project</span></span>

<span data-ttu-id="6fd76-119">使用已确认可以编译和运行的现有项目，或在硬盘上的文件夹中新建一个控制台应用项目。</span><span class="sxs-lookup"><span data-stu-id="6fd76-119">Use an existing project that you've confirmed compiles and runs, or create a new console app project in a folder on your hard drive.</span></span> <span data-ttu-id="6fd76-120">本教程假定项目文件夹名为 GarciaSoftware.ConsoleTemplate.CSharp，并存储在用户配置文件中的 Documents\Templates。</span><span class="sxs-lookup"><span data-stu-id="6fd76-120">This tutorial assumes that the name of the project folder is *GarciaSoftware.ConsoleTemplate.CSharp* stored at *Documents\Templates* in the user's profile.</span></span> <span data-ttu-id="6fd76-121">本教程的项目模板名称采用格式“\<公司名称>.\<模板类型>.\<编程语言>”，但也可以根据自己的意愿随意命名项目和模板。</span><span class="sxs-lookup"><span data-stu-id="6fd76-121">The tutorial project template name is in the format *\<Company Name>.\<Template Type>.\<Programming Language>*, but you're free to name your project and template anything you wish.</span></span>

1. <span data-ttu-id="6fd76-122">向 .template.config 项目根添加文件夹。</span><span class="sxs-lookup"><span data-stu-id="6fd76-122">Add a folder to the root of the project named *.template.config*.</span></span>
1. <span data-ttu-id="6fd76-123">在 .template.config 文件夹中，创建 template.json 文件来配置模板。</span><span class="sxs-lookup"><span data-stu-id="6fd76-123">Inside the *.template.config* folder, create a *template.json* file to configure your template.</span></span> <span data-ttu-id="6fd76-124">有关 template.json 文件的详细信息和成员定义，请参阅 [dotnet new 自定义模板](../tools/custom-templates.md#templatejson)主题和 [JSON 架构存储中的 template.json 架构](http://json.schemastore.org/template)。</span><span class="sxs-lookup"><span data-stu-id="6fd76-124">For more information and member definitions for the *template.json* file, see the [Custom templates for dotnet new](../tools/custom-templates.md#templatejson) topic and the [*template.json* schema at the JSON Schema Store](http://json.schemastore.org/template).</span></span>

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

<span data-ttu-id="6fd76-125">模板已完成。</span><span class="sxs-lookup"><span data-stu-id="6fd76-125">The template is finished.</span></span> <span data-ttu-id="6fd76-126">此时，可通过两种方式分发模板。</span><span class="sxs-lookup"><span data-stu-id="6fd76-126">At this point, you have two options for template distribution.</span></span> <span data-ttu-id="6fd76-127">若要继续阅读本教程，请选择下面两种路径之一：</span><span class="sxs-lookup"><span data-stu-id="6fd76-127">To continue this tutorial, choose one path or the other:</span></span>

1. <span data-ttu-id="6fd76-128">[NuGet 分发](#use-nuget-distribution)：从 NuGet 或本地 nupkg 文件安装模板，并使用安装后的模板。</span><span class="sxs-lookup"><span data-stu-id="6fd76-128">[NuGet distribution](#use-nuget-distribution): install the template from NuGet or from the local *nupkg* file, and use the installed template.</span></span>
2. <span data-ttu-id="6fd76-129">[文件系统分发](#use-file-system-distribution)。</span><span class="sxs-lookup"><span data-stu-id="6fd76-129">[File system distribution](#use-file-system-distribution).</span></span>

## <a name="use-nuget-distribution"></a><span data-ttu-id="6fd76-130">使用 NuGet 分发</span><span class="sxs-lookup"><span data-stu-id="6fd76-130">Use NuGet Distribution</span></span>

### <a name="pack-the-template-into-a-nuget-package"></a><span data-ttu-id="6fd76-131">将模板打包到 NuGet 包中</span><span class="sxs-lookup"><span data-stu-id="6fd76-131">Pack the template into a NuGet package</span></span>

1. <span data-ttu-id="6fd76-132">为 NuGet 包创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="6fd76-132">Create a folder for the NuGet package.</span></span> <span data-ttu-id="6fd76-133">在本教程中，使用的文件夹名为 GarciaSoftware.ConsoleTemplate.CSharp，该文件夹在用户配置文件中的 Documents\NuGetTemplates 内创建。</span><span class="sxs-lookup"><span data-stu-id="6fd76-133">For the tutorial, the folder name *GarciaSoftware.ConsoleTemplate.CSharp* is used, and the folder is created inside a *Documents\NuGetTemplates* folder in the user's profile.</span></span> <span data-ttu-id="6fd76-134">在新建的模板文件夹内，创建名为 content 的文件夹，以保存项目文件。</span><span class="sxs-lookup"><span data-stu-id="6fd76-134">Create a folder named *content* inside of the new template folder to hold the project files.</span></span>
1. <span data-ttu-id="6fd76-135">将项目文件夹的内容连同 .template.config/template.json 文件一起复制到创建的 content 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6fd76-135">Copy the contents of your project folder, together with its *.template.config/template.json* file, into the *content* folder you created.</span></span>
1. <span data-ttu-id="6fd76-136">在 content 文件夹旁边，添加 [nuspec 文件](/nuget/create-packages/creating-a-package)。</span><span class="sxs-lookup"><span data-stu-id="6fd76-136">Next to the *content* folder, add a [*nuspec* file](/nuget/create-packages/creating-a-package).</span></span> <span data-ttu-id="6fd76-137">nuspec 文件是 XML 清单文件，用于描述包内容，并促进创建 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="6fd76-137">The nuspec file is an XML manifest file that describes a package's contents and drives the process of creating the NuGet package.</span></span>

   ![显示 NuGet 包布局的目录结构](./media/create-custom-template/nuget-directory-layout.png)

1. <span data-ttu-id="6fd76-139">在 nuspec文件的 \<packageTypes> 元素中，添加 `name` 属性值为 `Template` 的 \<packageType> 元素。</span><span class="sxs-lookup"><span data-stu-id="6fd76-139">Inside of a **\<packageTypes>** element in the *nuspec* file, include a **\<packageType>** element with a `name` attribute value of `Template`.</span></span> <span data-ttu-id="6fd76-140">content 文件夹和 nuspec 文件应位于同一目录。</span><span class="sxs-lookup"><span data-stu-id="6fd76-140">Both the *content* folder and the *nuspec* file should reside in the same directory.</span></span> <span data-ttu-id="6fd76-141">下表列出了将模板生成为 NuGet 包至少所需的 nuspec 文件元素。</span><span class="sxs-lookup"><span data-stu-id="6fd76-141">The table shows the minimum *nuspec* file elements required to produce a template as a NuGet package.</span></span>

   | <span data-ttu-id="6fd76-142">元素</span><span class="sxs-lookup"><span data-stu-id="6fd76-142">Element</span></span>            | <span data-ttu-id="6fd76-143">类型</span><span class="sxs-lookup"><span data-stu-id="6fd76-143">Type</span></span>   | <span data-ttu-id="6fd76-144">说明</span><span class="sxs-lookup"><span data-stu-id="6fd76-144">Description</span></span> |
   | ------------------ | ------ | ----------- |
   | <span data-ttu-id="6fd76-145">**\<authors>**</span><span class="sxs-lookup"><span data-stu-id="6fd76-145">**\<authors>**</span></span>     | <span data-ttu-id="6fd76-146">字符串</span><span class="sxs-lookup"><span data-stu-id="6fd76-146">string</span></span> | <span data-ttu-id="6fd76-147">包创建者的逗号分隔列表，与 nuget.org 上的配置文件名称一致。创建者显示在 nuget.org 上的 NuGet 库中，用于交叉引用同一创建者的包。</span><span class="sxs-lookup"><span data-stu-id="6fd76-147">A comma-separated list of packages authors, matching the profile names on nuget.org. Authors are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span> |
   | <span data-ttu-id="6fd76-148">**\<description>**</span><span class="sxs-lookup"><span data-stu-id="6fd76-148">**\<description>**</span></span> | <span data-ttu-id="6fd76-149">字符串</span><span class="sxs-lookup"><span data-stu-id="6fd76-149">string</span></span> | <span data-ttu-id="6fd76-150">用于 UI 显示的包的详细说明。</span><span class="sxs-lookup"><span data-stu-id="6fd76-150">A long description of the package for UI display.</span></span> |
   | <span data-ttu-id="6fd76-151">**\<id>**</span><span class="sxs-lookup"><span data-stu-id="6fd76-151">**\<id>**</span></span>          | <span data-ttu-id="6fd76-152">字符串</span><span class="sxs-lookup"><span data-stu-id="6fd76-152">string</span></span> | <span data-ttu-id="6fd76-153">不区分大小写的包标识符，在 nuget.org 或包驻留的任意库中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6fd76-153">The case-insensitive package identifier, which must be unique across nuget.org or whatever gallery the package will reside in.</span></span> <span data-ttu-id="6fd76-154">ID 不得包含空格或对 URL 无效的字符，通常遵循 .NET 命名空间规则。</span><span class="sxs-lookup"><span data-stu-id="6fd76-154">IDs may not contain spaces or characters that are not valid for a URL and generally follow .NET namespace rules.</span></span> <span data-ttu-id="6fd76-155">有关指南，请参阅[选择唯一包标识符并设置版本号](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number)。</span><span class="sxs-lookup"><span data-stu-id="6fd76-155">See [Choosing a unique package identifier and setting the version number](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number) for guidance.</span></span> |
   | <span data-ttu-id="6fd76-156">**\<packageType>**</span><span class="sxs-lookup"><span data-stu-id="6fd76-156">**\<packageType>**</span></span> | <span data-ttu-id="6fd76-157">字符串</span><span class="sxs-lookup"><span data-stu-id="6fd76-157">string</span></span> | <span data-ttu-id="6fd76-158">将此元素置于 \<metadata> 元素之间的 \<packageTypes> 元素内。</span><span class="sxs-lookup"><span data-stu-id="6fd76-158">Place this element inside a **\<packageTypes>** element among the **\<metadata>** elements.</span></span> <span data-ttu-id="6fd76-159">将 \<packageType> 元素的 `name` 属性设置为 `Template`。</span><span class="sxs-lookup"><span data-stu-id="6fd76-159">Set the `name` attribute of the **\<packageType>** element to `Template`.</span></span> |
   | <span data-ttu-id="6fd76-160">**\<version>**</span><span class="sxs-lookup"><span data-stu-id="6fd76-160">**\<version>**</span></span>     | <span data-ttu-id="6fd76-161">字符串</span><span class="sxs-lookup"><span data-stu-id="6fd76-161">string</span></span> | <span data-ttu-id="6fd76-162">遵循 major.minor.patch 模式的包版本。</span><span class="sxs-lookup"><span data-stu-id="6fd76-162">The version of the package, following the major.minor.patch pattern.</span></span> <span data-ttu-id="6fd76-163">版本号可能包括预发布后缀，如[预发布版本](/nuget/create-packages/prerelease-packages#semantic-versioning)中所述。</span><span class="sxs-lookup"><span data-stu-id="6fd76-163">Version numbers may include a pre-release suffix as described in [Pre-release versions](/nuget/create-packages/prerelease-packages#semantic-versioning).</span></span> |

   <span data-ttu-id="6fd76-164">有关完整的 nuspec 文件架构，请参阅 [.nuspec 参考](/nuget/schema/nuspec)。</span><span class="sxs-lookup"><span data-stu-id="6fd76-164">See the [.nuspec reference](/nuget/schema/nuspec) for the complete *nuspec* file schema.</span></span>

   <span data-ttu-id="6fd76-165">在本教程中，nuspec 文件命名为 GarciaSoftware.ConsoleTemplate.CSharp.nuspec，包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="6fd76-165">The *nuspec* file for the tutorial is named *GarciaSoftware.ConsoleTemplate.CSharp.nuspec* and contains the following content:</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <package xmlns="http://schemas.microsoft.com/packaging/2012/06/nuspec.xsd">
     <metadata>
       <id>GarciaSoftware.ConsoleTemplate.CSharp</id>
       <version>1.0.0</version>
       <description>
         Creates the Garcia Software console app.
       </description>
       <authors>Catalina Garcia</authors>
       <packageTypes>
         <packageType name="Template" />
       </packageTypes>
     </metadata>
   </package>
   ```

1. <span data-ttu-id="6fd76-166">使用 `nuget pack <PATH_TO_NUSPEC_FILE>` 命令[创建包](/nuget/create-packages/creating-a-package#creating-the-package)。</span><span class="sxs-lookup"><span data-stu-id="6fd76-166">[Create the package](/nuget/create-packages/creating-a-package#creating-the-package) using the `nuget pack <PATH_TO_NUSPEC_FILE>` command.</span></span> <span data-ttu-id="6fd76-167">以下命令假定包含 NuGet 资产的文件夹位于 C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp。</span><span class="sxs-lookup"><span data-stu-id="6fd76-167">The following command assumes that the folder that holds the NuGet assets is at *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*.</span></span> <span data-ttu-id="6fd76-168">不过，无论将文件夹放置在系统上的什么位置，`nuget pack` 命令都接受 nuspec 文件路径：</span><span class="sxs-lookup"><span data-stu-id="6fd76-168">But wherever you place the folder on your system, the `nuget pack` command accepts the path to the *nuspec* file:</span></span>

   ```console
   nuget pack C:\Users\<USER>\Documents\NuGetTemplates\GarciaSoftware.ConsoleTemplate.CSharp\GarciaSoftware.ConsoleTemplate.CSharp.nuspec
   ```

### <a name="publishing-the-package-to-nugetorg"></a><span data-ttu-id="6fd76-169">将包发布到 nuget.org</span><span class="sxs-lookup"><span data-stu-id="6fd76-169">Publishing the package to nuget.org</span></span>

<span data-ttu-id="6fd76-170">若要发布 NuGet 包，请按照[创建和发布包](/nuget/quickstart/create-and-publish-a-package#publish-the-package)主题中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="6fd76-170">To publish a NuGet package, follow the instructions in the [Create and publish a package](/nuget/quickstart/create-and-publish-a-package#publish-the-package) topic.</span></span> <span data-ttu-id="6fd76-171">不过，不建议将本教程的模板发布到 NuGet，因为一旦发布，便永远无法删除，只能从列表去除。</span><span class="sxs-lookup"><span data-stu-id="6fd76-171">However, we recommend that you don't publish the tutorial template to NuGet as it can never be deleted once published, only delisted.</span></span> <span data-ttu-id="6fd76-172">至此已拥有 nupkg 文件形式的 NuGet 包，建议按照下面的说明操作，直接从本地 nupkg 文件安装模板。</span><span class="sxs-lookup"><span data-stu-id="6fd76-172">Now that you have the NuGet package in the form of a *nupkg* file, we suggest that you follow the instructions below to install the template directly from the local *nupkg* file.</span></span>

### <a name="install-the-template-from-a-nuget-package"></a><span data-ttu-id="6fd76-173">从 NuGet 包安装模板</span><span class="sxs-lookup"><span data-stu-id="6fd76-173">Install the template from a NuGet package</span></span>

#### <a name="install-the-template-from-the-local-nupkg-file"></a><span data-ttu-id="6fd76-174">从本地 nupkg 文件安装模板</span><span class="sxs-lookup"><span data-stu-id="6fd76-174">Install the template from the local *nupkg* file</span></span>

<span data-ttu-id="6fd76-175">若要从生成的 nupkg 文件安装模板，请结合使用 `dotnet new` 命令和 `-i|--install` 选项，并提供 nupkg 文件路径：</span><span class="sxs-lookup"><span data-stu-id="6fd76-175">To install the template from the *nupkg* file that you produced, use the `dotnet new` command with the `-i|--install` option and provide the path to the *nupkg* file:</span></span>

```console
dotnet new -i C:\Users\<USER>\GarciaSoftware.ConsoleTemplate.CSharp.1.0.0.nupkg
```

#### <a name="install-the-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="6fd76-176">从 nuget.org 中存储的 NuGet 包安装模板</span><span class="sxs-lookup"><span data-stu-id="6fd76-176">Install the template from a NuGet package stored at nuget.org</span></span>

<span data-ttu-id="6fd76-177">若要从 nuget.org 中存储的 NuGet 包安装模板，请结合使用 `dotnet new` 命令和 `-i|--install` 选项，并提供 NuGet 包名称：</span><span class="sxs-lookup"><span data-stu-id="6fd76-177">If you wish to install a template from a NuGet package stored at nuget.org, use the `dotnet new` command with the `-i|--install` option and supply the name of the NuGet package:</span></span>

```console
dotnet new -i GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="6fd76-178">示例代码只为了方便本文演示。</span><span class="sxs-lookup"><span data-stu-id="6fd76-178">The example is for demonstration purposes only.</span></span> <span data-ttu-id="6fd76-179">如果 nuget.org 中没有 `GarciaSoftware.ConsoleTemplate.CSharp` NuGet 包，不建议发布并从 NuGet 使用测试模板。</span><span class="sxs-lookup"><span data-stu-id="6fd76-179">There isn't a `GarciaSoftware.ConsoleTemplate.CSharp` NuGet package at nuget.org, and we don't recommend that you publish and consume test templates from NuGet.</span></span> <span data-ttu-id="6fd76-180">如果运行此命令，不会安装任何模板。</span><span class="sxs-lookup"><span data-stu-id="6fd76-180">If you run the command, no template is installed.</span></span> <span data-ttu-id="6fd76-181">不过，可以安装尚未发布到 nuget.org 的模板，具体方法是直接在本地文件系统上引用 nupkg 文件，如前一部分[从本地 nupkg 文件安装模板](#install-the-template-from-the-local-nupkg-file)所述。</span><span class="sxs-lookup"><span data-stu-id="6fd76-181">However, you can install a template that hasn't been published to nuget.org by referencing the *nupkg* file directly on your local file system as shown in the previous section [Install the template from the local nupkg file](#install-the-template-from-the-local-nupkg-file).</span></span>

<span data-ttu-id="6fd76-182">如果需要获取有关如何从 nuget.org 中的包安装模板的实际示例，可以使用 [dotnet-new 的 NUnit 3 模板](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/)。</span><span class="sxs-lookup"><span data-stu-id="6fd76-182">If you'd like a live example of how to install a template from a package at nuget.org, you can use the [NUnit 3 template for dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/).</span></span> <span data-ttu-id="6fd76-183">此模板将项目设置为使用 NUnit 单元测试。</span><span class="sxs-lookup"><span data-stu-id="6fd76-183">This template sets up a project to use NUnit unit testing.</span></span> <span data-ttu-id="6fd76-184">运行以下命令安装此模板：</span><span class="sxs-lookup"><span data-stu-id="6fd76-184">Use the following command to install it:</span></span>

```console
dotnet new -i NUnit3.DotNetNew.Template
```

<span data-ttu-id="6fd76-185">使用 `dotnet new -l` 列出模板时，模板列表中会列出短名称为“nunit”的“NUnit 3 测试项目”。</span><span class="sxs-lookup"><span data-stu-id="6fd76-185">When you list the templates with `dotnet new -l`, you see the *NUnit 3 Test Project* with a short name of *nunit* in the template list.</span></span> <span data-ttu-id="6fd76-186">可以在下一部分中使用此模板了。</span><span class="sxs-lookup"><span data-stu-id="6fd76-186">You're ready to use the template in the next section.</span></span>

![控制台窗口，显示带有其他模板的 NUnit 模板](./media/create-custom-template/nunit-template-console-window.png)

### <a name="create-a-project-from-the-template"></a><span data-ttu-id="6fd76-188">通过模板创建项目</span><span class="sxs-lookup"><span data-stu-id="6fd76-188">Create a project from the template</span></span>

<span data-ttu-id="6fd76-189">从 NuGet 安装模板后，在要放置模板引擎输出的目录（除非使用 `-o|--output` 选项指定特定的目录）执行 `dotnet new <TEMPLATE>` 命令，即可使用模板。</span><span class="sxs-lookup"><span data-stu-id="6fd76-189">After the template is installed from NuGet, use the template by executing the `dotnet new <TEMPLATE>` command from the directory where you want to the template engine's output placed (unless you're using the `-o|--output` option to specify a specific directory).</span></span> <span data-ttu-id="6fd76-190">有关详细信息，请参阅 [`dotnet new` 选项](~/docs/core/tools/dotnet-new.md#options)。</span><span class="sxs-lookup"><span data-stu-id="6fd76-190">For more information, see [`dotnet new` Options](~/docs/core/tools/dotnet-new.md#options).</span></span> <span data-ttu-id="6fd76-191">直接向 `dotnet new` 命令提供模板的短名称。</span><span class="sxs-lookup"><span data-stu-id="6fd76-191">Supply the template's short name directly to the `dotnet new` command.</span></span> <span data-ttu-id="6fd76-192">若要通过 NUnit 模板创建项目，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6fd76-192">To create a project from the NUnit template, run the following command:</span></span>

```console
dotnet new nunit
```

<span data-ttu-id="6fd76-193">控制台显示项目已创建，且项目包已还原。</span><span class="sxs-lookup"><span data-stu-id="6fd76-193">The console shows that the project is created and that the project's packages are restored.</span></span> <span data-ttu-id="6fd76-194">运行此命令后，项目便可供使用。</span><span class="sxs-lookup"><span data-stu-id="6fd76-194">After the command is run, the project is ready for use.</span></span>

![控制台窗口显示 dotnet new nunit 的输出，包括还原项目依赖项](./media/create-custom-template/dotnet-new-nunit-console-output.png)

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="6fd76-196">从 nuget.org 中存储的 NuGet 包卸载模板的具体步骤</span><span class="sxs-lookup"><span data-stu-id="6fd76-196">To uninstall a template from a NuGet package stored at nuget.org</span></span>

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="6fd76-197">示例代码只为了方便本文演示。</span><span class="sxs-lookup"><span data-stu-id="6fd76-197">The example is for demonstration purposes only.</span></span> <span data-ttu-id="6fd76-198">`GarciaSoftware.ConsoleTemplate.CSharp` NuGet 包没有存储到 nuget.org 或与 .NET Core SDK 一起安装。</span><span class="sxs-lookup"><span data-stu-id="6fd76-198">There isn't a `GarciaSoftware.ConsoleTemplate.CSharp` NuGet package at nuget.org or installed with the .NET Core SDK.</span></span> <span data-ttu-id="6fd76-199">如果运行此命令，不会卸载任何包/模板，并会看到以下异常消息：</span><span class="sxs-lookup"><span data-stu-id="6fd76-199">If you run the command, no package/template is uninstalled and you receive the following exception:</span></span>
>
> > <span data-ttu-id="6fd76-200">找不到要卸载的“GarciaSoftware.ConsoleTemplate.CSharp”包/模板。</span><span class="sxs-lookup"><span data-stu-id="6fd76-200">Could not find something to uninstall called 'GarciaSoftware.ConsoleTemplate.CSharp'.</span></span>

<span data-ttu-id="6fd76-201">若要卸载已安装的 [dotnet-new 的 NUnit 3 模板](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/)，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6fd76-201">If you installed the [NUnit 3 template for dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/) and wish to uninstall it, use the following command:</span></span>

```console
dotnet new -u NUnit3.DotNetNew.Template
```

### <a name="uninstall-the-template-from-a-local-nupkg-file"></a><span data-ttu-id="6fd76-202">从本地 nupkg 文件卸载模板</span><span class="sxs-lookup"><span data-stu-id="6fd76-202">Uninstall the template from a local nupkg file</span></span>

<span data-ttu-id="6fd76-203">若要卸载模板，请勿尝试使用 nupkg 文件路径。</span><span class="sxs-lookup"><span data-stu-id="6fd76-203">When you wish to uninstall the template, don't attempt to use the path to the *nupkg* file.</span></span> <span data-ttu-id="6fd76-204">无法尝试使用 `dotnet new -u <PATH_TO_NUPKG_FILE>` 卸载模板。</span><span class="sxs-lookup"><span data-stu-id="6fd76-204">*Attempting to uninstall a template using `dotnet new -u <PATH_TO_NUPKG_FILE>` fails.*</span></span> <span data-ttu-id="6fd76-205">按 `id` 引用包：</span><span class="sxs-lookup"><span data-stu-id="6fd76-205">Reference the package by its `id`:</span></span>

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp.1.0.0
```

## <a name="use-file-system-distribution"></a><span data-ttu-id="6fd76-206">使用文件系统分发</span><span class="sxs-lookup"><span data-stu-id="6fd76-206">Use file system distribution</span></span>

<span data-ttu-id="6fd76-207">若要分发模板，请确保用户可以在网络上访问项目模板文件夹的位置。</span><span class="sxs-lookup"><span data-stu-id="6fd76-207">To distribute the template, place the project template folder in a location accessible to users on your network.</span></span> <span data-ttu-id="6fd76-208">结合使用 `dotnet new` 命令和 `-i|--install` 选项，并指定模板文件夹路径（包含项目和 .template.config 文件夹的项目文件夹）。</span><span class="sxs-lookup"><span data-stu-id="6fd76-208">Use the `dotnet new` command with the `-i|--install` option and specify the path to the template folder (the project folder containing the project and the *.template.config* folder).</span></span>

<span data-ttu-id="6fd76-209">本教程假定项目模板存储在用户配置文件中的 Documents/Templates 文件夹内。</span><span class="sxs-lookup"><span data-stu-id="6fd76-209">The tutorial assumes the project template is stored in the *Documents/Templates* folder of the user's profile.</span></span> <span data-ttu-id="6fd76-210">从这个位置，使用以下命令安装模板，只将 \<USER> 替换为用户的配置文件名称：</span><span class="sxs-lookup"><span data-stu-id="6fd76-210">From that location, install the template with the following command replacing \<USER> with the user's profile name:</span></span>

```console
dotnet new -i C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

### <a name="create-a-project-from-the-template"></a><span data-ttu-id="6fd76-211">通过模板创建项目</span><span class="sxs-lookup"><span data-stu-id="6fd76-211">Create a project from the template</span></span>

<span data-ttu-id="6fd76-212">从文件系统安装模板后，在要放置模板引擎输出的目录（除非使用 `-o|--output` 选项指定特定的目录）执行 `dotnet new <TEMPLATE>` 命令，即可使用模板。</span><span class="sxs-lookup"><span data-stu-id="6fd76-212">After the template is installed from the file system, use the template by executing the `dotnet new <TEMPLATE>` command from the directory where you want to the template engine's output placed (unless you're using the `-o|--output` option to specify a specific directory).</span></span> <span data-ttu-id="6fd76-213">有关详细信息，请参阅 [`dotnet new` 选项](~/docs/core/tools/dotnet-new.md#options)。</span><span class="sxs-lookup"><span data-stu-id="6fd76-213">For more information, see [`dotnet new` Options](~/docs/core/tools/dotnet-new.md#options).</span></span> <span data-ttu-id="6fd76-214">直接向 `dotnet new` 命令提供模板的短名称。</span><span class="sxs-lookup"><span data-stu-id="6fd76-214">Supply the template's short name directly to the `dotnet new` command.</span></span>

<span data-ttu-id="6fd76-215">从 C:\Users\\\<USER>\Documents\Projects\MyConsoleApp 处创建的新项目文件夹，通过 `garciaconsole` 模板创建项目：</span><span class="sxs-lookup"><span data-stu-id="6fd76-215">From a new project folder created at *C:\Users\\\<USER>\Documents\Projects\MyConsoleApp*, create a project from the `garciaconsole` template:</span></span>

```console
dotnet new garciaconsole
```

### <a name="uninstall-the-template"></a><span data-ttu-id="6fd76-216">卸载模板</span><span class="sxs-lookup"><span data-stu-id="6fd76-216">Uninstall the template</span></span>

<span data-ttu-id="6fd76-217">如果在本地文件系统中的 C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp 处创建模板，请使用 `-u|--uninstall` 开关和模板文件夹路径卸载模板：</span><span class="sxs-lookup"><span data-stu-id="6fd76-217">If you created the template on your local file system at *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*, uninstall it with the `-u|--uninstall` switch and the path to the template folder:</span></span>

```console
dotnet new -u C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="6fd76-218">若要从本地文件系统卸载模板，需要完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="6fd76-218">To uninstall the template from your local file system, you need to fully qualify the path.</span></span> <span data-ttu-id="6fd76-219">例如，C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp 有效，但是包含文件夹中的 ./GarciaSoftware.ConsoleTemplate.CSharp 无效。</span><span class="sxs-lookup"><span data-stu-id="6fd76-219">For example, *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="6fd76-220">此外，模板路径中不要包含最后的终止目录斜杠。</span><span class="sxs-lookup"><span data-stu-id="6fd76-220">Additionally, do not include a final terminating directory slash on your template path.</span></span>

## <a name="see-also"></a><span data-ttu-id="6fd76-221">请参阅</span><span class="sxs-lookup"><span data-stu-id="6fd76-221">See also</span></span>

- [<span data-ttu-id="6fd76-222">dotnet/templating GitHub 存储库 Wiki</span><span class="sxs-lookup"><span data-stu-id="6fd76-222">dotnet/templating GitHub repo Wiki</span></span>](https://github.com/dotnet/templating/wiki)
- [<span data-ttu-id="6fd76-223">dotnet/dotnet-template-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="6fd76-223">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="6fd76-224">如何创建自己的 dotnet new 模板</span><span class="sxs-lookup"><span data-stu-id="6fd76-224">How to create your own templates for dotnet new</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)
- [<span data-ttu-id="6fd76-225">JSON 架构存储中的 template.json 架构</span><span class="sxs-lookup"><span data-stu-id="6fd76-225">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)
