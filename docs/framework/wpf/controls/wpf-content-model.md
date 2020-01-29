---
title: 콘텐츠 모델
ms.date: 03/30/2017
helpviewer_keywords:
- UIElement class [WPF], displaying content
- content model [WPF], controls
- controls [WPF], displaying text
- content display [WPF], controls
- controls [WPF], formatting text
- displaying content [WPF]
- arbitrary content classes [WPF], content model
- ContentControl class [WPF], displaying content
ms.assetid: 214da5ef-547a-4cf8-9b07-4aa8a0e52cdd
ms.openlocfilehash: a84ab2e66b4e373591fc9365b1c17d0bb0c66713
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738285"
---
# <a name="wpf-content-model"></a>WPF 콘텐츠 모델
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 다양한 형식의 콘텐츠를 표시하는 것을 기본 용도로 하는 많은 컨트롤 형식 및 컨트롤과 유사한 형식을 제공하는 프레젠테이션 플랫폼입니다. 사용할 컨트롤이나 파생시킬 컨트롤을 결정하려면 특정 컨트롤이 가장 잘 표시할 수 있는 개체 유형을 이해해야 합니다.  
  
 이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 형식 및 컨트롤과 비슷한 형식에 대한 콘텐츠 모델을 요약하여 보여 줍니다. 콘텐츠 모델은 컨트롤에 사용될 수 있는 컨트롤에 대해 설명합니다. 또한 이 항목에서는 각 컨트롤 모델에 대한 콘텐츠 속성을 보여 줍니다. 콘텐츠 속성은 개체의 콘텐츠를 저장하는 데 사용되는 속성입니다.  

<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a>임의의 콘텐츠가 들어 있는 클래스  
 某些控件可以包含任何类型的对象，例如字符串、<xref:System.DateTime> 对象或作为附加项的容器的 <xref:System.Windows.UIElement>。 例如，<xref:System.Windows.Controls.Button> 可以包含图像和某些文本;或 <xref:System.Windows.Controls.CheckBox> 可以包含 <xref:System.DateTime.Now%2A?displayProperty=nameWithType>的值。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 임의의 콘텐츠가 들어 있는 네 개의 클래스가 있습니다. 下表列出了从 <xref:System.Windows.Controls.Control>继承的类。  
  
