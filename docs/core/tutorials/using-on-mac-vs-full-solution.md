---
title: "使用 Visual Studio for Mac 在 macOS 上构建完整的 .NET Core 解决方案"
description: "本主题演示了构建包含可重用的库和单元测试的 .NET Core 解决方案。"
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 6945bedf-5bf3-4955-8588-83fb87511b79
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 60179fb0435803c3235b75ba012e588c6f1b35d3
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="building-a-complete-net-core-solution-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="bdb0f-104">使用 Visual Studio for Mac 在 macOS 上构建完整的 .NET Core 解决方案</span><span class="sxs-lookup"><span data-stu-id="bdb0f-104">Building a complete .NET Core solution on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="bdb0f-105">Visual Studio for Mac 提供用于开发 .NET Core 应用程序的功能全面的集成开发环境 (IDE)。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-105">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="bdb0f-106">本主题演示了构建包含可重用的库和单元测试的 .NET Core 解决方案。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-106">This topic walks you through building a .NET Core solution that includes a reusable library and unit testing.</span></span>

<span data-ttu-id="bdb0f-107">本教程介绍了如何创建接受来自用户的搜索词和文本字符串、使用类库中的方法计算字符串中出现的搜索词的次数，并将结果返回给用户的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-107">This tutorial shows you how to create an application that accepts a search word and a string of text from the user, counts the number of times the search word appears in the string using a method in a class library, and returns the result to the user.</span></span> <span data-ttu-id="bdb0f-108">该解决方案还包括针对类库的单元测试作为测试驱动开发 (TDD) 概念的介绍。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-108">The solution also includes unit testing for the class library as an introduction to test-driven development (TDD) concepts.</span></span> <span data-ttu-id="bdb0f-109">如果希望使用完整的示例学习该教程，请下载[示例解决方案](https://github.com/dotnet/docs/blob/master/samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter)。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-109">If you prefer to proceed through the tutorial with a complete sample, download the [sample solution](https://github.com/dotnet/docs/blob/master/samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter).</span></span> <span data-ttu-id="bdb0f-110">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-110">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

> [!NOTE]
> <span data-ttu-id="bdb0f-111">你的反馈非常有价值。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-111">Your feedback is highly valued.</span></span> <span data-ttu-id="bdb0f-112">有两种方法可以向开发团队提供有关 Visual Studio for Mac 的反馈：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-112">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
> * <span data-ttu-id="bdb0f-113">在 Visual Studio for Mac 中，从菜单选择“帮助” > “报告问题”，或从欢迎屏幕中选择“报告问题”，将打开一个窗口，以供填写 bug 报告。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-113">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which opens a window for filing a bug report.</span></span> <span data-ttu-id="bdb0f-114">可在[开发人员社区](https://developercommunity.visualstudio.com/spaces/41/index.html)门户中跟踪自己的反馈。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-114">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/41/index.html) portal.</span></span>
> * <span data-ttu-id="bdb0f-115">若要提出建议，从菜单中选择“帮助” > “提供建议”，或从欢迎屏幕中选择“提供建议”，转到 [Visual Studio for Mac UserVoice 网页](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac)。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-115">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which takes you to the [Visual Studio for Mac UserVoice webpage](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bdb0f-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="bdb0f-116">Prerequisites</span></span>

