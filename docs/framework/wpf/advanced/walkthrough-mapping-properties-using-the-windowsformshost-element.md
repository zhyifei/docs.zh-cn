---
title: "演练：使用 WindowsFormsHost 元素映射属性"
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
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f566d41ff1ffa07a2f52641ba05e48dfa604cfc9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a><span data-ttu-id="d3601-102">演练：使用 WindowsFormsHost 元素映射属性</span><span class="sxs-lookup"><span data-stu-id="d3601-102">Walkthrough: Mapping Properties Using the WindowsFormsHost Element</span></span>
<span data-ttu-id="d3601-103">本演练演示如何使用<xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>属性映射[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]到上一个承载的相应属性的属性[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件。</span><span class="sxs-lookup"><span data-stu-id="d3601-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> property to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
 <span data-ttu-id="d3601-104">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="d3601-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="d3601-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="d3601-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="d3601-106">定义应用程序布局。</span><span class="sxs-lookup"><span data-stu-id="d3601-106">Defining the application layout.</span></span>  
  
-   <span data-ttu-id="d3601-107">定义新的属性映射。</span><span class="sxs-lookup"><span data-stu-id="d3601-107">Defining a new property mapping.</span></span>  
  
-   <span data-ttu-id="d3601-108">删除默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="d3601-108">Removing a default property mapping.</span></span>  
  
-   <span data-ttu-id="d3601-109">替换默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="d3601-109">Replacing a default property mapping.</span></span>  
  
-   <span data-ttu-id="d3601-110">扩展默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="d3601-110">Extending a default property mapping.</span></span>  
  
 <span data-ttu-id="d3601-111">本演练的任务的完整代码清单，请参阅[映射属性使用 WindowsFormsHost 元素示例](http://go.microsoft.com/fwlink/?LinkID=160019)。</span><span class="sxs-lookup"><span data-stu-id="d3601-111">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the WindowsFormsHost Element Sample](http://go.microsoft.com/fwlink/?LinkID=160019).</span></span>  
  
 <span data-ttu-id="d3601-112">完成后，你将能够映射[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]到上一个承载的相应属性的属性[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件。</span><span class="sxs-lookup"><span data-stu-id="d3601-112">When you are finished, you will be able to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d3601-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="d3601-113">Prerequisites</span></span>  
 <span data-ttu-id="d3601-114">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="d3601-114">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="d3601-115">。</span><span class="sxs-lookup"><span data-stu-id="d3601-115">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="d3601-116">创建项目</span><span class="sxs-lookup"><span data-stu-id="d3601-116">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="d3601-117">创建并设置项目</span><span class="sxs-lookup"><span data-stu-id="d3601-117">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="d3601-118">创建一个名为的 WPF 应用程序项目`PropertyMappingWithWfhSample`。</span><span class="sxs-lookup"><span data-stu-id="d3601-118">Create a WPF Application project named `PropertyMappingWithWfhSample`.</span></span>  
  
2.  <span data-ttu-id="d3601-119">在解决方案资源管理器，将添加到名为 WindowsFormsIntegration.dll 的 WindowsFormsIntegration 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d3601-119">In Solution Explorer, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>  
  
3.  <span data-ttu-id="d3601-120">在解决方案资源管理器，将添加对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d3601-120">In Solution Explorer, add references to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="defining-the-application-layout"></a><span data-ttu-id="d3601-121">定义应用程序布局</span><span class="sxs-lookup"><span data-stu-id="d3601-121">Defining the Application Layout</span></span>  
 <span data-ttu-id="d3601-122">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-基于应用程序使用<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素来承载[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件。</span><span class="sxs-lookup"><span data-stu-id="d3601-122">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-define-the-application-layout"></a><span data-ttu-id="d3601-123">定义应用程序布局</span><span class="sxs-lookup"><span data-stu-id="d3601-123">To define the application layout</span></span>  
  
1.  <span data-ttu-id="d3601-124">打开在 Window1.xaml [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d3601-124">Open Window1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
2.  <span data-ttu-id="d3601-125">用下面的代码替换现有代码。</span><span class="sxs-lookup"><span data-stu-id="d3601-125">Replace the existing code with the following code.</span></span>  
  
     [!code-xaml[PropertyMappingWithWfhSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]  
  
3.  <span data-ttu-id="d3601-126">在代码编辑器中打开 Window1.xaml.cs。</span><span class="sxs-lookup"><span data-stu-id="d3601-126">Open Window1.xaml.cs in the Code Editor.</span></span>  
  
4.  <span data-ttu-id="d3601-127">在该文件顶部导入以下命名空间。</span><span class="sxs-lookup"><span data-stu-id="d3601-127">At the top of the file, import the following namespaces.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]  
  
## <a name="defining-a-new-property-mapping"></a><span data-ttu-id="d3601-128">定义新的属性映射</span><span class="sxs-lookup"><span data-stu-id="d3601-128">Defining a New Property Mapping</span></span>  
 <span data-ttu-id="d3601-129"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素提供了一些默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="d3601-129">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element provides several default property mappings.</span></span> <span data-ttu-id="d3601-130">通过调用将添加新的属性映射<xref:System.Windows.Forms.Integration.PropertyMap.Add%2A>方法<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的<xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>。</span><span class="sxs-lookup"><span data-stu-id="d3601-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-define-a-new-property-mapping"></a><span data-ttu-id="d3601-131">定义新的属性映射</span><span class="sxs-lookup"><span data-stu-id="d3601-131">To define a new property mapping</span></span>  
  
-   <span data-ttu-id="d3601-132">将以下代码复制到的定义`Window1`类。</span><span class="sxs-lookup"><span data-stu-id="d3601-132">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]  
  
     <span data-ttu-id="d3601-133">`AddClipMapping`方法将添加的新映射<xref:System.Windows.UIElement.Clip%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="d3601-133">The `AddClipMapping` method adds a new mapping for the <xref:System.Windows.UIElement.Clip%2A> property.</span></span>  
  
     <span data-ttu-id="d3601-134">`OnClipChange`方法将转换<xref:System.Windows.UIElement.Clip%2A>属性[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="d3601-134">The `OnClipChange` method translates the <xref:System.Windows.UIElement.Clip%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> property.</span></span>  
  
     <span data-ttu-id="d3601-135">`Window1_SizeChanged`方法可处理窗口的<xref:System.Windows.FrameworkElement.SizeChanged>事件并调整其大小以适合应用程序窗口的剪辑区域。</span><span class="sxs-lookup"><span data-stu-id="d3601-135">The `Window1_SizeChanged` method handles the window's <xref:System.Windows.FrameworkElement.SizeChanged> event and sizes the clipping region to fit the application window.</span></span>  
  
## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="d3601-136">删除默认属性映射</span><span class="sxs-lookup"><span data-stu-id="d3601-136">Removing a Default Property Mapping</span></span>  
 <span data-ttu-id="d3601-137">通过调用来移除默认属性映射<xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A>方法<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的<xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>。</span><span class="sxs-lookup"><span data-stu-id="d3601-137">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="d3601-138">删除默认属性映射</span><span class="sxs-lookup"><span data-stu-id="d3601-138">To remove a default property mapping</span></span>  
  
-   <span data-ttu-id="d3601-139">将以下代码复制到的定义`Window1`类。</span><span class="sxs-lookup"><span data-stu-id="d3601-139">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]  
  
     <span data-ttu-id="d3601-140">`RemoveCursorMapping`方法删除默认映射<xref:System.Windows.FrameworkElement.Cursor%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="d3601-140">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.FrameworkElement.Cursor%2A> property.</span></span>  
  
## <a name="replacing-a-default-property-mapping"></a><span data-ttu-id="d3601-141">替换默认属性映射</span><span class="sxs-lookup"><span data-stu-id="d3601-141">Replacing a Default Property Mapping</span></span>  
 <span data-ttu-id="d3601-142">通过删除默认映射和调用来替换默认属性映射<xref:System.Windows.Forms.Integration.PropertyMap.Add%2A>方法<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的<xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>。</span><span class="sxs-lookup"><span data-stu-id="d3601-142">Replace a default property mapping by removing the default mapping and calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-replace-a-default-property-mapping"></a><span data-ttu-id="d3601-143">替换默认属性映射</span><span class="sxs-lookup"><span data-stu-id="d3601-143">To replace a default property mapping</span></span>  
  
-   <span data-ttu-id="d3601-144">将以下代码复制到的定义`Window1`类。</span><span class="sxs-lookup"><span data-stu-id="d3601-144">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]  
  
     <span data-ttu-id="d3601-145">`ReplaceFlowDirectionMapping`方法替换的默认映射<xref:System.Windows.FrameworkElement.FlowDirection%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="d3601-145">The `ReplaceFlowDirectionMapping` method replaces the default mapping for the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property.</span></span>  
  
     <span data-ttu-id="d3601-146">`OnFlowDirectionChange`方法将转换<xref:System.Windows.FrameworkElement.FlowDirection%2A>属性[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="d3601-146">The `OnFlowDirectionChange` method translates the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> property.</span></span>  
  
     <span data-ttu-id="d3601-147">`cb_CheckedChanged`方法将处理<xref:System.Windows.Forms.CheckBox.CheckedChanged>上的事件<xref:System.Windows.Forms.CheckBox>控件。</span><span class="sxs-lookup"><span data-stu-id="d3601-147">The `cb_CheckedChanged` method handles the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event on the <xref:System.Windows.Forms.CheckBox> control.</span></span> <span data-ttu-id="d3601-148">它将分配<xref:System.Windows.FrameworkElement.FlowDirection%2A>属性基于的值<xref:System.Windows.Forms.CheckBox.CheckState%2A>属性</span><span class="sxs-lookup"><span data-stu-id="d3601-148">It assigns the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property based on the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property</span></span>  
  
## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="d3601-149">扩展默认属性映射</span><span class="sxs-lookup"><span data-stu-id="d3601-149">Extending a Default Property Mapping</span></span>  
 <span data-ttu-id="d3601-150">可以使用默认属性映射，并使用自己的映射对其进行扩展。</span><span class="sxs-lookup"><span data-stu-id="d3601-150">You can use a default property mapping and also extend it with your own mapping.</span></span>  
  
#### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="d3601-151">扩展默认属性映射</span><span class="sxs-lookup"><span data-stu-id="d3601-151">To extend a default property mapping</span></span>  
  
-   <span data-ttu-id="d3601-152">将以下代码复制到的定义`Window1`类。</span><span class="sxs-lookup"><span data-stu-id="d3601-152">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]  
  
     <span data-ttu-id="d3601-153">`ExtendBackgroundMapping`方法将自定义的属性转换器添加到现有<xref:System.Windows.Controls.Control.Background%2A>属性映射。</span><span class="sxs-lookup"><span data-stu-id="d3601-153">The `ExtendBackgroundMapping` method adds a custom property translator to the existing <xref:System.Windows.Controls.Control.Background%2A> property mapping.</span></span>  
  
     <span data-ttu-id="d3601-154">`OnBackgroundChange`方法将托管控件的特定映像<xref:System.Windows.Forms.Control.BackgroundImage%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="d3601-154">The `OnBackgroundChange` method assigns a specific image to the hosted control's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span> <span data-ttu-id="d3601-155">`OnBackgroundChange`应用的默认属性映射后调用方法。</span><span class="sxs-lookup"><span data-stu-id="d3601-155">The `OnBackgroundChange` method is called after the default property mapping is applied.</span></span>  
  
## <a name="initializing-your-property-mappings"></a><span data-ttu-id="d3601-156">初始化属性映射</span><span class="sxs-lookup"><span data-stu-id="d3601-156">Initializing Your Property Mappings</span></span>  
 <span data-ttu-id="d3601-157">通过调用前面所述的方法中设置属性映射<xref:System.Windows.FrameworkElement.Loaded>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d3601-157">Set up your property mappings by calling the previously described methods in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>  
  
#### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="d3601-158">初始化属性映射</span><span class="sxs-lookup"><span data-stu-id="d3601-158">To initialize your property mappings</span></span>  
  
1.  <span data-ttu-id="d3601-159">将以下代码复制到的定义`Window1`类。</span><span class="sxs-lookup"><span data-stu-id="d3601-159">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]  
  
     <span data-ttu-id="d3601-160">`WindowLoaded`方法将处理<xref:System.Windows.FrameworkElement.Loaded>事件并执行以下初始化。</span><span class="sxs-lookup"><span data-stu-id="d3601-160">The `WindowLoaded` method handles the <xref:System.Windows.FrameworkElement.Loaded> event and performs the following initialization.</span></span>  
  
    -   <span data-ttu-id="d3601-161">创建[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox>控件。</span><span class="sxs-lookup"><span data-stu-id="d3601-161">Creates a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> control.</span></span>  
  
    -   <span data-ttu-id="d3601-162">调用先前在演练中定义的方法来设置属性映射。</span><span class="sxs-lookup"><span data-stu-id="d3601-162">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>  
  
    -   <span data-ttu-id="d3601-163">将初始值分配给映射的属性。</span><span class="sxs-lookup"><span data-stu-id="d3601-163">Assigns initial values to the mapped properties.</span></span>  
  
2.  <span data-ttu-id="d3601-164">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3601-164">Press F5 to build and run the application.</span></span> <span data-ttu-id="d3601-165">单击复选框，以查看的效果<xref:System.Windows.FrameworkElement.FlowDirection%2A>映射。</span><span class="sxs-lookup"><span data-stu-id="d3601-165">Click the check box to see the effect of the <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span></span> <span data-ttu-id="d3601-166">单击复选框时，布局会反转其左右方向。</span><span class="sxs-lookup"><span data-stu-id="d3601-166">When you click the check box, the layout reverses its left-right orientation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3601-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3601-167">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="d3601-168">Windows 窗体和 WPF 属性映射</span><span class="sxs-lookup"><span data-stu-id="d3601-168">Windows Forms and WPF Property Mapping</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [<span data-ttu-id="d3601-169">WPF 设计器</span><span class="sxs-lookup"><span data-stu-id="d3601-169">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="d3601-170">演练：在 WPF 中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="d3601-170">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
