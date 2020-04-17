---
title: 在 WPF - .NET 桌面中创建模板
description: 了解如何在 Windows 演示文稿基础和 .NET Core 中创建和引用控件模板。
author: thraka
ms.author: adegeo
ms.date: 11/15/2019
no-loc:
- <Window>
- <ControlTemplate>
- <Ellipse>
- <ContentPresenter>
- <Trigger>
- <Setter>
- <PropertyTrigger>
- <Grid>
- <VisualStateManager.VisualStateGroups>
- <VisualStateGroup>
- <VisualState>
- <Storyboard>
- SizeToContent
- MinWidth
- TargetType
- Title
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.openlocfilehash: c901864d387b8de976bbfa9a9b3c14a7d5a0b4d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "81432538"
---
# <a name="create-a-template-for-a-control"></a>为控件创建模板

使用 Windows 演示文稿基础 （WPF），您可以使用自己的可重用模板自定义现有控件的可视结构和行为。 模板可以全局应用于应用程序、窗口和页面，也可以直接应用于控件。 通过为现有控件创建新模板，可以涵盖大多数需要您创建新控件的方案。

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

在本文中，您将探讨<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Button>控件创建新控件。

## <a name="when-to-create-a-controltemplate"></a>何时创建控件模板

控件具有许多属性，如<xref:System.Windows.Controls.Border.Background%2A>和<xref:System.Windows.Controls.Control.Foreground%2A>。 <xref:System.Windows.Controls.Control.FontFamily%2A> 这些属性控制控件外观的不同方面，但通过设置这些属性可以进行的更改是有限的。 例如，可以将<xref:System.Windows.Controls.Control.Foreground%2A>属性设置为蓝色，将<xref:System.Windows.Controls.Control.FontStyle%2A>属性设置为斜体。 <xref:System.Windows.Controls.CheckBox> 如果要自定义控件的外观，超出控件上其他属性设置可以执行的内容，请创建 一个<xref:System.Windows.Controls.ControlTemplate>。

在大多数用户界面中，按钮具有相同的常规外观：带有某些文本的矩形。 如果要创建圆角按钮，可以创建从按钮继承的新控件或重新创建按钮的功能。 此外，新的用户控件将提供圆形视觉对象。

通过自定义现有控件的可视布局，可以避免创建新控件。 使用圆角按钮，创建<xref:System.Windows.Controls.ControlTemplate>具有所需可视布局的 。

另一方面，如果需要具有新功能、不同属性和新设置的控件，则可以创建新<xref:System.Windows.Controls.UserControl>的 。

## <a name="prerequisites"></a>先决条件

创建新的 WPF 应用程序，并在*MainWindow.xaml（* 或您选择的其他窗口）中设置**\<窗口>** 元素上的以下属性：

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

将**\<窗口>** 元素的内容设置为以下 XAML：

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

最后 *，MainWindow.xaml*文件应类似于以下内容：

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

如果运行该应用程序，它如下所示：

