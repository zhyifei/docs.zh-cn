---
title: 演练：使用 WindowsFormsHost 元素映射属性
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: 943137017dcc1f8b347441669add13c3ab056f7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493646"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a><span data-ttu-id="7104b-102">演练：使用 WindowsFormsHost 元素映射属性</span><span class="sxs-lookup"><span data-stu-id="7104b-102">Walkthrough: Mapping Properties Using the WindowsFormsHost Element</span></span>

<span data-ttu-id="7104b-103">本演练演示如何使用<xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>属性将映射[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]属性设置为上托管的相应属性[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件。</span><span class="sxs-lookup"><span data-stu-id="7104b-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> property to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

<span data-ttu-id="7104b-104">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="7104b-104">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="7104b-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="7104b-105">Creating the project.</span></span>

-   <span data-ttu-id="7104b-106">定义应用程序布局。</span><span class="sxs-lookup"><span data-stu-id="7104b-106">Defining the application layout.</span></span>

-   <span data-ttu-id="7104b-107">定义新的属性映射。</span><span class="sxs-lookup"><span data-stu-id="7104b-107">Defining a new property mapping.</span></span>

-   <span data-ttu-id="7104b-108">删除默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="7104b-108">Removing a default property mapping.</span></span>

-   <span data-ttu-id="7104b-109">替换默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="7104b-109">Replacing a default property mapping.</span></span>

-   <span data-ttu-id="7104b-110">扩展默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="7104b-110">Extending a default property mapping.</span></span>

<span data-ttu-id="7104b-111">在本演练中所涉及任务的完整代码列表，请参阅[映射属性使用 WindowsFormsHost 元素示例](https://go.microsoft.com/fwlink/?LinkID=160019)。</span><span class="sxs-lookup"><span data-stu-id="7104b-111">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the WindowsFormsHost Element Sample](https://go.microsoft.com/fwlink/?LinkID=160019).</span></span>

<span data-ttu-id="7104b-112">完成后，你将能够映射[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]上托管的相应属性的属性[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件。</span><span class="sxs-lookup"><span data-stu-id="7104b-112">When you are finished, you will be able to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7104b-113">系统必备</span><span class="sxs-lookup"><span data-stu-id="7104b-113">Prerequisites</span></span>

<span data-ttu-id="7104b-114">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="7104b-114">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="7104b-115">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="7104b-115">Visual Studio 2017</span></span>

## <a name="create-and-set-up-the-project"></a><span data-ttu-id="7104b-116">创建并设置项目</span><span class="sxs-lookup"><span data-stu-id="7104b-116">Create and set up the project</span></span>

1.  <span data-ttu-id="7104b-117">创建**WPF 应用程序**名为项目`PropertyMappingWithWfhSample`。</span><span class="sxs-lookup"><span data-stu-id="7104b-117">Create a **WPF App** project named `PropertyMappingWithWfhSample`.</span></span>

2.  <span data-ttu-id="7104b-118">在中**解决方案资源管理器**，添加对 WindowsFormsIntegration 程序集，它名为 WindowsFormsIntegration.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="7104b-118">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3.  <span data-ttu-id="7104b-119">在中**解决方案资源管理器**，添加对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="7104b-119">In **Solution Explorer**, add references to the System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="defining-the-application-layout"></a><span data-ttu-id="7104b-120">定义应用程序布局</span><span class="sxs-lookup"><span data-stu-id="7104b-120">Defining the Application Layout</span></span>

<span data-ttu-id="7104b-121">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-基于应用程序使用<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素来承载[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件。</span><span class="sxs-lookup"><span data-stu-id="7104b-121">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

### <a name="to-define-the-application-layout"></a><span data-ttu-id="7104b-122">定义应用程序布局</span><span class="sxs-lookup"><span data-stu-id="7104b-122">To define the application layout</span></span>

1.  <span data-ttu-id="7104b-123">打开 Window1.xaml 中的[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7104b-123">Open Window1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

2.  <span data-ttu-id="7104b-124">用下面的代码替换现有代码。</span><span class="sxs-lookup"><span data-stu-id="7104b-124">Replace the existing code with the following code.</span></span>

     [!code-xaml[PropertyMappingWithWfhSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3.  <span data-ttu-id="7104b-125">在代码编辑器中打开 Window1.xaml.cs。</span><span class="sxs-lookup"><span data-stu-id="7104b-125">Open Window1.xaml.cs in the Code Editor.</span></span>

4.  <span data-ttu-id="7104b-126">在该文件顶部导入以下命名空间。</span><span class="sxs-lookup"><span data-stu-id="7104b-126">At the top of the file, import the following namespaces.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a><span data-ttu-id="7104b-127">定义新的属性映射</span><span class="sxs-lookup"><span data-stu-id="7104b-127">Defining a New Property Mapping</span></span>

<span data-ttu-id="7104b-128"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素提供了一些默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="7104b-128">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element provides several default property mappings.</span></span> <span data-ttu-id="7104b-129">通过调用添加新的属性映射<xref:System.Windows.Forms.Integration.PropertyMap.Add%2A>方法<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的<xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>。</span><span class="sxs-lookup"><span data-stu-id="7104b-129">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-define-a-new-property-mapping"></a><span data-ttu-id="7104b-130">定义新的属性映射</span><span class="sxs-lookup"><span data-stu-id="7104b-130">To define a new property mapping</span></span>

-   <span data-ttu-id="7104b-131">将以下代码复制到用于定义`Window1`类。</span><span class="sxs-lookup"><span data-stu-id="7104b-131">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     <span data-ttu-id="7104b-132">`AddClipMapping`方法将添加的新映射<xref:System.Windows.UIElement.Clip%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7104b-132">The `AddClipMapping` method adds a new mapping for the <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="7104b-133">`OnClipChange`方法将转换<xref:System.Windows.UIElement.Clip%2A>属性设置为[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7104b-133">The `OnClipChange` method translates the <xref:System.Windows.UIElement.Clip%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="7104b-134">`Window1_SizeChanged`方法处理窗口的<xref:System.Windows.FrameworkElement.SizeChanged>事件并调整其大小以适应应用程序窗口的剪辑区域。</span><span class="sxs-lookup"><span data-stu-id="7104b-134">The `Window1_SizeChanged` method handles the window's <xref:System.Windows.FrameworkElement.SizeChanged> event and sizes the clipping region to fit the application window.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="7104b-135">删除默认属性映射</span><span class="sxs-lookup"><span data-stu-id="7104b-135">Removing a Default Property Mapping</span></span>

<span data-ttu-id="7104b-136">通过调用来移除默认属性映射<xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A>方法<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的<xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>。</span><span class="sxs-lookup"><span data-stu-id="7104b-136">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="7104b-137">删除默认属性映射</span><span class="sxs-lookup"><span data-stu-id="7104b-137">To remove a default property mapping</span></span>

-   <span data-ttu-id="7104b-138">将以下代码复制到用于定义`Window1`类。</span><span class="sxs-lookup"><span data-stu-id="7104b-138">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     <span data-ttu-id="7104b-139">`RemoveCursorMapping`方法删除默认映射<xref:System.Windows.FrameworkElement.Cursor%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7104b-139">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.FrameworkElement.Cursor%2A> property.</span></span>

## <a name="replacing-a-default-property-mapping"></a><span data-ttu-id="7104b-140">替换默认属性映射</span><span class="sxs-lookup"><span data-stu-id="7104b-140">Replacing a Default Property Mapping</span></span>

<span data-ttu-id="7104b-141">通过删除默认映射和调用来替换默认属性映射<xref:System.Windows.Forms.Integration.PropertyMap.Add%2A>方法<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的<xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>。</span><span class="sxs-lookup"><span data-stu-id="7104b-141">Replace a default property mapping by removing the default mapping and calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-replace-a-default-property-mapping"></a><span data-ttu-id="7104b-142">替换默认属性映射</span><span class="sxs-lookup"><span data-stu-id="7104b-142">To replace a default property mapping</span></span>

-   <span data-ttu-id="7104b-143">将以下代码复制到用于定义`Window1`类。</span><span class="sxs-lookup"><span data-stu-id="7104b-143">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     <span data-ttu-id="7104b-144">`ReplaceFlowDirectionMapping`方法将替换的默认映射<xref:System.Windows.FrameworkElement.FlowDirection%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7104b-144">The `ReplaceFlowDirectionMapping` method replaces the default mapping for the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property.</span></span>

     <span data-ttu-id="7104b-145">`OnFlowDirectionChange`方法将转换<xref:System.Windows.FrameworkElement.FlowDirection%2A>属性设置为[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7104b-145">The `OnFlowDirectionChange` method translates the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> property.</span></span>

     <span data-ttu-id="7104b-146">`cb_CheckedChanged`方法将处理<xref:System.Windows.Forms.CheckBox.CheckedChanged>上的事件<xref:System.Windows.Forms.CheckBox>控件。</span><span class="sxs-lookup"><span data-stu-id="7104b-146">The `cb_CheckedChanged` method handles the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event on the <xref:System.Windows.Forms.CheckBox> control.</span></span> <span data-ttu-id="7104b-147">它将分配<xref:System.Windows.FrameworkElement.FlowDirection%2A>属性值的基础<xref:System.Windows.Forms.CheckBox.CheckState%2A>属性</span><span class="sxs-lookup"><span data-stu-id="7104b-147">It assigns the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property based on the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="7104b-148">扩展默认属性映射</span><span class="sxs-lookup"><span data-stu-id="7104b-148">Extending a Default Property Mapping</span></span>

<span data-ttu-id="7104b-149">可以使用默认属性映射，并使用自己的映射对其进行扩展。</span><span class="sxs-lookup"><span data-stu-id="7104b-149">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="7104b-150">扩展默认属性映射</span><span class="sxs-lookup"><span data-stu-id="7104b-150">To extend a default property mapping</span></span>

-   <span data-ttu-id="7104b-151">将以下代码复制到用于定义`Window1`类。</span><span class="sxs-lookup"><span data-stu-id="7104b-151">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     <span data-ttu-id="7104b-152">`ExtendBackgroundMapping`方法将自定义属性转换器添加到现有<xref:System.Windows.Controls.Control.Background%2A>属性映射。</span><span class="sxs-lookup"><span data-stu-id="7104b-152">The `ExtendBackgroundMapping` method adds a custom property translator to the existing <xref:System.Windows.Controls.Control.Background%2A> property mapping.</span></span>

     <span data-ttu-id="7104b-153">`OnBackgroundChange`方法将特定图像分配给托管控件的<xref:System.Windows.Forms.Control.BackgroundImage%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7104b-153">The `OnBackgroundChange` method assigns a specific image to the hosted control's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span> <span data-ttu-id="7104b-154">`OnBackgroundChange`应用默认属性映射后调用方法。</span><span class="sxs-lookup"><span data-stu-id="7104b-154">The `OnBackgroundChange` method is called after the default property mapping is applied.</span></span>

## <a name="initializing-your-property-mappings"></a><span data-ttu-id="7104b-155">初始化属性映射</span><span class="sxs-lookup"><span data-stu-id="7104b-155">Initializing Your Property Mappings</span></span>

<span data-ttu-id="7104b-156">通过调用前面所述的方法中设置属性映射<xref:System.Windows.FrameworkElement.Loaded>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7104b-156">Set up your property mappings by calling the previously described methods in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="7104b-157">初始化属性映射</span><span class="sxs-lookup"><span data-stu-id="7104b-157">To initialize your property mappings</span></span>

1.  <span data-ttu-id="7104b-158">将以下代码复制到用于定义`Window1`类。</span><span class="sxs-lookup"><span data-stu-id="7104b-158">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     <span data-ttu-id="7104b-159">`WindowLoaded`方法将处理<xref:System.Windows.FrameworkElement.Loaded>事件并执行以下初始化。</span><span class="sxs-lookup"><span data-stu-id="7104b-159">The `WindowLoaded` method handles the <xref:System.Windows.FrameworkElement.Loaded> event and performs the following initialization.</span></span>

    -   <span data-ttu-id="7104b-160">创建[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox>控件。</span><span class="sxs-lookup"><span data-stu-id="7104b-160">Creates a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> control.</span></span>

    -   <span data-ttu-id="7104b-161">调用先前在演练中定义的方法来设置属性映射。</span><span class="sxs-lookup"><span data-stu-id="7104b-161">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    -   <span data-ttu-id="7104b-162">将初始值分配给映射的属性。</span><span class="sxs-lookup"><span data-stu-id="7104b-162">Assigns initial values to the mapped properties.</span></span>

2.  <span data-ttu-id="7104b-163">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="7104b-163">Press **F5** to build and run the application.</span></span> <span data-ttu-id="7104b-164">单击复选框可查看的效果<xref:System.Windows.FrameworkElement.FlowDirection%2A>映射。</span><span class="sxs-lookup"><span data-stu-id="7104b-164">Click the check box to see the effect of the <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span></span> <span data-ttu-id="7104b-165">单击复选框时，布局会反转其左右方向。</span><span class="sxs-lookup"><span data-stu-id="7104b-165">When you click the check box, the layout reverses its left-right orientation.</span></span>

## <a name="see-also"></a><span data-ttu-id="7104b-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="7104b-166">See also</span></span>

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="7104b-167">Windows 窗体和 WPF 属性映射</span><span class="sxs-lookup"><span data-stu-id="7104b-167">Windows Forms and WPF Property Mapping</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="7104b-168">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="7104b-168">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="7104b-169">演练：承载在 WPF 中的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="7104b-169">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)