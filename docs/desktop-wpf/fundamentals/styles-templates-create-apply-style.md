---
title: 为控件创建样式
description: 了解如何在 Windows 演示文稿基础和 .NET Core 中创建和引用控件样式。
author: thraka
ms.author: adegeo
ms.date: 09/12/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: 2956dbf93a1d34feca31d3ab10536f5089010189
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2019
ms.locfileid: "81432556"
---
# <a name="create-a-style-for-a-control-in-wpf"></a>为 WPF 中的控件创建样式

使用 Windows 演示文稿基础 （WPF），您可以使用自己的可重用样式自定义现有控件的外观。 样式可以全局应用于你的应用、窗口和页面，也可以直接应用于控件。

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="create-a-style"></a>创建样式

可以将 a<xref:System.Windows.Style>视为将一组属性值应用于一个或多个元素的便捷方法。 <xref:System.Windows.FrameworkElement>可以在派生自<xref:System.Windows.FrameworkContentElement>或 或<xref:System.Windows.Window>或 的任何元素上使用样式。 <xref:System.Windows.Controls.Button>

声明样式的最常见方法是作为 XAML 文件中`Resources`部分中的资源。 因为样式是资源，因此它们遵循适用于所有资源的相同范围规则。 简单地说，声明样式会影响样式的应用位置。 例如，如果在应用定义 XAML 文件的根元素中声明样式，则可以在应用中的任意位置使用该样式。

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/App.xaml#AppResources)]

如果在应用的 XAML 文件中声明样式，则该样式只能在该 XAML 文件中使用。 有关资源的范围规则的详细信息，请参阅 [XAML 资源](xaml-resources-define.md)。

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowSingleResource.xaml#WindowResources)]

样式由`<Setter>`子元素组成，这些子元素在样式应用的元素上设置属性。 在上面的示例中，请注意样式设置为应用于`TextBlock`通过属性的类型。 `TargetType` <xref:System.Windows.Controls.Control.FontSize%2A>样式将`15`设置为 和<xref:System.Windows.Controls.Control.FontWeight%2A>。 `ExtraBold` 为每个属性`<Setter>`添加 样式更改的 。

## <a name="apply-a-style-implicitly"></a>隐式应用样式

A<xref:System.Windows.Style>是一种将一组属性值应用于多个元素的便捷方法。 例如，请考虑以下<xref:System.Windows.Controls.TextBlock>元素及其在窗口中的默认外观。

[!code-xaml[TextBlocks](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetTextBlocks)]

![样式示例屏幕截图](./media/styles-and-templates-overview/stylingintro-textblocksbefore.png "StylingIntro_TextBlocksBefore")

可以通过直接在每个<xref:System.Windows.Controls.Control.FontSize%2A><xref:System.Windows.Controls.Control.FontFamily%2A><xref:System.Windows.Controls.TextBlock>元素上设置属性（如 和 ，）来更改默认外观。 但是，如果您希望<xref:System.Windows.Controls.TextBlock>元素共享某些属性，则可以在 XAML 文件<xref:System.Windows.Style>`Resources`部分中创建 a，如下所示。

[!code-xaml[DefaultTextBlockStyle](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetDefaultTextBlockStyle)]

将<xref:System.Windows.Style.TargetType%2A>样式设置为<xref:System.Windows.Controls.TextBlock>类型并省略`x:Key`属性时，该样式将应用于范围为样式的所有<xref:System.Windows.Controls.TextBlock>元素，该元素通常是 XAML 文件本身。

现在元素<xref:System.Windows.Controls.TextBlock>如下所示。

![样式示例屏幕截图](./media/styles-and-templates-overview/stylingintro-textblocksbasestyle.png "StylingIntro_TextBlocksBaseStyle")

## <a name="apply-a-style-explicitly"></a>显式应用样式

如果向样式添加`x:Key`具有值的属性，则该样式将不再隐式应用于<xref:System.Windows.Style.TargetType%2A>的所有元素。 只有显式引用样式的元素才会应用样式。

下面是上一节中的样式，但使用 属性`x:Key`声明。

[!code-xaml[ExplicitStyleDeclare](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleDeclare)]

要应用样式，请使用<xref:System.Windows.FrameworkElement.Style%2A>[StaticResource 标记扩展](../../framework/wpf/advanced/staticresource-markup-extension.md)将元素`x:Key`上的属性设置为值，如下所示。

[!code-xaml[ExplicitStyleReference](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleReference)]

请注意，第一<xref:System.Windows.Controls.TextBlock>个元素的样式应用于它，而第二个 TextBlock 元素保持不变。 上一节的隐式样式已更改为声明`x:Key`属性的样式，这意味着受该样式影响的唯一元素是直接引用该样式的元素。

