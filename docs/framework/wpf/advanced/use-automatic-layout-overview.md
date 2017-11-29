---
title: "使用自动布局概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c9f5b9a6665778bc313febb039aeeeb2e484a6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="use-automatic-layout-overview"></a>使用自动布局概述
本主题介绍有关如何编写的开发人员准则[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]具有可本地化的应用程序[!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)]。 在过去的本地化[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]是一个耗时的过程。 每种语言，[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]必需的按像素调整改写。 使用适当的设计和编码标准，今日[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]可以用来构造，因此，本地化人员必须小于调整大小和重新定位的工作量。 编写的应用程序可以更轻松地调整大小和重新定位到方法调用自动布局，并可以通过使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序设计。  
  
<a name="advantages_of_autolayout"></a>   
## <a name="advantages-of-using-automatic-layout"></a>使用自动布局的优点  
 因为[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]演示系统非常强大且灵活，它提供的应用程序可以进行调整以适应不同的语言要求中的布局元素的功能。 下面列出自动布局的部分优点。  
  
-   [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 可通过任意语言正常显示。  
  
-   减少了文本转换完后重新调整控件位置和大小的需要。  
  
-   减少了重新调整窗口大小的需要。  
  
-   [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 布局可通过任意语言正确呈现。  
  
-   本地化过程可缩减为与进行字符串转换差不多。  
  
<a name="autolayout_controls"></a>   
## <a name="automatic-layout-and-controls"></a>自动布局和控件  
 利用自动布局，应用程序可以自动调整控件大小。 例如，控件可按字符串长度相应改变。 利用此功能，本地化人员可转换字符串，而无需再调整控件大小以适应转换后的文本。 下面的示例创建一个带有英文内容的按钮。  
  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 在此示例中，只需更改文本即可生成一个西班牙文按钮。 例如，  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 下图显示代码示例的输出。  
  
 ![具有不同语言的文本的同一按钮](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
自动调整大小的按钮  
  
<a name="autolayout_coding"></a>   
## <a name="automatic-layout-and-coding-standards"></a>自动布局和编码标准  
 使用自动布局方法需要一套编码和设计标准和规则以生成完全可本地化[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 下列准则可帮助完成自动布局编码。  
  
|编码标准|描述|  
|----------------------|-----------------|  
|不使用绝对位置。|-不要使用<xref:System.Windows.Controls.Canvas>因为它绝对定位元素。<br />-使用<xref:System.Windows.Controls.DockPanel>， <xref:System.Windows.Controls.StackPanel>，和<xref:System.Windows.Controls.Grid>定位控件。<br />-有关各种类型的面板的讨论，请参见[面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)。|  
|不设定固定的窗口大小。|-使用<xref:System.Windows.Window.SizeToContent%2A>。<br />- 例如：<br /><br /> [!code-xaml[LocalizationGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]|  
|添加一个 <xref:System.Windows.FrameworkElement.FlowDirection%2A>。|<ul><li>添加<xref:System.Windows.FrameworkElement.FlowDirection%2A>到你的应用程序的根元素。</li><li>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供一种支持水平、双向和垂直布局的简便方式。 在演示文稿 framework 中，<xref:System.Windows.FrameworkElement.FlowDirection%2A>属性可以用于定义布局。 流方向模式包括：<br /><br /> <ul><li><xref:System.Windows.FlowDirection.LeftToRight>(LrTb)-水平布局 Latin、 东亚语言等。</li><li><xref:System.Windows.FlowDirection.RightToLeft>(RlTb)-阿拉伯语、 希伯来语等双向。</li></ul></li></ul>|  
|使用复合字体而不是实体字体。|<ul><li>使用复合字体<xref:System.Windows.Controls.Control.FontFamily%2A>属性不需要进行本地化。</li><li>开发人员可以使用以下字体之一，也可以创建自己的字体。<br /><br /> <ul><li>Global User Interface</li><li>Global San Serif</li><li>Global Serif</li></ul></li></ul>|  
|添加 xml:lang。|添加`xml:lang`属性中的根元素你[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，如`xml:lang="en-US"`英文应用程序。<br />-因为复合字体使用`xml:lang`若要确定要使用的字体，设置此属性以支持多语言的方案。|  
  
<a name="autolay_grids"></a>   
## <a name="automatic-layout-and-grids"></a>自动布局和网格  
 <xref:System.Windows.Controls.Grid>元素，是用于自动布局，因为它使开发人员来定位元素。 A<xref:System.Windows.Controls.Grid>控件是支持的分发在其子元素，使用为列和行的排列中的可用空间。 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]元素可以跨多个单元格，并且可能具有在网格内的网格。 网格很有用，因为它们使你可以创建和位置复杂[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 下面的示例演示使用网格来定位某些按钮和文本。 请注意的高度和宽度的单元格设置为<xref:System.Windows.GridUnitType.Auto>; 因此，包含图像的按钮的单元格调整以适合图像。  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 下图显示了以上代码生成的网格。  
  
 ![网格示例](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")  
Grid  
  
<a name="autolay_grids_issharedsizescope"></a>   
## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a>使用 IsSharedSizeScope 属性的自动布局和网格  
 A<xref:System.Windows.Controls.Grid>元素是可本地化的应用程序来创建调整为适应内容的控件中有用。 不过，有时可能希望控件无论包含什么内容都可以保持特定大小。 例如，对于“确定”、“取消”和“浏览”按钮，可能不希望按钮根据内容调整大小。 在这种情况下<xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType>附加的属性可用于共享在多个网格元素之间同样的大小。 下面的示例演示如何共享列和行的大小调整数据之间多个<xref:System.Windows.Controls.Grid>元素。  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 **请注意**完整的代码示例，请参阅[共享大小调整属性之间网格](../../../../docs/framework/wpf/controls/how-to-share-sizing-properties-between-grids.md)  
  
## <a name="see-also"></a>另请参阅  
 [WPF 全球化](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)  
 [使用自动布局创建按钮](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)  
 [使用网格进行自动布局](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
