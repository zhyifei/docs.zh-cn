---
title: 在 Visual Studio 中使用 .NET Core 测试 .NET Standard 类库
description: 为 .NET Core 类库创建单元测试项目。 验证 .NET Core 类库能否正确地进行单元测试。
ms.date: 12/24/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet, seodoc18
ms.openlocfilehash: 307261088f5c7c69c0e69fbd6b99940c04842eec
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156616"
---
# <a name="test-a-net-standard-library-with-net-core-in-visual-studio"></a><span data-ttu-id="fd928-104">在 Visual Studio 中使用 .NET Core 测试 .NET Standard 库</span><span class="sxs-lookup"><span data-stu-id="fd928-104">Test a .NET Standard library with .NET Core in Visual Studio</span></span>

<span data-ttu-id="fd928-105">在[在 Visual Studio 中生成 .NET Standard 库](library-with-visual-studio.md)中，创建了一个简单的类库，用于向 <xref:System.String> 类添加扩展方法。</span><span class="sxs-lookup"><span data-stu-id="fd928-105">In [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md), you created a simple class library that adds an extension method to the <xref:System.String> class.</span></span> <span data-ttu-id="fd928-106">现在，将创建一个单元测试，用于确保此类库能够按预期运行。</span><span class="sxs-lookup"><span data-stu-id="fd928-106">Now, you'll create a unit test to make sure that it works as expected.</span></span> <span data-ttu-id="fd928-107">向在上一篇文章中创建的解决方案添加单元测试项目。</span><span class="sxs-lookup"><span data-stu-id="fd928-107">You'll add your unit test project to the solution you created in the previous article.</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="fd928-108">创建单元测试项目</span><span class="sxs-lookup"><span data-stu-id="fd928-108">Create a unit test project</span></span>

<span data-ttu-id="fd928-109">若要创建单元测试项目，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fd928-109">To create the unit test project, do the following:</span></span>

1. <span data-ttu-id="fd928-110">打开在[在 Visual Studio 中生成 .NET Standard 库](library-with-visual-studio.md)一文中创建的 `ClassLibraryProjects` 解决方案。</span><span class="sxs-lookup"><span data-stu-id="fd928-110">Open the `ClassLibraryProjects` solution you created in the [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md) article.</span></span>

1. <span data-ttu-id="fd928-111">将名为“StringLibraryTest”的新单元测试项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="fd928-111">Add a new unit test project named "StringLibraryTest" to the solution.</span></span>

   1. <span data-ttu-id="fd928-112">在“解决方案资源管理器”  中右键单击解决方案并选择“添加”   > “新建项目”  。</span><span class="sxs-lookup"><span data-stu-id="fd928-112">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="fd928-113">在“添加新项目”  页面，在搜索框中输入“mstest”  。</span><span class="sxs-lookup"><span data-stu-id="fd928-113">On the **Add a new project** page, enter **mstest** in the search box.</span></span> <span data-ttu-id="fd928-114">从“语言”列表中选择“C#”  或“Visual Basic”  ，然后从“平台”列表中选择“所有平台”  。</span><span class="sxs-lookup"><span data-stu-id="fd928-114">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="fd928-115">选择“MsTest 测试项目(.NET Core)”  模板，然后选择“下一步”  。</span><span class="sxs-lookup"><span data-stu-id="fd928-115">Choose the **MsTest Test Project (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="fd928-116">在“配置新项目”  页面，在“项目名称”  框中输入“StringLibraryTest”  。</span><span class="sxs-lookup"><span data-stu-id="fd928-116">On the **Configure your new project** page, enter **StringLibraryTest** in the **Project name** box.</span></span> <span data-ttu-id="fd928-117">然后选择“创建”  。</span><span class="sxs-lookup"><span data-stu-id="fd928-117">Then choose **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fd928-118">除了 MSTest 之外，还可以在 Visual Studio 中为 .NET Core 创建 xUnit 和 nUnit 测试项目。</span><span class="sxs-lookup"><span data-stu-id="fd928-118">In addition to an MSTest, you can also create xUnit and nUnit test projects for .NET Core in Visual Studio.</span></span>

