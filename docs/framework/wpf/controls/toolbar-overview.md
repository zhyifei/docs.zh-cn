---
title: ToolBar 概述
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: 460d4420d5faf849a8d05a94e0170aea384f69b4
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452690"
---
# <a name="toolbar-overview"></a>ToolBar 概述
<xref:System.Windows.Controls.ToolBar> 控件是通常在函数中相关的一组命令或控件的容器。 <xref:System.Windows.Controls.ToolBar> 通常包含用于调用命令的按钮。  

<a name="ToolBarControl"></a>   
## <a name="toolbar-control"></a>ToolBar 控件  
 <xref:System.Windows.Controls.ToolBar> 控件将其名称从按钮或其他控件的条形图排列为单个行或列。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> 控件提供了一种溢出机制，该机制会将大小不适当的任何项放在大小受限的 <xref:System.Windows.Controls.ToolBar> 中。 此外，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> 控件通常与相关 <xref:System.Windows.Controls.ToolBarTray> 控件一起使用，后者提供了特殊的布局行为，并支持用户启动的工具栏大小调整和排列。  
  
<a name="Creating_ToolBars"></a>   
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>在 ToolBarTray 中指定 ToolBar 位置  
 使用 "<xref:System.Windows.Controls.ToolBar.Band%2A>" 和 "<xref:System.Windows.Controls.ToolBar.BandIndex%2A>" 属性将 <xref:System.Windows.Controls.ToolBar> 放置在 <xref:System.Windows.Controls.ToolBarTray>中。 <xref:System.Windows.Controls.ToolBar.Band%2A> 指示 <xref:System.Windows.Controls.ToolBar> 在其父 <xref:System.Windows.Controls.ToolBarTray>内的位置。 <xref:System.Windows.Controls.ToolBar.BandIndex%2A> 指示 <xref:System.Windows.Controls.ToolBar> 在其带区内的位置顺序。 下面的示例演示如何使用此属性在 <xref:System.Windows.Controls.ToolBarTray>中放置 <xref:System.Windows.Controls.ToolBar> 控件。  
  
 [!code-xaml[ToolBarExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## <a name="toolbars-with-overflow-items"></a>带有溢出项的 ToolBar  
 通常 <xref:System.Windows.Controls.ToolBar> 控件包含的项多于工具栏大小可容纳的项。 发生这种情况时，<xref:System.Windows.Controls.ToolBar> 会显示溢出按钮。 若要查看溢出项，用户单击溢出按钮，项将显示在 <xref:System.Windows.Controls.ToolBar>下面的弹出窗口中。 下图显示了具有溢出项的 <xref:System.Windows.Controls.ToolBar>：  
  
 ![显示具有溢出项的工具栏的屏幕截图。](./media/toolbar-overview/toolbar-overflow-items.png)  
  
 可以通过将 <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> 附加属性设置为 <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType>、<xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>或 <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>来指定工具栏上的项放置在溢出面板上的时间。 以下示例指定工具栏上的最后四个按钮应始终在溢出面板上。  
  
 [!code-xaml[ToolBarExample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 <xref:System.Windows.Controls.ToolBar> 在其 <xref:System.Windows.Controls.ControlTemplate>中使用 <xref:System.Windows.Controls.Primitives.ToolBarPanel> 和 <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>。  <xref:System.Windows.Controls.Primitives.ToolBarPanel> 负责工具栏上项的布局。  <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> 负责 <xref:System.Windows.Controls.ToolBar>上无法容纳的项的布局。 有关 <xref:System.Windows.Controls.ToolBar><xref:System.Windows.Controls.ControlTemplate> 的示例，请参阅  
  
 [ToolBar 样式和模板](toolbar-styles-and-templates.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Primitives.ToolBarPanel>
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>
- [设置 ToolBar 上控件的样式](how-to-style-controls-on-a-toolbar.md)
- [WPF 控件库示例](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
