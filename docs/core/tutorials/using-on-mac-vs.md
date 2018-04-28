---
title: 借助 Visual Studio for Mac 在 macOS 上开始使用.NET Core
description: 本主题将指导你使用 Visual Studio for Mac 和 .NET Core 来构建简单的控制台应用程序。
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.topic: get-started-article
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 97a9c62280f09f244028c066a04350a59dd0400d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="getting-started-with-net-core-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="bc195-103">借助 Visual Studio for Mac 在 macOS 上开始使用.NET Core</span><span class="sxs-lookup"><span data-stu-id="bc195-103">Getting started with .NET Core on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="bc195-104">Visual Studio for Mac 提供用于开发 .NET Core 应用程序的功能全面的集成开发环境 (IDE)。</span><span class="sxs-lookup"><span data-stu-id="bc195-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="bc195-105">本主题将指导你使用 Visual Studio for Mac 和 .NET Core 来构建简单的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="bc195-105">This topic walks you through building a simple console application using Visual Studio for Mac and .NET Core.</span></span>

> [!NOTE]
> <span data-ttu-id="bc195-106">你的反馈非常有价值。</span><span class="sxs-lookup"><span data-stu-id="bc195-106">Your feedback is highly valued.</span></span> <span data-ttu-id="bc195-107">有两种方法可以向开发团队提供有关 Visual Studio for Mac 的反馈：</span><span class="sxs-lookup"><span data-stu-id="bc195-107">There are a two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
> * <span data-ttu-id="bc195-108">在 Visual Studio for Mac 中，从菜单中选择“帮助” > “报告问题”，或从欢迎屏幕中选择“报告问题”，将打开一个窗口，以供填写 bug 报告。</span><span class="sxs-lookup"><span data-stu-id="bc195-108">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="bc195-109">可在[开发人员社区](https://developercommunity.visualstudio.com/spaces/8/index.html)门户中跟踪自己的反馈。</span><span class="sxs-lookup"><span data-stu-id="bc195-109">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="bc195-110">若要提出建议，从菜单中选择“帮助” > “提供建议”，或从欢迎屏幕中选择“提供建议”，转到 [Visual Studio for Mac UserVoice 网页](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac)。</span><span class="sxs-lookup"><span data-stu-id="bc195-110">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac UserVoice webpage](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bc195-111">系统必备</span><span class="sxs-lookup"><span data-stu-id="bc195-111">Prerequisites</span></span>

<span data-ttu-id="bc195-112">请参阅 [Mac 上 .NET Core 的先决条件](../../core/macos-prerequisites.md)主题。</span><span class="sxs-lookup"><span data-stu-id="bc195-112">See the [Prerequisites for .NET Core on Mac](../../core/macos-prerequisites.md) topic.</span></span>

## <a name="getting-started"></a><span data-ttu-id="bc195-113">入门</span><span class="sxs-lookup"><span data-stu-id="bc195-113">Getting started</span></span>

<span data-ttu-id="bc195-114">如果已安装先决条件和 Visual Studio for Mac，请跳过此部分，并继续[创建项目](#creating-a-project)。</span><span class="sxs-lookup"><span data-stu-id="bc195-114">If you've already installed the prerequisites and Visual Studio for Mac, skip this section and proceed to [Creating a project](#creating-a-project).</span></span> <span data-ttu-id="bc195-115">请按照以下步骤安装先决条件和 Visual Studio for Mac：</span><span class="sxs-lookup"><span data-stu-id="bc195-115">Follow these steps to install the prerequisites and Visual Studio for Mac:</span></span>

<span data-ttu-id="bc195-116">下载 [Visual Studio for Mac 安装程序](https://www.visualstudio.com/vs/visual-studio-mac/)。</span><span class="sxs-lookup"><span data-stu-id="bc195-116">Download the [Visual Studio for Mac installer](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span> <span data-ttu-id="bc195-117">运行安装程序。</span><span class="sxs-lookup"><span data-stu-id="bc195-117">Run the installer.</span></span> <span data-ttu-id="bc195-118">阅读并同意许可协议。</span><span class="sxs-lookup"><span data-stu-id="bc195-118">Read and accept the license agreement.</span></span> <span data-ttu-id="bc195-119">在安装过程中，为你提供安装 Xamarin（一个跨平台移动应用开发技术）的机会。</span><span class="sxs-lookup"><span data-stu-id="bc195-119">During the install, you're provided the opportunity to install Xamarin, a cross-platform mobile app development technology.</span></span> <span data-ttu-id="bc195-120">安装 Xamarin 及其相关组件对于 .NET Core 开发而言是可选项。</span><span class="sxs-lookup"><span data-stu-id="bc195-120">Installing Xamarin and its related components is optional for .NET Core development.</span></span> <span data-ttu-id="bc195-121">有关 Visual Studio for Mac 安装过程的分步介绍，请参阅 [Visual Studio for Mac 简介](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/)。</span><span class="sxs-lookup"><span data-stu-id="bc195-121">For a walk-through of the Visual Studio for Mac install process, see [Introducing Visual Studio for Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/).</span></span> <span data-ttu-id="bc195-122">安装完成后，启动 Visual Studio for Mac IDE。</span><span class="sxs-lookup"><span data-stu-id="bc195-122">When the install is complete, start the Visual Studio for Mac IDE.</span></span>

## <a name="creating-a-project"></a><span data-ttu-id="bc195-123">创建项目</span><span class="sxs-lookup"><span data-stu-id="bc195-123">Creating a project</span></span>

1. <span data-ttu-id="bc195-124">选择欢迎屏幕上的“新建项目”。</span><span class="sxs-lookup"><span data-stu-id="bc195-124">Select **New Project** on the Welcome screen.</span></span>

   ![Visual Studio for Mac 欢迎屏幕上的新建项目按钮](./media/using-on-mac-vs/vsmac1.png)

1. <span data-ttu-id="bc195-126">在“新建项目”对话框中，选择“.NET Core”节点下的“应用”。</span><span class="sxs-lookup"><span data-stu-id="bc195-126">In the **New Project** dialog, select **App** under the **.NET Core** node.</span></span> <span data-ttu-id="bc195-127">单击“下一步”，然后选择“控制台应用程序”模板。</span><span class="sxs-lookup"><span data-stu-id="bc195-127">Select the **Console Application** template followed by **Next**.</span></span>

   ![新项目模板列表](./media/using-on-mac-vs/vsmac2.png)

1. <span data-ttu-id="bc195-129">为“项目名称”键入“HelloWorld”。</span><span class="sxs-lookup"><span data-stu-id="bc195-129">Type "HelloWorld" for the **Project Name**.</span></span> <span data-ttu-id="bc195-130">选择“创建”。</span><span class="sxs-lookup"><span data-stu-id="bc195-130">Select **Create**.</span></span>

   ![配置新的控制台应用程序对话框](./media/using-on-mac-vs/vsmac3.png)

1. <span data-ttu-id="bc195-132">等待还原项目的依赖项。</span><span class="sxs-lookup"><span data-stu-id="bc195-132">Wait while the project's dependencies are restored.</span></span> <span data-ttu-id="bc195-133">该项目包含一个 C# 文件 *Program.cs*，其中包含具有 `Main` 方法的 `Program` 类。</span><span class="sxs-lookup"><span data-stu-id="bc195-133">The project has a single C# file, *Program.cs*, containing a `Program` class with a `Main` method.</span></span> <span data-ttu-id="bc195-134">运行应用时，`Console.WriteLine` 语句将“Hello World!”</span><span class="sxs-lookup"><span data-stu-id="bc195-134">The `Console.WriteLine` statement will output "Hello World!"</span></span> <span data-ttu-id="bc195-135">输出至控制台。</span><span class="sxs-lookup"><span data-stu-id="bc195-135">to the console when the app is run.</span></span>

   ![打开 Program.cs 文件的主窗口](./media/using-on-mac-vs/vsmac4.png)

## <a name="run-the-application"></a><span data-ttu-id="bc195-137">运行此应用程序</span><span class="sxs-lookup"><span data-stu-id="bc195-137">Run the application</span></span>

<span data-ttu-id="bc195-138">使用 <kbd>F5</kbd> 在调试模式下运行此应用，或使用 <kbd>Ctrl</kbd>+<kbd>F5</kbd> 在发布模式下运行此应用。</span><span class="sxs-lookup"><span data-stu-id="bc195-138">Run the app in Debug mode using <kbd>F5</kbd> or in Release mode using <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span></span>

![应用程序输出窗格显示 Hello World!](./media/using-on-mac-vs/vsmac5.png)

## <a name="next-step"></a><span data-ttu-id="bc195-140">下一步</span><span class="sxs-lookup"><span data-stu-id="bc195-140">Next step</span></span>

<span data-ttu-id="bc195-141">[使用 Visual Studio for Mac 在 macOS 上构建完整的 .NET Core 解决方案](using-on-mac-vs-full-solution.md)主题为你演示如何构建包含可重用的库和单元测试的完整的 .NET Core 解决方案。</span><span class="sxs-lookup"><span data-stu-id="bc195-141">The [Building a complete .NET Core solution on macOS using Visual Studio for Mac](using-on-mac-vs-full-solution.md) topic shows you how to build a complete .NET Core solution that includes a reusable library and unit testing.</span></span>