1. <span data-ttu-id="fd928-119">此时，Visual Studio 会创建项目，并在具有以下代码的代码窗口中打开类文件：</span><span class="sxs-lookup"><span data-stu-id="fd928-119">Visual Studio creates the project and opens the class file in the code window with the following code:</span></span>

   ```csharp
   using Microsoft.VisualStudio.TestTools.UnitTesting;

    namespace StringLibraryTest
    {
        [TestClass]
        public class UnitTest1
        {
            [TestMethod]
            public void TestMethod1()
            {
            }
        }
    }
    ```

    ```vb
    Imports Microsoft.VisualStudio.TestTools.UnitTesting

    Namespace StringLibraryTest
        <TestClass>
        Public Class UnitTest1
            <TestMethod>
            Sub TestSub()

            End Sub
        End Class
    End Namespace
    ```

   <span data-ttu-id="fd928-120">单元测试模板创建的源代码负责执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fd928-120">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="fd928-121">它会导入 <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> 命名空间，其中包含用于单元测试的类型。</span><span class="sxs-lookup"><span data-stu-id="fd928-121">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>

   - <span data-ttu-id="fd928-122">向 `UnitTest1` 类应用 [TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) 特性。</span><span class="sxs-lookup"><span data-stu-id="fd928-122">It applies the [TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) attribute to the `UnitTest1` class.</span></span> <span data-ttu-id="fd928-123">测试类中标记有 [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) 属性的所有测试方法都会在单元测试运行时自动执行。</span><span class="sxs-lookup"><span data-stu-id="fd928-123">Each test method in a test class tagged with the [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) attribute is executed automatically when the unit test is run.</span></span>

   - <span data-ttu-id="fd928-124">它应用 [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) 属性，将 C# 中的 `TestMethod1` 或将 Visual Basic 中的 `TestSub` 定义为在单元测试运行时自动执行的测试方法。</span><span class="sxs-lookup"><span data-stu-id="fd928-124">It applies the [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) attribute to define `TestMethod1` in C# or `TestSub` in Visual Basic as a test method for automatic execution when the unit test is run.</span></span>

1. <span data-ttu-id="fd928-125">在“解决方案资源管理器”  中，右键单击“StringLibraryTest”  项目的“依赖项”  节点，并从上下文菜单中选择“添加引用”  。</span><span class="sxs-lookup"><span data-stu-id="fd928-125">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Reference** from the context menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd928-126">![StringLibraryTest 依赖项的上下文菜单](./media/testing-library-with-visual-studio/add-reference-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="fd928-126">![Context menu of StringLibraryTest dependencies](./media/testing-library-with-visual-studio/add-reference-context-menu.png)</span></span>

1. <span data-ttu-id="fd928-127">在“引用管理器”  对话框中，展开“项目”  节点，并选中“StringLibrary”  旁边的框。</span><span class="sxs-lookup"><span data-stu-id="fd928-127">In the **Reference Manager** dialog, expand the **Projects** node and check the box next to **StringLibrary**.</span></span> <span data-ttu-id="fd928-128">添加对 `StringLibrary` 程序集的引用后，编译器可以查找 StringLibrary  方法。</span><span class="sxs-lookup"><span data-stu-id="fd928-128">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods.</span></span> <span data-ttu-id="fd928-129">选择“确定”  按钮。</span><span class="sxs-lookup"><span data-stu-id="fd928-129">Select the **OK** button.</span></span> <span data-ttu-id="fd928-130">这会添加对类库项目 `StringLibrary` 的引用。</span><span class="sxs-lookup"><span data-stu-id="fd928-130">A reference is added to your class library project, `StringLibrary`.</span></span>

   ![Visual Studio 中的“引用管理器”对话框](./media/testing-library-with-visual-studio/project-reference-manager.png)

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="fd928-132">添加并运行单元测试方法</span><span class="sxs-lookup"><span data-stu-id="fd928-132">Add and run unit test methods</span></span>

