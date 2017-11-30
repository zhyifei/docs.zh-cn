---
title: "演练： 我第一个 WPF 桌面应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
caps.latest.revision: "71"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f9818231a68f5c2ac2a6852f27e4876baa9728e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="a7001-102">演练： 我第一个 WPF 桌面应用程序</span><span class="sxs-lookup"><span data-stu-id="a7001-102">Walkthrough: My first WPF desktop application</span></span>
<span data-ttu-id="a7001-103">本演练中提供的开发的简介[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]包括元素所共有的大多数的应用程序[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]应用程序：[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]标记、 代码隐藏、 应用程序定义、 控件、 布局、数据绑定和样式。</span><span class="sxs-lookup"><span data-stu-id="a7001-103">This walkthrough provides an introduction to the development of a [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] application that includes the elements that are common to most [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications: [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> 
  
 <span data-ttu-id="a7001-104">本演练将指导你通过一个简单的开发[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]应用程序使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="a7001-104">This walkthrough guides you through the development of a simple [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application using the following steps.</span></span> 
  
-   <span data-ttu-id="a7001-105">定义[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]设计的应用程序的外观[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a7001-105">Defining [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to design the appearance of the application's [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> 
  
-   <span data-ttu-id="a7001-106">编写代码以生成应用程序的行为。</span><span class="sxs-lookup"><span data-stu-id="a7001-106">Writing code to build the application's behavior.</span></span> 
  
-   <span data-ttu-id="a7001-107">创建应用程序定义以托管应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7001-107">Creating an application definition to manage the application.</span></span> 
  
-   <span data-ttu-id="a7001-108">添加控件和创建布局以构成应用程序[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a7001-108">Adding controls and creating the layout to compose the application [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> 
  
-   <span data-ttu-id="a7001-109">创建样式，以便创建在整个应用程序一致的外观[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a7001-109">Creating styles to create a consistent appearance throughout an application's [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> 
  
-   <span data-ttu-id="a7001-110">绑定[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]数据到同时填充[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]从数据并保留数据和[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]同步。</span><span class="sxs-lookup"><span data-stu-id="a7001-110">Binding the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to data to both populate the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] from data and keep the data and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] synchronized.</span></span> 
  
 <span data-ttu-id="a7001-111">本演练结束时，您便会生成独立[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]应用程序，用户可查看所选人员的费用报销。</span><span class="sxs-lookup"><span data-stu-id="a7001-111">By the end of the walkthrough, you will have built a standalone [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="a7001-112">应用程序将包含多种[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]浏览器样式窗口中承载的页。</span><span class="sxs-lookup"><span data-stu-id="a7001-112">The application will be composed of several [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pages that are hosted in a browser-style window.</span></span> 
  
 <span data-ttu-id="a7001-113">用于生成本演练的示例代码已适用于[!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)]和[!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)]在[生成 WPF 应用程序简介](http://go.microsoft.com/fwlink/?LinkID=160008)。</span><span class="sxs-lookup"><span data-stu-id="a7001-113">The sample code that is used to build this walkthrough is available for both [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] and [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] at  [Introduction to Building WPF Applications](http://go.microsoft.com/fwlink/?LinkID=160008).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a7001-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="a7001-114">Prerequisites</span></span>  

- [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="a7001-115"> 或更高版本</span><span class="sxs-lookup"><span data-stu-id="a7001-115"> or later</span></span>

<span data-ttu-id="a7001-116">有关安装最新版本的 Visual Studio 的详细信息，请参阅[安装 Visual Studio](/visualstudio/install/install-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="a7001-116">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>
  
## <a name="creating-the-application-project"></a><span data-ttu-id="a7001-117">创建应用程序项目</span><span class="sxs-lookup"><span data-stu-id="a7001-117">Creating the application project</span></span>  
 <span data-ttu-id="a7001-118">在本部分中，将创建包含应用程序定义、两个页面以及图像的应用程序基础结构。</span><span class="sxs-lookup"><span data-stu-id="a7001-118">In this section, you create the application infrastructure, which includes an application definition, two pages, and an image.</span></span> 
  
1. <span data-ttu-id="a7001-119">在 Visual Basic 或 Visual C# 中创建名为 `ExpenseIt` 的新 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="a7001-119">Create a new WPF Application project in Visual Basic or Visual C# named `ExpenseIt`.</span></span> <span data-ttu-id="a7001-120">有关详细信息，请参阅[如何：创建新的 WPF 应用程序项目](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)。</span><span class="sxs-lookup"><span data-stu-id="a7001-120">For more information, see [How to: Create a New WPF Application Project](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span> 
  
    > [!NOTE]
    >  <span data-ttu-id="a7001-121">本演练使用<xref:System.Windows.Controls.DataGrid>是在.NET Framework 4 中可用的控件。</span><span class="sxs-lookup"><span data-stu-id="a7001-121">This walkthrough uses the <xref:System.Windows.Controls.DataGrid> control that is available in the .NET Framework 4.</span></span> <span data-ttu-id="a7001-122">为确保你的项目面向.NET Framework 4 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a7001-122">Be sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="a7001-123">有关详细信息，请参阅[如何： 面向.NET Framework 版本](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)。</span><span class="sxs-lookup"><span data-stu-id="a7001-123">For more information, see[How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span> 
  
2. <span data-ttu-id="a7001-124">打开 Application.xaml (Visual Basic) 或 App.xaml (C#)。</span><span class="sxs-lookup"><span data-stu-id="a7001-124">Open Application.xaml (Visual Basic) or App.xaml (C#).</span></span> 
  
     <span data-ttu-id="a7001-125">这[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件定义[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]应用程序和任何应用程序资源。</span><span class="sxs-lookup"><span data-stu-id="a7001-125">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file defines a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application and any application resources.</span></span> <span data-ttu-id="a7001-126">此外使用此文件来指定[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]自动显示在应用程序启动; 在此情况下，MainWindow.xaml。</span><span class="sxs-lookup"><span data-stu-id="a7001-126">You also use this file to specify the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] that automatically shows when the application starts; in this case, MainWindow.xaml.</span></span> 
  
     <span data-ttu-id="a7001-127">你[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]应如下所示在 Visual Basic 中：</span><span class="sxs-lookup"><span data-stu-id="a7001-127">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]  
  
     <span data-ttu-id="a7001-128">或者，在 C# 中是这样：</span><span class="sxs-lookup"><span data-stu-id="a7001-128">Or like this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]  
  
3. <span data-ttu-id="a7001-129">打开 MainWindow.xaml。</span><span class="sxs-lookup"><span data-stu-id="a7001-129">Open MainWindow.xaml.</span></span> 
  
     <span data-ttu-id="a7001-130">这[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件是你的应用程序的主窗口，并显示在页中创建的内容。</span><span class="sxs-lookup"><span data-stu-id="a7001-130">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="a7001-131"><xref:System.Windows.Window>类定义的属性窗口中，例如，其标题、 大小或图标，并处理事件，例如关闭或隐藏。</span><span class="sxs-lookup"><span data-stu-id="a7001-131">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span> 
  
4. <span data-ttu-id="a7001-132">更改<xref:System.Windows.Window>元素<xref:System.Windows.Navigation.NavigationWindow>。</span><span class="sxs-lookup"><span data-stu-id="a7001-132">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> 
  
     <span data-ttu-id="a7001-133">此应用程序将导航到不同内容，具体取决于用户交互。</span><span class="sxs-lookup"><span data-stu-id="a7001-133">This application will navigate to different content depending on the user interaction.</span></span> <span data-ttu-id="a7001-134">因此，main<xref:System.Windows.Window>需要更改为<xref:System.Windows.Navigation.NavigationWindow>。</span><span class="sxs-lookup"><span data-stu-id="a7001-134">Therefore, the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="a7001-135"><xref:System.Windows.Navigation.NavigationWindow>继承的所有属性<xref:System.Windows.Window>。</span><span class="sxs-lookup"><span data-stu-id="a7001-135"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="a7001-136"><xref:System.Windows.Navigation.NavigationWindow> XAML 文件中的元素创建的实例<xref:System.Windows.Navigation.NavigationWindow>类。</span><span class="sxs-lookup"><span data-stu-id="a7001-136">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="a7001-137">有关详细信息，请参阅[导航概述](../../../../docs/framework/wpf/app-development/navigation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a7001-137">For more information, see [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span></span> 
  
5. <span data-ttu-id="a7001-138">在更改下列属性<xref:System.Windows.Navigation.NavigationWindow>元素：</span><span class="sxs-lookup"><span data-stu-id="a7001-138">Change the following properties on the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>  
  
    -   <span data-ttu-id="a7001-139">设置<xref:System.Windows.Window.Title%2A>属性设置为"ExpenseIt"。</span><span class="sxs-lookup"><span data-stu-id="a7001-139">Set the <xref:System.Windows.Window.Title%2A> property to "ExpenseIt".</span></span> 
  
    -   <span data-ttu-id="a7001-140">设置<xref:System.Windows.FrameworkElement.Width%2A>为 500 像素的属性。</span><span class="sxs-lookup"><span data-stu-id="a7001-140">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span> 
  
    -   <span data-ttu-id="a7001-141">设置<xref:System.Windows.FrameworkElement.Height%2A>为 350 像素的属性。</span><span class="sxs-lookup"><span data-stu-id="a7001-141">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span> 
  
    -   <span data-ttu-id="a7001-142">删除<xref:System.Windows.Controls.Grid>之间的元素<xref:System.Windows.Navigation.NavigationWindow>标记。</span><span class="sxs-lookup"><span data-stu-id="a7001-142">Remove the <xref:System.Windows.Controls.Grid> elements between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span> 
  
     <span data-ttu-id="a7001-143">你[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]应如下所示在 Visual Basic 中：</span><span class="sxs-lookup"><span data-stu-id="a7001-143">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]  
  
     <span data-ttu-id="a7001-144">或者，在 C# 中是这样：</span><span class="sxs-lookup"><span data-stu-id="a7001-144">Or like this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]  
  
6. <span data-ttu-id="a7001-145">打开 MainWindow.xaml.vb 或 MainWindow.xaml.cs。</span><span class="sxs-lookup"><span data-stu-id="a7001-145">Open MainWindow.xaml.vb or MainWindow.xaml.cs.</span></span> 
  
     <span data-ttu-id="a7001-146">此文件是代码隐藏文件，包含用于处理在 MainWindow.xaml 中声明的事件的代码。</span><span class="sxs-lookup"><span data-stu-id="a7001-146">This file is a code-behind file that contains code to handle the events declared in MainWindow.xaml.</span></span> <span data-ttu-id="a7001-147">此文件包含在 XAML 中定义的窗口的分部类。</span><span class="sxs-lookup"><span data-stu-id="a7001-147">This file contains a partial class for the window defined in XAML.</span></span> 
  
7. <span data-ttu-id="a7001-148">如果你使用的 C#，更改`MainWindow`类以派生自<xref:System.Windows.Navigation.NavigationWindow>。</span><span class="sxs-lookup"><span data-stu-id="a7001-148">If you are using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> 
  
     <span data-ttu-id="a7001-149">在 Visual Basic 中，当在 XAML 中更改窗口时，这种情况会自动发生。</span><span class="sxs-lookup"><span data-stu-id="a7001-149">In Visual Basic, this happens automatically when you change the window in XAML.</span></span> 
  
     <span data-ttu-id="a7001-150">代码应如下所示。</span><span class="sxs-lookup"><span data-stu-id="a7001-150">Your code should look like this.</span></span> 
  
    [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
    [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]  
  
## <a name="adding-files-to-the-application"></a><span data-ttu-id="a7001-151">将文件添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="a7001-151">Adding files to the application</span></span>  
 <span data-ttu-id="a7001-152">在本部分中，将向应用程序添加两个页面和一个图像。</span><span class="sxs-lookup"><span data-stu-id="a7001-152">In this section, you add two pages and an image to the application.</span></span> 
  
1. <span data-ttu-id="a7001-153">将新的页 (WPF) 添加到名为的项目`ExpenseItHome.xaml`。</span><span class="sxs-lookup"><span data-stu-id="a7001-153">Add a new Page (WPF) to the project named `ExpenseItHome.xaml`.</span></span> <span data-ttu-id="a7001-154">有关详细信息，请参阅[如何： 将新项添加到 WPF 项目](http://msdn.microsoft.com/en-us/17e6b238-fc32-4385-98ef-2f66ca09d9ad)。</span><span class="sxs-lookup"><span data-stu-id="a7001-154">For more information, see [How to: Add New Items to a WPF Project](http://msdn.microsoft.com/en-us/17e6b238-fc32-4385-98ef-2f66ca09d9ad).</span></span> 
  
     <span data-ttu-id="a7001-155">此页是应用程序启动时显示的第一个页面。</span><span class="sxs-lookup"><span data-stu-id="a7001-155">This page is the first page that is displayed when the application is launched.</span></span> <span data-ttu-id="a7001-156">它将显示一个人员列表，用户可从中选择某个人员以显示其费用报表。</span><span class="sxs-lookup"><span data-stu-id="a7001-156">It will show a list of people from which a user can select a person to show an expense report for.</span></span> 
  
2. <span data-ttu-id="a7001-157">打开 ExpenseItHome.xaml。</span><span class="sxs-lookup"><span data-stu-id="a7001-157">Open ExpenseItHome.xaml.</span></span> 
  
3. <span data-ttu-id="a7001-158">设置<xref:System.Windows.Controls.Page.Title%2A>到"ExpenseIt-主页"。</span><span class="sxs-lookup"><span data-stu-id="a7001-158">Set the <xref:System.Windows.Controls.Page.Title%2A> to "ExpenseIt - Home".</span></span> 
  
     <span data-ttu-id="a7001-159">你[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]应如下所示在 Visual Basic 中：</span><span class="sxs-lookup"><span data-stu-id="a7001-159">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]  
  
     <span data-ttu-id="a7001-160">或者，在 C# 中是这样：</span><span class="sxs-lookup"><span data-stu-id="a7001-160">Or this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]  
  
4. <span data-ttu-id="a7001-161">打开 MainWindow.xaml。</span><span class="sxs-lookup"><span data-stu-id="a7001-161">Open MainWindow.xaml.</span></span> 
  
5. <span data-ttu-id="a7001-162">设置<xref:System.Windows.Navigation.NavigationWindow.Source%2A>属性<xref:System.Windows.Navigation.NavigationWindow>到"ExpenseItHome.xaml"。</span><span class="sxs-lookup"><span data-stu-id="a7001-162">Set the <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property on the <xref:System.Windows.Navigation.NavigationWindow> to "ExpenseItHome.xaml".</span></span> 
  
     <span data-ttu-id="a7001-163">这将 ExpenseItHome.xaml 设置为应用程序启动时打开的第一个页面。</span><span class="sxs-lookup"><span data-stu-id="a7001-163">This sets ExpenseItHome.xaml to be the first page opened when the application starts.</span></span> <span data-ttu-id="a7001-164">你[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]应如下所示在 Visual Basic 中：</span><span class="sxs-lookup"><span data-stu-id="a7001-164">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]  
  
     <span data-ttu-id="a7001-165">或者，在 C# 中是这样：</span><span class="sxs-lookup"><span data-stu-id="a7001-165">Or this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]  
  
6. <span data-ttu-id="a7001-166">将新的页 (WPF) 添加到名为的项目`ExpenseReportPage.xaml`。</span><span class="sxs-lookup"><span data-stu-id="a7001-166">Add a new Page (WPF) to the project named `ExpenseReportPage.xaml`.</span></span> 
  
     <span data-ttu-id="a7001-167">此页面将显示在 ExpenseItHome.xaml 上选择的人员的费用报表。</span><span class="sxs-lookup"><span data-stu-id="a7001-167">This page will show the expense report for the person that is selected on ExpenseItHome.xaml.</span></span> 
  
7. <span data-ttu-id="a7001-168">打开 ExpenseReportPage.xaml。</span><span class="sxs-lookup"><span data-stu-id="a7001-168">Open ExpenseReportPage.xaml.</span></span> 
  
8. <span data-ttu-id="a7001-169">设置<xref:System.Windows.Controls.Page.Title%2A>到"ExpenseIt-View Expense"。</span><span class="sxs-lookup"><span data-stu-id="a7001-169">Set the <xref:System.Windows.Controls.Page.Title%2A> to "ExpenseIt - View Expense".</span></span> 
  
     <span data-ttu-id="a7001-170">你[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]应如下所示在 Visual Basic 中：</span><span class="sxs-lookup"><span data-stu-id="a7001-170">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]  
  
     <span data-ttu-id="a7001-171">或者，在 C# 中是这样：</span><span class="sxs-lookup"><span data-stu-id="a7001-171">Or this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]  
  
9. <span data-ttu-id="a7001-172">打开 ExpenseItHome.xaml.vb 和 ExpenseReportPage.xaml.vb，或者 ExpenseItHome.xaml.cs 和 ExpenseReportPage.xaml.cs。</span><span class="sxs-lookup"><span data-stu-id="a7001-172">Open ExpenseItHome.xaml.vb and ExpenseReportPage.xaml.vb, or ExpenseItHome.xaml.cs and ExpenseReportPage.xaml.cs.</span></span> 
  
     <span data-ttu-id="a7001-173">创建新页面文件时，Visual Studio 将自动创建代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="a7001-173">When you create a new Page file, Visual Studio automatically creates a code behind file.</span></span> <span data-ttu-id="a7001-174">这些代码隐藏文件处理响应用户输入的逻辑。</span><span class="sxs-lookup"><span data-stu-id="a7001-174">These code-behind files handle the logic for responding to user input.</span></span> 
  
     <span data-ttu-id="a7001-175">代码应如下所示。</span><span class="sxs-lookup"><span data-stu-id="a7001-175">Your code should look like this.</span></span> 
  
    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]  
  
    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]  
  
10. <span data-ttu-id="a7001-176">将名为 watermark.png 的图像添加至项目。</span><span class="sxs-lookup"><span data-stu-id="a7001-176">Add an image named watermark.png to the project.</span></span> <span data-ttu-id="a7001-177">可以创建自己的图像，也可以从示例代码中复制文件。</span><span class="sxs-lookup"><span data-stu-id="a7001-177">You can either create your own image, or copy the file from the sample code.</span></span> <span data-ttu-id="a7001-178">有关详细信息，请参阅[NIB： 如何： 将现有项目添加到项目](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)。</span><span class="sxs-lookup"><span data-stu-id="a7001-178">For more information, see [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span></span> 

## <a name="building-and-running-the-application"></a><span data-ttu-id="a7001-179">生成并运行应用程序</span><span class="sxs-lookup"><span data-stu-id="a7001-179">Building and running the application</span></span>  
 <span data-ttu-id="a7001-180">在本部分中，将生成和运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7001-180">In this section, you build and run the application.</span></span> 
  
1. <span data-ttu-id="a7001-181">生成并运行应用程序通过按 f5 键或选择**启动调试**从**调试**菜单。</span><span class="sxs-lookup"><span data-stu-id="a7001-181">Build and run the application by pressing F5 or select **Start Debugging** from the **Debug** menu.</span></span> 
  
     <span data-ttu-id="a7001-182">下图显示具有的应用程序<xref:System.Windows.Navigation.NavigationWindow>按钮。</span><span class="sxs-lookup"><span data-stu-id="a7001-182">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons.</span></span> 
  
     <span data-ttu-id="a7001-183">![ExpenseIt 示例屏幕快照](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")</span><span class="sxs-lookup"><span data-stu-id="a7001-183">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")</span></span>  
  
2. <span data-ttu-id="a7001-184">关闭应用程序以返回到[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a7001-184">Close the application to return to [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span> 
  
## <a name="creating-the-layout"></a><span data-ttu-id="a7001-185">创建布局</span><span class="sxs-lookup"><span data-stu-id="a7001-185">Creating the layout</span></span>  
 <span data-ttu-id="a7001-186">布局提供有序的方式来放置[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]元素，并还管理的大小和这些元素的位置时[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]一起调整大小。</span><span class="sxs-lookup"><span data-stu-id="a7001-186">Layout provides an ordered way to place [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements, and also manages the size and position of those elements when a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is resized.</span></span> <span data-ttu-id="a7001-187">通常使用以下布局控件之一来创建布局：</span><span class="sxs-lookup"><span data-stu-id="a7001-187">You typically create a layout with one of the following layout controls:</span></span>  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="a7001-188">每个布局控件都为子元素支持特殊类型的布局。</span><span class="sxs-lookup"><span data-stu-id="a7001-188">Each of these layout controls supports a special type of layout for its child elements.</span></span> <span data-ttu-id="a7001-189">ExpenseIt 页面可进行调整，并且每个页面均有与其他元素水平或垂直排列的元素。</span><span class="sxs-lookup"><span data-stu-id="a7001-189">ExpenseIt pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="a7001-190">因此，<xref:System.Windows.Controls.Grid>是应用程序的理想布局元素。</span><span class="sxs-lookup"><span data-stu-id="a7001-190">Consequently, the <xref:System.Windows.Controls.Grid> is the ideal layout element for the application.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="a7001-191">有关详细信息<xref:System.Windows.Controls.Panel>元素，请参阅[面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a7001-191">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span> <span data-ttu-id="a7001-192">有关布局详细信息，请参阅[布局](../../../../docs/framework/wpf/advanced/layout.md)。</span><span class="sxs-lookup"><span data-stu-id="a7001-192">For more information about layout, see [Layout](../../../../docs/framework/wpf/advanced/layout.md).</span></span> 
  
 <span data-ttu-id="a7001-193">在部分中，你创建一个单列的表具有三个行和 10 像素边距通过添加到的列和行定义<xref:System.Windows.Controls.Grid>ExpenseItHome.xaml 中。</span><span class="sxs-lookup"><span data-stu-id="a7001-193">In the section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in ExpenseItHome.xaml.</span></span> 
  
1. <span data-ttu-id="a7001-194">打开 ExpenseItHome.xaml。</span><span class="sxs-lookup"><span data-stu-id="a7001-194">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="a7001-195">设置<xref:System.Windows.FrameworkElement.Margin%2A>属性<xref:System.Windows.Controls.Grid>到对应于左侧、 顶部、 右侧和底部边距的"10,0,10,10"的元素。</span><span class="sxs-lookup"><span data-stu-id="a7001-195">Set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10" which corresponds to left, top, right and bottom margins.</span></span> 
  
3. <span data-ttu-id="a7001-196">添加以下[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]之间<xref:System.Windows.Controls.Grid>标记以创建行和列定义。</span><span class="sxs-lookup"><span data-stu-id="a7001-196">Add the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions.</span></span> 
  
    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]  
  
     <span data-ttu-id="a7001-197"><xref:System.Windows.Controls.RowDefinition.Height%2A>的两个行设置为<xref:System.Windows.GridLength.Auto%2A>，将大小调整行这意味着根据行中的内容。</span><span class="sxs-lookup"><span data-stu-id="a7001-197">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A> which means that the rows will be sized base on the content in the rows.</span></span> <span data-ttu-id="a7001-198">默认值<xref:System.Windows.Controls.RowDefinition.Height%2A>是<xref:System.Windows.GridUnitType.Star>调整大小，这意味着将为行的可用空间的加权的比例。</span><span class="sxs-lookup"><span data-stu-id="a7001-198">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row will be a weighted proportion of the available space.</span></span> <span data-ttu-id="a7001-199">例如，如果两行高度均为“*”，则它们各自的高度将会是可用空间的一半。</span><span class="sxs-lookup"><span data-stu-id="a7001-199">For example if two rows each have a height of "*", they will each have a height that is half of the available space.</span></span>  
  
     <span data-ttu-id="a7001-200">你<xref:System.Windows.Controls.Grid>现在应类似下面的 XAML:</span><span class="sxs-lookup"><span data-stu-id="a7001-200">Your <xref:System.Windows.Controls.Grid> should now look like the following XAML:</span></span>  
  
    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]  
  
## <a name="adding-controls"></a><span data-ttu-id="a7001-201">添加控件</span><span class="sxs-lookup"><span data-stu-id="a7001-201">Adding controls</span></span>  
 <span data-ttu-id="a7001-202">在此部分中，主页页面[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]更新以显示用户可从中以显示所选人员的费用报表的人员列表。</span><span class="sxs-lookup"><span data-stu-id="a7001-202">In this section, the home page [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is updated to show a list of people that users can select from to show the expense report for a selected person.</span></span> <span data-ttu-id="a7001-203">控件是允许用户与应用程序交互的 UI 对象。</span><span class="sxs-lookup"><span data-stu-id="a7001-203">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="a7001-204">有关详细信息，请参阅 [控件](../../../../docs/framework/wpf/controls/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a7001-204">For more information, see [Controls](../../../../docs/framework/wpf/controls/index.md).</span></span> 
  
 <span data-ttu-id="a7001-205">若要创建此[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，以下元素添加到 ExpenseItHome.xaml:</span><span class="sxs-lookup"><span data-stu-id="a7001-205">To create this [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], the following elements are added to ExpenseItHome.xaml:</span></span>  
  
-   <span data-ttu-id="a7001-206"><xref:System.Windows.Controls.ListBox>（有关的人员列表）。</span><span class="sxs-lookup"><span data-stu-id="a7001-206"><xref:System.Windows.Controls.ListBox> (for the list of people).</span></span> 
  
-   <span data-ttu-id="a7001-207"><xref:System.Windows.Controls.Label>（对于列表标头）。</span><span class="sxs-lookup"><span data-stu-id="a7001-207"><xref:System.Windows.Controls.Label> (for the list header).</span></span> 
  
-   <span data-ttu-id="a7001-208"><xref:System.Windows.Controls.Button>（若要单击以查看费用报表列表中选择的人员）。</span><span class="sxs-lookup"><span data-stu-id="a7001-208"><xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span> 
  
 <span data-ttu-id="a7001-209">每个控件所在的行中<xref:System.Windows.Controls.Grid>通过设置<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>附加属性。</span><span class="sxs-lookup"><span data-stu-id="a7001-209">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="a7001-210">有关附加属性的详细信息，请参阅[附加属性概述](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a7001-210">For more information about attached properties, see [Attached Properties Overview](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).</span></span> 
  
1. <span data-ttu-id="a7001-211">打开 ExpenseItHome.xaml。</span><span class="sxs-lookup"><span data-stu-id="a7001-211">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="a7001-212">添加以下[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]之间<xref:System.Windows.Controls.Grid>标记。</span><span class="sxs-lookup"><span data-stu-id="a7001-212">Add the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] between the <xref:System.Windows.Controls.Grid> tags.</span></span> 
  
    [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]  
  
3. <span data-ttu-id="a7001-213">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7001-213">Build and run the application.</span></span> 
  
 <span data-ttu-id="a7001-214">下图显示了在本部分中由 XAML 创建的控件。</span><span class="sxs-lookup"><span data-stu-id="a7001-214">The following illustration shows the controls that are created by the XAML in this section.</span></span> 
  
 <span data-ttu-id="a7001-215">![ExpenseIt 示例屏幕快照](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")</span><span class="sxs-lookup"><span data-stu-id="a7001-215">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")</span></span>  
  
## <a name="adding-an-image-and-a-title"></a><span data-ttu-id="a7001-216">添加的映像和标题</span><span class="sxs-lookup"><span data-stu-id="a7001-216">Adding an image and a title</span></span>  
 <span data-ttu-id="a7001-217">在此部分中，主页页面[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]更新使用的映像和页面标题。</span><span class="sxs-lookup"><span data-stu-id="a7001-217">In this section, the home page [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is updated with an image and a page title.</span></span> 
  
1. <span data-ttu-id="a7001-218">打开 ExpenseItHome.xaml。</span><span class="sxs-lookup"><span data-stu-id="a7001-218">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="a7001-219">添加到另一列<xref:System.Windows.Controls.Grid.ColumnDefinitions%2A>带有固定<xref:System.Windows.Controls.ColumnDefinition.Width%2A>为 230 像素。</span><span class="sxs-lookup"><span data-stu-id="a7001-219">Add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels.</span></span> 
  
    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]  
  
3. <span data-ttu-id="a7001-220">添加到另一个行<xref:System.Windows.Controls.Grid.RowDefinitions%2A>。</span><span class="sxs-lookup"><span data-stu-id="a7001-220">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>.</span></span> 
  
    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]  
  
4. <span data-ttu-id="a7001-221">将控件移至第二列中，通过设置<xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>为 1。</span><span class="sxs-lookup"><span data-stu-id="a7001-221">Move the controls to the second column by setting <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> to 1.</span></span> <span data-ttu-id="a7001-222">每个控件下移一行时，通过增加<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>1。</span><span class="sxs-lookup"><span data-stu-id="a7001-222">Move each control down a row, by increasing the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> by 1.</span></span> 
  
    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]  
  
5. <span data-ttu-id="a7001-223">设置<xref:System.Windows.Controls.Panel.Background%2A>的<xref:System.Windows.Controls.Grid>要 watermark.png 图像文件。</span><span class="sxs-lookup"><span data-stu-id="a7001-223">Set the <xref:System.Windows.Controls.Panel.Background%2A> of the <xref:System.Windows.Controls.Grid> to be the watermark.png image file.</span></span> 
  
    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]  
  
6. <span data-ttu-id="a7001-224">之前<xref:System.Windows.Controls.Border>，添加<xref:System.Windows.Controls.Label>"查看费用报表"为页的标题的内容。</span><span class="sxs-lookup"><span data-stu-id="a7001-224">Before the <xref:System.Windows.Controls.Border>, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report" to be the title of the page.</span></span> 
  
    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]  
  
7. <span data-ttu-id="a7001-225">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7001-225">Build and run the application.</span></span> 
  
 <span data-ttu-id="a7001-226">下图显示完成本部分的结果。</span><span class="sxs-lookup"><span data-stu-id="a7001-226">The following illustration shows the results of this section.</span></span> 
  
 <span data-ttu-id="a7001-227">![ExpenseIt 示例屏幕快照](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")</span><span class="sxs-lookup"><span data-stu-id="a7001-227">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")</span></span>  
  
## <a name="adding-code-to-handle-events"></a><span data-ttu-id="a7001-228">添加代码以处理事件</span><span class="sxs-lookup"><span data-stu-id="a7001-228">Adding code to handle events</span></span>  
  
1. <span data-ttu-id="a7001-229">打开 ExpenseItHome.xaml。</span><span class="sxs-lookup"><span data-stu-id="a7001-229">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="a7001-230">添加<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件处理程序<xref:System.Windows.Controls.Button>元素。</span><span class="sxs-lookup"><span data-stu-id="a7001-230">Add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="a7001-231">有关详细信息，请参阅[如何： 创建一个简单的事件处理程序](http://msdn.microsoft.com/en-us/b1456e07-9dec-4354-99cf-18666b64f480)。</span><span class="sxs-lookup"><span data-stu-id="a7001-231">For more information, see [How to: Create a Simple Event Handler](http://msdn.microsoft.com/en-us/b1456e07-9dec-4354-99cf-18666b64f480).</span></span> 
  
    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]  
  
3. <span data-ttu-id="a7001-232">打开 ExpenseItHome.xaml.vb 或 ExpenseItHome.xaml.cs。</span><span class="sxs-lookup"><span data-stu-id="a7001-232">Open ExpenseItHome.xaml.vb or ExpenseItHome.xaml.cs.</span></span> 
  
4. <span data-ttu-id="a7001-233">以下代码添加到<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件处理程序，这会导致窗口导航到 ExpenseReportPage.xaml 文件。</span><span class="sxs-lookup"><span data-stu-id="a7001-233">Add the following code to the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler, which causes the window to navigate to the ExpenseReportPage.xaml file.</span></span> 
  
    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]  
  
## <a name="creating-the-ui-for-expensereportpage"></a><span data-ttu-id="a7001-234">为 ExpenseReportPage 创建 UI</span><span class="sxs-lookup"><span data-stu-id="a7001-234">Creating the UI for ExpenseReportPage</span></span>  
 <span data-ttu-id="a7001-235">ExpenseReportPage.xaml 显示在 ExpenseItHome.xaml 中选择的人员的费用报表。</span><span class="sxs-lookup"><span data-stu-id="a7001-235">ExpenseReportPage.xaml displays the expense report for the person that was selected on the ExpenseItHome.xaml.</span></span> <span data-ttu-id="a7001-236">本部分添加控件并创建[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]的 ExpenseReportPage.xaml。</span><span class="sxs-lookup"><span data-stu-id="a7001-236">This section adds controls and creates the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] for ExpenseReportPage.xaml.</span></span> <span data-ttu-id="a7001-237">本部分还将背景和填充颜色添加到各种[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]元素。</span><span class="sxs-lookup"><span data-stu-id="a7001-237">This section also adds background and fill colors to the various [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements.</span></span> 
  
1. <span data-ttu-id="a7001-238">打开 ExpenseReportPage.xaml。</span><span class="sxs-lookup"><span data-stu-id="a7001-238">Open ExpenseReportPage.xaml.</span></span> 
  
2. <span data-ttu-id="a7001-239">在 <xref:System.Windows.Controls.Grid> 标记之间添加以下 XAML。</span><span class="sxs-lookup"><span data-stu-id="a7001-239">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags.</span></span> 
  
     <span data-ttu-id="a7001-240">此 UI 是类似于在 ExpenseItHome.xaml 上创建，但报表数据将显示在 UI <xref:System.Windows.Controls.DataGrid>。</span><span class="sxs-lookup"><span data-stu-id="a7001-240">This UI is similar to the UI created on ExpenseItHome.xaml except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span> 
  
    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]  
  
3. <span data-ttu-id="a7001-241">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7001-241">Build and run the application.</span></span> 
  
    > [!NOTE]
    >  <span data-ttu-id="a7001-242">如果收到错误<xref:System.Windows.Controls.DataGrid>找不到或不存在，请确保你的项目面向.NET Framework 4 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a7001-242">If you get an error that the <xref:System.Windows.Controls.DataGrid> was not found or does not exist, make sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="a7001-243">有关详细信息，请参阅[如何：面向 .NET Framework 的某个版本](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)。</span><span class="sxs-lookup"><span data-stu-id="a7001-243">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span> 
  
4. <span data-ttu-id="a7001-244">单击**视图**按钮。</span><span class="sxs-lookup"><span data-stu-id="a7001-244">Click the **View** button.</span></span> 
  
     <span data-ttu-id="a7001-245">出现费用报告页。</span><span class="sxs-lookup"><span data-stu-id="a7001-245">The expense report page appears.</span></span> 
  
 <span data-ttu-id="a7001-246">下图显示[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]元素添加到 ExpenseReportPage.xaml。</span><span class="sxs-lookup"><span data-stu-id="a7001-246">The following illustration shows the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements added to ExpenseReportPage.xaml.</span></span> <span data-ttu-id="a7001-247">注意向后导航按钮已启用。</span><span class="sxs-lookup"><span data-stu-id="a7001-247">Notice that the back navigation button is enabled.</span></span> 
  
 <span data-ttu-id="a7001-248">![ExpenseIt 示例屏幕快照](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")</span><span class="sxs-lookup"><span data-stu-id="a7001-248">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")</span></span>  
  
## <a name="styling-controls"></a><span data-ttu-id="a7001-249">设置控件样式</span><span class="sxs-lookup"><span data-stu-id="a7001-249">Styling controls</span></span>  
 <span data-ttu-id="a7001-250">各种元素的外观通常可以为中的相同类型的所有元素相同[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a7001-250">The appearance of various elements can often be the same for all elements of the same type in a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]<span data-ttu-id="a7001-251"> 使用样式，以使外观可在多个元素上重复使用。</span><span class="sxs-lookup"><span data-stu-id="a7001-251"> uses styles to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="a7001-252">可重用性的样式有助于简化[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]创建和管理。</span><span class="sxs-lookup"><span data-stu-id="a7001-252">The reusability of styles helps to simplify [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] creation and management.</span></span> <span data-ttu-id="a7001-253">有关样式的详细信息，请参阅[样式和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)。</span><span class="sxs-lookup"><span data-stu-id="a7001-253">For more information about styles, see [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span> <span data-ttu-id="a7001-254">本部分替换在以前步骤中通过样式定义的按元素划分的属性。</span><span class="sxs-lookup"><span data-stu-id="a7001-254">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span> 
  
1. <span data-ttu-id="a7001-255">打开 Application.xaml 或 App.xaml。</span><span class="sxs-lookup"><span data-stu-id="a7001-255">Open Application.xaml or App.xaml.</span></span> 
  
2. <span data-ttu-id="a7001-256">将以下 XAML 之间添加<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>标记：</span><span class="sxs-lookup"><span data-stu-id="a7001-256">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>  
  
    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]  
  
     <span data-ttu-id="a7001-257">这[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]将添加以下样式：</span><span class="sxs-lookup"><span data-stu-id="a7001-257">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] adds the following styles:</span></span>  
  
    -  <span data-ttu-id="a7001-258">`headerTextStyle`：可设置页标题 <xref:System.Windows.Controls.Label>的格式。</span><span class="sxs-lookup"><span data-stu-id="a7001-258">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span> 
  
    -  <span data-ttu-id="a7001-259">`labelStyle`：可设置 <xref:System.Windows.Controls.Label> 控件的格式。</span><span class="sxs-lookup"><span data-stu-id="a7001-259">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span> 
  
    -  <span data-ttu-id="a7001-260">`columnHeaderStyle`：可设置 <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>的格式。</span><span class="sxs-lookup"><span data-stu-id="a7001-260">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span> 
  
    -  <span data-ttu-id="a7001-261">`listHeaderStyle`：可设置列表标头 <xref:System.Windows.Controls.Border> 控件的格式。</span><span class="sxs-lookup"><span data-stu-id="a7001-261">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span> 
  
    -  <span data-ttu-id="a7001-262">`listHeaderTextStyle`： 若要设置列表标头的格式<xref:System.Windows.Controls.Label>。</span><span class="sxs-lookup"><span data-stu-id="a7001-262">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span> 
  
    -  <span data-ttu-id="a7001-263">`buttonStyle`： 若要设置格式<xref:System.Windows.Controls.Button>ExpenseItHome.xaml 上。</span><span class="sxs-lookup"><span data-stu-id="a7001-263">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on ExpenseItHome.xaml.</span></span> 
  
     <span data-ttu-id="a7001-264">请注意，样式是资源和子级<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>属性元素。</span><span class="sxs-lookup"><span data-stu-id="a7001-264">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="a7001-265">在此位置中，这些样式将应用到应用程序中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="a7001-265">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="a7001-266">有关使用中的资源的示例[!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]应用程序，请参阅[使用应用程序资源](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="a7001-266">For an example of using resources in a [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] application, see [Use Application Resources](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).</span></span> 
  
3. <span data-ttu-id="a7001-267">打开 ExpenseItHome.xaml。</span><span class="sxs-lookup"><span data-stu-id="a7001-267">Open ExpenseItHome.xaml.</span></span> 
  
4. <span data-ttu-id="a7001-268">替换之间的所有内容<xref:System.Windows.Controls.Grid>使用以下 XAML 元素。</span><span class="sxs-lookup"><span data-stu-id="a7001-268">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML.</span></span> 
  
    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]  
  
     <span data-ttu-id="a7001-269">应用样式会删除和替换定义每个控件外观的属性（如 <xref:System.Windows.VerticalAlignment> 和 <xref:System.Windows.Media.FontFamily> 。</span><span class="sxs-lookup"><span data-stu-id="a7001-269">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="a7001-270">例如，`headerTextStyle`应用于"查看费用报表" <xref:System.Windows.Controls.Label>。</span><span class="sxs-lookup"><span data-stu-id="a7001-270">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span> 
  
5. <span data-ttu-id="a7001-271">打开 ExpenseReportPage.xaml。</span><span class="sxs-lookup"><span data-stu-id="a7001-271">Open ExpenseReportPage.xaml.</span></span> 
  
6. <span data-ttu-id="a7001-272">替换之间的所有内容<xref:System.Windows.Controls.Grid>使用以下 XAML 元素。</span><span class="sxs-lookup"><span data-stu-id="a7001-272">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML.</span></span> 
  
    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]  
  
     <span data-ttu-id="a7001-273">这会将样式添加到 <xref:System.Windows.Controls.Label> 和 <xref:System.Windows.Controls.Border> 元素。</span><span class="sxs-lookup"><span data-stu-id="a7001-273">This adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span> 
  
7. <span data-ttu-id="a7001-274">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7001-274">Build and run the application.</span></span> 
  
     <span data-ttu-id="a7001-275">在添加后[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]在此部分中，应用程序看上去相同一样使用样式更新之前。</span><span class="sxs-lookup"><span data-stu-id="a7001-275">After adding the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in this section, the application looks the same as it did before being updated with styles.</span></span> 
  
## <a name="binding-data-to-a-control"></a><span data-ttu-id="a7001-276">将数据绑定到控件</span><span class="sxs-lookup"><span data-stu-id="a7001-276">Binding data to a control</span></span>  
 <span data-ttu-id="a7001-277">在本部分中，你创建[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]绑定到各种控件的数据。</span><span class="sxs-lookup"><span data-stu-id="a7001-277">In this section, you create the [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] data that is bound to various controls.</span></span> 
  
1. <span data-ttu-id="a7001-278">打开 ExpenseItHome.xaml。</span><span class="sxs-lookup"><span data-stu-id="a7001-278">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="a7001-279">在起始<xref:System.Windows.Controls.Grid>元素中，添加以下 XAML，以创建<xref:System.Windows.Data.XmlDataProvider>包含每人数据。</span><span class="sxs-lookup"><span data-stu-id="a7001-279">After the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person.</span></span> 
  
     <span data-ttu-id="a7001-280">作为创建数据<xref:System.Windows.Controls.Grid>资源。</span><span class="sxs-lookup"><span data-stu-id="a7001-280">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="a7001-281">这通常会作为文件加载，但为简单起见数据以内联方式添加。</span><span class="sxs-lookup"><span data-stu-id="a7001-281">Normally this would be loaded as a file, but for simplicity the data is added inline.</span></span> 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
3. <span data-ttu-id="a7001-282">在<xref:System.Windows.Controls.Grid>资源，添加以下<xref:System.Windows.DataTemplate>，它定义如何显示中的数据<xref:System.Windows.Controls.ListBox>。</span><span class="sxs-lookup"><span data-stu-id="a7001-282">In the <xref:System.Windows.Controls.Grid> resource, add the following <xref:System.Windows.DataTemplate>, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="a7001-283">有关数据模板的详细信息，请参阅[数据模板化概述](../../../../docs/framework/wpf/data/data-templating-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a7001-283">For more information about data templates, see [Data Templating Overview](../../../../docs/framework/wpf/data/data-templating-overview.md).</span></span> 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
4. <span data-ttu-id="a7001-284">将现有<xref:System.Windows.Controls.ListBox>使用以下 XAML。</span><span class="sxs-lookup"><span data-stu-id="a7001-284">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML.</span></span> 
  
    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]  
  
     <span data-ttu-id="a7001-285">此 XAML 将绑定<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>属性<xref:System.Windows.Controls.ListBox>到数据源并应用数据模板作为<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>。</span><span class="sxs-lookup"><span data-stu-id="a7001-285">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span> 
  
## <a name="connecting-data-to-controls"></a><span data-ttu-id="a7001-286">将数据连接到控件</span><span class="sxs-lookup"><span data-stu-id="a7001-286">Connecting data to controls</span></span>  
 <span data-ttu-id="a7001-287">在本部分中，你编写检索 ExpenseItHome.xaml 页面上的用户的列表中选择并将其引用的构造函数传递的当前项的代码`ExpenseReportPage`期间实例化。</span><span class="sxs-lookup"><span data-stu-id="a7001-287">In this section, you write the code that retrieves the current item that is selected in the list of people on the ExpenseItHome.xaml page, and passes its reference to the constructor of `ExpenseReportPage` during instantiation.</span></span> <span data-ttu-id="a7001-288">`ExpenseReportPage` 通过传递项设置数据上下文，该项是在 ExpenseReportPage.xaml 中定义的控件要绑定到的对象。</span><span class="sxs-lookup"><span data-stu-id="a7001-288">`ExpenseReportPage` sets its data context with the passed item, which is what the controls defined in ExpenseReportPage.xaml will bind to.</span></span> 
  
1. <span data-ttu-id="a7001-289">打开 ExpenseReportPage.xaml.vb 或 ExpenseReportPage.xaml.cs。</span><span class="sxs-lookup"><span data-stu-id="a7001-289">Open ExpenseReportPage.xaml.vb or ExpenseReportPage.xaml.cs.</span></span> 
  
2. <span data-ttu-id="a7001-290">添加获取对象的构造函数，以便传递所选人员的费用报表数据。</span><span class="sxs-lookup"><span data-stu-id="a7001-290">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span> 
  
    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]  
  
3. <span data-ttu-id="a7001-291">打开 ExpenseItHome.xaml.vb 或 ExpenseItHome.xaml.cs。</span><span class="sxs-lookup"><span data-stu-id="a7001-291">Open ExpenseItHome.xaml.vb or ExpenseItHome.xaml.cs.</span></span> 
  
4. <span data-ttu-id="a7001-292">更改<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件处理程序以调用新的构造函数传递所选人员的费用报表数据。</span><span class="sxs-lookup"><span data-stu-id="a7001-292">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span> 
  
    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]  
  