|임의의 콘텐츠가 들어 있는 클래스|콘텐츠|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|임의의 단일 개체입니다.|  
|<xref:System.Windows.Controls.HeaderedContentControl>|헤더 및 단일 항목이며 둘 모두 임의의 개체입니다.|  
|<xref:System.Windows.Controls.ItemsControl>|임의 개체의 컬렉션입니다.|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|헤더와 항목 컬렉션이며 모두 임의의 개체입니다.|  
  
 이러한 클래스에서 상속하는 컨트롤은 동일한 형식의 콘텐츠를 포함하며 콘텐츠를 동일한 방식으로 처리할 수 있습니다. 下图显示了一个来自每个包含图像和文本的内容模型的控件：  
  
 ![显示四个不同控件的屏幕截图，每个内容模型一个。](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a>임의의 단일 개체가 들어 있는 컨트롤  
 <xref:System.Windows.Controls.ContentControl> 类包含一段任意内容。 它的内容属性为 <xref:System.Windows.Controls.ContentControl.Content%2A>。 以下控件从 <xref:System.Windows.Controls.ContentControl> 继承，并使用其内容模型：  
  
- <xref:System.Windows.Controls.Button>  
  
- <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
- <xref:System.Windows.Controls.CheckBox>  
  
- <xref:System.Windows.Controls.ComboBoxItem>  
  
- <xref:System.Windows.Controls.ContentControl>  
  
- <xref:System.Windows.Controls.Frame>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GroupItem>  
  
- <xref:System.Windows.Controls.Label>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Navigation.NavigationWindow>  
  
- <xref:System.Windows.Controls.RadioButton>  
  
- <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
- <xref:System.Windows.Controls.ScrollViewer>  
  
- <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
- <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
- <xref:System.Windows.Controls.ToolTip>  
  
- <xref:System.Windows.Controls.UserControl>  
  
- <xref:System.Windows.Window>  
  
 下图显示了将 <xref:System.Windows.Controls.ContentControl.Content%2A> 设置为字符串、<xref:System.DateTime> 对象、<xref:System.Windows.Shapes.Rectangle>以及包含 <xref:System.Windows.Shapes.Ellipse> 和 <xref:System.Windows.Controls.TextBlock>的 <xref:System.Windows.Controls.Panel> 的四个按钮：  
  
 ![显示具有不同内容类型的四个按钮的屏幕截图。](./media/wpf-content-model/control-content-model-buttons.png)  
  
 有关如何设置 <xref:System.Windows.Controls.ContentControl.Content%2A> 属性的示例，请参阅 <xref:System.Windows.Controls.ContentControl>。  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a>헤더와 임의의 단일 개체가 들어 있는 컨트롤  
 <xref:System.Windows.Controls.HeaderedContentControl> 类继承自 <xref:System.Windows.Controls.ContentControl> 并显示带有标头的内容。 它从 <xref:System.Windows.Controls.ContentControl> 继承 content 属性 <xref:System.Windows.Controls.ContentControl.Content%2A>，并定义类型 <xref:System.Object>的 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 属性;因此，两者都可以是任意对象。  
  
 以下控件从 <xref:System.Windows.Controls.HeaderedContentControl> 继承，并使用其内容模型：  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 下图显示了两个 <xref:System.Windows.Controls.TabItem> 的对象。 第一个 <xref:System.Windows.Controls.TabItem> 具有 <xref:System.Windows.UIElement> 对象作为 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 和 <xref:System.Windows.Controls.ContentControl.Content%2A>。 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 设置为包含 <xref:System.Windows.Shapes.Ellipse> 和 <xref:System.Windows.Controls.TextBlock>的 <xref:System.Windows.Controls.StackPanel>。 <xref:System.Windows.Controls.ContentControl.Content%2A> 设置为包含 <xref:System.Windows.Controls.TextBlock> 和 <xref:System.Windows.Controls.Label>的 <xref:System.Windows.Controls.StackPanel>。 第二个 <xref:System.Windows.Controls.TabItem> 在 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 中有一个字符串，<xref:System.Windows.Controls.TextBlock> 在 <xref:System.Windows.Controls.ContentControl.Content%2A>中。  
  
 ![在标头属性中使用不同类型的 TabControl。](./media/wpf-content-model/control-content-model-tab.png)  
  
 有关如何创建 <xref:System.Windows.Controls.TabItem> 对象的示例，请参阅 <xref:System.Windows.Controls.HeaderedContentControl>。  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a>임의 개체의 컬렉션을 포함하는 컨트롤  
 <xref:System.Windows.Controls.ItemsControl> 类继承自 <xref:System.Windows.Controls.Control>，可以包含多个项，例如字符串、对象或其他元素。 它的内容属性是 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 和 <xref:System.Windows.Controls.ItemsControl.Items%2A>。 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 通常用于填充包含数据集合的 <xref:System.Windows.Controls.ItemsControl>。 如果不想使用集合来填充 <xref:System.Windows.Controls.ItemsControl>，则可以通过使用 <xref:System.Windows.Controls.ItemsControl.Items%2A> 属性添加项。  
  
 以下控件从 <xref:System.Windows.Controls.ItemsControl> 继承，并使用其内容模型：  
  
- <xref:System.Windows.Controls.Menu>  
  
- <xref:System.Windows.Controls.Primitives.MenuBase>  
  
- <xref:System.Windows.Controls.ContextMenu>  
  
- <xref:System.Windows.Controls.ComboBox>  
  
- <xref:System.Windows.Controls.ItemsControl>  
  
- <xref:System.Windows.Controls.ListBox>  
  
- <xref:System.Windows.Controls.ListView>  
  
- <xref:System.Windows.Controls.TabControl>  
  
- <xref:System.Windows.Controls.TreeView>  
  
- <xref:System.Windows.Controls.Primitives.Selector>  
  
- <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 下图显示了包含以下类型的项的 <xref:System.Windows.Controls.ListBox>：  
  
- 문자열  
  
- <xref:System.DateTime> 개체입니다.  
  
- <xref:System.Windows.UIElement>  
  
- 包含 <xref:System.Windows.Shapes.Ellipse> 和 <xref:System.Windows.Controls.TextBlock>的 <xref:System.Windows.Controls.Panel>。  
  
 ![显示具有四种内容类型的列表框的屏幕截图。](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a>헤더와 임의 개체의 컬렉션을 포함하는 컨트롤  
 <xref:System.Windows.Controls.HeaderedItemsControl> 类继承自 <xref:System.Windows.Controls.ItemsControl>，可以包含多个项，例如字符串、对象或其他元素以及标头。 它继承 <xref:System.Windows.Controls.ItemsControl> 内容属性、<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>和 <xref:System.Windows.Controls.ItemsControl.Items%2A>，并定义可以为任意对象的 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 属性。  
  
 以下控件从 <xref:System.Windows.Controls.HeaderedItemsControl> 继承，并使用其内容模型：  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a>UIElement 개체 컬렉션을 포함하는 클래스  
 <xref:System.Windows.Controls.Panel> 类定位和排列子 <xref:System.Windows.UIElement> 对象。 它的内容属性为 <xref:System.Windows.Controls.Panel.Children%2A>。  
  
 下面的类从 <xref:System.Windows.Controls.Panel> 类继承并使用其内容模型：  
  
- <xref:System.Windows.Controls.Canvas>  
  
- <xref:System.Windows.Controls.DockPanel>  
  
- <xref:System.Windows.Controls.Grid>  
  
- <xref:System.Windows.Controls.Primitives.TabPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
- <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
- <xref:System.Windows.Controls.StackPanel>  
  
- <xref:System.Windows.Controls.VirtualizingPanel>  
  
- <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
- <xref:System.Windows.Controls.WrapPanel>  
  
 자세한 내용은 [패널 개요](panels-overview.md)를 참조하세요.  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a>UIElement의 모양에 영향을 주는 클래스  
 <xref:System.Windows.Controls.Decorator> 类将视觉效果应用于单个子 <xref:System.Windows.UIElement>或围绕单个子。 它的内容属性为 <xref:System.Windows.Controls.Decorator.Child%2A>。 以下类从 <xref:System.Windows.Controls.Decorator> 继承，并使用其内容模型：  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 下图显示了一个围绕它的 <xref:System.Windows.Controls.Border> 的 <xref:System.Windows.Controls.TextBox>。  
  
 ![검은색 테두리가 있는 TextBox](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")  
테두리가 있는 TextBlock  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a>UIElement에 대한 시각적 피드백을 제공하는 클래스  
 <xref:System.Windows.Documents.Adorner> 类向用户提供视觉提示。 例如，使用 <xref:System.Windows.Documents.Adorner> 向元素添加功能句柄，或提供有关控件的状态信息。 <xref:System.Windows.Documents.Adorner> 类提供了一个框架，以便您可以创建自己的装饰器。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 구현된 표시기를 제공하지 않습니다. 자세한 내용은 [표시기 개요](adorners-overview.md)를 참조하세요.  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a>사용자가 텍스트를 입력할 수 있는 클래스  
 WPF는 사용자가 텍스트를 입력할 수 있는 세 개의 기본 컨트롤을 제공합니다. 각 컨트롤에는 텍스트가 다르게 표시됩니다. 다음 표에서는 이 세 가지 텍스트 관련 컨트롤과 텍스트를 표시할 때의 기능 및 컨트롤 텍스트를 포함하는 속성을 보여 줍니다.  
  
|Control|텍스트 표시|콘텐츠 속성|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|일반 텍스트|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|서식 있는 텍스트|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|숨겨진 텍스트(문자가 마스킹됨)|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a>텍스트를 표시하는 클래스  
 여러 클래스를 사용하여 일반 텍스트나 서식이 지정된 텍스트를 표시할 수 있습니다. 您可以使用 <xref:System.Windows.Controls.TextBlock> 显示少量文本。 如果要显示大量文本，请使用 <xref:System.Windows.Controls.FlowDocumentReader>、<xref:System.Windows.Controls.FlowDocumentPageViewer>或 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 控件。  
  
 <xref:System.Windows.Controls.TextBlock> 具有两个内容属性： <xref:System.Windows.Controls.TextBlock.Text%2A> 和 <xref:System.Windows.Controls.TextBlock.Inlines%2A>。 如果要显示使用一致格式的文本，则 <xref:System.Windows.Controls.TextBlock.Text%2A> 属性通常是最佳选择。 如果计划在整个文本中使用不同的格式，请使用 <xref:System.Windows.Controls.TextBlock.Inlines%2A> 属性。 <xref:System.Windows.Controls.TextBlock.Inlines%2A> 属性是 <xref:System.Windows.Documents.Inline> 对象的集合，这些对象指定如何设置文本格式。  
  
 下表列出了 <xref:System.Windows.Controls.FlowDocumentReader>、<xref:System.Windows.Controls.FlowDocumentPageViewer>和 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 类的 content 属性。  
  
|Control|콘텐츠 속성|콘텐츠 속성 형식|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|문서|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|문서|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|문서|<xref:System.Windows.Documents.FlowDocument>|  
  
 <xref:System.Windows.Documents.FlowDocument> 实现 <xref:System.Windows.Documents.IDocumentPaginatorSource> 接口;因此，这三个类都可以将 <xref:System.Windows.Documents.FlowDocument> 作为内容。  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a>텍스트 서식을 지정하는 클래스  
 <xref:System.Windows.Documents.TextElement> 及其相关类允许您设置文本格式。 <xref:System.Windows.Documents.TextElement> 对象包含 <xref:System.Windows.Controls.TextBlock> 和 <xref:System.Windows.Documents.FlowDocument> 对象中的文本并设置其格式。 <xref:System.Windows.Documents.TextElement> 对象的两个主要类型是 <xref:System.Windows.Documents.Block> 元素和 <xref:System.Windows.Documents.Inline> 元素。 <xref:System.Windows.Documents.Block> 元素表示文本块，如段落或列表。 <xref:System.Windows.Documents.Inline> 元素表示块中的部分文本。 许多 <xref:System.Windows.Documents.Inline> 类指定其应用到的文本的格式设置。 每个 <xref:System.Windows.Documents.TextElement> 都有其自己的内容模型。 자세한 내용은 [TextElement 콘텐츠 모델 개요](../advanced/textelement-content-model-overview.md)를 참조하세요.  
  
## <a name="see-also"></a>另请参阅

- [고급](../advanced/index.md)
