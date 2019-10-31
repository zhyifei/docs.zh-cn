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
ms.openlocfilehash: c8a83dd3f7327d00979431ca7fa801ff642a4eef
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197810"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a><span data-ttu-id="fa65e-102">演练：使用 WindowsFormsHost 元素映射属性</span><span class="sxs-lookup"><span data-stu-id="fa65e-102">Walkthrough: Mapping Properties Using the WindowsFormsHost Element</span></span>

<span data-ttu-id="fa65e-103">本演练演示如何使用 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> 属性将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 属性映射到寄宿 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件上的相应属性。</span><span class="sxs-lookup"><span data-stu-id="fa65e-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> property to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

<span data-ttu-id="fa65e-104">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="fa65e-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="fa65e-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="fa65e-105">Creating the project.</span></span>

- <span data-ttu-id="fa65e-106">定义应用程序布局。</span><span class="sxs-lookup"><span data-stu-id="fa65e-106">Defining the application layout.</span></span>

- <span data-ttu-id="fa65e-107">定义新的属性映射。</span><span class="sxs-lookup"><span data-stu-id="fa65e-107">Defining a new property mapping.</span></span>

- <span data-ttu-id="fa65e-108">删除默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="fa65e-108">Removing a default property mapping.</span></span>

- <span data-ttu-id="fa65e-109">替换默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="fa65e-109">Replacing a default property mapping.</span></span>

- <span data-ttu-id="fa65e-110">扩展默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="fa65e-110">Extending a default property mapping.</span></span>

<span data-ttu-id="fa65e-111">有关本演练中所述任务的完整代码列表，请参阅[使用 System.windows.forms.integration.windowsformshost> 元素映射属性示例](https://go.microsoft.com/fwlink/?LinkID=160019)。</span><span class="sxs-lookup"><span data-stu-id="fa65e-111">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the WindowsFormsHost Element Sample](https://go.microsoft.com/fwlink/?LinkID=160019).</span></span>

<span data-ttu-id="fa65e-112">完成后，你将能够将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 属性映射到托管 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件上的相应属性。</span><span class="sxs-lookup"><span data-stu-id="fa65e-112">When you are finished, you will be able to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fa65e-113">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="fa65e-113">Prerequisites</span></span>

<span data-ttu-id="fa65e-114">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="fa65e-114">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="fa65e-115">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="fa65e-115">Visual Studio 2017</span></span>

## <a name="create-and-set-up-the-project"></a><span data-ttu-id="fa65e-116">创建和设置项目</span><span class="sxs-lookup"><span data-stu-id="fa65e-116">Create and set up the project</span></span>

1. <span data-ttu-id="fa65e-117">创建一个名为 `PropertyMappingWithWfhSample`的**WPF 应用程序**项目。</span><span class="sxs-lookup"><span data-stu-id="fa65e-117">Create a **WPF App** project named `PropertyMappingWithWfhSample`.</span></span>

2. <span data-ttu-id="fa65e-118">在**解决方案资源管理器**中，添加对 WindowsFormsIntegration 程序集的引用，该程序集名为 WindowsFormsIntegration。</span><span class="sxs-lookup"><span data-stu-id="fa65e-118">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="fa65e-119">在**解决方案资源管理器**中，添加对 System.web 和 system.web 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="fa65e-119">In **Solution Explorer**, add references to the System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="defining-the-application-layout"></a><span data-ttu-id="fa65e-120">定义应用程序布局</span><span class="sxs-lookup"><span data-stu-id="fa65e-120">Defining the Application Layout</span></span>

<span data-ttu-id="fa65e-121">基于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的应用程序使用 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素来承载 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。</span><span class="sxs-lookup"><span data-stu-id="fa65e-121">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

### <a name="to-define-the-application-layout"></a><span data-ttu-id="fa65e-122">定义应用程序布局</span><span class="sxs-lookup"><span data-stu-id="fa65e-122">To define the application layout</span></span>

1. <span data-ttu-id="fa65e-123">在 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]中打开 Window1.xaml。</span><span class="sxs-lookup"><span data-stu-id="fa65e-123">Open Window1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

