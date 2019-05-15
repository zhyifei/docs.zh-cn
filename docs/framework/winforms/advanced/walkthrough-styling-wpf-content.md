---
title: 演练：设置 WPF 内容的样式
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: b689bb7299d541708db7ae786bff62a1007608e5
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2019
ms.locfileid: "65557886"
---
# <a name="walkthrough-style-wpf-content"></a><span data-ttu-id="6cca7-102">演练：样式的 WPF 内容</span><span class="sxs-lookup"><span data-stu-id="6cca7-102">Walkthrough: Style WPF content</span></span>

<span data-ttu-id="6cca7-103">本演练显示了如何将样式应用到 Windows 窗体上承载的 Windows Presentation Foundation (WPF) 控件中。</span><span class="sxs-lookup"><span data-stu-id="6cca7-103">This walkthrough show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

 <span data-ttu-id="6cca7-104">在本演练中，你将要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="6cca7-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="6cca7-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="6cca7-105">Create the project.</span></span>

- <span data-ttu-id="6cca7-106">创建 WPF 控件类型。</span><span class="sxs-lookup"><span data-stu-id="6cca7-106">Create the WPF control type.</span></span>

- <span data-ttu-id="6cca7-107">将样式应用到 WPF control.a</span><span class="sxs-lookup"><span data-stu-id="6cca7-107">Apply a style to the WPF control.a</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6cca7-108">系统必备</span><span class="sxs-lookup"><span data-stu-id="6cca7-108">Prerequisites</span></span>

<span data-ttu-id="6cca7-109">若要完成本演练，必须具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="6cca7-109">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="6cca7-110">创建项目</span><span class="sxs-lookup"><span data-stu-id="6cca7-110">Create the project</span></span>

<span data-ttu-id="6cca7-111">打开 Visual Studio 并创建新的 Windows 窗体应用程序项目在 Visual Basic 或 VisualC#名为`StylingWpfContent`。</span><span class="sxs-lookup"><span data-stu-id="6cca7-111">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="6cca7-112">承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="6cca7-112">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="6cca7-113">创建 WPF 控件类型</span><span class="sxs-lookup"><span data-stu-id="6cca7-113">Create the WPF control types</span></span>

<span data-ttu-id="6cca7-114">将 WPF 控件类型添加到项目后，就可在 <xref:System.Windows.Forms.Integration.ElementHost> 控件中托管它。</span><span class="sxs-lookup"><span data-stu-id="6cca7-114">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

1. <span data-ttu-id="6cca7-115">将新的 WPF <xref:System.Windows.Controls.UserControl> 项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="6cca7-115">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="6cca7-116">使用控件类型的默认名称，`UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="6cca7-116">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="6cca7-117">有关详细信息，请参见[演练：在设计时在 Windows 窗体上创建新的 WPF 内容](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="6cca7-117">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="6cca7-118">在设计视图中，请确保已选中 `UserControl1`。</span><span class="sxs-lookup"><span data-stu-id="6cca7-118">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="6cca7-119">有关详细信息，请参阅[如何：选择并在设计图面上移动元素](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="6cca7-119">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="6cca7-120">在中**属性**窗口中，设置的值<xref:System.Windows.FrameworkElement.Width%2A>并<xref:System.Windows.FrameworkElement.Height%2A>属性设置为`200`。</span><span class="sxs-lookup"><span data-stu-id="6cca7-120">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

4. <span data-ttu-id="6cca7-121">添加<xref:System.Windows.Controls.Button?displayProperty=nameWithType>控制对<xref:System.Windows.Controls.UserControl>并将值设置<xref:System.Windows.Controls.ContentControl.Content%2A>属性设置为**取消**。</span><span class="sxs-lookup"><span data-stu-id="6cca7-121">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>

5. <span data-ttu-id="6cca7-122">添加另一个<xref:System.Windows.Controls.Button?displayProperty=nameWithType>控制对<xref:System.Windows.Controls.UserControl>并将值设置<xref:System.Windows.Controls.ContentControl.Content%2A>属性设置为**确定**。</span><span class="sxs-lookup"><span data-stu-id="6cca7-122">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>

6. <span data-ttu-id="6cca7-123">生成项目。</span><span class="sxs-lookup"><span data-stu-id="6cca7-123">Build the project.</span></span>

## <a name="apply-a-style-to-a-wpf-control"></a><span data-ttu-id="6cca7-124">将样式应用到 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="6cca7-124">Apply a Style to a WPF Control</span></span>

<span data-ttu-id="6cca7-125">可对 WPF 控件应用不同样式以更改它的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="6cca7-125">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>

1. <span data-ttu-id="6cca7-126">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="6cca7-126">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="6cca7-127">在中**工具箱**，双击`UserControl1`若要创建的实例`UserControl1`窗体上。</span><span class="sxs-lookup"><span data-stu-id="6cca7-127">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

     <span data-ttu-id="6cca7-128">`UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="6cca7-128">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

