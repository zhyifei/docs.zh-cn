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
ms.openlocfilehash: 884ecb110b4168c6dc1e4c664de1dcb8db3734c5
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="deploying-net-core-apps-with-visual-studio"></a><span data-ttu-id="79aa5-104">使用 Visual Studio 部署 .NET Core 应用</span><span class="sxs-lookup"><span data-stu-id="79aa5-104">Deploying .NET Core apps with Visual Studio</span></span>

<span data-ttu-id="79aa5-105">可将 .NET Core 应用程序部署为依赖框架的部署或独立部署，前者包含应用程序二进制文件，但依赖目标系统上存在的 .NET Core，而后者同时包含应用程序和 .NET Core 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="79aa5-105">You can deploy a .NET Core application either as a *framework-dependent deployment*, which includes your application binaries but depends on the presence of .NET Core on the target system, or as a *self-contained deployment*, which includes both your application and .NET Core binaries.</span></span> <span data-ttu-id="79aa5-106">有关 .NET Core 应用程序部署的概述，请参阅 [.NET Core 应用程序部署](index.md)。</span><span class="sxs-lookup"><span data-stu-id="79aa5-106">For an overview of .NET Core application deployment, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="79aa5-107">以下各节演示如何使用 Microsoft Visual Studio 创建下列各类部署：</span><span class="sxs-lookup"><span data-stu-id="79aa5-107">The following sections show how to use Microsoft Visual Studio to create the following kinds of deployments:</span></span>

