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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: fc6f988d6ffd270eba4abe277ca34fa2eeec56fd
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197422"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="d341d-102">演练：在设计时在 Windows 窗体上创建新的 WPF 内容</span><span class="sxs-lookup"><span data-stu-id="d341d-102">Walkthrough: Create new WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="d341d-103">本文介绍如何创建 Windows Presentation Foundation （WPF）控件，以便在基于 Windows 窗体的应用程序中使用。</span><span class="sxs-lookup"><span data-stu-id="d341d-103">This article shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d341d-104">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="d341d-104">Prerequisites</span></span>

<span data-ttu-id="d341d-105">若要完成本演练，必须具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="d341d-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="d341d-106">创建项目</span><span class="sxs-lookup"><span data-stu-id="d341d-106">Create the project</span></span>

<span data-ttu-id="d341d-107">打开 Visual Studio，并在 Visual Basic 或 Visual C#命名 `HostingWpf`中创建新的**Windows 窗体应用程序（.NET Framework）** 项目。</span><span class="sxs-lookup"><span data-stu-id="d341d-107">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="d341d-108">承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="d341d-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-a-new-wpf-control"></a><span data-ttu-id="d341d-109">创建新的 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="d341d-109">Create a new WPF control</span></span>

<span data-ttu-id="d341d-110">创建新的 WPF 控件并将其添加到你的项目中，这与将任何其他项添加到你的项目中一样容易。</span><span class="sxs-lookup"><span data-stu-id="d341d-110">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="d341d-111">Windows 窗体设计器使用名为*复合控件*或*用户控件*的特定类型控件。</span><span class="sxs-lookup"><span data-stu-id="d341d-111">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="d341d-112">有关 WPF 用户控件的详细信息，请参阅 <xref:System.Windows.Controls.UserControl>。</span><span class="sxs-lookup"><span data-stu-id="d341d-112">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="d341d-113">WPF 的 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> 类型不同于 Windows 窗体提供的用户控件类型（也称为 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>）。</span><span class="sxs-lookup"><span data-stu-id="d341d-113">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="d341d-114">若要创建新的 WPF 控件：</span><span class="sxs-lookup"><span data-stu-id="d341d-114">To create a new WPF control:</span></span>

