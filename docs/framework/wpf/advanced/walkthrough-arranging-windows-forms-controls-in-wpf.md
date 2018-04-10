---
title: 演练：在 WPF 中排列 Windows 窗体控件
ms.custom: ''
ms.date: 04/03/2018
ms.prod: .net-framework
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4f3129b4128444530b1277299f3f95ce49232421
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="de1f5-102">演练：在 WPF 中排列 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="de1f5-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>
<span data-ttu-id="de1f5-103">本演练演示如何使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]布局功能来排列[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]混合应用程序中的控件。</span><span class="sxs-lookup"><span data-stu-id="de1f5-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>  
  
 <span data-ttu-id="de1f5-104">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="de1f5-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="de1f5-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="de1f5-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="de1f5-106">使用默认布局设置。</span><span class="sxs-lookup"><span data-stu-id="de1f5-106">Using default layout settings.</span></span>  
  
-   <span data-ttu-id="de1f5-107">根据内容调整大小。</span><span class="sxs-lookup"><span data-stu-id="de1f5-107">Sizing to content.</span></span>  
  
-   <span data-ttu-id="de1f5-108">使用绝对定位。</span><span class="sxs-lookup"><span data-stu-id="de1f5-108">Using absolute positioning.</span></span>  
  
-   <span data-ttu-id="de1f5-109">显式指定大小。</span><span class="sxs-lookup"><span data-stu-id="de1f5-109">Specifying size explicitly.</span></span>  
  
-   <span data-ttu-id="de1f5-110">设置布局属性。</span><span class="sxs-lookup"><span data-stu-id="de1f5-110">Setting layout properties.</span></span>  
  
-   <span data-ttu-id="de1f5-111">了解 Z 顺序限制。</span><span class="sxs-lookup"><span data-stu-id="de1f5-111">Understanding z-order limitations.</span></span>  
  
-   <span data-ttu-id="de1f5-112">停靠。</span><span class="sxs-lookup"><span data-stu-id="de1f5-112">Docking.</span></span>  
  
-   <span data-ttu-id="de1f5-113">设置可见性。</span><span class="sxs-lookup"><span data-stu-id="de1f5-113">Setting visibility.</span></span>  
  
-   <span data-ttu-id="de1f5-114">承载不拉伸的控件。</span><span class="sxs-lookup"><span data-stu-id="de1f5-114">Hosting a control that does not stretch.</span></span>  
  
-   <span data-ttu-id="de1f5-115">缩放。</span><span class="sxs-lookup"><span data-stu-id="de1f5-115">Scaling.</span></span>  
  
-   <span data-ttu-id="de1f5-116">旋转。</span><span class="sxs-lookup"><span data-stu-id="de1f5-116">Rotating.</span></span>  
  
-   <span data-ttu-id="de1f5-117">设置填充和边距。</span><span class="sxs-lookup"><span data-stu-id="de1f5-117">Setting padding and margins.</span></span>  
  
