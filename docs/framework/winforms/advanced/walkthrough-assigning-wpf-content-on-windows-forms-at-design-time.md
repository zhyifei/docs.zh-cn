---
title: 演练：在设计时在 Windows 窗体上分配 WPF 内容
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
ms.openlocfilehash: 09427bfc836f40ca9c7aa76f4904bfe7083bf8dc
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211240"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="ff5bc-102">演练：在设计时分配在 Windows 窗体上的 WPF 内容</span><span class="sxs-lookup"><span data-stu-id="ff5bc-102">Walkthrough: Assign WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="ff5bc-103">本演练展示了如何选择要在窗体上显示的 Windows Presentation Foundation (WPF) 控件类型。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-103">This walkthrough show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="ff5bc-104">可选择项目中包含的任何 WPF 控件类型。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-104">You can select any WPF control types which are included in your project.</span></span>

<span data-ttu-id="ff5bc-105">在本演练中，你将要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="ff5bc-105">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="ff5bc-106">创建项目。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-106">Create the project.</span></span>

- <span data-ttu-id="ff5bc-107">创建 WPF 控件类型。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-107">Create the WPF control types.</span></span>

- <span data-ttu-id="ff5bc-108">选择 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-108">Select WPF controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ff5bc-109">系统必备</span><span class="sxs-lookup"><span data-stu-id="ff5bc-109">Prerequisites</span></span>

<span data-ttu-id="ff5bc-110">若要完成本演练，必须具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-110">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="ff5bc-111">创建项目</span><span class="sxs-lookup"><span data-stu-id="ff5bc-111">Create the project</span></span>

<span data-ttu-id="ff5bc-112">打开 Visual Studio 并创建新的 Windows 窗体应用程序项目在 Visual Basic 或 VisualC#名为`SelectingWpfContent`。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-112">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="ff5bc-113">承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-113">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="ff5bc-114">创建 WPF 控件类型</span><span class="sxs-lookup"><span data-stu-id="ff5bc-114">Create the WPF control types</span></span>

<span data-ttu-id="ff5bc-115">将 WPF 控件类型添加到项目后，可将其托管到不同的 <xref:System.Windows.Forms.Integration.ElementHost> 控件。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-115">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>

## <a name="create-wpf-control-types"></a><span data-ttu-id="ff5bc-116">创建 WPF 控件类型</span><span class="sxs-lookup"><span data-stu-id="ff5bc-116">Create WPF control types</span></span>

1. <span data-ttu-id="ff5bc-117">将新的 WPF <xref:System.Windows.Controls.UserControl> 项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-117">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="ff5bc-118">使用控件类型的默认名称，`UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-118">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="ff5bc-119">有关详细信息，请参见[演练：在设计时在 Windows 窗体上创建新的 WPF 内容](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-119">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="ff5bc-120">在设计视图中，请确保已选中 `UserControl1`。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-120">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="ff5bc-121">有关详细信息，请参阅[如何：选择并在设计图面上移动元素](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-121">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="ff5bc-122">在中**属性**窗口中，设置的值<xref:System.Windows.FrameworkElement.Width%2A>并<xref:System.Windows.FrameworkElement.Height%2A>属性设置为`200`。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-122">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

4. <span data-ttu-id="ff5bc-123">添加<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>控制对<xref:System.Windows.Controls.UserControl>并将值设置<xref:System.Windows.Controls.TextBox.Text%2A>属性设置为**承载的内容**。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-123">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

5. <span data-ttu-id="ff5bc-124">将第二个 WPF <xref:System.Windows.Controls.UserControl> 添加到项目。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-124">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="ff5bc-125">使用控件类型的默认名称，`UserControl2.xaml`。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-125">Use the default name for the control type, `UserControl2.xaml`.</span></span>

6. <span data-ttu-id="ff5bc-126">在中**属性**窗口中，设置的值<xref:System.Windows.FrameworkElement.Width%2A>并<xref:System.Windows.FrameworkElement.Height%2A>属性设置为`200`。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-126">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

7. <span data-ttu-id="ff5bc-127">添加<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>控制对<xref:System.Windows.Controls.UserControl>并将值设置<xref:System.Windows.Controls.TextBox.Text%2A>属性设置为**承载的内容 2**。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-127">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>

 <span data-ttu-id="ff5bc-128">**请注意**一般情况下，你应承载更复杂的 WPF 内容。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-128">**Note** In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="ff5bc-129">此处，<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 控件仅为了便于说明。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-129">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

1. <span data-ttu-id="ff5bc-130">生成项目。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-130">Build the project.</span></span>

## <a name="select-wpf-controls"></a><span data-ttu-id="ff5bc-131">选择 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="ff5bc-131">Select WPF controls</span></span>

<span data-ttu-id="ff5bc-132">可将不同的 WPF 内容分配到 <xref:System.Windows.Forms.Integration.ElementHost> 控件，该控件现已承载内容。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-132">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>

1. <span data-ttu-id="ff5bc-133">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-133">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="ff5bc-134">在中**工具箱**，双击`UserControl1`若要创建的实例`UserControl1`窗体上。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-134">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

     <span data-ttu-id="ff5bc-135">`UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-135">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

3. <span data-ttu-id="ff5bc-136">中的智能标记面板`elementHost1`，打开**选择承载的内容**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-136">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>

4. <span data-ttu-id="ff5bc-137">选择**UserControl2**从下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-137">Select **UserControl2** from the drop-down list box.</span></span>

     <span data-ttu-id="ff5bc-138">`elementHost1` 控件现承载 `UserControl2` 类型的实例。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-138">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>

5. <span data-ttu-id="ff5bc-139">在中**属性**窗口中，确认<xref:System.Windows.Forms.Integration.ElementHost.Child%2A>属性设置为**UserControl2**。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-139">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>

6. <span data-ttu-id="ff5bc-140">从**工具箱**，在**WPF 互操作性**组中，将<xref:System.Windows.Forms.Integration.ElementHost>拖到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-140">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>

     <span data-ttu-id="ff5bc-141">新控件的默认名称是 `elementHost2`。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-141">The default name for the new control is `elementHost2`.</span></span>

7. <span data-ttu-id="ff5bc-142">中的智能标记面板`elementHost2`，打开**选择承载的内容**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-142">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>

8. <span data-ttu-id="ff5bc-143">选择**UserControl1**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-143">Select **UserControl1** from the drop-down list.</span></span>

9. <span data-ttu-id="ff5bc-144">`elementHost2` 控件现承载 `UserControl1` 类型的实例。</span><span class="sxs-lookup"><span data-stu-id="ff5bc-144">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff5bc-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff5bc-145">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="ff5bc-146">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="ff5bc-146">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="ff5bc-147">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="ff5bc-147">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="ff5bc-148">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="ff5bc-148">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
