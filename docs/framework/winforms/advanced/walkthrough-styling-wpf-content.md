---
title: 演练：设置 WPF 内容的样式
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: d815311a89ba09ade7e3092ca4eeab67cbe20bd0
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211267"
---
# <a name="walkthrough-style-wpf-content"></a>演练：样式的 WPF 内容

本演练显示了如何将样式应用到 Windows 窗体上承载的 Windows Presentation Foundation (WPF) 控件中。

 在本演练中，你将要执行以下任务：

- 创建项目。

- 创建 WPF 控件类型。

- 将样式应用到 WPF control.a

## <a name="prerequisites"></a>系统必备

若要完成本演练，必须具有 Visual Studio。

## <a name="create-the-project"></a>创建项目

打开 Visual Studio 并创建新的 Windows 窗体应用程序项目在 Visual Basic 或 VisualC#名为`StylingWpfContent`。

> [!NOTE]
> 承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。

## <a name="create-the-wpf-control-types"></a>创建 WPF 控件类型

将 WPF 控件类型添加到项目后，就可在 <xref:System.Windows.Forms.Integration.ElementHost> 控件中托管它。

1. 将新的 WPF <xref:System.Windows.Controls.UserControl> 项目添加到解决方案。 使用控件类型的默认名称，`UserControl1.xaml`。 有关详细信息，请参见[演练：在设计时在 Windows 窗体上创建新的 WPF 内容](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。

2. 在设计视图中，请确保已选中 `UserControl1`。 有关详细信息，请参阅[如何：选择并在设计图面上移动元素](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))。

3. 在中**属性**窗口中，设置的值<xref:System.Windows.FrameworkElement.Width%2A>并<xref:System.Windows.FrameworkElement.Height%2A>属性设置为`200`。

4. 添加<xref:System.Windows.Controls.Button?displayProperty=nameWithType>控制对<xref:System.Windows.Controls.UserControl>并将值设置<xref:System.Windows.Controls.ContentControl.Content%2A>属性设置为**取消**。

5. 添加另一个<xref:System.Windows.Controls.Button?displayProperty=nameWithType>控制对<xref:System.Windows.Controls.UserControl>并将值设置<xref:System.Windows.Controls.ContentControl.Content%2A>属性设置为**确定**。

6. 生成项目。

## <a name="apply-a-style-to-a-wpf-control"></a>将样式应用到 WPF 控件

可对 WPF 控件应用不同样式以更改它的外观和行为。

1. 在 Windows 窗体设计器中打开 `Form1`。

2. 在中**工具箱**，双击`UserControl1`若要创建的实例`UserControl1`窗体上。

     `UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。

3. 中的智能标记面板`elementHost1`，单击**编辑所承载的内容**从下拉列表。

     `UserControl1` 将在 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] 中打开。

4. 在 XAML 视图中，将以下 XAML 插到 `<UserControl>` 开始标记后面。

     此 XAML 创建具有对比渐变边框的渐变。 单击此控件后，将更改渐变以生成按下按钮的外观。 有关详细信息，请参阅[样式设置和模板化](../../wpf/controls/styling-and-templating.md)。

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

4. 通过插入“取消”按钮的 `<Button>` 标记中的以下 XAML，将上一步中定义的 `SimpleButton` 样式应用到“取消”按钮。

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   按钮声明将类似于以下 XAML:

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

5. 生成项目。

6. 在 Windows 窗体设计器中打开 `Form1`。

7. 将新样式应用到按钮控件中。

8. 从**调试**菜单中，选择**开始调试**运行该应用程序。

9. 单击“确定”和“取消”按钮并查看差异。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [迁移和互操作性](../../wpf/advanced/migration-and-interoperability.md)
- [使用 WPF 控件](using-wpf-controls.md)
- [在 Visual Studio 中设计 XAML](/visualstudio/designers/designing-xaml-in-visual-studio)
- [XAML 概述 (WPF)](../../wpf/advanced/xaml-overview-wpf.md)
- [样式设置和模板化](../../wpf/controls/styling-and-templating.md)
