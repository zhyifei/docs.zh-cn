---
title: 演练：设置 WPF 内容的样式
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8b9e2c5c05f1a4b263890c2d8ca8474abe07d836
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197412"
---
# <a name="walkthrough-style-wpf-content"></a><span data-ttu-id="7687d-102">演练：样式 WPF 内容</span><span class="sxs-lookup"><span data-stu-id="7687d-102">Walkthrough: Style WPF content</span></span>

<span data-ttu-id="7687d-103">本文介绍如何将样式应用于 Windows 窗体上承载的 Windows Presentation Foundation （WPF）控件。</span><span class="sxs-lookup"><span data-stu-id="7687d-103">This article show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7687d-104">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="7687d-104">Prerequisites</span></span>

<span data-ttu-id="7687d-105">若要完成本演练，必须具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="7687d-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="7687d-106">创建项目</span><span class="sxs-lookup"><span data-stu-id="7687d-106">Create the project</span></span>

<span data-ttu-id="7687d-107">打开 Visual Studio，并在 Visual Basic 或视觉对象C#命名 `StylingWpfContent`中创建新的 Windows 窗体应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="7687d-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="7687d-108">承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="7687d-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="7687d-109">创建 WPF 控件类型</span><span class="sxs-lookup"><span data-stu-id="7687d-109">Create the WPF control types</span></span>

<span data-ttu-id="7687d-110">将 WPF 控件类型添加到项目后，就可在 <xref:System.Windows.Forms.Integration.ElementHost> 控件中托管它。</span><span class="sxs-lookup"><span data-stu-id="7687d-110">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

1. <span data-ttu-id="7687d-111">将新的 WPF <xref:System.Windows.Controls.UserControl> 项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="7687d-111">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="7687d-112">使用控件类型的默认名称，`UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="7687d-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="7687d-113">有关详细信息，请参阅[演练：在设计时在 Windows 窗体上创建新的 WPF 内容](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="7687d-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="7687d-114">在设计视图中，请确保已选中 `UserControl1`。</span><span class="sxs-lookup"><span data-stu-id="7687d-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="7687d-115">在 "**属性**" 窗口中，将 "<xref:System.Windows.FrameworkElement.Width%2A>" 和 "<xref:System.Windows.FrameworkElement.Height%2A>" 属性的值设置为**200**。</span><span class="sxs-lookup"><span data-stu-id="7687d-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="7687d-116">向 <xref:System.Windows.Controls.UserControl> 中添加 <xref:System.Windows.Controls.Button?displayProperty=nameWithType> 控件，并将 <xref:System.Windows.Controls.ContentControl.Content%2A> 属性的值设置为 "**取消**"。</span><span class="sxs-lookup"><span data-stu-id="7687d-116">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>

5. <span data-ttu-id="7687d-117">将第二个 <xref:System.Windows.Controls.Button?displayProperty=nameWithType> 控件添加到 <xref:System.Windows.Controls.UserControl> 并将 <xref:System.Windows.Controls.ContentControl.Content%2A> 属性的值设置为 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="7687d-117">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>

6. <span data-ttu-id="7687d-118">生成项目。</span><span class="sxs-lookup"><span data-stu-id="7687d-118">Build the project.</span></span>

## <a name="apply-a-style-to-a-wpf-control"></a><span data-ttu-id="7687d-119">将样式应用到 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="7687d-119">Apply a Style to a WPF Control</span></span>

<span data-ttu-id="7687d-120">可对 WPF 控件应用不同样式以更改它的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="7687d-120">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>

1. <span data-ttu-id="7687d-121">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="7687d-121">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="7687d-122">在 "**工具箱**" 中，双击 "`UserControl1`" 以在窗体上创建 `UserControl1` 的实例。</span><span class="sxs-lookup"><span data-stu-id="7687d-122">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="7687d-123">`UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="7687d-123">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

1. <span data-ttu-id="7687d-124">在 `elementHost1`的智能标记面板中，单击下拉列表中的 "**编辑承载的内容**"。</span><span class="sxs-lookup"><span data-stu-id="7687d-124">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>

   <span data-ttu-id="7687d-125">`UserControl1` 在 WPF 设计器中打开。</span><span class="sxs-lookup"><span data-stu-id="7687d-125">`UserControl1` opens in the WPF Designer.</span></span>

1. <span data-ttu-id="7687d-126">在 XAML 视图中，将以下 XAML 插到 `<UserControl>` 开始标记后面。</span><span class="sxs-lookup"><span data-stu-id="7687d-126">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span> <span data-ttu-id="7687d-127">此 XAML 创建具有对比渐变边框的渐变。</span><span class="sxs-lookup"><span data-stu-id="7687d-127">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="7687d-128">单击此控件后，将更改渐变以生成按下按钮的外观。</span><span class="sxs-lookup"><span data-stu-id="7687d-128">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="7687d-129">有关详细信息，请参阅[样式设置和模板化](../../wpf/controls/styling-and-templating.md)。</span><span class="sxs-lookup"><span data-stu-id="7687d-129">For more information, see [Styling and Templating](../../wpf/controls/styling-and-templating.md).</span></span>

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

1. <span data-ttu-id="7687d-130">通过在 "**取消**" 按钮的 `<Button>` 标记中插入以下 XAML，将上一步中定义的 `SimpleButton` 样式应用到 "取消" 按钮。</span><span class="sxs-lookup"><span data-stu-id="7687d-130">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the **Cancel** button.</span></span>

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   <span data-ttu-id="7687d-131">按钮声明将类似于以下 XAML：</span><span class="sxs-lookup"><span data-stu-id="7687d-131">Your button declaration will resemble the following XAML:</span></span>

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. <span data-ttu-id="7687d-132">生成项目。</span><span class="sxs-lookup"><span data-stu-id="7687d-132">Build the project.</span></span>

1. <span data-ttu-id="7687d-133">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="7687d-133">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="7687d-134">将新样式应用到按钮控件中。</span><span class="sxs-lookup"><span data-stu-id="7687d-134">The new style is applied to the button control.</span></span>

1. <span data-ttu-id="7687d-135">从 "**调试**" 菜单中，选择 "**启动调试**" 以运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="7687d-135">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>

1. <span data-ttu-id="7687d-136">单击 **"确定" 和 "** **取消**" 按钮，查看不同之处。</span><span class="sxs-lookup"><span data-stu-id="7687d-136">Click the **OK** and **Cancel** buttons and view the differences.</span></span>

## <a name="see-also"></a><span data-ttu-id="7687d-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="7687d-137">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="7687d-138">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="7687d-138">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="7687d-139">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="7687d-139">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="7687d-140">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="7687d-140">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="7687d-141">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="7687d-141">XAML Overview (WPF)</span></span>](../../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="7687d-142">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="7687d-142">Styling and Templating</span></span>](../../wpf/controls/styling-and-templating.md)
