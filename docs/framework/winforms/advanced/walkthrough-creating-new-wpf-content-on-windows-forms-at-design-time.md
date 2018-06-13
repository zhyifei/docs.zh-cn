---
title: 演练：设计时在 Windows 窗体上创建新的 WPF 内容
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: 1ea0160530fea0f35c6d4746dc4bbca9439bc462
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529004"
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="40eb1-102">演练：设计时在 Windows 窗体上创建新的 WPF 内容</span><span class="sxs-lookup"><span data-stu-id="40eb1-102">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="40eb1-103">本主题显示如何创建 Windows Presentation Foundation (WPF) 控件，以便在基于 Windows 窗体的应用程序中使用。</span><span class="sxs-lookup"><span data-stu-id="40eb1-103">This topic shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>  
  
 <span data-ttu-id="40eb1-104">在本演练中，你将要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="40eb1-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="40eb1-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="40eb1-105">Create the project.</span></span>  
  
-   <span data-ttu-id="40eb1-106">创建一个新的 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="40eb1-106">Create a new WPF control.</span></span>  
  
-   <span data-ttu-id="40eb1-107">将新的 WPF 控件添加到 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="40eb1-107">Add the new WPF control to a Windows Form.</span></span> <span data-ttu-id="40eb1-108">WPF 控件承载在 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="40eb1-108">The WPF control is hosted in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40eb1-109">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="40eb1-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="40eb1-110">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="40eb1-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="40eb1-111">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="40eb1-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="40eb1-112">系统必备</span><span class="sxs-lookup"><span data-stu-id="40eb1-112">Prerequisites</span></span>  
 <span data-ttu-id="40eb1-113">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="40eb1-113">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="40eb1-114">。</span><span class="sxs-lookup"><span data-stu-id="40eb1-114">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="40eb1-115">创建项目</span><span class="sxs-lookup"><span data-stu-id="40eb1-115">Creating the Project</span></span>  
 <span data-ttu-id="40eb1-116">第一步是创建 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="40eb1-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40eb1-117">承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="40eb1-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="40eb1-118">要创建项目</span><span class="sxs-lookup"><span data-stu-id="40eb1-118">To create the project</span></span>  
  
-   <span data-ttu-id="40eb1-119">创建新的 Windows 窗体应用程序项目中 Visual Basic 或 Visual C# 名为`HostingWpf`。</span><span class="sxs-lookup"><span data-stu-id="40eb1-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `HostingWpf`.</span></span>  
  
## <a name="creating-a-new-wpf-control"></a><span data-ttu-id="40eb1-120">创建新的 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="40eb1-120">Creating a New WPF Control</span></span>  
 <span data-ttu-id="40eb1-121">创建新的 WPF 控件并将其添加到你的项目中，这与将任何其他项添加到你的项目中一样容易。</span><span class="sxs-lookup"><span data-stu-id="40eb1-121">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="40eb1-122">Windows 窗体设计器使用一种名为控件的特定*复合控件*，或*用户控件*。</span><span class="sxs-lookup"><span data-stu-id="40eb1-122">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="40eb1-123">有关 WPF 用户控件的详细信息，请参阅 <xref:System.Windows.Controls.UserControl>。</span><span class="sxs-lookup"><span data-stu-id="40eb1-123">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40eb1-124">WPF 的 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> 类型不同于 Windows 窗体提供的用户控件类型（也称为 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>）。</span><span class="sxs-lookup"><span data-stu-id="40eb1-124">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>  
  
#### <a name="to-create-a-new-wpf-control"></a><span data-ttu-id="40eb1-125">创建新的 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="40eb1-125">To create a new WPF control</span></span>  
  
