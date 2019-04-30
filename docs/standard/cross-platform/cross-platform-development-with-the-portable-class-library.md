---
title: 使用可移植类库的跨平台开发
ms.date: 09/17/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
author: mairaw
ms.author: mairaw
ms.openlocfilehash: afaa8e118bb21e5c1e4f1c53b1d0d29ca6bb3bf5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62055051"
---
# <a name="cross-platform-development-with-the-portable-class-library"></a><span data-ttu-id="41ec6-102">使用可移植类库的跨平台开发</span><span class="sxs-lookup"><span data-stu-id="41ec6-102">Cross-platform development with the Portable Class Library</span></span>

<span data-ttu-id="41ec6-103">在 Visual Studio 中的可移植类库项目类型可帮助你快速轻松地构建跨平台应用和 Microsoft 平台的库。</span><span class="sxs-lookup"><span data-stu-id="41ec6-103">The Portable Class Library project type in Visual Studio helps you build cross-platform apps and libraries for Microsoft platforms quickly and easily.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

<span data-ttu-id="41ec6-104">可移植类库可以帮助你减少开发和测试代码的时间和成本。</span><span class="sxs-lookup"><span data-stu-id="41ec6-104">Portable class libraries can help you reduce the time and costs of developing and testing code.</span></span> <span data-ttu-id="41ec6-105">使用此项目类型来编写和生成可移植.NET Framework 程序集，然后从面向.NET Framework、 iOS 或 mac。 如多个平台的应用中引用这些程序集</span><span class="sxs-lookup"><span data-stu-id="41ec6-105">Use this project type to write and build portable .NET Framework assemblies, and then reference those assemblies from apps that target multiple platforms such as the .NET Framework, iOS, or Mac.</span></span>

<span data-ttu-id="41ec6-106">即使是在 Visual Studio 中创建可移植类库项目并开始开发它之后，你仍然可以更改目标平台。</span><span class="sxs-lookup"><span data-stu-id="41ec6-106">Even after you create a Portable Class Library project in Visual Studio and start developing it, you can change the target platforms.</span></span> <span data-ttu-id="41ec6-107">Visual Studio 将编译成库与新的程序集，可帮助您找到您需要在代码中进行的更改。</span><span class="sxs-lookup"><span data-stu-id="41ec6-107">Visual Studio compiles your library with the new assemblies, which helps you identify the changes you need to make in your code.</span></span>

## <a name="create-a-portable-class-library-project"></a><span data-ttu-id="41ec6-108">创建可移植类库项目</span><span class="sxs-lookup"><span data-stu-id="41ec6-108">Create a Portable Class Library project</span></span>

<span data-ttu-id="41ec6-109">若要创建可移植类库，请使用 Visual Studio 中提供的模板。</span><span class="sxs-lookup"><span data-stu-id="41ec6-109">To create a Portable Class Library, use the template provided in Visual Studio.</span></span> <span data-ttu-id="41ec6-110">创建新的项目 (**文件** > **新建项目**)，然后在**新建项目**对话框框中，选择您的编程语言 （Visual C# 或 Visual Basic）。</span><span class="sxs-lookup"><span data-stu-id="41ec6-110">Create a new project (**File** > **New Project**), and in the **New Project** dialog box, select your programming language (Visual C# or Visual Basic).</span></span> <span data-ttu-id="41ec6-111">然后，选择**类库 （旧版可移植）** 模板。</span><span class="sxs-lookup"><span data-stu-id="41ec6-111">Then, select the **Class Library (Legacy Portable)** template.</span></span> <span data-ttu-id="41ec6-112">输入你的项目的名称，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="41ec6-112">Enter a name for your project and choose **OK**.</span></span>

<span data-ttu-id="41ec6-113">**添加可移植类库**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="41ec6-113">The **Add Portable Class Library** dialog box appears.</span></span> <span data-ttu-id="41ec6-114">选择两个或多个目标，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="41ec6-114">Choose two or more targets, and then choose **OK**.</span></span>

