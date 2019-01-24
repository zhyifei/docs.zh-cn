---
title: 在 Visual Studio 2017 中生成 Visual Basic .NET Standard 类库
description: 了解如何使用 Visual Studio 2017 生成以 Visual Basic 编写的 .NET Standard 类库
author: rpetrusha
ms.author: ronpet
ms.date: 08/07/2017
dev_langs:
- vb
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: 1fddbfd84164a95505cff1783e241ea9001231f5
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362036"
---
# <a name="build-a-net-standard-library-with-visual-basic-and-the-net-core-sdk-in-visual-studio-2017"></a><span data-ttu-id="dd416-103">在 Visual Studio 2017 中使用 Visual Basic 和 .NET Core SDK 生成 .NET Standard 库</span><span class="sxs-lookup"><span data-stu-id="dd416-103">Build a .NET Standard library with Visual Basic and the .NET Core SDK in Visual Studio 2017</span></span>

<span data-ttu-id="dd416-104">类库定义的是可以由应用程序调用的类型和方法。</span><span class="sxs-lookup"><span data-stu-id="dd416-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="dd416-105">借助定目标到 .NET Standard 2.0 的类库，任何支持相应版本 .NET Standard 的 .NET 实现都可以调用库。</span><span class="sxs-lookup"><span data-stu-id="dd416-105">A class library that targets the .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of the .NET Standard.</span></span> <span data-ttu-id="dd416-106">完成类库时，可以决定是要将其作为第三方组件进行分布，还是要将其作为与一个或多个应用程序捆绑在一起的组件进行添加。</span><span class="sxs-lookup"><span data-stu-id="dd416-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="dd416-107">有关 .NET Standard 版本及其支持的平台列表，请参阅 [.NET Standard](../../standard/net-standard.md)。</span><span class="sxs-lookup"><span data-stu-id="dd416-107">For a list of the .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="dd416-108">在本主题中，将创建包含一个字符串处理方法的简单实用工具库。</span><span class="sxs-lookup"><span data-stu-id="dd416-108">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="dd416-109">我们将把它作为[扩展方法](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)进行实现，这样就可以把它作为 <xref:System.String> 类成员进行调用。</span><span class="sxs-lookup"><span data-stu-id="dd416-109">You'll implement it as an [extension method](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="creating-a-class-library-solution"></a><span data-ttu-id="dd416-110">创建类库解决方案</span><span class="sxs-lookup"><span data-stu-id="dd416-110">Creating a class library solution</span></span>

<span data-ttu-id="dd416-111">首先为类库项目及其相关项目创建解决方案。</span><span class="sxs-lookup"><span data-stu-id="dd416-111">Start by creating a solution for your class library project and its related projects.</span></span> <span data-ttu-id="dd416-112">Visual Studio 解决方案只用作一个或多个项目的容器。</span><span class="sxs-lookup"><span data-stu-id="dd416-112">A Visual Studio Solution just serves as a container for one or more projects.</span></span> <span data-ttu-id="dd416-113">若要创建解决方案，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dd416-113">To create the solution:</span></span>

1. <span data-ttu-id="dd416-114">在 Visual Studio 菜单栏上，选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="dd416-114">On the Visual Studio menu bar, choose **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="dd416-115">在“新建项目”对话框中，展开“其他项目类型”节点，然后选择“Visual Studio 解决方案”。</span><span class="sxs-lookup"><span data-stu-id="dd416-115">In the **New Project** dialog, expand the **Other Project Types** node, and select **Visual Studio Solutions**.</span></span> <span data-ttu-id="dd416-116">将解决方案命名为“ClassLibraryProjects”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="dd416-116">Name the solution "ClassLibraryProjects" and select the **OK** button.</span></span>

   ![Visual Studio“新建测试项目”对话框](./media/library-with-visual-studio/new-project-dialog.png)

## <a name="creating-the-class-library-project"></a><span data-ttu-id="dd416-118">创建类库项目</span><span class="sxs-lookup"><span data-stu-id="dd416-118">Creating the class library project</span></span>

<span data-ttu-id="dd416-119">创建类库项目：</span><span class="sxs-lookup"><span data-stu-id="dd416-119">Create your class library project:</span></span>

