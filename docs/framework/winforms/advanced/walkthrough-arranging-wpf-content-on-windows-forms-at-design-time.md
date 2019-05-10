---
title: 演练：在设计时在 Windows 窗体上排列 WPF 内容
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
ms.openlocfilehash: a8f690438136450cb12dbcf5e17ddfcca617457e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211447"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="38079-102">演练：在设计时排列 Windows 窗体上的 WPF 内容</span><span class="sxs-lookup"><span data-stu-id="38079-102">Walkthrough: Arrange WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="38079-103">本演练演示如何使用 Windows 窗体布局功能（例如锚定和对齐线）排列 Windows Presentation Foundation (WPF) 控件。</span><span class="sxs-lookup"><span data-stu-id="38079-103">This walkthrough shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>

<span data-ttu-id="38079-104">在本演练中，你将要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="38079-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="38079-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="38079-105">Create the project.</span></span>

- <span data-ttu-id="38079-106">创建 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="38079-106">Create the WPF control.</span></span>

- <span data-ttu-id="38079-107">在布局面板中承载 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="38079-107">Host WPF controls in a layout panel.</span></span>

- <span data-ttu-id="38079-108">使用对齐线对齐 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="38079-108">Use snaplines to align WPF controls.</span></span>

- <span data-ttu-id="38079-109">锚定和停靠 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="38079-109">Anchor and dock WPF controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="38079-110">系统必备</span><span class="sxs-lookup"><span data-stu-id="38079-110">Prerequisites</span></span>

<span data-ttu-id="38079-111">若要完成本演练，必须具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="38079-111">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="38079-112">创建项目</span><span class="sxs-lookup"><span data-stu-id="38079-112">Create the project</span></span>

<span data-ttu-id="38079-113">打开 Visual Studio 并创建新的 Windows 窗体应用程序项目在 Visual Basic 或 VisualC#名为`ArrangeElementHost`。</span><span class="sxs-lookup"><span data-stu-id="38079-113">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>

> [!NOTE]
> <span data-ttu-id="38079-114">承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="38079-114">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control"></a><span data-ttu-id="38079-115">创建 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="38079-115">Create the WPF control</span></span>

<span data-ttu-id="38079-116">将 WPF 控件添加到项目后，就可以在窗体上对其进行排列。</span><span class="sxs-lookup"><span data-stu-id="38079-116">After you add a WPF control to the project, you can arrange it on the form.</span></span>

