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
ms.openlocfilehash: c3440ddf6cdae6b24bcf1059ab2c76d8fb957263
ms.sourcegitcommit: 11deacc8ec9f229ab8ee3cd537515d4c2826515f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2019
ms.locfileid: "66003856"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="48de6-102">演练：我的第一个 WPF 桌面应用程序</span><span class="sxs-lookup"><span data-stu-id="48de6-102">Walkthrough: My first WPF desktop application</span></span>

<span data-ttu-id="48de6-103">本文介绍如何开发包括元素所共有的大多数 WPF 应用程序的 Windows Presentation Foundation (WPF) 桌面应用程序：Extensible Application Markup Language (XAML) 标记、 代码隐藏、 应用程序定义、 控件、 布局、 数据绑定和样式。</span><span class="sxs-lookup"><span data-stu-id="48de6-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="48de6-104">若要开发应用程序，您将使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="48de6-104">To develop the application, you'll use Visual Studio.</span></span> 

<span data-ttu-id="48de6-105">本演练包含以下步骤：</span><span class="sxs-lookup"><span data-stu-id="48de6-105">This walkthrough includes the following steps:</span></span>

- <span data-ttu-id="48de6-106">使用 XAML 来设计应用程序的用户界面 (UI) 的外观。</span><span class="sxs-lookup"><span data-stu-id="48de6-106">Use XAML to design the appearance of the application's user interface (UI).</span></span>

- <span data-ttu-id="48de6-107">编写代码以生成应用程序的行为。</span><span class="sxs-lookup"><span data-stu-id="48de6-107">Write code to build the application's behavior.</span></span>

- <span data-ttu-id="48de6-108">创建应用程序定义管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="48de6-108">Create an application definition to manage the application.</span></span>

- <span data-ttu-id="48de6-109">将控件添加和创建布局以构成应用程序 UI。</span><span class="sxs-lookup"><span data-stu-id="48de6-109">Add controls and create the layout to compose the application UI.</span></span>

- <span data-ttu-id="48de6-110">创建应用程序的 UI 具有一致外观的样式。</span><span class="sxs-lookup"><span data-stu-id="48de6-110">Create styles for a consistent appearance throughout the application's UI.</span></span>

- <span data-ttu-id="48de6-111">绑定到数据，来填充数据从 UI 并保留数据和 UI 同步的用户界面。</span><span class="sxs-lookup"><span data-stu-id="48de6-111">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="48de6-112">本演练结束时，你将生成独立的 Windows 应用程序，允许用户查看所选人员的费用报表。</span><span class="sxs-lookup"><span data-stu-id="48de6-112">By the end of the walkthrough, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="48de6-113">应用程序的托管在浏览器样式的窗口中的多个 WPF 页面组成。</span><span class="sxs-lookup"><span data-stu-id="48de6-113">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="48de6-114">用于生成此演练的示例代码是适用于这两个 Visual Basic 和C#处[演练 WPF 应用程序示例代码](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)。</span><span class="sxs-lookup"><span data-stu-id="48de6-114">The sample code that is used to build this walkthrough is available for both Visual Basic and C# at [Walkthrough WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="48de6-115">您可以切换之间的示例代码的代码语言C#和使用 Visual Basic **\< />** 这篇文章右上角的下拉列表。</span><span class="sxs-lookup"><span data-stu-id="48de6-115">You can toggle the code language of the sample code between C# and Visual Basic by using the **\</>** drop-down on the upper right side of this article.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="48de6-116">系统必备</span><span class="sxs-lookup"><span data-stu-id="48de6-116">Prerequisites</span></span>