1. <span data-ttu-id="6cca7-129">中的智能标记面板`elementHost1`，单击**编辑所承载的内容**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="6cca7-129">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>

     <span data-ttu-id="6cca7-130">`UserControl1` 将在 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] 中打开。</span><span class="sxs-lookup"><span data-stu-id="6cca7-130">`UserControl1` opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

1. <span data-ttu-id="6cca7-131">在 XAML 视图中，将以下 XAML 插到 `<UserControl>` 开始标记后面。</span><span class="sxs-lookup"><span data-stu-id="6cca7-131">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span>

     <span data-ttu-id="6cca7-132">此 XAML 创建具有对比渐变边框的渐变。</span><span class="sxs-lookup"><span data-stu-id="6cca7-132">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="6cca7-133">单击此控件后，将更改渐变以生成按下按钮的外观。</span><span class="sxs-lookup"><span data-stu-id="6cca7-133">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="6cca7-134">有关详细信息，请参阅[样式设置和模板化](../../wpf/controls/styling-and-templating.md)。</span><span class="sxs-lookup"><span data-stu-id="6cca7-134">For more information, see [Styling and Templating](../../wpf/controls/styling-and-templating.md).</span></span>

   ```xaml
   <UserControl.Resources>
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#FFF" Offset="0.0"/>
        <GradientStop Color="#CCC" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#BBB" Offset="0.0"/>
        <GradientStop Color="#EEE" Offset="0.1"/>
        <GradientStop Color="#EEE" Offset="0.9"/>
        <GradientStop Color="#FFF" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#444" Offset="0.0"/>
        <GradientStop Color="#888" Offset="1.0"/>
    </LinearGradientBrush>

    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="{x:Type Button}">
                    <Grid x:Name="Grid">
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>
                    </Grid>
                    <ControlTemplate.Triggers>
                        <Trigger Property="IsPressed" Value="true">
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>
                        </Trigger>
                    </ControlTemplate.Triggers>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>
   </UserControl.Resources>
   ```

1. <span data-ttu-id="6cca7-135">通过插入“取消”按钮的 `<Button>` 标记中的以下 XAML，将上一步中定义的 `SimpleButton` 样式应用到“取消”按钮。</span><span class="sxs-lookup"><span data-stu-id="6cca7-135">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the Cancel button.</span></span>

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   <span data-ttu-id="6cca7-136">按钮声明将类似于以下 XAML:</span><span class="sxs-lookup"><span data-stu-id="6cca7-136">Your button declaration will resemble the following XAML:</span></span>

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. <span data-ttu-id="6cca7-137">生成项目。</span><span class="sxs-lookup"><span data-stu-id="6cca7-137">Build the project.</span></span>

1. <span data-ttu-id="6cca7-138">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="6cca7-138">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="6cca7-139">将新样式应用到按钮控件中。</span><span class="sxs-lookup"><span data-stu-id="6cca7-139">The new style is applied to the button control.</span></span>

1. <span data-ttu-id="6cca7-140">从**调试**菜单中，选择**开始调试**运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="6cca7-140">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>

1. <span data-ttu-id="6cca7-141">单击“确定”和“取消”按钮并查看差异。</span><span class="sxs-lookup"><span data-stu-id="6cca7-141">Click the OK and Cancel buttons and view the differences.</span></span>

## <a name="see-also"></a><span data-ttu-id="6cca7-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="6cca7-142">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="6cca7-143">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="6cca7-143">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="6cca7-144">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="6cca7-144">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="6cca7-145">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="6cca7-145">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="6cca7-146">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="6cca7-146">XAML Overview (WPF)</span></span>](../../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="6cca7-147">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="6cca7-147">Styling and Templating</span></span>](../../wpf/controls/styling-and-templating.md)
