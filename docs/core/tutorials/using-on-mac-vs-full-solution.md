---
title: 使用 Visual Studio for Mac 构建完整的 .NET Core 解决方案
description: 本文演示了构建包含可重用的库和单元测试的 .NET Core 解决方案。
ms.date: 12/19/2019
ms.openlocfilehash: 8c9fcca404a3875b6bb7f9cf20551a017ff553c5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "78239958"
---
# <a name="build-a-complete-net-core-solution-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="26222-103">使用 Visual Studio for Mac 在 macOS 上构建完整的 .NET Core 解决方案</span><span class="sxs-lookup"><span data-stu-id="26222-103">Build a complete .NET Core solution on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="26222-104">Visual Studio for Mac 提供用于开发 .NET Core 应用程序的功能全面的集成开发环境 (IDE)。</span><span class="sxs-lookup"><span data-stu-id="26222-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="26222-105">本文演示了构建包含可重用的库和单元测试的 .NET Core 解决方案。</span><span class="sxs-lookup"><span data-stu-id="26222-105">This article walks you through building a .NET Core solution that includes a reusable library and unit testing.</span></span>

<span data-ttu-id="26222-106">本教程介绍了如何创建接受来自用户的搜索词和文本字符串、使用类库中的方法计算字符串中出现的搜索词的次数，并将结果返回给用户的应用程序。</span><span class="sxs-lookup"><span data-stu-id="26222-106">This tutorial shows you how to create an application that accepts a search word and a string of text from the user, counts the number of times the search word appears in the string using a method in a class library, and returns the result to the user.</span></span> <span data-ttu-id="26222-107">该解决方案还包括类库的单元测试（作为单元测试概念的介绍）。</span><span class="sxs-lookup"><span data-stu-id="26222-107">The solution also includes unit testing for the class library as an introduction to unit testing concepts.</span></span> <span data-ttu-id="26222-108">如果希望使用完整的示例学习该教程，请下载[示例解决方案](https://github.com/dotnet/samples/blob/master/core/tutorials/using-on-mac-vs-full-solution/WordCounter)。</span><span class="sxs-lookup"><span data-stu-id="26222-108">If you prefer to proceed through the tutorial with a complete sample, download the [sample solution](https://github.com/dotnet/samples/blob/master/core/tutorials/using-on-mac-vs-full-solution/WordCounter).</span></span> <span data-ttu-id="26222-109">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="26222-109">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

> [!NOTE]
> <span data-ttu-id="26222-110">你的反馈非常有价值。</span><span class="sxs-lookup"><span data-stu-id="26222-110">Your feedback is highly valued.</span></span> <span data-ttu-id="26222-111">有两种方法可以向开发团队提供有关 Visual Studio for Mac 的反馈：</span><span class="sxs-lookup"><span data-stu-id="26222-111">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> - <span data-ttu-id="26222-112">在 Visual Studio for Mac 中，从菜单选择“帮助”   > “报告问题”  ，或从欢迎屏幕中选择“报告问题”  ，将打开一个窗口，以供填写 bug 报告。</span><span class="sxs-lookup"><span data-stu-id="26222-112">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which opens a window for filing a bug report.</span></span> <span data-ttu-id="26222-113">可在[开发人员社区](https://developercommunity.visualstudio.com/spaces/41/index.html)门户中跟踪自己的反馈。</span><span class="sxs-lookup"><span data-stu-id="26222-113">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/41/index.html) portal.</span></span>
> - <span data-ttu-id="26222-114">若要提出建议，从菜单中选择“帮助”   > “提供建议”  ，或从欢迎屏幕中选择“提供建议”  ，转到 [Visual Studio for Mac 开发人员社区网页](https://developercommunity.visualstudio.com/content/idea/post.html?space=41)。</span><span class="sxs-lookup"><span data-stu-id="26222-114">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which takes you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="26222-115">先决条件</span><span class="sxs-lookup"><span data-stu-id="26222-115">Prerequisites</span></span>

- [<span data-ttu-id="26222-116">.NET Core SDK 3.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="26222-116">.NET Core SDK 3.1 or later</span></span>](https://dotnet.microsoft.com/download)
- [<span data-ttu-id="26222-117">Visual Studio 2019 for Mac</span><span class="sxs-lookup"><span data-stu-id="26222-117">Visual Studio 2019 for Mac</span></span>](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)

<span data-ttu-id="26222-118">若要了解有关先决条件的详细信息，请参阅 [.NET Core 依赖项和要求](../install/dependencies.md?pivots=os-macos)。</span><span class="sxs-lookup"><span data-stu-id="26222-118">For more information on prerequisites, see the [.NET Core dependencies and requirements](../install/dependencies.md?pivots=os-macos).</span></span> <span data-ttu-id="26222-119">有关 Visual Studio 2019 for Mac 完整系统要求的信息，请参阅 [Visual Studio 2019 for Mac 产品系列系统要求](/visualstudio/productinfo/vs2019-system-requirements-mac)。</span><span class="sxs-lookup"><span data-stu-id="26222-119">For the full system requirements of Visual Studio 2019 for Mac, see [Visual Studio 2019 for Mac Product Family System Requirements](/visualstudio/productinfo/vs2019-system-requirements-mac).</span></span>

## <a name="building-a-library"></a><span data-ttu-id="26222-120">生成库</span><span class="sxs-lookup"><span data-stu-id="26222-120">Building a library</span></span>

1. <span data-ttu-id="26222-121">在“开始”窗口，选择“新建项目”  。</span><span class="sxs-lookup"><span data-stu-id="26222-121">On the start window, select **New Project**.</span></span> <span data-ttu-id="26222-122">在“.NET Core”  节点下的“新建项目”  对话框中，选择“.NET 标准库”  模板。</span><span class="sxs-lookup"><span data-stu-id="26222-122">In the **New Project** dialog under the **.NET Core** node, select the **.NET Standard Library** template.</span></span> <span data-ttu-id="26222-123">此命令将创建一个 .NET Standard 库，该库面向 .NET Core 及支持 [.NET Standard](../../standard/net-standard.md) 版本 2.1 的任何其他 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="26222-123">This command creates a .NET Standard library that targets .NET Core as well as any other .NET implementation that supports version 2.1 of the [.NET Standard](../../standard/net-standard.md).</span></span> <span data-ttu-id="26222-124">如果安装了多个版本的 .NET Core SDK，则可以为库选择不同版本的 .NET Standard。</span><span class="sxs-lookup"><span data-stu-id="26222-124">If you have multiple versions of the .NET Core SDK installed, you can choose different versions of .NET Standard for your library.</span></span> <span data-ttu-id="26222-125">选择“.NET Standard 2.1”，然后选择“下一步”  。</span><span class="sxs-lookup"><span data-stu-id="26222-125">Choose ".NET Standard 2.1" and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-126">![Visual Studio for Mac“新建项目”对话框](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project.png)</span><span class="sxs-lookup"><span data-stu-id="26222-126">![Visual Studio for Mac New project dialog](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project.png)</span></span>

1. <span data-ttu-id="26222-127">将项目命名为“TextUtils”（“Text Utilities”的短名称），将解决方案命名为“WordCounter”。</span><span class="sxs-lookup"><span data-stu-id="26222-127">Name the project "TextUtils" (a short name for "Text Utilities") and the solution "WordCounter".</span></span> <span data-ttu-id="26222-128">使“在解决方案目录中创建项目目录”  保持选中状态。</span><span class="sxs-lookup"><span data-stu-id="26222-128">Leave **Create a project directory within the solution directory** checked.</span></span> <span data-ttu-id="26222-129">选择“创建”  。</span><span class="sxs-lookup"><span data-stu-id="26222-129">Select **Create**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-130">![Visual Studio for Mac“新建项目”对话框选项](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-options.png)</span><span class="sxs-lookup"><span data-stu-id="26222-130">![Visual Studio for Mac New project dialog options](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-options.png)</span></span>

1. <span data-ttu-id="26222-131">在“解决方案”  边栏中，展开 `TextUtils` 节点以显示模板提供的类文件 *Class1.cs*。</span><span class="sxs-lookup"><span data-stu-id="26222-131">In the **Solution** pad, expand the `TextUtils` node to reveal the class file provided by the template, *Class1.cs*.</span></span> <span data-ttu-id="26222-132">按住 Ctrl 并单击该文件，从上下文菜单中选择“重命名”  ，然后将该文件重命名为 WordCount.cs  。</span><span class="sxs-lookup"><span data-stu-id="26222-132">Ctrl-click the file, select **Rename** from the context menu, and rename the file to *WordCount.cs*.</span></span> <span data-ttu-id="26222-133">打开文件并将内容替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="26222-133">Open the file and replace the contents with the following code:</span></span>

   [!code-csharp[Main](../../../samples/snippets/core/tutorials/using-on-mac-vs-full-solution/csharp/TextUtils/WordCount.cs)]

1. <span data-ttu-id="26222-134">通过使用以下三种不同的方法之一保存文件：使用键盘快捷方式 <kbd>&#8984;</kbd>+<kbd>s</kbd>，从菜单中选择“文件”   > “保存”  ，或按住 Ctrl 并单击文件的选项卡，并从上下文菜单中选择“保存”  。</span><span class="sxs-lookup"><span data-stu-id="26222-134">Save the file by using any of three different methods: use the keyboard shortcut <kbd>&#8984;</kbd>+<kbd>s</kbd>, select **File** > **Save** from the menu, or ctrl-click on the file's tab and select **Save** from the contextual menu.</span></span> <span data-ttu-id="26222-135">下图显示 IDE 窗口：</span><span class="sxs-lookup"><span data-stu-id="26222-135">The following image shows the IDE window:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-136">![带有类库文件和方法的 Visual Studio for Mac IDE 窗口](./media/using-on-mac-vs-full-solution/visual-studio-mac-editor.png)</span><span class="sxs-lookup"><span data-stu-id="26222-136">![Visual Studio for Mac IDE window with class library file and method](./media/using-on-mac-vs-full-solution/visual-studio-mac-editor.png)</span></span>

1. <span data-ttu-id="26222-137">在 IDE 窗口底部边距处选择“错误”  ，打开“错误”  面板。</span><span class="sxs-lookup"><span data-stu-id="26222-137">Select **Errors** in the margin at the bottom of the IDE window to open the **Errors** panel.</span></span> <span data-ttu-id="26222-138">选择“生成输出”  按钮。</span><span class="sxs-lookup"><span data-stu-id="26222-138">Select the **Build Output** button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-139">![显示“错误”按钮的 Visual Studio Mac IDE 底部边距处](./media/using-on-mac-vs-full-solution/visual-studio-mac-error-button.png)</span><span class="sxs-lookup"><span data-stu-id="26222-139">![Bottom margin of the Visual Studio Mac IDE showing the Errors button](./media/using-on-mac-vs-full-solution/visual-studio-mac-error-button.png)</span></span>

1. <span data-ttu-id="26222-140">从菜单中选择“生成”   > “生成所有”  。</span><span class="sxs-lookup"><span data-stu-id="26222-140">Select **Build** > **Build All** from the menu.</span></span>

   <span data-ttu-id="26222-141">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="26222-141">The solution builds.</span></span> <span data-ttu-id="26222-142">生成输出面板显示生成成功。</span><span class="sxs-lookup"><span data-stu-id="26222-142">The build output panel shows that the build is successful.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-143">![“错误”面板的 Visual Studio Mac 生成输出面板，其中显示生成成功消息](./media/using-on-mac-vs-full-solution/visual-studio-mac-build-panel.png)</span><span class="sxs-lookup"><span data-stu-id="26222-143">![Visual Studio Mac Build output pane of the Errors panel with Build successful message](./media/using-on-mac-vs-full-solution/visual-studio-mac-build-panel.png)</span></span>

## <a name="creating-a-test-project"></a><span data-ttu-id="26222-144">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="26222-144">Creating a test project</span></span>

<span data-ttu-id="26222-145">单元测试在开发和发布期间提供自动化的软件测试。</span><span class="sxs-lookup"><span data-stu-id="26222-145">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="26222-146">本教程中使用的测试框架是 [xUnit（版本 2.4.0 或更高版本）](https://xunit.github.io/)，使用下列步骤将 xUnit 测试项目添加到解决方案时将自动安装此框架：</span><span class="sxs-lookup"><span data-stu-id="26222-146">The testing framework that you use in this tutorial is [xUnit (version 2.4.0 or later)](https://xunit.github.io/), which is installed automatically when the xUnit test project is added to the solution in the following steps:</span></span>

1. <span data-ttu-id="26222-147">在“解决方案”  边栏中，按住 Ctrl 并单击 `WordCounter` 解决方案并选择“添加”   > “添加新项目”  。</span><span class="sxs-lookup"><span data-stu-id="26222-147">In the **Solution** sidebar, ctrl-click the `WordCounter` solution and select **Add** > **Add New Project**.</span></span>

1. <span data-ttu-id="26222-148">在“新建项目”  对话框中，从“.NET Core”  节点中选择“测试”  。</span><span class="sxs-lookup"><span data-stu-id="26222-148">In the **New Project** dialog, select **Tests** from the **.NET Core** node.</span></span> <span data-ttu-id="26222-149">在“下一步”  后，选择“xUnit 测试项目”  。</span><span class="sxs-lookup"><span data-stu-id="26222-149">Select the **xUnit Test Project** followed by **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-150">![创建 xUnit 测试项目的 Visual Studio Mac“新建项目”对话框](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-project.png)</span><span class="sxs-lookup"><span data-stu-id="26222-150">![Visual Studio Mac New Project dialog creating xUnit test project](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-project.png)</span></span>

1. <span data-ttu-id="26222-151">如果有多个版本的 .NET Core SDK，则需要选择此项目的版本。</span><span class="sxs-lookup"><span data-stu-id="26222-151">If you have multiple versions of the .NET Core SDK, you'll need to select the version for this project.</span></span> <span data-ttu-id="26222-152">选择“.NET Core 3.1”  。</span><span class="sxs-lookup"><span data-stu-id="26222-152">Select **.NET Core 3.1**.</span></span> <span data-ttu-id="26222-153">将新项目命名为"TestLibrary"，然后选择“创建”  。</span><span class="sxs-lookup"><span data-stu-id="26222-153">Name the new project "TestLibrary" and select **Create**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-154">![提供项目名称的 Visual Studio Mac“新建项目”对话框](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-name.png)</span><span class="sxs-lookup"><span data-stu-id="26222-154">![Visual Studio Mac New Project dialog providing project name](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-name.png)</span></span>

1. <span data-ttu-id="26222-155">若要使测试库使用 `WordCount` 类，请将引用添加到 `TextUtils` 项目中。</span><span class="sxs-lookup"><span data-stu-id="26222-155">In order for the test library to work with the `WordCount` class, add a reference to the `TextUtils` project.</span></span> <span data-ttu-id="26222-156">在“解决方案”  边栏中，按住 Ctrl 并单击“TestLibrary”  下的“依赖项”  。</span><span class="sxs-lookup"><span data-stu-id="26222-156">In the **Solution** sidebar, ctrl-click **Dependencies** under **TestLibrary**.</span></span> <span data-ttu-id="26222-157">从上下文菜单中选择“编辑引用”  。</span><span class="sxs-lookup"><span data-stu-id="26222-157">Select **Edit References** from the context menu.</span></span>

1. <span data-ttu-id="26222-158">在“编辑引用”  对话框中，选择“项目”  选项卡上的“TextUtils”  项目。选择“确定”  。</span><span class="sxs-lookup"><span data-stu-id="26222-158">In the **Edit References** dialog, select the **TextUtils** project on the **Projects** tab. Select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-159">![Visual Studio Mac“编辑引用”对话框](./media/using-on-mac-vs-full-solution/visual-studio-mac-edit-references.png)</span><span class="sxs-lookup"><span data-stu-id="26222-159">![Visual Studio Mac Edit References dialog](./media/using-on-mac-vs-full-solution/visual-studio-mac-edit-references.png)</span></span>

1. <span data-ttu-id="26222-160">在 **TestLibrary** 项目中，将 *UnitTest1.cs* 文件重命名为 *TextUtilsTests.cs*。</span><span class="sxs-lookup"><span data-stu-id="26222-160">In the **TestLibrary** project, rename the *UnitTest1.cs* file to *TextUtilsTests.cs*.</span></span>

1. <span data-ttu-id="26222-161">打开该文件，并将代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="26222-161">Open the file and replace the code with the following code:</span></span>

   ```csharp
   using Xunit;
   using TextUtils;
   using System.Diagnostics;

   namespace TestLibrary
   {
       public class TextUtils_GetWordCountShould
       {
           [Fact]
           public void IgnoreCasing()
           {
               var wordCount = WordCount.GetWordCount("Jack", "Jack jack");

               Assert.NotEqual(2, wordCount);
           }
       }
   }
   ```

   <span data-ttu-id="26222-162">下图显示了就地使用单元测试代码的 IDE。</span><span class="sxs-lookup"><span data-stu-id="26222-162">The following image shows the IDE with the unit test code in place.</span></span> <span data-ttu-id="26222-163">请注意 `Assert.NotEqual` 语句。</span><span class="sxs-lookup"><span data-stu-id="26222-163">Pay attention to the `Assert.NotEqual` statement.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-164">![IDE 主窗口中的 Visual Studio for Mac 初始单元测试](./media/using-on-mac-vs-full-solution/visual-studio-mac-assert-test.png)</span><span class="sxs-lookup"><span data-stu-id="26222-164">![Visual Studio for Mac Initial unit test in the IDE main window](./media/using-on-mac-vs-full-solution/visual-studio-mac-assert-test.png)</span></span>

   <span data-ttu-id="26222-165">请务必使新的测试失败一次，以确定其测试逻辑正确无误。</span><span class="sxs-lookup"><span data-stu-id="26222-165">It's important to make a new test fail once to confirm its testing logic is correct.</span></span> <span data-ttu-id="26222-166">该方法使用“Jack”和“jack”（大写和小写）传递名称“Jack”（大写）和字符串。</span><span class="sxs-lookup"><span data-stu-id="26222-166">The method passes in the name "Jack" (uppercase) and a string with "Jack" and "jack" (uppercase and lowercase).</span></span> <span data-ttu-id="26222-167">如果 `GetWordCount` 方法运行正常，则返回搜索词的两个实例的计数。</span><span class="sxs-lookup"><span data-stu-id="26222-167">If the `GetWordCount` method is working properly, it returns a count of two instances of the search word.</span></span> <span data-ttu-id="26222-168">为了有意进行失败测试，首先实现测试断言，即搜索词“Jack”的两个实例不是由 `GetWordCount` 方法返回的。</span><span class="sxs-lookup"><span data-stu-id="26222-168">In order to fail this test on purpose, you first implement the test asserting that two instances of the search word "Jack" aren't returned by the `GetWordCount` method.</span></span> <span data-ttu-id="26222-169">继续执行下一步骤，有意使测试失败。</span><span class="sxs-lookup"><span data-stu-id="26222-169">Continue to the next step to fail the test on purpose.</span></span>

1. <span data-ttu-id="26222-170">打开屏幕右侧的“单元测试”  面板。</span><span class="sxs-lookup"><span data-stu-id="26222-170">Open the **Unit Tests** panel on the right side of the screen.</span></span> <span data-ttu-id="26222-171">从菜单中选择“查看”   > “测试”  。</span><span class="sxs-lookup"><span data-stu-id="26222-171">Select **View** > **Tests** from the menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-172">![Visual Studio for Mac“单元测试”面板](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-panel.png)</span><span class="sxs-lookup"><span data-stu-id="26222-172">![Visual Studio for Mac Unit Tests panel](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-panel.png)</span></span>

1. <span data-ttu-id="26222-173">单击“停靠”  图标使此面板保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="26222-173">Click the **Dock** icon to keep the panel open.</span></span> <span data-ttu-id="26222-174">（在下图中突出显示。）</span><span class="sxs-lookup"><span data-stu-id="26222-174">(Highlighted in the following image.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-175">![Visual Studio for Mac“单元测试”面板停靠图标](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-dock-icon.png)</span><span class="sxs-lookup"><span data-stu-id="26222-175">![Visual Studio for Mac Unit Tests panel dock icon](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-dock-icon.png)</span></span>

1. <span data-ttu-id="26222-176">单击“全部运行”  按钮。</span><span class="sxs-lookup"><span data-stu-id="26222-176">Click the **Run All** button.</span></span>

   <span data-ttu-id="26222-177">测试失败，这是正确的结果。</span><span class="sxs-lookup"><span data-stu-id="26222-177">The test fails, which is the correct result.</span></span> <span data-ttu-id="26222-178">测试方法断言不会从提供给 `GetWordCount` 的方法的字符串“Jack jack”中返回 `inputString`“Jack”的两个实例。</span><span class="sxs-lookup"><span data-stu-id="26222-178">The test method asserts that two instances of the `inputString`, "Jack," aren't returned from the string "Jack jack" provided to the `GetWordCount` method.</span></span> <span data-ttu-id="26222-179">因为已在 `GetWordCount` 方法中对单词的大小写进行了分解，所以返回了两个实例。</span><span class="sxs-lookup"><span data-stu-id="26222-179">Since word casing was factored out in the `GetWordCount` method, two instances are returned.</span></span> <span data-ttu-id="26222-180">2 *不等于* 2 的断言失败。</span><span class="sxs-lookup"><span data-stu-id="26222-180">The assertion that 2 *is not equal to* 2 fails.</span></span> <span data-ttu-id="26222-181">这是正确的结果，且测试的逻辑良好。</span><span class="sxs-lookup"><span data-stu-id="26222-181">This result is the correct outcome, and the logic of our test is good.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-182">![Visual Studio for Mac 测试失败显示](./media/using-on-mac-vs-full-solution/visual-studio-for-mac-unit-test-failure.png)</span><span class="sxs-lookup"><span data-stu-id="26222-182">![Visual Studio for Mac test failure display](./media/using-on-mac-vs-full-solution/visual-studio-for-mac-unit-test-failure.png)</span></span>

1. <span data-ttu-id="26222-183">通过将 `Assert.NotEqual` 更改为 `Assert.Equal` 来修改 `IgnoreCasing` 测试方法。</span><span class="sxs-lookup"><span data-stu-id="26222-183">Modify the `IgnoreCasing` test method by changing `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="26222-184">使用键盘快捷方式 <kbd>Ctrl</kbd>+<kbd>s</kbd> 保存该文件，从菜单选择“文件”   > “保存”  ，或按住 Ctrl 并单击文件的选项卡，并从上下文菜单中选择“保存”  。</span><span class="sxs-lookup"><span data-stu-id="26222-184">Save the file by using the keyboard shortcut <kbd>Ctrl</kbd>+<kbd>s</kbd>, **File** > **Save** from the menu, or ctrl-clicking on the file's tab and selecting **Save** from the context menu.</span></span>

   <span data-ttu-id="26222-185">`searchWord`Jack”应返回两个实例，并且 `inputString`“Jack jack”传递到 `GetWordCount`。</span><span class="sxs-lookup"><span data-stu-id="26222-185">You expect that the `searchWord` "Jack" returns two instances with `inputString` "Jack jack" passed into `GetWordCount`.</span></span> <span data-ttu-id="26222-186">通过单击“单元测试”  面板中的“运行测试”  按钮或屏幕底部的“测试结果”  面板中的“重新运行测试”  按钮重新运行测试。</span><span class="sxs-lookup"><span data-stu-id="26222-186">Run the test again by clicking the **Run Tests** button in the **Unit Tests** panel or the **Rerun Tests** button in the **Test Results** panel at the bottom of the screen.</span></span> <span data-ttu-id="26222-187">测试通过。</span><span class="sxs-lookup"><span data-stu-id="26222-187">The test passes.</span></span> <span data-ttu-id="26222-188">在字符串"Jack jack"（忽略大小写）中有“Jack”的两个实例，且测试断言为 `true`。</span><span class="sxs-lookup"><span data-stu-id="26222-188">There are two instances of "Jack" in the string "Jack jack" (ignoring casing), and the test assertion is `true`.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-189">![Visual Studio for Mac 测试通过显示](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)</span><span class="sxs-lookup"><span data-stu-id="26222-189">![Visual Studio for Mac tests pass display](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)</span></span>

1. <span data-ttu-id="26222-190">使用 `Fact` 测试单个返回值仅仅是借助单元测试可以实现的功能的开始。</span><span class="sxs-lookup"><span data-stu-id="26222-190">Testing individual return values with a `Fact` is only the beginning of what you can do with unit testing.</span></span> <span data-ttu-id="26222-191">另一个功能强大的技术是允许你使用 `Theory` 立即测试多个值。</span><span class="sxs-lookup"><span data-stu-id="26222-191">Another powerful technique allows you to test several values at once using a `Theory`.</span></span> <span data-ttu-id="26222-192">将以下方法添加到你的 `TextUtils_GetWordCountShould` 类。</span><span class="sxs-lookup"><span data-stu-id="26222-192">Add the following method to your `TextUtils_GetWordCountShould` class.</span></span> <span data-ttu-id="26222-193">添加该方法后，在类中有两个方法：</span><span class="sxs-lookup"><span data-stu-id="26222-193">You have two methods in the class after you add this method:</span></span>

   ```csharp
   [Theory]
   [InlineData(0, "Ting", "Does not appear in the string.")]
   [InlineData(1, "Ting", "Ting appears once.")]
   [InlineData(2, "Ting", "Ting appears twice with Ting.")]
   public void CountInstancesCorrectly(int count,
                                       string searchWord,
                                       string inputString)
   {
       Assert.NotEqual(count, WordCount.GetWordCount(searchWord,
                                                  inputString));
   }
   ```

   <span data-ttu-id="26222-194">`CountInstancesCorrectly` 检查 `GetWordCount` 方法计数是否正确。</span><span class="sxs-lookup"><span data-stu-id="26222-194">The `CountInstancesCorrectly` checks that the `GetWordCount` method counts correctly.</span></span> <span data-ttu-id="26222-195">`InlineData` 提供计数、搜索词和要检查的输入字符串。</span><span class="sxs-lookup"><span data-stu-id="26222-195">The `InlineData` provides a count, a search word, and an input string to check.</span></span> <span data-ttu-id="26222-196">测试方法为数据的每行运行一次。</span><span class="sxs-lookup"><span data-stu-id="26222-196">The test method runs once for each line of data.</span></span> <span data-ttu-id="26222-197">请再次注意，使用 `Assert.NotEqual` 首先声明失败，即使知道数据中的计数是正确的，且这些值与 `GetWordCount` 方法所返回的计数相匹配。</span><span class="sxs-lookup"><span data-stu-id="26222-197">Note once again that you're asserting a failure first by using `Assert.NotEqual`, even when you know that the counts in the data are correct and that the values match the counts returned by the `GetWordCount` method.</span></span> <span data-ttu-id="26222-198">有意执行测试失败的步骤起初看起来像是浪费时间，但是首先通过失败测试检查测试的逻辑对于测试逻辑而言，是一项重要检查。</span><span class="sxs-lookup"><span data-stu-id="26222-198">Performing the step of failing the test on purpose might seem like a waste of time at first, but checking the logic of the test by failing it first is an important check on the logic of your tests.</span></span> <span data-ttu-id="26222-199">如果在预期失败时找到一种可通过的测试方法，则你已在测试逻辑中找到 bug。</span><span class="sxs-lookup"><span data-stu-id="26222-199">When you come across a test method that passes when you expect it to fail, you've found a bug in the logic of the test.</span></span> <span data-ttu-id="26222-200">每次创建测试方法时，都值得采取此步骤。</span><span class="sxs-lookup"><span data-stu-id="26222-200">It's worth the effort to take this step every time you create a test method.</span></span>

1. <span data-ttu-id="26222-201">保存文件并重新运行测试。</span><span class="sxs-lookup"><span data-stu-id="26222-201">Save the file and run the tests again.</span></span> <span data-ttu-id="26222-202">大小写测试通过，但三个计数测试失败。</span><span class="sxs-lookup"><span data-stu-id="26222-202">The casing test passes but the three count tests fail.</span></span> <span data-ttu-id="26222-203">这与我们预期的结果完全一致。</span><span class="sxs-lookup"><span data-stu-id="26222-203">This outcome is exactly what you expect to happen.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-204">![Visual Studio for Mac 预期测试失败](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-failure.png)</span><span class="sxs-lookup"><span data-stu-id="26222-204">![Visual Studio for Mac expected test failure](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-failure.png)</span></span>

1. <span data-ttu-id="26222-205">通过将 `Assert.NotEqual` 更改为 `Assert.Equal` 来修改 `CountInstancesCorrectly` 测试方法。</span><span class="sxs-lookup"><span data-stu-id="26222-205">Modify the `CountInstancesCorrectly` test method by changing `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="26222-206">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="26222-206">Save the file.</span></span> <span data-ttu-id="26222-207">重新运行测试。</span><span class="sxs-lookup"><span data-stu-id="26222-207">Run the tests again.</span></span> <span data-ttu-id="26222-208">所有测试通过。</span><span class="sxs-lookup"><span data-stu-id="26222-208">All tests pass.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-209">![Visual Studio for Mac 预期测试通过](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)</span><span class="sxs-lookup"><span data-stu-id="26222-209">![Visual Studio for Mac expected test passes](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)</span></span>

## <a name="adding-a-console-app"></a><span data-ttu-id="26222-210">添加控制台应用</span><span class="sxs-lookup"><span data-stu-id="26222-210">Adding a console app</span></span>

1. <span data-ttu-id="26222-211">在“解决方案”  边栏中，按住 Ctrl 并单击 `WordCounter` 解决方案。</span><span class="sxs-lookup"><span data-stu-id="26222-211">In the **Solution** sidebar, ctrl-click the `WordCounter` solution.</span></span> <span data-ttu-id="26222-212">通过从“.NET Core”   > “应用”  模板中选择模板来添加新的**控制台应用程序**项目。</span><span class="sxs-lookup"><span data-stu-id="26222-212">Add a new **Console Application** project by selecting the template from the **.NET Core** > **App** templates.</span></span> <span data-ttu-id="26222-213">选择“下一步”  。</span><span class="sxs-lookup"><span data-stu-id="26222-213">Select **Next**.</span></span> <span data-ttu-id="26222-214">将项目命名为 **WordCounterApp**。</span><span class="sxs-lookup"><span data-stu-id="26222-214">Name the project **WordCounterApp**.</span></span> <span data-ttu-id="26222-215">选择“创建”  以在解决方案中创建项目。</span><span class="sxs-lookup"><span data-stu-id="26222-215">Select **Create** to create the project in the solution.</span></span>

1. <span data-ttu-id="26222-216">在“解决方案”  边栏中，按住 Ctrl 并单击新“WordCounterApp”  项目的“依赖项”  。</span><span class="sxs-lookup"><span data-stu-id="26222-216">In the **Solutions** sidebar, ctrl-click the **Dependencies** node of the new **WordCounterApp** project.</span></span> <span data-ttu-id="26222-217">在“编辑引用”  对话框中，选中“TextUtils”  ，然后选择“确定”  。</span><span class="sxs-lookup"><span data-stu-id="26222-217">In the **Edit References** dialog, check **TextUtils** and select **OK**.</span></span>

1. <span data-ttu-id="26222-218">打开 *Program.cs* 文件。</span><span class="sxs-lookup"><span data-stu-id="26222-218">Open the *Program.cs* file.</span></span> <span data-ttu-id="26222-219">将代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="26222-219">Replace the code with the following code:</span></span>

   [!code-csharp[Main](../../../samples/snippets/core/tutorials/using-on-mac-vs-full-solution/csharp/WordCounterApp/Program.cs)]

1. <span data-ttu-id="26222-220">按住 Ctrl 并单击 `WordCounterApp` 项目，并从上下文菜单中选择“运行项目”  。</span><span class="sxs-lookup"><span data-stu-id="26222-220">Ctrl-click on the `WordCounterApp` project and select **Run project** from the context menu.</span></span> <span data-ttu-id="26222-221">运行应用时，在控制台窗口中的提示符处提供搜索词和输入字符串的值。</span><span class="sxs-lookup"><span data-stu-id="26222-221">When you run the app, provide values for the search word and input string at the prompts in the console window.</span></span> <span data-ttu-id="26222-222">应用指示搜索词在字符串中出现的次数。</span><span class="sxs-lookup"><span data-stu-id="26222-222">The app indicates the number of times the search word appears in the string.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-223">![Visual Studio for Mac 控制台窗口，显示正在运行的应用](./media/using-on-mac-vs-full-solution/visual-studio-mac-console-window.png)</span><span class="sxs-lookup"><span data-stu-id="26222-223">![Visual Studio for Mac console window showing your app running](./media/using-on-mac-vs-full-solution/visual-studio-mac-console-window.png)</span></span>

1. <span data-ttu-id="26222-224">要探索的最后一个功能是使用 Visual Studio for Mac 进行调试。</span><span class="sxs-lookup"><span data-stu-id="26222-224">The last feature to explore is debugging with Visual Studio for Mac.</span></span> <span data-ttu-id="26222-225">在 `Console.WriteLine` 语句上设置断点：在第 23 行的左边距处选择，可以看到代码行旁边出现红色的圆圈。</span><span class="sxs-lookup"><span data-stu-id="26222-225">Set a breakpoint on the `Console.WriteLine` statement: Select in the left margin of line 23, and you see a red circle appear next to the line of code.</span></span> <span data-ttu-id="26222-226">或者，在代码行上的任意位置进行选择，然后从菜单中选择“运行”   > “切换断点”  。</span><span class="sxs-lookup"><span data-stu-id="26222-226">Alternatively, select anywhere on the line of code and select **Run** > **Toggle Breakpoint** from the menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-227">![Visual Studio for Mac 断点设置](./media/using-on-mac-vs-full-solution/visual-studio-mac-breakpoint.png)</span><span class="sxs-lookup"><span data-stu-id="26222-227">![Visual Studio for Mac breakpoint set](./media/using-on-mac-vs-full-solution/visual-studio-mac-breakpoint.png)</span></span>

1. <span data-ttu-id="26222-228">按住 Ctrl 并单击 `WordCounterApp` 项目。</span><span class="sxs-lookup"><span data-stu-id="26222-228">ctrl-click the `WordCounterApp` project.</span></span> <span data-ttu-id="26222-229">从上下文菜单中选择“开始调试项目”  。</span><span class="sxs-lookup"><span data-stu-id="26222-229">Select **Start Debugging Project** from the context menu.</span></span> <span data-ttu-id="26222-230">应用运行时，输入搜索词“cat”和“The dog chased the cat, but the cat escaped.”</span><span class="sxs-lookup"><span data-stu-id="26222-230">When the app runs, enter the search word "cat" and "The dog chased the cat, but the cat escaped."</span></span> <span data-ttu-id="26222-231">以供字符串进行搜索。</span><span class="sxs-lookup"><span data-stu-id="26222-231">for the string to search.</span></span> <span data-ttu-id="26222-232">到达 `Console.WriteLine` 语句时，将在执行该语句前暂停执行程序。</span><span class="sxs-lookup"><span data-stu-id="26222-232">When the `Console.WriteLine` statement is reached, program execution halts before the statement is executed.</span></span> <span data-ttu-id="26222-233">在“本地”  选项卡中，可以看到 `searchWord`、`inputString`、`wordCount` 和 `pluralChar` 值。</span><span class="sxs-lookup"><span data-stu-id="26222-233">In the **Locals** tab, you can see the `searchWord`, `inputString`, `wordCount`, and `pluralChar` values.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-234">![Visual Studio for Mac 调试器程序执行停止](./media/using-on-mac-vs-full-solution/visual-studio-mac-debugger.png)</span><span class="sxs-lookup"><span data-stu-id="26222-234">![Visual Studio for Mac debugger program execution stopped](./media/using-on-mac-vs-full-solution/visual-studio-mac-debugger.png)</span></span>

1. <span data-ttu-id="26222-235">在“即时”  面板中，键入“wordCount = 999;”，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="26222-235">In the **Immediate** pane, type "wordCount = 999;" and press Enter.</span></span> <span data-ttu-id="26222-236">此命令将无意义的值 999 分配到 `wordCount` 变量，显示可以在调试时替换变量值。</span><span class="sxs-lookup"><span data-stu-id="26222-236">This command assigns a nonsense value of 999 to the `wordCount` variable showing that you can replace variable values while debugging.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-237">![Visual Studio for Mac 在即时窗口中更改值](./media/using-on-mac-vs-full-solution/visual-studio-mac-immediate-window.png)</span><span class="sxs-lookup"><span data-stu-id="26222-237">![Visual Studio for Mac changing values in the immediate window](./media/using-on-mac-vs-full-solution/visual-studio-mac-immediate-window.png)</span></span>

1. <span data-ttu-id="26222-238">在工具栏中，单击“继续”  。</span><span class="sxs-lookup"><span data-stu-id="26222-238">In the toolbar, click the *continue* arrow.</span></span> <span data-ttu-id="26222-239">查看控制台窗口中的输出。</span><span class="sxs-lookup"><span data-stu-id="26222-239">Look at the output in the console window.</span></span> <span data-ttu-id="26222-240">它报告调试应用时所设置的不正确的值 999。</span><span class="sxs-lookup"><span data-stu-id="26222-240">It reports the incorrect value of 999 that you set when you were debugging the app.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-241">![Visual Studio for Mac 工具栏中的“继续”按钮](./media/using-on-mac-vs-full-solution/visual-studio-mac-toolbar.png)</span><span class="sxs-lookup"><span data-stu-id="26222-241">![Visual Studio for Mac continue button in the toolbar](./media/using-on-mac-vs-full-solution/visual-studio-mac-toolbar.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26222-242">![Visual Studio for Mac 控制台窗口输出](./media/using-on-mac-vs-full-solution/visual-studio-mac-output.png)</span><span class="sxs-lookup"><span data-stu-id="26222-242">![Visual Studio for Mac console window output](./media/using-on-mac-vs-full-solution/visual-studio-mac-output.png)</span></span>

<span data-ttu-id="26222-243">可以使用相同的过程通过单元测试项目来调试代码。</span><span class="sxs-lookup"><span data-stu-id="26222-243">You can use the same process to debug code using your unit test project.</span></span> <span data-ttu-id="26222-244">按住 Ctrl 并单击“测试库”  项目，然后从上下文菜单中选择“启动调试项目”  ，而不是启动 WordCount 应用项目。</span><span class="sxs-lookup"><span data-stu-id="26222-244">Instead of starting the WordCount app project, ctrl-click the **Test Library** project, and select **Start Debugging Project** from the context menu.</span></span> <span data-ttu-id="26222-245">Visual Studio for Mac 在附加了调试器的情况启动测试项目。</span><span class="sxs-lookup"><span data-stu-id="26222-245">Visual Studio for Mac starts your test project with the debugger attached.</span></span> <span data-ttu-id="26222-246">执行将在添加到测试项目的任何断点或基础库代码处停止。</span><span class="sxs-lookup"><span data-stu-id="26222-246">Execution will stop at any breakpoint you've added to the test project, or the underlying library code.</span></span>

## <a name="see-also"></a><span data-ttu-id="26222-247">请参阅</span><span class="sxs-lookup"><span data-stu-id="26222-247">See also</span></span>

- [<span data-ttu-id="26222-248">Visual Studio 2019 for Mac 发行说明</span><span class="sxs-lookup"><span data-stu-id="26222-248">Visual Studio 2019 for Mac Release Notes</span></span>](/visualstudio/releasenotes/vs2019-mac-relnotes)
