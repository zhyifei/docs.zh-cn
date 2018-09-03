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
ms.openlocfilehash: 98b108be518a9fef03ee299d43ed591cf736f68f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484934"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="c8d50-102">演练：在 WPF 中排列 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="c8d50-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>
<span data-ttu-id="c8d50-103">本演练演示如何使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]布局功能来排列[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]混合应用程序中的控件。</span><span class="sxs-lookup"><span data-stu-id="c8d50-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>  
  
 <span data-ttu-id="c8d50-104">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="c8d50-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="c8d50-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="c8d50-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="c8d50-106">使用默认布局设置。</span><span class="sxs-lookup"><span data-stu-id="c8d50-106">Using default layout settings.</span></span>  
  
-   <span data-ttu-id="c8d50-107">根据内容调整大小。</span><span class="sxs-lookup"><span data-stu-id="c8d50-107">Sizing to content.</span></span>  
  
-   <span data-ttu-id="c8d50-108">使用绝对定位。</span><span class="sxs-lookup"><span data-stu-id="c8d50-108">Using absolute positioning.</span></span>  
  
-   <span data-ttu-id="c8d50-109">显式指定大小。</span><span class="sxs-lookup"><span data-stu-id="c8d50-109">Specifying size explicitly.</span></span>  
  
-   <span data-ttu-id="c8d50-110">设置布局属性。</span><span class="sxs-lookup"><span data-stu-id="c8d50-110">Setting layout properties.</span></span>  
  
-   <span data-ttu-id="c8d50-111">了解 Z 顺序限制。</span><span class="sxs-lookup"><span data-stu-id="c8d50-111">Understanding z-order limitations.</span></span>  
  
-   <span data-ttu-id="c8d50-112">停靠。</span><span class="sxs-lookup"><span data-stu-id="c8d50-112">Docking.</span></span>  
  
-   <span data-ttu-id="c8d50-113">设置可见性。</span><span class="sxs-lookup"><span data-stu-id="c8d50-113">Setting visibility.</span></span>  
  
-   <span data-ttu-id="c8d50-114">承载不拉伸的控件。</span><span class="sxs-lookup"><span data-stu-id="c8d50-114">Hosting a control that does not stretch.</span></span>  
  
-   <span data-ttu-id="c8d50-115">缩放。</span><span class="sxs-lookup"><span data-stu-id="c8d50-115">Scaling.</span></span>  
  
-   <span data-ttu-id="c8d50-116">旋转。</span><span class="sxs-lookup"><span data-stu-id="c8d50-116">Rotating.</span></span>  
  
-   <span data-ttu-id="c8d50-117">设置填充和边距。</span><span class="sxs-lookup"><span data-stu-id="c8d50-117">Setting padding and margins.</span></span>  
  
