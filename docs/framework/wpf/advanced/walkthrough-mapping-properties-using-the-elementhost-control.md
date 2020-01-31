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
ms.openlocfilehash: 7ff4ff607ab70b55cda1e2c4736ff773d4907a22
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794118"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="a8ff6-102">演练：使用 ElementHost 控件映射属性</span><span class="sxs-lookup"><span data-stu-id="a8ff6-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>

<span data-ttu-id="a8ff6-103">本演练演示如何使用 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> 属性将 Windows 窗体属性映射到寄宿 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素上的相应属性。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map Windows Forms properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>

<span data-ttu-id="a8ff6-104">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="a8ff6-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="a8ff6-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-105">Creating the project.</span></span>

- <span data-ttu-id="a8ff6-106">定义新的属性映射。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-106">Defining a new property mapping.</span></span>

- <span data-ttu-id="a8ff6-107">删除默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-107">Removing a default property mapping.</span></span>

- <span data-ttu-id="a8ff6-108">扩展默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-108">Extending a default property mapping.</span></span>

<span data-ttu-id="a8ff6-109">有关本演练中所述任务的完整代码列表，请参阅[使用 ElementHost 控件示例映射属性](https://go.microsoft.com/fwlink/?LinkID=160018)。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](https://go.microsoft.com/fwlink/?LinkID=160018).</span></span>

<span data-ttu-id="a8ff6-110">完成后，可以将 Windows 窗体属性映射到寄宿元素上相应的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 属性。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-110">When you are finished, you will be able to map Windows Forms properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a8ff6-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="a8ff6-111">Prerequisites</span></span>

<span data-ttu-id="a8ff6-112">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="a8ff6-112">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="a8ff6-113">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="a8ff6-113">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="a8ff6-114">创建项目</span><span class="sxs-lookup"><span data-stu-id="a8ff6-114">Creating the Project</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="a8ff6-115">创建项目</span><span class="sxs-lookup"><span data-stu-id="a8ff6-115">To create the project</span></span>

1. <span data-ttu-id="a8ff6-116">创建一个名为 `PropertyMappingWithElementHost`**Windows 窗体应用**项目。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-116">Create a **Windows Forms App** project named `PropertyMappingWithElementHost`.</span></span>

2. <span data-ttu-id="a8ff6-117">在**解决方案资源管理器**中，添加对以下 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-117">In **Solution Explorer**, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>

    - <span data-ttu-id="a8ff6-118">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="a8ff6-118">PresentationCore</span></span>

    - <span data-ttu-id="a8ff6-119">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="a8ff6-119">PresentationFramework</span></span>

    - <span data-ttu-id="a8ff6-120">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="a8ff6-120">WindowsBase</span></span>

    - <span data-ttu-id="a8ff6-121">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="a8ff6-121">WindowsFormsIntegration</span></span>

3. <span data-ttu-id="a8ff6-122">将以下代码复制到 `Form1` 代码文件的顶部。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-122">Copy the following code into the top of the `Form1` code file.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. <span data-ttu-id="a8ff6-123">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-123">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="a8ff6-124">双击窗体，为 <xref:System.Windows.Forms.Form.Load> 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-124">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>

5. <span data-ttu-id="a8ff6-125">返回到 Windows 窗体设计器并为窗体的 <xref:System.Windows.Forms.Control.Resize> 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-125">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="a8ff6-126">有关详细信息，请参阅[如何：使用设计器创建事件处理程序](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-126">For more information, see [How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

6. <span data-ttu-id="a8ff6-127">在 `Form1` 类中声明 <xref:System.Windows.Forms.Integration.ElementHost> 字段。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-127">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a><span data-ttu-id="a8ff6-128">定义新的属性映射</span><span class="sxs-lookup"><span data-stu-id="a8ff6-128">Defining New Property Mappings</span></span>

<span data-ttu-id="a8ff6-129"><xref:System.Windows.Forms.Integration.ElementHost> 控件提供了几个默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-129">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="a8ff6-130">通过对 <xref:System.Windows.Forms.Integration.ElementHost> 控件的 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>调用 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 方法，可以添加新的属性映射。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-define-new-property-mappings"></a><span data-ttu-id="a8ff6-131">定义新的属性映射</span><span class="sxs-lookup"><span data-stu-id="a8ff6-131">To define new property mappings</span></span>

1. <span data-ttu-id="a8ff6-132">将以下代码复制到 `Form1` 类的定义中。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-132">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     <span data-ttu-id="a8ff6-133">`AddMarginMapping` 方法为 <xref:System.Windows.Forms.Control.Margin%2A> 属性添加新映射。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-133">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>

     <span data-ttu-id="a8ff6-134">`OnMarginChange` 方法将 <xref:System.Windows.Forms.Control.Margin%2A> 属性转换为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-134">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>

2. <span data-ttu-id="a8ff6-135">将以下代码复制到 `Form1` 类的定义中。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-135">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     <span data-ttu-id="a8ff6-136">`AddRegionMapping` 方法为 <xref:System.Windows.Forms.Control.Region%2A> 属性添加新映射。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-136">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="a8ff6-137">`OnRegionChange` 方法将 <xref:System.Windows.Forms.Control.Region%2A> 属性转换为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-137">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="a8ff6-138">`Form1_Resize` 方法处理窗体的 <xref:System.Windows.Forms.Control.Resize> 事件，并调整剪辑区域的大小以适合承载的元素。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-138">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="a8ff6-139">删除默认属性映射</span><span class="sxs-lookup"><span data-stu-id="a8ff6-139">Removing a Default Property Mapping</span></span>

<span data-ttu-id="a8ff6-140">通过对 <xref:System.Windows.Forms.Integration.ElementHost> 控件的 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>调用 <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> 方法来删除默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-140">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="a8ff6-141">删除默认属性映射</span><span class="sxs-lookup"><span data-stu-id="a8ff6-141">To remove a default property mapping</span></span>

- <span data-ttu-id="a8ff6-142">将以下代码复制到 `Form1` 类的定义中。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-142">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     <span data-ttu-id="a8ff6-143">`RemoveCursorMapping` 方法将删除 <xref:System.Windows.Forms.Control.Cursor%2A> 属性的默认映射。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-143">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="a8ff6-144">扩展默认属性映射</span><span class="sxs-lookup"><span data-stu-id="a8ff6-144">Extending a Default Property Mapping</span></span>

<span data-ttu-id="a8ff6-145">可以使用默认属性映射，并使用自己的映射对其进行扩展。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-145">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="a8ff6-146">扩展默认属性映射</span><span class="sxs-lookup"><span data-stu-id="a8ff6-146">To extend a default property mapping</span></span>

- <span data-ttu-id="a8ff6-147">将以下代码复制到 `Form1` 类的定义中。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-147">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     <span data-ttu-id="a8ff6-148">`ExtendBackColorMapping` 方法将自定义属性转换器添加到现有 <xref:System.Windows.Forms.Control.BackColor%2A> 属性映射。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-148">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>

     <span data-ttu-id="a8ff6-149">`OnBackColorChange` 方法将特定的图像分配给寄宿控件的 <xref:System.Windows.Controls.Control.Background%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-149">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="a8ff6-150">应用默认属性映射后，将调用 `OnBackColorChange` 方法。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-150">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>

## <a name="initialize-your-property-mappings"></a><span data-ttu-id="a8ff6-151">初始化属性映射</span><span class="sxs-lookup"><span data-stu-id="a8ff6-151">Initialize your property mappings</span></span>

1. <span data-ttu-id="a8ff6-152">将以下代码复制到 `Form1` 类的定义中。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-152">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     <span data-ttu-id="a8ff6-153">`Form1_Load` 方法处理 <xref:System.Windows.Forms.Form.Load> 事件并执行以下初始化。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-153">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>

    - <span data-ttu-id="a8ff6-154">创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> 元素。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-154">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>

    - <span data-ttu-id="a8ff6-155">调用先前在演练中定义的方法来设置属性映射。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-155">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    - <span data-ttu-id="a8ff6-156">将初始值分配给映射的属性。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-156">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="a8ff6-157">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a8ff6-157">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8ff6-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8ff6-158">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="a8ff6-159">Windows 窗体和 WPF 属性映射</span><span class="sxs-lookup"><span data-stu-id="a8ff6-159">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="a8ff6-160">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="a8ff6-160">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="a8ff6-161">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="a8ff6-161">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
