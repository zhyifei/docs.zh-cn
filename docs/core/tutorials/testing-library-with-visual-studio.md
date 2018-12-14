---
title: 使用 Visual Studio 2017 测试 .NET Core 类库
description: 为 .NET Core 类库创建单元测试项目。 验证 .NET Core 类库能否正确地进行单元测试。
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
dev_langs:
- csharp
- vb
ms.custom:
- vs-dotnet
- seodoc18
ms.openlocfilehash: e3b13126833e49681661e8834ce9f3d8a6c1133e
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144892"
---
# <a name="testing-a-class-library-with-net-core-in-visual-studio-2017"></a><span data-ttu-id="2c244-104">使用 Visual Studio 2017 测试 .NET Core 类库</span><span class="sxs-lookup"><span data-stu-id="2c244-104">Testing a class library with .NET Core in Visual Studio 2017</span></span>

<span data-ttu-id="2c244-105">在[使用 Visual Studio 2017 生成 C# .NET Core 类库](library-with-visual-studio.md)或[使用 Visual Studio 2017 生成 Visual Basic .NET Core 类库](vb-library-with-visual-studio.md)中，创建了简单的类库，用于向 <xref:System.String> 类添加扩展方法。</span><span class="sxs-lookup"><span data-stu-id="2c244-105">In [Building a class library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio.md) or [Building a class library with Visual Basic and .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md), you created a simple class library that adds an extension method to the <xref:System.String> class.</span></span> <span data-ttu-id="2c244-106">现在，将创建一个单元测试，用于确保此类库能够按预期运行。</span><span class="sxs-lookup"><span data-stu-id="2c244-106">Now, you'll create a unit test to make sure that it works as expected.</span></span> <span data-ttu-id="2c244-107">向在上一主题中创建的解决方案添加单元测试项目。</span><span class="sxs-lookup"><span data-stu-id="2c244-107">You'll add your unit test project to the solution you created in the previous topic.</span></span>

## <a name="creating-a-unit-test-project"></a><span data-ttu-id="2c244-108">创建单元测试项目</span><span class="sxs-lookup"><span data-stu-id="2c244-108">Creating a unit test project</span></span>

<span data-ttu-id="2c244-109">若要创建单元测试项目，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2c244-109">To create the unit test project, do the following:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="2c244-110">C#</span><span class="sxs-lookup"><span data-stu-id="2c244-110">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="2c244-111">在“解决方案资源管理器”中，打开“ClassLibraryProjects”解决方案节点的上下文菜单，再依次选择“添加” > “新项目”。</span><span class="sxs-lookup"><span data-stu-id="2c244-111">In **Solution Explorer**, open the context menu for the **ClassLibraryProjects** solution node and select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="2c244-112">在“添加新项目”对话框中，选择“Visual C#”节点。</span><span class="sxs-lookup"><span data-stu-id="2c244-112">In the **Add New Project** dialog, select the **Visual C#** node.</span></span> <span data-ttu-id="2c244-113">然后，依次选择“.NET Core”节点和“MSTest 测试项目(.NET Core)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="2c244-113">Then select the **.NET Core** node followed by the **MSTest Test Project (.NET Core)** project template.</span></span> <span data-ttu-id="2c244-114">在“名称”文本框中，输入项目名称“StringLibraryTest”。</span><span class="sxs-lookup"><span data-stu-id="2c244-114">In the **Name** text box, enter "StringLibraryTest" as the name of the project.</span></span> <span data-ttu-id="2c244-115">选择“确定”，创建单元测试项目。</span><span class="sxs-lookup"><span data-stu-id="2c244-115">Select **OK** to create the unit test project.</span></span>

   ![“添加新项目”对话框](./media/testing-library-with-visual-studio/testproject.png)

   > [!NOTE]  
   > <span data-ttu-id="2c244-117">除了 MSTest 测试项目之外，还可以使用 Visual Studio 为 .NET Core 创建 xUnit 测试项目。</span><span class="sxs-lookup"><span data-stu-id="2c244-117">In addition to an MSTest Test project, you can also use Visual Studio to create an xUnit test project for .NET Core.</span></span>

1. <span data-ttu-id="2c244-118">此时，Visual Studio 会创建项目，并在代码窗口中打开 UnitTest1.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="2c244-118">Visual Studio creates the project and opens the *UnitTest1.cs* file in the code window.</span></span>

   ![Visual Studio 代码窗口显示单元测试项目默认的 UnitTest1 类和 TestMethod1 方法](./media/testing-library-with-visual-studio/unittestwindow.png)

   <span data-ttu-id="2c244-120">单元测试模板创建的源代码负责执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2c244-120">The source code created by the unit test template does the following:</span></span>

   * <span data-ttu-id="2c244-121">它会导入 <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> 命名空间，其中包含用于单元测试的类型。</span><span class="sxs-lookup"><span data-stu-id="2c244-121">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>

   * <span data-ttu-id="2c244-122">向 `UnitTest1` 类应用 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 特性。</span><span class="sxs-lookup"><span data-stu-id="2c244-122">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span> <span data-ttu-id="2c244-123">测试类中标记有 \[TestMethod\] 属性的所有测试方法都会在单元测试运行时自动执行。</span><span class="sxs-lookup"><span data-stu-id="2c244-123">Each test method in a test class tagged with the \[TestMethod\] attribute is executed automatically when the unit test is run.</span></span>

   * <span data-ttu-id="2c244-124">它会应用 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 属性，将 `TestMethod1` 定义为在单元测试运行时自动执行的测试方法。</span><span class="sxs-lookup"><span data-stu-id="2c244-124">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1` as a test method for automatic execution when the unit test is run.</span></span>

1. <span data-ttu-id="2c244-125">在“解决方案资源管理器”中，右键单击“StringLibraryTest”项目的“依赖项”节点，并从上下文菜单中选择“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="2c244-125">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Reference** from the context menu.</span></span>

   ![StringLibraryTest 依赖项的上下文菜单](./media/testing-library-with-visual-studio/addreference.png)

1. <span data-ttu-id="2c244-127">在“引用管理器”对话框中，展开“项目”节点，并选中“StringLibrary”旁边的框。</span><span class="sxs-lookup"><span data-stu-id="2c244-127">In the **Reference Manager** dialog, expand the **Projects** node and check the box next to **StringLibrary**.</span></span> <span data-ttu-id="2c244-128">添加对 `StringLibrary` 程序集的引用后，编译器可以查找 StringLibrary 方法。</span><span class="sxs-lookup"><span data-stu-id="2c244-128">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods.</span></span> <span data-ttu-id="2c244-129">选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="2c244-129">Select the **OK** button.</span></span> <span data-ttu-id="2c244-130">这会添加对类库项目 `StringLibrary` 的引用。</span><span class="sxs-lookup"><span data-stu-id="2c244-130">This adds a reference to your class library project, `StringLibrary`.</span></span>

   ![引用管理器](./media/testing-library-with-visual-studio/referencemanager.png)
# <a name="visual-basictabvb"></a>[<span data-ttu-id="2c244-132">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2c244-132">Visual Basic</span></span>](#tab/vb) 
1. <span data-ttu-id="2c244-133">在“解决方案资源管理器”中，打开“ClassLibraryProjects”解决方案节点的上下文菜单，再依次选择“添加” > “新项目”。</span><span class="sxs-lookup"><span data-stu-id="2c244-133">In **Solution Explorer**, open the context menu for the **ClassLibraryProjects** solution node and select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="2c244-134">在“添加新项目”对话框中，选择“Visual Basic”节点。</span><span class="sxs-lookup"><span data-stu-id="2c244-134">In the **Add New Project** dialog, select the **Visual Basic** node.</span></span> <span data-ttu-id="2c244-135">然后，依次选择“.NET Core”节点和“MSTest 测试项目(.NET Core)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="2c244-135">Then select the **.NET Core** node followed by the **MSTest Test Project (.NET Core)** project template.</span></span> <span data-ttu-id="2c244-136">在“名称”文本框中，输入项目名称“StringLibraryTest”。</span><span class="sxs-lookup"><span data-stu-id="2c244-136">In the **Name** text box, enter "StringLibraryTest" as the name of the project.</span></span> <span data-ttu-id="2c244-137">选择“确定”，创建单元测试项目。</span><span class="sxs-lookup"><span data-stu-id="2c244-137">Select **OK** to create the unit test project.</span></span>

   ![“添加新项目”对话框](./media/testing-library-with-visual-studio/vb-testproject.png)

   > [!NOTE]  
   > <span data-ttu-id="2c244-139">除了 MSTest 测试项目之外，还可以使用 Visual Studio 为 .NET Core 创建 xUnit 测试项目。</span><span class="sxs-lookup"><span data-stu-id="2c244-139">In addition to an MSTest Test project, you can also use Visual Studio to create an xUnit test project for .NET Core.</span></span>

1. <span data-ttu-id="2c244-140">此时，Visual Studio 会创建项目，并在代码窗口中打开 UnitTest1.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="2c244-140">Visual Studio creates the project and opens the *UnitTest1.vb* file in the code window.</span></span>

   ![Visual Studio 代码窗口显示单元测试项目默认的 UnitTest1 类和 TestMethod1 方法](./media/testing-library-with-visual-studio/vb-unittestwindow.png)

   <span data-ttu-id="2c244-142">单元测试模板创建的源代码负责执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2c244-142">The source code created by the unit test template does the following:</span></span>

   * <span data-ttu-id="2c244-143">导入 [Microsoft.VisualStudio.TestTools.UnitTesting]<xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=namewithType> 命名空间，其中包含用于单元测试的类型。</span><span class="sxs-lookup"><span data-stu-id="2c244-143">It imports the [Microsoft.VisualStudio.TestTools.UnitTesting]<xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=namewithType> namespace, which contains the types used for unit testing.</span></span>

   * <span data-ttu-id="2c244-144">向 `UnitTest1` 类应用 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 特性。</span><span class="sxs-lookup"><span data-stu-id="2c244-144">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>) attribute to the `UnitTest1` class.</span></span> <span data-ttu-id="2c244-145">测试类中标记有 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 特性的所有测试方法都会在单元测试运行时自动执行。</span><span class="sxs-lookup"><span data-stu-id="2c244-145">Each test method in a test class tagged with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute is executed automatically when the unit test is run.</span></span>

   * <span data-ttu-id="2c244-146">它会应用 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 属性，将 `TestMethod1` 定义为在单元测试运行时自动执行的测试方法。</span><span class="sxs-lookup"><span data-stu-id="2c244-146">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1` as a test method for automatic execution when the unit test is run.</span></span>

1. <span data-ttu-id="2c244-147">在“解决方案资源管理器”中，右键单击“StringLibraryTest”项目的“依赖项”节点，并从上下文菜单中选择“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="2c244-147">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Reference** from the context menu.</span></span>

   ![StringLibraryTest 依赖项的上下文菜单](./media/testing-library-with-visual-studio/addreference.png)

1. <span data-ttu-id="2c244-149">在“引用管理器”对话框中，展开“项目”节点，并选中“StringLibrary”旁边的框。</span><span class="sxs-lookup"><span data-stu-id="2c244-149">In the **Reference Manager** dialog, expand the **Projects** node and check the box next to **StringLibrary**.</span></span> <span data-ttu-id="2c244-150">添加对 `StringLibrary` 程序集的引用后，编译器可以查找 StringLibrary 方法。</span><span class="sxs-lookup"><span data-stu-id="2c244-150">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods.</span></span> <span data-ttu-id="2c244-151">选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="2c244-151">Select the **OK** button.</span></span> <span data-ttu-id="2c244-152">这会添加对类库项目 `StringLibrary` 的引用。</span><span class="sxs-lookup"><span data-stu-id="2c244-152">This adds a reference to your class library project, `StringLibrary`.</span></span>

   ![引用管理器](./media/testing-library-with-visual-studio/referencemanager.png)
---

## <a name="adding-and-running-unit-test-methods"></a><span data-ttu-id="2c244-154">添加并运行单元测试方法</span><span class="sxs-lookup"><span data-stu-id="2c244-154">Adding and running unit test methods</span></span>

<span data-ttu-id="2c244-155">运行单元测试时，Visual Studio 执行单元测试类（对其应用了 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 特性的类）中标记有 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 特性的所有方法。</span><span class="sxs-lookup"><span data-stu-id="2c244-155">When Visual Studio runs a unit test, it executes each method marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a unit test class, the class to which the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute is applied.</span></span> <span data-ttu-id="2c244-156">当第一次遇到测试不通过或测试方法中的所有测试均已成功通过时，测试方法终止。</span><span class="sxs-lookup"><span data-stu-id="2c244-156">A test method ends when the first failure is encountered or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="2c244-157">最常见的测试调用 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> 类的成员。</span><span class="sxs-lookup"><span data-stu-id="2c244-157">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="2c244-158">许多断言方法至少包含两个参数，其中一个是预期的测试结果，另一个是实际的测试结果。</span><span class="sxs-lookup"><span data-stu-id="2c244-158">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="2c244-159">下表显示了最常调用的一些方法。</span><span class="sxs-lookup"><span data-stu-id="2c244-159">Some of its most frequently called methods are shown in the table below.</span></span>

<span data-ttu-id="2c244-160">断言方法</span><span class="sxs-lookup"><span data-stu-id="2c244-160">Assert methods</span></span> | <span data-ttu-id="2c244-161">函数</span><span class="sxs-lookup"><span data-stu-id="2c244-161">Function</span></span>
--- | ---
`Assert.AreEqual` | <span data-ttu-id="2c244-162">验证两个值或对象是否相等。</span><span class="sxs-lookup"><span data-stu-id="2c244-162">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="2c244-163">如果值或对象不相等，则断言失败。</span><span class="sxs-lookup"><span data-stu-id="2c244-163">The assert fails if the values or objects are not equal.</span></span>
`Assert.AreSame` | <span data-ttu-id="2c244-164">验证两个对象变量引用的是否是同一个对象。</span><span class="sxs-lookup"><span data-stu-id="2c244-164">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="2c244-165">如果这些变量引用不同的对象，则断言失败。</span><span class="sxs-lookup"><span data-stu-id="2c244-165">The assert fails if the variables refer to different objects.</span></span>
`Assert.IsFalse` | <span data-ttu-id="2c244-166">验证条件是否为 `false`。</span><span class="sxs-lookup"><span data-stu-id="2c244-166">Verifies that a condition is `false`.</span></span> <span data-ttu-id="2c244-167">如果条件为 `true`，则断言失败。</span><span class="sxs-lookup"><span data-stu-id="2c244-167">The assert fails if the condition is `true`.</span></span>
`Assert.IsNotNull` | <span data-ttu-id="2c244-168">验证对象是否不为 `null`。</span><span class="sxs-lookup"><span data-stu-id="2c244-168">Verifies that an object is not `null`.</span></span> <span data-ttu-id="2c244-169">如果对象为 `null`，则断言失败。</span><span class="sxs-lookup"><span data-stu-id="2c244-169">The assert fails if the object is `null`.</span></span>

<span data-ttu-id="2c244-170">还可向测试方法应用 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute> 特性。</span><span class="sxs-lookup"><span data-stu-id="2c244-170">You can also apply the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute> attribute to a test method.</span></span> <span data-ttu-id="2c244-171">它指明了测试方法预计会引发的异常类型。</span><span class="sxs-lookup"><span data-stu-id="2c244-171">It indicates the type of exception a test method is expected to throw.</span></span> <span data-ttu-id="2c244-172">如果未抛出指定异常，则测试不通过。</span><span class="sxs-lookup"><span data-stu-id="2c244-172">The test fails if the specified exception is not thrown.</span></span>

<span data-ttu-id="2c244-173">测试 `StringLibrary.StartsWithUpper` 方法时，需要提供许多以大写字符开头的字符串。</span><span class="sxs-lookup"><span data-stu-id="2c244-173">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="2c244-174">在这种情况下，此方法应返回 `true`，以便可以调用 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="2c244-174">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A> method.</span></span> <span data-ttu-id="2c244-175">同样，需要提供许多以非大写字符开头的字符串。</span><span class="sxs-lookup"><span data-stu-id="2c244-175">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="2c244-176">在这种情况下，此方法应返回 `false`，以便可以调用 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="2c244-176">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A> method.</span></span>

<span data-ttu-id="2c244-177">由于库方法处理的是字符串，因此还需要确保它能够成功处理[空字符串 (`String.Empty`)](xref:System.String.Empty)（不含字符且 <xref:System.String.Length> 为 0 的有效字符串）和 `null` 字符串（尚未初始化的字符串）。</span><span class="sxs-lookup"><span data-stu-id="2c244-177">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that has not been initialized.</span></span> <span data-ttu-id="2c244-178">如果对 <xref:System.String> 实例调用 `StartsWithUpper` 作为扩展方法，无法向其传递 `null` 字符串。</span><span class="sxs-lookup"><span data-stu-id="2c244-178">If `StartsWithUpper` is called as an extension method on a <xref:System.String> instance, it cannot be passed a `null` string.</span></span> <span data-ttu-id="2c244-179">不过，还可以直接将其作为静态方法进行调用，并向其传递一个 <xref:System.String> 自变量。</span><span class="sxs-lookup"><span data-stu-id="2c244-179">However, you can also call it directly as a static method and pass a single <xref:System.String> argument.</span></span>

<span data-ttu-id="2c244-180">将定义三个方法，每个方法都会对字符串数组中的各个元素反复调用它的 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> 方法。</span><span class="sxs-lookup"><span data-stu-id="2c244-180">You'll define three methods, each of which calls its <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="2c244-181">由于测试方法在第一次遇到测试不通过时会立即失败，因此将调用方法重载，以便传递字符串来指明方法调用中使用的字符串值。</span><span class="sxs-lookup"><span data-stu-id="2c244-181">Because the test method fails as soon as it encounters the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="2c244-182">创建测试方法：</span><span class="sxs-lookup"><span data-stu-id="2c244-182">To create the test methods:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="2c244-183">C#</span><span class="sxs-lookup"><span data-stu-id="2c244-183">C#</span></span>](#tab/csharp) 
1. <span data-ttu-id="2c244-184">将 UnitTest1.cs 代码窗口中的代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="2c244-184">In the *UnitTest1.cs* code window, replace the code with the following code:</span></span>

   [!CODE-csharp[Test#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs)]

   <span data-ttu-id="2c244-185">请注意，`TestStartsWithUpper` 方法中测试的大写字符包括希腊文大写字母 alpha (U+0391) 和西里尔文大写字母 EM (U+041C)，`TestDoesNotStartWithUpper` 方法中测试的小写字符包括希腊文小写字母 alpha (U+03B1) 和西里尔文小写字母 Ghe (U+0433)。</span><span class="sxs-lookup"><span data-stu-id="2c244-185">Note that your test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C), and the test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="2c244-186">在菜单栏上，选择“文件” > “将 UnitTest1.cs 另存为”。</span><span class="sxs-lookup"><span data-stu-id="2c244-186">On the menu bar, select **File** > **Save UnitTest1.cs As**.</span></span> <span data-ttu-id="2c244-187">在“文件另存为”对话框中，选择“保存”按钮旁边的箭头，然后选择“保存时使用编码”。</span><span class="sxs-lookup"><span data-stu-id="2c244-187">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   ![“文件另存为”对话框](./media/testing-library-with-visual-studio/savefileas.png)
# <a name="visual-basictabvb"></a>[<span data-ttu-id="2c244-189">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2c244-189">Visual Basic</span></span>](#tab/vb) 
1. <span data-ttu-id="2c244-190">将 UnitTest1.vb 代码窗口中的代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="2c244-190">In the *UnitTest1.vb* code window, replace the code with the following code:</span></span>

    [!CODE-vb[Test#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/testlib.vb)]

   <span data-ttu-id="2c244-191">请注意，`TestStartsWithUpper` 方法中测试的大写字符包括希腊文大写字母 alpha (U+0391) 和西里尔文大写字母 EM (U+041C)，`TestDoesNotStartWithUpper` 方法中测试的小写字符包括希腊文小写字母 alpha (U+03B1) 和西里尔文小写字母 Ghe (U+0433)。</span><span class="sxs-lookup"><span data-stu-id="2c244-191">Note that your test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C), and the test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="2c244-192">在菜单栏上，依次选择“文件” > “将 UnitTest1.vb 另存为”。</span><span class="sxs-lookup"><span data-stu-id="2c244-192">On the menu bar, select **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="2c244-193">在“文件另存为”对话框中，选择“保存”按钮旁边的箭头，然后选择“保存时使用编码”。</span><span class="sxs-lookup"><span data-stu-id="2c244-193">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   ![“文件另存为”对话框](./media/testing-library-with-visual-studio/savefileas.png)
---

1. <span data-ttu-id="2c244-195">在“确认另存为”对话框中，选择“是”按钮，保存文件。</span><span class="sxs-lookup"><span data-stu-id="2c244-195">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="2c244-196">在“高级保存选项”对话框的“编码”下拉列表中，选择“Unicode (UTF-8 带签名) - 代码页 65001”，然后选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="2c244-196">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   ![“高级保存选项”对话框](./media/testing-library-with-visual-studio/advancedsaveoptions.png)

   <span data-ttu-id="2c244-198">如果无法将源代码保存为 UTF8 编码文件，Visual Studio 可能会将其另存为 ASCII 文件。</span><span class="sxs-lookup"><span data-stu-id="2c244-198">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="2c244-199">在这种情况下，运行时将无法准确解码 ASCII 范围以外的 UTF8 字符，且测试结果也会不准确。</span><span class="sxs-lookup"><span data-stu-id="2c244-199">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be accurate.</span></span>

1. <span data-ttu-id="2c244-200">在菜单栏上，选择“测试” > “运行” > “所有测试”。</span><span class="sxs-lookup"><span data-stu-id="2c244-200">On the menu bar, select **Test** > **Run** > **All Tests**.</span></span> <span data-ttu-id="2c244-201">此时，“测试资源管理器”窗口打开并显示测试已成功运行。</span><span class="sxs-lookup"><span data-stu-id="2c244-201">The **Test Explorer** window opens and shows that the tests ran successfully.</span></span> <span data-ttu-id="2c244-202">“通过的测试”部分列出了三个测试，“摘要”部分报告了测试运行结果。</span><span class="sxs-lookup"><span data-stu-id="2c244-202">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   ![测试资源管理器窗口](./media/testing-library-with-visual-studio/firsttest.png)

## <a name="handling-test-failures"></a><span data-ttu-id="2c244-204">处理未通过的测试</span><span class="sxs-lookup"><span data-stu-id="2c244-204">Handling test failures</span></span>

<span data-ttu-id="2c244-205">由于运行的测试均通过，因此需进行少量改动，以使其中一个测试方法失败：</span><span class="sxs-lookup"><span data-stu-id="2c244-205">Your test run had no failures, but change it slightly so that one of the test methods fails:</span></span>

1. <span data-ttu-id="2c244-206">通过修改 `TestDoesNotStartWithUpper` 方法中的 `words` 数组来包含字符串“Error”。</span><span class="sxs-lookup"><span data-stu-id="2c244-206">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="2c244-207">由于 Visual Studio 将在生成运行测试的解决方案时自动保存打开的文件，因此无需手动保存。</span><span class="sxs-lookup"><span data-stu-id="2c244-207">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```
   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```
1. <span data-ttu-id="2c244-208">从菜单栏中选择“测试” > “运行” > “所有测试”，运行测试。</span><span class="sxs-lookup"><span data-stu-id="2c244-208">Run the test by selecting **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="2c244-209">“测试资源管理器”窗口指示有两个测试成功，还有一个失败。</span><span class="sxs-lookup"><span data-stu-id="2c244-209">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   ![测试资源管理器窗口](./media/testing-library-with-visual-studio/failedtest.png)

1. <span data-ttu-id="2c244-211">在“未通过的测试”部分中，选择未通过的测试 `TestDoesNotStartWith`。</span><span class="sxs-lookup"><span data-stu-id="2c244-211">In the **Failed Tests** section, select the failed test, `TestDoesNotStartWith`.</span></span> <span data-ttu-id="2c244-212">“测试资源管理器”窗口显示断言生成的消息：“Assert.IsFalse 失败。</span><span class="sxs-lookup"><span data-stu-id="2c244-212">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="2c244-213">‘Error’ 应返回 false; 实际返回 True”。</span><span class="sxs-lookup"><span data-stu-id="2c244-213">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="2c244-214">由于此次失败，数组中“Error”之后的所有字符串都未进行测试。</span><span class="sxs-lookup"><span data-stu-id="2c244-214">Because of the failure, all strings in the array after "Error" were not tested.</span></span>

   ![显示 Is False 断言失败的“测试资源管理器”窗口](./media/testing-library-with-visual-studio/failedtestdetail.png)

1. <span data-ttu-id="2c244-216">删除添加的代码 (`"Error", `)，然后重新运行测试。</span><span class="sxs-lookup"><span data-stu-id="2c244-216">Remove the code that you added (`"Error", `) and rerun the test.</span></span> <span data-ttu-id="2c244-217">测试将通过。</span><span class="sxs-lookup"><span data-stu-id="2c244-217">The tests will pass.</span></span>

## <a name="testing-the-release-version-of-the-library"></a><span data-ttu-id="2c244-218">测试库的发行版本</span><span class="sxs-lookup"><span data-stu-id="2c244-218">Testing the Release version of the library</span></span>

<span data-ttu-id="2c244-219">现已测试库的调试版本。</span><span class="sxs-lookup"><span data-stu-id="2c244-219">You've been running your tests against the Debug version of the library.</span></span> <span data-ttu-id="2c244-220">至此，测试已全部通过，且已充分测试库，应对库的发布版本再运行一次这些测试。</span><span class="sxs-lookup"><span data-stu-id="2c244-220">Now that your tests have all passed and you've adequately tested your library, you should run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="2c244-221">许多因素（包括编译器优化）有时可能会导致调试版本和发行版本出现行为差异。</span><span class="sxs-lookup"><span data-stu-id="2c244-221">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="2c244-222">若要测试发行版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2c244-222">To test the Release build:</span></span>

1. <span data-ttu-id="2c244-223">在 Visual Studio 工具栏中，将生成配置从 **“调试”** 更改为 **“发行”**。</span><span class="sxs-lookup"><span data-stu-id="2c244-223">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   ![Visual Studio 工具栏](./media/testing-library-with-visual-studio/toolbar.png)

1. <span data-ttu-id="2c244-225">在“解决方案资源管理器”中，右键单击“StringLibrary”项目，从上下文菜单中选择“生成”，重新编译库。</span><span class="sxs-lookup"><span data-stu-id="2c244-225">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   ![StringLibrary 上下文菜单](./media/testing-library-with-visual-studio/buildlibrary.png)

1. <span data-ttu-id="2c244-227">从菜单栏中选择“测试” > “运行” > “所有测试”，运行单元测试。</span><span class="sxs-lookup"><span data-stu-id="2c244-227">Run the unit tests by choosing **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="2c244-228">测试通过。</span><span class="sxs-lookup"><span data-stu-id="2c244-228">The tests pass.</span></span>

<span data-ttu-id="2c244-229">至此，已完成对库的测试，下一步就是使其可供调用方使用。</span><span class="sxs-lookup"><span data-stu-id="2c244-229">Now that you've finished testing your library, the next step is to make it available to callers.</span></span> <span data-ttu-id="2c244-230">可以将类库与一个或多个应用程序捆绑在一起，也可以 NuGet 包的形式分发类库。</span><span class="sxs-lookup"><span data-stu-id="2c244-230">You can bundle it with one or more applications, or you can distribute it as a NuGet package.</span></span> <span data-ttu-id="2c244-231">有关详细信息，请参阅[使用 .NET Standard 类库](./consuming-library-with-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="2c244-231">For more information, see [Consuming a .NET Standard Class Library](./consuming-library-with-visual-studio.md).</span></span>
