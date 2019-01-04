---
title: 使用 Visual Studio 2017 生成 C# .NET Standard 类库
description: 了解如何使用 Visual Studio 2017 创建 C# .NET Standard 类库。
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: 0c98f8c8fc4847570964d8d4ea8deb221164441d
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168931"
---
# <a name="build-a-net-standard-class-library-with-c-and-the-net-core-sdk-in-visual-studio-2017"></a><span data-ttu-id="1c61a-103">在 Visual Studio 2017 中使用 C# 和 .NET Core SDK 生成 .NET Standard 类库</span><span class="sxs-lookup"><span data-stu-id="1c61a-103">Build a .NET Standard class library with C# and the .NET Core SDK in Visual Studio 2017</span></span>

<span data-ttu-id="1c61a-104">类库定义的是可以由应用程序调用的类型和方法。</span><span class="sxs-lookup"><span data-stu-id="1c61a-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="1c61a-105">借助定目标到 .NET Standard 2.0 的类库，任何支持相应版本 .NET Standard 的 .NET 实现都可以调用库。</span><span class="sxs-lookup"><span data-stu-id="1c61a-105">A class library that targets the .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of the .NET Standard.</span></span> <span data-ttu-id="1c61a-106">完成类库时，可以决定是要将其作为第三方组件进行分布，还是要将其作为与一个或多个应用程序捆绑在一起的组件进行添加。</span><span class="sxs-lookup"><span data-stu-id="1c61a-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="1c61a-107">有关 .NET Standard 版本及其支持的平台列表，请参阅 [.NET Standard](../../standard/net-standard.md)。</span><span class="sxs-lookup"><span data-stu-id="1c61a-107">For a list of the .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="1c61a-108">在本主题中，将创建包含一个字符串处理方法的简单实用工具库。</span><span class="sxs-lookup"><span data-stu-id="1c61a-108">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="1c61a-109">我们将把它作为[扩展方法](../../csharp/programming-guide/classes-and-structs/extension-methods.md)进行实现，这样就可以把它作为 <xref:System.String> 类成员进行调用。</span><span class="sxs-lookup"><span data-stu-id="1c61a-109">You'll implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="creating-a-class-library-solution"></a><span data-ttu-id="1c61a-110">创建类库解决方案</span><span class="sxs-lookup"><span data-stu-id="1c61a-110">Creating a class library solution</span></span>

<span data-ttu-id="1c61a-111">首先为类库项目及其相关项目创建解决方案。</span><span class="sxs-lookup"><span data-stu-id="1c61a-111">Start by creating a solution for your class library project and its related projects.</span></span> <span data-ttu-id="1c61a-112">Visual Studio 解决方案只用作一个或多个项目的容器。</span><span class="sxs-lookup"><span data-stu-id="1c61a-112">A Visual Studio Solution just serves as a container for one or more projects.</span></span> <span data-ttu-id="1c61a-113">若要创建解决方案，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1c61a-113">To create the solution:</span></span>

1. <span data-ttu-id="1c61a-114">在 Visual Studio 菜单栏上，选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="1c61a-114">On the Visual Studio menu bar, choose **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="1c61a-115">在“新建项目”对话框中，展开“其他项目类型”节点，然后选择“Visual Studio 解决方案”。</span><span class="sxs-lookup"><span data-stu-id="1c61a-115">In the **New Project** dialog, expand the **Other Project Types** node, and select **Visual Studio Solutions**.</span></span> <span data-ttu-id="1c61a-116">将解决方案命名为“ClassLibraryProjects”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="1c61a-116">Name the solution "ClassLibraryProjects" and select the **OK** button.</span></span>

   ![“新建项目”对话框，其中突出显示新的空白解决方案](./media/library-with-visual-studio/new-project-dialog.png)

## <a name="creating-the-class-library-project"></a><span data-ttu-id="1c61a-118">创建类库项目</span><span class="sxs-lookup"><span data-stu-id="1c61a-118">Creating the class library project</span></span>

<span data-ttu-id="1c61a-119">创建类库项目：</span><span class="sxs-lookup"><span data-stu-id="1c61a-119">Create your class library project:</span></span>

