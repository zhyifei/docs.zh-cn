---
title: 在 Visual Studio 中生成 .NET Standard 类库
description: 了解如何使用 Visual Studio 生成以 C# 或 Visual Basic 编写的 .NET Standard 类库
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 748a1499e0c3a4a41613a69b715dbcfbd585bfe3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714011"
---
# <a name="build-a-net-standard-library-in-visual-studio"></a><span data-ttu-id="2340c-103">在 Visual Studio 中生成 .NET Standard 库</span><span class="sxs-lookup"><span data-stu-id="2340c-103">Build a .NET Standard library in Visual Studio</span></span>

<span data-ttu-id="2340c-104">类库定义的是可以由应用程序调用的类型和方法  。</span><span class="sxs-lookup"><span data-stu-id="2340c-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="2340c-105">借助面向 .NET Standard 2.0 的类库，任何支持相应 .NET Standard 版本的 .NET 实现都可以调用库。</span><span class="sxs-lookup"><span data-stu-id="2340c-105">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="2340c-106">完成类库时，可以决定是要将其作为第三方组件进行分布，还是要将其作为与一个或多个应用程序捆绑在一起的组件进行添加。</span><span class="sxs-lookup"><span data-stu-id="2340c-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="2340c-107">有关 .NET Standard 版本及其支持的平台列表，请参阅 [.NET Standard](../../standard/net-standard.md)。</span><span class="sxs-lookup"><span data-stu-id="2340c-107">For a list of .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="2340c-108">在本主题中，将创建包含一个字符串处理方法的简单实用工具库。</span><span class="sxs-lookup"><span data-stu-id="2340c-108">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="2340c-109">我们将把它作为[扩展方法](../../csharp/programming-guide/classes-and-structs/extension-methods.md)进行实现，这样就可以把它作为 <xref:System.String> 类成员进行调用。</span><span class="sxs-lookup"><span data-stu-id="2340c-109">You'll implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="create-a-visual-studio-solution"></a><span data-ttu-id="2340c-110">创建 Visual Studio 解决方案</span><span class="sxs-lookup"><span data-stu-id="2340c-110">Create a Visual Studio solution</span></span>

<span data-ttu-id="2340c-111">首先，创建一个空白解决方案来放置类库项目。</span><span class="sxs-lookup"><span data-stu-id="2340c-111">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="2340c-112">Visual Studio 解决方案用作一个或多个项目的容器。</span><span class="sxs-lookup"><span data-stu-id="2340c-112">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="2340c-113">如果继续学习本系列教程，你将向相同的解决方案添加其他相关项目。</span><span class="sxs-lookup"><span data-stu-id="2340c-113">You'll add additional, related projects to the same solution if you continue on with the tutorial series.</span></span>

<span data-ttu-id="2340c-114">创建空白解决方案：</span><span class="sxs-lookup"><span data-stu-id="2340c-114">To create the blank solution:</span></span>

1. <span data-ttu-id="2340c-115">打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="2340c-115">Open Visual Studio.</span></span>

2. <span data-ttu-id="2340c-116">在“开始”窗口上，选择“创建新项目”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-116">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="2340c-117">在“创建新项目”  页面上，在搜索框中输入“解决方案”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-117">On the **Create a new project** page, enter **solution** in the search box.</span></span> <span data-ttu-id="2340c-118">选择“空白解决方案”  模板，然后选择“下一步”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-118">Choose the **Blank Solution** template, and then choose **Next**.</span></span>

   ![Visual Studio 中的空白解决方案模板](media/library-with-visual-studio/blank-solution.png)

4. <span data-ttu-id="2340c-120">在“配置新项目”  页面上，在“项目名称”  框中输入“ClassLibraryProjects”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-120">On the **Configure your new project** page, enter **ClassLibraryProjects** in the **Project name** box.</span></span> <span data-ttu-id="2340c-121">然后，选择“创建”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-121">Then, choose **Create**.</span></span>

> [!TIP]
> <span data-ttu-id="2340c-122">你还可以跳过此步骤，并让 Visual Studio 在下一步中创建项目时为你创建该解决方案。</span><span class="sxs-lookup"><span data-stu-id="2340c-122">You can also skip this step and let Visual Studio create the solution for you when you create the project in the next step.</span></span> <span data-ttu-id="2340c-123">在“配置新项目”  页上查找解决方案选项。</span><span class="sxs-lookup"><span data-stu-id="2340c-123">Look for the solution options on the **Configure your new project** page.</span></span>

## <a name="create-a-class-library-project"></a><span data-ttu-id="2340c-124">创建类库项目</span><span class="sxs-lookup"><span data-stu-id="2340c-124">Create a class library project</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[<span data-ttu-id="2340c-125">C#</span><span class="sxs-lookup"><span data-stu-id="2340c-125">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="2340c-126">将名为“StringLibrary”的新 C# .NET Standard 类库项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="2340c-126">Add a new C# .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="2340c-127">在“解决方案资源管理器”  中右键单击解决方案并选择“添加”   > “新建项目”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-127">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="2340c-128">在“创建新项目”  页面上，在搜索框中输入“库”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-128">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="2340c-129">从“语言”列表中选择“C#”  ，然后从“平台”列表中选择“所有平台”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-129">Choose **C#** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="2340c-130">选择“类库 (.NET Standard)”  模板，然后选择“下一步”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-130">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="2340c-131">在“配置新项目”  页面，在“项目名称”  框中输入“StringLibrary”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-131">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="2340c-132">然后，选择“创建”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-132">Then, choose **Create**.</span></span>

