---
title: 演练：设计时在 Windows 窗体上创建新的 WPF 内容
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: dc72b86a69d44ad282e30b000313b73211cad09c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43671734"
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="377b5-102">演练：设计时在 Windows 窗体上创建新的 WPF 内容</span><span class="sxs-lookup"><span data-stu-id="377b5-102">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>

<span data-ttu-id="377b5-103">本主题显示如何创建 Windows Presentation Foundation (WPF) 控件，以便在基于 Windows 窗体的应用程序中使用。</span><span class="sxs-lookup"><span data-stu-id="377b5-103">This topic shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

<span data-ttu-id="377b5-104">在本演练中，你将要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="377b5-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="377b5-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="377b5-105">Create the project.</span></span>

- <span data-ttu-id="377b5-106">创建一个新的 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="377b5-106">Create a new WPF control.</span></span>

- <span data-ttu-id="377b5-107">将新的 WPF 控件添加到 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="377b5-107">Add the new WPF control to a Windows Form.</span></span> <span data-ttu-id="377b5-108">WPF 控件承载在 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="377b5-108">The WPF control is hosted in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="377b5-109">系统必备</span><span class="sxs-lookup"><span data-stu-id="377b5-109">Prerequisites</span></span>

<span data-ttu-id="377b5-110">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="377b5-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="377b5-111">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="377b5-111">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="377b5-112">创建项目</span><span class="sxs-lookup"><span data-stu-id="377b5-112">Creating the Project</span></span>

<span data-ttu-id="377b5-113">第一步是创建 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="377b5-113">The first step is to create the Windows Forms project.</span></span> <span data-ttu-id="377b5-114">打开 Visual Studio 并创建一个新**Windows 窗体应用 (.NET Framework)** 项目在 Visual Basic 或 Visual C# 名为`HostingWpf`。</span><span class="sxs-lookup"><span data-stu-id="377b5-114">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="377b5-115">承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="377b5-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="creating-a-new-wpf-control"></a><span data-ttu-id="377b5-116">创建新的 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="377b5-116">Creating a New WPF Control</span></span>

<span data-ttu-id="377b5-117">创建新的 WPF 控件并将其添加到你的项目中，这与将任何其他项添加到你的项目中一样容易。</span><span class="sxs-lookup"><span data-stu-id="377b5-117">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="377b5-118">Windows 窗体设计器适用于特定类型的名为控件*复合控件*，或*用户控件*。</span><span class="sxs-lookup"><span data-stu-id="377b5-118">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="377b5-119">有关 WPF 用户控件的详细信息，请参阅 <xref:System.Windows.Controls.UserControl>。</span><span class="sxs-lookup"><span data-stu-id="377b5-119">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="377b5-120">WPF 的 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> 类型不同于 Windows 窗体提供的用户控件类型（也称为 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>）。</span><span class="sxs-lookup"><span data-stu-id="377b5-120">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

### <a name="to-create-a-new-wpf-control"></a><span data-ttu-id="377b5-121">创建新的 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="377b5-121">To create a new WPF control</span></span>