![在 Visual Studio 中添加可移植库目标](media/add-portable-class-library.png)

## <a name="change-targets"></a><span data-ttu-id="41ec6-116">更改目标</span><span class="sxs-lookup"><span data-stu-id="41ec6-116">Change targets</span></span>

<span data-ttu-id="41ec6-117">在创建时或之后开始开发，可以更改目标平台的可移植类库项目。</span><span class="sxs-lookup"><span data-stu-id="41ec6-117">You can change the target platforms of a portable class library project when you create it or after you’ve started development.</span></span> <span data-ttu-id="41ec6-118">如果你想要在创建你的项目后更改目标**解决方案资源管理器**，打开 （不是解决方案），你可移植类库项目的快捷菜单，然后选择**属性**.</span><span class="sxs-lookup"><span data-stu-id="41ec6-118">If you want to change the targets after you’ve created your project, in **Solution Explorer**, open the shortcut menu for your Portable Class Library project (not the solution), and then choose **Properties**.</span></span> <span data-ttu-id="41ec6-119">在项目属性页上，**库**选项卡将显示你的项目当前针对的平台。</span><span class="sxs-lookup"><span data-stu-id="41ec6-119">On the project properties page, the **Library** tab shows the platforms that your project currently targets.</span></span>

![在 Visual Studio 中的可移植类库的项目属性](media/pcl-project-properties.png)

<span data-ttu-id="41ec6-121">若要添加或删除的目标，请选择**更改**按钮，然后选择和清除相应的复选框。</span><span class="sxs-lookup"><span data-stu-id="41ec6-121">To add or remove targets, choose the **Change** button, and then select and clear the appropriate check boxes.</span></span>

<span data-ttu-id="41ec6-122">在你更改目标时，供你在开发项目时使用的 API 也将发生更改以匹配你的选择。</span><span class="sxs-lookup"><span data-stu-id="41ec6-122">When you change the targets, the APIs that are available to you for developing your project will change to match your selection.</span></span> <span data-ttu-id="41ec6-123">Visual Studio 报告因目标更改而可能导致的错误和警告。</span><span class="sxs-lookup"><span data-stu-id="41ec6-123">Visual Studio reports the errors and warnings that may occur as a result of the targets changing.</span></span>

<span data-ttu-id="41ec6-124">如果您想要评估可移植性的程序集之前在 Visual Studio 中进行更改，可以使用[.NET 可移植性分析器](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)。</span><span class="sxs-lookup"><span data-stu-id="41ec6-124">If you want to evaluate the portability of your assemblies before you make changes in Visual Studio, you can use the [.NET Portability Analyzer](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b).</span></span>

## <a name="supported-types-and-members"></a><span data-ttu-id="41ec6-125">支持的类型和成员</span><span class="sxs-lookup"><span data-stu-id="41ec6-125">Supported types and members</span></span>

<span data-ttu-id="41ec6-126">可移植类库项目中可用的类型和成员受若干兼容性因素的约束：</span><span class="sxs-lookup"><span data-stu-id="41ec6-126">The types and members that are available in Portable Class Library projects are constrained by several compatibility factors:</span></span>

- <span data-ttu-id="41ec6-127">它们必须在所选各目标之间共享。</span><span class="sxs-lookup"><span data-stu-id="41ec6-127">They must be shared across the targets you selected.</span></span>

- <span data-ttu-id="41ec6-128">它们必须在这些目标上具有类似的行为方式。</span><span class="sxs-lookup"><span data-stu-id="41ec6-128">The must behave similarly across those targets.</span></span>

- <span data-ttu-id="41ec6-129">它们不能是要弃用的候选项。</span><span class="sxs-lookup"><span data-stu-id="41ec6-129">They must not be candidates for deprecation.</span></span>

