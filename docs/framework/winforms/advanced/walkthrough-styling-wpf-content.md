---
title: 演练：样式 WPF 内容
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 07241d41e3fbf270a76bd241765bfa369ee265d5
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646330"
---
# <a name="walkthrough-style-wpf-content"></a><span data-ttu-id="00355-102">演练：样式 WPF 内容</span><span class="sxs-lookup"><span data-stu-id="00355-102">Walkthrough: Style WPF content</span></span>

<span data-ttu-id="00355-103">本文介绍如何将样式应用于 Windows 窗体上托管的 Windows 演示文稿基础 （WPF） 控件。</span><span class="sxs-lookup"><span data-stu-id="00355-103">This article show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="00355-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="00355-104">Prerequisites</span></span>

<span data-ttu-id="00355-105">若要完成本演练，必须具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="00355-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="00355-106">创建项目</span><span class="sxs-lookup"><span data-stu-id="00355-106">Create the project</span></span>

<span data-ttu-id="00355-107">打开可视化工作室，并在名为`StylingWpfContent`的"视觉基本"或"视觉 C#"中创建新的 Windows 窗体应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="00355-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="00355-108">承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="00355-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="00355-109">创建 WPF 控件类型</span><span class="sxs-lookup"><span data-stu-id="00355-109">Create the WPF control types</span></span>

<span data-ttu-id="00355-110">将 WPF 控件类型添加到项目后，就可在 <xref:System.Windows.Forms.Integration.ElementHost> 控件中托管它。</span><span class="sxs-lookup"><span data-stu-id="00355-110">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

1. <span data-ttu-id="00355-111">将新的 WPF <xref:System.Windows.Controls.UserControl> 项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="00355-111">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="00355-112">使用控件类型的默认名称，`UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="00355-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="00355-113">有关详细信息，请参阅[演练：在设计时间在 Windows 窗体上创建新的 WPF 内容](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="00355-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="00355-114">在设计视图中，请确保已选中 `UserControl1`。</span><span class="sxs-lookup"><span data-stu-id="00355-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="00355-115">在 **"属性"** 窗口中，将 和<xref:System.Windows.FrameworkElement.Width%2A><xref:System.Windows.FrameworkElement.Height%2A>属性的值设置为**200**。</span><span class="sxs-lookup"><span data-stu-id="00355-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="00355-116">将<xref:System.Windows.Controls.Button?displayProperty=nameWithType>控件添加到 ，<xref:System.Windows.Controls.UserControl>并将<xref:System.Windows.Controls.ContentControl.Content%2A>属性的值设置为 **"取消**"。</span><span class="sxs-lookup"><span data-stu-id="00355-116">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>

5. <span data-ttu-id="00355-117">将第二<xref:System.Windows.Controls.Button?displayProperty=nameWithType>个控件添加到<xref:System.Windows.Controls.UserControl>，并将<xref:System.Windows.Controls.ContentControl.Content%2A>属性的值设置为 **"确定**"。</span><span class="sxs-lookup"><span data-stu-id="00355-117">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>

6. <span data-ttu-id="00355-118">生成项目。</span><span class="sxs-lookup"><span data-stu-id="00355-118">Build the project.</span></span>

## <a name="apply-a-style-to-a-wpf-control"></a><span data-ttu-id="00355-119">将样式应用于 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="00355-119">Apply a Style to a WPF Control</span></span>

<span data-ttu-id="00355-120">可对 WPF 控件应用不同样式以更改它的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="00355-120">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>

1. <span data-ttu-id="00355-121">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="00355-121">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="00355-122">在**工具箱**中，双击`UserControl1`以在窗体上创建`UserControl1`的实例。</span><span class="sxs-lookup"><span data-stu-id="00355-122">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="00355-123">`UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="00355-123">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

1. <span data-ttu-id="00355-124">在 的`elementHost1`智能标记面板中，单击下拉列表中**的"编辑托管内容**"。</span><span class="sxs-lookup"><span data-stu-id="00355-124">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>

   <span data-ttu-id="00355-125">`UserControl1`在 WPF 设计器中打开。</span><span class="sxs-lookup"><span data-stu-id="00355-125">`UserControl1` opens in the WPF Designer.</span></span>

1. <span data-ttu-id="00355-126">在 XAML 视图中，将以下 XAML 插到 `<UserControl>` 开始标记后面。</span><span class="sxs-lookup"><span data-stu-id="00355-126">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span> <span data-ttu-id="00355-127">此 XAML 创建具有对比渐变边框的渐变。</span><span class="sxs-lookup"><span data-stu-id="00355-127">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="00355-128">单击此控件后，将更改渐变以生成按下按钮的外观。</span><span class="sxs-lookup"><span data-stu-id="00355-128">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="00355-129">有关详细信息，请参阅[样式和模板](../../../desktop-wpf/fundamentals/styles-templates-overview.md)化。</span><span class="sxs-lookup"><span data-stu-id="00355-129">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

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

1. <span data-ttu-id="00355-130">通过在"`SimpleButton`取消"按钮`<Button>`的标记中插入以下 XAML，将上一步中定义的样式应用于"**取消"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="00355-130">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the **Cancel** button.</span></span>

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   <span data-ttu-id="00355-131">您的按钮声明类似于以下 XAML：</span><span class="sxs-lookup"><span data-stu-id="00355-131">Your button declaration will resemble the following XAML:</span></span>

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. <span data-ttu-id="00355-132">生成项目。</span><span class="sxs-lookup"><span data-stu-id="00355-132">Build the project.</span></span>

1. <span data-ttu-id="00355-133">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="00355-133">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="00355-134">将新样式应用到按钮控件中。</span><span class="sxs-lookup"><span data-stu-id="00355-134">The new style is applied to the button control.</span></span>

1. <span data-ttu-id="00355-135">在 **"调试"** 菜单中，选择 **"开始调试"** 以运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="00355-135">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>

1. <span data-ttu-id="00355-136">单击"**确定\*\*\*\*"和"取消"** 按钮并查看差异。</span><span class="sxs-lookup"><span data-stu-id="00355-136">Click the **OK** and **Cancel** buttons and view the differences.</span></span>

## <a name="see-also"></a><span data-ttu-id="00355-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00355-137">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="00355-138">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="00355-138">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="00355-139">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="00355-139">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="00355-140">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="00355-140">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="00355-141">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="00355-141">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="00355-142">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="00355-142">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