- <span data-ttu-id="48de6-117">（本文使用 Visual Studio 2019） 的 visual Studio 2017 或更高版本</span><span class="sxs-lookup"><span data-stu-id="48de6-117">Visual Studio 2017 or later (this article uses Visual Studio 2019)</span></span>

   <span data-ttu-id="48de6-118">有关安装 Visual Studio 的最新版本的详细信息，请参阅[安装 Visual Studio](/visualstudio/install/install-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="48de6-118">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="48de6-119">创建应用程序项目</span><span class="sxs-lookup"><span data-stu-id="48de6-119">Create the application project</span></span>

<span data-ttu-id="48de6-120">第一步是创建应用程序基础结构，其中包括应用程序定义，两个页面和一个图像。</span><span class="sxs-lookup"><span data-stu-id="48de6-120">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="48de6-121">在 Visual Basic 或 Visual C# 名为创建新的 WPF 应用程序项目 **`ExpenseIt`**:</span><span class="sxs-lookup"><span data-stu-id="48de6-121">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="48de6-122">打开 Visual Studio 并选择**创建一个新项目**下**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="48de6-122">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="48de6-123">**创建一个新项目**对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="48de6-123">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="48de6-124">在中**语言**下拉列表中，选择**C#** 或**Visual Basic**。</span><span class="sxs-lookup"><span data-stu-id="48de6-124">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>
      
   3. <span data-ttu-id="48de6-125">选择**WPF 应用 (.NET Framework)** 模板，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="48de6-125">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span> 
     
      ![创建新项目对话框](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)
    
      <span data-ttu-id="48de6-127">**配置新项目**对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="48de6-127">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="48de6-128">输入项目名称**`ExpenseIt`** ，然后选择**创建**。</span><span class="sxs-lookup"><span data-stu-id="48de6-128">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![配置新项目对话框](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="48de6-130">Visual Studio 创建项目并打开名为的默认应用程序窗口的设计器**MainWindow.xaml**。</span><span class="sxs-lookup"><span data-stu-id="48de6-130">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="48de6-131">打开*Application.xaml* (Visual Basic) 或*App.xaml* (C#)。</span><span class="sxs-lookup"><span data-stu-id="48de6-131">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="48de6-132">此 XAML 文件定义 WPF 应用程序和任何应用程序资源。</span><span class="sxs-lookup"><span data-stu-id="48de6-132">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="48de6-133">此外使用此文件来指定 UI 中，在这种情况下*MainWindow.xaml*，应用程序启动时自动显示。</span><span class="sxs-lookup"><span data-stu-id="48de6-133">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="48de6-134">在 XAML 应如下所示在 Visual Basic 中所示：</span><span class="sxs-lookup"><span data-stu-id="48de6-134">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="48de6-135">和类似中的以下C#:</span><span class="sxs-lookup"><span data-stu-id="48de6-135">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="48de6-136">打开*MainWindow.xaml*。</span><span class="sxs-lookup"><span data-stu-id="48de6-136">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="48de6-137">此 XAML 文件是你的应用程序的主窗口，并显示在页面中创建的内容。</span><span class="sxs-lookup"><span data-stu-id="48de6-137">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="48de6-138"><xref:System.Windows.Window>类定义的属性窗口中，例如其标题、 大小或图标，并处理事件，例如关闭或隐藏。</span><span class="sxs-lookup"><span data-stu-id="48de6-138">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="48de6-139">更改<xref:System.Windows.Window>元素<xref:System.Windows.Navigation.NavigationWindow>，如以下 XAML 所示：</span><span class="sxs-lookup"><span data-stu-id="48de6-139">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="48de6-140">此应用程序中导航到不同的内容，具体取决于用户输入。</span><span class="sxs-lookup"><span data-stu-id="48de6-140">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="48de6-141">这就是为什么主要<xref:System.Windows.Window>需要更改为<xref:System.Windows.Navigation.NavigationWindow>。</span><span class="sxs-lookup"><span data-stu-id="48de6-141">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="48de6-142"><xref:System.Windows.Navigation.NavigationWindow> 继承的所有属性<xref:System.Windows.Window>。</span><span class="sxs-lookup"><span data-stu-id="48de6-142"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="48de6-143"><xref:System.Windows.Navigation.NavigationWindow> XAML 文件中的元素创建的实例<xref:System.Windows.Navigation.NavigationWindow>类。</span><span class="sxs-lookup"><span data-stu-id="48de6-143">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="48de6-144">有关详细信息，请参阅[导航概述](../app-development/navigation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="48de6-144">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="48de6-145">删除<xref:System.Windows.Controls.Grid>元素从之间<xref:System.Windows.Navigation.NavigationWindow>标记。</span><span class="sxs-lookup"><span data-stu-id="48de6-145">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="48de6-146">更改下列属性的 XAML 代码中<xref:System.Windows.Navigation.NavigationWindow>元素：</span><span class="sxs-lookup"><span data-stu-id="48de6-146">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="48de6-147">设置<xref:System.Windows.Window.Title%2A>属性设置为"`ExpenseIt`"。</span><span class="sxs-lookup"><span data-stu-id="48de6-147">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="48de6-148">设置<xref:System.Windows.FrameworkElement.Height%2A>属性设置为 350 像素。</span><span class="sxs-lookup"><span data-stu-id="48de6-148">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="48de6-149">设置<xref:System.Windows.FrameworkElement.Width%2A>属性设置为 500 像素。</span><span class="sxs-lookup"><span data-stu-id="48de6-149">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="48de6-150">在 XAML 应如下所示适用于 Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="48de6-150">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="48de6-151">并如下所示的C#:</span><span class="sxs-lookup"><span data-stu-id="48de6-151">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="48de6-152">打开*MainWindow.xaml.vb*或*MainWindow.xaml.cs*。</span><span class="sxs-lookup"><span data-stu-id="48de6-152">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="48de6-153">此文件是包含代码来处理中声明的事件的代码隐藏文件*MainWindow.xaml*。</span><span class="sxs-lookup"><span data-stu-id="48de6-153">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="48de6-154">此文件包含在 XAML 中定义的窗口的分部类。</span><span class="sxs-lookup"><span data-stu-id="48de6-154">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="48de6-155">如果您使用的C#，更改`MainWindow`类派生自<xref:System.Windows.Navigation.NavigationWindow>。</span><span class="sxs-lookup"><span data-stu-id="48de6-155">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="48de6-156">（在 Visual Basic 中，自动发生此情况更改 XAML 中的窗口。）在C#代码现在应如下所示：</span><span class="sxs-lookup"><span data-stu-id="48de6-156">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="48de6-157">将文件添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="48de6-157">Add files to the application</span></span>

<span data-ttu-id="48de6-158">本部分将向应用程序添加两个页面和一个图像。</span><span class="sxs-lookup"><span data-stu-id="48de6-158">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="48de6-159">将新页面添加到项目中，并将其命名*`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="48de6-159">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="48de6-160">在中**解决方案资源管理器**，右键单击 **`ExpenseIt`** 项目节点，然后选择**添加** > **页**。</span><span class="sxs-lookup"><span data-stu-id="48de6-160">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="48de6-161">在中**添加新项**对话框中，**页面 (WPF)** 尚未选择模板。</span><span class="sxs-lookup"><span data-stu-id="48de6-161">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="48de6-162">输入的名称 **`ExpenseItHome`** ，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="48de6-162">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="48de6-163">此页是应用程序启动时显示的第一页。</span><span class="sxs-lookup"><span data-stu-id="48de6-163">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="48de6-164">它将显示要从中，以查看其费用报表的人员列表。</span><span class="sxs-lookup"><span data-stu-id="48de6-164">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="48de6-165">打开 *`ExpenseItHome.xaml`* 。</span><span class="sxs-lookup"><span data-stu-id="48de6-165">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="48de6-166">设置<xref:System.Windows.Controls.Page.Title%2A>到"`ExpenseIt - Home`"。</span><span class="sxs-lookup"><span data-stu-id="48de6-166">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="48de6-167">设置`DesignHeight`和`DesignWidth`元素值为 300 像素。</span><span class="sxs-lookup"><span data-stu-id="48de6-167">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="48de6-168">XAML 现在将出现，如下所示的 Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="48de6-168">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="48de6-169">并如下所示的C#:</span><span class="sxs-lookup"><span data-stu-id="48de6-169">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="48de6-170">打开*MainWindow.xaml*。</span><span class="sxs-lookup"><span data-stu-id="48de6-170">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="48de6-171">添加<xref:System.Windows.Navigation.NavigationWindow.Source%2A>属性设置为<xref:System.Windows.Navigation.NavigationWindow>元素并将其设置为"`ExpenseItHome.xaml`"。</span><span class="sxs-lookup"><span data-stu-id="48de6-171">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="48de6-172">这将设置 *`ExpenseItHome.xaml`* 的第一页时打开应用程序启动。</span><span class="sxs-lookup"><span data-stu-id="48de6-172">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> 

    <span data-ttu-id="48de6-173">在 Visual Basic 中的 XAML 的示例：</span><span class="sxs-lookup"><span data-stu-id="48de6-173">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="48de6-174">和 C# 中：</span><span class="sxs-lookup"><span data-stu-id="48de6-174">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="48de6-175">您还可以设置**源**属性中的**杂项**类别**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="48de6-175">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![在属性窗口中的源属性](./media/properties-source.png)

1. <span data-ttu-id="48de6-177">将另一个新的 WPF 页添加到项目中，并将其命名*ExpenseReportPage.xaml*::</span><span class="sxs-lookup"><span data-stu-id="48de6-177">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="48de6-178">在中**解决方案资源管理器**，右键单击 **`ExpenseIt`** 项目节点，然后选择**添加** > **页**。</span><span class="sxs-lookup"><span data-stu-id="48de6-178">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="48de6-179">在中**添加新项**对话框中，选择**页面 (WPF)** 模板。</span><span class="sxs-lookup"><span data-stu-id="48de6-179">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="48de6-180">输入的名称**ExpenseReportPage**，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="48de6-180">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="48de6-181">此页会显示费用报表上选择的人员 **`ExpenseItHome`** 页。</span><span class="sxs-lookup"><span data-stu-id="48de6-181">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="48de6-182">打开 *ExpenseReportPage.xaml*。</span><span class="sxs-lookup"><span data-stu-id="48de6-182">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="48de6-183">设置<xref:System.Windows.Controls.Page.Title%2A>到"`ExpenseIt - View Expense`"。</span><span class="sxs-lookup"><span data-stu-id="48de6-183">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="48de6-184">设置`DesignHeight`和`DesignWidth`元素值为 300 像素。</span><span class="sxs-lookup"><span data-stu-id="48de6-184">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="48de6-185">*ExpenseReportPage.xaml*现在如下所示在 Visual Basic 中：</span><span class="sxs-lookup"><span data-stu-id="48de6-185">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="48de6-186">和类似中的以下C#:</span><span class="sxs-lookup"><span data-stu-id="48de6-186">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="48de6-187">打开*ExpenseItHome.xaml.vb*并*ExpenseReportPage.xaml.vb*，或*ExpenseItHome.xaml.cs*和*ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="48de6-187">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="48de6-188">创建新的页面文件时，Visual Studio 将自动创建其*代码隐藏*文件。</span><span class="sxs-lookup"><span data-stu-id="48de6-188">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="48de6-189">这些代码隐藏文件处理响应用户输入的逻辑。</span><span class="sxs-lookup"><span data-stu-id="48de6-189">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="48de6-190">你的代码应如以下所示**`ExpenseItHome`**:</span><span class="sxs-lookup"><span data-stu-id="48de6-190">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="48de6-191">和类似如下针对**ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="48de6-191">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="48de6-192">添加名为图像*watermark.png*到项目。</span><span class="sxs-lookup"><span data-stu-id="48de6-192">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="48de6-193">可以创建自己的映像、 将文件从示例代码中，或获取它[此处](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)。</span><span class="sxs-lookup"><span data-stu-id="48de6-193">You can create your own image, copy the file from the sample code, or get it [here](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>

    1. <span data-ttu-id="48de6-194">右键单击项目节点并选择**外** > **现有项**，或按**Shift**+**Alt**+ **A**。</span><span class="sxs-lookup"><span data-stu-id="48de6-194">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="48de6-195">在中**添加现有项**对话框中，将文件筛选器设置为**的所有文件**或**映像文件**，浏览到你想要使用，并选择图像文件**添加**.</span><span class="sxs-lookup"><span data-stu-id="48de6-195">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="48de6-196">编译和运行应用程序</span><span class="sxs-lookup"><span data-stu-id="48de6-196">Build and run the application</span></span>

1. <span data-ttu-id="48de6-197">若要生成并运行应用程序，按**F5**或选择**开始调试**从**调试**菜单。</span><span class="sxs-lookup"><span data-stu-id="48de6-197">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="48de6-198">下图显示了与应用程序<xref:System.Windows.Navigation.NavigationWindow>按钮：</span><span class="sxs-lookup"><span data-stu-id="48de6-198">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![应用程序后生成并运行它。](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="48de6-200">关闭要返回到 Visual Studio 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="48de6-200">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="48de6-201">创建布局</span><span class="sxs-lookup"><span data-stu-id="48de6-201">Create the layout</span></span>

<span data-ttu-id="48de6-202">布局提供有序的方式来放置 UI 元素，并调整 UI 时还管理的大小和这些元素的位置。</span><span class="sxs-lookup"><span data-stu-id="48de6-202">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="48de6-203">通常使用以下布局控件之一来创建布局：</span><span class="sxs-lookup"><span data-stu-id="48de6-203">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="48de6-204"><xref:System.Windows.Controls.Canvas> -定义区域，在其中可显式定位子元素使用相对于画布区域的坐标。</span><span class="sxs-lookup"><span data-stu-id="48de6-204"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="48de6-205"><xref:System.Windows.Controls.DockPanel> -定义一个区域，其中您可以排列子元素水平或垂直，相对于彼此。</span><span class="sxs-lookup"><span data-stu-id="48de6-205"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="48de6-206"><xref:System.Windows.Controls.Grid> -定义列和行组成的灵活网格区域。</span><span class="sxs-lookup"><span data-stu-id="48de6-206"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="48de6-207"><xref:System.Windows.Controls.StackPanel> -将子元素排列成水平或垂直的一行。</span><span class="sxs-lookup"><span data-stu-id="48de6-207"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="48de6-208"><xref:System.Windows.Controls.VirtualizingStackPanel> -排列并显示方向是水平还是垂直的一行上的内容。</span><span class="sxs-lookup"><span data-stu-id="48de6-208"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="48de6-209"><xref:System.Windows.Controls.WrapPanel> -定位子元素顺序位置从左到右，将内容切换到下一行上包含框的边缘。</span><span class="sxs-lookup"><span data-stu-id="48de6-209"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="48de6-210">后续排序按照按顺序从上到下还是从右到左，取决于 Orientation 属性的值。</span><span class="sxs-lookup"><span data-stu-id="48de6-210">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="48de6-211">适用于其子元素，每个布局控件支持特定类型的布局。</span><span class="sxs-lookup"><span data-stu-id="48de6-211">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="48de6-212">`ExpenseIt` 页面可进行调整，但每个页面不水平或垂直排列以及其他元素的元素。</span><span class="sxs-lookup"><span data-stu-id="48de6-212">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="48de6-213">在此示例中，<xref:System.Windows.Controls.Grid>用作应用程序布局元素。</span><span class="sxs-lookup"><span data-stu-id="48de6-213">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="48de6-214">有关详细信息<xref:System.Windows.Controls.Panel>元素，请参阅[面板概述](../controls/panels-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="48de6-214">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="48de6-215">有关布局的详细信息，请参阅[布局](../advanced/layout.md)。</span><span class="sxs-lookup"><span data-stu-id="48de6-215">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="48de6-216">在本部分中，您创建的单列的表具有三个行和 10 像素边距通过添加到的列和行定义<xref:System.Windows.Controls.Grid>中*`ExpenseItHome.xaml`*。</span><span class="sxs-lookup"><span data-stu-id="48de6-216">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="48de6-217">在中*`ExpenseItHome.xaml`*，将<xref:System.Windows.FrameworkElement.Margin%2A>属性上的<xref:System.Windows.Controls.Grid>"10,0,10,10"，对应于左侧、 顶部、 右侧和底部边距的元素：</span><span class="sxs-lookup"><span data-stu-id="48de6-217">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="48de6-218">您还可以设置**边距**中的值**属性**窗口下**布局**类别：</span><span class="sxs-lookup"><span data-stu-id="48de6-218">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![在属性窗口中的边距值](./media/properties-margin.png)

2. <span data-ttu-id="48de6-220">添加以下 XAML 之间<xref:System.Windows.Controls.Grid>标记以创建行和列定义：</span><span class="sxs-lookup"><span data-stu-id="48de6-220">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="48de6-221"><xref:System.Windows.Controls.RowDefinition.Height%2A>的两个行设置为<xref:System.Windows.GridLength.Auto%2A>，这意味着行大小将调整根据行中的内容。</span><span class="sxs-lookup"><span data-stu-id="48de6-221">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="48de6-222">默认值<xref:System.Windows.Controls.RowDefinition.Height%2A>是<xref:System.Windows.GridUnitType.Star>大小调整，这意味着行的高度可用空间的加权的比例。</span><span class="sxs-lookup"><span data-stu-id="48de6-222">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="48de6-223">例如，如果两个行具有<xref:System.Windows.Controls.RowDefinition.Height%2A>的"\*"，它们都有高度将会是可用空间的一半。</span><span class="sxs-lookup"><span data-stu-id="48de6-223">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="48de6-224">你<xref:System.Windows.Controls.Grid>现在应包含以下 XAML:</span><span class="sxs-lookup"><span data-stu-id="48de6-224">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="48de6-225">添加控件</span><span class="sxs-lookup"><span data-stu-id="48de6-225">Add controls</span></span>

<span data-ttu-id="48de6-226">在本部分中，将更新主页 UI 以显示一组人员，您在其中选择一个人即可显示其费用报表。</span><span class="sxs-lookup"><span data-stu-id="48de6-226">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="48de6-227">控件是允许用户与应用程序交互的 UI 对象。</span><span class="sxs-lookup"><span data-stu-id="48de6-227">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="48de6-228">有关详细信息，请参阅 [控件](../controls/index.md)。</span><span class="sxs-lookup"><span data-stu-id="48de6-228">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="48de6-229">若要创建此 UI，将添加到以下元素 *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="48de6-229">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="48de6-230">一个<xref:System.Windows.Controls.ListBox>（适用于的人员列表）。</span><span class="sxs-lookup"><span data-stu-id="48de6-230">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="48de6-231">一个<xref:System.Windows.Controls.Label>（用于列表标题）。</span><span class="sxs-lookup"><span data-stu-id="48de6-231">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="48de6-232">一个<xref:System.Windows.Controls.Button>（可以单击以在列表中选择的人员查看费用报表）。</span><span class="sxs-lookup"><span data-stu-id="48de6-232">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="48de6-233">每个控件的某一行中放置<xref:System.Windows.Controls.Grid>通过设置<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>附加属性。</span><span class="sxs-lookup"><span data-stu-id="48de6-233">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="48de6-234">有关附加属性的详细信息，请参阅[附加属性概述](../advanced/attached-properties-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="48de6-234">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="48de6-235">在中*`ExpenseItHome.xaml`*，添加以下 XAML 某处之间<xref:System.Windows.Controls.Grid>标记：</span><span class="sxs-lookup"><span data-stu-id="48de6-235">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="48de6-236">此外可以通过将其从拖动来创建控件**工具箱**窗口拖到设计窗口中，然后设置其属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="48de6-236">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="48de6-237">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="48de6-237">Build and run the application.</span></span>

    <span data-ttu-id="48de6-238">下图显示了你创建的控件：</span><span class="sxs-lookup"><span data-stu-id="48de6-238">The following illustration shows the controls you created:</span></span>

![ExpenseIt 示例屏幕截图显示名称的列表](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="48de6-240">添加图像和标题</span><span class="sxs-lookup"><span data-stu-id="48de6-240">Add an image and a title</span></span>

<span data-ttu-id="48de6-241">在本部分中，将更新主页 UI 的图像和页面标题。</span><span class="sxs-lookup"><span data-stu-id="48de6-241">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="48de6-242">在中*`ExpenseItHome.xaml`*，添加到另一个列<xref:System.Windows.Controls.Grid.ColumnDefinitions%2A>具有固定<xref:System.Windows.Controls.ColumnDefinition.Width%2A>为 230 像素：</span><span class="sxs-lookup"><span data-stu-id="48de6-242">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="48de6-243">添加到另一行<xref:System.Windows.Controls.Grid.RowDefinitions%2A>，总共四行：</span><span class="sxs-lookup"><span data-stu-id="48de6-243">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="48de6-244">将控件移动到第二列中，通过设置<xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>为 1 的三个控件 （边框、 列表框中，和按钮） 每个属性。</span><span class="sxs-lookup"><span data-stu-id="48de6-244">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="48de6-245">每个控件下移一行通过递增其<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>值加 1 每三个控件 （边框、 列表框中，和按钮） 和 Border 元素。</span><span class="sxs-lookup"><span data-stu-id="48de6-245">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="48de6-246">三个控件的 XAML 现在看起来如下所示：</span><span class="sxs-lookup"><span data-stu-id="48de6-246">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="48de6-247">设置<xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType>属性设置为*watermark.png*图像文件，添加以下 XAML 任意位置之间`<Grid>`和`</Grid>`标记：</span><span class="sxs-lookup"><span data-stu-id="48de6-247">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="48de6-248">之前<xref:System.Windows.Controls.Border>元素中，添加<xref:System.Windows.Controls.Label>"查看费用报表"的内容。</span><span class="sxs-lookup"><span data-stu-id="48de6-248">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="48de6-249">此标签是页面的标题。</span><span class="sxs-lookup"><span data-stu-id="48de6-249">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="48de6-250">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="48de6-250">Build and run the application.</span></span>

<span data-ttu-id="48de6-251">下图显示了刚添加的结果：</span><span class="sxs-lookup"><span data-stu-id="48de6-251">The following illustration shows the results of what you just added:</span></span>

![ExpenseIt 示例屏幕截图显示了新的图像背景和页标题](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="48de6-253">添加代码以处理事件</span><span class="sxs-lookup"><span data-stu-id="48de6-253">Add code to handle events</span></span>

1. <span data-ttu-id="48de6-254">在中*`ExpenseItHome.xaml`*，添加<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件处理程序<xref:System.Windows.Controls.Button>元素。</span><span class="sxs-lookup"><span data-stu-id="48de6-254">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="48de6-255">有关详细信息，请参阅[如何：创建一个简单的事件处理程序](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="48de6-255">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="48de6-256">打开 *`ExpenseItHome.xaml.vb`* 或 *`ExpenseItHome.xaml.cs`* 。</span><span class="sxs-lookup"><span data-stu-id="48de6-256">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="48de6-257">将以下代码添加到`ExpenseItHome`类添加一个按钮单击事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="48de6-257">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="48de6-258">事件处理程序打开**ExpenseReportPage**页。</span><span class="sxs-lookup"><span data-stu-id="48de6-258">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="48de6-259">为 ExpenseReportPage 创建 UI</span><span class="sxs-lookup"><span data-stu-id="48de6-259">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="48de6-260">*ExpenseReportPage.xaml*选择的人员显示费用报表 **`ExpenseItHome`** 页。</span><span class="sxs-lookup"><span data-stu-id="48de6-260">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="48de6-261">在本部分中，您将创建的用户界面**ExpenseReportPage**。</span><span class="sxs-lookup"><span data-stu-id="48de6-261">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="48de6-262">此外将添加背景和填充到各种 UI 元素的颜色。</span><span class="sxs-lookup"><span data-stu-id="48de6-262">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="48de6-263">打开 *ExpenseReportPage.xaml*。</span><span class="sxs-lookup"><span data-stu-id="48de6-263">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="48de6-264">添加以下 XAML 之间<xref:System.Windows.Controls.Grid>标记：</span><span class="sxs-lookup"><span data-stu-id="48de6-264">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="48de6-265">此用户界面是类似于 *`ExpenseItHome.xaml`* ，但报表数据显示在<xref:System.Windows.Controls.DataGrid>。</span><span class="sxs-lookup"><span data-stu-id="48de6-265">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="48de6-266">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="48de6-266">Build and run the application.</span></span>

4. <span data-ttu-id="48de6-267">选择**视图**按钮。</span><span class="sxs-lookup"><span data-stu-id="48de6-267">Select the **View** button.</span></span>

    <span data-ttu-id="48de6-268">出现费用报告页。</span><span class="sxs-lookup"><span data-stu-id="48de6-268">The expense report page appears.</span></span> <span data-ttu-id="48de6-269">另请注意，启用向后导航按钮。</span><span class="sxs-lookup"><span data-stu-id="48de6-269">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="48de6-270">下图显示了添加到的 UI 元素*ExpenseReportPage.xaml*。</span><span class="sxs-lookup"><span data-stu-id="48de6-270">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![ExpenseIt 示例屏幕截图显示刚刚为 ExpenseReportPage 创建 UI。](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="48de6-272">控件的样式</span><span class="sxs-lookup"><span data-stu-id="48de6-272">Style controls</span></span>

<span data-ttu-id="48de6-273">各种元素的外观通常是相同的 UI 中的相同类型的所有元素。</span><span class="sxs-lookup"><span data-stu-id="48de6-273">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="48de6-274">使用 UI[样式](../controls/styling-and-templating.md)以使外观可重复使用跨多个元素。</span><span class="sxs-lookup"><span data-stu-id="48de6-274">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="48de6-275">重复使用样式有助于简化 XAML 创建和管理。</span><span class="sxs-lookup"><span data-stu-id="48de6-275">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="48de6-276">本部分替换在以前步骤中通过样式定义的按元素划分的属性。</span><span class="sxs-lookup"><span data-stu-id="48de6-276">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="48de6-277">打开*Application.xaml*或*App.xaml*。</span><span class="sxs-lookup"><span data-stu-id="48de6-277">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="48de6-278">添加以下 XAML 之间<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>标记：</span><span class="sxs-lookup"><span data-stu-id="48de6-278">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="48de6-279">此 XAML 将添加以下样式：</span><span class="sxs-lookup"><span data-stu-id="48de6-279">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="48de6-280">`headerTextStyle`：设置页标题的格式<xref:System.Windows.Controls.Label>。</span><span class="sxs-lookup"><span data-stu-id="48de6-280">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="48de6-281">`labelStyle`：若要设置格式<xref:System.Windows.Controls.Label>控件。</span><span class="sxs-lookup"><span data-stu-id="48de6-281">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="48de6-282">`columnHeaderStyle`：若要设置格式<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>。</span><span class="sxs-lookup"><span data-stu-id="48de6-282">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="48de6-283">`listHeaderStyle`：若要设置列表标头的格式<xref:System.Windows.Controls.Border>控件。</span><span class="sxs-lookup"><span data-stu-id="48de6-283">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="48de6-284">`listHeaderTextStyle`：若要设置列表标头的格式<xref:System.Windows.Controls.Label>。</span><span class="sxs-lookup"><span data-stu-id="48de6-284">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="48de6-285">`buttonStyle`：若要设置格式<xref:System.Windows.Controls.Button>上`ExpenseItHome.xaml`。</span><span class="sxs-lookup"><span data-stu-id="48de6-285">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="48de6-286">请注意，这些样式是资源和子级的<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>属性元素。</span><span class="sxs-lookup"><span data-stu-id="48de6-286">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="48de6-287">在此位置中，这些样式将应用到应用程序中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="48de6-287">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="48de6-288">在.NET 应用中使用的资源的示例，请参阅[使用应用程序资源](../advanced/how-to-use-application-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="48de6-288">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="48de6-289">在中*`ExpenseItHome.xaml`*，将为之间的所有内容<xref:System.Windows.Controls.Grid>具有以下 XAML 元素：</span><span class="sxs-lookup"><span data-stu-id="48de6-289">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="48de6-290">应用样式会删除和替换定义每个控件外观的属性（如 <xref:System.Windows.VerticalAlignment> 和 <xref:System.Windows.Media.FontFamily> 。</span><span class="sxs-lookup"><span data-stu-id="48de6-290">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="48de6-291">例如，`headerTextStyle`应用于"查看费用报表" <xref:System.Windows.Controls.Label>。</span><span class="sxs-lookup"><span data-stu-id="48de6-291">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="48de6-292">打开 *ExpenseReportPage.xaml*。</span><span class="sxs-lookup"><span data-stu-id="48de6-292">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="48de6-293">替换之间的所有内容<xref:System.Windows.Controls.Grid>具有以下 XAML 元素：</span><span class="sxs-lookup"><span data-stu-id="48de6-293">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="48de6-294">此 XAML 将添加到样式<xref:System.Windows.Controls.Label>和<xref:System.Windows.Controls.Border>元素。</span><span class="sxs-lookup"><span data-stu-id="48de6-294">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="48de6-295">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="48de6-295">Build and run the application.</span></span> <span data-ttu-id="48de6-296">窗口外观是与以前相同。</span><span class="sxs-lookup"><span data-stu-id="48de6-296">The window appearance is the same as previously.</span></span>

    ![ExpenseIt 示例屏幕截图，其中相同的外观如下所示的最后一节。](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="48de6-298">关闭要返回到 Visual Studio 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="48de6-298">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="48de6-299">将数据绑定到控件</span><span class="sxs-lookup"><span data-stu-id="48de6-299">Bind data to a control</span></span>

<span data-ttu-id="48de6-300">在本部分中，将创建绑定到各种控件的 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="48de6-300">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="48de6-301">在中*`ExpenseItHome.xaml`*，打开之后<xref:System.Windows.Controls.Grid>元素中，添加以下 XAML 以创建<xref:System.Windows.Data.XmlDataProvider>包含数据的每个用户：</span><span class="sxs-lookup"><span data-stu-id="48de6-301">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="48de6-302">作为创建数据<xref:System.Windows.Controls.Grid>资源。</span><span class="sxs-lookup"><span data-stu-id="48de6-302">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="48de6-303">通常情况下会作为一个文件，加载此数据，但为简单起见数据添加内联。</span><span class="sxs-lookup"><span data-stu-id="48de6-303">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="48de6-304">内`<Grid.Resources>`元素中，添加以下`<xref:System.Windows.DataTemplate>`元素，它定义如何显示中的数据<xref:System.Windows.Controls.ListBox>后，`<XmlDataProvider>`元素：</span><span class="sxs-lookup"><span data-stu-id="48de6-304">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="48de6-305">有关数据模板的详细信息，请参阅[数据模板化概述](../data/data-templating-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="48de6-305">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="48de6-306">替换现有<xref:System.Windows.Controls.ListBox>使用以下 XAML:</span><span class="sxs-lookup"><span data-stu-id="48de6-306">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="48de6-307">此 XAML 绑定<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>的属性<xref:System.Windows.Controls.ListBox>到数据源，并应用数据模板作为<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>。</span><span class="sxs-lookup"><span data-stu-id="48de6-307">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="48de6-308">将数据连接到控件</span><span class="sxs-lookup"><span data-stu-id="48de6-308">Connect data to controls</span></span>

<span data-ttu-id="48de6-309">接下来，将添加代码以检索名称上所选 **`ExpenseItHome`** 页上，并将其传递给构造函数的**ExpenseReportPage**。</span><span class="sxs-lookup"><span data-stu-id="48de6-309">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="48de6-310">**ExpenseReportPage**设置与所传递的项目，这是定义的控件的数据上下文中*ExpenseReportPage.xaml*将绑定到。</span><span class="sxs-lookup"><span data-stu-id="48de6-310">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="48de6-311">打开 *ExpenseReportPage.xaml.vb* 或 *ExpenseReportPage.xaml.cs*。</span><span class="sxs-lookup"><span data-stu-id="48de6-311">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="48de6-312">添加获取对象的构造函数，以便传递所选人员的费用报表数据。</span><span class="sxs-lookup"><span data-stu-id="48de6-312">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="48de6-313">打开 *`ExpenseItHome.xaml.vb`* 或 *`ExpenseItHome.xaml.cs`* 。</span><span class="sxs-lookup"><span data-stu-id="48de6-313">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="48de6-314">更改<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件处理程序以调用新的构造函数传递所选人员的费用报表数据。</span><span class="sxs-lookup"><span data-stu-id="48de6-314">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="48de6-315">使用数据模板的样式数据</span><span class="sxs-lookup"><span data-stu-id="48de6-315">Style data with data templates</span></span>

<span data-ttu-id="48de6-316">在本部分中，将使用数据模板来更新数据绑定列表中每个项的 UI。</span><span class="sxs-lookup"><span data-stu-id="48de6-316">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="48de6-317">打开 *ExpenseReportPage.xaml*。</span><span class="sxs-lookup"><span data-stu-id="48de6-317">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="48de6-318">将"Name"和"部门"的内容绑定<xref:System.Windows.Controls.Label>元素到相应的数据源属性。</span><span class="sxs-lookup"><span data-stu-id="48de6-318">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="48de6-319">有关数据绑定的详细信息，请参阅[数据绑定概述](../data/data-binding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="48de6-319">For more information about data binding, see [Data binding overview](../data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="48de6-320">打开之后<xref:System.Windows.Controls.Grid>元素中，添加以下数据模板，用于定义如何显示费用报表数据：</span><span class="sxs-lookup"><span data-stu-id="48de6-320">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="48de6-321">替换<xref:System.Windows.Controls.DataGridTextColumn>具有的元素<xref:System.Windows.Controls.DataGridTemplateColumn>下<xref:System.Windows.Controls.DataGrid>元素并将模板应用于它们。</span><span class="sxs-lookup"><span data-stu-id="48de6-321">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="48de6-322">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="48de6-322">Build and run the application.</span></span>

6. <span data-ttu-id="48de6-323">选择 person，然后选择**视图**按钮。</span><span class="sxs-lookup"><span data-stu-id="48de6-323">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="48de6-324">下图显示的两个页面`ExpenseIt`控件、 布局、 样式、 数据绑定和数据模板应用与应用程序：</span><span class="sxs-lookup"><span data-stu-id="48de6-324">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![显示名称列表和费用报表应用程序的两个页面。](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="48de6-326">此示例演示了 WPF 的特定功能并不遵循所有最佳实践等安全、 本地化和可访问性。</span><span class="sxs-lookup"><span data-stu-id="48de6-326">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="48de6-327">WPF 和.NET 应用程序开发最佳做法的全面介绍，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="48de6-327">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="48de6-328">辅助功能</span><span class="sxs-lookup"><span data-stu-id="48de6-328">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
>
> - [<span data-ttu-id="48de6-329">安全性</span><span class="sxs-lookup"><span data-stu-id="48de6-329">Security</span></span>](../security-wpf.md)
>
> - [<span data-ttu-id="48de6-330">WPF 全球化和本地化</span><span class="sxs-lookup"><span data-stu-id="48de6-330">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
>
> - [<span data-ttu-id="48de6-331">WPF 性能</span><span class="sxs-lookup"><span data-stu-id="48de6-331">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="48de6-332">后续步骤</span><span class="sxs-lookup"><span data-stu-id="48de6-332">Next steps</span></span>

<span data-ttu-id="48de6-333">在本演练中介绍了大量用于创建使用 Windows Presentation Foundation (WPF) UI 技术。</span><span class="sxs-lookup"><span data-stu-id="48de6-333">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="48de6-334">现在应具有一个基本的了解数据绑定的.NET 应用程序的构建基块。</span><span class="sxs-lookup"><span data-stu-id="48de6-334">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="48de6-335">有关 WPF 体系结构和编程模型的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="48de6-335">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="48de6-336">WPF 体系结构</span><span class="sxs-lookup"><span data-stu-id="48de6-336">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="48de6-337">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="48de6-337">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="48de6-338">依赖属性概述</span><span class="sxs-lookup"><span data-stu-id="48de6-338">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="48de6-339">布局</span><span class="sxs-lookup"><span data-stu-id="48de6-339">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="48de6-340">有关创建应用程序的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="48de6-340">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="48de6-341">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="48de6-341">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="48de6-342">控件</span><span class="sxs-lookup"><span data-stu-id="48de6-342">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="48de6-343">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="48de6-343">Data binding overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="48de6-344">图形和多媒体</span><span class="sxs-lookup"><span data-stu-id="48de6-344">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="48de6-345">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="48de6-345">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="48de6-346">请参阅</span><span class="sxs-lookup"><span data-stu-id="48de6-346">See also</span></span>

- [<span data-ttu-id="48de6-347">面板概述</span><span class="sxs-lookup"><span data-stu-id="48de6-347">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="48de6-348">数据模板化概述</span><span class="sxs-lookup"><span data-stu-id="48de6-348">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="48de6-349">生成 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="48de6-349">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="48de6-350">样式和模板</span><span class="sxs-lookup"><span data-stu-id="48de6-350">Styles and templates</span></span>](../controls/styles-and-templates.md)