1.  <span data-ttu-id="40eb1-126">在**解决方案资源管理器**，添加新**WPF 用户控件库**到解决方案的项目。</span><span class="sxs-lookup"><span data-stu-id="40eb1-126">In **Solution Explorer**, add a new **WPF User Control Library** project to the solution.</span></span> <span data-ttu-id="40eb1-127">使用控件库默认名称 `WpfControlLibrary1`。</span><span class="sxs-lookup"><span data-stu-id="40eb1-127">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="40eb1-128">默认控件名称是 `UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="40eb1-128">The default control name is `UserControl1.xaml`.</span></span>  
  
     <span data-ttu-id="40eb1-129">添加新控件将产生以下影响。</span><span class="sxs-lookup"><span data-stu-id="40eb1-129">Adding the new control has the following effects.</span></span>  
  
    -   <span data-ttu-id="40eb1-130">添加文件 UserControl1.xaml。</span><span class="sxs-lookup"><span data-stu-id="40eb1-130">File UserControl1.xaml is added.</span></span>  
  
    -   <span data-ttu-id="40eb1-131">添加文件 UserControl1.xaml.cs 或 UserControl1.xaml.vb。</span><span class="sxs-lookup"><span data-stu-id="40eb1-131">Either file UserControl1.xaml.cs or UserControl1.xaml.vb is added.</span></span> <span data-ttu-id="40eb1-132">此文件包含事件处理程序和其他实现的代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="40eb1-132">This file contains the code-behind for event handlers and other implementation.</span></span>  
  
    -   <span data-ttu-id="40eb1-133">添加对 WPF 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="40eb1-133">References to WPF assemblies are added.</span></span>  
  
    -   <span data-ttu-id="40eb1-134">文件 UserControl1.xaml 在 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] 中打开。</span><span class="sxs-lookup"><span data-stu-id="40eb1-134">File UserControl1.xaml opens in the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="40eb1-135">在设计视图中，请确保已选中 `UserControl1`。</span><span class="sxs-lookup"><span data-stu-id="40eb1-135">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="40eb1-136">有关详细信息，请参阅[如何： 选择和设计图面上移动元素](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474)。</span><span class="sxs-lookup"><span data-stu-id="40eb1-136">For more information, see [How to: Select and Move Elements on the Design Surface](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="40eb1-137">在**属性**窗口中，设置的值<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性设置为`200`。</span><span class="sxs-lookup"><span data-stu-id="40eb1-137">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="40eb1-138">从**工具箱**，拖动<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>控件拖到设计图面。</span><span class="sxs-lookup"><span data-stu-id="40eb1-138">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>  
  
5.  <span data-ttu-id="40eb1-139">在**属性**窗口中，设置的值<xref:System.Windows.Controls.TextBox.Text%2A>属性**承载的内容**。</span><span class="sxs-lookup"><span data-stu-id="40eb1-139">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="40eb1-140">一般情况下，你应承载更复杂的 WPF 内容。</span><span class="sxs-lookup"><span data-stu-id="40eb1-140">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="40eb1-141">此处，<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 控件仅为了便于说明。</span><span class="sxs-lookup"><span data-stu-id="40eb1-141">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>  
  
6.  <span data-ttu-id="40eb1-142">生成项目。</span><span class="sxs-lookup"><span data-stu-id="40eb1-142">Build the project.</span></span>  
  
## <a name="adding-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="40eb1-143">将 WPF 控件添加到 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="40eb1-143">Adding a WPF Control to a Windows Form</span></span>  
 <span data-ttu-id="40eb1-144">新的 WPF 控件可供在窗体上使用。</span><span class="sxs-lookup"><span data-stu-id="40eb1-144">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="40eb1-145">Windows 窗体使用 <xref:System.Windows.Forms.Integration.ElementHost> 控件承载 WPF 内容</span><span class="sxs-lookup"><span data-stu-id="40eb1-145">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content</span></span>  
  
#### <a name="to-add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="40eb1-146">将 WPF 控件添加到 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="40eb1-146">To add a WPF control to a Windows Form</span></span>  
  
1.  <span data-ttu-id="40eb1-147">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="40eb1-147">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="40eb1-148">在**工具箱**，找到标记为选项卡**WPFUserControlLibrary WPF 用户控件**。</span><span class="sxs-lookup"><span data-stu-id="40eb1-148">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>  
  
3.  <span data-ttu-id="40eb1-149">将 `UserControl1` 的实例拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="40eb1-149">Drag an instance of `UserControl1` onto the form.</span></span>  
  
    -   <span data-ttu-id="40eb1-150">在窗体上自动创建 <xref:System.Windows.Forms.Integration.ElementHost> 控件以承载 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="40eb1-150">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>  
  
    -   <span data-ttu-id="40eb1-151"><xref:System.Windows.Forms.Integration.ElementHost>控件被命名为`elementHost1`并在**属性**窗口中，你可以看到其<xref:System.Windows.Forms.Integration.ElementHost.Child%2A>属性设置为**UserControl1**。</span><span class="sxs-lookup"><span data-stu-id="40eb1-151">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>  
  
    -   <span data-ttu-id="40eb1-152">将对 WPF 程序集的引用添加到项目。</span><span class="sxs-lookup"><span data-stu-id="40eb1-152">References to WPF assemblies are added to the project.</span></span>  
  
    -   <span data-ttu-id="40eb1-153">`elementHost1` 控件具有显示可用承载选项的智能标记面板。</span><span class="sxs-lookup"><span data-stu-id="40eb1-153">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>  
  
4.  <span data-ttu-id="40eb1-154">在**ElementHost 任务**智能标记面板中，选择**在父容器中的停靠**。</span><span class="sxs-lookup"><span data-stu-id="40eb1-154">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>  
  
5.  <span data-ttu-id="40eb1-155">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="40eb1-155">Press F5 to build and run the application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="40eb1-156">后续步骤</span><span class="sxs-lookup"><span data-stu-id="40eb1-156">Next Steps</span></span>  
 <span data-ttu-id="40eb1-157">Windows 窗体和 WPF 是不同的技术，但它们设计为可以密切地互操作。</span><span class="sxs-lookup"><span data-stu-id="40eb1-157">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="40eb1-158">若要在你的应用程序中提供更丰富的外观和行为，请尝试以下操作。</span><span class="sxs-lookup"><span data-stu-id="40eb1-158">To provide richer appearance and behavior in your applications, try the following.</span></span>  
  
-   <span data-ttu-id="40eb1-159">在 WPF 页中承载 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="40eb1-159">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="40eb1-160">有关详细信息，请参阅[演练： 承载 Windows 窗体控件在 WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="40eb1-160">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>  
  
-   <span data-ttu-id="40eb1-161">将 Windows 窗体的视觉样式应用于你的 WPF 内容。</span><span class="sxs-lookup"><span data-stu-id="40eb1-161">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="40eb1-162">有关详细信息，请参阅[如何：在混合应用程序中启用视觉样式](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)。</span><span class="sxs-lookup"><span data-stu-id="40eb1-162">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>  
  
-   <span data-ttu-id="40eb1-163">更改 WPF 内容的样式。</span><span class="sxs-lookup"><span data-stu-id="40eb1-163">Change the style of your WPF content.</span></span> <span data-ttu-id="40eb1-164">有关详细信息，请参阅[演练： 样式 WPF 内容](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)。</span><span class="sxs-lookup"><span data-stu-id="40eb1-164">For more information, see [Walkthrough: Styling WPF Content](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40eb1-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="40eb1-165">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="40eb1-166">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="40eb1-166">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="40eb1-167">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="40eb1-167">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="40eb1-168">WPF 设计器</span><span class="sxs-lookup"><span data-stu-id="40eb1-168">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