1. <span data-ttu-id="38079-117">将新的 WPF <xref:System.Windows.Controls.UserControl> 添加到项目。</span><span class="sxs-lookup"><span data-stu-id="38079-117">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="38079-118">使用控件类型的默认名称，`UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="38079-118">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="38079-119">有关详细信息，请参见[演练：在设计时在 Windows 窗体上创建新的 WPF 内容](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="38079-119">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="38079-120">在设计视图中，请确保已选中 `UserControl1`。</span><span class="sxs-lookup"><span data-stu-id="38079-120">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="38079-121">有关详细信息，请参阅[如何：选择并在设计图面上移动元素](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="38079-121">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="38079-122">在中**属性**窗口中，设置的值<xref:System.Windows.FrameworkElement.Width%2A>并<xref:System.Windows.FrameworkElement.Height%2A>属性设置为`200`。</span><span class="sxs-lookup"><span data-stu-id="38079-122">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

4. <span data-ttu-id="38079-123">将 <xref:System.Windows.Controls.Control.Background%2A> 属性的值设置为 `Blue`。</span><span class="sxs-lookup"><span data-stu-id="38079-123">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>

5. <span data-ttu-id="38079-124">生成项目。</span><span class="sxs-lookup"><span data-stu-id="38079-124">Build the project.</span></span>

## <a name="hosting-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="38079-125">在布局面板中承载 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="38079-125">Hosting WPF Controls in a Layout Panel</span></span>
 <span data-ttu-id="38079-126">在布局面板中使用 WPF 控件与使用其他 Windows 窗体控件的方式可以相同。</span><span class="sxs-lookup"><span data-stu-id="38079-126">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>

#### <a name="to-host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="38079-127">若要在布局面板中承载 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="38079-127">To host WPF controls in a layout panel</span></span>

1. <span data-ttu-id="38079-128">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="38079-128">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="38079-129">在中**工具箱**，拖动<xref:System.Windows.Forms.TableLayoutPanel>拖到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="38079-129">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>

3. <span data-ttu-id="38079-130">上<xref:System.Windows.Forms.TableLayoutPanel>控件的智能标记面板中，选择**移除最后一行**。</span><span class="sxs-lookup"><span data-stu-id="38079-130">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>

4. <span data-ttu-id="38079-131">将 <xref:System.Windows.Forms.TableLayoutPanel> 控件的大小调整为更大的宽度和高度。</span><span class="sxs-lookup"><span data-stu-id="38079-131">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>

5. <span data-ttu-id="38079-132">在中**工具箱**，双击`UserControl1`若要创建的实例`UserControl1`中的第一个单元<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="38079-132">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

     <span data-ttu-id="38079-133">`UserControl1` 的实例承载在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="38079-133">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

6. <span data-ttu-id="38079-134">在中**工具箱**，双击`UserControl1`的第二个单元格中创建另一个实例<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="38079-134">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="38079-135">在中**文档大纲**窗口中，选择`tableLayoutPanel1`。</span><span class="sxs-lookup"><span data-stu-id="38079-135">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span> <span data-ttu-id="38079-136">有关详细信息，请参阅[文档大纲窗口](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/46xf4h0w(v=vs.100)#using-the-document-outline-window-for-silverlight-and-wpf)。</span><span class="sxs-lookup"><span data-stu-id="38079-136">For more information, see [Document Outline Window](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/46xf4h0w(v=vs.100)#using-the-document-outline-window-for-silverlight-and-wpf).</span></span>

8. <span data-ttu-id="38079-137">在中**属性**窗口中，设置的值<xref:System.Windows.Forms.Control.Padding%2A>属性设置为`10, 10, 10, 10`。</span><span class="sxs-lookup"><span data-stu-id="38079-137">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to `10, 10, 10, 10`.</span></span>

     <span data-ttu-id="38079-138">调整两个 <xref:System.Windows.Forms.Integration.ElementHost> 控件的大小以适应新的布局。</span><span class="sxs-lookup"><span data-stu-id="38079-138">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>

## <a name="using-snaplines-to-align-wpf-controls"></a><span data-ttu-id="38079-139">使用对齐线对齐 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="38079-139">Using Snaplines to Align WPF Controls</span></span>
 <span data-ttu-id="38079-140">使用对齐线能够轻松对齐窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="38079-140">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="38079-141">还可以使用对齐线对齐 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="38079-141">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="38079-142">有关详细信息，请参见[演练：在 Windows 上排列控件窗体使用对齐线](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)。</span><span class="sxs-lookup"><span data-stu-id="38079-142">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

#### <a name="to-use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="38079-143">若要使用对齐线对齐 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="38079-143">To use snaplines to align WPF controls</span></span>

1. <span data-ttu-id="38079-144">从**工具箱**，一个实例的拖放`UserControl1`拖到窗体并将它放在下方的空间<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="38079-144">From the **Toolbox**, drag an instance of `UserControl1` onto the form and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

     <span data-ttu-id="38079-145">`UserControl1` 的实例承载在名为 `elementHost3` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="38079-145">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>

2. <span data-ttu-id="38079-146">使用对齐线，将 `elementHost3` 的左边缘与 <xref:System.Windows.Forms.TableLayoutPanel> 控件的左边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="38079-146">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="38079-147">使用对齐线，将 `elementHost3` 按与 <xref:System.Windows.Forms.TableLayoutPanel> 控件相同的宽度排列。</span><span class="sxs-lookup"><span data-stu-id="38079-147">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="38079-148">朝着 <xref:System.Windows.Forms.TableLayoutPanel> 控件移动 `elementHost3`，直到控件间显示居中对齐线。</span><span class="sxs-lookup"><span data-stu-id="38079-148">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>

5. <span data-ttu-id="38079-149">在中**属性**窗口中，设置到边距属性的值`20, 20, 20, 20`。</span><span class="sxs-lookup"><span data-stu-id="38079-149">In the **Properties** window, set the value of the Margin property to `20, 20, 20, 20`.</span></span>

6. <span data-ttu-id="38079-150">向远离 <xref:System.Windows.Forms.TableLayoutPanel> 控件的方向移动 `elementHost3`，直到再次显示居中对齐线。</span><span class="sxs-lookup"><span data-stu-id="38079-150">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="38079-151">现在，居中对齐线指示边距为 20。</span><span class="sxs-lookup"><span data-stu-id="38079-151">The center snapline now indicates a margin of 20.</span></span>

7. <span data-ttu-id="38079-152">向右移动 `elementHost3`，直到其左边缘与 `elementHost1` 的左边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="38079-152">Move `elementHost3` to the right, until its left edge aligns with the left edge of `elementHost1`.</span></span>

8. <span data-ttu-id="38079-153">更改 `elementHost3` 的宽度，直到其右边缘与 `elementHost2` 的右边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="38079-153">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>

## <a name="anchoring-and-docking-wpf-controls"></a><span data-ttu-id="38079-154">锚定和停靠 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="38079-154">Anchoring and Docking WPF Controls</span></span>
 <span data-ttu-id="38079-155">窗体上承载的 WPF 控件具有与其他 Windows 窗体控件相同的锚定和停靠行为。</span><span class="sxs-lookup"><span data-stu-id="38079-155">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>

#### <a name="to-anchor-and-dock-wpf-controls"></a><span data-ttu-id="38079-156">若要锚定和停靠 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="38079-156">To anchor and dock WPF controls</span></span>

1. <span data-ttu-id="38079-157">选择 `elementHost1`。</span><span class="sxs-lookup"><span data-stu-id="38079-157">Select `elementHost1`.</span></span>

2. <span data-ttu-id="38079-158">在中**属性**窗口中，将<xref:System.Windows.Forms.Control.Anchor%2A>属性设置为**顶部、 底部、 Left、 Right**。</span><span class="sxs-lookup"><span data-stu-id="38079-158">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>

3. <span data-ttu-id="38079-159">将 <xref:System.Windows.Forms.TableLayoutPanel> 控件的大小调整为更大。</span><span class="sxs-lookup"><span data-stu-id="38079-159">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>

     <span data-ttu-id="38079-160">调整 `elementHost1` 控件大小，以填充单元格。</span><span class="sxs-lookup"><span data-stu-id="38079-160">The `elementHost1` control resizes to fill the cell.</span></span>

4. <span data-ttu-id="38079-161">选择 `elementHost2`。</span><span class="sxs-lookup"><span data-stu-id="38079-161">Select `elementHost2`.</span></span>

5. <span data-ttu-id="38079-162">在中**属性**窗口中，设置的值<xref:System.Windows.Forms.Control.Dock%2A>属性设置为<xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="38079-162">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

     <span data-ttu-id="38079-163">调整 `elementHost2` 控件大小，以填充单元格。</span><span class="sxs-lookup"><span data-stu-id="38079-163">The `elementHost2` control resizes to fill the cell.</span></span>

6. <span data-ttu-id="38079-164">选择 <xref:System.Windows.Forms.TableLayoutPanel> 控件。</span><span class="sxs-lookup"><span data-stu-id="38079-164">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="38079-165">将其 <xref:System.Windows.Forms.Control.Dock%2A> 属性的值设置为 <xref:System.Windows.Forms.DockStyle.Top>。</span><span class="sxs-lookup"><span data-stu-id="38079-165">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>

8. <span data-ttu-id="38079-166">选择 `elementHost3`。</span><span class="sxs-lookup"><span data-stu-id="38079-166">Select `elementHost3`.</span></span>

9. <span data-ttu-id="38079-167">将其 <xref:System.Windows.Forms.Control.Dock%2A> 属性的值设置为 <xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="38079-167">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

     <span data-ttu-id="38079-168">调整 `elementHost3` 控件大小，以填充窗体上的剩余空间。</span><span class="sxs-lookup"><span data-stu-id="38079-168">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>

10. <span data-ttu-id="38079-169">调整窗体大小。</span><span class="sxs-lookup"><span data-stu-id="38079-169">Resize the form.</span></span>

     <span data-ttu-id="38079-170">所有三个 <xref:System.Windows.Forms.Integration.ElementHost> 控件将相应地调整大小。</span><span class="sxs-lookup"><span data-stu-id="38079-170">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>

     <span data-ttu-id="38079-171">有关详细信息，请参阅[如何：锚定和停靠在 TableLayoutPanel 控件中的子控件](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)。</span><span class="sxs-lookup"><span data-stu-id="38079-171">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="38079-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="38079-172">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="38079-173">如何：锚定和停靠在 TableLayoutPanel 控件中的子控件</span><span class="sxs-lookup"><span data-stu-id="38079-173">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="38079-174">如何：将控件与窗体边缘对齐在设计时</span><span class="sxs-lookup"><span data-stu-id="38079-174">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [<span data-ttu-id="38079-175">演练：使用对齐线的 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="38079-175">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="38079-176">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="38079-176">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="38079-177">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="38079-177">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="38079-178">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="38079-178">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