-   <span data-ttu-id="de1f5-118">使用动态布局容器。</span><span class="sxs-lookup"><span data-stu-id="de1f5-118">Using dynamic layout containers.</span></span>  
  
 <span data-ttu-id="de1f5-119">本演练的任务的完整代码清单，请参阅[排列 Windows 窗体控件在 WPF 示例](http://go.microsoft.com/fwlink/?LinkID=159971)。</span><span class="sxs-lookup"><span data-stu-id="de1f5-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159971).</span></span>  
  
 <span data-ttu-id="de1f5-120">完成后，你将会了解的[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]布局中的功能[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-基于应用程序。</span><span class="sxs-lookup"><span data-stu-id="de1f5-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="de1f5-121">系统必备</span><span class="sxs-lookup"><span data-stu-id="de1f5-121">Prerequisites</span></span>  
 <span data-ttu-id="de1f5-122">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="de1f5-122">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="de1f5-123">。</span><span class="sxs-lookup"><span data-stu-id="de1f5-123">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="de1f5-124">创建项目</span><span class="sxs-lookup"><span data-stu-id="de1f5-124">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="de1f5-125">创建并设置项目</span><span class="sxs-lookup"><span data-stu-id="de1f5-125">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="de1f5-126">创建一个名为的 WPF 应用程序项目`WpfLayoutHostingWf`。</span><span class="sxs-lookup"><span data-stu-id="de1f5-126">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>  
  
2.  <span data-ttu-id="de1f5-127">在解决方案资源管理器中，添加对下列程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="de1f5-127">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="de1f5-128">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="de1f5-128">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="de1f5-129">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="de1f5-129">System.Windows.Forms</span></span>  
  
    -   <span data-ttu-id="de1f5-130">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="de1f5-130">System.Drawing</span></span>  
  
3.  <span data-ttu-id="de1f5-131">双击 MainWindow.xaml，在 XAML 视图中将其打开。</span><span class="sxs-lookup"><span data-stu-id="de1f5-131">Double-click MainWindow.xaml to open it in XAML view.</span></span>  
  
4.  <span data-ttu-id="de1f5-132">在<xref:System.Windows.Window>元素中，添加以下[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]命名空间映射。</span><span class="sxs-lookup"><span data-stu-id="de1f5-132">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="de1f5-133">在<xref:System.Windows.Controls.Grid>元素集<xref:System.Windows.Controls.Grid.ShowGridLines%2A>属性`true`并定义 5 行和三个列。</span><span class="sxs-lookup"><span data-stu-id="de1f5-133">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a><span data-ttu-id="de1f5-134">使用默认布局设置</span><span class="sxs-lookup"><span data-stu-id="de1f5-134">Using Default Layout Settings</span></span>  
 <span data-ttu-id="de1f5-135">默认情况下，<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素独立处理的布局将托管的[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件。</span><span class="sxs-lookup"><span data-stu-id="de1f5-135">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-use-default-layout-settings"></a><span data-ttu-id="de1f5-136">使用默认布局设置</span><span class="sxs-lookup"><span data-stu-id="de1f5-136">To use default layout settings</span></span>  
  
1.  <span data-ttu-id="de1f5-137">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-137">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  <span data-ttu-id="de1f5-138">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="de1f5-138">Press F5 to build and run the application.</span></span> <span data-ttu-id="de1f5-139">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType>控件会出现在<xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="de1f5-139">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="de1f5-140">托管的控件根据其内容调整大小和<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素大小以适应所承载的控件。</span><span class="sxs-lookup"><span data-stu-id="de1f5-140">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>  
  
## <a name="sizing-to-content"></a><span data-ttu-id="de1f5-141">按内容调整大小</span><span class="sxs-lookup"><span data-stu-id="de1f5-141">Sizing to Content</span></span>  
 <span data-ttu-id="de1f5-142"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素可确保托管的控件调整大小以正确显示其内容。</span><span class="sxs-lookup"><span data-stu-id="de1f5-142">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>  
  
#### <a name="to-size-to-content"></a><span data-ttu-id="de1f5-143">按内容调整大小</span><span class="sxs-lookup"><span data-stu-id="de1f5-143">To size to content</span></span>  
  
1.  <span data-ttu-id="de1f5-144">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-144">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  <span data-ttu-id="de1f5-145">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="de1f5-145">Press F5 to build and run the application.</span></span> <span data-ttu-id="de1f5-146">两个新的按钮控件可以调整大小，以正确，显示的较长的文本字符串和更大的字体大小和<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的大小以适应所承载的控件。</span><span class="sxs-lookup"><span data-stu-id="de1f5-146">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>  
  
## <a name="using-absolute-positioning"></a><span data-ttu-id="de1f5-147">使用绝对定位</span><span class="sxs-lookup"><span data-stu-id="de1f5-147">Using Absolute Positioning</span></span>  
 <span data-ttu-id="de1f5-148">你可以使用绝对定位将放置<xref:System.Windows.Forms.Integration.WindowsFormsHost>任意位置中的用户界面 (UI) 元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-148">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>  
  
#### <a name="to-use-absolute-positioning"></a><span data-ttu-id="de1f5-149">使用绝对定位</span><span class="sxs-lookup"><span data-stu-id="de1f5-149">To use absolute positioning</span></span>  
  
1.  <span data-ttu-id="de1f5-150">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-150">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  <span data-ttu-id="de1f5-151">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="de1f5-151">Press F5 to build and run the application.</span></span> <span data-ttu-id="de1f5-152"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素位于顶部的网格单元格从 20 像素和从左侧起的 20 像素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-152">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>  
  
## <a name="specifying-size-explicitly"></a><span data-ttu-id="de1f5-153">显式指定大小</span><span class="sxs-lookup"><span data-stu-id="de1f5-153">Specifying Size Explicitly</span></span>  
 <span data-ttu-id="de1f5-154">你可以指定的大小<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素使用<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="de1f5-154">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>  
  
#### <a name="to-specify-size-explicitly"></a><span data-ttu-id="de1f5-155">显式指定大小</span><span class="sxs-lookup"><span data-stu-id="de1f5-155">To specify size explicitly</span></span>  
  
1.  <span data-ttu-id="de1f5-156">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-156">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  <span data-ttu-id="de1f5-157">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="de1f5-157">Press F5 to build and run the application.</span></span> <span data-ttu-id="de1f5-158"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素设置为的大小为 50 像素宽乘 70 像素高，则该值小于默认布局设置。</span><span class="sxs-lookup"><span data-stu-id="de1f5-158">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="de1f5-159">内容[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]相应地重新排列控件。</span><span class="sxs-lookup"><span data-stu-id="de1f5-159">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>  
  
## <a name="setting-layout-properties"></a><span data-ttu-id="de1f5-160">设置布局属性</span><span class="sxs-lookup"><span data-stu-id="de1f5-160">Setting Layout Properties</span></span>  
 <span data-ttu-id="de1f5-161">始终使用的属性在托管控件上设置布局相关属性<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-161">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="de1f5-162">直接对承载控件设置布局属性会产生意外结果。</span><span class="sxs-lookup"><span data-stu-id="de1f5-162">Setting layout properties directly on the hosted control will yield unintended results.</span></span>  
  
 <span data-ttu-id="de1f5-163">设置托管控件中的布局相关属性[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]不起作用。</span><span class="sxs-lookup"><span data-stu-id="de1f5-163">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="de1f5-164">查看对承载控件设置属性的效果</span><span class="sxs-lookup"><span data-stu-id="de1f5-164">To see the effects of setting properties on the hosted control</span></span>  
  
1.  <span data-ttu-id="de1f5-165">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-165">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  <span data-ttu-id="de1f5-166">在“解决方案资源管理器”中，双击 MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="de1f5-166">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="de1f5-167">vb 或 MainWindow.xaml.cs 在代码编辑器中将其打开。</span><span class="sxs-lookup"><span data-stu-id="de1f5-167">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>  
  
3.  <span data-ttu-id="de1f5-168">下面的代码复制到`MainWindow`类定义。</span><span class="sxs-lookup"><span data-stu-id="de1f5-168">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  <span data-ttu-id="de1f5-169">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="de1f5-169">Press F5 to build and run the application.</span></span>  
  
5.  <span data-ttu-id="de1f5-170">单击**Click me**按钮。</span><span class="sxs-lookup"><span data-stu-id="de1f5-170">Click the **Click me** button.</span></span> <span data-ttu-id="de1f5-171">`button1_Click`事件处理程序将设置<xref:System.Windows.Forms.Control.Top%2A>和<xref:System.Windows.Forms.Control.Left%2A>托管控件的属性。</span><span class="sxs-lookup"><span data-stu-id="de1f5-171">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="de1f5-172">这将导致托管的控件中被重新定位<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-172">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="de1f5-173">宿主保持相同的屏幕区域，但承载控件被剪裁。</span><span class="sxs-lookup"><span data-stu-id="de1f5-173">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="de1f5-174">相反，应始终填充托管的控件<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-174">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
## <a name="understanding-z-order-limitations"></a><span data-ttu-id="de1f5-175">了解 Z 顺序限制</span><span class="sxs-lookup"><span data-stu-id="de1f5-175">Understanding Z-Order Limitations</span></span>  
 <span data-ttu-id="de1f5-176">可见<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素始终绘制基于其他 WPF 元素，并且它们会受到影响按 z 顺序。</span><span class="sxs-lookup"><span data-stu-id="de1f5-176">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="de1f5-177">若要查看此 z 顺序行为，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="de1f5-177">To see this z-order behavior, do the following:</span></span>

1.  <span data-ttu-id="de1f5-178">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-178">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
 
2.  <span data-ttu-id="de1f5-179">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="de1f5-179">Press F5 to build and run the application.</span></span> <span data-ttu-id="de1f5-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素绘制通过 label 元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-180">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>  


## <a name="docking"></a><span data-ttu-id="de1f5-181">停靠</span><span class="sxs-lookup"><span data-stu-id="de1f5-181">Docking</span></span>  
 <span data-ttu-id="de1f5-182"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素支持[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]停靠。</span><span class="sxs-lookup"><span data-stu-id="de1f5-182"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="de1f5-183">设置<xref:System.Windows.Controls.DockPanel.Dock%2A>附加属性停靠在托管的控件<xref:System.Windows.Controls.DockPanel>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-183">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
#### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="de1f5-184">停靠承载控件</span><span class="sxs-lookup"><span data-stu-id="de1f5-184">To dock a hosted control</span></span>  
  
1.  <span data-ttu-id="de1f5-185">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-185">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  <span data-ttu-id="de1f5-186">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="de1f5-186">Press F5 to build and run the application.</span></span> <span data-ttu-id="de1f5-187"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素沿停靠的右侧<xref:System.Windows.Controls.DockPanel>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-187">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
## <a name="setting-visibility"></a><span data-ttu-id="de1f5-188">设置可见性</span><span class="sxs-lookup"><span data-stu-id="de1f5-188">Setting Visibility</span></span>  
 <span data-ttu-id="de1f5-189">你可以进行你[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件不可见，或通过设置其折叠起来<xref:System.Windows.UIElement.Visibility%2A>属性<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-189">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="de1f5-190">当控件不可见时，控件不会显示，但会占据布局空间。</span><span class="sxs-lookup"><span data-stu-id="de1f5-190">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="de1f5-191">当控件处于折叠状态时，控件不会显示，也不会占据布局空间。</span><span class="sxs-lookup"><span data-stu-id="de1f5-191">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>  
  
#### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="de1f5-192">设置承载控件的可见性</span><span class="sxs-lookup"><span data-stu-id="de1f5-192">To set the visibility of a hosted control</span></span>  
  
1.  <span data-ttu-id="de1f5-193">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-193">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  <span data-ttu-id="de1f5-194">在 MainWindow.xaml.vb 或 MainWindow.xaml.cs 中，将以下代码复制到类定义。</span><span class="sxs-lookup"><span data-stu-id="de1f5-194">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  <span data-ttu-id="de1f5-195">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="de1f5-195">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="de1f5-196">单击**单击此项可使不可见**按钮来制作<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素不可见。</span><span class="sxs-lookup"><span data-stu-id="de1f5-196">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>  
  
5.  <span data-ttu-id="de1f5-197">单击**单击此项可折叠**按钮以隐藏<xref:System.Windows.Forms.Integration.WindowsFormsHost>从布局元素完全。</span><span class="sxs-lookup"><span data-stu-id="de1f5-197">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="de1f5-198">当[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件处于折叠状态，周围元素排列以占据其空间。</span><span class="sxs-lookup"><span data-stu-id="de1f5-198">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>  
  
## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="de1f5-199">承载不拉伸的控件</span><span class="sxs-lookup"><span data-stu-id="de1f5-199">Hosting a Control That Does Not Stretch</span></span>  
 <span data-ttu-id="de1f5-200">某些[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件具有固定的大小，而且不会拉伸以填充在布局中的可用空间。</span><span class="sxs-lookup"><span data-stu-id="de1f5-200">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="de1f5-201">例如，<xref:System.Windows.Forms.MonthCalendar>控件可以显示固定空间中的每个月。</span><span class="sxs-lookup"><span data-stu-id="de1f5-201">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>  
  
#### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="de1f5-202">承载不拉伸的控件</span><span class="sxs-lookup"><span data-stu-id="de1f5-202">To host a control that does not stretch</span></span>  
  
1.  <span data-ttu-id="de1f5-203">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-203">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  <span data-ttu-id="de1f5-204">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="de1f5-204">Press F5 to build and run the application.</span></span> <span data-ttu-id="de1f5-205"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素居中在网格行中，但它不会拉伸以填充可用空间。</span><span class="sxs-lookup"><span data-stu-id="de1f5-205">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="de1f5-206">如果该窗口是足够大，可能会看到显示由所承载的两个或多个月<xref:System.Windows.Forms.MonthCalendar>控件，但这些为中心的行中。</span><span class="sxs-lookup"><span data-stu-id="de1f5-206">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="de1f5-207">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]布局引擎中心不能调整大小以填充可用空间的元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-207">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>  
  
## <a name="scaling"></a><span data-ttu-id="de1f5-208">缩放</span><span class="sxs-lookup"><span data-stu-id="de1f5-208">Scaling</span></span>  
 <span data-ttu-id="de1f5-209">与 WPF 元素不同大多数 Windows 窗体控件不是连续的可缩放的。</span><span class="sxs-lookup"><span data-stu-id="de1f5-209">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="de1f5-210">若要提供自定义缩放，重写<xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="de1f5-210">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span> 
  
#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="de1f5-211">使用默认行为缩放承载控件</span><span class="sxs-lookup"><span data-stu-id="de1f5-211">To scale a hosted control by using the default behavior</span></span>  
  
1.  <span data-ttu-id="de1f5-212">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-212">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  <span data-ttu-id="de1f5-213">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="de1f5-213">Press F5 to build and run the application.</span></span> <span data-ttu-id="de1f5-214">承载控件及其周围元素按 0.5 的比例进行缩放。</span><span class="sxs-lookup"><span data-stu-id="de1f5-214">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="de1f5-215">但是，承载控件的字体不缩放。</span><span class="sxs-lookup"><span data-stu-id="de1f5-215">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="de1f5-216">旋转</span><span class="sxs-lookup"><span data-stu-id="de1f5-216">Rotating</span></span>  
 <span data-ttu-id="de1f5-217">WPF 与元素不同，Windows 窗体控件不支持旋转。</span><span class="sxs-lookup"><span data-stu-id="de1f5-217">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="de1f5-218"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素在应用的旋转转换时不旋转与其他 WPF 元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-218">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="de1f5-219">非 180 度引发的任何旋转值<xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>事件。</span><span class="sxs-lookup"><span data-stu-id="de1f5-219">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>
 
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="de1f5-220">查看混合应用程序中的旋转效果</span><span class="sxs-lookup"><span data-stu-id="de1f5-220">To see the effect of rotation in a hybrid application</span></span>  
  
1.  <span data-ttu-id="de1f5-221">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-221">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  <span data-ttu-id="de1f5-222">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="de1f5-222">Press F5 to build and run the application.</span></span> <span data-ttu-id="de1f5-223">承载控件不旋转，但是它周围的元素旋转 180 度。</span><span class="sxs-lookup"><span data-stu-id="de1f5-223">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="de1f5-224">可能必须调整窗口大小才能看到这些元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-224">You may have to resize the window to see the elements.</span></span>  
 

## <a name="setting-padding-and-margins"></a><span data-ttu-id="de1f5-225">设置填充和边距</span><span class="sxs-lookup"><span data-stu-id="de1f5-225">Setting Padding and Margins</span></span>  
 <span data-ttu-id="de1f5-226">填充和边距中的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]布局是类似于填充和边距中的[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="de1f5-226">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="de1f5-227">只需设置<xref:System.Windows.Controls.Control.Padding%2A>和<xref:System.Windows.FrameworkElement.Margin%2A>属性<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-227">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="de1f5-228">为承载控件设置填充和边距</span><span class="sxs-lookup"><span data-stu-id="de1f5-228">To set padding and margins for a hosted control</span></span>  
  
1.  <span data-ttu-id="de1f5-229">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-229">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  <span data-ttu-id="de1f5-230">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="de1f5-230">Press F5 to build and run the application.</span></span> <span data-ttu-id="de1f5-231">填充和边距设置适用于承载[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]与它们将按应用相同的方式控件[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="de1f5-231">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="de1f5-232">使用动态布局容器</span><span class="sxs-lookup"><span data-stu-id="de1f5-232">Using Dynamic Layout Containers</span></span>  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="de1f5-233"> 提供两个动态布局容器，<xref:System.Windows.Forms.FlowLayoutPanel>和<xref:System.Windows.Forms.TableLayoutPanel>。</span><span class="sxs-lookup"><span data-stu-id="de1f5-233"> provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="de1f5-234">你还可以使用这些容器中的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]布局。</span><span class="sxs-lookup"><span data-stu-id="de1f5-234">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>  
  
#### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="de1f5-235">使用动态布局容器</span><span class="sxs-lookup"><span data-stu-id="de1f5-235">To use a dynamic layout container</span></span>  
  
1.  <span data-ttu-id="de1f5-236">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="de1f5-236">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  <span data-ttu-id="de1f5-237">在 MainWindow.xaml.vb 或 MainWindow.xaml.cs 中，将以下代码复制到类定义。</span><span class="sxs-lookup"><span data-stu-id="de1f5-237">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  <span data-ttu-id="de1f5-238">添加对的调用`InitializeFlowLayoutPanel`构造函数中的方法。</span><span class="sxs-lookup"><span data-stu-id="de1f5-238">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  <span data-ttu-id="de1f5-239">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="de1f5-239">Press F5 to build and run the application.</span></span> <span data-ttu-id="de1f5-240"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素填充<xref:System.Windows.Controls.DockPanel>，和<xref:System.Windows.Forms.FlowLayoutPanel>排列其子控件在默认<xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>。</span><span class="sxs-lookup"><span data-stu-id="de1f5-240">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de1f5-241">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de1f5-241">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="de1f5-242">WPF 设计器</span><span class="sxs-lookup"><span data-stu-id="de1f5-242">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="de1f5-243">WindowsFormsHost 元素的布局注意事项</span><span class="sxs-lookup"><span data-stu-id="de1f5-243">Layout Considerations for the WindowsFormsHost Element</span></span>](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)  
 [<span data-ttu-id="de1f5-244">排列 Windows 窗体控件在 WPF 示例</span><span class="sxs-lookup"><span data-stu-id="de1f5-244">Arranging Windows Forms Controls in WPF Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [<span data-ttu-id="de1f5-245">演练：在 WPF 中托管 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="de1f5-245">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="de1f5-246">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="de1f5-246">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
