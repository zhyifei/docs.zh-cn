---
title: 使用 Visual Studio 发布 .NET Core Hello World 应用程序
description: 发布会创建运行 .NET Core 应用程序所需的一组文件。
author: BillWagner
ms.author: wiwagn
ms.date: 12/10/2019
ms.custom: vs-dotnet
ms.openlocfilehash: bdd6e28713bdece2bd144e6763bd84d719e91449
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156629"
---
# <a name="publish-your-net-core-hello-world-application-with-visual-studio"></a><span data-ttu-id="69e5b-103">使用 Visual Studio 发布 .NET Core Hello World 应用程序</span><span class="sxs-lookup"><span data-stu-id="69e5b-103">Publish your .NET Core Hello World application with Visual Studio</span></span>

<span data-ttu-id="69e5b-104">在[在 Visual Studio 中使用 .NET Core 创建 Hello World 应用程序](with-visual-studio.md)中，生成了 Hello World 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="69e5b-104">In [Create a Hello World application with .NET Core in Visual Studio](with-visual-studio.md), you built a Hello World console application.</span></span> <span data-ttu-id="69e5b-105">在[使用 Visual Studio 调试 Hello World 应用程序](debugging-with-visual-studio.md)中，使用 Visual Studio 调试程序测试了应用程序。</span><span class="sxs-lookup"><span data-stu-id="69e5b-105">In [Debug your Hello World application with Visual Studio](debugging-with-visual-studio.md), you tested it using the Visual Studio debugger.</span></span> <span data-ttu-id="69e5b-106">至此，你已确定应用程序能够按预期运行，可以发布它以供其他用户运行了。</span><span class="sxs-lookup"><span data-stu-id="69e5b-106">Now that you're sure that it works as expected, you can publish it so that other users can run it.</span></span> <span data-ttu-id="69e5b-107">发布应用程序会创建运行应用程序所需的一组文件。</span><span class="sxs-lookup"><span data-stu-id="69e5b-107">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="69e5b-108">若要部署文件，请将文件复制到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="69e5b-108">To deploy the files, copy them to the target machine.</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="69e5b-109">发布应用</span><span class="sxs-lookup"><span data-stu-id="69e5b-109">Publish the app</span></span>