-   <span data-ttu-id="c8d50-118">使用动态布局容器。</span><span class="sxs-lookup"><span data-stu-id="c8d50-118">Using dynamic layout containers.</span></span>  
  
 <span data-ttu-id="c8d50-119">在本演练中所涉及任务的完整代码列表，请参阅[在 WPF 示例中排列 Windows 窗体控件](https://go.microsoft.com/fwlink/?LinkID=159971)。</span><span class="sxs-lookup"><span data-stu-id="c8d50-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>  
  
 <span data-ttu-id="c8d50-120">完成后，必须了解[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]布局中的功能[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-基于应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8d50-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c8d50-121">系统必备</span><span class="sxs-lookup"><span data-stu-id="c8d50-121">Prerequisites</span></span>  
 <span data-ttu-id="c8d50-122">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="c8d50-122">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="c8d50-123">。</span><span class="sxs-lookup"><span data-stu-id="c8d50-123">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="c8d50-124">创建项目</span><span class="sxs-lookup"><span data-stu-id="c8d50-124">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="c8d50-125">创建并设置项目</span><span class="sxs-lookup"><span data-stu-id="c8d50-125">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="c8d50-126">创建一个名为的 WPF 应用程序项目`WpfLayoutHostingWf`。</span><span class="sxs-lookup"><span data-stu-id="c8d50-126">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>  
  
2.  <span data-ttu-id="c8d50-127">在解决方案资源管理器中，添加对下列程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="c8d50-127">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="c8d50-128">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="c8d50-128">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="c8d50-129">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="c8d50-129">System.Windows.Forms</span></span>  
  
    -   <span data-ttu-id="c8d50-130">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="c8d50-130">System.Drawing</span></span>  
  
3.  <span data-ttu-id="c8d50-131">双击 MainWindow.xaml，在 XAML 视图中将其打开。</span><span class="sxs-lookup"><span data-stu-id="c8d50-131">Double-click MainWindow.xaml to open it in XAML view.</span></span>  
  
4.  <span data-ttu-id="c8d50-132">在中<xref:System.Windows.Window>元素中，添加以下[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]命名空间映射。</span><span class="sxs-lookup"><span data-stu-id="c8d50-132">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="c8d50-133">在中<xref:System.Windows.Controls.Grid>元素集<xref:System.Windows.Controls.Grid.ShowGridLines%2A>属性设置为`true`并定义五行三列。</span><span class="sxs-lookup"><span data-stu-id="c8d50-133">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a><span data-ttu-id="c8d50-134">使用默认布局设置</span><span class="sxs-lookup"><span data-stu-id="c8d50-134">Using Default Layout Settings</span></span>  
 <span data-ttu-id="c8d50-135">默认情况下<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素处理承载的布局[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件。</span><span class="sxs-lookup"><span data-stu-id="c8d50-135">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-use-default-layout-settings"></a><span data-ttu-id="c8d50-136">使用默认布局设置</span><span class="sxs-lookup"><span data-stu-id="c8d50-136">To use default layout settings</span></span>  
  
1.  <span data-ttu-id="c8d50-137">将复制到以下 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-137">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  <span data-ttu-id="c8d50-138">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8d50-138">Press F5 to build and run the application.</span></span> <span data-ttu-id="c8d50-139">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType>控件会出现在<xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="c8d50-139">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="c8d50-140">所承载的控件根据其内容调整大小和<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素大小以适应所承载的控件。</span><span class="sxs-lookup"><span data-stu-id="c8d50-140">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>  
  
## <a name="sizing-to-content"></a><span data-ttu-id="c8d50-141">按内容调整大小</span><span class="sxs-lookup"><span data-stu-id="c8d50-141">Sizing to Content</span></span>  
 <span data-ttu-id="c8d50-142"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素可确保所承载的控件调整大小以正确显示其内容。</span><span class="sxs-lookup"><span data-stu-id="c8d50-142">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>  
  
#### <a name="to-size-to-content"></a><span data-ttu-id="c8d50-143">按内容调整大小</span><span class="sxs-lookup"><span data-stu-id="c8d50-143">To size to content</span></span>  
  
1.  <span data-ttu-id="c8d50-144">将复制到以下 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-144">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  <span data-ttu-id="c8d50-145">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8d50-145">Press F5 to build and run the application.</span></span> <span data-ttu-id="c8d50-146">两个新按钮控件会调整大小以正确，显示较长文本字符串和较大字号和<xref:System.Windows.Forms.Integration.WindowsFormsHost>调整元素大小以容纳所承载的控件。</span><span class="sxs-lookup"><span data-stu-id="c8d50-146">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>  
  
## <a name="using-absolute-positioning"></a><span data-ttu-id="c8d50-147">使用绝对定位</span><span class="sxs-lookup"><span data-stu-id="c8d50-147">Using Absolute Positioning</span></span>  
 <span data-ttu-id="c8d50-148">可以使用绝对定位将<xref:System.Windows.Forms.Integration.WindowsFormsHost>用户界面 (UI) 中的任意位置的元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-148">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>  
  
#### <a name="to-use-absolute-positioning"></a><span data-ttu-id="c8d50-149">使用绝对定位</span><span class="sxs-lookup"><span data-stu-id="c8d50-149">To use absolute positioning</span></span>  
  
1.  <span data-ttu-id="c8d50-150">将复制到以下 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-150">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  <span data-ttu-id="c8d50-151">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8d50-151">Press F5 to build and run the application.</span></span> <span data-ttu-id="c8d50-152"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素放在距顶部的网格单元格的 20 像素，距左侧 20 像素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-152">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>  
  
## <a name="specifying-size-explicitly"></a><span data-ttu-id="c8d50-153">显式指定大小</span><span class="sxs-lookup"><span data-stu-id="c8d50-153">Specifying Size Explicitly</span></span>  
 <span data-ttu-id="c8d50-154">可以指定的大小<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素使用<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="c8d50-154">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>  
  
#### <a name="to-specify-size-explicitly"></a><span data-ttu-id="c8d50-155">显式指定大小</span><span class="sxs-lookup"><span data-stu-id="c8d50-155">To specify size explicitly</span></span>  
  
1.  <span data-ttu-id="c8d50-156">将复制到以下 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-156">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  <span data-ttu-id="c8d50-157">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8d50-157">Press F5 to build and run the application.</span></span> <span data-ttu-id="c8d50-158"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素设置为的大小为宽 50 像素高 70 像素，这是比默认布局设置小。</span><span class="sxs-lookup"><span data-stu-id="c8d50-158">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="c8d50-159">内容[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]相应重新排列控件。</span><span class="sxs-lookup"><span data-stu-id="c8d50-159">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>  
  
## <a name="setting-layout-properties"></a><span data-ttu-id="c8d50-160">设置布局属性</span><span class="sxs-lookup"><span data-stu-id="c8d50-160">Setting Layout Properties</span></span>  
 <span data-ttu-id="c8d50-161">始终使用的属性对承载控件设置布局相关属性<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-161">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="c8d50-162">直接对承载控件设置布局属性会产生意外结果。</span><span class="sxs-lookup"><span data-stu-id="c8d50-162">Setting layout properties directly on the hosted control will yield unintended results.</span></span>  
  
 <span data-ttu-id="c8d50-163">在承载控件设置布局相关属性[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]不起作用。</span><span class="sxs-lookup"><span data-stu-id="c8d50-163">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="c8d50-164">查看对承载控件设置属性的效果</span><span class="sxs-lookup"><span data-stu-id="c8d50-164">To see the effects of setting properties on the hosted control</span></span>  
  
1.  <span data-ttu-id="c8d50-165">将复制到以下 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-165">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  <span data-ttu-id="c8d50-166">在“解决方案资源管理器”中，双击 MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="c8d50-166">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="c8d50-167">vb 或 MainWindow.xaml.cs 在代码编辑器中将其打开。</span><span class="sxs-lookup"><span data-stu-id="c8d50-167">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>  
  
3.  <span data-ttu-id="c8d50-168">以下代码复制到`MainWindow`类定义。</span><span class="sxs-lookup"><span data-stu-id="c8d50-168">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  <span data-ttu-id="c8d50-169">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8d50-169">Press F5 to build and run the application.</span></span>  
  
5.  <span data-ttu-id="c8d50-170">单击**Click me**按钮。</span><span class="sxs-lookup"><span data-stu-id="c8d50-170">Click the **Click me** button.</span></span> <span data-ttu-id="c8d50-171">`button1_Click`事件处理程序集<xref:System.Windows.Forms.Control.Top%2A>和<xref:System.Windows.Forms.Control.Left%2A>上所承载的控件的属性。</span><span class="sxs-lookup"><span data-stu-id="c8d50-171">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="c8d50-172">这将导致中重新定位承载的控件<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-172">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="c8d50-173">宿主保持相同的屏幕区域，但承载控件被剪裁。</span><span class="sxs-lookup"><span data-stu-id="c8d50-173">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="c8d50-174">相反，所承载的控件应始终填充<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-174">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
## <a name="understanding-z-order-limitations"></a><span data-ttu-id="c8d50-175">了解 Z 顺序限制</span><span class="sxs-lookup"><span data-stu-id="c8d50-175">Understanding Z-Order Limitations</span></span>  
 <span data-ttu-id="c8d50-176">可见<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素始终绘制在其他 WPF 元素，之上，因而它们不受 z 顺序。</span><span class="sxs-lookup"><span data-stu-id="c8d50-176">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="c8d50-177">若要查看此 z 顺序行为，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c8d50-177">To see this z-order behavior, do the following:</span></span>

1.  <span data-ttu-id="c8d50-178">将复制到以下 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-178">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
 
2.  <span data-ttu-id="c8d50-179">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8d50-179">Press F5 to build and run the application.</span></span> <span data-ttu-id="c8d50-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素绘于标签元素上方。</span><span class="sxs-lookup"><span data-stu-id="c8d50-180">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>  


## <a name="docking"></a><span data-ttu-id="c8d50-181">停靠</span><span class="sxs-lookup"><span data-stu-id="c8d50-181">Docking</span></span>  
 <span data-ttu-id="c8d50-182"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素支持[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]停靠。</span><span class="sxs-lookup"><span data-stu-id="c8d50-182"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="c8d50-183">设置<xref:System.Windows.Controls.DockPanel.Dock%2A>附加属性以停靠中承载的控件<xref:System.Windows.Controls.DockPanel>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-183">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
#### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="c8d50-184">停靠承载控件</span><span class="sxs-lookup"><span data-stu-id="c8d50-184">To dock a hosted control</span></span>  
  
1.  <span data-ttu-id="c8d50-185">将复制到以下 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-185">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  <span data-ttu-id="c8d50-186">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8d50-186">Press F5 to build and run the application.</span></span> <span data-ttu-id="c8d50-187"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的右侧停靠<xref:System.Windows.Controls.DockPanel>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-187">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
## <a name="setting-visibility"></a><span data-ttu-id="c8d50-188">设置可见性</span><span class="sxs-lookup"><span data-stu-id="c8d50-188">Setting Visibility</span></span>  
 <span data-ttu-id="c8d50-189">可以让你[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件不可见或通过设置折叠<xref:System.Windows.UIElement.Visibility%2A>属性上的<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-189">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="c8d50-190">当控件不可见时，控件不会显示，但会占据布局空间。</span><span class="sxs-lookup"><span data-stu-id="c8d50-190">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="c8d50-191">当控件处于折叠状态时，控件不会显示，也不会占据布局空间。</span><span class="sxs-lookup"><span data-stu-id="c8d50-191">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>  
  
#### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="c8d50-192">设置承载控件的可见性</span><span class="sxs-lookup"><span data-stu-id="c8d50-192">To set the visibility of a hosted control</span></span>  
  
1.  <span data-ttu-id="c8d50-193">将复制到以下 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-193">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  <span data-ttu-id="c8d50-194">在 MainWindow.xaml.vb 或 MainWindow.xaml.cs 中，将以下代码复制到类定义。</span><span class="sxs-lookup"><span data-stu-id="c8d50-194">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  <span data-ttu-id="c8d50-195">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8d50-195">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="c8d50-196">单击**单击此项可使不可见**按钮，使<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素不可见。</span><span class="sxs-lookup"><span data-stu-id="c8d50-196">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>  
  
5.  <span data-ttu-id="c8d50-197">单击**单击此项可折叠**按钮以隐藏<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素在布局完全。</span><span class="sxs-lookup"><span data-stu-id="c8d50-197">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="c8d50-198">当[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件处于折叠状态，周围的元素会重新排列以占据其空间。</span><span class="sxs-lookup"><span data-stu-id="c8d50-198">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>  
  
## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="c8d50-199">承载不拉伸的控件</span><span class="sxs-lookup"><span data-stu-id="c8d50-199">Hosting a Control That Does Not Stretch</span></span>  
 <span data-ttu-id="c8d50-200">某些[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件具有固定的大小，不会拉伸以填充布局中的可用空间。</span><span class="sxs-lookup"><span data-stu-id="c8d50-200">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="c8d50-201">例如，<xref:System.Windows.Forms.MonthCalendar>控件在固定的空间中显示一个月。</span><span class="sxs-lookup"><span data-stu-id="c8d50-201">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>  
  
#### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="c8d50-202">承载不拉伸的控件</span><span class="sxs-lookup"><span data-stu-id="c8d50-202">To host a control that does not stretch</span></span>  
  
1.  <span data-ttu-id="c8d50-203">将复制到以下 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-203">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  <span data-ttu-id="c8d50-204">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8d50-204">Press F5 to build and run the application.</span></span> <span data-ttu-id="c8d50-205"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素居中在网格行中，但它不会拉伸以填充可用空间。</span><span class="sxs-lookup"><span data-stu-id="c8d50-205">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="c8d50-206">如果窗口足够大，可能会看到显示所承载的两个或多个月<xref:System.Windows.Forms.MonthCalendar>控件，但这些行中居中。</span><span class="sxs-lookup"><span data-stu-id="c8d50-206">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="c8d50-207">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]布局引擎中心无法调整大小以填充可用空间的元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-207">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>  
  
## <a name="scaling"></a><span data-ttu-id="c8d50-208">缩放</span><span class="sxs-lookup"><span data-stu-id="c8d50-208">Scaling</span></span>  
 <span data-ttu-id="c8d50-209">与 WPF 元素不同大多数 Windows 窗体控件不是连续方式缩放。</span><span class="sxs-lookup"><span data-stu-id="c8d50-209">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="c8d50-210">若要提供自定义缩放，重写<xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="c8d50-210">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span> 
  
#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="c8d50-211">使用默认行为缩放承载控件</span><span class="sxs-lookup"><span data-stu-id="c8d50-211">To scale a hosted control by using the default behavior</span></span>  
  
1.  <span data-ttu-id="c8d50-212">将复制到以下 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-212">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  <span data-ttu-id="c8d50-213">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8d50-213">Press F5 to build and run the application.</span></span> <span data-ttu-id="c8d50-214">承载控件及其周围元素按 0.5 的比例进行缩放。</span><span class="sxs-lookup"><span data-stu-id="c8d50-214">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="c8d50-215">但是，承载控件的字体不缩放。</span><span class="sxs-lookup"><span data-stu-id="c8d50-215">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="c8d50-216">旋转</span><span class="sxs-lookup"><span data-stu-id="c8d50-216">Rotating</span></span>  
 <span data-ttu-id="c8d50-217">与 WPF 元素不同 Windows 窗体控件不支持旋转。</span><span class="sxs-lookup"><span data-stu-id="c8d50-217">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="c8d50-218"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素不会不会旋转与其他 WPF 元素时应用旋转转换。</span><span class="sxs-lookup"><span data-stu-id="c8d50-218">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="c8d50-219">180 度引发以外的任何旋转值<xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>事件。</span><span class="sxs-lookup"><span data-stu-id="c8d50-219">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>
 
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="c8d50-220">查看混合应用程序中的旋转效果</span><span class="sxs-lookup"><span data-stu-id="c8d50-220">To see the effect of rotation in a hybrid application</span></span>  
  
1.  <span data-ttu-id="c8d50-221">将复制到以下 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-221">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  <span data-ttu-id="c8d50-222">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8d50-222">Press F5 to build and run the application.</span></span> <span data-ttu-id="c8d50-223">承载控件不旋转，但是它周围的元素旋转 180 度。</span><span class="sxs-lookup"><span data-stu-id="c8d50-223">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="c8d50-224">可能必须调整窗口大小才能看到这些元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-224">You may have to resize the window to see the elements.</span></span>  
 

## <a name="setting-padding-and-margins"></a><span data-ttu-id="c8d50-225">设置填充和边距</span><span class="sxs-lookup"><span data-stu-id="c8d50-225">Setting Padding and Margins</span></span>  
 <span data-ttu-id="c8d50-226">填充和边距中的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]布局是类似于填充和边距中的[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c8d50-226">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="c8d50-227">只需将设置<xref:System.Windows.Controls.Control.Padding%2A>并<xref:System.Windows.FrameworkElement.Margin%2A>上的属性<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-227">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="c8d50-228">为承载控件设置填充和边距</span><span class="sxs-lookup"><span data-stu-id="c8d50-228">To set padding and margins for a hosted control</span></span>  
  
1.  <span data-ttu-id="c8d50-229">将复制到以下 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-229">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  <span data-ttu-id="c8d50-230">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8d50-230">Press F5 to build and run the application.</span></span> <span data-ttu-id="c8d50-231">填充和边距设置应用于承载[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件中的应用方式相同[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c8d50-231">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="c8d50-232">使用动态布局容器</span><span class="sxs-lookup"><span data-stu-id="c8d50-232">Using Dynamic Layout Containers</span></span>  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="c8d50-233"> 提供了两个动态布局容器，<xref:System.Windows.Forms.FlowLayoutPanel>和<xref:System.Windows.Forms.TableLayoutPanel>。</span><span class="sxs-lookup"><span data-stu-id="c8d50-233"> provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="c8d50-234">此外可以使用这些容器[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]布局。</span><span class="sxs-lookup"><span data-stu-id="c8d50-234">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>  
  
#### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="c8d50-235">使用动态布局容器</span><span class="sxs-lookup"><span data-stu-id="c8d50-235">To use a dynamic layout container</span></span>  
  
1.  <span data-ttu-id="c8d50-236">将复制到以下 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="c8d50-236">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  <span data-ttu-id="c8d50-237">在 MainWindow.xaml.vb 或 MainWindow.xaml.cs 中，将以下代码复制到类定义。</span><span class="sxs-lookup"><span data-stu-id="c8d50-237">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  <span data-ttu-id="c8d50-238">添加对的调用`InitializeFlowLayoutPanel`构造函数中的方法。</span><span class="sxs-lookup"><span data-stu-id="c8d50-238">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  <span data-ttu-id="c8d50-239">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8d50-239">Press F5 to build and run the application.</span></span> <span data-ttu-id="c8d50-240"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素填充<xref:System.Windows.Controls.DockPanel>，并<xref:System.Windows.Forms.FlowLayoutPanel>排列其子控件在默认<xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>。</span><span class="sxs-lookup"><span data-stu-id="c8d50-240">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d50-241">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8d50-241">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="c8d50-242">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="c8d50-242">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)  
 [<span data-ttu-id="c8d50-243">WindowsFormsHost 元素的布局注意事项</span><span class="sxs-lookup"><span data-stu-id="c8d50-243">Layout Considerations for the WindowsFormsHost Element</span></span>](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)  
 [<span data-ttu-id="c8d50-244">在 WPF 示例中排列 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="c8d50-244">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)  
 [<span data-ttu-id="c8d50-245">演练：在 WPF 中托管 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="c8d50-245">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="c8d50-246">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="c8d50-246">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
