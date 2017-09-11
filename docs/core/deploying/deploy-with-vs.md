---
title: "使用 Visual Studio 部署 .NET Core 应用"
description: "了解如何使用 Visual Studio 部署 .NET Core 应用"
keywords: ".NET、.NET Core、.NET Core 部署"
author: rpetrusha
ms.author: ronpet
ms.date: 04/18/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 01049a21-fd50-4419-9ab2-0e4a2e091050
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5cc9de1371ba90532e20c11c9f82002ad5a5fa92
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="deploying-net-core-apps-with-visual-studio"></a><span data-ttu-id="56b35-104">使用 Visual Studio 部署 .NET Core 应用</span><span class="sxs-lookup"><span data-stu-id="56b35-104">Deploying .NET Core apps with Visual Studio</span></span>

<span data-ttu-id="56b35-105">可将 .NET Core 应用程序部署为依赖框架的部署或独立部署，前者包含应用程序二进制文件，但依赖目标系统上存在的 .NET Core，而后者同时包含应用程序和 .NET Core 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="56b35-105">You can deploy a .NET Core application either as a *framework-dependent deployment*, which includes your application binaries but depends on the presence of .NET Core on the target system, or as a *self-contained deployment*, which includes both your application and .NET Core binaries.</span></span> <span data-ttu-id="56b35-106">有关 .NET Core 应用程序部署的概述，请参阅 [.NET Core 应用程序部署](index.md)。</span><span class="sxs-lookup"><span data-stu-id="56b35-106">For an overview of .NET Core application deployment, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="56b35-107">以下各节演示如何使用 Microsoft Visual Studio 创建下列各类部署：</span><span class="sxs-lookup"><span data-stu-id="56b35-107">The following sections show how to use Microsoft Visual Studio to create the following kinds of deployments:</span></span>