<span data-ttu-id="fd928-133">运行单元测试时，Visual Studio 执行单元测试类（对其应用了 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 特性的类）中标记有 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 特性的所有方法。</span><span class="sxs-lookup"><span data-stu-id="fd928-133">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a unit test class, the class to which the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute is applied.</span></span> <span data-ttu-id="fd928-134">当第一次遇到测试不通过或测试方法中的所有测试均已成功通过时，测试方法终止。</span><span class="sxs-lookup"><span data-stu-id="fd928-134">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="fd928-135">最常见的测试调用 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> 类的成员。</span><span class="sxs-lookup"><span data-stu-id="fd928-135">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="fd928-136">许多断言方法至少包含两个参数，其中一个是预期的测试结果，另一个是实际的测试结果。</span><span class="sxs-lookup"><span data-stu-id="fd928-136">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="fd928-137">下表显示了 `Assert` 类最常调用的一些方法：</span><span class="sxs-lookup"><span data-stu-id="fd928-137">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="fd928-138">断言方法</span><span class="sxs-lookup"><span data-stu-id="fd928-138">Assert methods</span></span>     | <span data-ttu-id="fd928-139">函数</span><span class="sxs-lookup"><span data-stu-id="fd928-139">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="fd928-140">验证两个值或对象是否相等。</span><span class="sxs-lookup"><span data-stu-id="fd928-140">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="fd928-141">如果值或对象不相等，则断言失败。</span><span class="sxs-lookup"><span data-stu-id="fd928-141">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="fd928-142">验证两个对象变量引用的是否是同一个对象。</span><span class="sxs-lookup"><span data-stu-id="fd928-142">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="fd928-143">如果这些变量引用不同的对象，则断言失败。</span><span class="sxs-lookup"><span data-stu-id="fd928-143">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="fd928-144">验证条件是否为 `false`。</span><span class="sxs-lookup"><span data-stu-id="fd928-144">Verifies that a condition is `false`.</span></span> <span data-ttu-id="fd928-145">如果条件为 `true`，则断言失败。</span><span class="sxs-lookup"><span data-stu-id="fd928-145">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="fd928-146">验证对象是否不为 `null`。</span><span class="sxs-lookup"><span data-stu-id="fd928-146">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="fd928-147">如果对象为 `null`，则断言失败。</span><span class="sxs-lookup"><span data-stu-id="fd928-147">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="fd928-148">还可以在测试方法中使用 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A> 方法来指示它应引发的异常的类型。</span><span class="sxs-lookup"><span data-stu-id="fd928-148">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="fd928-149">如果未引发指定异常，则测试不通过。</span><span class="sxs-lookup"><span data-stu-id="fd928-149">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="fd928-150">测试 `StringLibrary.StartsWithUpper` 方法时，需要提供许多以大写字符开头的字符串。</span><span class="sxs-lookup"><span data-stu-id="fd928-150">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="fd928-151">在这种情况下，此方法应返回 `true`，以便可以调用 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="fd928-151">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A> method.</span></span> <span data-ttu-id="fd928-152">同样，需要提供许多以非大写字符开头的字符串。</span><span class="sxs-lookup"><span data-stu-id="fd928-152">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="fd928-153">在这种情况下，此方法应返回 `false`，以便可以调用 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="fd928-153">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A> method.</span></span>

<span data-ttu-id="fd928-154">由于库方法处理的是字符串，因此还需要确保它能够成功处理[空字符串 (`String.Empty`)](xref:System.String.Empty)（不含字符且 <xref:System.String.Length> 为 0 的有效字符串）和 `null` 字符串（尚未初始化的字符串）。</span><span class="sxs-lookup"><span data-stu-id="fd928-154">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="fd928-155">如果对 <xref:System.String> 实例调用 `StartsWithUpper` 作为扩展方法，无法向其传递 `null` 字符串。</span><span class="sxs-lookup"><span data-stu-id="fd928-155">If `StartsWithUpper` is called as an extension method on a <xref:System.String> instance, it can't be passed a `null` string.</span></span> <span data-ttu-id="fd928-156">不过，还可以直接将其作为静态方法进行调用，并向其传递一个 <xref:System.String> 自变量。</span><span class="sxs-lookup"><span data-stu-id="fd928-156">However, you can also call it directly as a static method and pass a single <xref:System.String> argument.</span></span>

<span data-ttu-id="fd928-157">将定义三个方法，每个方法都会对字符串数组中的各个元素反复调用它的 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> 方法。</span><span class="sxs-lookup"><span data-stu-id="fd928-157">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="fd928-158">由于测试方法在第一次遇到测试不通过时会立即失败，因此将调用方法重载，以便传递字符串来指明方法调用中使用的字符串值。</span><span class="sxs-lookup"><span data-stu-id="fd928-158">Because the test method fails as soon as it finds the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="fd928-159">创建测试方法：</span><span class="sxs-lookup"><span data-stu-id="fd928-159">To create the test methods:</span></span>