1. <span data-ttu-id="2340c-133">请检查以确保库面向 .NET Standard 的正确版本。</span><span class="sxs-lookup"><span data-stu-id="2340c-133">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="2340c-134">右键单击“解决方案资源管理器”  中的库项目，然后选择“属性”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-134">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="2340c-135">“目标框架”  文本框显示项目面向 .NET Standard 2.0。</span><span class="sxs-lookup"><span data-stu-id="2340c-135">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![类库的项目属性](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="2340c-137">将代码窗口中的代码替换为以下代码，并保存文件：</span><span class="sxs-lookup"><span data-stu-id="2340c-137">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   <span data-ttu-id="2340c-138">类库 `UtilityLibraries.StringLibrary`包含一个名为 `StartsWithUpper` 的方法。</span><span class="sxs-lookup"><span data-stu-id="2340c-138">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="2340c-139">此方法会返回 <xref:System.Boolean> 值，以指明当前字符串实例是否以大写字符开头。</span><span class="sxs-lookup"><span data-stu-id="2340c-139">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="2340c-140">Unicode 标准会区分大小写字符。</span><span class="sxs-lookup"><span data-stu-id="2340c-140">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="2340c-141">如果为大写字符，<xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> 方法返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="2340c-141">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="2340c-142">在菜单栏中，选择“生成”   > “生成解决方案”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-142">On the menu bar, select **Build** > **Build Solution**.</span></span>

# <a name="visual-basictabvb"></a>[<span data-ttu-id="2340c-143">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2340c-143">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="2340c-144">将名为“StringLibrary”的新 Visual Basic .NET Standard 类库项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="2340c-144">Add a new Visual Basic .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="2340c-145">在“解决方案资源管理器”  中右键单击解决方案并选择“添加”   > “新建项目”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-145">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="2340c-146">在“创建新项目”  页面上，在搜索框中输入“库”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-146">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="2340c-147">从“语言”列表中选择“Visual Basic”  ，然后从“平台”列表中选择“所有平台”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-147">Choose **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="2340c-148">选择“类库 (.NET Standard)”  模板，然后选择“下一步”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-148">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="2340c-149">在“配置新项目”  页面，在“项目名称”  框中输入“StringLibrary”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-149">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="2340c-150">然后，选择“创建”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-150">Then, choose **Create**.</span></span>

1. <span data-ttu-id="2340c-151">请检查以确保库面向 .NET Standard 的正确版本。</span><span class="sxs-lookup"><span data-stu-id="2340c-151">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="2340c-152">右键单击“解决方案资源管理器”  中的库项目，然后选择“属性”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-152">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="2340c-153">“目标框架”  文本框显示项目面向 .NET Standard 2.0。</span><span class="sxs-lookup"><span data-stu-id="2340c-153">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![类库的项目属性](./media/library-with-visual-studio/vb/library-project-properties.png)

1. <span data-ttu-id="2340c-155">在“属性”  对话框中，清除“根命名空间”  文本框中的文本。</span><span class="sxs-lookup"><span data-stu-id="2340c-155">In the **Properties** dialog, clear the text in the **Root namespace** text box.</span></span> <span data-ttu-id="2340c-156">对于每个项目，Visual Basic 会自动创建一个与项目名称对应的命名空间。</span><span class="sxs-lookup"><span data-stu-id="2340c-156">For each project, Visual Basic automatically creates a namespace that corresponds to the project name.</span></span> <span data-ttu-id="2340c-157">在本教程中，通过使用代码文件中的 [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) 关键字定义顶级命名空间。</span><span class="sxs-lookup"><span data-stu-id="2340c-157">In this tutorial, you define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword in the code file.</span></span>

1. <span data-ttu-id="2340c-158">将代码窗口中的代码替换为以下代码，并保存文件：</span><span class="sxs-lookup"><span data-stu-id="2340c-158">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   <span data-ttu-id="2340c-159">类库 `UtilityLibraries.StringLibrary`包含一个名为 `StartsWithUpper` 的方法。</span><span class="sxs-lookup"><span data-stu-id="2340c-159">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="2340c-160">此方法会返回 <xref:System.Boolean> 值，以指明当前字符串实例是否以大写字符开头。</span><span class="sxs-lookup"><span data-stu-id="2340c-160">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="2340c-161">Unicode 标准会区分大小写字符。</span><span class="sxs-lookup"><span data-stu-id="2340c-161">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="2340c-162">如果为大写字符，<xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> 方法返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="2340c-162">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="2340c-163">在菜单栏中，选择“生成”   > “生成解决方案”  。</span><span class="sxs-lookup"><span data-stu-id="2340c-163">On the menu bar, select **Build** > **Build Solution**.</span></span>

---

   <span data-ttu-id="2340c-164">此项目的编译应该没有错误。</span><span class="sxs-lookup"><span data-stu-id="2340c-164">The project should compile without error.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2340c-165">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2340c-165">Next steps</span></span>

<span data-ttu-id="2340c-166">已成功生成库。</span><span class="sxs-lookup"><span data-stu-id="2340c-166">You've successfully built the library.</span></span> <span data-ttu-id="2340c-167">由于尚未调用库的任何方法，因此还不知道它能否按预期运行。</span><span class="sxs-lookup"><span data-stu-id="2340c-167">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="2340c-168">开发库的下一步是测试库。</span><span class="sxs-lookup"><span data-stu-id="2340c-168">The next step in developing your library is to test it.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="2340c-169">创建单元测试项目</span><span class="sxs-lookup"><span data-stu-id="2340c-169">Create a unit test project</span></span>](testing-library-with-visual-studio.md)
