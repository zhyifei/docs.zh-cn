---
title: 在 Visual Studio 中创建一个 WPF 应用程序
ms.date: 03/20/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
author: mairaw
ms.author: mairaw
ms.custom: vs-dotnet
ms.openlocfilehash: 9d0abd18b2242ab21e8a915caac1ff9e3216acd0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617271"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="c6705-102">演练：我的第一个 WPF 桌面应用程序</span><span class="sxs-lookup"><span data-stu-id="c6705-102">Walkthrough: My first WPF desktop application</span></span>

<span data-ttu-id="c6705-103">本文介绍如何开发包括元素所共有的大多数 WPF 应用程序的 Windows Presentation Foundation (WPF) 桌面应用程序：Extensible Application Markup Language (XAML) 标记、 代码隐藏、 应用程序定义、 控件、 布局、 数据绑定和样式。</span><span class="sxs-lookup"><span data-stu-id="c6705-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="c6705-104">若要开发应用程序，您将使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="c6705-104">To develop the application, you'll use Visual Studio.</span></span> 

<span data-ttu-id="c6705-105">本演练包含以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c6705-105">This walkthrough includes the following steps:</span></span>

- <span data-ttu-id="c6705-106">使用 XAML 来设计应用程序的用户界面 (UI) 的外观。</span><span class="sxs-lookup"><span data-stu-id="c6705-106">Use XAML to design the appearance of the application's user interface (UI).</span></span>

- <span data-ttu-id="c6705-107">编写代码以生成应用程序的行为。</span><span class="sxs-lookup"><span data-stu-id="c6705-107">Write code to build the application's behavior.</span></span>

- <span data-ttu-id="c6705-108">创建应用程序定义管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="c6705-108">Create an application definition to manage the application.</span></span>

- <span data-ttu-id="c6705-109">将控件添加和创建布局以构成应用程序 UI。</span><span class="sxs-lookup"><span data-stu-id="c6705-109">Add controls and create the layout to compose the application UI.</span></span>

- <span data-ttu-id="c6705-110">创建应用程序的 UI 具有一致外观的样式。</span><span class="sxs-lookup"><span data-stu-id="c6705-110">Create styles for a consistent appearance throughout the application's UI.</span></span>

- <span data-ttu-id="c6705-111">绑定到数据，来填充数据从 UI 并保留数据和 UI 同步的用户界面。</span><span class="sxs-lookup"><span data-stu-id="c6705-111">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="c6705-112">本演练结束时，你将生成独立的 Windows 应用程序，允许用户查看所选人员的费用报表。</span><span class="sxs-lookup"><span data-stu-id="c6705-112">By the end of the walkthrough, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="c6705-113">应用程序的托管在浏览器样式的窗口中的多个 WPF 页面组成。</span><span class="sxs-lookup"><span data-stu-id="c6705-113">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="c6705-114">用于生成此演练的示例代码是适用于这两个 Visual Basic 和C#处[演练 WPF 应用程序示例代码](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)。</span><span class="sxs-lookup"><span data-stu-id="c6705-114">The sample code that is used to build this walkthrough is available for both Visual Basic and C# at [Walkthrough WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="c6705-115">您可以切换之间的示例代码的代码语言C#和使用 Visual Basic **\< />** 这篇文章右上角的下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c6705-115">You can toggle the code language of the sample code between C# and Visual Basic by using the **\</>** drop-down on the upper right side of this article.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c6705-116">系统必备</span><span class="sxs-lookup"><span data-stu-id="c6705-116">Prerequisites</span></span>