1. <span data-ttu-id="377b5-122">在中**解决方案资源管理器**，添加一个新**WPF 用户控件库 (.NET Framework)** 到解决方案。</span><span class="sxs-lookup"><span data-stu-id="377b5-122">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="377b5-123">使用控件库默认名称 `WpfControlLibrary1`。</span><span class="sxs-lookup"><span data-stu-id="377b5-123">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="377b5-124">默认控件名称是 `UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="377b5-124">The default control name is `UserControl1.xaml`.</span></span>

     <span data-ttu-id="377b5-125">添加新控件将产生以下影响：</span><span class="sxs-lookup"><span data-stu-id="377b5-125">Adding the new control has the following effects:</span></span>

    - <span data-ttu-id="377b5-126">添加文件 UserControl1.xaml。</span><span class="sxs-lookup"><span data-stu-id="377b5-126">File UserControl1.xaml is added.</span></span>

    - <span data-ttu-id="377b5-127">添加文件 UserControl1.xaml.cs 或 UserControl1.xaml.vb。</span><span class="sxs-lookup"><span data-stu-id="377b5-127">Either file UserControl1.xaml.cs or UserControl1.xaml.vb is added.</span></span> <span data-ttu-id="377b5-128">此文件包含事件处理程序和其他实现的代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="377b5-128">This file contains the code-behind for event handlers and other implementation.</span></span>

    - <span data-ttu-id="377b5-129">添加对 WPF 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="377b5-129">References to WPF assemblies are added.</span></span>

    - <span data-ttu-id="377b5-130">文件 UserControl1.xaml 在 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] 中打开。</span><span class="sxs-lookup"><span data-stu-id="377b5-130">File UserControl1.xaml opens in the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span></span>

2. <span data-ttu-id="377b5-131">在设计视图中，请确保已选中 `UserControl1`。</span><span class="sxs-lookup"><span data-stu-id="377b5-131">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="377b5-132">有关详细信息，请参阅[如何： 选择和设计图面上移动元素](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474)。</span><span class="sxs-lookup"><span data-stu-id="377b5-132">For more information, see [How to: Select and Move Elements on the Design Surface](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>

3. <span data-ttu-id="377b5-133">在中**属性**窗口中，设置的值<xref:System.Windows.FrameworkElement.Width%2A>并<xref:System.Windows.FrameworkElement.Height%2A>属性设置为**200**。</span><span class="sxs-lookup"><span data-stu-id="377b5-133">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="377b5-134">从**工具箱**，拖动<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>控件拖到设计图面上的。</span><span class="sxs-lookup"><span data-stu-id="377b5-134">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="377b5-135">在中**属性**窗口中，设置的值<xref:System.Windows.Controls.TextBox.Text%2A>属性设置为**承载的内容**。</span><span class="sxs-lookup"><span data-stu-id="377b5-135">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="377b5-136">一般情况下，你应承载更复杂的 WPF 内容。</span><span class="sxs-lookup"><span data-stu-id="377b5-136">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="377b5-137">此处，<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 控件仅为了便于说明。</span><span class="sxs-lookup"><span data-stu-id="377b5-137">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="377b5-138">生成项目。</span><span class="sxs-lookup"><span data-stu-id="377b5-138">Build the project.</span></span>

## <a name="adding-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="377b5-139">将 WPF 控件添加到 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="377b5-139">Adding a WPF Control to a Windows Form</span></span>

<span data-ttu-id="377b5-140">新的 WPF 控件可供在窗体上使用。</span><span class="sxs-lookup"><span data-stu-id="377b5-140">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="377b5-141">Windows 窗体使用<xref:System.Windows.Forms.Integration.ElementHost>承载 WPF 内容的控件。</span><span class="sxs-lookup"><span data-stu-id="377b5-141">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

### <a name="to-add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="377b5-142">将 WPF 控件添加到 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="377b5-142">To add a WPF control to a Windows Form</span></span>

1. <span data-ttu-id="377b5-143">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="377b5-143">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="377b5-144">在中**工具箱**，找到标记为选项卡**WPFUserControlLibrary WPF 用户控件**。</span><span class="sxs-lookup"><span data-stu-id="377b5-144">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="377b5-145">将 `UserControl1` 的实例拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="377b5-145">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="377b5-146">在窗体上自动创建 <xref:System.Windows.Forms.Integration.ElementHost> 控件以承载 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="377b5-146">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="377b5-147"><xref:System.Windows.Forms.Integration.ElementHost>控件被命名为`elementHost1`并在**属性**窗口中，您可以看到其<xref:System.Windows.Forms.Integration.ElementHost.Child%2A>属性设置为**UserControl1**。</span><span class="sxs-lookup"><span data-stu-id="377b5-147">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="377b5-148">将对 WPF 程序集的引用添加到项目。</span><span class="sxs-lookup"><span data-stu-id="377b5-148">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="377b5-149">`elementHost1` 控件具有显示可用承载选项的智能标记面板。</span><span class="sxs-lookup"><span data-stu-id="377b5-149">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="377b5-150">在中**ElementHost 任务**智能标记面板中，选择**在父容器中的停靠**。</span><span class="sxs-lookup"><span data-stu-id="377b5-150">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="377b5-151">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="377b5-151">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="377b5-152">后续步骤</span><span class="sxs-lookup"><span data-stu-id="377b5-152">Next Steps</span></span>

<span data-ttu-id="377b5-153">Windows 窗体和 WPF 是不同的技术，但它们设计为可以密切地互操作。</span><span class="sxs-lookup"><span data-stu-id="377b5-153">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="377b5-154">若要提供更丰富的外观和行为应用程序中的，请尝试以下方法：</span><span class="sxs-lookup"><span data-stu-id="377b5-154">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="377b5-155">在 WPF 页中承载 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="377b5-155">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="377b5-156">有关详细信息，请参阅[演练： 承载 Windows 窗体控件在 WPF 中](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="377b5-156">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="377b5-157">将 Windows 窗体的视觉样式应用于你的 WPF 内容。</span><span class="sxs-lookup"><span data-stu-id="377b5-157">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="377b5-158">有关详细信息，请参阅[如何：在混合应用程序中启用视觉样式](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)。</span><span class="sxs-lookup"><span data-stu-id="377b5-158">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="377b5-159">更改 WPF 内容的样式。</span><span class="sxs-lookup"><span data-stu-id="377b5-159">Change the style of your WPF content.</span></span> <span data-ttu-id="377b5-160">有关详细信息，请参阅[演练： 设置 WPF 内容](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)。</span><span class="sxs-lookup"><span data-stu-id="377b5-160">For more information, see [Walkthrough: Styling WPF Content](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="377b5-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="377b5-161">See Also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="377b5-162">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="377b5-162">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="377b5-163">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="377b5-163">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)
- [<span data-ttu-id="377b5-164">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="377b5-164">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
