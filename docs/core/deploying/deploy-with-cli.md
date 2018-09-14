---
title: 使用 CLI 工具部署 .NET Core 应用
description: 了解如何使用命令行接口 (CLI) 工具部署 .NET Core 应用
author: rpetrusha
ms.author: ronpet
ms.date: 09/05/2018
dev_langs:
- csharp
- vb
ms.openlocfilehash: a7e810372d831699eae777186385e45fe65cdf45
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44272886"
---
# <a name="deploying-net-core-apps-with-command-line-interface-cli-tools"></a><span data-ttu-id="0271e-103">使用命令行接口 (CLI) 工具部署 .NET Core 应用</span><span class="sxs-lookup"><span data-stu-id="0271e-103">Deploying .NET Core apps with command-line interface (CLI) tools</span></span>

<span data-ttu-id="0271e-104">可将 .NET Core 应用程序部署为依赖框架的部署或独立部署，前者包含应用程序二进制文件，但依赖目标系统上存在的 .NET Core，而后者同时包含应用程序和 .NET Core 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="0271e-104">You can deploy a .NET Core application either as a *framework-dependent deployment*, which includes your application binaries but depends on the presence of .NET Core on the target system, or as a *self-contained deployment*, which includes both your application and the .NET Core binaries.</span></span> <span data-ttu-id="0271e-105">请参阅 [.NET Core 应用程序部署](index.md)了解相关概述。</span><span class="sxs-lookup"><span data-stu-id="0271e-105">For an overview, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="0271e-106">以下各节演示如何使用 [.NET Core 命令行接口工具](../tools/index.md)创建下列各类部署：</span><span class="sxs-lookup"><span data-stu-id="0271e-106">The following sections show how to use [.NET Core command-line interface tools](../tools/index.md) to create the following kinds of deployments:</span></span>