1. <span data-ttu-id="dd416-120">在“解决方案资源管理器”中，右键单击“ClassLibraryProjects”解决方案文件，然后从上下文菜单中选择“添加” > “新项目”。</span><span class="sxs-lookup"><span data-stu-id="dd416-120">In **Solution Explorer**, right-click on the **ClassLibraryProjects** solution file and from the context menu, select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="dd416-121">在“添加新项目”对话框中，展开“Visual Basic”节点，并依次选择“.NET Standard”节点和“类库(.NET Standard)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="dd416-121">In the **Add New Project** dialog, expand the **Visual Basic** node, then select the **.NET Standard** node followed by the **Class Library (.NET Standard)** project template.</span></span> <span data-ttu-id="dd416-122">在“名称”文本框中，输入项目名称“StringLibrary”。</span><span class="sxs-lookup"><span data-stu-id="dd416-122">In the **Name** text box, enter "StringLibrary" as the name of the project.</span></span> <span data-ttu-id="dd416-123">选择“确定”，创建类库项目。</span><span class="sxs-lookup"><span data-stu-id="dd416-123">Select **OK** to create the class library project.</span></span>

   ![Visual Studio“添加新的库项目”对话框](./media/vb-library-with-visual-studio/create-new-library-project.png)

   <span data-ttu-id="dd416-125">然后，代码窗口在 Visual Studio 开发环境中打开。</span><span class="sxs-lookup"><span data-stu-id="dd416-125">The code window then opens in the Visual Studio development environment.</span></span> 
 
   ![显示默认类库模板代码的 Visual Studio 应用程序窗口](./media/vb-library-with-visual-studio/visual-studio-library.png)

1. <span data-ttu-id="dd416-127">请检查以确保库定目标到 .NET Standard 的正确版本。</span><span class="sxs-lookup"><span data-stu-id="dd416-127">Check to make sure that the library targets the correct version of the .NET Standard.</span></span> <span data-ttu-id="dd416-128">右键单击“解决方案资源管理器”窗口中的库项目，再选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="dd416-128">Right-click on the library project in the **Solution Explorer** windows, then select **Properties**.</span></span> <span data-ttu-id="dd416-129">“目标框架”文本框显示定目标到 .NET Standard 2.0。</span><span class="sxs-lookup"><span data-stu-id="dd416-129">The **Target Framework** text box shows that we're targeting .NET Standard 2.0.</span></span>

   ![类库的项目属性](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="dd416-131">另外，在“属性”对话框中，清除“根命名空间”文本框中的文本。</span><span class="sxs-lookup"><span data-stu-id="dd416-131">Also in the **Properties** dialog, clear the text in the **Root namespace** text box.</span></span> <span data-ttu-id="dd416-132">对于每个项目，Visual Basic 会自动创建与项目名称对应的命名空间，在源代码文件中定义的任何命名空间都是相应命名空间的父级。</span><span class="sxs-lookup"><span data-stu-id="dd416-132">For each project, Visual Basic automatically creates a namespace that corresponds to the project name, and any namespaces defined in source code files are parents of that namespace.</span></span> <span data-ttu-id="dd416-133">我们要使用 [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) 关键字来定义顶级命名空间。</span><span class="sxs-lookup"><span data-stu-id="dd416-133">We want to define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword.</span></span>
  
1. <span data-ttu-id="dd416-134">将代码窗口中的代码替换为以下代码，并保存文件：</span><span class="sxs-lookup"><span data-stu-id="dd416-134">Replace the code in the code window with the following code and save the file:</span></span>

  [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   <span data-ttu-id="dd416-135">类库 `UtilityLibraries.StringLibrary` 包含 `StartsWithUpper` 方法，此方法会返回 <xref:System.Boolean> 值，以指明当前字符串实例是否以大写字符开头。</span><span class="sxs-lookup"><span data-stu-id="dd416-135">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`, which returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="dd416-136">Unicode 标准会区分大小写字符。</span><span class="sxs-lookup"><span data-stu-id="dd416-136">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="dd416-137">如果为大写字符，<xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> 方法返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="dd416-137">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="dd416-138">在菜单栏中，选择“生成” > “生成解决方案”。</span><span class="sxs-lookup"><span data-stu-id="dd416-138">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="dd416-139">此项目的编译应该没有错误。</span><span class="sxs-lookup"><span data-stu-id="dd416-139">The project should compile without error.</span></span>

   ![显示生成成功的输出窗格](./media/library-with-visual-studio/output-pane-successful-build.png)



## <a name="next-step"></a><span data-ttu-id="dd416-141">下一步</span><span class="sxs-lookup"><span data-stu-id="dd416-141">Next step</span></span>

<span data-ttu-id="dd416-142">已成功生成库。</span><span class="sxs-lookup"><span data-stu-id="dd416-142">You've successfully built the library.</span></span> <span data-ttu-id="dd416-143">由于尚未调用库的任何方法，因此还不知道它能否按预期运行。</span><span class="sxs-lookup"><span data-stu-id="dd416-143">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="dd416-144">开发库的下一步是使用[单元测试项目](testing-library-with-visual-studio.md)测试库。</span><span class="sxs-lookup"><span data-stu-id="dd416-144">The next step in developing your library is to test it by using a [Unit Test Project](testing-library-with-visual-studio.md).</span></span>
