---
title: ToolBar 概述
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: b5498b8b88c7403ffe51256a57544261de3ace08
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186618"
---
# <a name="toolbar-overview"></a>ToolBar 概述
<xref:System.Windows.Controls.ToolBar>控件是一组命令或控件的容器，这些命令或控件通常与其功能相关。 通常<xref:System.Windows.Controls.ToolBar>包含调用命令的按钮。  

<a name="ToolBarControl"></a>
## <a name="toolbar-control"></a>ToolBar 控件  
 控件<xref:System.Windows.Controls.ToolBar>将其名称从类似条形的按钮或其他控件排列到单个行或列中。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.ToolBar>控件提供溢出机制，将任何不自然适合在大小约束<xref:System.Windows.Controls.ToolBar>中的项放入特殊溢出区域。 此外，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.ToolBar>控件通常与相关<xref:System.Windows.Controls.ToolBarTray>控件一起使用，后者提供特殊的布局行为，并支持用户启动的工具栏大小调整和排列。  
  
<a name="Creating_ToolBars"></a>
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>在 ToolBarTray 中指定 ToolBar 位置  
 使用<xref:System.Windows.Controls.ToolBar.Band%2A>和<xref:System.Windows.Controls.ToolBar.BandIndex%2A>属性将<xref:System.Windows.Controls.ToolBar>放置在<xref:System.Windows.Controls.ToolBarTray>中。 <xref:System.Windows.Controls.ToolBar.Band%2A>指示 放置在其父<xref:System.Windows.Controls.ToolBar><xref:System.Windows.Controls.ToolBarTray>项 中的位置。 <xref:System.Windows.Controls.ToolBar.BandIndex%2A>指示 在其波段中放置<xref:System.Windows.Controls.ToolBar>的顺序。 下面的示例演示如何使用此属性将控件放置在<xref:System.Windows.Controls.ToolBar>中。 <xref:System.Windows.Controls.ToolBarTray>  
  
 [!code-xaml[ToolBarExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>
## <a name="toolbars-with-overflow-items"></a>带有溢出项的 ToolBar  
 控件<xref:System.Windows.Controls.ToolBar>包含的项目数通常超过工具栏大小。 发生这种情况时，<xref:System.Windows.Controls.ToolBar>将显示溢出按钮。 要查看溢出项，用户单击溢出按钮，这些项目将显示在 下面的弹出窗口中<xref:System.Windows.Controls.ToolBar>。 下图显示了具有溢出项<xref:System.Windows.Controls.ToolBar>的：  
  
 ![显示具有溢出项的工具栏的屏幕截图。](./media/toolbar-overview/toolbar-overflow-items.png)  
  
 通过将<xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType>附加属性<xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType><xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>设置为 或，可以指定工具栏上的项何时放置在溢出面板上。 <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType> 以下示例指定工具栏上的最后四个按钮应始终在溢出面板上。  
  
 [!code-xaml[ToolBarExample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 中的<xref:System.Windows.Controls.ToolBar>使用<xref:System.Windows.Controls.Primitives.ToolBarPanel>和<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>在其<xref:System.Windows.Controls.ControlTemplate>中 。  <xref:System.Windows.Controls.Primitives.ToolBarPanel>负责工具栏上项的布局。  <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>负责不适合 的项的布局<xref:System.Windows.Controls.ToolBar>。 有关 的 。 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.ToolBar>  
  
 [ToolBar 样式和模板](toolbar-styles-and-templates.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Primitives.ToolBarPanel>
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>
- [设置 ToolBar 上的控件的样式](how-to-style-controls-on-a-toolbar.md)
- [WPF 控件库示例](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