1. <span data-ttu-id="1c61a-120">在“解决方案资源管理器”中，右键单击“ClassLibraryProjects”解决方案文件，然后从上下文菜单中选择“添加” > “新项目”。</span><span class="sxs-lookup"><span data-stu-id="1c61a-120">In **Solution Explorer**, right-click on the **ClassLibraryProjects** solution file and from the context menu, select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="1c61a-121">在“添加新项目”对话框中，展开“Visual C#”节点，并依次选择“.NET Standard”节点和“类库(.NET Standard)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="1c61a-121">In the **Add New Project** dialog, expand the **Visual C#** node, then select the **.NET Standard** node followed by the **Class Library (.NET Standard)** project template.</span></span> <span data-ttu-id="1c61a-122">在“名称”文本框中，输入项目名称“StringLibrary”。</span><span class="sxs-lookup"><span data-stu-id="1c61a-122">In the **Name** text box, enter "StringLibrary" as the name of the project.</span></span> <span data-ttu-id="1c61a-123">选择“确定”，创建类库项目。</span><span class="sxs-lookup"><span data-stu-id="1c61a-123">Select **OK** to create the class library project.</span></span>

   ![“添加新的库项目”对话框](./media/library-with-visual-studio/add-new-library-project.png)

   <span data-ttu-id="1c61a-125">然后，代码窗口在 Visual Studio 开发环境中打开。</span><span class="sxs-lookup"><span data-stu-id="1c61a-125">The code window then opens in the Visual Studio development environment.</span></span>

   ![显示默认类库模板代码的 Visual Studio 应用程序窗口](./media/library-with-visual-studio/string-library-project.png)

1. <span data-ttu-id="1c61a-127">请检查以确保库定目标到 .NET Standard 的正确版本。</span><span class="sxs-lookup"><span data-stu-id="1c61a-127">Check to make sure that our library targets the correct version of the .NET Standard.</span></span> <span data-ttu-id="1c61a-128">右键单击“解决方案资源管理器”窗口中的库项目，再选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="1c61a-128">Right-click on the library project in the **Solution Explorer** windows, then select **Properties**.</span></span> <span data-ttu-id="1c61a-129">“目标框架”文本框显示定目标到 .NET Standard 2.0。</span><span class="sxs-lookup"><span data-stu-id="1c61a-129">The **Target Framework** text box shows that we're targeting .NET Standard 2.0.</span></span>

   ![类库的项目属性](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="1c61a-131">将代码窗口中的代码替换为以下代码，并保存文件：</span><span class="sxs-lookup"><span data-stu-id="1c61a-131">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   <span data-ttu-id="1c61a-132">类库 `UtilityLibraries.StringLibrary` 包含 `StartsWithUpper` 方法，此方法会返回 <xref:System.Boolean> 值，以指明当前字符串实例是否以大写字符开头。</span><span class="sxs-lookup"><span data-stu-id="1c61a-132">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`, which returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="1c61a-133">Unicode 标准会区分大小写字符。</span><span class="sxs-lookup"><span data-stu-id="1c61a-133">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="1c61a-134">如果为大写字符，<xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> 方法返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="1c61a-134">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="1c61a-135">在菜单栏中，选择“生成” > “生成解决方案”。</span><span class="sxs-lookup"><span data-stu-id="1c61a-135">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="1c61a-136">此项目的编译应该没有错误。</span><span class="sxs-lookup"><span data-stu-id="1c61a-136">The project should compile without error.</span></span>

   ![显示生成成功的输出窗格](./media/library-with-visual-studio/output-pane-successful-build.png)

## <a name="next-step"></a><span data-ttu-id="1c61a-138">下一步</span><span class="sxs-lookup"><span data-stu-id="1c61a-138">Next step</span></span>

<span data-ttu-id="1c61a-139">已成功生成库。</span><span class="sxs-lookup"><span data-stu-id="1c61a-139">You've successfully built the library.</span></span> <span data-ttu-id="1c61a-140">由于尚未调用库的任何方法，因此还不知道它能否按预期运行。</span><span class="sxs-lookup"><span data-stu-id="1c61a-140">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="1c61a-141">开发库的下一步是使用[单元测试项目](testing-library-with-visual-studio.md)测试库。</span><span class="sxs-lookup"><span data-stu-id="1c61a-141">The next step in developing your library is to test it by using a [Unit Test Project](testing-library-with-visual-studio.md).</span></span>