2. <span data-ttu-id="fa65e-124">用下面的代码替换现有代码。</span><span class="sxs-lookup"><span data-stu-id="fa65e-124">Replace the existing code with the following code.</span></span>

     [!code-xaml[PropertyMappingWithWfhSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3. <span data-ttu-id="fa65e-125">在代码编辑器中打开 Window1.xaml.cs。</span><span class="sxs-lookup"><span data-stu-id="fa65e-125">Open Window1.xaml.cs in the Code Editor.</span></span>

4. <span data-ttu-id="fa65e-126">在该文件顶部导入以下命名空间。</span><span class="sxs-lookup"><span data-stu-id="fa65e-126">At the top of the file, import the following namespaces.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#20](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a><span data-ttu-id="fa65e-127">定义新的属性映射</span><span class="sxs-lookup"><span data-stu-id="fa65e-127">Defining a New Property Mapping</span></span>

<span data-ttu-id="fa65e-128"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素提供了几个默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="fa65e-128">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element provides several default property mappings.</span></span> <span data-ttu-id="fa65e-129">通过对 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>调用 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 方法，可以添加新的属性映射。</span><span class="sxs-lookup"><span data-stu-id="fa65e-129">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-define-a-new-property-mapping"></a><span data-ttu-id="fa65e-130">定义新的属性映射</span><span class="sxs-lookup"><span data-stu-id="fa65e-130">To define a new property mapping</span></span>

- <span data-ttu-id="fa65e-131">将以下代码复制到 `Window1` 类的定义中。</span><span class="sxs-lookup"><span data-stu-id="fa65e-131">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     <span data-ttu-id="fa65e-132">`AddClipMapping` 方法为 <xref:System.Windows.UIElement.Clip%2A> 属性添加新映射。</span><span class="sxs-lookup"><span data-stu-id="fa65e-132">The `AddClipMapping` method adds a new mapping for the <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="fa65e-133">`OnClipChange` 方法将 <xref:System.Windows.UIElement.Clip%2A> 属性转换为 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="fa65e-133">The `OnClipChange` method translates the <xref:System.Windows.UIElement.Clip%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="fa65e-134">`Window1_SizeChanged` 方法处理窗口的 <xref:System.Windows.FrameworkElement.SizeChanged> 事件，并调整剪辑区域的大小以适合应用程序窗口。</span><span class="sxs-lookup"><span data-stu-id="fa65e-134">The `Window1_SizeChanged` method handles the window's <xref:System.Windows.FrameworkElement.SizeChanged> event and sizes the clipping region to fit the application window.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="fa65e-135">删除默认属性映射</span><span class="sxs-lookup"><span data-stu-id="fa65e-135">Removing a Default Property Mapping</span></span>

<span data-ttu-id="fa65e-136">通过对 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>调用 <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> 方法来删除默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="fa65e-136">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="fa65e-137">删除默认属性映射</span><span class="sxs-lookup"><span data-stu-id="fa65e-137">To remove a default property mapping</span></span>

- <span data-ttu-id="fa65e-138">将以下代码复制到 `Window1` 类的定义中。</span><span class="sxs-lookup"><span data-stu-id="fa65e-138">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     <span data-ttu-id="fa65e-139">`RemoveCursorMapping` 方法将删除 <xref:System.Windows.FrameworkElement.Cursor%2A> 属性的默认映射。</span><span class="sxs-lookup"><span data-stu-id="fa65e-139">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.FrameworkElement.Cursor%2A> property.</span></span>

## <a name="replacing-a-default-property-mapping"></a><span data-ttu-id="fa65e-140">替换默认属性映射</span><span class="sxs-lookup"><span data-stu-id="fa65e-140">Replacing a Default Property Mapping</span></span>

<span data-ttu-id="fa65e-141">通过删除默认映射并对 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>调用 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 方法来替换默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="fa65e-141">Replace a default property mapping by removing the default mapping and calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-replace-a-default-property-mapping"></a><span data-ttu-id="fa65e-142">替换默认属性映射</span><span class="sxs-lookup"><span data-stu-id="fa65e-142">To replace a default property mapping</span></span>

- <span data-ttu-id="fa65e-143">将以下代码复制到 `Window1` 类的定义中。</span><span class="sxs-lookup"><span data-stu-id="fa65e-143">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     <span data-ttu-id="fa65e-144">`ReplaceFlowDirectionMapping` 方法替换 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 属性的默认映射。</span><span class="sxs-lookup"><span data-stu-id="fa65e-144">The `ReplaceFlowDirectionMapping` method replaces the default mapping for the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property.</span></span>

     <span data-ttu-id="fa65e-145">`OnFlowDirectionChange` 方法将 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 属性转换为 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="fa65e-145">The `OnFlowDirectionChange` method translates the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> property.</span></span>

     <span data-ttu-id="fa65e-146">`cb_CheckedChanged` 方法处理 <xref:System.Windows.Forms.CheckBox> 控件上的 <xref:System.Windows.Forms.CheckBox.CheckedChanged> 事件。</span><span class="sxs-lookup"><span data-stu-id="fa65e-146">The `cb_CheckedChanged` method handles the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event on the <xref:System.Windows.Forms.CheckBox> control.</span></span> <span data-ttu-id="fa65e-147">它基于 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 属性的值分配 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="fa65e-147">It assigns the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property based on the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="fa65e-148">扩展默认属性映射</span><span class="sxs-lookup"><span data-stu-id="fa65e-148">Extending a Default Property Mapping</span></span>

<span data-ttu-id="fa65e-149">可以使用默认属性映射，并使用自己的映射对其进行扩展。</span><span class="sxs-lookup"><span data-stu-id="fa65e-149">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="fa65e-150">扩展默认属性映射</span><span class="sxs-lookup"><span data-stu-id="fa65e-150">To extend a default property mapping</span></span>

- <span data-ttu-id="fa65e-151">将以下代码复制到 `Window1` 类的定义中。</span><span class="sxs-lookup"><span data-stu-id="fa65e-151">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     <span data-ttu-id="fa65e-152">`ExtendBackgroundMapping` 方法将自定义属性转换器添加到现有 <xref:System.Windows.Controls.Control.Background%2A> 属性映射。</span><span class="sxs-lookup"><span data-stu-id="fa65e-152">The `ExtendBackgroundMapping` method adds a custom property translator to the existing <xref:System.Windows.Controls.Control.Background%2A> property mapping.</span></span>

     <span data-ttu-id="fa65e-153">`OnBackgroundChange` 方法将特定的图像分配给寄宿控件的 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="fa65e-153">The `OnBackgroundChange` method assigns a specific image to the hosted control's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span> <span data-ttu-id="fa65e-154">应用默认属性映射后，将调用 `OnBackgroundChange` 方法。</span><span class="sxs-lookup"><span data-stu-id="fa65e-154">The `OnBackgroundChange` method is called after the default property mapping is applied.</span></span>

## <a name="initializing-your-property-mappings"></a><span data-ttu-id="fa65e-155">初始化属性映射</span><span class="sxs-lookup"><span data-stu-id="fa65e-155">Initializing Your Property Mappings</span></span>

<span data-ttu-id="fa65e-156">通过调用 <xref:System.Windows.FrameworkElement.Loaded> 事件处理程序中前面所述的方法来设置属性映射。</span><span class="sxs-lookup"><span data-stu-id="fa65e-156">Set up your property mappings by calling the previously described methods in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="fa65e-157">初始化属性映射</span><span class="sxs-lookup"><span data-stu-id="fa65e-157">To initialize your property mappings</span></span>

1. <span data-ttu-id="fa65e-158">将以下代码复制到 `Window1` 类的定义中。</span><span class="sxs-lookup"><span data-stu-id="fa65e-158">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     <span data-ttu-id="fa65e-159">`WindowLoaded` 方法处理 <xref:System.Windows.FrameworkElement.Loaded> 事件并执行以下初始化。</span><span class="sxs-lookup"><span data-stu-id="fa65e-159">The `WindowLoaded` method handles the <xref:System.Windows.FrameworkElement.Loaded> event and performs the following initialization.</span></span>

    - <span data-ttu-id="fa65e-160">创建 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="fa65e-160">Creates a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> control.</span></span>

    - <span data-ttu-id="fa65e-161">调用先前在演练中定义的方法来设置属性映射。</span><span class="sxs-lookup"><span data-stu-id="fa65e-161">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    - <span data-ttu-id="fa65e-162">将初始值分配给映射的属性。</span><span class="sxs-lookup"><span data-stu-id="fa65e-162">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="fa65e-163">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="fa65e-163">Press **F5** to build and run the application.</span></span> <span data-ttu-id="fa65e-164">单击该复选框可以查看 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 映射的效果。</span><span class="sxs-lookup"><span data-stu-id="fa65e-164">Click the check box to see the effect of the <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span></span> <span data-ttu-id="fa65e-165">单击复选框时，布局会反转其左右方向。</span><span class="sxs-lookup"><span data-stu-id="fa65e-165">When you click the check box, the layout reverses its left-right orientation.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa65e-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa65e-166">See also</span></span>

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="fa65e-167">Windows 窗体和 WPF 属性映射</span><span class="sxs-lookup"><span data-stu-id="fa65e-167">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="fa65e-168">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="fa65e-168">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="fa65e-169">演练：在 WPF 中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="fa65e-169">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
