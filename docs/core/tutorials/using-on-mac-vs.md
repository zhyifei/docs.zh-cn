---
title: 通过 Visual Studio for Mac 开始在 macOS 上使用 .NET Core
description: 本主题将指导你使用 Visual Studio for Mac 和 .NET Core 来构建简单的控制台应用程序。
author: mairaw
ms.date: 07/11/2019
ms.custom: seodec18
ms.openlocfilehash: 7dd8d5e8828c5337a52e9d1ea207aa5ef568556e
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69660493"
---
# <a name="get-started-with-net-core-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="d1bc5-103">通过 Visual Studio for Mac 开始在 macOS 上使用 .NET Core</span><span class="sxs-lookup"><span data-stu-id="d1bc5-103">Get started with .NET Core on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="d1bc5-104">Visual Studio for Mac 提供用于开发 .NET Core 应用程序的功能全面的集成开发环境 (IDE)。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="d1bc5-105">本主题将指导你使用 Visual Studio for Mac 和 .NET Core 来构建简单的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-105">This topic walks you through building a simple console application using Visual Studio for Mac and .NET Core.</span></span>

> [!NOTE]
> <span data-ttu-id="d1bc5-106">你的反馈非常有价值。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-106">Your feedback is highly valued.</span></span> <span data-ttu-id="d1bc5-107">有两种方法可以向开发团队提供有关 Visual Studio for Mac 的反馈：</span><span class="sxs-lookup"><span data-stu-id="d1bc5-107">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
> * <span data-ttu-id="d1bc5-108">在 Visual Studio for Mac 中，从菜单中选择“帮助”   > “报告问题”  ，或从欢迎屏幕中选择“报告问题”  ，将打开一个窗口，以供填写 bug 报告。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-108">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="d1bc5-109">可在[开发人员社区](https://developercommunity.visualstudio.com/spaces/8/index.html)门户中跟踪自己的反馈。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-109">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="d1bc5-110">若要提出建议，从菜单中选择“帮助”   > “提供建议”  ，或从欢迎屏幕中选择“提供建议”  ，转到 [Visual Studio for Mac 开发人员社区网页](https://developercommunity.visualstudio.com/content/idea/post.html?space=41)。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-110">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d1bc5-111">系统必备</span><span class="sxs-lookup"><span data-stu-id="d1bc5-111">Prerequisites</span></span>

<span data-ttu-id="d1bc5-112">请参阅 [Mac 上 .NET Core 的先决条件](../macos-prerequisites.md)主题。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-112">See the [Prerequisites for .NET Core on Mac](../macos-prerequisites.md) topic.</span></span>

<span data-ttu-id="d1bc5-113">请查看 [.NET Core 支持](https://docs.microsoft.com/visualstudio/mac/net-core-support?view=vsmac-2019)指南，确保使用的是受支持的 .NET Core 版本。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-113">Check the [.NET Core Support](https://docs.microsoft.com/visualstudio/mac/net-core-support?view=vsmac-2019) guide to ensure you're using a supported version of .NET Core.</span></span>

## <a name="get-started"></a><span data-ttu-id="d1bc5-114">入门</span><span class="sxs-lookup"><span data-stu-id="d1bc5-114">Get started</span></span>

<span data-ttu-id="d1bc5-115">如果已安装先决条件和 Visual Studio for Mac，请跳过此部分，并继续[创建项目](#creating-a-project)。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-115">If you've already installed the prerequisites and Visual Studio for Mac, skip this section and proceed to [Creating a project](#creating-a-project).</span></span> <span data-ttu-id="d1bc5-116">请按照以下步骤安装先决条件和 Visual Studio for Mac：</span><span class="sxs-lookup"><span data-stu-id="d1bc5-116">Follow these steps to install the prerequisites and Visual Studio for Mac:</span></span>

<span data-ttu-id="d1bc5-117">下载 [Visual Studio for Mac 安装程序](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-117">Download the [Visual Studio for Mac installer](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="d1bc5-118">运行安装程序。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-118">Run the installer.</span></span> <span data-ttu-id="d1bc5-119">阅读并同意许可协议。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-119">Read and accept the license agreement.</span></span> <span data-ttu-id="d1bc5-120">在安装过程中，选择用于安装 .NET Core 的选项。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-120">During the install, select the option to install .NET Core.</span></span> <span data-ttu-id="d1bc5-121">你有机会安装 Xamarin，这是一项跨平台移动应用开发技术。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-121">You're provided the opportunity to install Xamarin, a cross-platform mobile app development technology.</span></span> <span data-ttu-id="d1bc5-122">安装 Xamarin 及其相关组件对于 .NET Core 开发而言是可选项。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-122">Installing Xamarin and its related components is optional for .NET Core development.</span></span> <span data-ttu-id="d1bc5-123">有关 Visual Studio for Mac 安装过程的分步介绍，请参阅 [Visual Studio for Mac 文档](/visualstudio/mac/)。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-123">For a walk-through of the Visual Studio for Mac install process, see [Visual Studio for Mac documentation](/visualstudio/mac/).</span></span> <span data-ttu-id="d1bc5-124">安装完成后，启动 Visual Studio for Mac IDE。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-124">When the install is complete, start the Visual Studio for Mac IDE.</span></span>

## <a name="creating-a-project"></a><span data-ttu-id="d1bc5-125">创建项目</span><span class="sxs-lookup"><span data-stu-id="d1bc5-125">Creating a project</span></span>

1. <span data-ttu-id="d1bc5-126">在“开始”窗口上，选择“新建”  。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-126">Select **New** on the Start Window.</span></span>

   ![Visual Studio for Mac 开始屏幕上的“新建”按钮](./media/using-on-mac-vs/visual-studio-mac-new-project.png)

1. <span data-ttu-id="d1bc5-128">在“新建项目”  对话框中，选择“.NET Core”  节点下的“应用”  。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-128">In the **New Project** dialog, select **App** under the **.NET Core** node.</span></span> <span data-ttu-id="d1bc5-129">单击“下一步”  ，然后选择“控制台应用程序”  模板。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-129">Select the **Console Application** template followed by **Next**.</span></span>

   ![新项目模板列表](./media/using-on-mac-vs/visual-studio-mac-new-dialog.png)

1. <span data-ttu-id="d1bc5-131">如果安装了多个版本的 .NET Core，请选择项目的目标框架。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-131">If you have more than one version of .NET Core installed, select the target framework for your project.</span></span>

1. <span data-ttu-id="d1bc5-132">为“项目名称”  键入“HelloWorld”。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-132">Type "HelloWorld" for the **Project Name**.</span></span> <span data-ttu-id="d1bc5-133">选择“创建”  。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-133">Select **Create**.</span></span>

   ![配置新的控制台应用程序对话框](./media/using-on-mac-vs/visual-studio-mac-new-options.png)

1. <span data-ttu-id="d1bc5-135">等待还原项目的依赖项。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-135">Wait while the project's dependencies are restored.</span></span> <span data-ttu-id="d1bc5-136">该项目包含一个 C# 文件 *Program.cs*，其中包含具有 `Main` 方法的 `Program` 类。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-136">The project has a single C# file, *Program.cs*, containing a `Program` class with a `Main` method.</span></span> <span data-ttu-id="d1bc5-137">运行应用时，`Console.WriteLine` 语句将“Hello World!”</span><span class="sxs-lookup"><span data-stu-id="d1bc5-137">The `Console.WriteLine` statement will output "Hello World!"</span></span> <span data-ttu-id="d1bc5-138">输出至控制台。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-138">to the console when the app is run.</span></span>

   ![打开 Program.cs 文件的主窗口](./media/using-on-mac-vs/visual-studio-mac-editor.png)

## <a name="run-the-application"></a><span data-ttu-id="d1bc5-140">运行此应用程序</span><span class="sxs-lookup"><span data-stu-id="d1bc5-140">Run the application</span></span>

<span data-ttu-id="d1bc5-141">使用 ⌘ ↵（command + enter 键）在调试模式下运行应用，或者使用 ⌥ ⌘ ↵（option + command + enter 键）在发布模式下运行应用。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-141">Run the app in Debug mode using ⌘ ↵ (command + enter) or in Release mode using ⌥ ⌘ ↵ (option + command + enter).</span></span>

![应用程序输出窗格显示 Hello World!](./media/using-on-mac-vs/visual-studio-mac-output.png)

## <a name="next-step"></a><span data-ttu-id="d1bc5-143">下一步</span><span class="sxs-lookup"><span data-stu-id="d1bc5-143">Next step</span></span>

<span data-ttu-id="d1bc5-144">[使用 Visual Studio for Mac 在 macOS 上构建完整的 .NET Core 解决方案](using-on-mac-vs-full-solution.md)主题为你演示如何构建包含可重用的库和单元测试的完整的 .NET Core 解决方案。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-144">The [Building a complete .NET Core solution on macOS using Visual Studio for Mac](using-on-mac-vs-full-solution.md) topic shows you how to build a complete .NET Core solution that includes a reusable library and unit testing.</span></span>
