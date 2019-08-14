---
title: 演练：在 WPF 中排列 Windows 窗体控件
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: fa0181e95a03324c4cfa9395ae57439c260d1c23
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972311"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="a7f38-102">演练：在 WPF 中排列 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="a7f38-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>

<span data-ttu-id="a7f38-103">本演练演示如何使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]布局功能在混合应用程序中排列[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件。</span><span class="sxs-lookup"><span data-stu-id="a7f38-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>

<span data-ttu-id="a7f38-104">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="a7f38-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="a7f38-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="a7f38-105">Creating the project.</span></span>

- <span data-ttu-id="a7f38-106">使用默认布局设置。</span><span class="sxs-lookup"><span data-stu-id="a7f38-106">Using default layout settings.</span></span>

- <span data-ttu-id="a7f38-107">根据内容调整大小。</span><span class="sxs-lookup"><span data-stu-id="a7f38-107">Sizing to content.</span></span>

- <span data-ttu-id="a7f38-108">使用绝对定位。</span><span class="sxs-lookup"><span data-stu-id="a7f38-108">Using absolute positioning.</span></span>

- <span data-ttu-id="a7f38-109">显式指定大小。</span><span class="sxs-lookup"><span data-stu-id="a7f38-109">Specifying size explicitly.</span></span>

- <span data-ttu-id="a7f38-110">设置布局属性。</span><span class="sxs-lookup"><span data-stu-id="a7f38-110">Setting layout properties.</span></span>

- <span data-ttu-id="a7f38-111">了解 Z 顺序限制。</span><span class="sxs-lookup"><span data-stu-id="a7f38-111">Understanding z-order limitations.</span></span>

- <span data-ttu-id="a7f38-112">停靠。</span><span class="sxs-lookup"><span data-stu-id="a7f38-112">Docking.</span></span>

- <span data-ttu-id="a7f38-113">设置可见性。</span><span class="sxs-lookup"><span data-stu-id="a7f38-113">Setting visibility.</span></span>

- <span data-ttu-id="a7f38-114">承载不拉伸的控件。</span><span class="sxs-lookup"><span data-stu-id="a7f38-114">Hosting a control that does not stretch.</span></span>

- <span data-ttu-id="a7f38-115">缩放。</span><span class="sxs-lookup"><span data-stu-id="a7f38-115">Scaling.</span></span>

- <span data-ttu-id="a7f38-116">旋转。</span><span class="sxs-lookup"><span data-stu-id="a7f38-116">Rotating.</span></span>

- <span data-ttu-id="a7f38-117">设置填充和边距。</span><span class="sxs-lookup"><span data-stu-id="a7f38-117">Setting padding and margins.</span></span>

- <span data-ttu-id="a7f38-118">使用动态布局容器。</span><span class="sxs-lookup"><span data-stu-id="a7f38-118">Using dynamic layout containers.</span></span>

<span data-ttu-id="a7f38-119">有关本演练中所述任务的完整代码列表, 请参阅[在 WPF 中排列 Windows 窗体控件示例](https://go.microsoft.com/fwlink/?LinkID=159971)。</span><span class="sxs-lookup"><span data-stu-id="a7f38-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>

<span data-ttu-id="a7f38-120">完成后, 你将了解基于应用程序的[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]布局[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]功能。</span><span class="sxs-lookup"><span data-stu-id="a7f38-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a7f38-121">系统必备</span><span class="sxs-lookup"><span data-stu-id="a7f38-121">Prerequisites</span></span>

<span data-ttu-id="a7f38-122">若要完成本演练，必须具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="a7f38-122">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="a7f38-123">创建项目</span><span class="sxs-lookup"><span data-stu-id="a7f38-123">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="a7f38-124">创建并设置项目</span><span class="sxs-lookup"><span data-stu-id="a7f38-124">To create and set up the project</span></span>

1. <span data-ttu-id="a7f38-125">创建一个名为`WpfLayoutHostingWf`的 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="a7f38-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>

2. <span data-ttu-id="a7f38-126">在解决方案资源管理器中，添加对下列程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="a7f38-126">In Solution Explorer, add references to the following assemblies.</span></span>

    - <span data-ttu-id="a7f38-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="a7f38-127">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="a7f38-128">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="a7f38-128">System.Windows.Forms</span></span>

    - <span data-ttu-id="a7f38-129">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="a7f38-129">System.Drawing</span></span>

3. <span data-ttu-id="a7f38-130">双击 MainWindow.xaml，在 XAML 视图中将其打开。</span><span class="sxs-lookup"><span data-stu-id="a7f38-130">Double-click MainWindow.xaml to open it in XAML view.</span></span>

4. <span data-ttu-id="a7f38-131">在元素中, 添加以下[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]命名空间映射。 <xref:System.Windows.Window></span><span class="sxs-lookup"><span data-stu-id="a7f38-131">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="a7f38-132">在元素中, <xref:System.Windows.Controls.Grid.ShowGridLines%2A>将属性设置`true`为, 并定义五行和三列。 <xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="a7f38-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a><span data-ttu-id="a7f38-133">使用默认布局设置</span><span class="sxs-lookup"><span data-stu-id="a7f38-133">Using Default Layout Settings</span></span>

<span data-ttu-id="a7f38-134">默认情况下, <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素处理承载[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]的控件的布局。</span><span class="sxs-lookup"><span data-stu-id="a7f38-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

### <a name="to-use-default-layout-settings"></a><span data-ttu-id="a7f38-135">使用默认布局设置</span><span class="sxs-lookup"><span data-stu-id="a7f38-135">To use default layout settings</span></span>

1. <span data-ttu-id="a7f38-136">将以下 XAML 复制到<xref:System.Windows.Controls.Grid>元素中。</span><span class="sxs-lookup"><span data-stu-id="a7f38-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. <span data-ttu-id="a7f38-137">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7f38-137">Press F5 to build and run the application.</span></span> <span data-ttu-id="a7f38-138">控件将出现在中<xref:System.Windows.Controls.Canvas>。 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="a7f38-138">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="a7f38-139">承载的控件根据其内容调整大小, 并<xref:System.Windows.Forms.Integration.WindowsFormsHost>调整元素大小以容纳承载的控件。</span><span class="sxs-lookup"><span data-stu-id="a7f38-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>

## <a name="sizing-to-content"></a><span data-ttu-id="a7f38-140">按内容调整大小</span><span class="sxs-lookup"><span data-stu-id="a7f38-140">Sizing to Content</span></span>

<span data-ttu-id="a7f38-141"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素确保所承载的控件的大小调整为正确显示其内容。</span><span class="sxs-lookup"><span data-stu-id="a7f38-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>

### <a name="to-size-to-content"></a><span data-ttu-id="a7f38-142">按内容调整大小</span><span class="sxs-lookup"><span data-stu-id="a7f38-142">To size to content</span></span>

1. <span data-ttu-id="a7f38-143">将以下 XAML 复制到<xref:System.Windows.Controls.Grid>元素中。</span><span class="sxs-lookup"><span data-stu-id="a7f38-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. <span data-ttu-id="a7f38-144">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7f38-144">Press F5 to build and run the application.</span></span> <span data-ttu-id="a7f38-145">这两个新按钮控件的大小调整为正确显示较长的文本字符串和更大的<xref:System.Windows.Forms.Integration.WindowsFormsHost>字号, 并调整元素的大小以容纳所承载的控件。</span><span class="sxs-lookup"><span data-stu-id="a7f38-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>

## <a name="using-absolute-positioning"></a><span data-ttu-id="a7f38-146">使用绝对定位</span><span class="sxs-lookup"><span data-stu-id="a7f38-146">Using Absolute Positioning</span></span>

<span data-ttu-id="a7f38-147">可以使用绝对定位将<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素放在用户界面 (UI) 中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="a7f38-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>

### <a name="to-use-absolute-positioning"></a><span data-ttu-id="a7f38-148">使用绝对定位</span><span class="sxs-lookup"><span data-stu-id="a7f38-148">To use absolute positioning</span></span>

1. <span data-ttu-id="a7f38-149">将以下 XAML 复制到<xref:System.Windows.Controls.Grid>元素中。</span><span class="sxs-lookup"><span data-stu-id="a7f38-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. <span data-ttu-id="a7f38-150">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7f38-150">Press F5 to build and run the application.</span></span> <span data-ttu-id="a7f38-151">将<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素置于网格单元顶部20个像素的位置, 左侧20个像素。</span><span class="sxs-lookup"><span data-stu-id="a7f38-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>

## <a name="specifying-size-explicitly"></a><span data-ttu-id="a7f38-152">显式指定大小</span><span class="sxs-lookup"><span data-stu-id="a7f38-152">Specifying Size Explicitly</span></span>

<span data-ttu-id="a7f38-153">您可以<xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.FrameworkElement.Width%2A>使用和<xref:System.Windows.FrameworkElement.Height%2A>属性指定元素的大小。</span><span class="sxs-lookup"><span data-stu-id="a7f38-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>

### <a name="to-specify-size-explicitly"></a><span data-ttu-id="a7f38-154">显式指定大小</span><span class="sxs-lookup"><span data-stu-id="a7f38-154">To specify size explicitly</span></span>

1. <span data-ttu-id="a7f38-155">将以下 XAML 复制到<xref:System.Windows.Controls.Grid>元素中。</span><span class="sxs-lookup"><span data-stu-id="a7f38-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. <span data-ttu-id="a7f38-156">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7f38-156">Press F5 to build and run the application.</span></span> <span data-ttu-id="a7f38-157"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的大小设置为50像素宽 x 70 像素高, 小于默认布局设置。</span><span class="sxs-lookup"><span data-stu-id="a7f38-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="a7f38-158">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件的内容会相应地重新排列。</span><span class="sxs-lookup"><span data-stu-id="a7f38-158">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>

## <a name="setting-layout-properties"></a><span data-ttu-id="a7f38-159">设置布局属性</span><span class="sxs-lookup"><span data-stu-id="a7f38-159">Setting Layout Properties</span></span>

<span data-ttu-id="a7f38-160">始终使用<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的属性设置承载控件上与布局相关的属性。</span><span class="sxs-lookup"><span data-stu-id="a7f38-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="a7f38-161">直接对承载控件设置布局属性会产生意外结果。</span><span class="sxs-lookup"><span data-stu-id="a7f38-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>

 <span data-ttu-id="a7f38-162">在中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]的托管控件上设置与布局相关的属性不起作用。</span><span class="sxs-lookup"><span data-stu-id="a7f38-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>

### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="a7f38-163">查看对承载控件设置属性的效果</span><span class="sxs-lookup"><span data-stu-id="a7f38-163">To see the effects of setting properties on the hosted control</span></span>

1. <span data-ttu-id="a7f38-164">将以下 XAML 复制到<xref:System.Windows.Controls.Grid>元素中。</span><span class="sxs-lookup"><span data-stu-id="a7f38-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. <span data-ttu-id="a7f38-165">在“解决方案资源管理器”中，双击 MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="a7f38-165">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="a7f38-166">vb 或 MainWindow.xaml.cs 在代码编辑器中将其打开。</span><span class="sxs-lookup"><span data-stu-id="a7f38-166">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>

3. <span data-ttu-id="a7f38-167">将以下代码复制到`MainWindow`类定义中。</span><span class="sxs-lookup"><span data-stu-id="a7f38-167">Copy the following code into the `MainWindow` class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. <span data-ttu-id="a7f38-168">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7f38-168">Press F5 to build and run the application.</span></span>

5. <span data-ttu-id="a7f38-169">单击 "**单击**此按钮"。</span><span class="sxs-lookup"><span data-stu-id="a7f38-169">Click the **Click me** button.</span></span> <span data-ttu-id="a7f38-170">事件处理程序在承载<xref:System.Windows.Forms.Control.Top%2A>控件<xref:System.Windows.Forms.Control.Left%2A>上设置和属性。 `button1_Click`</span><span class="sxs-lookup"><span data-stu-id="a7f38-170">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="a7f38-171">这会导致在<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素内重新定位承载的控件。</span><span class="sxs-lookup"><span data-stu-id="a7f38-171">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="a7f38-172">宿主保持相同的屏幕区域，但承载控件被剪裁。</span><span class="sxs-lookup"><span data-stu-id="a7f38-172">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="a7f38-173">托管控件应始终填充<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素。</span><span class="sxs-lookup"><span data-stu-id="a7f38-173">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="a7f38-174">了解 Z 顺序限制</span><span class="sxs-lookup"><span data-stu-id="a7f38-174">Understanding Z-Order Limitations</span></span>

<span data-ttu-id="a7f38-175">可见<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素始终在其他 WPF 元素之上绘制, 并且不受 z 顺序的影响。</span><span class="sxs-lookup"><span data-stu-id="a7f38-175">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="a7f38-176">若要查看此 z 顺序行为, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="a7f38-176">To see this z-order behavior, do the following:</span></span>

1. <span data-ttu-id="a7f38-177">将以下 XAML 复制到<xref:System.Windows.Controls.Grid>元素中。</span><span class="sxs-lookup"><span data-stu-id="a7f38-177">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. <span data-ttu-id="a7f38-178">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7f38-178">Press F5 to build and run the application.</span></span> <span data-ttu-id="a7f38-179"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素在标签元素上绘制。</span><span class="sxs-lookup"><span data-stu-id="a7f38-179">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="a7f38-180">停靠</span><span class="sxs-lookup"><span data-stu-id="a7f38-180">Docking</span></span>

<span data-ttu-id="a7f38-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素支持[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]停靠。</span><span class="sxs-lookup"><span data-stu-id="a7f38-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="a7f38-182">设置附加属性以将承载的控件停靠<xref:System.Windows.Controls.DockPanel>在元素中。 <xref:System.Windows.Controls.DockPanel.Dock%2A></span><span class="sxs-lookup"><span data-stu-id="a7f38-182">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="a7f38-183">停靠承载控件</span><span class="sxs-lookup"><span data-stu-id="a7f38-183">To dock a hosted control</span></span>

1. <span data-ttu-id="a7f38-184">将以下 XAML 复制到<xref:System.Windows.Controls.Grid>元素中。</span><span class="sxs-lookup"><span data-stu-id="a7f38-184">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. <span data-ttu-id="a7f38-185">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7f38-185">Press F5 to build and run the application.</span></span> <span data-ttu-id="a7f38-186">元素停靠在<xref:System.Windows.Controls.DockPanel>元素的右侧。 <xref:System.Windows.Forms.Integration.WindowsFormsHost></span><span class="sxs-lookup"><span data-stu-id="a7f38-186">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="a7f38-187">设置可见性</span><span class="sxs-lookup"><span data-stu-id="a7f38-187">Setting Visibility</span></span>

<span data-ttu-id="a7f38-188">可以通过在[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素上<xref:System.Windows.UIElement.Visibility%2A>设置属性, 使控件不可见或折叠。</span><span class="sxs-lookup"><span data-stu-id="a7f38-188">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="a7f38-189">当控件不可见时，控件不会显示，但会占据布局空间。</span><span class="sxs-lookup"><span data-stu-id="a7f38-189">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="a7f38-190">当控件处于折叠状态时，控件不会显示，也不会占据布局空间。</span><span class="sxs-lookup"><span data-stu-id="a7f38-190">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="a7f38-191">设置承载控件的可见性</span><span class="sxs-lookup"><span data-stu-id="a7f38-191">To set the visibility of a hosted control</span></span>

1. <span data-ttu-id="a7f38-192">将以下 XAML 复制到<xref:System.Windows.Controls.Grid>元素中。</span><span class="sxs-lookup"><span data-stu-id="a7f38-192">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. <span data-ttu-id="a7f38-193">在 MainWindow.xaml.vb 或 MainWindow.xaml.cs 中，将以下代码复制到类定义。</span><span class="sxs-lookup"><span data-stu-id="a7f38-193">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. <span data-ttu-id="a7f38-194">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7f38-194">Press F5 to build and run the application.</span></span>

4. <span data-ttu-id="a7f38-195">单击 "**单击以使不可见**" <xref:System.Windows.Forms.Integration.WindowsFormsHost>按钮, 使元素不可见。</span><span class="sxs-lookup"><span data-stu-id="a7f38-195">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5. <span data-ttu-id="a7f38-196">单击 "**单击以折叠**" 按钮可完全<xref:System.Windows.Forms.Integration.WindowsFormsHost>隐藏布局中的元素。</span><span class="sxs-lookup"><span data-stu-id="a7f38-196">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="a7f38-197">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]当控件处于折叠状态时, 会重新排列周围的元素以占用其空间。</span><span class="sxs-lookup"><span data-stu-id="a7f38-197">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="a7f38-198">承载不拉伸的控件</span><span class="sxs-lookup"><span data-stu-id="a7f38-198">Hosting a Control That Does Not Stretch</span></span>

<span data-ttu-id="a7f38-199">某些[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件具有固定大小, 因此不拉伸以填充布局中的可用空间。</span><span class="sxs-lookup"><span data-stu-id="a7f38-199">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="a7f38-200">例如, <xref:System.Windows.Forms.MonthCalendar>控件在固定空间中显示月份。</span><span class="sxs-lookup"><span data-stu-id="a7f38-200">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="a7f38-201">承载不拉伸的控件</span><span class="sxs-lookup"><span data-stu-id="a7f38-201">To host a control that does not stretch</span></span>

1. <span data-ttu-id="a7f38-202">将以下 XAML 复制到<xref:System.Windows.Controls.Grid>元素中。</span><span class="sxs-lookup"><span data-stu-id="a7f38-202">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. <span data-ttu-id="a7f38-203">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7f38-203">Press F5 to build and run the application.</span></span> <span data-ttu-id="a7f38-204"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素在网格行中居中, 但不拉伸以填充可用空间。</span><span class="sxs-lookup"><span data-stu-id="a7f38-204">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="a7f38-205">如果窗口足够大, 则可能会看到由寄宿<xref:System.Windows.Forms.MonthCalendar>控件显示的两个或多个月份, 但这两个月居中显示在行中。</span><span class="sxs-lookup"><span data-stu-id="a7f38-205">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="a7f38-206">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]布局引擎中心元素无法调整大小以填充可用空间。</span><span class="sxs-lookup"><span data-stu-id="a7f38-206">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="a7f38-207">缩放</span><span class="sxs-lookup"><span data-stu-id="a7f38-207">Scaling</span></span>

<span data-ttu-id="a7f38-208">与 WPF 元素不同, 大多数 Windows 窗体控件不是持续缩放的。</span><span class="sxs-lookup"><span data-stu-id="a7f38-208">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="a7f38-209">若要提供自定义缩放, 请<xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType>重写方法。</span><span class="sxs-lookup"><span data-stu-id="a7f38-209">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="a7f38-210">使用默认行为缩放承载控件</span><span class="sxs-lookup"><span data-stu-id="a7f38-210">To scale a hosted control by using the default behavior</span></span>

1. <span data-ttu-id="a7f38-211">将以下 XAML 复制到<xref:System.Windows.Controls.Grid>元素中。</span><span class="sxs-lookup"><span data-stu-id="a7f38-211">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. <span data-ttu-id="a7f38-212">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7f38-212">Press F5 to build and run the application.</span></span> <span data-ttu-id="a7f38-213">承载控件及其周围元素按 0.5 的比例进行缩放。</span><span class="sxs-lookup"><span data-stu-id="a7f38-213">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="a7f38-214">但是，承载控件的字体不缩放。</span><span class="sxs-lookup"><span data-stu-id="a7f38-214">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="a7f38-215">旋转</span><span class="sxs-lookup"><span data-stu-id="a7f38-215">Rotating</span></span>

<span data-ttu-id="a7f38-216">与 WPF 元素不同, Windows 窗体控件不支持旋转。</span><span class="sxs-lookup"><span data-stu-id="a7f38-216">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="a7f38-217">应用<xref:System.Windows.Forms.Integration.WindowsFormsHost>旋转转换后, 元素不会随其他 WPF 元素一起旋转。</span><span class="sxs-lookup"><span data-stu-id="a7f38-217">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="a7f38-218">180度以外的<xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>任何旋转值都会引发事件。</span><span class="sxs-lookup"><span data-stu-id="a7f38-218">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="a7f38-219">查看混合应用程序中的旋转效果</span><span class="sxs-lookup"><span data-stu-id="a7f38-219">To see the effect of rotation in a hybrid application</span></span>

1. <span data-ttu-id="a7f38-220">将以下 XAML 复制到<xref:System.Windows.Controls.Grid>元素中。</span><span class="sxs-lookup"><span data-stu-id="a7f38-220">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. <span data-ttu-id="a7f38-221">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7f38-221">Press F5 to build and run the application.</span></span> <span data-ttu-id="a7f38-222">承载控件不旋转，但是它周围的元素旋转 180 度。</span><span class="sxs-lookup"><span data-stu-id="a7f38-222">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="a7f38-223">可能必须调整窗口大小才能看到这些元素。</span><span class="sxs-lookup"><span data-stu-id="a7f38-223">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="a7f38-224">设置填充和边距</span><span class="sxs-lookup"><span data-stu-id="a7f38-224">Setting Padding and Margins</span></span>

<span data-ttu-id="a7f38-225">布局中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的填充和边距类似于中的[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]填充和边距。</span><span class="sxs-lookup"><span data-stu-id="a7f38-225">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="a7f38-226">只需在<xref:System.Windows.Controls.Control.Padding%2A> <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素<xref:System.Windows.FrameworkElement.Margin%2A>上设置和属性即可。</span><span class="sxs-lookup"><span data-stu-id="a7f38-226">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="a7f38-227">为承载控件设置填充和边距</span><span class="sxs-lookup"><span data-stu-id="a7f38-227">To set padding and margins for a hosted control</span></span>

1. <span data-ttu-id="a7f38-228">将以下 XAML 复制到<xref:System.Windows.Controls.Grid>元素中。</span><span class="sxs-lookup"><span data-stu-id="a7f38-228">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. <span data-ttu-id="a7f38-229">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7f38-229">Press F5 to build and run the application.</span></span> <span data-ttu-id="a7f38-230">填充和边距设置以应用于的相同方式[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]应用于承载的控件。</span><span class="sxs-lookup"><span data-stu-id="a7f38-230">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="a7f38-231">使用动态布局容器</span><span class="sxs-lookup"><span data-stu-id="a7f38-231">Using Dynamic Layout Containers</span></span>

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="a7f38-232">提供两个动态布局容器<xref:System.Windows.Forms.FlowLayoutPanel> : <xref:System.Windows.Forms.TableLayoutPanel>和。</span><span class="sxs-lookup"><span data-stu-id="a7f38-232">provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="a7f38-233">你还可以在布局中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]使用这些容器。</span><span class="sxs-lookup"><span data-stu-id="a7f38-233">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="a7f38-234">使用动态布局容器</span><span class="sxs-lookup"><span data-stu-id="a7f38-234">To use a dynamic layout container</span></span>

1. <span data-ttu-id="a7f38-235">将以下 XAML 复制到<xref:System.Windows.Controls.Grid>元素中。</span><span class="sxs-lookup"><span data-stu-id="a7f38-235">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. <span data-ttu-id="a7f38-236">在 MainWindow.xaml.vb 或 MainWindow.xaml.cs 中，将以下代码复制到类定义。</span><span class="sxs-lookup"><span data-stu-id="a7f38-236">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. <span data-ttu-id="a7f38-237">将调用添加到构造函数中的 `InitializeFlowLayoutPanel` 方法。</span><span class="sxs-lookup"><span data-stu-id="a7f38-237">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. <span data-ttu-id="a7f38-238">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7f38-238">Press F5 to build and run the application.</span></span> <span data-ttu-id="a7f38-239">元素填充, 并<xref:System.Windows.Forms.FlowLayoutPanel>将其子控件排列为默认值<xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>。 <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Controls.DockPanel></span><span class="sxs-lookup"><span data-stu-id="a7f38-239">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7f38-240">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7f38-240">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="a7f38-241">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="a7f38-241">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="a7f38-242">WindowsFormsHost 元素的布局注意事项</span><span class="sxs-lookup"><span data-stu-id="a7f38-242">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="a7f38-243">在 WPF 中排列 Windows 窗体控件示例</span><span class="sxs-lookup"><span data-stu-id="a7f38-243">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)
- [<span data-ttu-id="a7f38-244">演练：在 WPF 中承载 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="a7f38-244">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="a7f38-245">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="a7f38-245">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