- <span data-ttu-id="41ec6-130">它们必须在可移植环境中有意义，特别是在支持成员不可移植时。</span><span class="sxs-lookup"><span data-stu-id="41ec6-130">They must make sense in a portable environment, especially when supporting members are not portable.</span></span>

<span data-ttu-id="41ec6-131">如果一个成员在可移植类库和所选的目标中受支持，它将会你的 IntelliSense 项目中出现。</span><span class="sxs-lookup"><span data-stu-id="41ec6-131">If a member is supported in the Portable Class Library and for your selected targets, it will appear in your project in IntelliSense.</span></span> <span data-ttu-id="41ec6-132">但是，请记住某一 API 可能在可移植类库中受支持，但你是否可以使用该 API ​​取决于你选择的目标。</span><span class="sxs-lookup"><span data-stu-id="41ec6-132">However, remember that an API may be supported in the Portable Class Library, but whether you can use the API depends on the targets you select.</span></span>

## <a name="api-differences-in-the-portable-class-library"></a><span data-ttu-id="41ec6-133">可移植类库中的 API 差异</span><span class="sxs-lookup"><span data-stu-id="41ec6-133">API differences in the Portable Class Library</span></span>

<span data-ttu-id="41ec6-134">为了使可移植类库程序集在所有支持的平台中都兼容，可移植类库中对部分成员进行了轻微更改。</span><span class="sxs-lookup"><span data-stu-id="41ec6-134">To make Portable Class Library assemblies compatible across all supported platforms, some members have been slightly changed in the Portable Class Library.</span></span>

## <a name="use-the-portable-class-library"></a><span data-ttu-id="41ec6-135">使用可移植类库</span><span class="sxs-lookup"><span data-stu-id="41ec6-135">Use the Portable Class Library</span></span>

<span data-ttu-id="41ec6-136">构建可移植类库项目后，只需从其他项目中引用它即可。</span><span class="sxs-lookup"><span data-stu-id="41ec6-136">After you build your Portable Class Library project, you just reference it from other projects.</span></span> <span data-ttu-id="41ec6-137">可以引用该项目或包含你要访问的类的特定程序集。</span><span class="sxs-lookup"><span data-stu-id="41ec6-137">You can reference either the project or specific assemblies that contain the classes you want to access.</span></span>

<span data-ttu-id="41ec6-138">若要运行引用可移植类库程序集的应用，必须在计算机上安装所需版本（或更高版本）的目标平台。</span><span class="sxs-lookup"><span data-stu-id="41ec6-138">To run an app that references a Portable Class Library assembly, the required version (or later) of the targeted platforms must be installed on your computer.</span></span> <span data-ttu-id="41ec6-139">Visual Studio 包含所有必需的框架，因此你无需进一步修改即可在用来开发应用的计算机上运行该应用。</span><span class="sxs-lookup"><span data-stu-id="41ec6-139">Visual Studio contains all the required frameworks, so you can run the app without further modification on the computer that you used to develop the app.</span></span>

### <a name="deploy-a-universal-windows-app"></a><span data-ttu-id="41ec6-140">部署通用 Windows 应用</span><span class="sxs-lookup"><span data-stu-id="41ec6-140">Deploy a Universal Windows app</span></span>

<span data-ttu-id="41ec6-141">创建通用 Windows 应用时引用可移植类库程序集、 部署应用程序所需的一切尽在应用包和再执行其他步骤所需。</span><span class="sxs-lookup"><span data-stu-id="41ec6-141">When you create a Universal Windows app that references a Portable Class Library assembly, everything you need to deploy the app is included in the app package, and no further steps are required.</span></span>

### <a name="deploy-a-net-framework-app"></a><span data-ttu-id="41ec6-142">部署.NET Framework 应用程序</span><span class="sxs-lookup"><span data-stu-id="41ec6-142">Deploy a .NET Framework app</span></span>

