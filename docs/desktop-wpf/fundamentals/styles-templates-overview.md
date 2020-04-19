---
title: 样式和模板
description: 了解 .NET Core 的 Windows 演示基础 （WPF） 中的 XAML 资源。 了解与样式和主题相关的 XAML 资源类型。
author: thraka
ms.author: adegeo
ms.date: 09/09/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: f845e739ec3cae502d1e4fd6631f987c5364a42e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433096"
---
# <a name="styles-and-templates-in-wpf"></a>WPF 中的样式和模板

Windows 演示基础 （WPF） 样式和模板化是指一组功能，这些功能使开发人员和设计人员能够为其产品创建视觉上引人注目的效果和一致的外观。 自定义应用的外观时，您需要一个强大的样式和模板模型，以便维护和共享应用内部和应用程序之间的外观。 WPF 提供该模型。

WPF 样式模型的另一个功能是表示和逻辑的分离。 设计人员可以同时使用 XAML 处理应用的外观，而开发人员则使用 C# 或 Visual Basic 处理编程逻辑。

此概述侧重于应用程序的样式和模板化方面，不讨论任何数据绑定概念。 有关数据绑定的信息，请参阅[数据绑定概述](../data/data-binding-overview.md)。

了解资源非常重要，这些资源使样式和模板能够重复使用。 有关资源的详细信息，请参阅 [XAML 资源](xaml-resources-define.md)。

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sample"></a>示例

