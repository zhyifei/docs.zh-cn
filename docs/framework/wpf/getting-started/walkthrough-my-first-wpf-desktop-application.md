---
title: 教程：在 Visual Studio 2019 中创建第一个 WPF 应用程序-.NET Framework
ms.date: 09/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
ms.topic: tutorial
ms.custom: vs-dotnet
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c8b7f6f3bdbf3adc7c355e88cfe1f569cc0cb76f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799341"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a><span data-ttu-id="80fc8-102">教程：在 Visual Studio 2019 中创建第一个 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="80fc8-102">Tutorial: Create your first WPF application in Visual Studio 2019</span></span>

<span data-ttu-id="80fc8-103">本文介绍如何开发 Windows Presentation Foundation （WPF）桌面应用程序，该应用程序包括大多数 WPF 应用程序所共有的元素：Extensible Application Markup Language （XAML）标记、代码隐藏、应用程序定义、控件、布局、数据绑定和样式。</span><span class="sxs-lookup"><span data-stu-id="80fc8-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="80fc8-104">若要开发应用程序，请使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="80fc8-104">To develop the application, you'll use Visual Studio.</span></span> 

<span data-ttu-id="80fc8-105">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="80fc8-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="80fc8-106">创建 WPF 项目。</span><span class="sxs-lookup"><span data-stu-id="80fc8-106">Create a WPF project.</span></span>
> - <span data-ttu-id="80fc8-107">使用 XAML 设计应用程序的用户界面（UI）的外观。</span><span class="sxs-lookup"><span data-stu-id="80fc8-107">Use XAML to design the appearance of the application's user interface (UI).</span></span>
> - <span data-ttu-id="80fc8-108">编写代码以生成应用程序的行为。</span><span class="sxs-lookup"><span data-stu-id="80fc8-108">Write code to build the application's behavior.</span></span>
> - <span data-ttu-id="80fc8-109">创建应用程序定义以管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="80fc8-109">Create an application definition to manage the application.</span></span>
> - <span data-ttu-id="80fc8-110">添加控件并创建用于撰写应用程序 UI 的布局。</span><span class="sxs-lookup"><span data-stu-id="80fc8-110">Add controls and create the layout to compose the application UI.</span></span>
> - <span data-ttu-id="80fc8-111">在应用程序的 UI 中创建样式以实现一致的外观。</span><span class="sxs-lookup"><span data-stu-id="80fc8-111">Create styles for a consistent appearance throughout the application's UI.</span></span>
> - <span data-ttu-id="80fc8-112">将 UI 绑定到数据，从数据填充 UI，并使数据和 UI 同步。</span><span class="sxs-lookup"><span data-stu-id="80fc8-112">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="80fc8-113">本教程结束时，将生成一个独立的 Windows 应用程序，允许用户查看所选人员的费用报表。</span><span class="sxs-lookup"><span data-stu-id="80fc8-113">By the end of the tutorial, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="80fc8-114">应用程序由多个承载于浏览器样式窗口中的 WPF 页组成。</span><span class="sxs-lookup"><span data-stu-id="80fc8-114">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="80fc8-115">本教程中使用的示例代码可用于 Visual Basic 和C# [教程 WPF 应用程序示例代码](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)。</span><span class="sxs-lookup"><span data-stu-id="80fc8-115">The sample code that is used in this tutorial is available for both Visual Basic and C# at [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="80fc8-116">您可以使用此页顶部的语言选择器来C#切换与 Visual Basic 的示例代码的代码语言。</span><span class="sxs-lookup"><span data-stu-id="80fc8-116">You can toggle the code language of the sample code between C# and Visual Basic by using the language selector on top of this page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80fc8-117">系统必备</span><span class="sxs-lookup"><span data-stu-id="80fc8-117">Prerequisites</span></span>