- <span data-ttu-id="bdb0f-117">OpenSSL（如果运行 .NET Core 1.1）：请参阅 [Mac 上 .NET Core 的先决条件](../macos-prerequisites.md)主题。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-117">OpenSSL (if running .NET Core 1.1): See the [Prerequisites for .NET Core on Mac](../macos-prerequisites.md) topic.</span></span>
- [<span data-ttu-id="bdb0f-118">.NET Core SDK 1.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="bdb0f-118">.NET Core SDK 1.1 or later</span></span>](https://www.microsoft.com/net/core#macos)
- [<span data-ttu-id="bdb0f-119">Visual Studio 2017 for Mac</span><span class="sxs-lookup"><span data-stu-id="bdb0f-119">Visual Studio 2017 for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

<span data-ttu-id="bdb0f-120">有关先决条件的详细信息，请参阅 [Mac 上的 .NET Core 的先决条件](../../core/macos-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-120">For more information on prerequisites, see the [Prerequisites for .NET Core on Mac](../../core/macos-prerequisites.md).</span></span> <span data-ttu-id="bdb0f-121">有关 Visual Studio 2017 for Mac 完整系统要求的信息，请参阅 [Visual Studio 2017 for Mac 产品系列系统要求](https://www.visualstudio.com/productinfo/vs2017-system-requirements-mac)。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-121">For the full system requirements of Visual Studio 2017 for Mac, see [Visual Studio 2017 for Mac Product Family System Requirements](https://www.visualstudio.com/productinfo/vs2017-system-requirements-mac).</span></span>

## <a name="building-a-library"></a><span data-ttu-id="bdb0f-122">生成库</span><span class="sxs-lookup"><span data-stu-id="bdb0f-122">Building a library</span></span>

1. <span data-ttu-id="bdb0f-123">在欢迎屏幕上，选择“新建项目”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-123">On the Welcome screen, select **New Project**.</span></span> <span data-ttu-id="bdb0f-124">在“多平台”节点下的“新建项目”对话框中，选择“.NET 标准库”模板。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-124">In the **New Project** dialog under the **Multiplatform** node, select the **.NET Standard Library** template.</span></span> <span data-ttu-id="bdb0f-125">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-125">Select **Next**.</span></span>

   ![“新建项目”对话框](./media/using-on-mac-vs-full-solution/vsmacfull01.png)

1. <span data-ttu-id="bdb0f-127">将项目命名为“TextUtils”（“Text Utilities”的短名称），将解决方案命名为“WordCounter”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-127">Name the project "TextUtils" (a short name for "Text Utilities") and the solution "WordCounter".</span></span> <span data-ttu-id="bdb0f-128">使“在解决方案目录中创建项目目录”保持选中状态。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-128">Leave **Create a project directory within the solution directory** checked.</span></span> <span data-ttu-id="bdb0f-129">选择“创建”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-129">Select **Create**.</span></span>

   ![“新建项目”对话框](./media/using-on-mac-vs-full-solution/vsmacfull02.png)

1. <span data-ttu-id="bdb0f-131">在“解决方案”边栏中，展开 `TextUtils` 节点以显示模板提供的类文件 *Class1.cs*。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-131">In the **Solution** sidebar, expand the `TextUtils` node to reveal the class file provided by the template, *Class1.cs*.</span></span> <span data-ttu-id="bdb0f-132">右键单击该文件，从上下文菜单中选择“重命名”，然后将该文件重命名为 *WordCount.cs*。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-132">Right-click the file, select **Rename** from the context menu, and rename the file to *WordCount.cs*.</span></span> <span data-ttu-id="bdb0f-133">打开文件并将内容替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-133">Open the file and replace the contents with the following code:</span></span>

   <span data-ttu-id="bdb0f-134">[!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/TextUtils/WordCount.cs)]</span><span class="sxs-lookup"><span data-stu-id="bdb0f-134">[!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/TextUtils/WordCount.cs)]</span></span>

1. <span data-ttu-id="bdb0f-135">通过使用以下三种不同的方法之一保存文件：使用键盘快捷方式 <kbd>&#8984;</kbd>+<kbd>s</kbd>，从菜单中选择“文件” > “保存”，或右键单击文件的选项卡，并从上下文菜单中选择“保存”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-135">Save the file by using any of three different methods: use the keyboard shortcut <kbd>&#8984;</kbd>+<kbd>s</kbd>, select **File** > **Save** from the menu, or right-click on the file's tab and select **Save** from the contextual menu.</span></span> <span data-ttu-id="bdb0f-136">下图显示 IDE 窗口：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-136">The following image shows the IDE window:</span></span>

   ![IDE 窗口显示 TextUtils 类库、WordCount 类文件、静态类 WordCount 和 GetWordCount 方法](./media/using-on-mac-vs-full-solution/vsmacfull03.png)

1. <span data-ttu-id="bdb0f-138">在 IDE 窗口底部边距处选择“错误”，打开“错误”面板。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-138">Select **Errors** in the margin at the bottom of the IDE window to open the **Errors** panel.</span></span> <span data-ttu-id="bdb0f-139">选择“生成输出”按钮。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-139">Select the **Build Output** button.</span></span>

   ![IDE 的底部边距处显示错误按钮](./media/using-on-mac-vs-full-solution/vsmacfull03b.png)

1. <span data-ttu-id="bdb0f-141">从菜单中选择“生成” > “生成所有”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-141">Select **Build** > **Build All** from the menu.</span></span>

   <span data-ttu-id="bdb0f-142">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-142">The solution builds.</span></span> <span data-ttu-id="bdb0f-143">生成输出面板显示生成成功。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-143">The build output panel shows that the build is successful.</span></span>

   ![错误面板的生成输出面板显示生成成功消息](./media/using-on-mac-vs-full-solution/vsmacfull04.png)

## <a name="creating-a-test-project"></a><span data-ttu-id="bdb0f-145">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="bdb0f-145">Creating a test project</span></span>

<span data-ttu-id="bdb0f-146">单元测试在开发和发布期间提供自动化的软件测试。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-146">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="bdb0f-147">本教程中使用的测试框架是 [xUnit（版本 2.2.0 或更高版本）](https://xunit.github.io/)，使用下列步骤将 xUnit 测试项目添加到解决方案时将自动安装此框架：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-147">The testing framework that you use in this tutorial is [xUnit (version 2.2.0 or later)](https://xunit.github.io/), which is installed automatically when the xUnit test project is added to the solution in the following steps:</span></span>

1. <span data-ttu-id="bdb0f-148">在“解决方案”边栏中，右键单击 `WordCounter` 解决方案并选择“添加” > “添加新项目”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-148">In the **Solution** sidebar, right-click the `WordCounter` solution and select **Add** > **Add New Project**.</span></span>

1. <span data-ttu-id="bdb0f-149">在“新建项目”对话框中，从“.NET Core”节点中选择“测试”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-149">In the **New Project** dialog, select **Tests** from the **.NET Core** node.</span></span> <span data-ttu-id="bdb0f-150">在“下一步”后，选择“xUnit 测试项目”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-150">Select the **xUnit Test Project** followed by **Next**.</span></span>

   ![创建 xUnit 测试项目的“新建项目”对话框](./media/using-on-mac-vs-full-solution/vsmacfull05.png)

1. <span data-ttu-id="bdb0f-152">将新项目命名为"TestLibrary"，然后选择“创建”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-152">Name the new project "TestLibrary" and select **Create**.</span></span>

   ![提供项目名称的“新建项目”对话框](./media/using-on-mac-vs-full-solution/vsmacfull06.png)

1. <span data-ttu-id="bdb0f-154">若要使测试库使用 `WordCount` 类，请将引用添加到 `TextUtils` 项目中。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-154">In order for the test library to work with the `WordCount` class, add a reference to the `TextUtils` project.</span></span> <span data-ttu-id="bdb0f-155">在“解决方案”边栏中，右键单击“TestLibrary”下的“依赖项”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-155">In the **Solution** sidebar, right-click **Dependencies** under **TestLibrary**.</span></span> <span data-ttu-id="bdb0f-156">从上下文菜单中选择“编辑引用”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-156">Select **Edit References** from the context menu.</span></span>

1. <span data-ttu-id="bdb0f-157">在“编辑引用”对话框中，选择“项目”选项卡上的“TextUtils”项目。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-157">In the **Edit References** dialog, select the **TextUtils** project on the **Projects** tab.</span></span> <span data-ttu-id="bdb0f-158">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-158">Select **OK**.</span></span>

   ![编辑引用对话框](./media/using-on-mac-vs-full-solution/vsmacfull07.png)

1. <span data-ttu-id="bdb0f-160">在 **TestLibrary** 项目中，将 *UnitTest1.cs* 文件重命名为 *TextUtilsTests.cs*。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-160">In the **TestLibrary** project, rename the *UnitTest1.cs* file to *TextUtilsTests.cs*.</span></span>

1. <span data-ttu-id="bdb0f-161">打开该文件，并将代码替换为以下内容：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-161">Open the file and replace the code with the following:</span></span>

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

   <span data-ttu-id="bdb0f-162">下图显示了就地使用单元测试代码的 IDE。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-162">The following image shows the IDE with the unit test code in place.</span></span> <span data-ttu-id="bdb0f-163">请注意 `Assert.NotEqual` 语句。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-163">Pay attention to the `Assert.NotEqual` statement.</span></span>

   ![在 IDE 主窗口中检查 GetWordCount 的初始单元测试](./media/using-on-mac-vs-full-solution/vsmacfull08.png)

   <span data-ttu-id="bdb0f-165">使用 TDD 时，请务必使新的测试失败一次，以确定其测试逻辑正确无误。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-165">Using TDD, it's important to make a new test fail once to confirm its testing logic is correct.</span></span> <span data-ttu-id="bdb0f-166">该方法使用“Jack”和“jack”（大写和小写）传递名称“Jack”（大写）和字符串。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-166">The method passes in the name "Jack" (uppercase) and a string with "Jack" and "jack" (uppercase and lowercase).</span></span> <span data-ttu-id="bdb0f-167">如果 `GetWordCount` 方法运行正常，则返回搜索词的两个实例的计数。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-167">If the `GetWordCount` method is working properly, it returns a count of two instances of the search word.</span></span> <span data-ttu-id="bdb0f-168">为了有意进行失败测试，首先实现测试断言，即搜索词“Jack”的两个实例不是由 `GetWordCount` 方法返回的。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-168">In order to fail this test on purpose, you first implement the test asserting that two instances of the search word "Jack" aren't returned by the `GetWordCount` method.</span></span> <span data-ttu-id="bdb0f-169">继续执行下一步骤，有意使测试失败。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-169">Continue to the next step to fail the test on purpose.</span></span>

1. <span data-ttu-id="bdb0f-170">打开屏幕右侧的“单元测试”面板。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-170">Open the **Unit Tests** panel on the right side of the screen.</span></span>

![“单元测试”面板](./media/using-on-mac-vs-full-solution/vsmacfull_UnitTestPanel.png)

1. <span data-ttu-id="bdb0f-172">单击“停靠”图标使此面板保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-172">Click the **Dock** icon to keep the panel open.</span></span>

![“单元测试”面板“停靠”图标](./media/using-on-mac-vs-full-solution/vsmacfull_UnitTestPanelDockIcon.png)

1. <span data-ttu-id="bdb0f-174">单击“全部运行”按钮。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-174">Click the **Run All** button.</span></span>
   
   <span data-ttu-id="bdb0f-175">测试失败，这是正确的结果。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-175">The test fails, which is the correct result.</span></span> <span data-ttu-id="bdb0f-176">测试方法断言不会从提供给 `GetWordCount` 的方法的字符串“Jack jack”中返回 `inputString`“Jack”的两个实例。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-176">The test method asserts that two instances of the `inputString`, "Jack," aren't returned from the string "Jack jack" provided to the `GetWordCount` method.</span></span> <span data-ttu-id="bdb0f-177">因为已在 `GetWordCount` 方法中对单词的大小写进行了分解，所以返回了两个实例。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-177">Since word casing was factored out in the `GetWordCount` method, two instances are returned.</span></span> <span data-ttu-id="bdb0f-178">2  *不等于*  2 的断言失败。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-178">The assertion that 2 *is not equal to* 2 fails.</span></span> <span data-ttu-id="bdb0f-179">这是正确的结果，且测试的逻辑良好。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-179">This is the correct outcome, and the logic of our test is good.</span></span>

   ![测试失败](./media/using-on-mac-vs-full-solution/vsmacfull09.png)

1. <span data-ttu-id="bdb0f-181">通过将 `Assert.NotEqual` 更改为 `Assert.Equal` 来修改 `IgnoreCasing` 测试方法。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-181">Modify the `IgnoreCasing` test method by changing `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="bdb0f-182">使用键盘快捷方式 <kbd>&#8984;</kbd>+<kbd>s</kbd> 保存该文件，从菜单选择“文件” > “保存”，或右键单击文件的选项卡，并从上下文菜单中选择“保存”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-182">Save the file by using the keyboard shortcut <kbd>&#8984;</kbd>+<kbd>s</kbd>, **File** > **Save** from the menu, or right-clicking on the file's tab and selecting **Save** from the context menu.</span></span>

   <span data-ttu-id="bdb0f-183">`searchWord`Jack”应返回两个实例，并且 `inputString`“Jack jack”传递到 `GetWordCount`。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-183">You expect that the `searchWord` "Jack" returns two instances with `inputString` "Jack jack" passed into `GetWordCount`.</span></span> <span data-ttu-id="bdb0f-184">通过单击“单元测试”面板中的“运行测试”按钮或屏幕底部的“测试结果”面板中的“重新运行测试”按钮重新运行测试。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-184">Run the test again by clicking the **Run Tests** button in the **Unit Tests** panel or the **Rerun Tests** button in the **Test Results** panel at the bottom of the screen.</span></span> <span data-ttu-id="bdb0f-185">测试通过。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-185">The test passes.</span></span> <span data-ttu-id="bdb0f-186">在字符串"Jack jack"（忽略大小写）中有“Jack”的两个实例，且测试断言为 `true`。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-186">There are two instances of "Jack" in the string "Jack jack" (ignoring casing), and the test assertion is `true`.</span></span>

   ![测试通过](./media/using-on-mac-vs-full-solution/vsmacfull10.png)

1. <span data-ttu-id="bdb0f-188">使用 `Fact` 测试单个返回值仅仅是借助单元测试可以实现的功能的开始。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-188">Testing individual return values with a `Fact` is only the beginning of what you can do with unit testing.</span></span> <span data-ttu-id="bdb0f-189">另一个功能强大的技术是允许你使用 `Theory` 立即测试多个值。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-189">Another powerful technique allows you to test several values at once using a `Theory`.</span></span> <span data-ttu-id="bdb0f-190">将以下方法添加到你的 `TextUtils_GetWordCountShould` 类。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-190">Add the following method to your `TextUtils_GetWordCountShould` class.</span></span> <span data-ttu-id="bdb0f-191">添加该方法后，在类中有两个方法：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-191">You have two methods in the class after you add this method:</span></span>

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

   <span data-ttu-id="bdb0f-192">`CountInstancesCorrectly` 检查 `GetWordCount` 方法计数是否正确。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-192">The `CountInstancesCorrectly` checks that the `GetWordCount` method counts correctly.</span></span> <span data-ttu-id="bdb0f-193">`InlineData` 提供计数、搜索词和要检查的输入字符串。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-193">The `InlineData` provides a count, a search word, and an input string to check.</span></span> <span data-ttu-id="bdb0f-194">测试方法为数据的每行运行一次。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-194">The test method runs once for each line of data.</span></span> <span data-ttu-id="bdb0f-195">请再次注意，使用 `Assert.NotEqual` 首先声明失败，即使知道数据中的计数是正确的，且这些值与 `GetWordCount` 方法所返回的计数相匹配。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-195">Note once again that you're asserting a failure first by using `Assert.NotEqual`, even when you know that the counts in the data are correct and that the values match the counts returned by the `GetWordCount` method.</span></span> <span data-ttu-id="bdb0f-196">有意执行测试失败的步骤起初看起来像是浪费时间，但是首先通过失败测试检查测试的逻辑对于测试逻辑而言，是一项重要检查。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-196">Performing the step of failing the test on purpose might seem like a waste of time at first, but checking the logic of the test by failing it first is an important check on the logic of your tests.</span></span> <span data-ttu-id="bdb0f-197">如果在预期失败时找到一种可通过的测试方法，则你已在测试逻辑中找到 bug。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-197">When you come across a test method that passes when you expect it to fail, you've found a bug in the logic of the test.</span></span> <span data-ttu-id="bdb0f-198">每次创建测试方法时，都值得采取此步骤。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-198">It's worth the effort to take this step every time you create a test method.</span></span>
   
1. <span data-ttu-id="bdb0f-199">保存文件并重新运行测试。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-199">Save the file and run the tests again.</span></span> <span data-ttu-id="bdb0f-200">大小写测试通过，但三个计数测试失败。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-200">The casing test passes but the three count tests fail.</span></span> <span data-ttu-id="bdb0f-201">这与我们预期的结果完全一致。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-201">This is exactly what you expect to happen.</span></span>

   ![测试失败](./media/using-on-mac-vs-full-solution/vsmacfull11.png)

1. <span data-ttu-id="bdb0f-203">通过将 `Assert.NotEqual` 更改为 `Assert.Equal` 来修改 `CountInstancesCorrectly` 测试方法。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-203">Modify the `CountInstancesCorrectly` test method by changing `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="bdb0f-204">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-204">Save the file.</span></span> <span data-ttu-id="bdb0f-205">重新运行测试。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-205">Run the tests again.</span></span> <span data-ttu-id="bdb0f-206">所有测试通过。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-206">All tests pass.</span></span>

   ![测试通过](./media/using-on-mac-vs-full-solution/vsmacfull12.png)

## <a name="adding-a-console-app"></a><span data-ttu-id="bdb0f-208">添加控制台应用</span><span class="sxs-lookup"><span data-stu-id="bdb0f-208">Adding a console app</span></span>

1. <span data-ttu-id="bdb0f-209">在“解决方案”边栏中，右键单击 `WordCounter` 解决方案。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-209">In the **Solution** sidebar, right-click the `WordCounter` solution.</span></span> <span data-ttu-id="bdb0f-210">通过从“.NET Core” > “应用” 模板中选择模板来添加新的**控制台应用程序**项目。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-210">Add a new **Console Application** project by selecting the template from the **.NET Core** > **App** templates.</span></span> <span data-ttu-id="bdb0f-211">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-211">Select **Next**.</span></span> <span data-ttu-id="bdb0f-212">将项目命名为 **WordCounterApp**。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-212">Name the project **WordCounterApp**.</span></span> <span data-ttu-id="bdb0f-213">选择“创建”以在解决方案中创建项目。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-213">Select **Create** to create the project in the solution.</span></span>

1. <span data-ttu-id="bdb0f-214">在“解决方案”边栏中，右键单击新 **WordCounterApp** 项目的“依赖项”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-214">In the **Solutions** sidebar, right-click the **Dependencies** node of the new **WordCounterApp** project.</span></span> <span data-ttu-id="bdb0f-215">在“编辑引用”对话框中，选中“TextUtils”，然后选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-215">In the **Edit References** dialog, check **TextUtils** and select **OK**.</span></span>

1. <span data-ttu-id="bdb0f-216">打开 *Program.cs* 文件。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-216">Open the *Program.cs* file.</span></span> <span data-ttu-id="bdb0f-217">将代码替换为以下内容：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-217">Replace the code with the following:</span></span>

   <span data-ttu-id="bdb0f-218">[!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/WordCounterApp/Program.cs)]</span><span class="sxs-lookup"><span data-stu-id="bdb0f-218">[!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/WordCounterApp/Program.cs)]</span></span>

1. <span data-ttu-id="bdb0f-219">如要在控制台窗口而不是在 IDE 中运行应用，右键单击 `WordCounterApp` 项目，选择“选项”，然后打开“配置”下的“默认”节点。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-219">To run the app in a console window instead of the IDE, right-click the `WordCounterApp` project, select **Options**, and open the **Default** node under **Configurations**.</span></span> <span data-ttu-id="bdb0f-220">选中“在外部控制台上运行”框。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-220">Check the box for **Run on external console**.</span></span> <span data-ttu-id="bdb0f-221">使“暂停控制台输出”选项保持选中状态。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-221">Leave the **Pause console output** option checked.</span></span> <span data-ttu-id="bdb0f-222">此设置使应用在控制台窗口中生成，以便可以为 `Console.ReadLine` 语句键入输入。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-222">This setting causes the app to spawn in a console window so that you can type input for the `Console.ReadLine` statements.</span></span> <span data-ttu-id="bdb0f-223">如果使应用在 IDE 中持续运行，则仅能看到 `Console.WriteLine` 语句的输出。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-223">If you leave the app to run in the IDE, you can only see the output of `Console.WriteLine` statements.</span></span> <span data-ttu-id="bdb0f-224">`Console.ReadLine` 语句无法在 IDE 的“应用程序输出”面板中运行。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-224">`Console.ReadLine` statements do not work in the IDE's **Application Output** panel.</span></span>

   ![项目选项窗口](./media/using-on-mac-vs-full-solution/vsmacfull13.png)

1. <span data-ttu-id="bdb0f-226">由于 Visual Studio for Mac 的当前版本无法在解决方案运行时运行测试，因此，可以直接运行控制台应用。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-226">Because the current version of Visual Studio for Mac cannot run the tests when the solution is run, you run the console app directly.</span></span> <span data-ttu-id="bdb0f-227">右键单击 `WordCounterApp` 项目，并从上下文菜单中选择“运行项目”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-227">Right-click on the `WordCounterApp` project and select **Run item** from the context menu.</span></span> <span data-ttu-id="bdb0f-228">如果尝试使用播放按钮运行应用，测试运行程序和应用将无法运行。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-228">If you attempt to run the app with the Play button, the test runner and app fail to run.</span></span> <span data-ttu-id="bdb0f-229">有关此问题的运行状态的详细信息，请参阅 [xunit/xamarinstudio.xunit (#60)](https://github.com/xunit/xamarinstudio.xunit/issues/60)。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-229">For more information on the status of the work on this issue, see [xunit/xamarinstudio.xunit (#60)](https://github.com/xunit/xamarinstudio.xunit/issues/60).</span></span> <span data-ttu-id="bdb0f-230">运行应用时，在控制台窗口中的提示符处提供搜索词和输入字符串的值。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-230">When you run the app, provide values for the search word and input string at the prompts in the console window.</span></span> <span data-ttu-id="bdb0f-231">应用指示搜索词在字符串中出现的次数。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-231">The app indicates the number of times the search word appears in the string.</span></span>

   ![控制台窗口显示字符串中搜索的词 olives，“Iro ate olives by the lake, and the olives were wonderful.”](./media/using-on-mac-vs-full-solution/vsmacfull14.png)

1. <span data-ttu-id="bdb0f-234">要探索的最后一个功能是使用 Visual Studio for Mac 进行调试。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-234">The last feature to explore is debugging with Visual Studio for Mac.</span></span> <span data-ttu-id="bdb0f-235">在 `Console.WriteLine` 语句上设置断点：在第 23 行的左边距处选择，可以看到代码行旁边出现红色的圆圈。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-235">Set a breakpoint on the `Console.WriteLine` statement: Select in the left margin of line 23, and you see a red circle appear next to the line of code.</span></span> <span data-ttu-id="bdb0f-236">或者，在代码行上的任意位置进行选择，然后从菜单中选择“运行” > “切换断点”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-236">Alternatively, select anywhere on the line of code and select **Run** > **Toggle Breakpoint** from the menu.</span></span>

   ![在第 23 行 Console.WriteLine 语句处设置断点](./media/using-on-mac-vs-full-solution/vsmacfull15.png)

1. <span data-ttu-id="bdb0f-238">右键单击 `WordCounterApp` 项目。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-238">Right-click the `WordCounterApp` project.</span></span> <span data-ttu-id="bdb0f-239">从上下文菜单中选择“开始调试项目”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-239">Select **Start Debugging item** from the context menu.</span></span> <span data-ttu-id="bdb0f-240">应用运行时，输入搜索词“cat”和“The dog chased the cat, but the cat escaped.”</span><span class="sxs-lookup"><span data-stu-id="bdb0f-240">When the app runs, enter the search word "cat" and "The dog chased the cat, but the cat escaped."</span></span> <span data-ttu-id="bdb0f-241">以供字符串进行搜索。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-241">for the string to search.</span></span> <span data-ttu-id="bdb0f-242">到达 `Console.WriteLine` 语句时，将在执行该语句前暂停执行程序。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-242">When the `Console.WriteLine` statement is reached, program execution halts before the statement is executed.</span></span> <span data-ttu-id="bdb0f-243">在“本地”选项卡中，可以看到 `searchWord`、`inputString`、`wordCount` 和 `pluralChar` 值。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-243">In the **Locals** tab, you can see the `searchWord`, `inputString`, `wordCount`, and `pluralChar` values.</span></span>

   ![在 Console.WriteLine 语句处停止执行程序，且本地窗口将在执行 Console.WriteLine 语句前立即显示值。](./media/using-on-mac-vs-full-solution/vsmacfull16.png)

1. <span data-ttu-id="bdb0f-245">在“即时”面板中，键入“wordCount = 999;”，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-245">In the **Immediate** pane, type "wordCount = 999;" and press Enter.</span></span> <span data-ttu-id="bdb0f-246">该操作将无意义的值 999 分配到 `wordCount` 变量，显示可以在调试时替换变量值。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-246">This assigns a nonsense value of 999 to the `wordCount` variable showing that you can replace variable values while debugging.</span></span>

   ![命中端点。](./media/using-on-mac-vs-full-solution/vsmacfull17.png)

1. <span data-ttu-id="bdb0f-249">在工具栏中，单击“继续”。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-249">In the toolbar, click the *continue* arrow.</span></span> <span data-ttu-id="bdb0f-250">查看控制台窗口中的输出。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-250">Look at the output in the console window.</span></span> <span data-ttu-id="bdb0f-251">它报告调试应用时所设置的不正确的值 999。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-251">It reports the incorrect value of 999 that you set when you were debugging the app.</span></span>

   ![工具栏中的继续按钮](./media/using-on-mac-vs-full-solution/vsmacfull18.png)

   ![搜索词计数在应用的输出中更改为值 999](./media/using-on-mac-vs-full-solution/vsmacfull19.png)

## <a name="see-also"></a><span data-ttu-id="bdb0f-254">请参阅</span><span class="sxs-lookup"><span data-stu-id="bdb0f-254">See also</span></span>

[<span data-ttu-id="bdb0f-255">Visual Studio 2017 for Mac 发行说明</span><span class="sxs-lookup"><span data-stu-id="bdb0f-255">Visual Studio 2017 for Mac Release Notes</span></span>](https://www.visualstudio.com/news/releasenotes/vs2017-mac-relnotes)

