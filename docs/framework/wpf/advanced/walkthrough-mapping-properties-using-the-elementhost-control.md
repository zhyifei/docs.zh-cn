---
title: "演练：使用 ElementHost 控件映射属性"
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
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dae954012d15431d2019d3d9cbe61747a8646d4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="43991-102">演练：使用 ElementHost 控件映射属性</span><span class="sxs-lookup"><span data-stu-id="43991-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>
<span data-ttu-id="43991-103">本演练演示如何使用<xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>属性映射[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]到上一个承载的相应属性的属性[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]元素。</span><span class="sxs-lookup"><span data-stu-id="43991-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>  
  
 <span data-ttu-id="43991-104">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="43991-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="43991-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="43991-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="43991-106">定义新的属性映射。</span><span class="sxs-lookup"><span data-stu-id="43991-106">Defining a new property mapping.</span></span>  
  
-   <span data-ttu-id="43991-107">删除默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="43991-107">Removing a default property mapping.</span></span>  
  
-   <span data-ttu-id="43991-108">扩展默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="43991-108">Extending a default property mapping.</span></span>  
  
 <span data-ttu-id="43991-109">本演练的任务的完整代码清单，请参阅[映射属性使用 ElementHost 控件示例](http://go.microsoft.com/fwlink/?LinkID=160018)。</span><span class="sxs-lookup"><span data-stu-id="43991-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](http://go.microsoft.com/fwlink/?LinkID=160018).</span></span>  
  
 <span data-ttu-id="43991-110">完成后，你将能够映射[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]到对应的属性[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]上承载的元素的属性。</span><span class="sxs-lookup"><span data-stu-id="43991-110">When you are finished, you will be able to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="43991-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="43991-111">Prerequisites</span></span>  
 <span data-ttu-id="43991-112">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="43991-112">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="43991-113">。</span><span class="sxs-lookup"><span data-stu-id="43991-113">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="43991-114">创建项目</span><span class="sxs-lookup"><span data-stu-id="43991-114">Creating the Project</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="43991-115">创建项目</span><span class="sxs-lookup"><span data-stu-id="43991-115">To create the project</span></span>  
  
1.  <span data-ttu-id="43991-116">创建[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]应用程序项目中名为`PropertyMappingWithElementHost`。</span><span class="sxs-lookup"><span data-stu-id="43991-116">Create a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application project named `PropertyMappingWithElementHost`.</span></span> <span data-ttu-id="43991-117">有关详细信息，请参阅 [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)。</span><span class="sxs-lookup"><span data-stu-id="43991-117">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="43991-118">在解决方案资源管理器中，添加对以下引用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]程序集。</span><span class="sxs-lookup"><span data-stu-id="43991-118">In Solution Explorer, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>  
  
    -   <span data-ttu-id="43991-119">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="43991-119">PresentationCore</span></span>  
  
    -   <span data-ttu-id="43991-120">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="43991-120">PresentationFramework</span></span>  
  
    -   <span data-ttu-id="43991-121">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="43991-121">WindowsBase</span></span>  
  
    -   <span data-ttu-id="43991-122">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="43991-122">WindowsFormsIntegration</span></span>  
  
3.  <span data-ttu-id="43991-123">将以下代码复制到顶部`Form1`代码文件。</span><span class="sxs-lookup"><span data-stu-id="43991-123">Copy the following code into the top of the `Form1` code file.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]  
  
4.  <span data-ttu-id="43991-124">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="43991-124">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="43991-125">双击要添加的事件处理程序的窗体<xref:System.Windows.Forms.Form.Load>事件。</span><span class="sxs-lookup"><span data-stu-id="43991-125">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>  
  
