---
title: ToolBar 概述
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: 0c66867ce4d86a11424d7a7a859817d603b4227e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="toolbar-overview"></a>ToolBar 概述
<xref:System.Windows.Controls.ToolBar> 控件是一组命令或控件，通常在功能上相关的容器。 A<xref:System.Windows.Controls.ToolBar>通常包含调用命令的按钮。  
  
  
<a name="ToolBarControl"></a>   
## <a name="toolbar-control"></a>ToolBar 控件  
 <xref:System.Windows.Controls.ToolBar>控制所采用的按钮或其他控件栏类似的排列方式到单个行或列从其名称。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> 控件提供一种溢出机制，然后放置在大小约束自然不适合任何项<xref:System.Windows.Controls.ToolBar>到特殊溢出区域。 此外， [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar>控件通常用于与相关<xref:System.Windows.Controls.ToolBarTray>控件，它为用户启动调整大小和排列的工具栏提供特殊的布局行为，以及支持。  
  
<a name="Creating_ToolBars"></a>   
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>在 ToolBarTray 中指定 ToolBar 位置  
 使用<xref:System.Windows.Controls.ToolBar.Band%2A>和<xref:System.Windows.Controls.ToolBar.BandIndex%2A>属性来定位<xref:System.Windows.Controls.ToolBar>中<xref:System.Windows.Controls.ToolBarTray>。 <xref:System.Windows.Controls.ToolBar.Band%2A> 指示在其中的位置<xref:System.Windows.Controls.ToolBar>放置在其父内<xref:System.Windows.Controls.ToolBarTray>。 <xref:System.Windows.Controls.ToolBar.BandIndex%2A> 指示的顺序<xref:System.Windows.Controls.ToolBar>放置在其带内。 下面的示例演示如何使用此属性将<xref:System.Windows.Controls.ToolBar>控件内<xref:System.Windows.Controls.ToolBarTray>。  
  
 [!code-xaml[ToolBarExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## <a name="toolbars-with-overflow-items"></a>带有溢出项的 ToolBar  
 通常<xref:System.Windows.Controls.ToolBar>控件包含的项比适合到工具栏的大小。 在此情况下，<xref:System.Windows.Controls.ToolBar>显示溢出按钮。 若要查看的溢出项，用户单击了溢出按钮和项显示在弹出窗口下面<xref:System.Windows.Controls.ToolBar>。 下图显示<xref:System.Windows.Controls.ToolBar>具有溢出项。  
  
 ![存在溢出的工具栏](../../../../docs/framework/wpf/controls/media/toolbarwithoverflowitem.png "ToolbarWithOverflowItem")  
带有溢出项的 ToolBar  
  
 你可以指定当工具栏上的项将置于溢出面板中通过设置<xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType>附加到属性<xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType>， <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>，或<xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>。 以下示例指定工具栏上的最后四个按钮应始终在溢出面板上。  
  
 [!code-xaml[ToolBarExample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 <xref:System.Windows.Controls.ToolBar>使用<xref:System.Windows.Controls.Primitives.ToolBarPanel>和<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>中其<xref:System.Windows.Controls.ControlTemplate>。  <xref:System.Windows.Controls.Primitives.ToolBarPanel>负责在工具栏上的项的布局。  <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>负责无法容纳在项的布局<xref:System.Windows.Controls.ToolBar>。 有关的示例<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.ToolBar>，请参阅  
  
 [ToolBar 样式和模板](../../../../docs/framework/wpf/controls/toolbar-styles-and-templates.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
 <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
 [设置 ToolBar 上控件的样式](../../../../docs/framework/wpf/controls/how-to-style-controls-on-a-toolbar.md)  
 [WPF 控件库示例](http://go.microsoft.com/fwlink/?LinkID=160053)