- <span data-ttu-id="0271e-107">依赖框架的部署</span><span class="sxs-lookup"><span data-stu-id="0271e-107">Framework-dependent deployment</span></span>
- <span data-ttu-id="0271e-108">包含第三方依赖项的依赖框架的部署</span><span class="sxs-lookup"><span data-stu-id="0271e-108">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="0271e-109">独立部署</span><span class="sxs-lookup"><span data-stu-id="0271e-109">Self-contained deployment</span></span>
- <span data-ttu-id="0271e-110">包含第三方依赖项的独立部署</span><span class="sxs-lookup"><span data-stu-id="0271e-110">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="0271e-111">从命令行工作时，可使用所选的程序编辑器。</span><span class="sxs-lookup"><span data-stu-id="0271e-111">When working from the command line, you can use a program editor of your choice.</span></span> <span data-ttu-id="0271e-112">如果使用的程序编辑器是 [Visual Studio Code](https://code.visualstudio.com)，则可通过选择“视图” > “集成终端”打开 Visual Studio Code 环境中的命令控制台。</span><span class="sxs-lookup"><span data-stu-id="0271e-112">If your program editor is [Visual Studio Code](https://code.visualstudio.com), you can open a command console inside your Visual Studio Code environment by selecting **View** > **Integrated Terminal**.</span></span>

## <a name="framework-dependent-deployment"></a><span data-ttu-id="0271e-113">依赖框架的部署</span><span class="sxs-lookup"><span data-stu-id="0271e-113">Framework-dependent deployment</span></span>

<span data-ttu-id="0271e-114">如果不使用第三方依赖项，部属依赖框架的部署只包括生成、测试和发布应用。</span><span class="sxs-lookup"><span data-stu-id="0271e-114">Deploying a framework-dependent deployment with no third-party dependencies simply involves building, testing, and publishing the app.</span></span> <span data-ttu-id="0271e-115">一个用 C# 编写的简单示例可说明此过程。</span><span class="sxs-lookup"><span data-stu-id="0271e-115">A simple example written in C# illustrates the process.</span></span>

1. <span data-ttu-id="0271e-116">创建项目目录。</span><span class="sxs-lookup"><span data-stu-id="0271e-116">Create a project directory.</span></span>

   <span data-ttu-id="0271e-117">为项目创建一个目录，并将其设为当前目录。</span><span class="sxs-lookup"><span data-stu-id="0271e-117">Create a directory for your project and make it your current directory.</span></span>

1. <span data-ttu-id="0271e-118">创建项目。</span><span class="sxs-lookup"><span data-stu-id="0271e-118">Create the project.</span></span>

   <span data-ttu-id="0271e-119">在命令行中，键入 [dotnet new console](../tools/dotnet-new.md) 以创建新的 C# 控制台项目或键入 [dotnet new console -lang vb](../tools/dotnet-new.md) 以在该目录中创建新的 Visual Basic 控制台项目。</span><span class="sxs-lookup"><span data-stu-id="0271e-119">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project or [dotnet new console -lang vb](../tools/dotnet-new.md) to create a new Visual Basic console project in that directory.</span></span>

1. <span data-ttu-id="0271e-120">添加应用程序的源代码。</span><span class="sxs-lookup"><span data-stu-id="0271e-120">Add the application's source code.</span></span>

   <span data-ttu-id="0271e-121">在编辑器中打开 Program.cs 文件或 Program.vb 文件，然后使用下列代码替换自动生成的代码。</span><span class="sxs-lookup"><span data-stu-id="0271e-121">Open the *Program.cs* or *Program.vb* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="0271e-122">它会提示用户输入文本，并显示用户输入的个别词。</span><span class="sxs-lookup"><span data-stu-id="0271e-122">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="0271e-123">它使用正则表达式 `\w+` 来将输入文本中的词分开。</span><span class="sxs-lookup"><span data-stu-id="0271e-123">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](~/samples/snippets/core/deploying/cs/deployment-example.cs)]
   [!code-vb[deployment#1](~/samples/snippets/core/deploying/vb/deployment-example.vb)]

1. <span data-ttu-id="0271e-124">更新项目的依赖项和工具。</span><span class="sxs-lookup"><span data-stu-id="0271e-124">Update the project's dependencies and tools.</span></span>

   <span data-ttu-id="0271e-125">运行 [dotnet restore](../tools/dotnet-restore.md)（[请参阅注释](#dotnet-restore-note)）命令，还原项目中指定的依赖项。</span><span class="sxs-lookup"><span data-stu-id="0271e-125">Run the [dotnet restore](../tools/dotnet-restore.md) ([see note](#dotnet-restore-note)) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="0271e-126">创建应用的调试版本。</span><span class="sxs-lookup"><span data-stu-id="0271e-126">Create a Debug build of your app.</span></span>

   <span data-ttu-id="0271e-127">使用 [dotnet 生成](../tools/dotnet-build.md)命令生成应用程序，或使用 [dotnet 运行](../tools/dotnet-run.md)命令生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="0271e-127">Use the [dotnet build](../tools/dotnet-build.md) command to build your application or the [dotnet run](../tools/dotnet-run.md) command to build and run it.</span></span>

1. <span data-ttu-id="0271e-128">部署应用。</span><span class="sxs-lookup"><span data-stu-id="0271e-128">Deploy your app.</span></span>

   <span data-ttu-id="0271e-129">完成程序调试和测试后，使用下列命令创建部署：</span><span class="sxs-lookup"><span data-stu-id="0271e-129">After you've debugged and tested the program, create the deployment by using the following command:</span></span>

      ```console
      dotnet publish -f netcoreapp2.1 -c Release
      ```
   <span data-ttu-id="0271e-130">这将创建一个应用的发行版（而不是调试版）。</span><span class="sxs-lookup"><span data-stu-id="0271e-130">This creates a Release (rather than a Debug) version of your app.</span></span> <span data-ttu-id="0271e-131">生成的文件位于名为“发布”的目录中，该目录位于项目的 bin 目录的子目录中。</span><span class="sxs-lookup"><span data-stu-id="0271e-131">The resulting files are placed in a directory named *publish*      that's in a subdirectory of your project's *bin* directory.</span></span>

   <span data-ttu-id="0271e-132">与应用程序的文件一起，发布过程将发出包含应用调试信息的程序数据库 (.pdb) 文件。</span><span class="sxs-lookup"><span data-stu-id="0271e-132">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="0271e-133">该文件主要用于调试异常。</span><span class="sxs-lookup"><span data-stu-id="0271e-133">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="0271e-134">可以选择不将其与应用程序的文件一起分布。</span><span class="sxs-lookup"><span data-stu-id="0271e-134">You can choose not to distribute it with your application's files.</span></span> <span data-ttu-id="0271e-135">但是，如果要调试应用的发布版本，则应保存该文件。</span><span class="sxs-lookup"><span data-stu-id="0271e-135">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

   <span data-ttu-id="0271e-136">可以采用任何喜欢的方式部署完整的应用程序文件集。</span><span class="sxs-lookup"><span data-stu-id="0271e-136">You can deploy the complete set of application files in any way you like.</span></span> <span data-ttu-id="0271e-137">例如，可以使用简单的 `copy` 命令将其打包为 Zip 文件，或者使用选择的安装包进行部署。</span><span class="sxs-lookup"><span data-stu-id="0271e-137">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

1. <span data-ttu-id="0271e-138">运行你的应用</span><span class="sxs-lookup"><span data-stu-id="0271e-138">Run your app</span></span>

   <span data-ttu-id="0271e-139">安装成功后，用户可通过使用 `dotnet` 命令或提供应用程序文件名（如 `dotnet fdd.dll`）来执行应用程序。</span><span class="sxs-lookup"><span data-stu-id="0271e-139">Once installed, users can execute your application by using the `dotnet` command and providing the application filename, such as `dotnet fdd.dll`.</span></span>

   <span data-ttu-id="0271e-140">除应用程序二进制文件外，安装程序还应捆绑共享框架安装程序，或在安装应用程序的过程中将其作为先决条件进行检查。</span><span class="sxs-lookup"><span data-stu-id="0271e-140">In addition to the application binaries, your installer should also either bundle the shared framework installer or check for it as a prerequisite as part of the application installation.</span></span>  <span data-ttu-id="0271e-141">安装共享框架需要管理员/根访问权限。</span><span class="sxs-lookup"><span data-stu-id="0271e-141">Installation of the shared framework requires Administrator/root access.</span></span>

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a><span data-ttu-id="0271e-142">包含第三方依赖项的依赖框架的部署</span><span class="sxs-lookup"><span data-stu-id="0271e-142">Framework-dependent deployment with third-party dependencies</span></span>

<span data-ttu-id="0271e-143">要使用一个或多个第三方依赖项来部署依赖框架的部署，需要这些依赖项都可供项目使用。</span><span class="sxs-lookup"><span data-stu-id="0271e-143">Deploying a framework-dependent deployment with one or more third-party dependencies requires that those dependencies be available to your project.</span></span> <span data-ttu-id="0271e-144">在运行 `dotnet restore`（[请参阅注释](#dotnet-restore-note)）命令之前，还需执行额外两个步骤：</span><span class="sxs-lookup"><span data-stu-id="0271e-144">Two additional steps are required before you can run the `dotnet restore` ([see note](#dotnet-restore-note)) command:</span></span>

1. <span data-ttu-id="0271e-145">向 csproj 文件的 `<ItemGroup>` 部分添加对所需第三方库的引用。</span><span class="sxs-lookup"><span data-stu-id="0271e-145">Add references to required third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="0271e-146">以下 `<ItemGroup>` 部分包含 [Json.NET](http://www.newtonsoft.com/json) 的依赖项（作为第三方库）：</span><span class="sxs-lookup"><span data-stu-id="0271e-146">The following `<ItemGroup>` section contains a dependency on [Json.NET](http://www.newtonsoft.com/json) as a third-party library:</span></span>

      ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
      ```

1. <span data-ttu-id="0271e-147">如果尚未安装，请下载包含第三方依赖项的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="0271e-147">If you haven't already, download the NuGet package containing the third-party dependency.</span></span> <span data-ttu-id="0271e-148">若要下载该包，请在添加依赖项后执行 `dotnet restore`（[请参阅注释](#dotnet-restore-note)）命令。</span><span class="sxs-lookup"><span data-stu-id="0271e-148">To download the package, execute the `dotnet restore` ([see note](#dotnet-restore-note)) command after adding the dependency.</span></span> <span data-ttu-id="0271e-149">因为依赖项在发布时已从本地 NuGet 缓存解析出来，因此它一定适用于你的系统。</span><span class="sxs-lookup"><span data-stu-id="0271e-149">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="0271e-150">请注意，如果依赖框架的部署具有第三方依赖项，则其可移植性只与第三方依赖项相同。</span><span class="sxs-lookup"><span data-stu-id="0271e-150">Note that a framework-dependent deployment with third-party dependencies is only as portable as its third-party dependencies.</span></span> <span data-ttu-id="0271e-151">例如，如果某个第三方库只支持 macOS，该应用将无法移植到 Windows 系统。</span><span class="sxs-lookup"><span data-stu-id="0271e-151">For example, if a third-party library only supports macOS, the app isn't portable to Windows systems.</span></span> <span data-ttu-id="0271e-152">当第三方依赖项本身取决于本机代码时，也可能发生此情况。</span><span class="sxs-lookup"><span data-stu-id="0271e-152">This happens if the third-party dependency itself depends on native code.</span></span> <span data-ttu-id="0271e-153">[Kestrel 服务器](/aspnet/core/fundamentals/servers/kestrel)就是一个很好的示例，它需要 [libuv](https://github.com/libuv/libuv) 的本机依赖项。</span><span class="sxs-lookup"><span data-stu-id="0271e-153">A good example of this is [Kestrel server](/aspnet/core/fundamentals/servers/kestrel), which requires a native dependency on [libuv](https://github.com/libuv/libuv).</span></span> <span data-ttu-id="0271e-154">当为具有此类第三方依赖项的应用程序创建 FDD 时，已发布的输出会针对每个本机依赖项支持（存在于 NuGet 包中）的[运行时标识符 (RID)](../rid-catalog.md) 包含一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="0271e-154">When an FDD is created for an application with this kind of third-party dependency, the published output contains a folder for each [Runtime Identifier (RID)](../rid-catalog.md) that the native dependency supports (and that exists in its NuGet package).</span></span>

## <a name="simpleSelf"></a><span data-ttu-id="0271e-155">不包含第三方依赖项的独立部署</span><span class="sxs-lookup"><span data-stu-id="0271e-155">Self-contained deployment without third-party dependencies</span></span>

<span data-ttu-id="0271e-156">部署没有第三方依赖项的独立部署包括创建项目、修改 csproj 文件、生成、测试以及发布应用。</span><span class="sxs-lookup"><span data-stu-id="0271e-156">Deploying a self-contained deployment without third-party dependencies involves creating the project, modifying the *csproj* file, building, testing, and publishing the app.</span></span> <span data-ttu-id="0271e-157">一个用 C# 编写的简单示例可说明此过程。</span><span class="sxs-lookup"><span data-stu-id="0271e-157">A simple example written in C# illustrates the process.</span></span> <span data-ttu-id="0271e-158">该示例演示如何使用命令行中的 [dotnet 实用工具](../tools/dotnet.md)创建独立部署。</span><span class="sxs-lookup"><span data-stu-id="0271e-158">The example shows how to create a self-contained deployment using the [dotnet utility](../tools/dotnet.md) from the command line.</span></span>

1. <span data-ttu-id="0271e-159">为项目创建目录。</span><span class="sxs-lookup"><span data-stu-id="0271e-159">Create a directory for the project.</span></span>

   <span data-ttu-id="0271e-160">为项目创建一个目录，并将其设为当前目录。</span><span class="sxs-lookup"><span data-stu-id="0271e-160">Create a directory for your project, and make it your current directory.</span></span>

1. <span data-ttu-id="0271e-161">创建项目。</span><span class="sxs-lookup"><span data-stu-id="0271e-161">Create the project.</span></span>

   <span data-ttu-id="0271e-162">在命令栏行中，键入 [dotnet new console](../tools/dotnet-new.md)，在该目录中创建新的 C# 控制台项目。</span><span class="sxs-lookup"><span data-stu-id="0271e-162">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project in that directory.</span></span>

1. <span data-ttu-id="0271e-163">添加应用程序的源代码。</span><span class="sxs-lookup"><span data-stu-id="0271e-163">Add the application's source code.</span></span>

   <span data-ttu-id="0271e-164">在编辑器中打开 Program.cs 文件，然后使用下列代码替换自动生成的代码。</span><span class="sxs-lookup"><span data-stu-id="0271e-164">Open the *Program.cs* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="0271e-165">它会提示用户输入文本，并显示用户输入的个别词。</span><span class="sxs-lookup"><span data-stu-id="0271e-165">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="0271e-166">它使用正则表达式 `\w+` 来将输入文本中的词分开。</span><span class="sxs-lookup"><span data-stu-id="0271e-166">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](~/samples/snippets/core/deploying/cs/deployment-example.cs)]
   [!code-vb[deployment#1](~/samples/snippets/core/deploying/vb/deployment-example.vb)]
1. <span data-ttu-id="0271e-167">定义应用的目标平台。</span><span class="sxs-lookup"><span data-stu-id="0271e-167">Define the platforms that your app will target.</span></span>

   <span data-ttu-id="0271e-168">在 csproj 文件（该文件用于定义应用的目标平台）的 `<PropertyGroup>` 部分中创建 `<RuntimeIdentifiers>` 标记，然后指定每个目标平台的运行时标识符 (RID)。</span><span class="sxs-lookup"><span data-stu-id="0271e-168">Create a `<RuntimeIdentifiers>` tag in the `<PropertyGroup>` section of your *csproj* file that defines the platforms your app targets and specify the runtime identifier (RID) for each platform that you target.</span></span> <span data-ttu-id="0271e-169">请注意，还需要添加分号来分隔 RID。</span><span class="sxs-lookup"><span data-stu-id="0271e-169">Note that you also need to add a semicolon to separate the RIDs.</span></span> <span data-ttu-id="0271e-170">请查看[运行时标识符目录](../rid-catalog.md)，获取运行时标识符列表。</span><span class="sxs-lookup"><span data-stu-id="0271e-170">See [Runtime IDentifier catalog](../rid-catalog.md) for a list of runtime identifiers.</span></span>

   <span data-ttu-id="0271e-171">例如，以下 `<PropertyGroup>` 部分表明应用在 64 位 Windows 10 操作系统和 64 位 OS X 10.11 版本的操作系统上运行。</span><span class="sxs-lookup"><span data-stu-id="0271e-171">For example, the following `<PropertyGroup>` section indicates that the app runs on 64-bit Windows 10 operating systems and the 64-bit OS X Version 10.11 operating system.</span></span>

     ```xml
     <PropertyGroup>
         <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
     </PropertyGroup>
     ```

   <span data-ttu-id="0271e-172">请注意，`<RuntimeIdentifiers>` 元素可能出现在 csproj 文件的任何 `<PropertyGroup>` 中。</span><span class="sxs-lookup"><span data-stu-id="0271e-172">Note that the `<RuntimeIdentifiers>` element can appear in any `<PropertyGroup>` in your *csproj* file.</span></span> <span data-ttu-id="0271e-173">本节后面部分将显示完整的示例 csproj 文件。</span><span class="sxs-lookup"><span data-stu-id="0271e-173">A complete sample *csproj* file appears later in this section.</span></span>

1. <span data-ttu-id="0271e-174">更新项目的依赖项和工具。</span><span class="sxs-lookup"><span data-stu-id="0271e-174">Update the project's dependencies and tools.</span></span>

   <span data-ttu-id="0271e-175">运行 [dotnet restore](../tools/dotnet-restore.md)（[请参阅注释](#dotnet-restore-note)）命令，还原项目中指定的依赖项。</span><span class="sxs-lookup"><span data-stu-id="0271e-175">Run the [dotnet restore](../tools/dotnet-restore.md) ([see note](#dotnet-restore-note)) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="0271e-176">确定是否要使用全球化固定模式。</span><span class="sxs-lookup"><span data-stu-id="0271e-176">Determine whether you want to use globalization invariant mode.</span></span>

   <span data-ttu-id="0271e-177">特别是如果应用面向 Linux，则可以通过利用[全球化固定模式](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md)来减小部署的总规模。</span><span class="sxs-lookup"><span data-stu-id="0271e-177">Particularly if your app targets Linux, you can reduce the total size of your deployment by taking advantage of [globalization invariant mode](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).</span></span> <span data-ttu-id="0271e-178">全球化固定模式适用于不具有全局意识且可以使用[固定区域性](xref:System.Globalization.CultureInfo.InvariantCulture)的格式约定、大小写约定以及字符串比较和排序顺序的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0271e-178">Globalization invariant mode is useful for applications that are not globally aware and that can use the formatting conventions, casing conventions, and string comparison and sort order of the [invariant culture](xref:System.Globalization.CultureInfo.InvariantCulture).</span></span>

   <span data-ttu-id="0271e-179">要启用固定模式，右键单击“解决方案资源管理器”中的项目（不是解决方案），然后选择“编辑 SCD.csproj”或“编辑 SCD.vbproj”。</span><span class="sxs-lookup"><span data-stu-id="0271e-179">To enable invariant mode, right-click on your project (not the solution) in **Solution Explorer**, and select **Edit SCD.csproj** or **Edit SCD.vbproj**.</span></span> <span data-ttu-id="0271e-180">然后将以下突出显示的行添加到文件中：</span><span class="sxs-lookup"><span data-stu-id="0271e-180">Then add the following highlighted lines to the file:</span></span>

 [!code-xml[globalization-invariant-mode](~/samples/snippets/core/deploying/xml/invariant.csproj)]

1. <span data-ttu-id="0271e-181">创建应用的调试版本。</span><span class="sxs-lookup"><span data-stu-id="0271e-181">Create a Debug build of your app.</span></span>

   <span data-ttu-id="0271e-182">在命令行中，使用 [dotnet 生成](../tools/dotnet-build.md)命令。</span><span class="sxs-lookup"><span data-stu-id="0271e-182">From the command line, use the [dotnet build](../tools/dotnet-build.md) command.</span></span>

1. <span data-ttu-id="0271e-183">调试并测试程序后，为应用的每个目标平台创建要与应用一起部署的文件。</span><span class="sxs-lookup"><span data-stu-id="0271e-183">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

   <span data-ttu-id="0271e-184">同时对两个目标平台使用 `dotnet publish` 命令，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0271e-184">Use the `dotnet publish` command for both target platforms as follows:</span></span>

      ```console
      dotnet publish -c Release -r win10-x64
      dotnet publish -c Release -r osx.10.11-x64
      ```

   <span data-ttu-id="0271e-185">这将为每个目标平台创建一个应用的发行版（而不是调试版）。</span><span class="sxs-lookup"><span data-stu-id="0271e-185">This creates a Release (rather than a Debug) version of your app for each target platform.</span></span> <span data-ttu-id="0271e-186">生成的文件位于名为“发布”的子目录中，该子目录位于项目的 .\bin\Release\netcoreapp2.1\<runtime_identifier> 子目录的子目录中。</span><span class="sxs-lookup"><span data-stu-id="0271e-186">The resulting files are placed in a subdirectory named *publish* that's in a subdirectory of your project's *.\bin\Release\netcoreapp2.1\<runtime_identifier>* subdirectory.</span></span> <span data-ttu-id="0271e-187">请注意，每个子目录中都包含完整的启动应用所需的文件集（既有应用文件，也有所有 .NET Core 文件）。</span><span class="sxs-lookup"><span data-stu-id="0271e-187">Note that each subdirectory contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="0271e-188">与应用程序的文件一起，发布过程将发出包含应用调试信息的程序数据库 (.pdb) 文件。</span><span class="sxs-lookup"><span data-stu-id="0271e-188">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="0271e-189">该文件主要用于调试异常。</span><span class="sxs-lookup"><span data-stu-id="0271e-189">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="0271e-190">可以选择不使用应用程序文件打包该文件。</span><span class="sxs-lookup"><span data-stu-id="0271e-190">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="0271e-191">但是，如果要调试应用的发布版本，则应保存该文件。</span><span class="sxs-lookup"><span data-stu-id="0271e-191">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="0271e-192">可按照任何喜欢的方式部署已发布的文件。</span><span class="sxs-lookup"><span data-stu-id="0271e-192">Deploy the published files in any way you like.</span></span> <span data-ttu-id="0271e-193">例如，可以使用简单的 `copy` 命令将其打包为 Zip 文件，或者使用选择的安装包进行部署。</span><span class="sxs-lookup"><span data-stu-id="0271e-193">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="0271e-194">下面是此项目完整的 csproj 文件。</span><span class="sxs-lookup"><span data-stu-id="0271e-194">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

## <a name="self-contained-deployment-with-third-party-dependencies"></a><span data-ttu-id="0271e-195">包含第三方依赖项的独立部署</span><span class="sxs-lookup"><span data-stu-id="0271e-195">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="0271e-196">部署包含一个或多个第三方依赖项的独立部署包括添加依赖项。</span><span class="sxs-lookup"><span data-stu-id="0271e-196">Deploying a self-contained deployment with one or more third-party dependencies involves adding the dependencies.</span></span> <span data-ttu-id="0271e-197">在运行 `dotnet restore`（[请参阅注释](#dotnet-restore-note)）命令之前，还需执行额外两个步骤：</span><span class="sxs-lookup"><span data-stu-id="0271e-197">Two additional steps are required before you can run the `dotnet restore` ([see note](#dotnet-restore-note)) command:</span></span>

1. <span data-ttu-id="0271e-198">将对任何第三方库的引用添加到 csproj 文件的 `<ItemGroup>` 部分。</span><span class="sxs-lookup"><span data-stu-id="0271e-198">Add references to any third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="0271e-199">以下 `<ItemGroup>` 部分使用 Json.NET 作为第三方库。</span><span class="sxs-lookup"><span data-stu-id="0271e-199">The following `<ItemGroup>` section uses Json.NET as a third-party library.</span></span>

    ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
    ```

1. <span data-ttu-id="0271e-200">如果尚未安装，请将包含第三方依赖项的 NuGet 包下载到系统。</span><span class="sxs-lookup"><span data-stu-id="0271e-200">If you haven't already, download the NuGet package containing the third-party dependency to your system.</span></span> <span data-ttu-id="0271e-201">若要使依赖项对应用适用，请在添加依赖项后执行 `dotnet restore`（[请参阅注释](#dotnet-restore-note)）命令。</span><span class="sxs-lookup"><span data-stu-id="0271e-201">To make the dependency available to your app, execute the `dotnet restore` ([see note](#dotnet-restore-note)) command after adding the dependency.</span></span> <span data-ttu-id="0271e-202">因为依赖项在发布时已从本地 NuGet 缓存解析出来，因此它一定适用于你的系统。</span><span class="sxs-lookup"><span data-stu-id="0271e-202">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="0271e-203">下面是此项目的完整 csproj 文件：</span><span class="sxs-lookup"><span data-stu-id="0271e-203">The following is the complete *csproj* file for this project:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="0271e-204">部署应用程序时，应用中使用的任何第三方依赖项也包含在应用程序文件中。</span><span class="sxs-lookup"><span data-stu-id="0271e-204">When you deploy your application, any third-party dependencies used in your app are also contained with your application files.</span></span> <span data-ttu-id="0271e-205">运行应用的系统上不需要第三方库。</span><span class="sxs-lookup"><span data-stu-id="0271e-205">Third-party libraries aren't required on the system on which the app is running.</span></span>

<span data-ttu-id="0271e-206">请注意，可以只将具有一个第三方库的独立部署部署到该库支持的平台。</span><span class="sxs-lookup"><span data-stu-id="0271e-206">Note that you can only deploy a self-contained deployment with a third-party library to platforms supported by that library.</span></span> <span data-ttu-id="0271e-207">这与依赖框架的部署中具有本机依赖项和第三方依赖项相似，其中的本机依赖项必须与部署应用的平台兼容。</span><span class="sxs-lookup"><span data-stu-id="0271e-207">This is similar to having third-party dependencies with native dependencies in a framework-dependent deployment, where the native dependencies must be compatible with the platform to which the app is deployed.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

## <a name="see-also"></a><span data-ttu-id="0271e-208">请参阅</span><span class="sxs-lookup"><span data-stu-id="0271e-208">See also</span></span>

* [<span data-ttu-id="0271e-209">.NET Core 应用程序部署</span><span class="sxs-lookup"><span data-stu-id="0271e-209">.NET Core Application Deployment</span></span>](index.md)
* [<span data-ttu-id="0271e-210">.NET Core 运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="0271e-210">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