5.  <span data-ttu-id="43991-126">返回到 Windows 窗体设计器并添加一个事件处理程序窗体的<xref:System.Windows.Forms.Control.Resize>事件。</span><span class="sxs-lookup"><span data-stu-id="43991-126">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="43991-127">有关详细信息，请参阅[如何： 使用设计器创建事件处理程序](http://msdn.microsoft.com/en-us/8461e9b8-14e8-406f-936e-3726732b23d2)。</span><span class="sxs-lookup"><span data-stu-id="43991-127">For more information, see [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/en-us/8461e9b8-14e8-406f-936e-3726732b23d2).</span></span>  
  
6.  <span data-ttu-id="43991-128">声明<xref:System.Windows.Forms.Integration.ElementHost>字段`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="43991-128">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]  
  
## <a name="defining-new-property-mappings"></a><span data-ttu-id="43991-129">定义新的属性映射</span><span class="sxs-lookup"><span data-stu-id="43991-129">Defining New Property Mappings</span></span>  
 <span data-ttu-id="43991-130"><xref:System.Windows.Forms.Integration.ElementHost>控件提供了一些默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="43991-130">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="43991-131">通过调用将添加新的属性映射<xref:System.Windows.Forms.Integration.PropertyMap.Add%2A>方法<xref:System.Windows.Forms.Integration.ElementHost>控件的<xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>。</span><span class="sxs-lookup"><span data-stu-id="43991-131">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-define-new-property-mappings"></a><span data-ttu-id="43991-132">若要定义新的属性映射</span><span class="sxs-lookup"><span data-stu-id="43991-132">To define new property mappings</span></span>  
  
1.  <span data-ttu-id="43991-133">将以下代码复制到的定义`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="43991-133">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]  
  
     <span data-ttu-id="43991-134">`AddMarginMapping`方法将添加的新映射<xref:System.Windows.Forms.Control.Margin%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="43991-134">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>  
  
     <span data-ttu-id="43991-135">`OnMarginChange`方法将转换<xref:System.Windows.Forms.Control.Margin%2A>属性[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.FrameworkElement.Margin%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="43991-135">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>  
  
2.  <span data-ttu-id="43991-136">将以下代码复制到的定义`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="43991-136">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]  
  
     <span data-ttu-id="43991-137">`AddRegionMapping`方法将添加的新映射<xref:System.Windows.Forms.Control.Region%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="43991-137">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>  
  
     <span data-ttu-id="43991-138">`OnRegionChange`方法将转换<xref:System.Windows.Forms.Control.Region%2A>属性[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.UIElement.Clip%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="43991-138">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>  
  
     <span data-ttu-id="43991-139">`Form1_Resize`方法可处理窗体的<xref:System.Windows.Forms.Control.Resize>事件并调整其大小以适合托管的元素的剪辑区域。</span><span class="sxs-lookup"><span data-stu-id="43991-139">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>  
  
## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="43991-140">删除默认属性映射</span><span class="sxs-lookup"><span data-stu-id="43991-140">Removing a Default Property Mapping</span></span>  
 <span data-ttu-id="43991-141">通过调用来移除默认属性映射<xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A>方法<xref:System.Windows.Forms.Integration.ElementHost>控件的<xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>。</span><span class="sxs-lookup"><span data-stu-id="43991-141">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="43991-142">删除默认属性映射</span><span class="sxs-lookup"><span data-stu-id="43991-142">To remove a default property mapping</span></span>  
  
-   <span data-ttu-id="43991-143">将以下代码复制到的定义`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="43991-143">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]  
  
     <span data-ttu-id="43991-144">`RemoveCursorMapping`方法删除默认映射<xref:System.Windows.Forms.Control.Cursor%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="43991-144">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>  
  
## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="43991-145">扩展默认属性映射</span><span class="sxs-lookup"><span data-stu-id="43991-145">Extending a Default Property Mapping</span></span>  
 <span data-ttu-id="43991-146">可以使用默认属性映射，并使用自己的映射对其进行扩展。</span><span class="sxs-lookup"><span data-stu-id="43991-146">You can use a default property mapping and also extend it with your own mapping.</span></span>  
  
#### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="43991-147">扩展默认属性映射</span><span class="sxs-lookup"><span data-stu-id="43991-147">To extend a default property mapping</span></span>  
  
-   <span data-ttu-id="43991-148">将以下代码复制到的定义`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="43991-148">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]  
  
     <span data-ttu-id="43991-149">`ExtendBackColorMapping`方法将自定义的属性转换器添加到现有<xref:System.Windows.Forms.Control.BackColor%2A>属性映射。</span><span class="sxs-lookup"><span data-stu-id="43991-149">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>  
  
     <span data-ttu-id="43991-150">`OnBackColorChange`方法将托管控件的特定映像<xref:System.Windows.Controls.Control.Background%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="43991-150">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="43991-151">`OnBackColorChange`应用的默认属性映射后调用方法。</span><span class="sxs-lookup"><span data-stu-id="43991-151">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>  
  
## <a name="initializing-your-property-mappings"></a><span data-ttu-id="43991-152">初始化属性映射</span><span class="sxs-lookup"><span data-stu-id="43991-152">Initializing Your Property Mappings</span></span>  
  
#### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="43991-153">初始化属性映射</span><span class="sxs-lookup"><span data-stu-id="43991-153">To initialize your property mappings</span></span>  
  
1.  <span data-ttu-id="43991-154">将以下代码复制到的定义`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="43991-154">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]  
  
     <span data-ttu-id="43991-155">`Form1_Load`方法将处理<xref:System.Windows.Forms.Form.Load>事件并执行以下初始化。</span><span class="sxs-lookup"><span data-stu-id="43991-155">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>  
  
    -   <span data-ttu-id="43991-156">创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Button>元素。</span><span class="sxs-lookup"><span data-stu-id="43991-156">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>  
  
    -   <span data-ttu-id="43991-157">调用先前在演练中定义的方法来设置属性映射。</span><span class="sxs-lookup"><span data-stu-id="43991-157">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>  
  
    -   <span data-ttu-id="43991-158">将初始值分配给映射的属性。</span><span class="sxs-lookup"><span data-stu-id="43991-158">Assigns initial values to the mapped properties.</span></span>  
  
2.  <span data-ttu-id="43991-159">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="43991-159">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43991-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43991-160">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="43991-161">Windows 窗体和 WPF 属性映射</span><span class="sxs-lookup"><span data-stu-id="43991-161">Windows Forms and WPF Property Mapping</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [<span data-ttu-id="43991-162">WPF 设计器</span><span class="sxs-lookup"><span data-stu-id="43991-162">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="43991-163">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="43991-163">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