本概述中提供的示例代码基于下图所示[的简单照片浏览应用程序](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。

![带样式的 ListView](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

此简单照片示例使用样式设置和模板化创建极具视觉表现力的用户体验。 该示例具有两<xref:System.Windows.Controls.TextBlock>个元素和<xref:System.Windows.Controls.ListBox>一个绑定到图像列表的控件。

有关完整示例，请参阅[样式设置和模板化示例简介](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。

## <a name="styles"></a>样式

可以将 a<xref:System.Windows.Style>视为将一组属性值应用于多个元素的便捷方法。 <xref:System.Windows.FrameworkElement>可以在派生自<xref:System.Windows.FrameworkContentElement>或 或<xref:System.Windows.Window>或 的任何元素上使用样式。 <xref:System.Windows.Controls.Button>

声明样式的最常见方法是作为 XAML 文件中`Resources`部分中的资源。 因为样式是资源，因此它们遵循适用于所有资源的相同范围规则。 简单地说，声明样式会影响样式的应用位置。 例如，如果在应用定义 XAML 文件的根元素中声明样式，则可以在应用中的任意位置使用该样式。

例如，以下 XAML 代码声明 的两个样式`TextBlock`为 a ，`TextBlock`一个自动应用于所有元素， 另一个必须显式引用。

[!code-xaml[SnippetDefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

下面是上面声明使用的样式的示例。

[!code-xaml[SnippetTextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

![样式化文本块](./media/styles-and-templates-overview/stylingintro-textblocks.png)

有关详细信息，请参阅为[控件创建样式](styles-templates-create-apply-style.md)。

## <a name="controltemplates"></a>ControlTemplates

在 WPF<xref:System.Windows.Controls.ControlTemplate>中，控件的定义控件的外观。 您可以通过定义新<xref:System.Windows.Controls.ControlTemplate>控件并将其分配给控件来更改控件的结构和外观。 在许多情况下，模板为您提供足够的灵活性，因此您不必编写自己的自定义控件。

每个控件都有一个默认模板分配给[控件.Template](xref:System.Windows.Controls.Control.Template)属性。 该模板将控件的可视化表示与控件的功能连接起来。 由于在 XAML 中定义模板，因此无需编写任何代码即可更改控件的外观。 每个模板都专为特定控件而设计，<xref:System.Windows.Controls.Button>例如 。

通常，在 XAML 文件`Resources`部分将模板声明为资源。 与所有资源一样，范围规则适用。

控件模板比样式涉及更多。 这是因为控件模板重写整个控件的可视外观，而样式只是将属性更改应用于现有控件。 但是，由于控件的模板是通过设置[Control.template](xref:System.Windows.Controls.Control.Template)属性应用的，因此可以使用样式来定义或设置模板。

设计器通常允许您创建现有模板的副本并对其进行修改。 例如，在可视化工作室 WPF 设计器中，`CheckBox`选择控件，然后右键单击并选择 **"编辑模板** > **创建副本**"。 此命令生成*定义模板的样式*。

```xaml
<Style x:Key="CheckBoxStyle1" TargetType="{x:Type CheckBox}">
    <Setter Property="FocusVisualStyle" Value="{StaticResource FocusVisual1}"/>
    <Setter Property="Background" Value="{StaticResource OptionMark.Static.Background1}"/>
    <Setter Property="BorderBrush" Value="{StaticResource OptionMark.Static.Border1}"/>
    <Setter Property="Foreground" Value="{DynamicResource {x:Static SystemColors.ControlTextBrushKey}}"/>
    <Setter Property="BorderThickness" Value="1"/>
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="{x:Type CheckBox}">
                <Grid x:Name="templateRoot" Background="Transparent" SnapsToDevicePixels="True">
                    <Grid.ColumnDefinitions>
                        <ColumnDefinition Width="Auto"/>
                        <ColumnDefinition Width="*"/>
                    </Grid.ColumnDefinitions>
                    <Border x:Name="checkBoxBorder" Background="{TemplateBinding Background}" BorderThickness="{TemplateBinding BorderThickness}" BorderBrush="{TemplateBinding BorderBrush}" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="1" VerticalAlignment="{TemplateBinding VerticalContentAlignment}">
                        <Grid x:Name="markGrid">
                            <Path x:Name="optionMark" Data="F1 M 9.97498,1.22334L 4.6983,9.09834L 4.52164,9.09834L 0,5.19331L 1.27664,3.52165L 4.255,6.08833L 8.33331,1.52588e-005L 9.97498,1.22334 Z " Fill="{StaticResource OptionMark.Static.Glyph1}" Margin="1" Opacity="0" Stretch="None"/>
                            <Rectangle x:Name="indeterminateMark" Fill="{StaticResource OptionMark.Static.Glyph1}" Margin="2" Opacity="0"/>
                        </Grid>
                    </Border>
                    <ContentPresenter x:Name="contentPresenter" Grid.Column="1" Focusable="False" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" RecognizesAccessKey="True" SnapsToDevicePixels="{TemplateBinding SnapsToDevicePixels}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}"/>
                </Grid>
                <ControlTemplate.Triggers>
                    <Trigger Property="HasContent" Value="true">
                        <Setter Property="FocusVisualStyle" Value="{StaticResource OptionMarkFocusVisual1}"/>
                        <Setter Property="Padding" Value="4,-1,0,0"/>

... content removed to save space ...
```

编辑模板副本是了解模板工作方式的好方法。 编辑副本并更改可视化演示文稿的几个方面，而不是创建新的空白模板。

例如，请参阅为[控件创建模板](../themes/how-to-create-apply-template.md)。

### <a name="templatebinding"></a>TemplateBinding

您可能已经注意到上一节中定义的模板资源使用[模板绑定标记扩展](../../framework/wpf/advanced/templatebinding-markup-extension.md)。 A`TemplateBinding`是模板方案绑定的优化形式，类似于使用 构造的`{Binding RelativeSource={RelativeSource TemplatedParent}}`绑定。 `TemplateBinding`可用于将模板的某些部分绑定到控件的属性。 例如，每个控件都有一个<xref:System.Windows.Controls.Control.BorderThickness>属性。 使用`TemplateBinding`管理模板中的哪个元素受此控件设置的影响。

### <a name="contentcontrol-and-itemscontrol"></a>内容控制和项目控制

<xref:System.Windows.Controls.ContentPresenter>如果在<xref:System.Windows.Controls.ControlTemplate>中声明 的<xref:System.Windows.Controls.ContentControl><xref:System.Windows.Controls.ContentPresenter><xref:System.Windows.Controls.ContentControl.ContentTemplate%2A><xref:System.Windows.Controls.ContentControl.Content%2A>。 同样，<xref:System.Windows.Controls.ItemsPresenter>中<xref:System.Windows.Controls.ControlTemplate>的 的<xref:System.Windows.Controls.ItemsControl>a 将自动绑定到<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A><xref:System.Windows.Controls.ItemsControl.Items%2A>和 属性。

## <a name="datatemplates"></a>数据模板

在此示例应用中，有一个<xref:System.Windows.Controls.ListBox>控件绑定到照片列表。

[!code-xaml[ListBox](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window3.xaml#SnippetListBox)]

目前<xref:System.Windows.Controls.ListBox>如下所示。

![应用模板之前的 ListBox](./media/styles-and-templates-overview/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")

大多数控件都具有某些类型的内容，并且该内容通常来自要绑定到的数据。 在此示例中，数据是照片列表。 在 WPF 中，<xref:System.Windows.DataTemplate>使用 定义数据的可视表示形式。 基本上，您放入的<xref:System.Windows.DataTemplate>，决定了数据在呈现应用中的外观。

在我们的示例应用中，每个自定义`Photo`对象都有一个`Source`类型字符串的属性，用于指定图像的文件路径。 当前，照片对象显示为文件路径。

[!code-csharp[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Photo.cs#PhotoClass)]
[!code-vb[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/Photo.vb#PhotoClass)]

要将照片显示为图像，请创建 一<xref:System.Windows.DataTemplate>个资源。

[!code-xaml[DataTemplate](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window4.xaml#SnippetDataTemplate)]

请注意，<xref:System.Windows.DataTemplate.DataType%2A>该属性与<xref:System.Windows.Style.TargetType%2A>的属性<xref:System.Windows.Style>类似。 如果 位于资源部分中，则当您将<xref:System.Windows.DataTemplate.DataType%2A>属性指定为类型并省略 时`x:Key`，每当出现该类型时，都会应用 。 <xref:System.Windows.DataTemplate> <xref:System.Windows.DataTemplate> 您始终可以选择使用 分配 ，<xref:System.Windows.DataTemplate>`x:Key`然后`StaticResource`将其设置为 用于采用<xref:System.Windows.DataTemplate>类型的属性，如<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>属性或<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>属性。

从本质上讲，<xref:System.Windows.DataTemplate>上述示例中的定义是，每当有对象`Photo`时，它应显示为 中的 a。 <xref:System.Windows.Controls.Image> <xref:System.Windows.Controls.Border> 有了这个<xref:System.Windows.DataTemplate>，我们的应用程序现在看起来像这样。

![照片图](./media/styles-and-templates-overview/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")

数据模板化模型提供其他功能。 例如，<xref:System.Windows.Controls.HeaderedItemsControl>如果显示的集合数据包含使用类型（如 或<xref:System.Windows.Controls.Menu>） 的其他集合<xref:System.Windows.Controls.TreeView>，则存在 。 <xref:System.Windows.HierarchicalDataTemplate> 另一个数据模板化功能是<xref:System.Windows.Controls.DataTemplateSelector>，它允许您根据自定义逻辑<xref:System.Windows.DataTemplate>选择 要使用的 。 有关详细信息，请参阅[数据模板化概述](../../framework/wpf/data/data-templating-overview.md)，该概述提供不同数据模板化功能的更多深入讨论。

## <a name="triggers"></a>触发器

触发器在属性值发生更改或引发事件时设置属性或启动操作，例如动画。 <xref:System.Windows.Style><xref:System.Windows.Controls.ControlTemplate>，并且<xref:System.Windows.DataTemplate>所有`Triggers`属性都可以包含一组触发器。 有几种类型的触发器。

### <a name="propertytriggers"></a>属性触发器

设置<xref:System.Windows.Trigger>属性值或基于属性值启动操作的 A 称为属性触发器。

要演示如何使用属性触发器，可以使每个<xref:System.Windows.Controls.ListBoxItem>触发器部分透明，除非已选择。 以下样式设置<xref:System.Windows.UIElement.Opacity%2A><xref:System.Windows.Controls.ListBoxItem>到`0.5`的值。 但是，<xref:System.Windows.Controls.ListBoxItem.IsSelected%2A>当`true`属性为 时<xref:System.Windows.UIElement.Opacity%2A>，将`1.0`设置为 。

[!code-xaml[PropertyTrigger](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window5.xaml#SnippetPropertyTrigger)]

此示例使用 设置<xref:System.Windows.Trigger>属性值，但请注意，<xref:System.Windows.Trigger>类还具有 使触发器执行操作<xref:System.Windows.TriggerBase.EnterActions%2A>的<xref:System.Windows.TriggerBase.ExitActions%2A>和 属性。

请注意，<xref:System.Windows.FrameworkElement.MaxHeight%2A>的属性<xref:System.Windows.Controls.ListBoxItem>设置为`75`。 在下图中，第三个项目是所选项。

![带样式的 ListView](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

### <a name="eventtriggers-and-storyboards"></a>EventTrigger 和情节提要

另一种类型的触发器是<xref:System.Windows.EventTrigger>，它根据事件的发生启动一组操作。 例如，以下<xref:System.Windows.EventTrigger>对象指定当鼠标指针进入 时<xref:System.Windows.Controls.ListBoxItem>，<xref:System.Windows.FrameworkElement.MaxHeight%2A>属性将动画化为超过`90``0.2`第二个周期的值。 当鼠标离开该项时，属性在 `1` 秒的时间内返回到原始值。 请注意，如何不必为<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A><xref:System.Windows.ContentElement.MouseLeave>动画指定值。 这是因为动画能够跟踪原始值。

[!code-xaml[StyleEventTriggers](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window6.xaml#SnippetStyleEventTriggers)]

有关详细信息，请参阅[情节提要概述](../../framework/wpf/graphics-multimedia/storyboards-overview.md)。

在下图中，鼠标指向第三个项目。

![样式示例屏幕截图](./media/styles-and-templates-overview/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>MultiTrigger、DataTrigger 和 MultiDataTrigger

除了<xref:System.Windows.Trigger>和<xref:System.Windows.EventTrigger>之外，还有其他类型的触发器。 <xref:System.Windows.MultiTrigger>允许您根据多个条件设置属性值。 使用<xref:System.Windows.DataTrigger>条件的属性<xref:System.Windows.MultiDataTrigger>为数据绑定时使用。

## <a name="visual-states"></a>视觉状态

控件始终处于特定**状态**。 例如，当鼠标在控件的表面上移动时，控件被视为处于 的通用状态`MouseOver`。 没有特定状态的控件被视为处于公共`Normal`状态。 州被分为组，前面提到的州是州组的`CommonStates`一部分。 大多数控件有两个状态组`CommonStates`：`FocusStates`和 。 应用于控件的每个状态组中，控件始终处于每个组的一个状态，如`CommonStates.MouseOver`和`FocusStates.Unfocused`。 但是，控件不能处于同一组中的两个不同的状态，例如`CommonStates.Normal`和`CommonStates.Disabled`。 下面是大多数控件识别和使用状态的表。

| VisualState 名称 | VisualStateGroup 名称 | 说明 |
| ---------------- | --------------------- | ----------- |
| 一般           | CommonStates          | 默认状态。 |
| MouseOver        | CommonStates          | 鼠标指针悬停在控件上方。 |
| 已按下          | CommonStates          | 已按下控件。 |
| 已禁用         | CommonStates          | 已禁用控件。 |
| 已设定焦点          | FocusStates           | 控件有焦点。 |
| 失去焦点        | FocusStates           | 控件没有焦点。 |

通过在控件模板<xref:System.Windows.VisualStateManager?displayProperty=fullName>的根元素上定义 ， 可以在控件进入特定状态时触发动画。 声明`VisualStateManager`和<xref:System.Windows.VisualStateGroup><xref:System.Windows.VisualState>要观察的哪些组合。 当控件进入监视状态时，`VisaulStateManager`将启动 由 定义的动画。

例如，以下 XAML 代码监视`CommonStates.MouseOver`状态，为名为 的元素`backgroundElement`的填充颜色设置动画。 当控件返回到状态`CommonStates.Normal`时，将还原命名`backgroundElement`元素的填充颜色。

```xaml
<ControlTemplate x:Key="roundbutton" TargetType="Button">
    <Grid>
        <VisualStateManager.VisualStateGroups>
            <VisualStateGroup Name="CommonStates">
                <VisualState Name="Normal">
                    <ColorAnimation Storyboard.TargetName="backgroundElement"
                                    Storyboard.TargetProperty="(Shape.Fill).(SolidColorBrush.Color)"
                                    To="{TemplateBinding Background}"
                                    Duration="0:0:0.3"/>
                </VisualState>
                <VisualState Name="MouseOver">
                    <ColorAnimation Storyboard.TargetName="backgroundElement"
                                    Storyboard.TargetProperty="(Shape.Fill).(SolidColorBrush.Color)"
                                    To="Yellow"
                                    Duration="0:0:0.3"/>
                </VisualState>
            </VisualStateGroup>
        </VisualStateManager.VisualStateGroups>

        ...
```

有关情节提要的详细信息，请参阅[情节提要概述](../../framework/wpf/graphics-multimedia/storyboards-overview.md)。

## <a name="shared-resources-and-themes"></a>共享资源和主题

典型的 WPF 应用可能具有多个在整个应用中应用的 UI 资源。 总之，这组资源可以被视为应用的主题。 WPF 通过使用封装为<xref:System.Windows.ResourceDictionary>类的资源字典，支持将 UI 资源打包为主题。

WPF 主题通过使用 WPF 公开的样式和模板机制来自定义任何元素的可视化对象来定义。

WPF 主题资源存储在嵌入式资源字典中。 这些资源必须嵌入到已签名的程序集内，并且可以嵌入到与代码本身相同的程序集内或并行程序集内。 对于包含 WPF 控件的程序集，主题资源位于一系列并行程序集中。

该主题成为在搜索元素样式时最后查看的位置。 通常，搜索将首先遍走元素树以搜索适当的资源，然后查看应用资源集合，最后查询系统。 这使应用开发人员有机会在到达主题之前重新定义树或应用级别上任何对象的样式。

您可以将资源字典定义为单个文件，以便跨多个应用重用主题。 还可以通过定义多个资源字典来创建可交换的主题，这些资源字典以不同的值提供相同类型的资源。 在应用级别重新定义这些样式或其他资源是蒙皮应用的建议方法。

要跨应用共享一组资源（包括样式和模板），可以创建 XAML 文件并定义包含对<xref:System.Windows.ResourceDictionary>`shared.xaml`文件的引用。

```xaml
<ResourceDictionary.MergedDictionaries>
  <ResourceDictionary Source="Shared.xaml" />
</ResourceDictionary.MergedDictionaries>
```

它是 的`shared.xaml`共享，它本身定义了<xref:System.Windows.ResourceDictionary>包含一组样式和画笔资源的 ，使应用中的控件具有一致的外观。

有关详细信息，请参阅[合并的资源字典](../../framework/wpf/advanced/merged-resource-dictionaries.md)。

如果要为自定义控件创建主题，请参阅[控件创作概述](../../framework/wpf/controls/control-authoring-overview.md#defining-resources-at-the-theme-level)**的主题级别部分的"定义资源**"。

## <a name="see-also"></a>请参阅

- [WPF 中的 Pack URI](../../framework/wpf/app-development/pack-uris-in-wpf.md)
- [如何：查找由 ControlTemplate 生成的元素](../../framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)
- [查找数据模板生成的元素](../../framework/wpf/data/how-to-find-datatemplate-generated-elements.md)