## <a name="styling-data-with-data-templates"></a><span data-ttu-id="a7001-293">使用数据模板的样式数据</span><span class="sxs-lookup"><span data-stu-id="a7001-293">Styling data with data templates</span></span>  
 <span data-ttu-id="a7001-294">在本部分中，你将更新[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]有关数据中的每个项绑定使用数据模板的列表。</span><span class="sxs-lookup"><span data-stu-id="a7001-294">In this section, you update the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] for each item in the data bound lists by using data templates.</span></span> 
  
1. <span data-ttu-id="a7001-295">打开 ExpenseReportPage.xaml。</span><span class="sxs-lookup"><span data-stu-id="a7001-295">Open ExpenseReportPage.xaml.</span></span> 
  
2. <span data-ttu-id="a7001-296">将绑定的内容的"名称"和"部门"<xref:System.Windows.Controls.Label>元素与适当的数据源属性。</span><span class="sxs-lookup"><span data-stu-id="a7001-296">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="a7001-297">有关数据绑定的详细信息，请参阅[数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a7001-297">For more information about data binding, see [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span> 
  
    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]  
  
3. <span data-ttu-id="a7001-298">在起始<xref:System.Windows.Controls.Grid>元素中，添加以下数据模板，定义如何显示费用报表数据。</span><span class="sxs-lookup"><span data-stu-id="a7001-298">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data.</span></span>  
    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]  
  
