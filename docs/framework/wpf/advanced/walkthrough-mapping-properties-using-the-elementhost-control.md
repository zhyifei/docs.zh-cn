---
title: 演练：使用 ElementHost 控件映射属性
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: 360f19e558f97e1807b329ad18e429fa893bbf86
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300913"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="6bb65-102">演练：使用 ElementHost 控件映射属性</span><span class="sxs-lookup"><span data-stu-id="6bb65-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>

<span data-ttu-id="6bb65-103">本演练演示如何使用<xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>属性将映射[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]属性设置为上托管的相应属性[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]元素。</span><span class="sxs-lookup"><span data-stu-id="6bb65-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>

<span data-ttu-id="6bb65-104">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="6bb65-104">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="6bb65-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="6bb65-105">Creating the project.</span></span>

-   <span data-ttu-id="6bb65-106">定义新的属性映射。</span><span class="sxs-lookup"><span data-stu-id="6bb65-106">Defining a new property mapping.</span></span>

-   <span data-ttu-id="6bb65-107">删除默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="6bb65-107">Removing a default property mapping.</span></span>

-   <span data-ttu-id="6bb65-108">扩展默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="6bb65-108">Extending a default property mapping.</span></span>

<span data-ttu-id="6bb65-109">在本演练中所涉及任务的完整代码列表，请参阅[映射属性使用 ElementHost 控件示例](https://go.microsoft.com/fwlink/?LinkID=160018)。</span><span class="sxs-lookup"><span data-stu-id="6bb65-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](https://go.microsoft.com/fwlink/?LinkID=160018).</span></span>

<span data-ttu-id="6bb65-110">完成后，你将能够映射[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]相对应的属性[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]上承载的元素的属性。</span><span class="sxs-lookup"><span data-stu-id="6bb65-110">When you are finished, you will be able to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6bb65-111">系统必备</span><span class="sxs-lookup"><span data-stu-id="6bb65-111">Prerequisites</span></span>

<span data-ttu-id="6bb65-112">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="6bb65-112">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="6bb65-113">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="6bb65-113">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="6bb65-114">创建项目</span><span class="sxs-lookup"><span data-stu-id="6bb65-114">Creating the Project</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="6bb65-115">要创建项目</span><span class="sxs-lookup"><span data-stu-id="6bb65-115">To create the project</span></span>

1. <span data-ttu-id="6bb65-116">创建**Windows 窗体应用程序**名为项目`PropertyMappingWithElementHost`。</span><span class="sxs-lookup"><span data-stu-id="6bb65-116">Create a **Windows Forms App** project named `PropertyMappingWithElementHost`.</span></span>

2. <span data-ttu-id="6bb65-117">在中**解决方案资源管理器**，将引用添加到以下[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]程序集。</span><span class="sxs-lookup"><span data-stu-id="6bb65-117">In **Solution Explorer**, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>

    -   <span data-ttu-id="6bb65-118">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="6bb65-118">PresentationCore</span></span>

    -   <span data-ttu-id="6bb65-119">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="6bb65-119">PresentationFramework</span></span>

    -   <span data-ttu-id="6bb65-120">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="6bb65-120">WindowsBase</span></span>

    -   <span data-ttu-id="6bb65-121">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="6bb65-121">WindowsFormsIntegration</span></span>

3. <span data-ttu-id="6bb65-122">将以下代码复制到顶部`Form1`代码文件。</span><span class="sxs-lookup"><span data-stu-id="6bb65-122">Copy the following code into the top of the `Form1` code file.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. <span data-ttu-id="6bb65-123">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="6bb65-123">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="6bb65-124">双击要添加的事件处理程序的窗体<xref:System.Windows.Forms.Form.Load>事件。</span><span class="sxs-lookup"><span data-stu-id="6bb65-124">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>

5. <span data-ttu-id="6bb65-125">返回到 Windows 窗体设计器并添加事件处理程序的窗体的<xref:System.Windows.Forms.Control.Resize>事件。</span><span class="sxs-lookup"><span data-stu-id="6bb65-125">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="6bb65-126">有关详细信息，请参阅[如何：创建事件处理程序使用设计器](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="6bb65-126">For more information, see [How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

6. <span data-ttu-id="6bb65-127">声明<xref:System.Windows.Forms.Integration.ElementHost>字段中`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="6bb65-127">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a><span data-ttu-id="6bb65-128">定义新的属性映射</span><span class="sxs-lookup"><span data-stu-id="6bb65-128">Defining New Property Mappings</span></span>

<span data-ttu-id="6bb65-129"><xref:System.Windows.Forms.Integration.ElementHost>控件提供了一些默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="6bb65-129">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="6bb65-130">通过调用添加新的属性映射<xref:System.Windows.Forms.Integration.PropertyMap.Add%2A>方法<xref:System.Windows.Forms.Integration.ElementHost>控件的<xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>。</span><span class="sxs-lookup"><span data-stu-id="6bb65-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-define-new-property-mappings"></a><span data-ttu-id="6bb65-131">若要定义新属性映射</span><span class="sxs-lookup"><span data-stu-id="6bb65-131">To define new property mappings</span></span>

1. <span data-ttu-id="6bb65-132">将以下代码复制到用于定义`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="6bb65-132">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     <span data-ttu-id="6bb65-133">`AddMarginMapping`方法将添加的新映射<xref:System.Windows.Forms.Control.Margin%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="6bb65-133">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>

     <span data-ttu-id="6bb65-134">`OnMarginChange`方法将转换<xref:System.Windows.Forms.Control.Margin%2A>属性设置为[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.FrameworkElement.Margin%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="6bb65-134">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>

2. <span data-ttu-id="6bb65-135">将以下代码复制到用于定义`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="6bb65-135">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     <span data-ttu-id="6bb65-136">`AddRegionMapping`方法将添加的新映射<xref:System.Windows.Forms.Control.Region%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="6bb65-136">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="6bb65-137">`OnRegionChange`方法将转换<xref:System.Windows.Forms.Control.Region%2A>属性设置为[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.UIElement.Clip%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="6bb65-137">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="6bb65-138">`Form1_Resize`方法将处理窗体的<xref:System.Windows.Forms.Control.Resize>事件并调整其大小以适合所承载的元素的剪辑区域。</span><span class="sxs-lookup"><span data-stu-id="6bb65-138">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="6bb65-139">删除默认属性映射</span><span class="sxs-lookup"><span data-stu-id="6bb65-139">Removing a Default Property Mapping</span></span>

<span data-ttu-id="6bb65-140">通过调用来移除默认属性映射<xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A>方法<xref:System.Windows.Forms.Integration.ElementHost>控件的<xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>。</span><span class="sxs-lookup"><span data-stu-id="6bb65-140">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="6bb65-141">删除默认属性映射</span><span class="sxs-lookup"><span data-stu-id="6bb65-141">To remove a default property mapping</span></span>

-   <span data-ttu-id="6bb65-142">将以下代码复制到用于定义`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="6bb65-142">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     <span data-ttu-id="6bb65-143">`RemoveCursorMapping`方法删除默认映射<xref:System.Windows.Forms.Control.Cursor%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="6bb65-143">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="6bb65-144">扩展默认属性映射</span><span class="sxs-lookup"><span data-stu-id="6bb65-144">Extending a Default Property Mapping</span></span>

<span data-ttu-id="6bb65-145">可以使用默认属性映射，并使用自己的映射对其进行扩展。</span><span class="sxs-lookup"><span data-stu-id="6bb65-145">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="6bb65-146">扩展默认属性映射</span><span class="sxs-lookup"><span data-stu-id="6bb65-146">To extend a default property mapping</span></span>

-   <span data-ttu-id="6bb65-147">将以下代码复制到用于定义`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="6bb65-147">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     <span data-ttu-id="6bb65-148">`ExtendBackColorMapping`方法将自定义属性转换器添加到现有<xref:System.Windows.Forms.Control.BackColor%2A>属性映射。</span><span class="sxs-lookup"><span data-stu-id="6bb65-148">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>

     <span data-ttu-id="6bb65-149">`OnBackColorChange`方法将特定图像分配给托管控件的<xref:System.Windows.Controls.Control.Background%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="6bb65-149">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="6bb65-150">`OnBackColorChange`应用默认属性映射后调用方法。</span><span class="sxs-lookup"><span data-stu-id="6bb65-150">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>

## <a name="initialize-your-property-mappings"></a><span data-ttu-id="6bb65-151">初始化属性映射</span><span class="sxs-lookup"><span data-stu-id="6bb65-151">Initialize your property mappings</span></span>

1. <span data-ttu-id="6bb65-152">将以下代码复制到用于定义`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="6bb65-152">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     <span data-ttu-id="6bb65-153">`Form1_Load`方法将处理<xref:System.Windows.Forms.Form.Load>事件并执行以下初始化。</span><span class="sxs-lookup"><span data-stu-id="6bb65-153">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>

    -   <span data-ttu-id="6bb65-154">创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Button>元素。</span><span class="sxs-lookup"><span data-stu-id="6bb65-154">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>

    -   <span data-ttu-id="6bb65-155">调用先前在演练中定义的方法来设置属性映射。</span><span class="sxs-lookup"><span data-stu-id="6bb65-155">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    -   <span data-ttu-id="6bb65-156">将初始值分配给映射的属性。</span><span class="sxs-lookup"><span data-stu-id="6bb65-156">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="6bb65-157">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="6bb65-157">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="6bb65-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bb65-158">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="6bb65-159">Windows 窗体和 WPF 属性映射</span><span class="sxs-lookup"><span data-stu-id="6bb65-159">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="6bb65-160">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="6bb65-160">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="6bb65-161">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="6bb65-161">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)