<span data-ttu-id="41ec6-143">部署引用可移植类库程序集的 .NET Framework 应用时，你必须指定一个对 .NET Framework 正确版本的依赖项。</span><span class="sxs-lookup"><span data-stu-id="41ec6-143">When you deploy a .NET Framework app that references a Portable Class Library assembly, you must specify a dependency on the correct version of the .NET Framework.</span></span> <span data-ttu-id="41ec6-144">通过指定此依赖项，可确保与你的应用程序一起安装所需的版本。</span><span class="sxs-lookup"><span data-stu-id="41ec6-144">By specifying this dependency, you ensure that the required version is installed with your app.</span></span>

- <span data-ttu-id="41ec6-145">若要创建 ClickOnce 部署的依赖项：在中**解决方案资源管理器**，选择想要发布的项目的项目节点。</span><span class="sxs-lookup"><span data-stu-id="41ec6-145">To create a dependency with ClickOnce deployment: In **Solution Explorer**, choose the project node for the project you want to publish.</span></span> <span data-ttu-id="41ec6-146">（这是引用了可移植类库项目的项目）在菜单栏上依次选择**项目** > **属性**，然后选择**发布**选项卡。上**发布**页上，选择**先决条件**。</span><span class="sxs-lookup"><span data-stu-id="41ec6-146">(This is the project that references the Portable Class Library project.) On the menu bar, choose **Project** > **Properties**, and then choose the **Publish** tab. On the **Publish** page, choose **Prerequisites**.</span></span> <span data-ttu-id="41ec6-147">选择所需 .NET Framework 版本作为系统必备组件。</span><span class="sxs-lookup"><span data-stu-id="41ec6-147">Select the required .NET Framework version as a prerequisite.</span></span>

- <span data-ttu-id="41ec6-148">若要创建安装项目的依赖项：在中**解决方案资源管理器**，选择安装项目。</span><span class="sxs-lookup"><span data-stu-id="41ec6-148">To create a dependency with a setup project: In **Solution Explorer**, choose the setup project.</span></span> <span data-ttu-id="41ec6-149">在菜单栏上依次选择**项目** > **属性** > **先决条件**。</span><span class="sxs-lookup"><span data-stu-id="41ec6-149">On the menu bar, choose **Project** > **Properties** > **Prerequisites**.</span></span> <span data-ttu-id="41ec6-150">选择所需 .NET Framework 版本作为系统必备组件。</span><span class="sxs-lookup"><span data-stu-id="41ec6-150">Select the required .NET Framework version as a prerequisite.</span></span>

<span data-ttu-id="41ec6-151">有关部署.NET Framework 应用程序的详细信息，请参阅[开发人员部署指南](../../../docs/framework/deployment/deployment-guide-for-developers.md)。</span><span class="sxs-lookup"><span data-stu-id="41ec6-151">For more information about deploying .NET Framework apps, see [Deployment Guide for Developers](../../../docs/framework/deployment/deployment-guide-for-developers.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="41ec6-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="41ec6-152">See also</span></span>

- [<span data-ttu-id="41ec6-153">将可移植类库与 MVVM 配合使用</span><span class="sxs-lookup"><span data-stu-id="41ec6-153">Using Portable Class Library with MVVM</span></span>](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md)
- [<span data-ttu-id="41ec6-154">面向多个平台的库的应用资源</span><span class="sxs-lookup"><span data-stu-id="41ec6-154">App Resources for Libraries That Target Multiple Platforms</span></span>](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md)
- [<span data-ttu-id="41ec6-155">.NET 可移植性分析器</span><span class="sxs-lookup"><span data-stu-id="41ec6-155">.NET Portability Analyzer</span></span>](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [<span data-ttu-id="41ec6-156">.NET Framework 对 Windows 应用商店应用和 Windows 运行时的支持情况</span><span class="sxs-lookup"><span data-stu-id="41ec6-156">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
- [<span data-ttu-id="41ec6-157">部署</span><span class="sxs-lookup"><span data-stu-id="41ec6-157">Deployment</span></span>](../../../docs/framework/deployment/net-framework-applications.md)
