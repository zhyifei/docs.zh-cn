---
title: Expander 概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Expander
- Expander control [WPF], about Expander control
ms.assetid: 877bf425-0e54-49ec-8fd2-13a211377abb
ms.openlocfilehash: 892d972a5704d50e91d04e05d6fdea7180a3155d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187113"
---
# <a name="expander-overview"></a>Expander 概述
控件<xref:System.Windows.Controls.Expander>提供了一种在类似于窗口且包含标头的可扩展区域中提供内容的方法。  

<a name="CreatinganExpanderinXAML"></a>
## <a name="creating-a-simple-expander"></a>创建简单的 Expander  
 下面的示例演示如何创建简单的<xref:System.Windows.Controls.Expander>控件。 此示例创建一个<xref:System.Windows.Controls.Expander>类似于上一个插图的图。  
  
 [!code-xaml[ExpanderExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 的<xref:System.Windows.Controls.ContentControl.Content%2A><xref:System.Windows.Controls.HeaderedContentControl.Header%2A>和<xref:System.Windows.Controls.Expander>也可以包含复杂的内容，如<xref:System.Windows.Controls.RadioButton>和<xref:System.Windows.Controls.Image>对象。  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>
## <a name="setting-the-direction-of-the-expanding-content-area"></a>设置展开内容区域的方向  
 可以使用 属性将<xref:System.Windows.Controls.Expander>控件的内容区域设置为以四个方向之一 （、<xref:System.Windows.Controls.ExpandDirection.Down> <xref:System.Windows.Controls.ExpandDirection.Up>、<xref:System.Windows.Controls.ExpandDirection.Left>或<xref:System.Windows.Controls.ExpandDirection.Right>） 展开。 <xref:System.Windows.Controls.ExpandDirection> 当内容区域折叠时，仅显示<xref:System.Windows.Controls.Expander><xref:System.Windows.Controls.HeaderedContentControl.Header%2A>及其切换按钮。 显示<xref:System.Windows.Controls.Button>方向箭头的控件用作切换按钮，用于展开或折叠内容区域。 展开时，<xref:System.Windows.Controls.Expander>将尝试在类似窗口的区域中显示其所有内容。  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>
## <a name="controlling-the-size-of-an-expander-in-a-panel"></a>在面板中控制 Expander 的大小  
 如果<xref:System.Windows.Controls.Expander><xref:System.Windows.Controls.Panel>控件位于继承于 （如<xref:System.Windows.Controls.StackPanel>） 的布局控件内，则在 属性<xref:System.Windows.FrameworkElement.Height%2A>设置为<xref:System.Windows.Controls.Expander><xref:System.Windows.Controls.ExpandDirection.Down>或<xref:System.Windows.Controls.ExpandDirection.Up><xref:System.Windows.Controls.Expander.ExpandDirection%2A>时，不要在 上指定 。 同样，在<xref:System.Windows.FrameworkElement.Width%2A><xref:System.Windows.Controls.Expander><xref:System.Windows.Controls.Expander.ExpandDirection%2A>将属性设置为<xref:System.Windows.Controls.ExpandDirection.Left>或<xref:System.Windows.Controls.ExpandDirection.Right>时，不要在 上指定 。  
  
 在<xref:System.Windows.Controls.Expander>控件上按展开内容的显示方向设置大小尺寸时，<xref:System.Windows.Controls.Expander>将控制内容使用的区域并在其周围显示边框。 即使内容已折叠，也会显示该边框。 要设置展开内容区域的大小，请设置 在 的内容上<xref:System.Windows.Controls.Expander>的大小尺寸，或者如果希望滚动功能，请设置<xref:System.Windows.Controls.ScrollViewer>包含内容的内容的大小尺寸。  
  
 <xref:System.Windows.Controls.Expander>当控件是 中的最后一个<xref:System.Windows.Controls.DockPanel>元素时[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]，将自动将<xref:System.Windows.Controls.Expander>维度设置为等于 的<xref:System.Windows.Controls.DockPanel>其余区域。 要<xref:System.Windows.Controls.DockPanel.LastChildFill%2A>防止此默认行为，将<xref:System.Windows.Controls.DockPanel>对象上的属性设置为`false`， 或确保<xref:System.Windows.Controls.Expander>不是 中的最后一个<xref:System.Windows.Controls.DockPanel>元素。  
  
<a name="CreatingScrollableContent"></a>
## <a name="creating-scrollable-content"></a>创建可滚动内容  
 如果内容太大，无法减小内容区域的大小，则可以将 的内容包装<xref:System.Windows.Controls.Expander>在 中<xref:System.Windows.Controls.ScrollViewer>，以便提供可滚动的内容。 该<xref:System.Windows.Controls.Expander>控件不会自动提供滚动功能。 下图显示了包含控件的<xref:System.Windows.Controls.Expander><xref:System.Windows.Controls.ScrollViewer>控件。  
  
 **ScrollViewer 中的 Expander**  
  
 ![显示带有滚动条的扩展器的屏幕截图。](./media/expander-overview/expander-scrollbar-control.jpg)  
  
 <xref:System.Windows.Controls.Expander>将控件<xref:System.Windows.Controls.ScrollViewer>放置在 中 时，设置与<xref:System.Windows.Controls.ScrollViewer><xref:System.Windows.Controls.Expander>内容打开的方向对应<xref:System.Windows.Controls.Expander>内容区域大小的维度属性。 例如，如果将<xref:System.Windows.Controls.Expander.ExpandDirection%2A>属性设置为<xref:System.Windows.Controls.Expander><xref:System.Windows.Controls.ExpandDirection.Down><xref:System.Windows.FrameworkElement.Height%2A><xref:System.Windows.Controls.ScrollViewer> 如果改为在内容本身上设置高度维度，<xref:System.Windows.Controls.ScrollViewer>则无法识别此设置，因此不提供可滚动的内容。  
  
 下面的示例演示如何创建<xref:System.Windows.Controls.Expander>包含复杂内容且包含<xref:System.Windows.Controls.ScrollViewer>控件的控件。 此示例创建类似于<xref:System.Windows.Controls.Expander>本节开头的插图的 。  
  
 [!code-csharp[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xaml[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>
## <a name="using-the-alignment-properties"></a>使用对齐属性  
 您可以通过在控件上设置 和<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A><xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>属性来<xref:System.Windows.Controls.Expander>对齐内容。 当设置这些属性时，对齐将同时应用于标头和展开的内容。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Expander>
- <xref:System.Windows.Controls.ExpandDirection>
- [如何使用主题](expander-how-to-topics.md)