- <span data-ttu-id="56b35-108">依赖框架的部署</span><span class="sxs-lookup"><span data-stu-id="56b35-108">Framework-dependent deployment</span></span>
- <span data-ttu-id="56b35-109">包含第三方依赖项的依赖框架的部署</span><span class="sxs-lookup"><span data-stu-id="56b35-109">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="56b35-110">独立部署</span><span class="sxs-lookup"><span data-stu-id="56b35-110">Self-contained deployment</span></span>
- <span data-ttu-id="56b35-111">包含第三方依赖项的独立部署</span><span class="sxs-lookup"><span data-stu-id="56b35-111">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="56b35-112">有关使用 Visual Studio 开发 .NET Core 应用程序的信息，请参阅 [Windows 上 .NET Core 的先决条件](../windows-prerequisites.md#prerequisites-with-visual-studio-2017)。</span><span class="sxs-lookup"><span data-stu-id="56b35-112">For information on using Visual Studio to develop .NET Core applications, see [Prerequisites for .NET Core on Windows](../windows-prerequisites.md#prerequisites-with-visual-studio-2017).</span></span>

## <a name="framework-dependent-deployment"></a><span data-ttu-id="56b35-113">依赖框架的部署</span><span class="sxs-lookup"><span data-stu-id="56b35-113">Framework-dependent deployment</span></span>

<span data-ttu-id="56b35-114">如果不使用第三方依赖项，部属依赖框架的部署只包括生成、测试和发布应用。</span><span class="sxs-lookup"><span data-stu-id="56b35-114">Deploying a framework-dependent deployment with no third-party dependencies simply involves building, testing, and publishing the app.</span></span> <span data-ttu-id="56b35-115">一个用 C# 编写的简单示例可说明此过程。</span><span class="sxs-lookup"><span data-stu-id="56b35-115">A simple example written in C# illustrates the process.</span></span>  

1. <span data-ttu-id="56b35-116">创建项目。</span><span class="sxs-lookup"><span data-stu-id="56b35-116">Create the project.</span></span>

   <span data-ttu-id="56b35-117">选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="56b35-117">Select **File** > **New** > **Project**.</span></span> <span data-ttu-id="56b35-118">在“新建项目”对话框中，在“已安装”项目类型窗格中选择“.NET Core”，然后在中心窗格中选择“控制台应用(.NET Core)”模板。</span><span class="sxs-lookup"><span data-stu-id="56b35-118">In the **New Project** dialog, select **.NET Core** in the **Installed** project types pane, and select the **Console App (.NET Core)** template in the center pane.</span></span> <span data-ttu-id="56b35-119">在“名称”文本框中输入项目名称，如“FDD”。</span><span class="sxs-lookup"><span data-stu-id="56b35-119">Enter a project name, such as "FDD", in the **Name** text box.</span></span> <span data-ttu-id="56b35-120">选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="56b35-120">Select the **OK** button.</span></span>

1. <span data-ttu-id="56b35-121">添加应用程序的源代码。</span><span class="sxs-lookup"><span data-stu-id="56b35-121">Add the application's source code.</span></span>

   <span data-ttu-id="56b35-122">在编辑器中打开 Program.cs 文件，然后使用下列代码替换自动生成的代码。</span><span class="sxs-lookup"><span data-stu-id="56b35-122">Open the *Program.cs* file in the editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="56b35-123">它会提示用户输入文本，并显示用户输入的个别词。</span><span class="sxs-lookup"><span data-stu-id="56b35-123">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="56b35-124">它使用正则表达式 `\w+` 来将输入文本中的词分开。</span><span class="sxs-lookup"><span data-stu-id="56b35-124">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   <span data-ttu-id="56b35-125">[!code-cs[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]</span><span class="sxs-lookup"><span data-stu-id="56b35-125">[!code-cs[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]</span></span>

1. <span data-ttu-id="56b35-126">创建应用的调试版本。</span><span class="sxs-lookup"><span data-stu-id="56b35-126">Create a Debug build of your app.</span></span>

   <span data-ttu-id="56b35-127">选择“生成” > “生成解决方案”。</span><span class="sxs-lookup"><span data-stu-id="56b35-127">Select **Build** > **Build Solution**.</span></span> <span data-ttu-id="56b35-128">也可通过选择“调试” > “开始调试”来编译和运行应用程序的调试版本。</span><span class="sxs-lookup"><span data-stu-id="56b35-128">You can also compile and run the Debug build of your application by selecting **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="56b35-129">部署应用。</span><span class="sxs-lookup"><span data-stu-id="56b35-129">Deploy your app.</span></span>

   <span data-ttu-id="56b35-130">调试并测试程序后，创建要与应用一起部署的文件。</span><span class="sxs-lookup"><span data-stu-id="56b35-130">After you've debugged and tested the program, create the files to be deployed with your app.</span></span> <span data-ttu-id="56b35-131">若要从 Visual Studio 发布，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="56b35-131">To publish from Visual Studio, do the following:</span></span>

      1. <span data-ttu-id="56b35-132">将工具栏上的解决方案配置从“调试”更改为“发布”，生成应用的发布（而非调试）版本。</span><span class="sxs-lookup"><span data-stu-id="56b35-132">Change the solution configuration from **Debug** to **Release** on the toolbar to build a Release (rather than a Debug) version of your app.</span></span>

      1. <span data-ttu-id="56b35-133">在“解决方案资源管理器”中右键单击项目（而非解决方案），然后选择“发布”。</span><span class="sxs-lookup"><span data-stu-id="56b35-133">Right-click on the project (not the solution) in **Solution Explorer**, and select **Publish**.</span></span>

      1. <span data-ttu-id="56b35-134">在“发布”选项卡上，选择“发布”。</span><span class="sxs-lookup"><span data-stu-id="56b35-134">In the **Publish** tab, select **Publish**.</span></span> <span data-ttu-id="56b35-135">Visual Studio 将包含应用程序的文件写入本地文件系统。</span><span class="sxs-lookup"><span data-stu-id="56b35-135">Visual Studio writes the files that comprise your application to the local file system.</span></span>

      1. <span data-ttu-id="56b35-136">“发布”选项卡现在显示单个配置文件 FolderProfile。</span><span class="sxs-lookup"><span data-stu-id="56b35-136">The **Publish** tab now shows a single profile, **FolderProfile**.</span></span> <span data-ttu-id="56b35-137">该配置文件的配置设置显示在选项卡的“摘要”部分。</span><span class="sxs-lookup"><span data-stu-id="56b35-137">The profile's configuration settings are shown in the **Summary** section of the tab.</span></span>

   <span data-ttu-id="56b35-138">生成的文件位于名为 `PublishOutput` 的目录中，该目录位于项目的 .\bin\release 子目录的子目录中。</span><span class="sxs-lookup"><span data-stu-id="56b35-138">The resulting files are placed in a directory named `PublishOutput` that is in a subdirectory of your project's *.\bin\release* subdirectory.</span></span>

<span data-ttu-id="56b35-139">与应用程序的文件一起，发布过程将发出包含应用调试信息的程序数据库 (.pdb) 文件。</span><span class="sxs-lookup"><span data-stu-id="56b35-139">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="56b35-140">该文件主要用于调试异常。</span><span class="sxs-lookup"><span data-stu-id="56b35-140">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="56b35-141">可以选择不使用应用程序文件打包该文件。</span><span class="sxs-lookup"><span data-stu-id="56b35-141">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="56b35-142">但是，如果要调试应用的发布版本，则应保存该文件。</span><span class="sxs-lookup"><span data-stu-id="56b35-142">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="56b35-143">可以采用任何喜欢的方式部署完整的应用程序文件集。</span><span class="sxs-lookup"><span data-stu-id="56b35-143">Deploy the complete set of application files in any way you like.</span></span> <span data-ttu-id="56b35-144">例如，可以使用简单的 `copy` 命令将其打包为 Zip 文件，或者使用选择的安装包进行部署。</span><span class="sxs-lookup"><span data-stu-id="56b35-144">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span> <span data-ttu-id="56b35-145">安装成功后，用户可通过使用 `dotnet` 命令或提供应用程序文件名（如 `dotnet fdd.dll`）来执行应用程序。</span><span class="sxs-lookup"><span data-stu-id="56b35-145">Once installed, users can then execute your application by using the `dotnet` command and providing the application filename, such as `dotnet fdd.dll`.</span></span>

<span data-ttu-id="56b35-146">除应用程序二进制文件外，安装程序还应捆绑共享框架安装程序，或在安装应用程序的过程中将其作为先决条件进行检查。</span><span class="sxs-lookup"><span data-stu-id="56b35-146">In addition to the application binaries, your installer should also either bundle the shared framework installer or check for it as a prerequisite as part of the application installation.</span></span>  <span data-ttu-id="56b35-147">安装共享框架需要管理员/根访问权限，因为它属于计算机范围。</span><span class="sxs-lookup"><span data-stu-id="56b35-147">Installation of the shared framework requires Administrator/root access since it is machine-wide.</span></span>

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a><span data-ttu-id="56b35-148">包含第三方依赖项的依赖框架的部署</span><span class="sxs-lookup"><span data-stu-id="56b35-148">Framework-dependent deployment with third-party dependencies</span></span>

<span data-ttu-id="56b35-149">要使用一个或多个第三方依赖项来部署依赖框架的部署，需要任何依赖项都可供项目使用。</span><span class="sxs-lookup"><span data-stu-id="56b35-149">Deploying a framework-dependent deployment with one or more third-party dependencies requires that any dependencies be available to your project.</span></span> <span data-ttu-id="56b35-150">在生成应用之前，还需执行以下额外步骤：</span><span class="sxs-lookup"><span data-stu-id="56b35-150">The following additional steps are required before you can build your app:</span></span>

1. <span data-ttu-id="56b35-151">使用 NuGet 包管理器向项目添加对 NuGet 包的引用；如果系统上还没有此包，请先安装它。</span><span class="sxs-lookup"><span data-stu-id="56b35-151">Use the **NuGet Package Manager** to add a reference to a NuGet package to your project; and if the package is not already available on your system, install it.</span></span> <span data-ttu-id="56b35-152">要打开包管理器，请选择“工具” > “NuGet 包管理器” > “管理解决方案的 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="56b35-152">To open the package manager, select **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution**.</span></span>

1. <span data-ttu-id="56b35-153">确认已在系统中安装 `Newtonsoft.Json`，如果尚未安装，请先安装它。</span><span class="sxs-lookup"><span data-stu-id="56b35-153">Confirm that `Newtonsoft.Json` is installed on your system and, if it is not, install it.</span></span> <span data-ttu-id="56b35-154">“已安装”选项卡列出了系统中已安装的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="56b35-154">The **Installed** tab lists NuGet packages installed on your system.</span></span> <span data-ttu-id="56b35-155">如果此处未列出 `Newtonsoft.Json`，请选择“浏览”选项卡，然后在搜索框中输入“Newtonsoft.Json”。</span><span class="sxs-lookup"><span data-stu-id="56b35-155">If `Newtonsoft.Json` is not listed there, select the **Browse** tab and enter "Newtonsoft.Json" in the search box.</span></span> <span data-ttu-id="56b35-156">选择 `Newtonsoft.Json`，在右侧窗格中选择项目，然后选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="56b35-156">Select `Newtonsoft.Json` and, in the right pane, select your project before selecting **Install**.</span></span>

1. <span data-ttu-id="56b35-157">如果系统中已安装 `Newtonsoft.Json`，请在“管理解决方案包”选项卡的右侧窗格中选择项目，将该项添加到项目。</span><span class="sxs-lookup"><span data-stu-id="56b35-157">If `Newtonsoft.Json` is already installed on your system, add it to your project by selecting your project in the right pane of hte **Manage Packages for Solution** tab.</span></span>

<span data-ttu-id="56b35-158">请注意，如果依赖框架的部署具有第三方依赖项，则其可移植性只与第三方依赖项相同。</span><span class="sxs-lookup"><span data-stu-id="56b35-158">Note that a framework-dependent deployment with third-party dependencies is only as portable as its third-party dependencies.</span></span> <span data-ttu-id="56b35-159">例如，如果某个第三方库只支持 macOS，该应用将无法移植到 Windows 系统。</span><span class="sxs-lookup"><span data-stu-id="56b35-159">For example, if a third-party library only supports macOS, the app isn't portable to Windows systems.</span></span> <span data-ttu-id="56b35-160">当第三方依赖项本身取决于本机代码时，也可能发生此情况。</span><span class="sxs-lookup"><span data-stu-id="56b35-160">This happens if the third-party dependency itself depends on native code.</span></span> <span data-ttu-id="56b35-161">[Kestrel 服务器](http://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel)就是一个很好的示例，它需要 [libuv](https://github.com/libuv/libuv) 的本机依赖项。</span><span class="sxs-lookup"><span data-stu-id="56b35-161">A good example of this is [Kestrel server](http://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel), which requires a native dependency on [libuv](https://github.com/libuv/libuv).</span></span> <span data-ttu-id="56b35-162">当为具有此类第三方依赖项的应用程序创建 FDD 时，已发布的输出会针对每个本机依赖项支持（存在于 NuGet 包中）的[运行时标识符 (RID)](../rid-catalog.md#what-are-rids) 包含一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="56b35-162">When an FDD is created for an application with this kind of third-party dependency, the published output contains a folder for each [Runtime Identifier (RID)](../rid-catalog.md#what-are-rids) that the native dependency supports (and that exists in its NuGet package).</span></span>

## <span data-ttu-id="56b35-163"><a name="simpleSelf"></a>不包含第三方依赖项的独立部署</span><span class="sxs-lookup"><span data-stu-id="56b35-163"><a name="simpleSelf"></a> Self-contained deployment without third-party dependencies</span></span>

<span data-ttu-id="56b35-164">部署没有第三方依赖项的独立部署包括创建项目、修改 csproj 文件、生成、测试以及发布应用。</span><span class="sxs-lookup"><span data-stu-id="56b35-164">Deploying a self-contained deployment with no third-party dependencies involves creating the project, modifying the *csproj* file, building, testing, and publishing the app.</span></span> <span data-ttu-id="56b35-165">一个用 C# 编写的简单示例可说明此过程。</span><span class="sxs-lookup"><span data-stu-id="56b35-165">A simple example written in C# illustrates the process.</span></span> 

1. <span data-ttu-id="56b35-166">创建项目。</span><span class="sxs-lookup"><span data-stu-id="56b35-166">Create the project.</span></span>

   <span data-ttu-id="56b35-167">选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="56b35-167">Select **File** > **New** > **Project**.</span></span> <span data-ttu-id="56b35-168">在“添加新项目”对话框中，在“已安装”项目类型窗格中选择“.NET Core”，然后在中心窗格中选择“控制台应用(.NET Core)”模板。</span><span class="sxs-lookup"><span data-stu-id="56b35-168">In the **Add New Project** dialog, select **.NET Core** in the **Installed** project types pane, and select the **Console App (.NET Core)** template in the center pane.</span></span> <span data-ttu-id="56b35-169">在“名称”文本框中输入项目名称如“SCD”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="56b35-169">Enter a project name, such as "SCD", in the **Name** text box, and select the **OK** button.</span></span>

1. <span data-ttu-id="56b35-170">添加应用程序的源代码。</span><span class="sxs-lookup"><span data-stu-id="56b35-170">Add the application's source code.</span></span>

   <span data-ttu-id="56b35-171">在编辑器中打开 Program.cs 文件，然后使用下列代码替换自动生成的代码。</span><span class="sxs-lookup"><span data-stu-id="56b35-171">Open the *Program.cs* file in your editor, and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="56b35-172">它会提示用户输入文本，并显示用户输入的个别词。</span><span class="sxs-lookup"><span data-stu-id="56b35-172">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="56b35-173">它使用正则表达式 `\w+` 来将输入文本中的词分开。</span><span class="sxs-lookup"><span data-stu-id="56b35-173">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   <span data-ttu-id="56b35-174">[!code-cs[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]</span><span class="sxs-lookup"><span data-stu-id="56b35-174">[!code-cs[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]</span></span>

1. <span data-ttu-id="56b35-175">定义应用的目标平台。</span><span class="sxs-lookup"><span data-stu-id="56b35-175">Define the platforms that your app will target.</span></span>

   1. <span data-ttu-id="56b35-176">在“解决方案资源管理器”中右键单击项目（而非解决方案），然后选择“编辑 SCD.csproj”。</span><span class="sxs-lookup"><span data-stu-id="56b35-176">Right-click on your project (not the solution) In **Solution Explorer**, and select **Edit SCD.csproj**.</span></span>

   1. <span data-ttu-id="56b35-177">在 csproj 文件（该文件用于定义应用的目标平台）的 `<PropertyGroup>` 部分中创建 `<RuntimeIdentifiers>` 标记，然后指定每个目标平台的运行时标识符 (RID)。</span><span class="sxs-lookup"><span data-stu-id="56b35-177">Create a `<RuntimeIdentifiers>` tag in the `<PropertyGroup>` section of your *csproj* file that defines the platforms your app targets, and specify the runtime identifier (RID) of each platform that you target.</span></span> <span data-ttu-id="56b35-178">请注意，还需要添加分号来分隔 RID。</span><span class="sxs-lookup"><span data-stu-id="56b35-178">Note that you also need to add a semicolon to separate the RIDs.</span></span> <span data-ttu-id="56b35-179">请查看[运行时标识符目录](../rid-catalog.md)，获取运行时标识符列表。</span><span class="sxs-lookup"><span data-stu-id="56b35-179">See [Runtime IDentifier catalog](../rid-catalog.md) for a list of runtime identifiers.</span></span> 

   <span data-ttu-id="56b35-180">例如，以下示例表明应用在 64 位 Windows 10 操作系统和 64 位 OS X 10.11 版本的操作系统上运行。</span><span class="sxs-lookup"><span data-stu-id="56b35-180">For example, the following example indicates that the app runs on 64-bit Windows 10 operating systems and the 64-bit OS X Version 10.11 operating system.</span></span>

```xml
<PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
</PropertyGroup>
```
   <span data-ttu-id="56b35-181">请注意，`<RuntimeIdentifiers>` 元素可能会进入 csproj 文件的任何 `<PropertyGroup>` 中。</span><span class="sxs-lookup"><span data-stu-id="56b35-181">Note that the `<RuntimeIdentifiers>` element can go into any `<PropertyGroup>` that you have in your *csproj* file.</span></span> <span data-ttu-id="56b35-182">本节后面部分将显示完整的示例 csproj 文件。</span><span class="sxs-lookup"><span data-stu-id="56b35-182">A complete sample *csproj* file appears later in this section.</span></span>

1. <span data-ttu-id="56b35-183">创建应用的调试版本。</span><span class="sxs-lookup"><span data-stu-id="56b35-183">Create a Debug build of your app.</span></span>

   <span data-ttu-id="56b35-184">选择“生成” > “生成解决方案”。</span><span class="sxs-lookup"><span data-stu-id="56b35-184">Select **Build** > **Build Solution**.</span></span> <span data-ttu-id="56b35-185">也可通过选择“调试” > “开始调试”来编译和运行应用程序的调试版本。</span><span class="sxs-lookup"><span data-stu-id="56b35-185">You can also compile and run the Debug build of your application by selecting **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="56b35-186">发布你的应用。</span><span class="sxs-lookup"><span data-stu-id="56b35-186">Publish your app.</span></span>

   <span data-ttu-id="56b35-187">调试并测试程序后，为应用的每个目标平台创建要与应用一起部署的文件。</span><span class="sxs-lookup"><span data-stu-id="56b35-187">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

   <span data-ttu-id="56b35-188">若要从 Visual Studio 发布应用，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="56b35-188">To publish your app from Visual Studio, do the following:</span></span>

      1. <span data-ttu-id="56b35-189">将工具栏上的解决方案配置从“调试”更改为“发布”，生成应用的发布（而非调试）版本。</span><span class="sxs-lookup"><span data-stu-id="56b35-189">Change the solution configuration from **Debug** to **Release** on the toolbar to build a Release (rather than a Debug) version of your app.</span></span>

      1. <span data-ttu-id="56b35-190">在“解决方案资源管理器”中右键单击项目（而非解决方案），然后选择“发布”。</span><span class="sxs-lookup"><span data-stu-id="56b35-190">Right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span> 

      1. <span data-ttu-id="56b35-191">在“发布”选项卡上，选择“发布”。</span><span class="sxs-lookup"><span data-stu-id="56b35-191">In the **Publish** tab, select **Publish**.</span></span> <span data-ttu-id="56b35-192">Visual Studio 将包含应用程序的文件写入本地文件系统。</span><span class="sxs-lookup"><span data-stu-id="56b35-192">Visual Studio writes the files that comprise your application to the local file system.</span></span>

      1. <span data-ttu-id="56b35-193">“发布”选项卡现在显示单个配置文件 FolderProfile。</span><span class="sxs-lookup"><span data-stu-id="56b35-193">The **Publish** tab now shows a single profile, **FolderProfile**.</span></span> <span data-ttu-id="56b35-194">该配置文件的配置设置显示在选项卡的“摘要”部分。</span><span class="sxs-lookup"><span data-stu-id="56b35-194">The profile's configuration settings are shown in the **Summary** section of the tab.</span></span> <span data-ttu-id="56b35-195">目标运行时用于标识已发布的运行时，目标位置用于标识独立部署文件的写入位置。</span><span class="sxs-lookup"><span data-stu-id="56b35-195">**Target Runtime** identifies which runtime has been published, and **Target Location** identifies where the files for the self-contained deployment were written.</span></span>

      1. <span data-ttu-id="56b35-196">默认情况下，Visual Studio 将所有已发布文件写入单个目录。</span><span class="sxs-lookup"><span data-stu-id="56b35-196">Visual Studio by default writes all published files to a single directory.</span></span> <span data-ttu-id="56b35-197">为了方便起见，最好为每个目标运行时创建单个配置文件，并将已发布文件置于特定于平台的目录中。</span><span class="sxs-lookup"><span data-stu-id="56b35-197">For convenience, it's best to create separate profiles for each target runtime and to place published files in a platform-specific directory.</span></span> <span data-ttu-id="56b35-198">这包括为每个目标平台创建单独的发布配置文件。</span><span class="sxs-lookup"><span data-stu-id="56b35-198">This involves creating a separate publishing profile for each target platform.</span></span> <span data-ttu-id="56b35-199">现在，请执行下列操作，为每个平台重新生成应用程序：</span><span class="sxs-lookup"><span data-stu-id="56b35-199">So now rebuild the application for each platform by doing the following:</span></span>

         1. <span data-ttu-id="56b35-200">在“发布”对话框中选择“创建新配置文件”。</span><span class="sxs-lookup"><span data-stu-id="56b35-200">Select **Create new profile** in the **Publish** dialog.</span></span>

         1. <span data-ttu-id="56b35-201">在“选取发布目标”对话框中，将“选择文件夹”位置更改为 bin\Release\PublishOutput\win10-x64。</span><span class="sxs-lookup"><span data-stu-id="56b35-201">In the **Pick a publish target** dialog, change the **Choose a folder** location to *bin\Release\PublishOutput\win10-x64*.</span></span> <span data-ttu-id="56b35-202">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="56b35-202">Select **OK**.</span></span>

         1. <span data-ttu-id="56b35-203">在配置文件列表中选择新配置文件 (FolderProfile1) ，并确保“目标运行时”为 `win10-x64`。</span><span class="sxs-lookup"><span data-stu-id="56b35-203">Select the new profile (**FolderProfile1**) in the list of profiles, and make sure that the **Target Runtime** is `win10-x64`.</span></span> <span data-ttu-id="56b35-204">如果不是，请选择“设置”。</span><span class="sxs-lookup"><span data-stu-id="56b35-204">If it isn't, select **Settings**.</span></span> <span data-ttu-id="56b35-205">在“配置文件设置”对话框中，将“目标运行时”更改为 `win10-x64`，然后选择“保存”。</span><span class="sxs-lookup"><span data-stu-id="56b35-205">In the **Profile Settings** dialog, change the **Target Runtime** to `win10-x64` and select **Save**.</span></span> <span data-ttu-id="56b35-206">否则，选择“取消”。</span><span class="sxs-lookup"><span data-stu-id="56b35-206">Otherwise, select **Cancel**.</span></span>

         1. <span data-ttu-id="56b35-207">选择“发布”，发布 64 位 Windows 10 平台的应用。</span><span class="sxs-lookup"><span data-stu-id="56b35-207">Select **Publish** to publish your app for 64-bit Windows 10 platforms.</span></span>

         1. <span data-ttu-id="56b35-208">请再次按照上述步骤创建 `osx.10.11-x64` 平台的配置文件。</span><span class="sxs-lookup"><span data-stu-id="56b35-208">Follow the previous steps again to create a profile for the `osx.10.11-x64` platform.</span></span> <span data-ttu-id="56b35-209">“目标位置”为 bin\Release\PublishOutput\osx.10.11-x64，“目标运行时”为 `osx.10.11-x64`。</span><span class="sxs-lookup"><span data-stu-id="56b35-209">The **Target Location** is *bin\Release\PublishOutput\osx.10.11-x64*, and the **Target Runtime** is `osx.10.11-x64`.</span></span> <span data-ttu-id="56b35-210">Visual Studio 分配给此配置文件的名称是 FolderProfile2。</span><span class="sxs-lookup"><span data-stu-id="56b35-210">The name that Visual Studio assigns to this profile is **FolderProfile2**.</span></span>

      <span data-ttu-id="56b35-211">请注意，每个目标位置中都包含启动应用所需的完整文件集（既包含应用文件，又包含所有 .NET Core 文件）。</span><span class="sxs-lookup"><span data-stu-id="56b35-211">Note that each target location contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="56b35-212">与应用程序的文件一起，发布过程将发出包含应用调试信息的程序数据库 (.pdb) 文件。</span><span class="sxs-lookup"><span data-stu-id="56b35-212">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="56b35-213">该文件主要用于调试异常。</span><span class="sxs-lookup"><span data-stu-id="56b35-213">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="56b35-214">可以选择不使用应用程序文件打包该文件。</span><span class="sxs-lookup"><span data-stu-id="56b35-214">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="56b35-215">但是，如果要调试应用的发布版本，则应保存该文件。</span><span class="sxs-lookup"><span data-stu-id="56b35-215">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="56b35-216">可按照任何喜欢的方式部署已发布的文件。</span><span class="sxs-lookup"><span data-stu-id="56b35-216">Deploy the published files in any way you like.</span></span> <span data-ttu-id="56b35-217">例如，可以使用简单的 `copy` 命令将其打包为 Zip 文件，或者使用选择的安装包进行部署。</span><span class="sxs-lookup"><span data-stu-id="56b35-217">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="56b35-218">下面是此项目完整的 csproj 文件。</span><span class="sxs-lookup"><span data-stu-id="56b35-218">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

## <a name="self-contained-deployment-with-third-party-dependencies"></a><span data-ttu-id="56b35-219">包含第三方依赖项的独立部署</span><span class="sxs-lookup"><span data-stu-id="56b35-219">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="56b35-220">部署包含一个或多个第三方依赖项的独立部署包括添加依赖项。</span><span class="sxs-lookup"><span data-stu-id="56b35-220">Deploying a self-contained deployment with one or more third-party dependencies involves adding the dependencies.</span></span> <span data-ttu-id="56b35-221">在生成应用之前，还需执行以下额外步骤：</span><span class="sxs-lookup"><span data-stu-id="56b35-221">The following additional steps are required before you can build your app:</span></span>

1. <span data-ttu-id="56b35-222">使用 NuGet 包管理器向项目添加对 NuGet 包的引用；如果系统上还没有此包，请先安装它。</span><span class="sxs-lookup"><span data-stu-id="56b35-222">Use the **NuGet Package Manager** to add a reference to a NuGet package to your project; and if the package is not already available on your system, install it.</span></span> <span data-ttu-id="56b35-223">要打开包管理器，请选择“工具” > “NuGet 包管理器” > “管理解决方案的 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="56b35-223">To open the package manager, select **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution**.</span></span>

1. <span data-ttu-id="56b35-224">确认已在系统中安装 `Newtonsoft.Json`，如果尚未安装，请先安装它。</span><span class="sxs-lookup"><span data-stu-id="56b35-224">Confirm that `Newtonsoft.Json` is installed on your system and, if it is not, install it.</span></span> <span data-ttu-id="56b35-225">“已安装”选项卡列出了系统中已安装的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="56b35-225">The **Installed** tab lists NuGet packages installed on your system.</span></span> <span data-ttu-id="56b35-226">如果此处未列出 `Newtonsoft.Json`，请选择“浏览”选项卡，然后在搜索框中输入“Newtonsoft.Json”。</span><span class="sxs-lookup"><span data-stu-id="56b35-226">If `Newtonsoft.Json` is not listed there, select the **Browse** tab and enter "Newtonsoft.Json" in the search box.</span></span> <span data-ttu-id="56b35-227">选择 `Newtonsoft.Json`，在右侧窗格中选择项目，然后选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="56b35-227">Select `Newtonsoft.Json` and, in the right pane, select your project before selecting **Install**.</span></span>

1. <span data-ttu-id="56b35-228">如果系统中已安装 `Newtonsoft.Json`，请在“管理解决方案包”选项卡的右侧窗格中选择项目，将其添加到项目。</span><span class="sxs-lookup"><span data-stu-id="56b35-228">If `Newtonsoft.Json` is already installed on your system, add it to your project by selecting your project in the right pane of the **Manage Packages for Solution** tab.</span></span>

<span data-ttu-id="56b35-229">下面是此项目的完整 csproj 文件：</span><span class="sxs-lookup"><span data-stu-id="56b35-229">The following is the complete *csproj* file for this project:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="56b35-230">部署应用程序时，应用中使用的任何第三方依赖项也包含在应用程序文件中。</span><span class="sxs-lookup"><span data-stu-id="56b35-230">When you deploy your application, any third-party dependencies used in your app are also contained with your application files.</span></span> <span data-ttu-id="56b35-231">运行应用的系统上不需要第三方库。</span><span class="sxs-lookup"><span data-stu-id="56b35-231">Third-party libraries aren't required on the system on which the app is running.</span></span>

<span data-ttu-id="56b35-232">请注意，可以只将具有一个第三方库的独立部署部署到该库支持的平台。</span><span class="sxs-lookup"><span data-stu-id="56b35-232">Note that you can only deploy a self-contained deployment with a third-party library to platforms supported by that library.</span></span> <span data-ttu-id="56b35-233">这与依赖框架的部署中具有本机依赖项和第三方依赖项相似，其中的本机依赖项不会存在于目标平台上，除非之前在该平台上安装了该依赖项。</span><span class="sxs-lookup"><span data-stu-id="56b35-233">This is similar to having third-party dependencies with native dependencies in your framework-dependent deployment, where the native dependencies won't exist on the target platform unless they were previously installed there.</span></span>

# <a name="see-also"></a><span data-ttu-id="56b35-234">请参阅</span><span class="sxs-lookup"><span data-stu-id="56b35-234">See also</span></span>
<span data-ttu-id="56b35-235">[.NET Core 应用程序部署](index.md) </span><span class="sxs-lookup"><span data-stu-id="56b35-235">[.NET Core Application Deployment](index.md) </span></span>  
[<span data-ttu-id="56b35-236">.NET Core 运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="56b35-236">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)   