1. <span data-ttu-id="d341d-115">在**解决方案资源管理器**中，将一个新的**WPF 用户控件库（.NET Framework）** 项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="d341d-115">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="d341d-116">使用控件库默认名称 `WpfControlLibrary1`。</span><span class="sxs-lookup"><span data-stu-id="d341d-116">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="d341d-117">默认控件名称是 `UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="d341d-117">The default control name is `UserControl1.xaml`.</span></span>

   <span data-ttu-id="d341d-118">添加新控件具有以下效果：</span><span class="sxs-lookup"><span data-stu-id="d341d-118">Adding the new control has the following effects:</span></span>

   - <span data-ttu-id="d341d-119">添加文件 UserControl1.xaml。</span><span class="sxs-lookup"><span data-stu-id="d341d-119">File UserControl1.xaml is added.</span></span>

   - <span data-ttu-id="d341d-120">添加文件 UserControl1.xaml.cs （或 UserControl1）。</span><span class="sxs-lookup"><span data-stu-id="d341d-120">File UserControl1.xaml.cs (or UserControl1.xaml.vb) is added.</span></span> <span data-ttu-id="d341d-121">此文件包含事件处理程序和其他实现的代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="d341d-121">This file contains the code-behind for event handlers and other implementation.</span></span>

   - <span data-ttu-id="d341d-122">添加对 WPF 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d341d-122">References to WPF assemblies are added.</span></span>

   - <span data-ttu-id="d341d-123">文件 UserControl1 在 Visual Studio 的 WPF 设计器中打开。</span><span class="sxs-lookup"><span data-stu-id="d341d-123">File UserControl1.xaml opens in the WPF Designer for Visual Studio.</span></span>

2. <span data-ttu-id="d341d-124">在设计视图中，请确保已选中 `UserControl1`。</span><span class="sxs-lookup"><span data-stu-id="d341d-124">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="d341d-125">在 "**属性**" 窗口中，将 "<xref:System.Windows.FrameworkElement.Width%2A>" 和 "<xref:System.Windows.FrameworkElement.Height%2A>" 属性的值设置为**200**。</span><span class="sxs-lookup"><span data-stu-id="d341d-125">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="d341d-126">从 "**工具箱**" 中，将 "<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>" 控件拖动到设计图面上。</span><span class="sxs-lookup"><span data-stu-id="d341d-126">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="d341d-127">在 "**属性**" 窗口中，将 "<xref:System.Windows.Controls.TextBox.Text%2A>" 属性的值设置为 "**托管内容**"。</span><span class="sxs-lookup"><span data-stu-id="d341d-127">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d341d-128">一般情况下，你应承载更复杂的 WPF 内容。</span><span class="sxs-lookup"><span data-stu-id="d341d-128">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="d341d-129">此处，<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 控件仅为了便于说明。</span><span class="sxs-lookup"><span data-stu-id="d341d-129">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="d341d-130">生成项目。</span><span class="sxs-lookup"><span data-stu-id="d341d-130">Build the project.</span></span>

## <a name="add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="d341d-131">将 WPF 控件添加到 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="d341d-131">Add a WPF control to a Windows Form</span></span>

<span data-ttu-id="d341d-132">新的 WPF 控件可供在窗体上使用。</span><span class="sxs-lookup"><span data-stu-id="d341d-132">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="d341d-133">Windows 窗体使用 <xref:System.Windows.Forms.Integration.ElementHost> 控件来承载 WPF 内容。</span><span class="sxs-lookup"><span data-stu-id="d341d-133">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

<span data-ttu-id="d341d-134">若要将 WPF 控件添加到 Windows 窗体：</span><span class="sxs-lookup"><span data-stu-id="d341d-134">To add a WPF control to a Windows Form:</span></span>

1. <span data-ttu-id="d341d-135">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="d341d-135">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="d341d-136">在 "**工具箱**" 中，找到标记为 " **WPFUserControlLibrary WPF 用户控件**" 的选项卡。</span><span class="sxs-lookup"><span data-stu-id="d341d-136">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="d341d-137">将 `UserControl1` 的实例拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="d341d-137">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="d341d-138">在窗体上自动创建 <xref:System.Windows.Forms.Integration.ElementHost> 控件以承载 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="d341d-138">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="d341d-139"><xref:System.Windows.Forms.Integration.ElementHost> 控件被命名为 `elementHost1` 并在 "**属性**" 窗口中，可以看到其 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 属性设置为 " **UserControl1**"。</span><span class="sxs-lookup"><span data-stu-id="d341d-139">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="d341d-140">将对 WPF 程序集的引用添加到项目。</span><span class="sxs-lookup"><span data-stu-id="d341d-140">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="d341d-141">`elementHost1` 控件具有显示可用承载选项的智能标记面板。</span><span class="sxs-lookup"><span data-stu-id="d341d-141">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="d341d-142">在 " **ElementHost 任务**" 智能标记面板中，选择 "**在父容器中停靠**"。</span><span class="sxs-lookup"><span data-stu-id="d341d-142">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="d341d-143">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="d341d-143">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d341d-144">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d341d-144">Next steps</span></span>

<span data-ttu-id="d341d-145">Windows 窗体和 WPF 是不同的技术，但它们设计为可以密切地互操作。</span><span class="sxs-lookup"><span data-stu-id="d341d-145">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="d341d-146">若要在应用程序中提供更丰富的外观和行为，请尝试以下操作：</span><span class="sxs-lookup"><span data-stu-id="d341d-146">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="d341d-147">在 WPF 页中承载 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="d341d-147">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="d341d-148">有关详细信息，请参阅[演练：在 WPF 中承载 Windows 窗体控件](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="d341d-148">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="d341d-149">将 Windows 窗体的视觉样式应用于你的 WPF 内容。</span><span class="sxs-lookup"><span data-stu-id="d341d-149">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="d341d-150">有关详细信息，请参阅[如何：在混合应用程序中启用视觉样式](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)。</span><span class="sxs-lookup"><span data-stu-id="d341d-150">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="d341d-151">更改 WPF 内容的样式。</span><span class="sxs-lookup"><span data-stu-id="d341d-151">Change the style of your WPF content.</span></span> <span data-ttu-id="d341d-152">有关详细信息，请参阅[演练：设置 WPF 内容的样式](walkthrough-styling-wpf-content.md)。</span><span class="sxs-lookup"><span data-stu-id="d341d-152">For more information, see [Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d341d-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="d341d-153">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="d341d-154">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="d341d-154">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="d341d-155">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="d341d-155">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="d341d-156">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="d341d-156">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