1. <span data-ttu-id="fd928-160">将 UnitTest1.cs  或 UnitTest1.vb  代码窗口中的代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="fd928-160">In the *UnitTest1.cs* or *UnitTest1.vb* code window, replace the code with the following code:</span></span>

   [!code-csharp[Test#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs)]
   [!code-vb[Test#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/testlib.vb)]

   <span data-ttu-id="fd928-161">`TestStartsWithUpper` 方法中的大写字符的测试包括希腊文大写字母 alpha (U+0391) 和西里尔文大写字母 EM (U+041C)。</span><span class="sxs-lookup"><span data-stu-id="fd928-161">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="fd928-162">`TestDoesNotStartWithUpper` 方法中的小写字符的测试包括希腊文小写字母 alpha (U+03B1) 和西里尔文小写字母 Ghe (U+0433)。</span><span class="sxs-lookup"><span data-stu-id="fd928-162">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="fd928-163">在菜单栏上，选择“文件”   > “将 UnitTest1.cs 另存为”  或“文件”   > “将 UnitTest1.vb 另存为”  。</span><span class="sxs-lookup"><span data-stu-id="fd928-163">On the menu bar, select **File** > **Save UnitTest1.cs As** or **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="fd928-164">在“文件另存为”  对话框中，选择“保存”  按钮旁边的箭头，然后选择“保存时使用编码”  。</span><span class="sxs-lookup"><span data-stu-id="fd928-164">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd928-165">![Visual Studio“文件另存为”对话框](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="fd928-165">![Visual Studio Save File As dialog](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span></span>

1. <span data-ttu-id="fd928-166">在“确认另存为”  对话框中，选择“是”  按钮，保存文件。</span><span class="sxs-lookup"><span data-stu-id="fd928-166">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="fd928-167">在“高级保存选项”  对话框的“编码”  下拉列表中，选择“Unicode (UTF-8 带签名) - 代码页 65001”  ，然后选择“确定”  。</span><span class="sxs-lookup"><span data-stu-id="fd928-167">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd928-168">![Visual Studio“高级保存选项”对话框](./media/testing-library-with-visual-studio/advanced-save-options.png)</span><span class="sxs-lookup"><span data-stu-id="fd928-168">![Visual Studio Advanced Save Options dialog](./media/testing-library-with-visual-studio/advanced-save-options.png)</span></span>

   <span data-ttu-id="fd928-169">如果无法将源代码保存为 UTF8 编码文件，Visual Studio 可能会将其另存为 ASCII 文件。</span><span class="sxs-lookup"><span data-stu-id="fd928-169">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="fd928-170">在这种情况下，运行时将无法准确解码 ASCII 范围以外的 UTF8 字符，且测试结果也会不正确。</span><span class="sxs-lookup"><span data-stu-id="fd928-170">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="fd928-171">在菜单栏上，选择“测试”   > “运行”   > “所有测试”  。</span><span class="sxs-lookup"><span data-stu-id="fd928-171">On the menu bar, select **Test** > **Run** > **All Tests**.</span></span> <span data-ttu-id="fd928-172">此时，“测试资源管理器”  窗口打开并显示测试已成功运行。</span><span class="sxs-lookup"><span data-stu-id="fd928-172">The **Test Explorer** window opens and shows that the tests ran successfully.</span></span> <span data-ttu-id="fd928-173">“通过的测试”  部分列出了三个测试，“摘要”  部分报告了测试运行结果。</span><span class="sxs-lookup"><span data-stu-id="fd928-173">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd928-174">![通过测试的“测试资源管理器”窗口](./media/testing-library-with-visual-studio/test-explorer-window.png)</span><span class="sxs-lookup"><span data-stu-id="fd928-174">![Test Explorer window with passing tests](./media/testing-library-with-visual-studio/test-explorer-window.png)</span></span>

## <a name="handle-test-failures"></a><span data-ttu-id="fd928-175">处理测试失败</span><span class="sxs-lookup"><span data-stu-id="fd928-175">Handle test failures</span></span>

<span data-ttu-id="fd928-176">由于运行的测试均通过，因此需进行少量改动，以使其中一个测试方法失败：</span><span class="sxs-lookup"><span data-stu-id="fd928-176">Your test run had no failures, but change it slightly so that one of the test methods fails:</span></span>

1. <span data-ttu-id="fd928-177">通过修改 `TestDoesNotStartWithUpper` 方法中的 `words` 数组来包含字符串“Error”。</span><span class="sxs-lookup"><span data-stu-id="fd928-177">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="fd928-178">由于 Visual Studio 将在生成运行测试的解决方案时自动保存打开的文件，因此无需手动保存。</span><span class="sxs-lookup"><span data-stu-id="fd928-178">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="fd928-179">从菜单栏中选择“测试”   > “运行”   > “所有测试”  ，运行测试。</span><span class="sxs-lookup"><span data-stu-id="fd928-179">Run the test by selecting **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="fd928-180">“测试资源管理器”  窗口指示有两个测试成功，还有一个失败。</span><span class="sxs-lookup"><span data-stu-id="fd928-180">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd928-181">![未通过测试的“测试资源管理器”窗口](./media/testing-library-with-visual-studio/failed-test-window.png)</span><span class="sxs-lookup"><span data-stu-id="fd928-181">![Test Explorer window with failing tests](./media/testing-library-with-visual-studio/failed-test-window.png)</span></span>

1. <span data-ttu-id="fd928-182">选择失败的测试，`TestDoesNotStartWith`。</span><span class="sxs-lookup"><span data-stu-id="fd928-182">Select the failed test, `TestDoesNotStartWith`.</span></span> <span data-ttu-id="fd928-183">“测试资源管理器”窗口显示断言生成的消息：  “Assert.IsFalse 失败。</span><span class="sxs-lookup"><span data-stu-id="fd928-183">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="fd928-184">“Error”应返回 false；实际返回 True”。</span><span class="sxs-lookup"><span data-stu-id="fd928-184">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="fd928-185">由于此次失败，数组中“Error”之后的所有字符串都未进行测试。</span><span class="sxs-lookup"><span data-stu-id="fd928-185">Because of the failure, all strings in the array after "Error" weren't tested.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd928-186">![显示 IsFalse 断言失败的“测试资源管理器”窗口](./media/testing-library-with-visual-studio/failed-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="fd928-186">![Test Explorer window showing the IsFalse assertion failure](./media/testing-library-with-visual-studio/failed-test-detail.png)</span></span>

1. <span data-ttu-id="fd928-187">撤消在步骤 1 中执行的修改并删除字符串“Error”。</span><span class="sxs-lookup"><span data-stu-id="fd928-187">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="fd928-188">重新运行测试，测试将通过。</span><span class="sxs-lookup"><span data-stu-id="fd928-188">Rerun the test and the tests will pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="fd928-189">测试库的发行版本</span><span class="sxs-lookup"><span data-stu-id="fd928-189">Test the Release version of the library</span></span>

<span data-ttu-id="fd928-190">现已测试库的调试版本。</span><span class="sxs-lookup"><span data-stu-id="fd928-190">You've been running your tests against the Debug version of the library.</span></span> <span data-ttu-id="fd928-191">至此，测试已全部通过，且已充分测试库，应对库的发布版本再运行一次这些测试。</span><span class="sxs-lookup"><span data-stu-id="fd928-191">Now that your tests have all passed and you've adequately tested your library, you should run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="fd928-192">许多因素（包括编译器优化）有时可能会导致调试版本和发行版本出现行为差异。</span><span class="sxs-lookup"><span data-stu-id="fd928-192">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="fd928-193">若要测试发行版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fd928-193">To test the Release build:</span></span>

1. <span data-ttu-id="fd928-194">在 Visual Studio 工具栏中，将生成配置从 **“调试”** 更改为 **“发行”** 。</span><span class="sxs-lookup"><span data-stu-id="fd928-194">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd928-195">![突出显示发布版本的 Visual Studio 工具栏](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span><span class="sxs-lookup"><span data-stu-id="fd928-195">![Visual Studio toolbar with release build highlighted](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span></span>

1. <span data-ttu-id="fd928-196">在“解决方案资源管理器”  中，右键单击“StringLibrary”  项目，从上下文菜单中选择“生成”  ，重新编译库。</span><span class="sxs-lookup"><span data-stu-id="fd928-196">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd928-197">![带有生成命令的 StringLibrary 上下文菜单](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="fd928-197">![StringLibrary context menu with build command](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span></span>

1. <span data-ttu-id="fd928-198">从菜单栏中选择“测试”   > “运行”   > “所有测试”  ，运行单元测试。</span><span class="sxs-lookup"><span data-stu-id="fd928-198">Run the unit tests by choosing **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="fd928-199">测试通过。</span><span class="sxs-lookup"><span data-stu-id="fd928-199">The tests pass.</span></span>

<span data-ttu-id="fd928-200">至此，已完成对库的测试，下一步就是使其可供调用方使用。</span><span class="sxs-lookup"><span data-stu-id="fd928-200">Now that you've finished testing your library, the next step is to make it available to callers.</span></span> <span data-ttu-id="fd928-201">可以将类库与一个或多个应用程序捆绑在一起，也可以 NuGet 包的形式分发类库。</span><span class="sxs-lookup"><span data-stu-id="fd928-201">You can bundle it with one or more applications, or you can distribute it as a NuGet package.</span></span> <span data-ttu-id="fd928-202">有关详细信息，请参阅[使用 .NET Standard 类库](consuming-library-with-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="fd928-202">For more information, see [Consuming a .NET Standard Class Library](consuming-library-with-visual-studio.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fd928-203">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd928-203">See also</span></span>

- [<span data-ttu-id="fd928-204">单元测试基础知识 - Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fd928-204">Unit test basics - Visual Studio</span></span>](/visualstudio/test/unit-test-basics)
