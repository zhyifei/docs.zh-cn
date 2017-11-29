---
title: "Expander 概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Expander
- Expander control [WPF], about Expander control
ms.assetid: 877bf425-0e54-49ec-8fd2-13a211377abb
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ff0a4432f6de8458e89132bbf46bab7568a04b60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="expander-overview"></a>Expander 概述
<xref:System.Windows.Controls.Expander>控件提供一种方法提供一个可展开的区域，它类似于一个窗口，并包含标头中的内容。  
  
  
<a name="CreatinganExpanderinXAML"></a>   
## <a name="creating-a-simple-expander"></a>创建简单的 Expander  
 下面的示例演示如何创建一个简单<xref:System.Windows.Controls.Expander>控件。 此示例将创建<xref:System.Windows.Controls.Expander>如上图所示。  
  
 [!code-xaml[ExpanderExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 <xref:System.Windows.Controls.ContentControl.Content%2A>和<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>的<xref:System.Windows.Controls.Expander>还可以包含复杂内容，如<xref:System.Windows.Controls.RadioButton>和<xref:System.Windows.Controls.Image>对象。  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>   
## <a name="setting-the-direction-of-the-expanding-content-area"></a>设置展开内容区域的方向  
 你可以设置的内容区域的<xref:System.Windows.Controls.Expander>控件中的四个方向一个展开 (<xref:System.Windows.Controls.ExpandDirection.Down>， <xref:System.Windows.Controls.ExpandDirection.Up>， <xref:System.Windows.Controls.ExpandDirection.Left>，或<xref:System.Windows.Controls.ExpandDirection.Right>) 通过使用<xref:System.Windows.Controls.ExpandDirection>属性。 当内容区域处于折叠状态，仅<xref:System.Windows.Controls.Expander><xref:System.Windows.Controls.HeaderedContentControl.Header%2A>和其切换按钮显示。 A<xref:System.Windows.Controls.Button>控件都显示方向箭头用作切换按钮以展开或折叠内容区域。 展开后，<xref:System.Windows.Controls.Expander>尝试在类似于窗口的区域中显示其所有的内容。  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>   
## <a name="controlling-the-size-of-an-expander-in-a-panel"></a>在面板中控制 Expander 的大小  
 如果<xref:System.Windows.Controls.Expander>控件是继承自的布局控件内<xref:System.Windows.Controls.Panel>，如<xref:System.Windows.Controls.StackPanel>，未指定<xref:System.Windows.FrameworkElement.Height%2A>上<xref:System.Windows.Controls.Expander>时<xref:System.Windows.Controls.Expander.ExpandDirection%2A>属性设置为<xref:System.Windows.Controls.ExpandDirection.Down>或<xref:System.Windows.Controls.ExpandDirection.Up>。 同样，未指定<xref:System.Windows.FrameworkElement.Width%2A>上<xref:System.Windows.Controls.Expander>时<xref:System.Windows.Controls.Expander.ExpandDirection%2A>属性设置为<xref:System.Windows.Controls.ExpandDirection.Left>或<xref:System.Windows.Controls.ExpandDirection.Right>。  
  
 当你将大小维度设置上<xref:System.Windows.Controls.Expander>方向，将显示的扩展的内容，控件<xref:System.Windows.Controls.Expander>控制可供内容并将显示在其周围边框的区域。 即使内容已折叠，也会显示该边框。 若要设置的扩展的内容区域的大小，请将大小维度设置上的内容<xref:System.Windows.Controls.Expander>，或者如果你希望上滚动功能，<xref:System.Windows.Controls.ScrollViewer>包含的内容。  
  
 当<xref:System.Windows.Controls.Expander>控件是中的最后一个元素<xref:System.Windows.Controls.DockPanel>，[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]自动设置<xref:System.Windows.Controls.Expander>维度为相等的其余区域<xref:System.Windows.Controls.DockPanel>。 若要防止此默认行为，设置<xref:System.Windows.Controls.DockPanel.LastChildFill%2A>属性<xref:System.Windows.Controls.DockPanel>对象传递给`false`，或请确保<xref:System.Windows.Controls.Expander>不是中的最后一个元素<xref:System.Windows.Controls.DockPanel>。  
  
<a name="CreatingScrollableContent"></a>   
## <a name="creating-scrollable-content"></a>创建可滚动内容  
 如果内容的内容区域的大小太大，您可以将包装的内容<xref:System.Windows.Controls.Expander>中<xref:System.Windows.Controls.ScrollViewer>以便提供可滚动的内容。 <xref:System.Windows.Controls.Expander>控件不会自动提供滚动功能。 下图显示<xref:System.Windows.Controls.Expander>包含控件<xref:System.Windows.Controls.ScrollViewer>控件。  
  
 **ScrollViewer 中的 Expander**  
  
 ![带有 ScrollBar 的 Expander](../../../../docs/framework/wpf/controls/media/expanderwithscrollbar.JPG "ExpanderWithScrollBar")  
  
 当你将放置<xref:System.Windows.Controls.Expander>中控制<xref:System.Windows.Controls.ScrollViewer>，将其设置<xref:System.Windows.Controls.ScrollViewer>维度属性对应的方向<xref:System.Windows.Controls.Expander>内容的大小会打开<xref:System.Windows.Controls.Expander>内容区域。 例如，如果你设置<xref:System.Windows.Controls.Expander.ExpandDirection%2A>属性<xref:System.Windows.Controls.Expander>到<xref:System.Windows.Controls.ExpandDirection.Down>（内容区域向下展开），设置<xref:System.Windows.FrameworkElement.Height%2A>属性<xref:System.Windows.Controls.ScrollViewer>控件添加到内容区域的所需高度。 如果在上内容本身，而是设置高度维度<xref:System.Windows.Controls.ScrollViewer>无法识别此设置，因此，不提供可滚动的内容。  
  
 下面的示例演示如何创建<xref:System.Windows.Controls.Expander>控件具有复杂内容且包含<xref:System.Windows.Controls.ScrollViewer>控件。 此示例将创建<xref:System.Windows.Controls.Expander>这是本部分开头图类似。  
  
 [!code-csharp[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xaml[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>   
## <a name="using-the-alignment-properties"></a>使用对齐属性  
 你可以通过设置对齐内容<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>和<xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>属性<xref:System.Windows.Controls.Expander>控件。 当设置这些属性时，对齐将同时应用于标头和展开的内容。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Controls.Expander>  
 <xref:System.Windows.Controls.ExpandDirection>  
 [操作说明主题](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