![样式示例屏幕截图](./media/styles-and-templates-overview/create-a-style-explicit-textblock.png "创建样式-显式文本块")

一旦显式或隐式应用样式，它就会密封，并且无法更改。 如果要更改已应用的样式，请创建新样式以替换现有样式。 有关更多信息，请参见 <xref:System.Windows.Style.IsSealed%2A> 属性。

可以创建一个根据自定义逻辑选择要应用的样式的对象。 例如，请参阅为<xref:System.Windows.Controls.StyleSelector>类提供的示例。

## <a name="apply-a-style-programmatically"></a>以编程方式应用样式

要以编程方式将命名样式分配给元素，请从资源集合中获取样式并将其分配给元素的属性<xref:System.Windows.FrameworkElement.Style%2A>。 资源集合中的项的类型<xref:System.Object>为 。 因此，在将其分配给属性之前，必须将检索<xref:System.Windows.Style?displayProperty=fullName>的样式转换为 。 `Style` 例如，以下代码设置对定义的样式`TextBlock``textblock1``TitleText`命名的样式。

[!code-csharp[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml.cs#SnippetSetStyleCode)]
[!code-vb[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/MainWindow.xaml.vb#SnippetSetStyleCode)]

## <a name="extend-a-style"></a>扩展样式

您可能希望两个<xref:System.Windows.Controls.TextBlock>元素共享一些属性值，例如<xref:System.Windows.Controls.Control.FontFamily%2A>和 中位<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>。 但是，您还希望文本 **"我的图片"** 具有一些其他属性。 可以通过创建基于第一种样式的新样式来执行此操作，如下所示。

[!code-xaml[DefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

[!code-xaml[TextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

此`TextBlock`样式现在居中，使用大小`Comic Sans MS`为 的`26`字体，前景颜色设置为示例中<xref:System.Windows.Media.LinearGradientBrush>所示。 请注意，它覆盖基本样式<xref:System.Windows.Controls.Control.FontSize%2A>的值。 如果有多个<xref:System.Windows.Setter>指向 中的同一<xref:System.Windows.Style>属性，则最后声明的 将`Setter`优先。

下面显示了<xref:System.Windows.Controls.TextBlock>元素现在的外观：

![带样式的 TextBlock](./media/styles-and-templates-overview/stylingintro-textblocks.png "StylingIntro_TextBlocks")

此`TitleText`样式扩展为<xref:System.Windows.Controls.TextBlock>类型创建的样式，该样式引用于`BasedOn="{StaticResource {x:Type TextBlock}}"`。 还可以通过使用`x:Key`的 样式扩展具有`x:Key`的样式。 例如，如果有一个样式命名`Header1`，并且要扩展该样式，则可以使用 。 `BasedOn="{StaticResource Header1}"`

## <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>目标类型属性和 x：键属性的关系

如<xref:System.Windows.Style.TargetType%2A>前所示，`TextBlock`在不分配样式的情况下将属性设置为 ，`x:Key`会导致将样式应用于所有<xref:System.Windows.Controls.TextBlock>元素。 在此情况下，`x:Key` 隐式设置为 `{x:Type TextBlock}`。 `x:Key`这意味着，如果显式将值设置为`{x:Type TextBlock}`以外的任何内容，<xref:System.Windows.Style>则 不会自动应用于所有`TextBlock`元素。 相反，必须显式将样式（通过使用`x:Key`值）应用于`TextBlock`元素。 如果样式位于资源部分，并且未在样式上设置`TargetType`属性，则必须设置该`x:Key`属性。

除了为`x:Key`提供默认值外，`TargetType`属性还指定 setter 属性应用于的类型。 如果不指定 ，`TargetType`则必须使用 语法<xref:System.Windows.Setter>`Property="ClassName.Property"`限定对象中的属性与类名称。 例如`Property="FontSize"`，必须设置为<xref:System.Windows.Setter.Property%2A>`"TextBlock.FontSize"`或`"Control.FontSize"`，而不是设置 。

另请注意，许多 WPF 控件由其他 WPF 控件的组合组成。 如果创建应用于某个类型的所有控件的样式，可能会产生意外结果。 例如，如果创建以<xref:System.Windows.Controls.TextBlock>中的类型<xref:System.Windows.Window>为目标的样式，则该样式将应用于窗口中的所有`TextBlock`控件，即使 是`TextBlock`另一个控件的一<xref:System.Windows.Controls.ListBox>部分（如 。

## <a name="see-also"></a>请参阅

<!-- - [Create a style for a control](styles-templates-create-apply-template.md) -->
- [XAML 资源概述](xaml-resources-define.md)
- [XAML 概述（WPF & .NET 核心）](xaml.md)