- <span data-ttu-id="c6705-117">Visual Studio 2017 或更高版本</span><span class="sxs-lookup"><span data-stu-id="c6705-117">Visual Studio 2017 or later</span></span>

   <span data-ttu-id="c6705-118">有关安装 Visual Studio 的最新版本的详细信息，请参阅[安装 Visual Studio](/visualstudio/install/install-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="c6705-118">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span> <span data-ttu-id="c6705-119">本文使用 Visual Studio 2019。</span><span class="sxs-lookup"><span data-stu-id="c6705-119">This article uses Visual Studio 2019.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="c6705-120">创建应用程序项目</span><span class="sxs-lookup"><span data-stu-id="c6705-120">Create the application project</span></span>

<span data-ttu-id="c6705-121">第一步是创建应用程序基础结构，其中包括应用程序定义，两个页面和一个图像。</span><span class="sxs-lookup"><span data-stu-id="c6705-121">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="c6705-122">在 Visual Basic 或 Visual C# 名为创建新的 WPF 应用程序项目 **`ExpenseIt`**:</span><span class="sxs-lookup"><span data-stu-id="c6705-122">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="c6705-123">打开 Visual Studio 并选择**文件** > **新建** > **项目**。</span><span class="sxs-lookup"><span data-stu-id="c6705-123">Open Visual Studio and select **File** > **New** > **Project**.</span></span>

      <span data-ttu-id="c6705-124">**创建一个新项目**对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="c6705-124">The **Create a new project** dialog opens.</span></span>

      ![创建新项目对话框](./media/gettingstartedfigure0a.png)

   2. <span data-ttu-id="c6705-126">在中**语言**下拉列表中，选择**C#** 或**Visual Basic**。</span><span class="sxs-lookup"><span data-stu-id="c6705-126">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>

   3. <span data-ttu-id="c6705-127">选择**WPF 应用 (.NET Framework)** 模板，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c6705-127">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span> 
    
   4. <span data-ttu-id="c6705-128">选择**创建一个新项目**。</span><span class="sxs-lookup"><span data-stu-id="c6705-128">Select **Create a new project**.</span></span>

      <span data-ttu-id="c6705-129">**配置新项目**对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="c6705-129">The **Configure a new project** dialog opens.</span></span>

      ![配置新项目对话框](./media/gettingstartedfigure0c.png)

   5. <span data-ttu-id="c6705-131">输入项目名称**`ExpenseIt`** ，然后选择**创建**。</span><span class="sxs-lookup"><span data-stu-id="c6705-131">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      <span data-ttu-id="c6705-132">Visual Studio 创建项目并打开名为的默认应用程序窗口的设计器**MainWindow.xaml**。</span><span class="sxs-lookup"><span data-stu-id="c6705-132">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="c6705-133">打开*Application.xaml* (Visual Basic) 或*App.xaml* (C#)。</span><span class="sxs-lookup"><span data-stu-id="c6705-133">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="c6705-134">此 XAML 文件定义 WPF 应用程序和任何应用程序资源。</span><span class="sxs-lookup"><span data-stu-id="c6705-134">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="c6705-135">此外使用此文件来指定 UI 中，在这种情况下*MainWindow.xaml*，应用程序启动时自动显示。</span><span class="sxs-lookup"><span data-stu-id="c6705-135">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="c6705-136">在 XAML 应如下所示在 Visual Basic 中所示：</span><span class="sxs-lookup"><span data-stu-id="c6705-136">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="c6705-137">和类似中的以下C#:</span><span class="sxs-lookup"><span data-stu-id="c6705-137">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="c6705-138">打开*MainWindow.xaml*。</span><span class="sxs-lookup"><span data-stu-id="c6705-138">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="c6705-139">此 XAML 文件是你的应用程序的主窗口，并显示在页面中创建的内容。</span><span class="sxs-lookup"><span data-stu-id="c6705-139">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="c6705-140"><xref:System.Windows.Window>类定义的属性窗口中，例如其标题、 大小或图标，并处理事件，例如关闭或隐藏。</span><span class="sxs-lookup"><span data-stu-id="c6705-140">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="c6705-141">更改<xref:System.Windows.Window>元素<xref:System.Windows.Navigation.NavigationWindow>，如以下 XAML 所示：</span><span class="sxs-lookup"><span data-stu-id="c6705-141">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="c6705-142">此应用程序中导航到不同的内容，具体取决于用户输入。</span><span class="sxs-lookup"><span data-stu-id="c6705-142">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="c6705-143">这就是为什么主要<xref:System.Windows.Window>需要更改为<xref:System.Windows.Navigation.NavigationWindow>。</span><span class="sxs-lookup"><span data-stu-id="c6705-143">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="c6705-144"><xref:System.Windows.Navigation.NavigationWindow> 继承的所有属性<xref:System.Windows.Window>。</span><span class="sxs-lookup"><span data-stu-id="c6705-144"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="c6705-145"><xref:System.Windows.Navigation.NavigationWindow> XAML 文件中的元素创建的实例<xref:System.Windows.Navigation.NavigationWindow>类。</span><span class="sxs-lookup"><span data-stu-id="c6705-145">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="c6705-146">有关详细信息，请参阅[导航概述](../app-development/navigation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c6705-146">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="c6705-147">删除<xref:System.Windows.Controls.Grid>元素从之间<xref:System.Windows.Navigation.NavigationWindow>标记。</span><span class="sxs-lookup"><span data-stu-id="c6705-147">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="c6705-148">更改下列属性的 XAML 代码中<xref:System.Windows.Navigation.NavigationWindow>元素：</span><span class="sxs-lookup"><span data-stu-id="c6705-148">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="c6705-149">设置<xref:System.Windows.Window.Title%2A>属性设置为"`ExpenseIt`"。</span><span class="sxs-lookup"><span data-stu-id="c6705-149">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="c6705-150">设置<xref:System.Windows.FrameworkElement.Height%2A>属性设置为 350 像素。</span><span class="sxs-lookup"><span data-stu-id="c6705-150">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="c6705-151">设置<xref:System.Windows.FrameworkElement.Width%2A>属性设置为 500 像素。</span><span class="sxs-lookup"><span data-stu-id="c6705-151">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="c6705-152">在 XAML 应如下所示适用于 Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="c6705-152">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="c6705-153">并如下所示的C#:</span><span class="sxs-lookup"><span data-stu-id="c6705-153">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="c6705-154">打开*MainWindow.xaml.vb*或*MainWindow.xaml.cs*。</span><span class="sxs-lookup"><span data-stu-id="c6705-154">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="c6705-155">此文件是包含代码来处理中声明的事件的代码隐藏文件*MainWindow.xaml*。</span><span class="sxs-lookup"><span data-stu-id="c6705-155">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="c6705-156">此文件包含在 XAML 中定义的窗口的分部类。</span><span class="sxs-lookup"><span data-stu-id="c6705-156">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="c6705-157">如果您使用的C#，更改`MainWindow`类派生自<xref:System.Windows.Navigation.NavigationWindow>。</span><span class="sxs-lookup"><span data-stu-id="c6705-157">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="c6705-158">（在 Visual Basic 中，自动发生此情况更改 XAML 中的窗口。）在C#代码现在应如下所示：</span><span class="sxs-lookup"><span data-stu-id="c6705-158">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="c6705-159">将文件添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="c6705-159">Add files to the application</span></span>

<span data-ttu-id="c6705-160">本部分将向应用程序添加两个页面和一个图像。</span><span class="sxs-lookup"><span data-stu-id="c6705-160">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="c6705-161">将新页面添加到项目中，并将其命名*`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="c6705-161">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="c6705-162">在中**解决方案资源管理器**，右键单击 **`ExpenseIt`** 项目节点，然后选择**添加** > **页**。</span><span class="sxs-lookup"><span data-stu-id="c6705-162">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="c6705-163">在中**添加新项**对话框中，**页面 (WPF)** 尚未选择模板。</span><span class="sxs-lookup"><span data-stu-id="c6705-163">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="c6705-164">输入的名称 **`ExpenseItHome`** ，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="c6705-164">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="c6705-165">此页是应用程序启动时显示的第一页。</span><span class="sxs-lookup"><span data-stu-id="c6705-165">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="c6705-166">它将显示要从中，以查看其费用报表的人员列表。</span><span class="sxs-lookup"><span data-stu-id="c6705-166">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="c6705-167">打开 *`ExpenseItHome.xaml`* 。</span><span class="sxs-lookup"><span data-stu-id="c6705-167">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="c6705-168">设置<xref:System.Windows.Controls.Page.Title%2A>到"`ExpenseIt - Home`"。</span><span class="sxs-lookup"><span data-stu-id="c6705-168">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="c6705-169">设置`DesignHeight`和`DesignWidth`元素值为 300 像素。</span><span class="sxs-lookup"><span data-stu-id="c6705-169">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="c6705-170">XAML 现在将出现，如下所示的 Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="c6705-170">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="c6705-171">并如下所示的C#:</span><span class="sxs-lookup"><span data-stu-id="c6705-171">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="c6705-172">打开*MainWindow.xaml*。</span><span class="sxs-lookup"><span data-stu-id="c6705-172">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="c6705-173">添加<xref:System.Windows.Navigation.NavigationWindow.Source%2A>属性设置为<xref:System.Windows.Navigation.NavigationWindow>元素并将其设置为"`ExpenseItHome.xaml`"。</span><span class="sxs-lookup"><span data-stu-id="c6705-173">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="c6705-174">这将设置 *`ExpenseItHome.xaml`* 的第一页时打开应用程序启动。</span><span class="sxs-lookup"><span data-stu-id="c6705-174">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> 

    <span data-ttu-id="c6705-175">在 Visual Basic 中的 XAML 的示例：</span><span class="sxs-lookup"><span data-stu-id="c6705-175">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="c6705-176">和 C# 中：</span><span class="sxs-lookup"><span data-stu-id="c6705-176">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="c6705-177">您还可以设置**源**属性中的**杂项**类别**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="c6705-177">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![在属性窗口中的源属性](./media/properties-source.png)

1. <span data-ttu-id="c6705-179">将另一个新的 WPF 页添加到项目中，并将其命名*ExpenseReportPage.xaml*::</span><span class="sxs-lookup"><span data-stu-id="c6705-179">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="c6705-180">在中**解决方案资源管理器**，右键单击 **`ExpenseIt`** 项目节点，然后选择**添加** > **页**。</span><span class="sxs-lookup"><span data-stu-id="c6705-180">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="c6705-181">在中**添加新项**对话框中，选择**页面 (WPF)** 模板。</span><span class="sxs-lookup"><span data-stu-id="c6705-181">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="c6705-182">输入的名称**ExpenseReportPage**，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="c6705-182">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="c6705-183">此页会显示费用报表上选择的人员 **`ExpenseItHome`** 页。</span><span class="sxs-lookup"><span data-stu-id="c6705-183">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="c6705-184">打开 *ExpenseReportPage.xaml*。</span><span class="sxs-lookup"><span data-stu-id="c6705-184">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="c6705-185">设置<xref:System.Windows.Controls.Page.Title%2A>到"`ExpenseIt - View Expense`"。</span><span class="sxs-lookup"><span data-stu-id="c6705-185">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="c6705-186">设置`DesignHeight`和`DesignWidth`元素值为 300 像素。</span><span class="sxs-lookup"><span data-stu-id="c6705-186">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="c6705-187">*ExpenseReportPage.xaml*现在如下所示在 Visual Basic 中：</span><span class="sxs-lookup"><span data-stu-id="c6705-187">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="c6705-188">和类似中的以下C#:</span><span class="sxs-lookup"><span data-stu-id="c6705-188">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="c6705-189">打开*ExpenseItHome.xaml.vb*并*ExpenseReportPage.xaml.vb*，或*ExpenseItHome.xaml.cs*和*ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="c6705-189">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="c6705-190">创建新的页面文件时，Visual Studio 将自动创建其*代码隐藏*文件。</span><span class="sxs-lookup"><span data-stu-id="c6705-190">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="c6705-191">这些代码隐藏文件处理响应用户输入的逻辑。</span><span class="sxs-lookup"><span data-stu-id="c6705-191">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="c6705-192">你的代码应如以下所示**`ExpenseItHome`**:</span><span class="sxs-lookup"><span data-stu-id="c6705-192">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="c6705-193">和类似如下针对**ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="c6705-193">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="c6705-194">添加名为图像*watermark.png*到项目。</span><span class="sxs-lookup"><span data-stu-id="c6705-194">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="c6705-195">可以创建自己的映像、 将文件从示例代码中，或获取它[此处](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)。</span><span class="sxs-lookup"><span data-stu-id="c6705-195">You can create your own image, copy the file from the sample code, or get it [here](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>

    1. <span data-ttu-id="c6705-196">右键单击项目节点并选择**外** > **现有项**，或按**Shift**+**Alt**+ **A**。</span><span class="sxs-lookup"><span data-stu-id="c6705-196">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="c6705-197">在中**添加现有项**对话框中，将文件筛选器设置为**的所有文件**或**映像文件**，浏览到你想要使用，并选择图像文件**添加**.</span><span class="sxs-lookup"><span data-stu-id="c6705-197">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="c6705-198">编译和运行应用程序</span><span class="sxs-lookup"><span data-stu-id="c6705-198">Build and run the application</span></span>

1. <span data-ttu-id="c6705-199">若要生成并运行应用程序，按**F5**或选择**开始调试**从**调试**菜单。</span><span class="sxs-lookup"><span data-stu-id="c6705-199">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="c6705-200">下图显示了与应用程序<xref:System.Windows.Navigation.NavigationWindow>按钮：</span><span class="sxs-lookup"><span data-stu-id="c6705-200">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![ExpenseIt 示例屏幕快照](./media/gettingstartedfigure1.png)

2. <span data-ttu-id="c6705-202">关闭要返回到 Visual Studio 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c6705-202">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="c6705-203">创建布局</span><span class="sxs-lookup"><span data-stu-id="c6705-203">Create the layout</span></span>

<span data-ttu-id="c6705-204">布局提供有序的方式来放置 UI 元素，并调整 UI 时还管理的大小和这些元素的位置。</span><span class="sxs-lookup"><span data-stu-id="c6705-204">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="c6705-205">通常使用以下布局控件之一来创建布局：</span><span class="sxs-lookup"><span data-stu-id="c6705-205">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="c6705-206"><xref:System.Windows.Controls.Canvas> -定义区域，在其中可显式定位子元素使用相对于画布区域的坐标。</span><span class="sxs-lookup"><span data-stu-id="c6705-206"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="c6705-207"><xref:System.Windows.Controls.DockPanel> -定义一个区域，其中您可以排列子元素水平或垂直，相对于彼此。</span><span class="sxs-lookup"><span data-stu-id="c6705-207"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="c6705-208"><xref:System.Windows.Controls.Grid> -定义列和行组成的灵活网格区域。</span><span class="sxs-lookup"><span data-stu-id="c6705-208"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="c6705-209"><xref:System.Windows.Controls.StackPanel> -将子元素排列成水平或垂直的一行。</span><span class="sxs-lookup"><span data-stu-id="c6705-209"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="c6705-210"><xref:System.Windows.Controls.VirtualizingStackPanel> -排列并显示方向是水平还是垂直的一行上的内容。</span><span class="sxs-lookup"><span data-stu-id="c6705-210"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="c6705-211"><xref:System.Windows.Controls.WrapPanel> -定位子元素顺序位置从左到右，将内容切换到下一行上包含框的边缘。</span><span class="sxs-lookup"><span data-stu-id="c6705-211"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="c6705-212">后续排序按照按顺序从上到下还是从右到左，取决于 Orientation 属性的值。</span><span class="sxs-lookup"><span data-stu-id="c6705-212">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="c6705-213">适用于其子元素，每个布局控件支持特定类型的布局。</span><span class="sxs-lookup"><span data-stu-id="c6705-213">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="c6705-214">`ExpenseIt` 页面可进行调整，但每个页面不水平或垂直排列以及其他元素的元素。</span><span class="sxs-lookup"><span data-stu-id="c6705-214">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="c6705-215">在此示例中，<xref:System.Windows.Controls.Grid>用作应用程序布局元素。</span><span class="sxs-lookup"><span data-stu-id="c6705-215">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="c6705-216">有关详细信息<xref:System.Windows.Controls.Panel>元素，请参阅[面板概述](../controls/panels-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c6705-216">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="c6705-217">有关布局的详细信息，请参阅[布局](../advanced/layout.md)。</span><span class="sxs-lookup"><span data-stu-id="c6705-217">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="c6705-218">在本部分中，您创建的单列的表具有三个行和 10 像素边距通过添加到的列和行定义<xref:System.Windows.Controls.Grid>中*`ExpenseItHome.xaml`*。</span><span class="sxs-lookup"><span data-stu-id="c6705-218">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="c6705-219">在中*`ExpenseItHome.xaml`*，将<xref:System.Windows.FrameworkElement.Margin%2A>属性上的<xref:System.Windows.Controls.Grid>"10,0,10,10"，对应于左侧、 顶部、 右侧和底部边距的元素：</span><span class="sxs-lookup"><span data-stu-id="c6705-219">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="c6705-220">您还可以设置**边距**中的值**属性**窗口下**布局**类别：</span><span class="sxs-lookup"><span data-stu-id="c6705-220">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![在属性窗口中的边距值](./media/properties-margin.png)

2. <span data-ttu-id="c6705-222">添加以下 XAML 之间<xref:System.Windows.Controls.Grid>标记以创建行和列定义：</span><span class="sxs-lookup"><span data-stu-id="c6705-222">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="c6705-223"><xref:System.Windows.Controls.RowDefinition.Height%2A>的两个行设置为<xref:System.Windows.GridLength.Auto%2A>，这意味着行大小将调整根据行中的内容。</span><span class="sxs-lookup"><span data-stu-id="c6705-223">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="c6705-224">默认值<xref:System.Windows.Controls.RowDefinition.Height%2A>是<xref:System.Windows.GridUnitType.Star>大小调整，这意味着行的高度可用空间的加权的比例。</span><span class="sxs-lookup"><span data-stu-id="c6705-224">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="c6705-225">例如，如果两个行具有<xref:System.Windows.Controls.RowDefinition.Height%2A>的"\*"，它们都有高度将会是可用空间的一半。</span><span class="sxs-lookup"><span data-stu-id="c6705-225">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="c6705-226">你<xref:System.Windows.Controls.Grid>现在应包含以下 XAML:</span><span class="sxs-lookup"><span data-stu-id="c6705-226">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="c6705-227">添加控件</span><span class="sxs-lookup"><span data-stu-id="c6705-227">Add controls</span></span>

<span data-ttu-id="c6705-228">在本部分中，将更新主页 UI 以显示一组人员，您在其中选择一个人即可显示其费用报表。</span><span class="sxs-lookup"><span data-stu-id="c6705-228">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="c6705-229">控件是允许用户与应用程序交互的 UI 对象。</span><span class="sxs-lookup"><span data-stu-id="c6705-229">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="c6705-230">有关详细信息，请参阅 [控件](../controls/index.md)。</span><span class="sxs-lookup"><span data-stu-id="c6705-230">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="c6705-231">若要创建此 UI，将添加到以下元素 *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="c6705-231">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="c6705-232">一个<xref:System.Windows.Controls.ListBox>（适用于的人员列表）。</span><span class="sxs-lookup"><span data-stu-id="c6705-232">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="c6705-233">一个<xref:System.Windows.Controls.Label>（用于列表标题）。</span><span class="sxs-lookup"><span data-stu-id="c6705-233">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="c6705-234">一个<xref:System.Windows.Controls.Button>（可以单击以在列表中选择的人员查看费用报表）。</span><span class="sxs-lookup"><span data-stu-id="c6705-234">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="c6705-235">每个控件的某一行中放置<xref:System.Windows.Controls.Grid>通过设置<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>附加属性。</span><span class="sxs-lookup"><span data-stu-id="c6705-235">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="c6705-236">有关附加属性的详细信息，请参阅[附加属性概述](../advanced/attached-properties-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c6705-236">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="c6705-237">在中*`ExpenseItHome.xaml`*，添加以下 XAML 某处之间<xref:System.Windows.Controls.Grid>标记：</span><span class="sxs-lookup"><span data-stu-id="c6705-237">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="c6705-238">此外可以通过将其从拖动来创建控件**工具箱**窗口拖到设计窗口中，然后设置其属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="c6705-238">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="c6705-239">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c6705-239">Build and run the application.</span></span>

    <span data-ttu-id="c6705-240">下图显示了你创建的控件：</span><span class="sxs-lookup"><span data-stu-id="c6705-240">The following illustration shows the controls you created:</span></span>

    ![ExpenseIt 示例屏幕快照](./media/gettingstartedfigure2.png)

3. <span data-ttu-id="c6705-242">关闭要返回到 Visual Studio 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c6705-242">Close the application to return to Visual Studio.</span></span>

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="c6705-243">添加图像和标题</span><span class="sxs-lookup"><span data-stu-id="c6705-243">Add an image and a title</span></span>

<span data-ttu-id="c6705-244">在本部分中，将更新主页 UI 的图像和页面标题。</span><span class="sxs-lookup"><span data-stu-id="c6705-244">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="c6705-245">在中*`ExpenseItHome.xaml`*，添加到另一个列<xref:System.Windows.Controls.Grid.ColumnDefinitions%2A>具有固定<xref:System.Windows.Controls.ColumnDefinition.Width%2A>为 230 像素：</span><span class="sxs-lookup"><span data-stu-id="c6705-245">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="c6705-246">添加到另一行<xref:System.Windows.Controls.Grid.RowDefinitions%2A>，总共四行：</span><span class="sxs-lookup"><span data-stu-id="c6705-246">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="c6705-247">将控件移动到第二列中，通过设置<xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>为 1 的三个控件 （边框、 列表框中，和按钮） 每个属性。</span><span class="sxs-lookup"><span data-stu-id="c6705-247">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="c6705-248">每个控件下移一行通过递增其<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>值加 1 每三个控件 （边框、 列表框中，和按钮） 和 Border 元素。</span><span class="sxs-lookup"><span data-stu-id="c6705-248">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="c6705-249">三个控件的 XAML 现在看起来如下所示：</span><span class="sxs-lookup"><span data-stu-id="c6705-249">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="c6705-250">设置<xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType>属性设置为*watermark.png*图像文件，添加以下 XAML 任意位置之间`<Grid>`和`</Grid>`标记：</span><span class="sxs-lookup"><span data-stu-id="c6705-250">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="c6705-251">之前<xref:System.Windows.Controls.Border>元素中，添加<xref:System.Windows.Controls.Label>"查看费用报表"的内容。</span><span class="sxs-lookup"><span data-stu-id="c6705-251">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="c6705-252">此标签是页面的标题。</span><span class="sxs-lookup"><span data-stu-id="c6705-252">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="c6705-253">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c6705-253">Build and run the application.</span></span>

<span data-ttu-id="c6705-254">下图显示了刚添加的结果：</span><span class="sxs-lookup"><span data-stu-id="c6705-254">The following illustration shows the results of what you just added:</span></span>

![ExpenseIt 示例屏幕快照](./media/gettingstartedfigure3.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="c6705-256">添加代码以处理事件</span><span class="sxs-lookup"><span data-stu-id="c6705-256">Add code to handle events</span></span>

1. <span data-ttu-id="c6705-257">在中*`ExpenseItHome.xaml`*，添加<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件处理程序<xref:System.Windows.Controls.Button>元素。</span><span class="sxs-lookup"><span data-stu-id="c6705-257">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="c6705-258">有关详细信息，请参阅[如何：创建一个简单的事件处理程序](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="c6705-258">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="c6705-259">打开 *`ExpenseItHome.xaml.vb`* 或 *`ExpenseItHome.xaml.cs`* 。</span><span class="sxs-lookup"><span data-stu-id="c6705-259">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="c6705-260">将以下代码添加到`ExpenseItHome`类添加一个按钮单击事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="c6705-260">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="c6705-261">事件处理程序打开**ExpenseReportPage**页。</span><span class="sxs-lookup"><span data-stu-id="c6705-261">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="c6705-262">为 ExpenseReportPage 创建 UI</span><span class="sxs-lookup"><span data-stu-id="c6705-262">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="c6705-263">*ExpenseReportPage.xaml*选择的人员显示费用报表 **`ExpenseItHome`** 页。</span><span class="sxs-lookup"><span data-stu-id="c6705-263">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="c6705-264">在本部分中，您将创建的用户界面**ExpenseReportPage**。</span><span class="sxs-lookup"><span data-stu-id="c6705-264">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="c6705-265">此外将添加背景和填充到各种 UI 元素的颜色。</span><span class="sxs-lookup"><span data-stu-id="c6705-265">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="c6705-266">打开 *ExpenseReportPage.xaml*。</span><span class="sxs-lookup"><span data-stu-id="c6705-266">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="c6705-267">添加以下 XAML 之间<xref:System.Windows.Controls.Grid>标记：</span><span class="sxs-lookup"><span data-stu-id="c6705-267">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="c6705-268">此用户界面是类似于 *`ExpenseItHome.xaml`* ，但报表数据显示在<xref:System.Windows.Controls.DataGrid>。</span><span class="sxs-lookup"><span data-stu-id="c6705-268">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="c6705-269">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c6705-269">Build and run the application.</span></span>

4. <span data-ttu-id="c6705-270">选择**视图**按钮。</span><span class="sxs-lookup"><span data-stu-id="c6705-270">Select the **View** button.</span></span>

    <span data-ttu-id="c6705-271">出现费用报告页。</span><span class="sxs-lookup"><span data-stu-id="c6705-271">The expense report page appears.</span></span> <span data-ttu-id="c6705-272">另请注意，启用向后导航按钮。</span><span class="sxs-lookup"><span data-stu-id="c6705-272">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="c6705-273">下图显示了添加到的 UI 元素*ExpenseReportPage.xaml*。</span><span class="sxs-lookup"><span data-stu-id="c6705-273">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![ExpenseIt 示例屏幕快照](./media/gettingstartedfigure4.png)

## <a name="style-controls"></a><span data-ttu-id="c6705-275">控件的样式</span><span class="sxs-lookup"><span data-stu-id="c6705-275">Style controls</span></span>

<span data-ttu-id="c6705-276">各种元素的外观通常是相同的 UI 中的相同类型的所有元素。</span><span class="sxs-lookup"><span data-stu-id="c6705-276">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="c6705-277">使用 UI[样式](../controls/styling-and-templating.md)以使外观可重复使用跨多个元素。</span><span class="sxs-lookup"><span data-stu-id="c6705-277">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="c6705-278">重复使用样式有助于简化 XAML 创建和管理。</span><span class="sxs-lookup"><span data-stu-id="c6705-278">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="c6705-279">本部分替换在以前步骤中通过样式定义的按元素划分的属性。</span><span class="sxs-lookup"><span data-stu-id="c6705-279">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="c6705-280">打开*Application.xaml*或*App.xaml*。</span><span class="sxs-lookup"><span data-stu-id="c6705-280">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="c6705-281">添加以下 XAML 之间<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>标记：</span><span class="sxs-lookup"><span data-stu-id="c6705-281">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="c6705-282">此 XAML 将添加以下样式：</span><span class="sxs-lookup"><span data-stu-id="c6705-282">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="c6705-283">`headerTextStyle`：设置页标题的格式<xref:System.Windows.Controls.Label>。</span><span class="sxs-lookup"><span data-stu-id="c6705-283">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="c6705-284">`labelStyle`：若要设置格式<xref:System.Windows.Controls.Label>控件。</span><span class="sxs-lookup"><span data-stu-id="c6705-284">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="c6705-285">`columnHeaderStyle`：若要设置格式<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>。</span><span class="sxs-lookup"><span data-stu-id="c6705-285">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="c6705-286">`listHeaderStyle`：若要设置列表标头的格式<xref:System.Windows.Controls.Border>控件。</span><span class="sxs-lookup"><span data-stu-id="c6705-286">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="c6705-287">`listHeaderTextStyle`：若要设置列表标头的格式<xref:System.Windows.Controls.Label>。</span><span class="sxs-lookup"><span data-stu-id="c6705-287">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="c6705-288">`buttonStyle`：若要设置格式<xref:System.Windows.Controls.Button>上`ExpenseItHome.xaml`。</span><span class="sxs-lookup"><span data-stu-id="c6705-288">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="c6705-289">请注意，这些样式是资源和子级的<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>属性元素。</span><span class="sxs-lookup"><span data-stu-id="c6705-289">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="c6705-290">在此位置中，这些样式将应用到应用程序中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="c6705-290">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="c6705-291">在.NET 应用中使用的资源的示例，请参阅[使用应用程序资源](../advanced/how-to-use-application-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="c6705-291">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="c6705-292">在中*`ExpenseItHome.xaml`*，将为之间的所有内容<xref:System.Windows.Controls.Grid>具有以下 XAML 元素：</span><span class="sxs-lookup"><span data-stu-id="c6705-292">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="c6705-293">应用样式会删除和替换定义每个控件外观的属性（如 <xref:System.Windows.VerticalAlignment> 和 <xref:System.Windows.Media.FontFamily> 。</span><span class="sxs-lookup"><span data-stu-id="c6705-293">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="c6705-294">例如，`headerTextStyle`应用于"查看费用报表" <xref:System.Windows.Controls.Label>。</span><span class="sxs-lookup"><span data-stu-id="c6705-294">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="c6705-295">打开 *ExpenseReportPage.xaml*。</span><span class="sxs-lookup"><span data-stu-id="c6705-295">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="c6705-296">替换之间的所有内容<xref:System.Windows.Controls.Grid>具有以下 XAML 元素：</span><span class="sxs-lookup"><span data-stu-id="c6705-296">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="c6705-297">此 XAML 将添加到样式<xref:System.Windows.Controls.Label>和<xref:System.Windows.Controls.Border>元素。</span><span class="sxs-lookup"><span data-stu-id="c6705-297">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="c6705-298">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c6705-298">Build and run the application.</span></span> <span data-ttu-id="c6705-299">窗口外观是与以前相同。</span><span class="sxs-lookup"><span data-stu-id="c6705-299">The window appearance is the same as previously.</span></span>

    ![ExpenseIt 示例屏幕快照](./media/gettingstartedfigure4.png)

7. <span data-ttu-id="c6705-301">关闭要返回到 Visual Studio 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c6705-301">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="c6705-302">将数据绑定到控件</span><span class="sxs-lookup"><span data-stu-id="c6705-302">Bind data to a control</span></span>

<span data-ttu-id="c6705-303">在本部分中，将创建绑定到各种控件的 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="c6705-303">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="c6705-304">在中*`ExpenseItHome.xaml`*，打开之后<xref:System.Windows.Controls.Grid>元素中，添加以下 XAML 以创建<xref:System.Windows.Data.XmlDataProvider>包含数据的每个用户：</span><span class="sxs-lookup"><span data-stu-id="c6705-304">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="c6705-305">作为创建数据<xref:System.Windows.Controls.Grid>资源。</span><span class="sxs-lookup"><span data-stu-id="c6705-305">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="c6705-306">通常情况下会作为一个文件，加载此数据，但为简单起见数据添加内联。</span><span class="sxs-lookup"><span data-stu-id="c6705-306">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="c6705-307">内`<Grid.Resources>`元素中，添加以下`<xref:System.Windows.DataTemplate>`元素，它定义如何显示中的数据<xref:System.Windows.Controls.ListBox>后，`<XmlDataProvider>`元素：</span><span class="sxs-lookup"><span data-stu-id="c6705-307">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="c6705-308">有关数据模板的详细信息，请参阅[数据模板化概述](../data/data-templating-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c6705-308">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="c6705-309">替换现有<xref:System.Windows.Controls.ListBox>使用以下 XAML:</span><span class="sxs-lookup"><span data-stu-id="c6705-309">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="c6705-310">此 XAML 绑定<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>的属性<xref:System.Windows.Controls.ListBox>到数据源，并应用数据模板作为<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>。</span><span class="sxs-lookup"><span data-stu-id="c6705-310">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="c6705-311">将数据连接到控件</span><span class="sxs-lookup"><span data-stu-id="c6705-311">Connect data to controls</span></span>

<span data-ttu-id="c6705-312">接下来，将添加代码以检索名称上所选 **`ExpenseItHome`** 页上，并将其传递给构造函数的**ExpenseReportPage**。</span><span class="sxs-lookup"><span data-stu-id="c6705-312">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="c6705-313">**ExpenseReportPage**设置与所传递的项目，这是定义的控件的数据上下文中*ExpenseReportPage.xaml*将绑定到。</span><span class="sxs-lookup"><span data-stu-id="c6705-313">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="c6705-314">打开 *ExpenseReportPage.xaml.vb* 或 *ExpenseReportPage.xaml.cs*。</span><span class="sxs-lookup"><span data-stu-id="c6705-314">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="c6705-315">添加获取对象的构造函数，以便传递所选人员的费用报表数据。</span><span class="sxs-lookup"><span data-stu-id="c6705-315">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="c6705-316">打开 *`ExpenseItHome.xaml.vb`* 或 *`ExpenseItHome.xaml.cs`* 。</span><span class="sxs-lookup"><span data-stu-id="c6705-316">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="c6705-317">更改<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件处理程序以调用新的构造函数传递所选人员的费用报表数据。</span><span class="sxs-lookup"><span data-stu-id="c6705-317">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="c6705-318">使用数据模板的样式数据</span><span class="sxs-lookup"><span data-stu-id="c6705-318">Style data with data templates</span></span>

<span data-ttu-id="c6705-319">在本部分中，将使用数据模板来更新数据绑定列表中每个项的 UI。</span><span class="sxs-lookup"><span data-stu-id="c6705-319">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="c6705-320">打开 *ExpenseReportPage.xaml*。</span><span class="sxs-lookup"><span data-stu-id="c6705-320">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="c6705-321">将"Name"和"部门"的内容绑定<xref:System.Windows.Controls.Label>元素到相应的数据源属性。</span><span class="sxs-lookup"><span data-stu-id="c6705-321">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="c6705-322">有关数据绑定的详细信息，请参阅[数据绑定概述](../data/data-binding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c6705-322">For more information about data binding, see [Data binding overview](../data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="c6705-323">打开之后<xref:System.Windows.Controls.Grid>元素中，添加以下数据模板，用于定义如何显示费用报表数据：</span><span class="sxs-lookup"><span data-stu-id="c6705-323">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="c6705-324">替换<xref:System.Windows.Controls.DataGridTextColumn>具有的元素<xref:System.Windows.Controls.DataGridTemplateColumn>下<xref:System.Windows.Controls.DataGrid>元素并将模板应用于它们。</span><span class="sxs-lookup"><span data-stu-id="c6705-324">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="c6705-325">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c6705-325">Build and run the application.</span></span>

6. <span data-ttu-id="c6705-326">选择 person，然后选择**视图**按钮。</span><span class="sxs-lookup"><span data-stu-id="c6705-326">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="c6705-327">下图显示的两个页面`ExpenseIt`控件、 布局、 样式、 数据绑定和数据模板应用与应用程序：</span><span class="sxs-lookup"><span data-stu-id="c6705-327">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![ExpenseIt 示例屏幕快照](./media/gettingstartedfigure5.png)

> [!NOTE]
> <span data-ttu-id="c6705-329">此示例演示了 WPF 的特定功能并不遵循所有最佳实践等安全、 本地化和可访问性。</span><span class="sxs-lookup"><span data-stu-id="c6705-329">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="c6705-330">WPF 和.NET 应用程序开发最佳做法的全面介绍，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="c6705-330">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="c6705-331">辅助功能</span><span class="sxs-lookup"><span data-stu-id="c6705-331">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
>
> - [<span data-ttu-id="c6705-332">安全性</span><span class="sxs-lookup"><span data-stu-id="c6705-332">Security</span></span>](../security-wpf.md)
>
> - [<span data-ttu-id="c6705-333">WPF 全球化和本地化</span><span class="sxs-lookup"><span data-stu-id="c6705-333">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
>
> - [<span data-ttu-id="c6705-334">WPF 性能</span><span class="sxs-lookup"><span data-stu-id="c6705-334">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="c6705-335">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c6705-335">Next steps</span></span>

<span data-ttu-id="c6705-336">在本演练中介绍了大量用于创建使用 Windows Presentation Foundation (WPF) UI 技术。</span><span class="sxs-lookup"><span data-stu-id="c6705-336">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="c6705-337">现在应具有一个基本的了解数据绑定的.NET 应用程序的构建基块。</span><span class="sxs-lookup"><span data-stu-id="c6705-337">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="c6705-338">有关 WPF 体系结构和编程模型的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="c6705-338">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="c6705-339">WPF 体系结构</span><span class="sxs-lookup"><span data-stu-id="c6705-339">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="c6705-340">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="c6705-340">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="c6705-341">依赖属性概述</span><span class="sxs-lookup"><span data-stu-id="c6705-341">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="c6705-342">布局</span><span class="sxs-lookup"><span data-stu-id="c6705-342">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="c6705-343">有关创建应用程序的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="c6705-343">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="c6705-344">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="c6705-344">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="c6705-345">控件</span><span class="sxs-lookup"><span data-stu-id="c6705-345">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="c6705-346">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="c6705-346">Data binding overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="c6705-347">图形和多媒体</span><span class="sxs-lookup"><span data-stu-id="c6705-347">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="c6705-348">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="c6705-348">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="c6705-349">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6705-349">See also</span></span>

- [<span data-ttu-id="c6705-350">面板概述</span><span class="sxs-lookup"><span data-stu-id="c6705-350">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="c6705-351">数据模板化概述</span><span class="sxs-lookup"><span data-stu-id="c6705-351">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="c6705-352">生成 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="c6705-352">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="c6705-353">样式和模板</span><span class="sxs-lookup"><span data-stu-id="c6705-353">Styles and templates</span></span>](../controls/styles-and-templates.md)
