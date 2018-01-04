---
title: "演练：设计时在 Windows 窗体上排列 WPF 内容"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c222e6f43bd595d264caeca2d9f79f7845f7f99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-arranging-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="6456e-102">演练：设计时在 Windows 窗体上排列 WPF 内容</span><span class="sxs-lookup"><span data-stu-id="6456e-102">Walkthrough: Arranging WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="6456e-103">本演练演示如何使用 Windows 窗体布局功能（例如锚定和对齐线）排列 Windows Presentation Foundation (WPF) 控件。</span><span class="sxs-lookup"><span data-stu-id="6456e-103">This walkthrough shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>  
  
 <span data-ttu-id="6456e-104">在本演练中，你将要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="6456e-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="6456e-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="6456e-105">Create the project.</span></span>  
  
-   <span data-ttu-id="6456e-106">创建 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="6456e-106">Create the WPF control.</span></span>  
  
-   <span data-ttu-id="6456e-107">在布局面板中承载 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="6456e-107">Host WPF controls in a layout panel.</span></span>  
  
-   <span data-ttu-id="6456e-108">使用对齐线对齐 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="6456e-108">Use snaplines to align WPF controls.</span></span>  
  
-   <span data-ttu-id="6456e-109">锚定和停靠 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="6456e-109">Anchor and dock WPF controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6456e-110">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="6456e-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6456e-111">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="6456e-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6456e-112">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="6456e-112">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6456e-113">系统必备</span><span class="sxs-lookup"><span data-stu-id="6456e-113">Prerequisites</span></span>  
 <span data-ttu-id="6456e-114">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="6456e-114">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="6456e-115">。</span><span class="sxs-lookup"><span data-stu-id="6456e-115">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="6456e-116">创建项目</span><span class="sxs-lookup"><span data-stu-id="6456e-116">Creating the Project</span></span>  
 <span data-ttu-id="6456e-117">第一步是创建 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="6456e-117">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6456e-118">承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="6456e-118">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="6456e-119">要创建项目</span><span class="sxs-lookup"><span data-stu-id="6456e-119">To create the project</span></span>  
  
-   <span data-ttu-id="6456e-120">创建新的 Windows 窗体应用程序项目中 Visual Basic 或 Visual C# 名为`ArrangeElementHost`。</span><span class="sxs-lookup"><span data-stu-id="6456e-120">Create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>  
  
## <a name="creating-the-wpf-control"></a><span data-ttu-id="6456e-121">创建 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="6456e-121">Creating the WPF Control</span></span>  
 <span data-ttu-id="6456e-122">将 WPF 控件添加到项目后，就可以在窗体上对其进行排列。</span><span class="sxs-lookup"><span data-stu-id="6456e-122">After you add a WPF control to the project, you can arrange it on the form.</span></span>  
  
#### <a name="to-create-wpf-controls"></a><span data-ttu-id="6456e-123">创建 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="6456e-123">To create WPF controls</span></span>  
  