![带两个未样式按钮的 WPF 窗口](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a>创建 ControlTemplate

声明<xref:System.Windows.Controls.ControlTemplate>的最常见方法是作为 XAML 文件中`Resources`的节中的资源。 由于模板是资源，因此它们遵循适用于所有资源的相同范围规则。 简单地说，声明模板的位置会影响模板的应用位置。 例如，如果在应用程序定义 XAML 文件的根元素中声明模板，则可以在应用程序中的任何位置使用该模板。 如果在窗口中定义模板，则只有该窗口中的控件可以使用该模板。

首先，向`Window.Resources`*MainWindow.xaml*文件添加元素：

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

使用以下属性集创建新**\<的 ControlTemplate>：**

|     |     |
| --- | --- |
| **x:Key**         | `roundbutton` |
| **TargetType**    | `Button` |

此控件模板非常简单：

- 控件的根元素，<xref:System.Windows.Controls.Grid>
- 绘制<xref:System.Windows.Shapes.Ellipse>按钮的圆舍入外观
- a<xref:System.Windows.Controls.ContentPresenter>以显示用户指定的按钮内容

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a>TemplateBinding

创建新 时<xref:System.Windows.Controls.ControlTemplate>，仍可能仍要使用公共属性来更改控件的外观。 [模板绑定](../../framework/wpf/advanced/templatebinding-markup-extension.md)标记扩展将 元素的属性绑定<xref:System.Windows.Controls.ControlTemplate>到由控件定义的公共属性。 使用[模板绑定](../../framework/wpf/advanced/templatebinding-markup-extension.md)时，将启用控件上的属性作为模板的参数。 换言之，设置控件属性后，该值将传递到包含 [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) 的元素。

### <a name="ellipse"></a>椭圆形

**:::no-loc text="Fill":::** 请注意**:::no-loc text="Stroke":::**，<xref:System.Windows.Controls.Control.Foreground>**\<椭圆>** 元素的 和 属性绑定到控件和<xref:System.Windows.Controls.Control.Background>属性。

### <a name="contentpresenter"></a>ContentPresenter

内容演示者>元素也会添加到模板中。 [ \<](xref:System.Windows.Controls.ContentPresenter) 由于此模板是为按钮设计的，因此，考虑到该按钮从<xref:System.Windows.Controls.ContentControl>继承。 该按钮显示元素的内容。 您可以在按钮内设置任何内容，例如纯文本或其他控件。 以下两个按钮均为有效按钮：

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

在前面的两个示例中，文本和复选框都设置为[Button.Content](xref:System.Windows.Controls.ContentControl.Content)属性。 任何设置为内容的内容都可以通过**\<ContentPresenter>**（即模板）显示，这是模板的作用。

如果 应用于<xref:System.Windows.Controls.ContentControl>类型（如 ，`Button`如 元素树中搜索 。 <xref:System.Windows.Controls.ContentPresenter> <xref:System.Windows.Controls.ControlTemplate> 如果找到`ContentPresenter`，模板将自动将控件的属性<xref:System.Windows.Controls.ContentControl.Content>绑定到 。 `ContentPresenter`

## <a name="use-the-template"></a>使用模板

查找本文开头声明的按钮。

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

将第二个按钮的属性<xref:System.Windows.Controls.Control.Template>设置为`roundbutton`资源：

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

如果运行项目并查看结果，您将看到该按钮具有圆润的背景。

![带一个模板椭圆形按钮的 WPF 窗口](media/create-apply-template/styled-button.png)

您可能已经注意到该按钮不是圆，而是偏斜的。 由于**\<椭圆>** 元素的工作方式，它总是展开以填充可用空间。 通过将按钮**:::no-loc text="width":::** 和**:::no-loc text="height":::** 属性更改为相同的值，使圆均匀：

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![带一个模板圆形按钮的 WPF 窗口](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a>添加触发器

即使应用了模板的按钮看起来不同，它的外观与任何其他按钮相同。 如果按下该按钮，事件将<xref:System.Windows.Controls.Primitives.ButtonBase.Click>触发。 但是，您可能已经注意到，当您将鼠标移到按钮上时，按钮的视觉效果不会更改。 这些可视化交互都由模板定义。

使用 WPF 提供的动态事件和属性系统，可以监视值的特定属性，然后在适当的时候重新设置模板的样式。 在此示例中，您将观看按钮的属性<xref:System.Windows.UIElement.IsMouseOver>。 当鼠标位于控件上时，使用新颜色对**\<椭圆>** 进行样式设置。 这种类型的触发器称为*属性触发器*。

为此，您需要向**\<椭圆>** 添加一个名称，以便参考。 给它的背景**元素**的名称。

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

接下来，<xref:System.Windows.Trigger>向[控件模板.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers)集合添加新。 触发器将监视值`IsMouseOver``true`的事件。

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

接下来，将**\<setter>** 添加到**\<将****\<椭圆>** 的**填充**属性更改为新颜色的触发器>。

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

运行该项目。 请注意，当您将鼠标移到按钮上时，**\<椭圆的颜色>** 更改。

![鼠标在 WPF 按钮上移动以更改填充颜色](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a>使用可视状态

可视状态由控件定义和触发。 例如，当鼠标移动到控件的顶部时，`CommonStates.MouseOver`将触发状态。 您可以根据控件的当前状态为属性更改设置动画。 在上一`AliceBlue``IsMouseOver``true`**\<节中，属性触发器>** 用于将按钮的前景更改为 属性为 时。 相反，创建一个可视状态，为更改此颜色设置动画，从而提供平滑过渡。 有关 Visual*状态*的详细信息，请参阅[WPF 中的样式和模板](../fundamentals/styles-templates-overview.md#visual-states)。

要将**\<属性触发>** 转换为动画视觉状态，首先，请从模板中删除**\<ControlTemplate.Trigger>** 元素。

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

接下来，在**\<控件模板的网格>** 根中，添加**\<VisualStateManager.VisualStateGroup>** 元素，该元素具有**\<VisualStateGroup** `CommonStates`>。 定义两种状态`Normal`，`MouseOver`和 。

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

触发**\<该**状态时，将应用 VisualState>中定义的任何动画。 为每个状态创建动画。 动画放在**\<情节提要>** 元素的内。 有关情节提要的详细信息，请参阅[情节提要概述](../../framework/wpf/graphics-multimedia/storyboards-overview.md)。

- 一般

  此状态为椭圆填充设置动画，将其还原到控件`Background`的颜色。

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- MouseOver

  此状态将椭圆`Background`颜色动画为新颜色： `Yellow`。

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

控件模板>现在应如下所示。 ** \<**

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

运行该项目。 请注意，当您将鼠标移到按钮上时，**\<椭圆的颜色>** 动画。

![鼠标在 WPF 按钮上移动以更改填充颜色](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a>后续步骤

- [为 WPF 中的控件创建样式](../fundamentals/styles-templates-create-apply-style.md)
- [WPF 中的样式和模板](../fundamentals/styles-templates-overview.md)
- [XAML 资源概述](../fundamentals/xaml-resources-define.md)
