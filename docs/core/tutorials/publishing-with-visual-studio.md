---
title: "使用 Visual Studio 2017 发布 Hello World 应用程序"
description: "发布应用程序会创建运行应用程序所需的一组文件。"
keywords: ".NET, .NET Core, 控制台应用程序, 发布, 部署"
author: BillWagner
ms.author: wiwagn
ms.date: 10/05/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a19545d3-24af-4a32-9778-cfb5ae938287
ms.openlocfilehash: a3e5bda5c99144c9ab5bbaf5e2f5566261af4813
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="publish-your-hello-world-application-with-visual-studio-2017"></a><span data-ttu-id="cde95-104">使用 Visual Studio 2017 发布 Hello World 应用程序</span><span class="sxs-lookup"><span data-stu-id="cde95-104">Publish your Hello World application with Visual Studio 2017</span></span>

<span data-ttu-id="cde95-105">在[使用 Visual Studio 2017 生成 C# .NET Core Hello World 应用程序](with-visual-studio.md)或[使用 Visual Studio 2017 生成 Visual Basic .NET Core Hello World 应用程序](vb-with-visual-studio.md)中，生成了 Hello World 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="cde95-105">In [Build a C# Hello World application with .NET Core in Visual Studio 2017](with-visual-studio.md) or [Build a Visual Basic Hello World application with .NET Core in Visual Studio 2017](vb-with-visual-studio.md), you built a Hello World console application.</span></span> <span data-ttu-id="cde95-106">在[使用 Visual Studio 2017 调试 C# Hello World 应用程序](debugging-with-visual-studio.md)中，使用 Visual Studio 调试程序测试了应用程序。</span><span class="sxs-lookup"><span data-stu-id="cde95-106">In [Debug your C# Hello World application with Visual Studio 2017](debugging-with-visual-studio.md), you tested it using the Visual Studio debugger.</span></span> <span data-ttu-id="cde95-107">至此，你已确定应用程序能够按预期运行，可以发布它以供其他用户运行了。</span><span class="sxs-lookup"><span data-stu-id="cde95-107">Now that you're sure that it works as expected, you can publish it so that other users can run it.</span></span> <span data-ttu-id="cde95-108">发布应用程序会创建运行应用程序所需的一组文件；可以通过将这些文件复制到目标计算机来进行部署。</span><span class="sxs-lookup"><span data-stu-id="cde95-108">Publishing creates the set of files that are needed to run your application, and you can deploy the files by copying them to a target machine.</span></span>

<span data-ttu-id="cde95-109">若要发布并运行应用程序，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cde95-109">To publish and run your application:</span></span> 

1. <span data-ttu-id="cde95-110">请确保 Visual Studio 生成的是应用程序的发布版本。</span><span class="sxs-lookup"><span data-stu-id="cde95-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="cde95-111">必要时，将工具栏上的生成配置设置从“调试”更改为“发布”。</span><span class="sxs-lookup"><span data-stu-id="cde95-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![Visual Studio 工具栏](media/publishing-with-visual-studio/toolbar.png)

1. <span data-ttu-id="cde95-113">右键单击“HelloWorld”项目（而不是 HelloWorld 解决方案），然后选择菜单中的“发布”。</span><span class="sxs-lookup"><span data-stu-id="cde95-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span> <span data-ttu-id="cde95-114">还可以选择**“生成”**Visual Studio 主菜单中的**“发布 HelloWorld”**。</span><span class="sxs-lookup"><span data-stu-id="cde95-114">You can also select **Publish HelloWorld** from the main Visual Studio **Build** menu.</span></span>

   ![Visual Studio 工具栏](media/publishing-with-visual-studio/publish1.png)


   ![Visual Studio 工具栏](media/publishing-with-visual-studio/publishwindow.png)

1. <span data-ttu-id="cde95-117">打开控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="cde95-117">Open a console window.</span></span> <span data-ttu-id="cde95-118">例如，在 Windows 任务栏的“在此处键入内容以进行搜索”文本框中，输入“`Command Prompt`”（或缩写“`cmd`”），再选择“命令提示符”桌面应用程序或按 Enter（如果已在搜索结果中选择），打开控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="cde95-118">For example in the **Type here to search** text box in the Windows taskbar, enter `Command Prompt` (or `cmd` for short), and open a console window by either selecting the **Command Prompt** desktop app or pressing Enter if it's selected in the search results.</span></span>

1. <span data-ttu-id="cde95-119">导航到已发布的应用程序，它位于应用程序项目目录的 `bin\release\PublishOutput` 子目录中。</span><span class="sxs-lookup"><span data-stu-id="cde95-119">Navigate to the published application in the `bin\release\PublishOutput` subdirectory of your application's project directory.</span></span> <span data-ttu-id="cde95-120">如下图所示，已发布的输出包括以下四个文件：</span><span class="sxs-lookup"><span data-stu-id="cde95-120">As the following figure shows, the published output includes the following four files:</span></span>

      * <span data-ttu-id="cde95-121">HelloWorld.deps.json</span><span class="sxs-lookup"><span data-stu-id="cde95-121">*HelloWorld.deps.json*</span></span>

         <span data-ttu-id="cde95-122">应用程序的运行时依赖项文件。</span><span class="sxs-lookup"><span data-stu-id="cde95-122">The application's runtime dependencies file.</span></span> <span data-ttu-id="cde95-123">它定义.NET 核心组件和运行你的应用程序所需的库 （包括包含你的应用程序的动态链接库）。</span><span class="sxs-lookup"><span data-stu-id="cde95-123">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run your application.</span></span> <span data-ttu-id="cde95-124">有关详细信息，请参阅[运行时配置文件](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="cde95-124">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>
 
      * <span data-ttu-id="cde95-125">HelloWorld.dll</span><span class="sxs-lookup"><span data-stu-id="cde95-125">*HelloWorld.dll*</span></span>

         <span data-ttu-id="cde95-126">包含你的应用程序的文件。</span><span class="sxs-lookup"><span data-stu-id="cde95-126">The file that contains your application.</span></span> <span data-ttu-id="cde95-127">它是一个动态链接库，可以通过输入执行`dotnet HelloWorld.dll`命令在控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="cde95-127">It is a dynamic link library that can be executed by entering the `dotnet HelloWorld.dll` command in a console window.</span></span> 

      * <span data-ttu-id="cde95-128">HelloWorld.pdb（对于部署是可选的）</span><span class="sxs-lookup"><span data-stu-id="cde95-128">*HelloWorld.pdb* (optional for deployment)</span></span>

         <span data-ttu-id="cde95-129">包含调试符号文件。</span><span class="sxs-lookup"><span data-stu-id="cde95-129">A file that contains debug symbols.</span></span> <span data-ttu-id="cde95-130">尽管应在需要调试应用程序的已发布版本时保存此文件，但无需将此文件与应用程序一起部署。</span><span class="sxs-lookup"><span data-stu-id="cde95-130">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

      * <span data-ttu-id="cde95-131">HelloWorld.runtimeconfig.json</span><span class="sxs-lookup"><span data-stu-id="cde95-131">*HelloWorld.runtimeconfig.json*</span></span>

         <span data-ttu-id="cde95-132">应用程序的运行时配置文件。</span><span class="sxs-lookup"><span data-stu-id="cde95-132">The application's runtime configuration file.</span></span> <span data-ttu-id="cde95-133">它标识你的应用程序生成上运行的.NET 核心的版本。</span><span class="sxs-lookup"><span data-stu-id="cde95-133">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="cde95-134">有关详细信息，请参阅[运行时配置文件](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="cde95-134">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>  

   ![显示已发布文件的控制台窗口](media/publishing-with-visual-studio/publishedfiles.png)

<span data-ttu-id="cde95-136">发布过程中会生成依赖于框架的部署，在此类部署中，若系统上安装了 .NET Core，已发布的应用程序可在 .NET Core 支持的任何平台上运行。</span><span class="sxs-lookup"><span data-stu-id="cde95-136">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application will run on any platform supported by .NET Core with .NET Core installed on the system.</span></span> <span data-ttu-id="cde95-137">用户可以通过在控制台窗口中发出 `dotnet HelloWorld.dll` 命令来运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="cde95-137">Users can run your application by issuing the `dotnet HelloWorld.dll` command from a console window.</span></span>

<span data-ttu-id="cde95-138">若要详细了解如何发布和部署 .NET Core 应用程序，请参阅 [.NET Core 应用程序部署](../../core/deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="cde95-138">For more information on publishing and deploying .NET Core applications, see [.NET Core Application Deployment](../../core/deploying/index.md).</span></span>