1.  <span data-ttu-id="6456e-124">将新的 WPF <xref:System.Windows.Controls.UserControl> 添加到项目。</span><span class="sxs-lookup"><span data-stu-id="6456e-124">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="6456e-125">使用控件类型的默认名称，`UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="6456e-125">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="6456e-126">有关详细信息，请参阅[演练： 创建新 WPF 内容在设计时的 Windows 窗体上](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="6456e-126">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="6456e-127">在设计视图中，请确保已选中 `UserControl1`。</span><span class="sxs-lookup"><span data-stu-id="6456e-127">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="6456e-128">有关详细信息，请参阅[如何： 选择和设计图面上移动元素](http://msdn.microsoft.com/en-us/54cb70b6-b35b-46e4-a0cc-65189399c474)。</span><span class="sxs-lookup"><span data-stu-id="6456e-128">For more information, see [How to: Select and Move Elements on the Design Surface](http://msdn.microsoft.com/en-us/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="6456e-129">在**属性**窗口中，设置的值<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性设置为`200`。</span><span class="sxs-lookup"><span data-stu-id="6456e-129">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="6456e-130">将 <xref:System.Windows.Controls.Control.Background%2A> 属性的值设置为 `Blue`。</span><span class="sxs-lookup"><span data-stu-id="6456e-130">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
5.  <span data-ttu-id="6456e-131">生成项目。</span><span class="sxs-lookup"><span data-stu-id="6456e-131">Build the project.</span></span>  
  
## <a name="hosting-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="6456e-132">在布局面板中承载 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="6456e-132">Hosting WPF Controls in a Layout Panel</span></span>  
 <span data-ttu-id="6456e-133">在布局面板中使用 WPF 控件与使用其他 Windows 窗体控件的方式可以相同。</span><span class="sxs-lookup"><span data-stu-id="6456e-133">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>  
  
#### <a name="to-host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="6456e-134">若要在布局面板中承载 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="6456e-134">To host WPF controls in a layout panel</span></span>  
  
1.  <span data-ttu-id="6456e-135">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="6456e-135">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="6456e-136">在**工具箱**，拖动<xref:System.Windows.Forms.TableLayoutPanel>拖到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="6456e-136">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>  
  
3.  <span data-ttu-id="6456e-137">上<xref:System.Windows.Forms.TableLayoutPanel>控件的智能标记面板中，选择**移除最后一行**。</span><span class="sxs-lookup"><span data-stu-id="6456e-137">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>  
  
4.  <span data-ttu-id="6456e-138">将 <xref:System.Windows.Forms.TableLayoutPanel> 控件的大小调整为更大的宽度和高度。</span><span class="sxs-lookup"><span data-stu-id="6456e-138">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>  
  
5.  <span data-ttu-id="6456e-139">在**工具箱**，双击`UserControl1`若要创建的实例`UserControl1`中的第一个单元格<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="6456e-139">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
     <span data-ttu-id="6456e-140">`UserControl1` 的实例承载在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="6456e-140">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
6.  <span data-ttu-id="6456e-141">在**工具箱**，双击`UserControl1`的第二个单元格中创建另一个实例<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="6456e-141">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
7.  <span data-ttu-id="6456e-142">在**文档大纲**窗口中，选择`tableLayoutPanel1`。</span><span class="sxs-lookup"><span data-stu-id="6456e-142">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span> <span data-ttu-id="6456e-143">有关详细信息，请参阅[文档大纲窗口](http://msdn.microsoft.com/en-us/9054f2bc-f6f8-4242-9fe0-be71089b12f8)。</span><span class="sxs-lookup"><span data-stu-id="6456e-143">For more information, see [Document Outline Window](http://msdn.microsoft.com/en-us/9054f2bc-f6f8-4242-9fe0-be71089b12f8).</span></span>  
  
8.  <span data-ttu-id="6456e-144">在**属性**窗口中，设置的值<xref:System.Windows.Forms.Control.Padding%2A>属性`10, 10, 10, 10`。</span><span class="sxs-lookup"><span data-stu-id="6456e-144">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to `10, 10, 10, 10`.</span></span>  
  
     <span data-ttu-id="6456e-145">调整两个 <xref:System.Windows.Forms.Integration.ElementHost> 控件的大小以适应新的布局。</span><span class="sxs-lookup"><span data-stu-id="6456e-145">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>  
  
## <a name="using-snaplines-to-align-wpf-controls"></a><span data-ttu-id="6456e-146">使用对齐线对齐 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="6456e-146">Using Snaplines to Align WPF Controls</span></span>  
 <span data-ttu-id="6456e-147">使用对齐线能够轻松对齐窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="6456e-147">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="6456e-148">还可以使用对齐线对齐 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="6456e-148">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="6456e-149">有关详细信息，请参阅[演练： 在 Windows 窗体使用对齐线上排列控件](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)。</span><span class="sxs-lookup"><span data-stu-id="6456e-149">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
#### <a name="to-use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="6456e-150">若要使用对齐线对齐 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="6456e-150">To use snaplines to align WPF controls</span></span>  
  
1.  <span data-ttu-id="6456e-151">从**工具箱**的一个实例拖`UserControl1`拖到窗体并将其放在下方的空间<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="6456e-151">From the **Toolbox**, drag an instance of `UserControl1` onto the form and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
     <span data-ttu-id="6456e-152">`UserControl1` 的实例承载在名为 `elementHost3` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="6456e-152">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>  
  
2.  <span data-ttu-id="6456e-153">使用对齐线，将 `elementHost3` 的左边缘与 <xref:System.Windows.Forms.TableLayoutPanel> 控件的左边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="6456e-153">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
3.  <span data-ttu-id="6456e-154">使用对齐线，将 `elementHost3` 按与 <xref:System.Windows.Forms.TableLayoutPanel> 控件相同的宽度排列。</span><span class="sxs-lookup"><span data-stu-id="6456e-154">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
4.  <span data-ttu-id="6456e-155">朝着 <xref:System.Windows.Forms.TableLayoutPanel> 控件移动 `elementHost3`，直到控件间显示居中对齐线。</span><span class="sxs-lookup"><span data-stu-id="6456e-155">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>  
  
5.  <span data-ttu-id="6456e-156">在**属性**窗口中，设置为边距属性的值`20, 20, 20, 20`。</span><span class="sxs-lookup"><span data-stu-id="6456e-156">In the **Properties** window, set the value of the Margin property to `20, 20, 20, 20`.</span></span>  
  
6.  <span data-ttu-id="6456e-157">向远离 <xref:System.Windows.Forms.TableLayoutPanel> 控件的方向移动 `elementHost3`，直到再次显示居中对齐线。</span><span class="sxs-lookup"><span data-stu-id="6456e-157">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="6456e-158">现在，居中对齐线指示边距为 20。</span><span class="sxs-lookup"><span data-stu-id="6456e-158">The center snapline now indicates a margin of 20.</span></span>  
  
7.  <span data-ttu-id="6456e-159">向右移动 `elementHost3`，直到其左边缘与 `elementHost1` 的左边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="6456e-159">Move `elementHost3` to the right, until its left edge aligns with the left edge of `elementHost1`.</span></span>  
  
8.  <span data-ttu-id="6456e-160">更改 `elementHost3` 的宽度，直到其右边缘与 `elementHost2` 的右边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="6456e-160">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>  
  
## <a name="anchoring-and-docking-wpf-controls"></a><span data-ttu-id="6456e-161">锚定和停靠 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="6456e-161">Anchoring and Docking WPF Controls</span></span>  
 <span data-ttu-id="6456e-162">窗体上承载的 WPF 控件具有与其他 Windows 窗体控件相同的锚定和停靠行为。</span><span class="sxs-lookup"><span data-stu-id="6456e-162">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>  
  
#### <a name="to-anchor-and-dock-wpf-controls"></a><span data-ttu-id="6456e-163">若要锚定和停靠 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="6456e-163">To anchor and dock WPF controls</span></span>  
  
1.  <span data-ttu-id="6456e-164">选择 `elementHost1`。</span><span class="sxs-lookup"><span data-stu-id="6456e-164">Select `elementHost1`.</span></span>  
  
2.  <span data-ttu-id="6456e-165">在**属性**窗口中，设置<xref:System.Windows.Forms.Control.Anchor%2A>属性**顶部、 底部、 Left、 Right**。</span><span class="sxs-lookup"><span data-stu-id="6456e-165">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>  
  
3.  <span data-ttu-id="6456e-166">将 <xref:System.Windows.Forms.TableLayoutPanel> 控件的大小调整为更大。</span><span class="sxs-lookup"><span data-stu-id="6456e-166">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>  
  
     <span data-ttu-id="6456e-167">调整 `elementHost1` 控件大小，以填充单元格。</span><span class="sxs-lookup"><span data-stu-id="6456e-167">The `elementHost1` control resizes to fill the cell.</span></span>  
  
4.  <span data-ttu-id="6456e-168">选择 `elementHost2`。</span><span class="sxs-lookup"><span data-stu-id="6456e-168">Select `elementHost2`.</span></span>  
  
5.  <span data-ttu-id="6456e-169">在**属性**窗口中，设置的值<xref:System.Windows.Forms.Control.Dock%2A>属性<xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="6456e-169">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
     <span data-ttu-id="6456e-170">调整 `elementHost2` 控件大小，以填充单元格。</span><span class="sxs-lookup"><span data-stu-id="6456e-170">The `elementHost2` control resizes to fill the cell.</span></span>  
  
6.  <span data-ttu-id="6456e-171">选择 <xref:System.Windows.Forms.TableLayoutPanel> 控件。</span><span class="sxs-lookup"><span data-stu-id="6456e-171">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
7.  <span data-ttu-id="6456e-172">将其 <xref:System.Windows.Forms.Control.Dock%2A> 属性的值设置为 <xref:System.Windows.Forms.DockStyle.Top>。</span><span class="sxs-lookup"><span data-stu-id="6456e-172">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>  
  
8.  <span data-ttu-id="6456e-173">选择 `elementHost3`。</span><span class="sxs-lookup"><span data-stu-id="6456e-173">Select `elementHost3`.</span></span>  
  
9. <span data-ttu-id="6456e-174">将其 <xref:System.Windows.Forms.Control.Dock%2A> 属性的值设置为 <xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="6456e-174">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
     <span data-ttu-id="6456e-175">调整 `elementHost3` 控件大小，以填充窗体上的剩余空间。</span><span class="sxs-lookup"><span data-stu-id="6456e-175">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>  
  
10. <span data-ttu-id="6456e-176">调整窗体大小。</span><span class="sxs-lookup"><span data-stu-id="6456e-176">Resize the form.</span></span>  
  
     <span data-ttu-id="6456e-177">所有三个 <xref:System.Windows.Forms.Integration.ElementHost> 控件将相应地调整大小。</span><span class="sxs-lookup"><span data-stu-id="6456e-177">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>  
  
     <span data-ttu-id="6456e-178">有关详细信息，请参阅[如何： 定位点和停靠子控件，在 TableLayoutPanel 控件中](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)。</span><span class="sxs-lookup"><span data-stu-id="6456e-178">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6456e-179">请参阅</span><span class="sxs-lookup"><span data-stu-id="6456e-179">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="6456e-180">如何：在 TableLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="6456e-180">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="6456e-181">如何：设计时将控件与窗体边缘对齐</span><span class="sxs-lookup"><span data-stu-id="6456e-181">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [<span data-ttu-id="6456e-182">演练：使用对齐线在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="6456e-182">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="6456e-183">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="6456e-183">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="6456e-184">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="6456e-184">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="6456e-185">WPF 设计器</span><span class="sxs-lookup"><span data-stu-id="6456e-185">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)