4. <span data-ttu-id="a7001-299">应用到模板<xref:System.Windows.Controls.DataGrid>列显示费用报表数据。</span><span class="sxs-lookup"><span data-stu-id="a7001-299">Apply the templates to the <xref:System.Windows.Controls.DataGrid> columns that display the expense report data.</span></span> 
  
    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]  
  
5. <span data-ttu-id="a7001-300">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7001-300">Build and run the application.</span></span> 
  
6. <span data-ttu-id="a7001-301">选择 person 并单击**视图**按钮。</span><span class="sxs-lookup"><span data-stu-id="a7001-301">Select a person and click the **View** button.</span></span> 
  
 <span data-ttu-id="a7001-302">下图显示具有所应用的控件、布局、样式、数据绑定和数据模板的 ExpenseIt 应用程序的两个页面。</span><span class="sxs-lookup"><span data-stu-id="a7001-302">The following illustration shows both pages of the ExpenseIt application with controls, layout, styles, data binding, and data templates applied.</span></span> 
  
 <span data-ttu-id="a7001-303">![ExpenseIt 示例屏幕快照](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")</span><span class="sxs-lookup"><span data-stu-id="a7001-303">![ExpenseIt sample screen shots](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="a7001-304">最佳实践</span><span class="sxs-lookup"><span data-stu-id="a7001-304">Best practices</span></span>  
 <span data-ttu-id="a7001-305">本示例演示了 WPF 的特定功能，因此不遵循应用程序开发的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="a7001-305">This sample demonstrates a specific feature of WPF and, consequently, does not follow application development best practices.</span></span> <span data-ttu-id="a7001-306">有关全面介绍[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]和[!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]应用程序开发最佳做法，根据需要参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="a7001-306">For comprehensive coverage of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] and the [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] application development best practices, see the following topics as appropriate:</span></span>  
  