- <span data-ttu-id="79aa5-108">依赖框架的部署</span><span class="sxs-lookup"><span data-stu-id="79aa5-108">Framework-dependent deployment</span></span>
- <span data-ttu-id="79aa5-109">包含第三方依赖项的依赖框架的部署</span><span class="sxs-lookup"><span data-stu-id="79aa5-109">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="79aa5-110">独立部署</span><span class="sxs-lookup"><span data-stu-id="79aa5-110">Self-contained deployment</span></span>
- <span data-ttu-id="79aa5-111">包含第三方依赖项的独立部署</span><span class="sxs-lookup"><span data-stu-id="79aa5-111">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="79aa5-112">有关使用 Visual Studio 开发 .NET Core 应用程序的信息，请参阅 [Windows 上 .NET Core 的先决条件](../windows-prerequisites.md#prerequisites-with-visual-studio-2017)。</span><span class="sxs-lookup"><span data-stu-id="79aa5-112">For information on using Visual Studio to develop .NET Core applications, see [Prerequisites for .NET Core on Windows](../windows-prerequisites.md#prerequisites-with-visual-studio-2017).</span></span>

## <a name="framework-dependent-deployment"></a><span data-ttu-id="79aa5-113">依赖框架的部署</span><span class="sxs-lookup"><span data-stu-id="79aa5-113">Framework-dependent deployment</span></span>

<span data-ttu-id="79aa5-114">如果不使用第三方依赖项，部属依赖框架的部署只包括生成、测试和发布应用。</span><span class="sxs-lookup"><span data-stu-id="79aa5-114">Deploying a framework-dependent deployment with no third-party dependencies simply involves building, testing, and publishing the app.</span></span> <span data-ttu-id="79aa5-115">一个用 C# 编写的简单示例可说明此过程。</span><span class="sxs-lookup"><span data-stu-id="79aa5-115">A simple example written in C# illustrates the process.</span></span>  

1. <span data-ttu-id="79aa5-116">创建项目。</span><span class="sxs-lookup"><span data-stu-id="79aa5-116">Create the project.</span></span>

   <span data-ttu-id="79aa5-117">选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-117">Select **File** > **New** > **Project**.</span></span> <span data-ttu-id="79aa5-118">在“新建项目”对话框中，在“已安装”项目类型窗格中选择“.NET Core”，然后在中心窗格中选择“控制台应用(.NET Core)”模板。</span><span class="sxs-lookup"><span data-stu-id="79aa5-118">In the **New Project** dialog, select **.NET Core** in the **Installed** project types pane, and select the **Console App (.NET Core)** template in the center pane.</span></span> <span data-ttu-id="79aa5-119">在“名称”文本框中输入项目名称，如“FDD”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-119">Enter a project name, such as "FDD", in the **Name** text box.</span></span> <span data-ttu-id="79aa5-120">选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="79aa5-120">Select the **OK** button.</span></span>

1. <span data-ttu-id="79aa5-121">添加应用程序的源代码。</span><span class="sxs-lookup"><span data-stu-id="79aa5-121">Add the application's source code.</span></span>

   <span data-ttu-id="79aa5-122">在编辑器中打开 Program.cs 文件，然后使用下列代码替换自动生成的代码。</span><span class="sxs-lookup"><span data-stu-id="79aa5-122">Open the *Program.cs* file in the editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="79aa5-123">它会提示用户输入文本，并显示用户输入的个别词。</span><span class="sxs-lookup"><span data-stu-id="79aa5-123">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="79aa5-124">它使用正则表达式 `\w+` 来将输入文本中的词分开。</span><span class="sxs-lookup"><span data-stu-id="79aa5-124">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. <span data-ttu-id="79aa5-125">创建应用的调试版本。</span><span class="sxs-lookup"><span data-stu-id="79aa5-125">Create a Debug build of your app.</span></span>

   <span data-ttu-id="79aa5-126">选择“生成” > “生成解决方案”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-126">Select **Build** > **Build Solution**.</span></span> <span data-ttu-id="79aa5-127">也可通过选择“调试” > “开始调试”来编译和运行应用程序的调试版本。</span><span class="sxs-lookup"><span data-stu-id="79aa5-127">You can also compile and run the Debug build of your application by selecting **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="79aa5-128">部署应用。</span><span class="sxs-lookup"><span data-stu-id="79aa5-128">Deploy your app.</span></span>

   <span data-ttu-id="79aa5-129">调试并测试程序后，创建要与应用一起部署的文件。</span><span class="sxs-lookup"><span data-stu-id="79aa5-129">After you've debugged and tested the program, create the files to be deployed with your app.</span></span> <span data-ttu-id="79aa5-130">若要从 Visual Studio 发布，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="79aa5-130">To publish from Visual Studio, do the following:</span></span>

      1. <span data-ttu-id="79aa5-131">将工具栏上的解决方案配置从“调试”更改为“发布”，生成应用的发布（而非调试）版本。</span><span class="sxs-lookup"><span data-stu-id="79aa5-131">Change the solution configuration from **Debug** to **Release** on the toolbar to build a Release (rather than a Debug) version of your app.</span></span>

      1. <span data-ttu-id="79aa5-132">在“解决方案资源管理器”中右键单击项目（而非解决方案），然后选择“发布”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-132">Right-click on the project (not the solution) in **Solution Explorer**, and select **Publish**.</span></span>

      1. <span data-ttu-id="79aa5-133">在“发布”选项卡上，选择“发布”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-133">In the **Publish** tab, select **Publish**.</span></span> <span data-ttu-id="79aa5-134">Visual Studio 将包含应用程序的文件写入本地文件系统。</span><span class="sxs-lookup"><span data-stu-id="79aa5-134">Visual Studio writes the files that comprise your application to the local file system.</span></span>

      1. <span data-ttu-id="79aa5-135">“发布”选项卡现在显示单个配置文件 FolderProfile。</span><span class="sxs-lookup"><span data-stu-id="79aa5-135">The **Publish** tab now shows a single profile, **FolderProfile**.</span></span> <span data-ttu-id="79aa5-136">该配置文件的配置设置显示在选项卡的“摘要”部分。</span><span class="sxs-lookup"><span data-stu-id="79aa5-136">The profile's configuration settings are shown in the **Summary** section of the tab.</span></span>

   <span data-ttu-id="79aa5-137">生成的文件位于名为 `PublishOutput` 的目录中，该目录位于项目的 .\bin\release 子目录的子目录中。</span><span class="sxs-lookup"><span data-stu-id="79aa5-137">The resulting files are placed in a directory named `PublishOutput` that is in a subdirectory of your project's *.\bin\release* subdirectory.</span></span>

<span data-ttu-id="79aa5-138">与应用程序的文件一起，发布过程将发出包含应用调试信息的程序数据库 (.pdb) 文件。</span><span class="sxs-lookup"><span data-stu-id="79aa5-138">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="79aa5-139">该文件主要用于调试异常。</span><span class="sxs-lookup"><span data-stu-id="79aa5-139">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="79aa5-140">可以选择不使用应用程序文件打包该文件。</span><span class="sxs-lookup"><span data-stu-id="79aa5-140">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="79aa5-141">但是，如果要调试应用的发布版本，则应保存该文件。</span><span class="sxs-lookup"><span data-stu-id="79aa5-141">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="79aa5-142">可以采用任何喜欢的方式部署完整的应用程序文件集。</span><span class="sxs-lookup"><span data-stu-id="79aa5-142">Deploy the complete set of application files in any way you like.</span></span> <span data-ttu-id="79aa5-143">例如，可以使用简单的 `copy` 命令将其打包为 Zip 文件，或者使用选择的安装包进行部署。</span><span class="sxs-lookup"><span data-stu-id="79aa5-143">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span> <span data-ttu-id="79aa5-144">安装成功后，用户可通过使用 `dotnet` 命令或提供应用程序文件名（如 `dotnet fdd.dll`）来执行应用程序。</span><span class="sxs-lookup"><span data-stu-id="79aa5-144">Once installed, users can then execute your application by using the `dotnet` command and providing the application filename, such as `dotnet fdd.dll`.</span></span>

<span data-ttu-id="79aa5-145">除应用程序二进制文件外，安装程序还应捆绑共享框架安装程序，或在安装应用程序的过程中将其作为先决条件进行检查。</span><span class="sxs-lookup"><span data-stu-id="79aa5-145">In addition to the application binaries, your installer should also either bundle the shared framework installer or check for it as a prerequisite as part of the application installation.</span></span>  <span data-ttu-id="79aa5-146">安装共享框架需要管理员/根访问权限，因为它属于计算机范围。</span><span class="sxs-lookup"><span data-stu-id="79aa5-146">Installation of the shared framework requires Administrator/root access since it is machine-wide.</span></span>

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a><span data-ttu-id="79aa5-147">包含第三方依赖项的依赖框架的部署</span><span class="sxs-lookup"><span data-stu-id="79aa5-147">Framework-dependent deployment with third-party dependencies</span></span>

<span data-ttu-id="79aa5-148">要使用一个或多个第三方依赖项来部署依赖框架的部署，需要任何依赖项都可供项目使用。</span><span class="sxs-lookup"><span data-stu-id="79aa5-148">Deploying a framework-dependent deployment with one or more third-party dependencies requires that any dependencies be available to your project.</span></span> <span data-ttu-id="79aa5-149">在生成应用之前，还需执行以下额外步骤：</span><span class="sxs-lookup"><span data-stu-id="79aa5-149">The following additional steps are required before you can build your app:</span></span>

1. <span data-ttu-id="79aa5-150">使用 NuGet 包管理器向项目添加对 NuGet 包的引用；如果系统上还没有此包，请先安装它。</span><span class="sxs-lookup"><span data-stu-id="79aa5-150">Use the **NuGet Package Manager** to add a reference to a NuGet package to your project; and if the package is not already available on your system, install it.</span></span> <span data-ttu-id="79aa5-151">要打开包管理器，请选择“工具” > “NuGet 包管理器” > “管理解决方案的 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-151">To open the package manager, select **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution**.</span></span>

1. <span data-ttu-id="79aa5-152">确认已在系统中安装 `Newtonsoft.Json`，如果尚未安装，请先安装它。</span><span class="sxs-lookup"><span data-stu-id="79aa5-152">Confirm that `Newtonsoft.Json` is installed on your system and, if it is not, install it.</span></span> <span data-ttu-id="79aa5-153">“已安装”选项卡列出了系统中已安装的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="79aa5-153">The **Installed** tab lists NuGet packages installed on your system.</span></span> <span data-ttu-id="79aa5-154">如果此处未列出 `Newtonsoft.Json`，请选择“浏览”选项卡，然后在搜索框中输入“Newtonsoft.Json”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-154">If `Newtonsoft.Json` is not listed there, select the **Browse** tab and enter "Newtonsoft.Json" in the search box.</span></span> <span data-ttu-id="79aa5-155">选择 `Newtonsoft.Json`，在右侧窗格中选择项目，然后选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-155">Select `Newtonsoft.Json` and, in the right pane, select your project before selecting **Install**.</span></span>

1. <span data-ttu-id="79aa5-156">如果系统中已安装 `Newtonsoft.Json`，请在“管理解决方案包”选项卡的右侧窗格中选择项目，将该项添加到项目。</span><span class="sxs-lookup"><span data-stu-id="79aa5-156">If `Newtonsoft.Json` is already installed on your system, add it to your project by selecting your project in the right pane of hte **Manage Packages for Solution** tab.</span></span>

<span data-ttu-id="79aa5-157">请注意，如果依赖框架的部署具有第三方依赖项，则其可移植性只与第三方依赖项相同。</span><span class="sxs-lookup"><span data-stu-id="79aa5-157">Note that a framework-dependent deployment with third-party dependencies is only as portable as its third-party dependencies.</span></span> <span data-ttu-id="79aa5-158">例如，如果某个第三方库只支持 macOS，该应用将无法移植到 Windows 系统。</span><span class="sxs-lookup"><span data-stu-id="79aa5-158">For example, if a third-party library only supports macOS, the app isn't portable to Windows systems.</span></span> <span data-ttu-id="79aa5-159">当第三方依赖项本身取决于本机代码时，也可能发生此情况。</span><span class="sxs-lookup"><span data-stu-id="79aa5-159">This happens if the third-party dependency itself depends on native code.</span></span> <span data-ttu-id="79aa5-160">[Kestrel 服务器](http://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel)就是一个很好的示例，它需要 [libuv](https://github.com/libuv/libuv) 的本机依赖项。</span><span class="sxs-lookup"><span data-stu-id="79aa5-160">A good example of this is [Kestrel server](http://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel), which requires a native dependency on [libuv](https://github.com/libuv/libuv).</span></span> <span data-ttu-id="79aa5-161">当为具有此类第三方依赖项的应用程序创建 FDD 时，已发布的输出会针对每个本机依赖项支持（存在于 NuGet 包中）的[运行时标识符 (RID)](../rid-catalog.md) 包含一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="79aa5-161">When an FDD is created for an application with this kind of third-party dependency, the published output contains a folder for each [Runtime Identifier (RID)](../rid-catalog.md) that the native dependency supports (and that exists in its NuGet package).</span></span>

## <a name="simpleSelf"></a><span data-ttu-id="79aa5-162">不包含第三方依赖项的独立部署</span><span class="sxs-lookup"><span data-stu-id="79aa5-162">Self-contained deployment without third-party dependencies</span></span>

<span data-ttu-id="79aa5-163">部署没有第三方依赖项的独立部署包括创建项目、修改 csproj 文件、生成、测试以及发布应用。</span><span class="sxs-lookup"><span data-stu-id="79aa5-163">Deploying a self-contained deployment with no third-party dependencies involves creating the project, modifying the *csproj* file, building, testing, and publishing the app.</span></span> <span data-ttu-id="79aa5-164">一个用 C# 编写的简单示例可说明此过程。</span><span class="sxs-lookup"><span data-stu-id="79aa5-164">A simple example written in C# illustrates the process.</span></span> 

1. <span data-ttu-id="79aa5-165">创建项目。</span><span class="sxs-lookup"><span data-stu-id="79aa5-165">Create the project.</span></span>

   <span data-ttu-id="79aa5-166">选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-166">Select **File** > **New** > **Project**.</span></span> <span data-ttu-id="79aa5-167">在“添加新项目”对话框中，在“已安装”项目类型窗格中选择“.NET Core”，然后在中心窗格中选择“控制台应用(.NET Core)”模板。</span><span class="sxs-lookup"><span data-stu-id="79aa5-167">In the **Add New Project** dialog, select **.NET Core** in the **Installed** project types pane, and select the **Console App (.NET Core)** template in the center pane.</span></span> <span data-ttu-id="79aa5-168">在“名称”文本框中输入项目名称如“SCD”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="79aa5-168">Enter a project name, such as "SCD", in the **Name** text box, and select the **OK** button.</span></span>

1. <span data-ttu-id="79aa5-169">添加应用程序的源代码。</span><span class="sxs-lookup"><span data-stu-id="79aa5-169">Add the application's source code.</span></span>

   <span data-ttu-id="79aa5-170">在编辑器中打开 Program.cs 文件，然后使用下列代码替换自动生成的代码。</span><span class="sxs-lookup"><span data-stu-id="79aa5-170">Open the *Program.cs* file in your editor, and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="79aa5-171">它会提示用户输入文本，并显示用户输入的个别词。</span><span class="sxs-lookup"><span data-stu-id="79aa5-171">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="79aa5-172">它使用正则表达式 `\w+` 来将输入文本中的词分开。</span><span class="sxs-lookup"><span data-stu-id="79aa5-172">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. <span data-ttu-id="79aa5-173">定义应用的目标平台。</span><span class="sxs-lookup"><span data-stu-id="79aa5-173">Define the platforms that your app will target.</span></span>

   1. <span data-ttu-id="79aa5-174">在“解决方案资源管理器”中右键单击项目（而非解决方案），然后选择“编辑 SCD.csproj”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-174">Right-click on your project (not the solution) In **Solution Explorer**, and select **Edit SCD.csproj**.</span></span>

   1. <span data-ttu-id="79aa5-175">在 csproj 文件（该文件用于定义应用的目标平台）的 `<PropertyGroup>` 部分中创建 `<RuntimeIdentifiers>` 标记，然后指定每个目标平台的运行时标识符 (RID)。</span><span class="sxs-lookup"><span data-stu-id="79aa5-175">Create a `<RuntimeIdentifiers>` tag in the `<PropertyGroup>` section of your *csproj* file that defines the platforms your app targets, and specify the runtime identifier (RID) of each platform that you target.</span></span> <span data-ttu-id="79aa5-176">请注意，还需要添加分号来分隔 RID。</span><span class="sxs-lookup"><span data-stu-id="79aa5-176">Note that you also need to add a semicolon to separate the RIDs.</span></span> <span data-ttu-id="79aa5-177">请查看[运行时标识符目录](../rid-catalog.md)，获取运行时标识符列表。</span><span class="sxs-lookup"><span data-stu-id="79aa5-177">See [Runtime IDentifier catalog](../rid-catalog.md) for a list of runtime identifiers.</span></span> 

   <span data-ttu-id="79aa5-178">例如，以下示例表明应用在 64 位 Windows 10 操作系统和 64 位 OS X 10.11 版本的操作系统上运行。</span><span class="sxs-lookup"><span data-stu-id="79aa5-178">For example, the following example indicates that the app runs on 64-bit Windows 10 operating systems and the 64-bit OS X Version 10.11 operating system.</span></span>

```xml
<PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
</PropertyGroup>
```
   <span data-ttu-id="79aa5-179">请注意，`<RuntimeIdentifiers>` 元素可能会进入 csproj 文件的任何 `<PropertyGroup>` 中。</span><span class="sxs-lookup"><span data-stu-id="79aa5-179">Note that the `<RuntimeIdentifiers>` element can go into any `<PropertyGroup>` that you have in your *csproj* file.</span></span> <span data-ttu-id="79aa5-180">本节后面部分将显示完整的示例 csproj 文件。</span><span class="sxs-lookup"><span data-stu-id="79aa5-180">A complete sample *csproj* file appears later in this section.</span></span>

1. <span data-ttu-id="79aa5-181">创建应用的调试版本。</span><span class="sxs-lookup"><span data-stu-id="79aa5-181">Create a Debug build of your app.</span></span>

   <span data-ttu-id="79aa5-182">选择“生成” > “生成解决方案”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-182">Select **Build** > **Build Solution**.</span></span> <span data-ttu-id="79aa5-183">也可通过选择“调试” > “开始调试”来编译和运行应用程序的调试版本。</span><span class="sxs-lookup"><span data-stu-id="79aa5-183">You can also compile and run the Debug build of your application by selecting **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="79aa5-184">发布你的应用。</span><span class="sxs-lookup"><span data-stu-id="79aa5-184">Publish your app.</span></span>

   <span data-ttu-id="79aa5-185">调试并测试程序后，为应用的每个目标平台创建要与应用一起部署的文件。</span><span class="sxs-lookup"><span data-stu-id="79aa5-185">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

   <span data-ttu-id="79aa5-186">若要从 Visual Studio 发布应用，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="79aa5-186">To publish your app from Visual Studio, do the following:</span></span>

      1. <span data-ttu-id="79aa5-187">将工具栏上的解决方案配置从“调试”更改为“发布”，生成应用的发布（而非调试）版本。</span><span class="sxs-lookup"><span data-stu-id="79aa5-187">Change the solution configuration from **Debug** to **Release** on the toolbar to build a Release (rather than a Debug) version of your app.</span></span>

      1. <span data-ttu-id="79aa5-188">在“解决方案资源管理器”中右键单击项目（而非解决方案），然后选择“发布”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-188">Right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span> 

      1. <span data-ttu-id="79aa5-189">在“发布”选项卡上，选择“发布”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-189">In the **Publish** tab, select **Publish**.</span></span> <span data-ttu-id="79aa5-190">Visual Studio 将包含应用程序的文件写入本地文件系统。</span><span class="sxs-lookup"><span data-stu-id="79aa5-190">Visual Studio writes the files that comprise your application to the local file system.</span></span>

      1. <span data-ttu-id="79aa5-191">“发布”选项卡现在显示单个配置文件 FolderProfile。</span><span class="sxs-lookup"><span data-stu-id="79aa5-191">The **Publish** tab now shows a single profile, **FolderProfile**.</span></span> <span data-ttu-id="79aa5-192">该配置文件的配置设置显示在选项卡的“摘要”部分。目标运行时用于标识已发布的运行时，目标位置用于标识独立部署文件的写入位置。</span><span class="sxs-lookup"><span data-stu-id="79aa5-192">The profile's configuration settings are shown in the **Summary** section of the tab. **Target Runtime** identifies which runtime has been published, and **Target Location** identifies where the files for the self-contained deployment were written.</span></span>

      1. <span data-ttu-id="79aa5-193">默认情况下，Visual Studio 将所有已发布文件写入单个目录。</span><span class="sxs-lookup"><span data-stu-id="79aa5-193">Visual Studio by default writes all published files to a single directory.</span></span> <span data-ttu-id="79aa5-194">为了方便起见，最好为每个目标运行时创建单个配置文件，并将已发布文件置于特定于平台的目录中。</span><span class="sxs-lookup"><span data-stu-id="79aa5-194">For convenience, it's best to create separate profiles for each target runtime and to place published files in a platform-specific directory.</span></span> <span data-ttu-id="79aa5-195">这包括为每个目标平台创建单独的发布配置文件。</span><span class="sxs-lookup"><span data-stu-id="79aa5-195">This involves creating a separate publishing profile for each target platform.</span></span> <span data-ttu-id="79aa5-196">现在，请执行下列操作，为每个平台重新生成应用程序：</span><span class="sxs-lookup"><span data-stu-id="79aa5-196">So now rebuild the application for each platform by doing the following:</span></span>

         1. <span data-ttu-id="79aa5-197">在“发布”对话框中选择“创建新配置文件”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-197">Select **Create new profile** in the **Publish** dialog.</span></span>

         1. <span data-ttu-id="79aa5-198">在“选取发布目标”对话框中，将“选择文件夹”位置更改为 bin\Release\PublishOutput\win10-x64。</span><span class="sxs-lookup"><span data-stu-id="79aa5-198">In the **Pick a publish target** dialog, change the **Choose a folder** location to *bin\Release\PublishOutput\win10-x64*.</span></span> <span data-ttu-id="79aa5-199">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-199">Select **OK**.</span></span>

         1. <span data-ttu-id="79aa5-200">在配置文件列表中选择新配置文件 (FolderProfile1) ，并确保“目标运行时”为 `win10-x64`。</span><span class="sxs-lookup"><span data-stu-id="79aa5-200">Select the new profile (**FolderProfile1**) in the list of profiles, and make sure that the **Target Runtime** is `win10-x64`.</span></span> <span data-ttu-id="79aa5-201">如果不是，请选择“设置”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-201">If it isn't, select **Settings**.</span></span> <span data-ttu-id="79aa5-202">在“配置文件设置”对话框中，将“目标运行时”更改为 `win10-x64`，然后选择“保存”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-202">In the **Profile Settings** dialog, change the **Target Runtime** to `win10-x64` and select **Save**.</span></span> <span data-ttu-id="79aa5-203">否则，选择“取消”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-203">Otherwise, select **Cancel**.</span></span>

         1. <span data-ttu-id="79aa5-204">选择“发布”，发布 64 位 Windows 10 平台的应用。</span><span class="sxs-lookup"><span data-stu-id="79aa5-204">Select **Publish** to publish your app for 64-bit Windows 10 platforms.</span></span>

         1. <span data-ttu-id="79aa5-205">请再次按照上述步骤创建 `osx.10.11-x64` 平台的配置文件。</span><span class="sxs-lookup"><span data-stu-id="79aa5-205">Follow the previous steps again to create a profile for the `osx.10.11-x64` platform.</span></span> <span data-ttu-id="79aa5-206">“目标位置”为 bin\Release\PublishOutput\osx.10.11-x64，“目标运行时”为 `osx.10.11-x64`。</span><span class="sxs-lookup"><span data-stu-id="79aa5-206">The **Target Location** is *bin\Release\PublishOutput\osx.10.11-x64*, and the **Target Runtime** is `osx.10.11-x64`.</span></span> <span data-ttu-id="79aa5-207">Visual Studio 分配给此配置文件的名称是 FolderProfile2。</span><span class="sxs-lookup"><span data-stu-id="79aa5-207">The name that Visual Studio assigns to this profile is **FolderProfile2**.</span></span>

      <span data-ttu-id="79aa5-208">请注意，每个目标位置中都包含启动应用所需的完整文件集（既包含应用文件，又包含所有 .NET Core 文件）。</span><span class="sxs-lookup"><span data-stu-id="79aa5-208">Note that each target location contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="79aa5-209">与应用程序的文件一起，发布过程将发出包含应用调试信息的程序数据库 (.pdb) 文件。</span><span class="sxs-lookup"><span data-stu-id="79aa5-209">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="79aa5-210">该文件主要用于调试异常。</span><span class="sxs-lookup"><span data-stu-id="79aa5-210">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="79aa5-211">可以选择不使用应用程序文件打包该文件。</span><span class="sxs-lookup"><span data-stu-id="79aa5-211">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="79aa5-212">但是，如果要调试应用的发布版本，则应保存该文件。</span><span class="sxs-lookup"><span data-stu-id="79aa5-212">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="79aa5-213">可按照任何喜欢的方式部署已发布的文件。</span><span class="sxs-lookup"><span data-stu-id="79aa5-213">Deploy the published files in any way you like.</span></span> <span data-ttu-id="79aa5-214">例如，可以使用简单的 `copy` 命令将其打包为 Zip 文件，或者使用选择的安装包进行部署。</span><span class="sxs-lookup"><span data-stu-id="79aa5-214">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="79aa5-215">下面是此项目完整的 csproj 文件。</span><span class="sxs-lookup"><span data-stu-id="79aa5-215">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

## <a name="self-contained-deployment-with-third-party-dependencies"></a><span data-ttu-id="79aa5-216">包含第三方依赖项的独立部署</span><span class="sxs-lookup"><span data-stu-id="79aa5-216">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="79aa5-217">部署包含一个或多个第三方依赖项的独立部署包括添加依赖项。</span><span class="sxs-lookup"><span data-stu-id="79aa5-217">Deploying a self-contained deployment with one or more third-party dependencies involves adding the dependencies.</span></span> <span data-ttu-id="79aa5-218">在生成应用之前，还需执行以下额外步骤：</span><span class="sxs-lookup"><span data-stu-id="79aa5-218">The following additional steps are required before you can build your app:</span></span>

1. <span data-ttu-id="79aa5-219">使用 NuGet 包管理器向项目添加对 NuGet 包的引用；如果系统上还没有此包，请先安装它。</span><span class="sxs-lookup"><span data-stu-id="79aa5-219">Use the **NuGet Package Manager** to add a reference to a NuGet package to your project; and if the package is not already available on your system, install it.</span></span> <span data-ttu-id="79aa5-220">要打开包管理器，请选择“工具” > “NuGet 包管理器” > “管理解决方案的 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-220">To open the package manager, select **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution**.</span></span>

1. <span data-ttu-id="79aa5-221">确认已在系统中安装 `Newtonsoft.Json`，如果尚未安装，请先安装它。</span><span class="sxs-lookup"><span data-stu-id="79aa5-221">Confirm that `Newtonsoft.Json` is installed on your system and, if it is not, install it.</span></span> <span data-ttu-id="79aa5-222">“已安装”选项卡列出了系统中已安装的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="79aa5-222">The **Installed** tab lists NuGet packages installed on your system.</span></span> <span data-ttu-id="79aa5-223">如果此处未列出 `Newtonsoft.Json`，请选择“浏览”选项卡，然后在搜索框中输入“Newtonsoft.Json”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-223">If `Newtonsoft.Json` is not listed there, select the **Browse** tab and enter "Newtonsoft.Json" in the search box.</span></span> <span data-ttu-id="79aa5-224">选择 `Newtonsoft.Json`，在右侧窗格中选择项目，然后选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="79aa5-224">Select `Newtonsoft.Json` and, in the right pane, select your project before selecting **Install**.</span></span>

1. <span data-ttu-id="79aa5-225">如果系统中已安装 `Newtonsoft.Json`，请在“管理解决方案包”选项卡的右侧窗格中选择项目，将其添加到项目。</span><span class="sxs-lookup"><span data-stu-id="79aa5-225">If `Newtonsoft.Json` is already installed on your system, add it to your project by selecting your project in the right pane of the **Manage Packages for Solution** tab.</span></span>

<span data-ttu-id="79aa5-226">下面是此项目的完整 csproj 文件：</span><span class="sxs-lookup"><span data-stu-id="79aa5-226">The following is the complete *csproj* file for this project:</span></span>

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

<span data-ttu-id="79aa5-227">部署应用程序时，应用中使用的任何第三方依赖项也包含在应用程序文件中。</span><span class="sxs-lookup"><span data-stu-id="79aa5-227">When you deploy your application, any third-party dependencies used in your app are also contained with your application files.</span></span> <span data-ttu-id="79aa5-228">运行应用的系统上不需要第三方库。</span><span class="sxs-lookup"><span data-stu-id="79aa5-228">Third-party libraries aren't required on the system on which the app is running.</span></span>

<span data-ttu-id="79aa5-229">请注意，可以只将具有一个第三方库的独立部署部署到该库支持的平台。</span><span class="sxs-lookup"><span data-stu-id="79aa5-229">Note that you can only deploy a self-contained deployment with a third-party library to platforms supported by that library.</span></span> <span data-ttu-id="79aa5-230">这与依赖框架的部署中具有本机依赖项和第三方依赖项相似，其中的本机依赖项不会存在于目标平台上，除非之前在该平台上安装了该依赖项。</span><span class="sxs-lookup"><span data-stu-id="79aa5-230">This is similar to having third-party dependencies with native dependencies in your framework-dependent deployment, where the native dependencies won't exist on the target platform unless they were previously installed there.</span></span>

# <a name="see-also"></a><span data-ttu-id="79aa5-231">请参阅</span><span class="sxs-lookup"><span data-stu-id="79aa5-231">See also</span></span>
<span data-ttu-id="79aa5-232">[.NET Core 应用程序部署](index.md) </span><span class="sxs-lookup"><span data-stu-id="79aa5-232">[.NET Core Application Deployment](index.md) </span></span>  
[<span data-ttu-id="79aa5-233">.NET Core 运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="79aa5-233">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)   