1. <span data-ttu-id="69e5b-110">请确保 Visual Studio 生成的是应用程序的发布版本。</span><span class="sxs-lookup"><span data-stu-id="69e5b-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="69e5b-111">必要时，将工具栏上的生成配置设置从“调试”  更改为“发布”  。</span><span class="sxs-lookup"><span data-stu-id="69e5b-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![选定发布版本的 Visual Studio 工具栏](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="69e5b-113">右键单击“HelloWorld”  项目（而不是 HelloWorld 解决方案），然后选择菜单中的“发布”  。</span><span class="sxs-lookup"><span data-stu-id="69e5b-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span> <span data-ttu-id="69e5b-114">（还可以选择“生成”  主菜单中的“发布 HelloWorld”  。）</span><span class="sxs-lookup"><span data-stu-id="69e5b-114">(You can also select **Publish HelloWorld** from the main **Build** menu.)</span></span>

   ![Visual Studio 发布上下文菜单](media/publishing-with-visual-studio/publish-context-menu.png)

1. <span data-ttu-id="69e5b-116">在“选择发布目标”  页上，选择“文件夹”  ，然后选择“创建配置文件”  。</span><span class="sxs-lookup"><span data-stu-id="69e5b-116">On the **Pick a publish target** page, select **Folder**, and then select **Create Profile**.</span></span>

   ![在 Visual Studio 中选择发布目标](media/publishing-with-visual-studio/pick-publish-target.png)

1. <span data-ttu-id="69e5b-118">在“发布”  页上，选择“发布”  。</span><span class="sxs-lookup"><span data-stu-id="69e5b-118">On the **Publish** page, select **Publish**.</span></span>

   ![Visual Studio 发布窗口](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a><span data-ttu-id="69e5b-120">检查文件</span><span class="sxs-lookup"><span data-stu-id="69e5b-120">Inspect the files</span></span>

<span data-ttu-id="69e5b-121">发布过程中会生成依赖于框架的部署，在此类部署中，若系统上安装了 .NET Core，已发布的应用程序可在 .NET Core 支持的任何平台上运行。</span><span class="sxs-lookup"><span data-stu-id="69e5b-121">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on any platform supported by .NET Core with .NET Core installed on the system.</span></span> <span data-ttu-id="69e5b-122">用户可以通过双击可执行文件或从命令提示符发出 `dotnet HelloWorld.dll` 命令来运行发布的应用。</span><span class="sxs-lookup"><span data-stu-id="69e5b-122">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="69e5b-123">在下面的步骤中，查看由发布过程创建的文件。</span><span class="sxs-lookup"><span data-stu-id="69e5b-123">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="69e5b-124">打开命令提示。</span><span class="sxs-lookup"><span data-stu-id="69e5b-124">Open a command prompt.</span></span>

   <span data-ttu-id="69e5b-125">打开命令提示符的一种方法是，在 Windows 任务栏上的搜索框中输入“命令提示符”  （或简写的“cmd”  ）。</span><span class="sxs-lookup"><span data-stu-id="69e5b-125">One way to open a command prompt is to enter **Command Prompt** (or **cmd** for short) in the search box on the Windows taskbar.</span></span> <span data-ttu-id="69e5b-126">选择“命令提示符”  桌面应用或按 Enter  （如果已在搜索结果中选择）。</span><span class="sxs-lookup"><span data-stu-id="69e5b-126">Select the **Command Prompt** desktop app, or press **Enter** if it's already selected in the search results.</span></span>

1. <span data-ttu-id="69e5b-127">导航到已发布的应用程序，它位于应用程序项目目录的 bin\Release\netcoreapp3.1\publish  子目录中。</span><span class="sxs-lookup"><span data-stu-id="69e5b-127">Navigate to the published application in the *bin\Release\netcoreapp3.1\publish* subdirectory of the application's project directory.</span></span>

   ![显示已发布文件的控制台窗口](media/publishing-with-visual-studio/published-files-output.png)

   <span data-ttu-id="69e5b-129">如下图所示，已发布的输出包括以下文件：</span><span class="sxs-lookup"><span data-stu-id="69e5b-129">As the image shows, the published output includes the following files:</span></span>

      * <span data-ttu-id="69e5b-130">HelloWorld.deps.json </span><span class="sxs-lookup"><span data-stu-id="69e5b-130">*HelloWorld.deps.json*</span></span>

         <span data-ttu-id="69e5b-131">这是应用程序的运行时依赖项文件。</span><span class="sxs-lookup"><span data-stu-id="69e5b-131">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="69e5b-132">它定义了运行应用程序所需的 .NET Core 组件和库（包括包含该应用程序的动态链接库）。</span><span class="sxs-lookup"><span data-stu-id="69e5b-132">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="69e5b-133">有关详细信息，请参阅[运行时配置文件](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="69e5b-133">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

      * <span data-ttu-id="69e5b-134">HelloWorld.dll </span><span class="sxs-lookup"><span data-stu-id="69e5b-134">*HelloWorld.dll*</span></span>

         <span data-ttu-id="69e5b-135">这是应用程序的[依赖于框架的部署](../deploying/deploy-with-cli.md#framework-dependent-deployment)版本。</span><span class="sxs-lookup"><span data-stu-id="69e5b-135">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="69e5b-136">若要执行此动态链接库，请在命令提示符处输入 `dotnet HelloWorld.dll`。</span><span class="sxs-lookup"><span data-stu-id="69e5b-136">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span>

      * <span data-ttu-id="69e5b-137">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="69e5b-137">*HelloWorld.exe*</span></span>

         <span data-ttu-id="69e5b-138">这是应用程序的[依赖于框架的可执行文件](../deploying/deploy-with-cli.md#framework-dependent-executable)版本。</span><span class="sxs-lookup"><span data-stu-id="69e5b-138">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="69e5b-139">若要运行该版本，请在命令提示符处输入 `HelloWorld.exe`。</span><span class="sxs-lookup"><span data-stu-id="69e5b-139">To run it, enter `HelloWorld.exe` at a command prompt.</span></span>

      * <span data-ttu-id="69e5b-140">HelloWorld.pdb  （对于部署是可选的）</span><span class="sxs-lookup"><span data-stu-id="69e5b-140">*HelloWorld.pdb* (optional for deployment)</span></span>

         <span data-ttu-id="69e5b-141">这是调试符号文件。</span><span class="sxs-lookup"><span data-stu-id="69e5b-141">This is the debug symbols file.</span></span> <span data-ttu-id="69e5b-142">尽管应在需要调试应用程序的已发布版本时保存此文件，但无需将此文件与应用程序一起部署。</span><span class="sxs-lookup"><span data-stu-id="69e5b-142">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

      * <span data-ttu-id="69e5b-143">HelloWorld.runtimeconfig.json </span><span class="sxs-lookup"><span data-stu-id="69e5b-143">*HelloWorld.runtimeconfig.json*</span></span>

         <span data-ttu-id="69e5b-144">这是应用程序的运行时配置文件。</span><span class="sxs-lookup"><span data-stu-id="69e5b-144">This is the application's run-time configuration file.</span></span> <span data-ttu-id="69e5b-145">它标识用于运行应用程序的 .NET Core 版本。</span><span class="sxs-lookup"><span data-stu-id="69e5b-145">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="69e5b-146">还可向其添加配置选项。</span><span class="sxs-lookup"><span data-stu-id="69e5b-146">You can also add configuration options to it.</span></span> <span data-ttu-id="69e5b-147">有关详细信息，请参阅 [.NET Core 运行时配置设置](../run-time-config/index.md#runtimeconfigjson)。</span><span class="sxs-lookup"><span data-stu-id="69e5b-147">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="69e5b-148">其他资源</span><span class="sxs-lookup"><span data-stu-id="69e5b-148">Additional resources</span></span>

- [<span data-ttu-id="69e5b-149">.NET Core 应用程序部署</span><span class="sxs-lookup"><span data-stu-id="69e5b-149">.NET Core application deployment</span></span>](../deploying/index.md)