-   <span data-ttu-id="a7001-307">辅助功能 - [辅助功能最佳做法](../../../../docs/framework/ui-automation/accessibility-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="a7001-307">Accessibility - [Accessibility Best Practices](../../../../docs/framework/ui-automation/accessibility-best-practices.md)</span></span>  
  
-   <span data-ttu-id="a7001-308">安全-[安全](../../../../docs/framework/wpf/security-wpf.md)</span><span class="sxs-lookup"><span data-stu-id="a7001-308">Security - [Security](../../../../docs/framework/wpf/security-wpf.md)</span></span>  
  
-   <span data-ttu-id="a7001-309">本地化 - [WPF 全球化和本地化概述](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a7001-309">Localization - [WPF Globalization and Localization Overview](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)</span></span>  
  
-   <span data-ttu-id="a7001-310">性能 - [优化 WPF 应用程序性能](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)</span><span class="sxs-lookup"><span data-stu-id="a7001-310">Performance - [Optimizing WPF Application Performance](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)</span></span>  
  
## <a name="whats-next"></a><span data-ttu-id="a7001-311">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a7001-311">What's next</span></span>  
 <span data-ttu-id="a7001-312">你现在有多种方法来创建[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]使用[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a7001-312">You now have a number of techniques at your disposal for creating a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] using [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span> <span data-ttu-id="a7001-313">现在你应有的数据绑定的基本构建基块全面的了解[!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7001-313">You should now have a broad understanding of the basic building blocks of a data-bound [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] application.</span></span> <span data-ttu-id="a7001-314">本主题并不详尽，但希望你现在也能够意识到你可以自己发现本主题尚未介绍的技术。</span><span class="sxs-lookup"><span data-stu-id="a7001-314">This topic is by no means exhaustive, but hopefully you also now have a sense of some of the possibilities you might discover on your own beyond the techniques in this topic.</span></span> 
  
 <span data-ttu-id="a7001-315">有关 WPF 体系结构和编程模型的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="a7001-315">For more information about the WPF architecture and programming models, see the following topics:</span></span>  
  
-   [<span data-ttu-id="a7001-316">WPF 体系结构</span><span class="sxs-lookup"><span data-stu-id="a7001-316">WPF Architecture</span></span>](../../../../docs/framework/wpf/advanced/wpf-architecture.md)  
  
-   [<span data-ttu-id="a7001-317">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="a7001-317">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
  
-   [<span data-ttu-id="a7001-318">依赖项属性概述</span><span class="sxs-lookup"><span data-stu-id="a7001-318">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
  
-   [<span data-ttu-id="a7001-319">布局</span><span class="sxs-lookup"><span data-stu-id="a7001-319">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)  
  
 <span data-ttu-id="a7001-320">有关创建应用程序的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="a7001-320">For more information about creating applications, see the following topics:</span></span>  
  
-   [<span data-ttu-id="a7001-321">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="a7001-321">Application Development</span></span>](../../../../docs/framework/wpf/app-development/index.md)  
  
-   [<span data-ttu-id="a7001-322">控件</span><span class="sxs-lookup"><span data-stu-id="a7001-322">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)  
  
-   [<span data-ttu-id="a7001-323">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="a7001-323">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
  
-   [<span data-ttu-id="a7001-324">图形和多媒体</span><span class="sxs-lookup"><span data-stu-id="a7001-324">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
  
-   [<span data-ttu-id="a7001-325">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="a7001-325">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
  
## <a name="see-also"></a><span data-ttu-id="a7001-326">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7001-326">See also</span></span>  
 [<span data-ttu-id="a7001-327">面板概述</span><span class="sxs-lookup"><span data-stu-id="a7001-327">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="a7001-328">数据模板化概述</span><span class="sxs-lookup"><span data-stu-id="a7001-328">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="a7001-329">生成 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="a7001-329">Building a WPF Application</span></span>](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [<span data-ttu-id="a7001-330">样式和模板</span><span class="sxs-lookup"><span data-stu-id="a7001-330">Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/styles-and-templates.md)