- <span data-ttu-id="80fc8-118">安装了 **.net 桌面开发**工作负载的[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 。</span><span class="sxs-lookup"><span data-stu-id="80fc8-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET desktop development** workload installed.</span></span>

   <span data-ttu-id="80fc8-119">有关安装最新版本的 Visual Studio 的详细信息，请参阅[安装 Visual studio](/visualstudio/install/install-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="80fc8-119">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="80fc8-120">创建应用程序项目</span><span class="sxs-lookup"><span data-stu-id="80fc8-120">Create the application project</span></span>

<span data-ttu-id="80fc8-121">第一步是创建应用程序基础结构，其中包括应用程序定义、两页和映像。</span><span class="sxs-lookup"><span data-stu-id="80fc8-121">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="80fc8-122">在 Visual Basic 或 Visual C# 名为创建新的 WPF 应用程序项目 **`ExpenseIt`** :</span><span class="sxs-lookup"><span data-stu-id="80fc8-122">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="80fc8-123">打开 Visual Studio，然后在 "**入门**" 菜单下选择 "**创建新项目**"。</span><span class="sxs-lookup"><span data-stu-id="80fc8-123">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="80fc8-124">此时将打开 "新建**项目**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="80fc8-124">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="80fc8-125">在 "**语言**" 下拉列表中**C#** ，选择或**Visual Basic**。</span><span class="sxs-lookup"><span data-stu-id="80fc8-125">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>
      
   3. <span data-ttu-id="80fc8-126">选择 " **WPF 应用（.NET Framework）** " 模板，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="80fc8-126">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span> 
     
      !["新建项目" 对话框](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)
    
      <span data-ttu-id="80fc8-128">此时将打开 "**配置新项目**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="80fc8-128">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="80fc8-129">输入项目名称 **`ExpenseIt`** ，然后选择**创建**。</span><span class="sxs-lookup"><span data-stu-id="80fc8-129">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      !["配置新项目" 对话框](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="80fc8-131">Visual Studio 将创建项目并打开名为**mainwindow.xaml**的默认应用程序窗口的设计器。</span><span class="sxs-lookup"><span data-stu-id="80fc8-131">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="80fc8-132">打开*Application .xaml* （Visual Basic）或*app.xaml* （C#）。</span><span class="sxs-lookup"><span data-stu-id="80fc8-132">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="80fc8-133">此 XAML 文件定义了 WPF 应用程序和任何应用程序资源。</span><span class="sxs-lookup"><span data-stu-id="80fc8-133">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="80fc8-134">你还可以使用此文件来指定在应用程序启动时自动显示的 UI，在本例中为*mainwindow.xaml。*</span><span class="sxs-lookup"><span data-stu-id="80fc8-134">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="80fc8-135">XAML 中的 Visual Basic 应如下所示：</span><span class="sxs-lookup"><span data-stu-id="80fc8-135">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="80fc8-136">如下所示C#：</span><span class="sxs-lookup"><span data-stu-id="80fc8-136">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="80fc8-137">打开*mainwindow.xaml*。</span><span class="sxs-lookup"><span data-stu-id="80fc8-137">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="80fc8-138">此 XAML 文件是应用程序的主窗口，并显示在页中创建的内容。</span><span class="sxs-lookup"><span data-stu-id="80fc8-138">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="80fc8-139"><xref:System.Windows.Window>类定义窗口的属性，例如其标题、大小或图标，并处理事件，例如关闭或隐藏。</span><span class="sxs-lookup"><span data-stu-id="80fc8-139">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="80fc8-140">将元素更改<xref:System.Windows.Navigation.NavigationWindow>为，如下面的 XAML 所示： <xref:System.Windows.Window></span><span class="sxs-lookup"><span data-stu-id="80fc8-140">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="80fc8-141">此应用根据用户输入导航到不同的内容。</span><span class="sxs-lookup"><span data-stu-id="80fc8-141">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="80fc8-142">这就是主要<xref:System.Windows.Window>需要更改为的<xref:System.Windows.Navigation.NavigationWindow>原因。</span><span class="sxs-lookup"><span data-stu-id="80fc8-142">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="80fc8-143"><xref:System.Windows.Navigation.NavigationWindow>继承的所有属性<xref:System.Windows.Window>。</span><span class="sxs-lookup"><span data-stu-id="80fc8-143"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="80fc8-144">XAML <xref:System.Windows.Navigation.NavigationWindow>文件中的元素创建<xref:System.Windows.Navigation.NavigationWindow>类的实例。</span><span class="sxs-lookup"><span data-stu-id="80fc8-144">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="80fc8-145">有关详细信息，请参阅[导航概述](../app-development/navigation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="80fc8-145">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="80fc8-146">删除<xref:System.Windows.Controls.Grid> 标记<xref:System.Windows.Navigation.NavigationWindow>之间的元素。</span><span class="sxs-lookup"><span data-stu-id="80fc8-146">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="80fc8-147">在<xref:System.Windows.Navigation.NavigationWindow>元素的 XAML 代码中更改以下属性：</span><span class="sxs-lookup"><span data-stu-id="80fc8-147">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="80fc8-148">将属性设置为 "`ExpenseIt`"。 <xref:System.Windows.Window.Title%2A></span><span class="sxs-lookup"><span data-stu-id="80fc8-148">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="80fc8-149"><xref:System.Windows.FrameworkElement.Height%2A>将属性设置为350像素。</span><span class="sxs-lookup"><span data-stu-id="80fc8-149">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="80fc8-150"><xref:System.Windows.FrameworkElement.Width%2A>将属性设置为500像素。</span><span class="sxs-lookup"><span data-stu-id="80fc8-150">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="80fc8-151">XAML 应该如下所示 Visual Basic：</span><span class="sxs-lookup"><span data-stu-id="80fc8-151">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="80fc8-152">并且类似于以下C#内容：</span><span class="sxs-lookup"><span data-stu-id="80fc8-152">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="80fc8-153">打开*mainwindow.xaml*或*MainWindow.xaml.cs*。</span><span class="sxs-lookup"><span data-stu-id="80fc8-153">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="80fc8-154">此文件是一个代码隐藏文件，其中包含处理*mainwindow.xaml*中声明的事件的代码。</span><span class="sxs-lookup"><span data-stu-id="80fc8-154">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="80fc8-155">此文件包含在 XAML 中定义的窗口的分部类。</span><span class="sxs-lookup"><span data-stu-id="80fc8-155">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="80fc8-156">如果使用C#的是，请将`MainWindow`类更改为派生<xref:System.Windows.Navigation.NavigationWindow>自。</span><span class="sxs-lookup"><span data-stu-id="80fc8-156">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="80fc8-157">（在 Visual Basic 中，当你更改 XAML 中的窗口时会自动发生这种情况。）你C#的代码现在应如下所示：</span><span class="sxs-lookup"><span data-stu-id="80fc8-157">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="80fc8-158">向应用程序添加文件</span><span class="sxs-lookup"><span data-stu-id="80fc8-158">Add files to the application</span></span>

<span data-ttu-id="80fc8-159">本部分将向应用程序添加两个页面和一个图像。</span><span class="sxs-lookup"><span data-stu-id="80fc8-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="80fc8-160">将新页面添加到项目中，并将其命名 *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="80fc8-160">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="80fc8-161">在中**解决方案资源管理器**，右键单击 **`ExpenseIt`** 项目节点，然后选择**添加** > **页**。</span><span class="sxs-lookup"><span data-stu-id="80fc8-161">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="80fc8-162">在 "**添加新项**" 对话框中，已选择 "**页（WPF）** 模板"。</span><span class="sxs-lookup"><span data-stu-id="80fc8-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="80fc8-163">输入的名称 **`ExpenseItHome`** ，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="80fc8-163">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="80fc8-164">此页是应用程序启动时显示的第一页。</span><span class="sxs-lookup"><span data-stu-id="80fc8-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="80fc8-165">它将显示要从中进行选择的人员的列表，以便为显示费用报表。</span><span class="sxs-lookup"><span data-stu-id="80fc8-165">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="80fc8-166">打开 *`ExpenseItHome.xaml`* 。</span><span class="sxs-lookup"><span data-stu-id="80fc8-166">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="80fc8-167">将设置`ExpenseIt - Home`为 ""。 <xref:System.Windows.Controls.Page.Title%2A></span><span class="sxs-lookup"><span data-stu-id="80fc8-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="80fc8-168">`DesignWidth`将设置`DesignHeight`为350像素，将设置为500像素。</span><span class="sxs-lookup"><span data-stu-id="80fc8-168">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="80fc8-169">XAML 现在如下 Visual Basic 显示：</span><span class="sxs-lookup"><span data-stu-id="80fc8-169">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="80fc8-170">并且类似于以下C#内容：</span><span class="sxs-lookup"><span data-stu-id="80fc8-170">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="80fc8-171">打开*mainwindow.xaml*。</span><span class="sxs-lookup"><span data-stu-id="80fc8-171">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="80fc8-172">将属性添加<xref:System.Windows.Navigation.NavigationWindow>到元素，并将其设置为`ExpenseItHome.xaml`""。 <xref:System.Windows.Navigation.NavigationWindow.Source%2A></span><span class="sxs-lookup"><span data-stu-id="80fc8-172">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="80fc8-173">这将设置 *`ExpenseItHome.xaml`* 的第一页时打开应用程序启动。</span><span class="sxs-lookup"><span data-stu-id="80fc8-173">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> 

    <span data-ttu-id="80fc8-174">Visual Basic 中的示例 XAML：</span><span class="sxs-lookup"><span data-stu-id="80fc8-174">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="80fc8-175">和 C# 中：</span><span class="sxs-lookup"><span data-stu-id="80fc8-175">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="80fc8-176">您还可以在 "**属性**" 窗口的 "**杂项**" 类别中设置**Source**属性。</span><span class="sxs-lookup"><span data-stu-id="80fc8-176">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![属性窗口中的源属性](./media/properties-source.png)

1. <span data-ttu-id="80fc8-178">向项目中添加另一个新的 WPF 页，并将其命名为*expensereportpage.xaml*：：</span><span class="sxs-lookup"><span data-stu-id="80fc8-178">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="80fc8-179">在中**解决方案资源管理器**，右键单击 **`ExpenseIt`** 项目节点，然后选择**添加** > **页**。</span><span class="sxs-lookup"><span data-stu-id="80fc8-179">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="80fc8-180">在 "**添加新项**" 对话框中，选择 "**页（WPF）** " 模板。</span><span class="sxs-lookup"><span data-stu-id="80fc8-180">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="80fc8-181">输入名称**expensereportpage.xaml**，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="80fc8-181">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="80fc8-182">此页会显示费用报表上选择的人员 **`ExpenseItHome`** 页。</span><span class="sxs-lookup"><span data-stu-id="80fc8-182">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="80fc8-183">打开 *ExpenseReportPage.xaml*。</span><span class="sxs-lookup"><span data-stu-id="80fc8-183">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="80fc8-184">将设置`ExpenseIt - View Expense`为 ""。 <xref:System.Windows.Controls.Page.Title%2A></span><span class="sxs-lookup"><span data-stu-id="80fc8-184">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="80fc8-185">`DesignWidth`将设置`DesignHeight`为350像素，将设置为500像素。</span><span class="sxs-lookup"><span data-stu-id="80fc8-185">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span> 

    <span data-ttu-id="80fc8-186">在 Visual Basic 中， *expensereportpage.xaml*现在如下所示：</span><span class="sxs-lookup"><span data-stu-id="80fc8-186">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="80fc8-187">如下所示C#：</span><span class="sxs-lookup"><span data-stu-id="80fc8-187">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="80fc8-188">打开*expenseithome.xaml*和*expensereportpage.xaml*，或*ExpenseItHome.xaml.cs*和*ExpenseReportPage.xaml.cs*。</span><span class="sxs-lookup"><span data-stu-id="80fc8-188">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="80fc8-189">创建新的页面文件时，Visual Studio 会自动创建其*代码隐藏*文件。</span><span class="sxs-lookup"><span data-stu-id="80fc8-189">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="80fc8-190">这些代码隐藏文件处理响应用户输入的逻辑。</span><span class="sxs-lookup"><span data-stu-id="80fc8-190">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="80fc8-191">你的代码应如以下所示 **`ExpenseItHome`** :</span><span class="sxs-lookup"><span data-stu-id="80fc8-191">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="80fc8-192">对于**expensereportpage.xaml**，如下所示：</span><span class="sxs-lookup"><span data-stu-id="80fc8-192">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="80fc8-193">向项目中添加一个名为 "*水印*" 的图像。</span><span class="sxs-lookup"><span data-stu-id="80fc8-193">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="80fc8-194">你可以创建自己的映像，从示例代码复制文件，或者从[microsoft/WPF 示例](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png)GitHub 存储库获取它。</span><span class="sxs-lookup"><span data-stu-id="80fc8-194">You can create your own image, copy the file from the sample code, or get it from the [microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub repository.</span></span>

    1. <span data-ttu-id="80fc8-195">右键单击项目节点并选择 "**添加** > **现有项**"，或按**Shift**+**Alt**+**A**。</span><span class="sxs-lookup"><span data-stu-id="80fc8-195">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="80fc8-196">在 "**添加现有项**" 对话框中，将 "文件筛选器" 设置为 "**所有文件**或**图像文件**"，浏览到想要使用的图像文件，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="80fc8-196">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="80fc8-197">编译和运行应用程序</span><span class="sxs-lookup"><span data-stu-id="80fc8-197">Build and run the application</span></span>

1. <span data-ttu-id="80fc8-198">若要生成并运行应用程序，请按**F5**或从 "**调试**" 菜单中选择 "**启动调试**"。</span><span class="sxs-lookup"><span data-stu-id="80fc8-198">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="80fc8-199">下图显示了具有<xref:System.Windows.Navigation.NavigationWindow>以下按钮的应用程序：</span><span class="sxs-lookup"><span data-stu-id="80fc8-199">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![生成并运行应用程序。](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="80fc8-201">关闭要返回到 Visual Studio 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="80fc8-201">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="80fc8-202">创建布局</span><span class="sxs-lookup"><span data-stu-id="80fc8-202">Create the layout</span></span>

<span data-ttu-id="80fc8-203">布局提供了放置 UI 元素的有序方式，还可在调整 UI 大小时管理这些元素的大小和位置。</span><span class="sxs-lookup"><span data-stu-id="80fc8-203">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="80fc8-204">通常使用以下布局控件之一来创建布局：</span><span class="sxs-lookup"><span data-stu-id="80fc8-204">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="80fc8-205"><xref:System.Windows.Controls.Canvas>-定义一个区域，可在其中使用相对于画布区域的坐标显式定位子元素。</span><span class="sxs-lookup"><span data-stu-id="80fc8-205"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="80fc8-206"><xref:System.Windows.Controls.DockPanel>-定义一个区域，您可以在其中彼此水平或垂直排列子元素。</span><span class="sxs-lookup"><span data-stu-id="80fc8-206"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="80fc8-207"><xref:System.Windows.Controls.Grid>-定义由列和行组成的灵活的网格区域。</span><span class="sxs-lookup"><span data-stu-id="80fc8-207"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="80fc8-208"><xref:System.Windows.Controls.StackPanel>-将子元素排列到可以水平或垂直方向的单个行中。</span><span class="sxs-lookup"><span data-stu-id="80fc8-208"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="80fc8-209"><xref:System.Windows.Controls.VirtualizingStackPanel>-在水平或垂直方向的单个行上排列和虚拟化内容。</span><span class="sxs-lookup"><span data-stu-id="80fc8-209"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="80fc8-210"><xref:System.Windows.Controls.WrapPanel>-按从左至右的顺序位置定位子元素，在包含框的边缘处将内容分解到下一行。</span><span class="sxs-lookup"><span data-stu-id="80fc8-210"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="80fc8-211">后续排序按从上到下或从右到左的顺序进行，具体取决于 "方向" 属性的值。</span><span class="sxs-lookup"><span data-stu-id="80fc8-211">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="80fc8-212">其中每个布局控件都支持其子元素的特定类型的布局。</span><span class="sxs-lookup"><span data-stu-id="80fc8-212">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="80fc8-213">`ExpenseIt`可以调整页的大小，并且每个页面都具有与其他元素水平和垂直排列的元素。</span><span class="sxs-lookup"><span data-stu-id="80fc8-213">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="80fc8-214">在此示例中， <xref:System.Windows.Controls.Grid>用作应用程序的布局元素。</span><span class="sxs-lookup"><span data-stu-id="80fc8-214">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="80fc8-215">有关<xref:System.Windows.Controls.Panel>元素的详细信息，请参阅[面板概述](../controls/panels-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="80fc8-215">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="80fc8-216">有关布局的详细信息，请参阅[布局](../advanced/layout.md)。</span><span class="sxs-lookup"><span data-stu-id="80fc8-216">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="80fc8-217">在本部分中，您创建的单列的表具有三个行和 10 像素边距通过添加到的列和行定义<xref:System.Windows.Controls.Grid>中 *`ExpenseItHome.xaml`* 。</span><span class="sxs-lookup"><span data-stu-id="80fc8-217">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="80fc8-218">在中 *`ExpenseItHome.xaml`* ，将<xref:System.Windows.FrameworkElement.Margin%2A>属性上的<xref:System.Windows.Controls.Grid>"10,0,10,10"，对应于左侧、 顶部、 右侧和底部边距的元素：</span><span class="sxs-lookup"><span data-stu-id="80fc8-218">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="80fc8-219">您还可以在 "**属性**" 窗口中的 "**布局**" 类别下设置**边距**值：</span><span class="sxs-lookup"><span data-stu-id="80fc8-219">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![属性窗口中的边距值](./media/properties-margin.png)

2. <span data-ttu-id="80fc8-221">在<xref:System.Windows.Controls.Grid>标记之间添加以下 XAML 以创建行和列定义：</span><span class="sxs-lookup"><span data-stu-id="80fc8-221">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="80fc8-222">两行的均设置为<xref:System.Windows.GridLength.Auto%2A>，这意味着根据行中的内容调整行的大小。 <xref:System.Windows.Controls.RowDefinition.Height%2A></span><span class="sxs-lookup"><span data-stu-id="80fc8-222">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="80fc8-223">默认值<xref:System.Windows.Controls.RowDefinition.Height%2A>为<xref:System.Windows.GridUnitType.Star>大小调整，这意味着行高为可用空间的加权比例。</span><span class="sxs-lookup"><span data-stu-id="80fc8-223">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="80fc8-224">例如，如果两个行都具有<xref:System.Windows.Controls.RowDefinition.Height%2A> "\*"，则每个行都具有一半的可用空间。</span><span class="sxs-lookup"><span data-stu-id="80fc8-224">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="80fc8-225">现在<xref:System.Windows.Controls.Grid>应包含以下 XAML：</span><span class="sxs-lookup"><span data-stu-id="80fc8-225">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="80fc8-226">添加控件</span><span class="sxs-lookup"><span data-stu-id="80fc8-226">Add controls</span></span>

<span data-ttu-id="80fc8-227">在本部分中，你将更新主页 UI 以显示人员列表，你可以在其中选择一个人员来显示其费用报表。</span><span class="sxs-lookup"><span data-stu-id="80fc8-227">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="80fc8-228">控件是允许用户与应用程序交互的 UI 对象。</span><span class="sxs-lookup"><span data-stu-id="80fc8-228">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="80fc8-229">有关详细信息，请参阅 [控件](../controls/index.md)。</span><span class="sxs-lookup"><span data-stu-id="80fc8-229">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="80fc8-230">若要创建此 UI，将添加到以下元素 *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="80fc8-230">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="80fc8-231">一个<xref:System.Windows.Controls.ListBox> （适用于用户列表）。</span><span class="sxs-lookup"><span data-stu-id="80fc8-231">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="80fc8-232">一个<xref:System.Windows.Controls.Label> （用于列表标头）。</span><span class="sxs-lookup"><span data-stu-id="80fc8-232">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="80fc8-233">一个<xref:System.Windows.Controls.Button> （单击此项可查看列表中所选人员的费用报表）。</span><span class="sxs-lookup"><span data-stu-id="80fc8-233">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="80fc8-234">每个控件都通过<xref:System.Windows.Controls.Grid> <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>设置附加属性放置在的一行中。</span><span class="sxs-lookup"><span data-stu-id="80fc8-234">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="80fc8-235">有关附加属性的详细信息，请参阅[附加属性概述](../advanced/attached-properties-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="80fc8-235">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="80fc8-236">在 *`ExpenseItHome.xaml`* 中，在<xref:System.Windows.Controls.Grid>标记之间添加以下 XAML：</span><span class="sxs-lookup"><span data-stu-id="80fc8-236">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="80fc8-237">还可以通过将控件从 "**工具箱**" 窗口拖到设计窗口，然后在 "**属性**" 窗口中设置其属性来创建控件。</span><span class="sxs-lookup"><span data-stu-id="80fc8-237">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="80fc8-238">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="80fc8-238">Build and run the application.</span></span>

    <span data-ttu-id="80fc8-239">下图显示了您创建的控件：</span><span class="sxs-lookup"><span data-stu-id="80fc8-239">The following illustration shows the controls you created:</span></span>

![显示名称列表的 ExpenseIt 示例屏幕截图](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="80fc8-241">添加图像和标题</span><span class="sxs-lookup"><span data-stu-id="80fc8-241">Add an image and a title</span></span>

<span data-ttu-id="80fc8-242">在本部分中，将使用图像和页面标题更新主页 UI。</span><span class="sxs-lookup"><span data-stu-id="80fc8-242">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="80fc8-243">在中 *`ExpenseItHome.xaml`* ，添加到另一个列<xref:System.Windows.Controls.Grid.ColumnDefinitions%2A>具有固定<xref:System.Windows.Controls.ColumnDefinition.Width%2A>为 230 像素：</span><span class="sxs-lookup"><span data-stu-id="80fc8-243">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="80fc8-244">向添加另一行<xref:System.Windows.Controls.Grid.RowDefinitions%2A>，总计四行：</span><span class="sxs-lookup"><span data-stu-id="80fc8-244">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="80fc8-245">将控件移动到第二列，方法是<xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>将这三个控件（边框、列表框和按钮）中每个控件的属性设置为1。</span><span class="sxs-lookup"><span data-stu-id="80fc8-245">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="80fc8-246">将每个控件的<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>值向下移动一行，为三个控件中的每一个（边框、列表框和按钮）和 Border 元素递增1。</span><span class="sxs-lookup"><span data-stu-id="80fc8-246">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="80fc8-247">这三个控件的 XAML 现在如下所示：</span><span class="sxs-lookup"><span data-stu-id="80fc8-247">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="80fc8-248">将以下`</Grid>`XAML添加到 <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> 和标记之间的任意位置，将属性设置`<Grid>`为水印 .png 图像文件：</span><span class="sxs-lookup"><span data-stu-id="80fc8-248">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="80fc8-249">在元素之前，添加一个<xref:System.Windows.Controls.Label>具有内容 "查看支出报表" 的。 <xref:System.Windows.Controls.Border></span><span class="sxs-lookup"><span data-stu-id="80fc8-249">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="80fc8-250">此标签是页面的标题。</span><span class="sxs-lookup"><span data-stu-id="80fc8-250">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="80fc8-251">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="80fc8-251">Build and run the application.</span></span>

<span data-ttu-id="80fc8-252">下图显示刚刚添加的内容的结果：</span><span class="sxs-lookup"><span data-stu-id="80fc8-252">The following illustration shows the results of what you just added:</span></span>

![显示新图像背景和页面标题的 ExpenseIt 示例屏幕截图](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="80fc8-254">添加代码以处理事件</span><span class="sxs-lookup"><span data-stu-id="80fc8-254">Add code to handle events</span></span>

1. <span data-ttu-id="80fc8-255">在中 *`ExpenseItHome.xaml`* ，添加<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件处理程序<xref:System.Windows.Controls.Button>元素。</span><span class="sxs-lookup"><span data-stu-id="80fc8-255">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="80fc8-256">有关详细信息，请参阅[如何：创建一个简单的事件](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))处理程序。</span><span class="sxs-lookup"><span data-stu-id="80fc8-256">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="80fc8-257">打开 *`ExpenseItHome.xaml.vb`* 或 *`ExpenseItHome.xaml.cs`* 。</span><span class="sxs-lookup"><span data-stu-id="80fc8-257">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="80fc8-258">将下面的代码添加到`ExpenseItHome`类，以添加按钮单击事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="80fc8-258">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="80fc8-259">该事件处理程序将打开**expensereportpage.xaml**页。</span><span class="sxs-lookup"><span data-stu-id="80fc8-259">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="80fc8-260">创建 Expensereportpage.xaml 的 UI</span><span class="sxs-lookup"><span data-stu-id="80fc8-260">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="80fc8-261">*ExpenseReportPage.xaml*选择的人员显示费用报表 **`ExpenseItHome`** 页。</span><span class="sxs-lookup"><span data-stu-id="80fc8-261">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="80fc8-262">在本部分中，你将为**expensereportpage.xaml**创建 UI。</span><span class="sxs-lookup"><span data-stu-id="80fc8-262">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="80fc8-263">还将向各种 UI 元素添加背景色和填充颜色。</span><span class="sxs-lookup"><span data-stu-id="80fc8-263">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="80fc8-264">打开 *ExpenseReportPage.xaml*。</span><span class="sxs-lookup"><span data-stu-id="80fc8-264">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="80fc8-265">在<xref:System.Windows.Controls.Grid>标记之间添加以下 XAML：</span><span class="sxs-lookup"><span data-stu-id="80fc8-265">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="80fc8-266">此用户界面是类似于 *`ExpenseItHome.xaml`* ，但报表数据显示在<xref:System.Windows.Controls.DataGrid>。</span><span class="sxs-lookup"><span data-stu-id="80fc8-266">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="80fc8-267">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="80fc8-267">Build and run the application.</span></span>

4. <span data-ttu-id="80fc8-268">选择 "**视图**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="80fc8-268">Select the **View** button.</span></span>

    <span data-ttu-id="80fc8-269">出现费用报告页。</span><span class="sxs-lookup"><span data-stu-id="80fc8-269">The expense report page appears.</span></span> <span data-ttu-id="80fc8-270">另请注意，"后退" 导航按钮已启用。</span><span class="sxs-lookup"><span data-stu-id="80fc8-270">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="80fc8-271">下图显示了添加到*expensereportpage.xaml*的 UI 元素。</span><span class="sxs-lookup"><span data-stu-id="80fc8-271">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![ExpenseIt 示例屏幕截图，显示刚刚为 Expensereportpage.xaml 创建的 UI。](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="80fc8-273">样式控件</span><span class="sxs-lookup"><span data-stu-id="80fc8-273">Style controls</span></span>

<span data-ttu-id="80fc8-274">对于 UI 中同一类型的所有元素，各种元素的外观通常是相同的。</span><span class="sxs-lookup"><span data-stu-id="80fc8-274">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="80fc8-275">UI 使用[样式](../controls/styling-and-templating.md)使外观在多个元素中可重用。</span><span class="sxs-lookup"><span data-stu-id="80fc8-275">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="80fc8-276">样式的可重用性有助于简化 XAML 创建和管理。</span><span class="sxs-lookup"><span data-stu-id="80fc8-276">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="80fc8-277">本部分替换在以前步骤中通过样式定义的按元素划分的属性。</span><span class="sxs-lookup"><span data-stu-id="80fc8-277">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="80fc8-278">打开*Application .xaml*或*app.xaml*。</span><span class="sxs-lookup"><span data-stu-id="80fc8-278">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="80fc8-279">在<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>标记之间添加以下 XAML：</span><span class="sxs-lookup"><span data-stu-id="80fc8-279">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="80fc8-280">此 XAML 将添加以下样式：</span><span class="sxs-lookup"><span data-stu-id="80fc8-280">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="80fc8-281">`headerTextStyle`：设置页标题<xref:System.Windows.Controls.Label>的格式。</span><span class="sxs-lookup"><span data-stu-id="80fc8-281">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="80fc8-282">`labelStyle`：设置控件的<xref:System.Windows.Controls.Label>格式。</span><span class="sxs-lookup"><span data-stu-id="80fc8-282">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="80fc8-283">`columnHeaderStyle`：格式化<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>。</span><span class="sxs-lookup"><span data-stu-id="80fc8-283">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="80fc8-284">`listHeaderStyle`：设置列表标头<xref:System.Windows.Controls.Border>控件的格式。</span><span class="sxs-lookup"><span data-stu-id="80fc8-284">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="80fc8-285">`listHeaderTextStyle`：设置列表标头<xref:System.Windows.Controls.Label>的格式。</span><span class="sxs-lookup"><span data-stu-id="80fc8-285">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="80fc8-286">`buttonStyle`：要格式化的<xref:System.Windows.Controls.Button>。 `ExpenseItHome.xaml`</span><span class="sxs-lookup"><span data-stu-id="80fc8-286">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="80fc8-287">请注意，样式是<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>属性元素的资源和子级。</span><span class="sxs-lookup"><span data-stu-id="80fc8-287">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="80fc8-288">在此位置中，这些样式将应用到应用程序中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="80fc8-288">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="80fc8-289">有关在 .NET 应用中使用资源的示例，请参阅[使用应用程序资源](../advanced/how-to-use-application-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="80fc8-289">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="80fc8-290">在中 *`ExpenseItHome.xaml`* ，将为之间的所有内容<xref:System.Windows.Controls.Grid>具有以下 XAML 元素：</span><span class="sxs-lookup"><span data-stu-id="80fc8-290">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="80fc8-291">应用样式会删除和替换定义每个控件外观的属性（如 <xref:System.Windows.VerticalAlignment> 和 <xref:System.Windows.Media.FontFamily> 。</span><span class="sxs-lookup"><span data-stu-id="80fc8-291">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="80fc8-292">例如， `headerTextStyle`将应用于 "查看支出报表" <xref:System.Windows.Controls.Label>。</span><span class="sxs-lookup"><span data-stu-id="80fc8-292">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="80fc8-293">打开 *ExpenseReportPage.xaml*。</span><span class="sxs-lookup"><span data-stu-id="80fc8-293">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="80fc8-294">将<xref:System.Windows.Controls.Grid>元素之间的所有内容替换为以下 XAML：</span><span class="sxs-lookup"><span data-stu-id="80fc8-294">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="80fc8-295">此 XAML 将样式添加到<xref:System.Windows.Controls.Label>和<xref:System.Windows.Controls.Border>元素。</span><span class="sxs-lookup"><span data-stu-id="80fc8-295">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="80fc8-296">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="80fc8-296">Build and run the application.</span></span> <span data-ttu-id="80fc8-297">窗口外观与以前相同。</span><span class="sxs-lookup"><span data-stu-id="80fc8-297">The window appearance is the same as previously.</span></span>

    ![与上一节中的外观相同的 ExpenseIt 示例屏幕快照。](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="80fc8-299">关闭要返回到 Visual Studio 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="80fc8-299">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="80fc8-300">将数据绑定到控件</span><span class="sxs-lookup"><span data-stu-id="80fc8-300">Bind data to a control</span></span>

<span data-ttu-id="80fc8-301">在本部分中，将创建绑定到各种控件的 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="80fc8-301">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="80fc8-302">在中 *`ExpenseItHome.xaml`* ，打开之后<xref:System.Windows.Controls.Grid>元素中，添加以下 XAML 以创建<xref:System.Windows.Data.XmlDataProvider>包含数据的每个用户：</span><span class="sxs-lookup"><span data-stu-id="80fc8-302">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="80fc8-303">数据作为<xref:System.Windows.Controls.Grid>资源创建。</span><span class="sxs-lookup"><span data-stu-id="80fc8-303">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="80fc8-304">通常，此数据将作为文件加载，但为简单起见，数据是以内联方式添加的。</span><span class="sxs-lookup"><span data-stu-id="80fc8-304">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="80fc8-305">在元素中，添加以下`<xref:System.Windows.DataTemplate>`元素，该元素定义如何在<xref:System.Windows.Controls.ListBox>中的`<XmlDataProvider>`元素后显示数据： `<Grid.Resources>`</span><span class="sxs-lookup"><span data-stu-id="80fc8-305">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="80fc8-306">有关数据模板的详细信息，请参阅[数据模板化概述](../data/data-templating-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="80fc8-306">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="80fc8-307">将现有<xref:System.Windows.Controls.ListBox>的替换为以下 XAML：</span><span class="sxs-lookup"><span data-stu-id="80fc8-307">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="80fc8-308">此 XAML 将的<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListBox>属性绑定到数据源，并应用数据模板作为<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>。</span><span class="sxs-lookup"><span data-stu-id="80fc8-308">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="80fc8-309">将数据连接到控件</span><span class="sxs-lookup"><span data-stu-id="80fc8-309">Connect data to controls</span></span>

<span data-ttu-id="80fc8-310">接下来，将添加代码以检索名称上所选 **`ExpenseItHome`** 页上，并将其传递给构造函数的**ExpenseReportPage**。</span><span class="sxs-lookup"><span data-stu-id="80fc8-310">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="80fc8-311">**Expensereportpage.xaml**用传递的项设置其数据上下文，这是在*expensereportpage.xaml*中定义的控件绑定到的内容。</span><span class="sxs-lookup"><span data-stu-id="80fc8-311">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="80fc8-312">打开 *ExpenseReportPage.xaml.vb* 或 *ExpenseReportPage.xaml.cs*。</span><span class="sxs-lookup"><span data-stu-id="80fc8-312">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="80fc8-313">添加获取对象的构造函数，以便传递所选人员的费用报表数据。</span><span class="sxs-lookup"><span data-stu-id="80fc8-313">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="80fc8-314">打开 *`ExpenseItHome.xaml.vb`* 或 *`ExpenseItHome.xaml.cs`* 。</span><span class="sxs-lookup"><span data-stu-id="80fc8-314">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="80fc8-315"><xref:System.Windows.Controls.Primitives.ButtonBase.Click>更改事件处理程序以调用传递所选人员的费用报表数据的新构造函数。</span><span class="sxs-lookup"><span data-stu-id="80fc8-315">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="80fc8-316">数据模板的样式数据</span><span class="sxs-lookup"><span data-stu-id="80fc8-316">Style data with data templates</span></span>

<span data-ttu-id="80fc8-317">在本部分中，将使用数据模板更新数据绑定列表中每个项的 UI。</span><span class="sxs-lookup"><span data-stu-id="80fc8-317">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="80fc8-318">打开 *ExpenseReportPage.xaml*。</span><span class="sxs-lookup"><span data-stu-id="80fc8-318">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="80fc8-319">将 "名称" 和 "部门" <xref:System.Windows.Controls.Label>元素的内容绑定到相应的数据源属性。</span><span class="sxs-lookup"><span data-stu-id="80fc8-319">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="80fc8-320">有关数据绑定的详细信息，请参阅[数据绑定概述](../data/data-binding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="80fc8-320">For more information about data binding, see [Data binding overview](../data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="80fc8-321">在开始<xref:System.Windows.Controls.Grid>元素之后，添加以下数据模板，这些数据模板定义如何显示费用报表数据：</span><span class="sxs-lookup"><span data-stu-id="80fc8-321">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="80fc8-322">将元素替换为<xref:System.Windows.Controls.DataGridTemplateColumn> <xref:System.Windows.Controls.DataGrid>元素下的元素，并将模板应用于这些元素。<xref:System.Windows.Controls.DataGridTextColumn></span><span class="sxs-lookup"><span data-stu-id="80fc8-322">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="80fc8-323">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="80fc8-323">Build and run the application.</span></span>

6. <span data-ttu-id="80fc8-324">选择一个用户，然后选择 "**查看**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="80fc8-324">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="80fc8-325">下图显示了`ExpenseIt`应用程序的两个页面，并应用了控件、布局、样式、数据绑定和数据模板：</span><span class="sxs-lookup"><span data-stu-id="80fc8-325">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![应用的两个页面均显示名称列表和支出报表。](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="80fc8-327">此示例演示了 WPF 的特定功能，并且不遵循安全性、本地化和辅助功能等功能的所有最佳实践。</span><span class="sxs-lookup"><span data-stu-id="80fc8-327">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="80fc8-328">有关 WPF 和 .NET 应用开发最佳做法的全面介绍，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="80fc8-328">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="80fc8-329">辅助功能</span><span class="sxs-lookup"><span data-stu-id="80fc8-329">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
> - [<span data-ttu-id="80fc8-330">安全性</span><span class="sxs-lookup"><span data-stu-id="80fc8-330">Security</span></span>](../security-wpf.md)
> - [<span data-ttu-id="80fc8-331">WPF 全球化和本地化</span><span class="sxs-lookup"><span data-stu-id="80fc8-331">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
> - [<span data-ttu-id="80fc8-332">WPF 性能</span><span class="sxs-lookup"><span data-stu-id="80fc8-332">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="80fc8-333">后续步骤</span><span class="sxs-lookup"><span data-stu-id="80fc8-333">Next steps</span></span>

<span data-ttu-id="80fc8-334">在本演练中，您学习了使用 Windows Presentation Foundation （WPF）创建 UI 的多种方法。</span><span class="sxs-lookup"><span data-stu-id="80fc8-334">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="80fc8-335">现在，你应基本了解数据绑定 .NET 应用的构建基块。</span><span class="sxs-lookup"><span data-stu-id="80fc8-335">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="80fc8-336">有关 WPF 体系结构和编程模型的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="80fc8-336">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="80fc8-337">WPF 体系结构</span><span class="sxs-lookup"><span data-stu-id="80fc8-337">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="80fc8-338">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="80fc8-338">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="80fc8-339">依赖项属性概述</span><span class="sxs-lookup"><span data-stu-id="80fc8-339">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="80fc8-340">布局</span><span class="sxs-lookup"><span data-stu-id="80fc8-340">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="80fc8-341">有关创建应用程序的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="80fc8-341">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="80fc8-342">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="80fc8-342">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="80fc8-343">控件</span><span class="sxs-lookup"><span data-stu-id="80fc8-343">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="80fc8-344">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="80fc8-344">Data binding overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="80fc8-345">图形和多媒体</span><span class="sxs-lookup"><span data-stu-id="80fc8-345">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="80fc8-346">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="80fc8-346">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="80fc8-347">请参阅</span><span class="sxs-lookup"><span data-stu-id="80fc8-347">See also</span></span>

- [<span data-ttu-id="80fc8-348">面板概述</span><span class="sxs-lookup"><span data-stu-id="80fc8-348">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="80fc8-349">数据模板化概述</span><span class="sxs-lookup"><span data-stu-id="80fc8-349">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="80fc8-350">生成 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="80fc8-350">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="80fc8-351">样式和模板</span><span class="sxs-lookup"><span data-stu-id="80fc8-351">Styles and templates</span></span>](../controls/styles-and-templates.md)
