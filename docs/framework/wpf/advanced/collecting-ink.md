---
title: 收集墨迹
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
ms.openlocfilehash: d441f606a577a2c0506a0f9ae510b3ea1045bba9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="collecting-ink"></a>收集墨迹
[Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) 平台会收集数字墨迹，这是其功能中的核心部分之一。 本主题讨论墨迹中 Windows Presentation Foundation (WPF) 的集合的方法。  
  
## <a name="prerequisites"></a>系统必备  
 要使用以下示例，首先必须安装 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] 和 [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]。 还必须了解如何编写 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的应用程序。 有关详细信息，有关如何开始使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，请参阅[演练： 我第一个 WPF 桌面应用程序](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)。  
  
## <a name="using-the-inkcanvas-element"></a>使用 InkCanvas 元素  
 <xref:System.Windows.Controls.InkCanvas>元素提供的最简单的方法中收集墨迹[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。 <xref:System.Windows.Controls.InkCanvas>元素是类似于[Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/microsoft.ink.inkoverlay\(v=vs.90\).aspx)对象[!INCLUDE[TLA2#tla_tpclssdk](../../../../includes/tla2sharptla-tpclssdk-md.md)]及更早版本。  
  
 使用<xref:System.Windows.Controls.InkCanvas>要接收和显示墨迹输入元素。 通常使用触笔（与数字化仪交互产生墨迹笔画）输入墨迹。 此外，还可以使用鼠标代替触笔。 创建的笔画表示为<xref:System.Windows.Ink.Stroke>对象，并且它们可以操作以编程方式和由用户输入。 <xref:System.Windows.Controls.InkCanvas>使用户能够选择、 修改或删除现有<xref:System.Windows.Ink.Stroke>。  
  
 通过使用 XAML，可以轻松设置墨迹收集，就像将 `InkCanvas` 元素添加到树中一样轻松。 下面的示例添加<xref:System.Windows.Controls.InkCanvas>为默认值[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中创建项目[!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]。  
  
 [!code-xaml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]  
  
 `InkCanvas` 元素也可以包含子元素，这样便可以将墨迹批注功能添加到几乎所有类型的 XAML 元素。 例如，若要将墨迹功能添加到文本元素中时，只需使其成为子的<xref:System.Windows.Controls.InkCanvas>。  
  
 [!code-xaml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]  
  
 同样，可轻松添加图像墨迹标记支持。  
  
 [!code-xaml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]  
  
### <a name="inkcollection-modes"></a>InkCollection 模式  
 <xref:System.Windows.Controls.InkCanvas>提供支持，对各种输入模式通过其<xref:System.Windows.Controls.InkCanvas.EditingMode%2A>属性。  
  
### <a name="manipulating-ink"></a>操作墨迹  
 <xref:System.Windows.Controls.InkCanvas>的多种墨迹编辑操作提供支持。 例如，<xref:System.Windows.Controls.InkCanvas>支持笔后擦除时需要将该功能添加到元素没有其他代码使用。  
  
#### <a name="selection"></a>选择  
 设置选择模式非常简单，只设置<xref:System.Windows.Controls.InkCanvasEditingMode>属性**选择**。 下面的代码设置的值的编辑模式<xref:System.Windows.Forms.CheckBox>:  
  
 [!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
 [!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]  
  
#### <a name="drawingattributes"></a>DrawingAttributes  
 使用<xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>属性可以更改墨迹笔画的外观。 例如，<xref:System.Windows.Ink.DrawingAttributes.Color%2A>的成员<xref:System.Windows.Ink.DrawingAttributes>设置呈现的颜色<xref:System.Windows.Ink.Stroke>。 下面的示例将所选笔画的颜色更改为红色。  
  
 [!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
 [!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]  
  
### <a name="defaultdrawingattributes"></a>DefaultDrawingAttributes  
 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>属性提供访问权限属性，例如高度、 宽度和颜色在中创建的笔画<xref:System.Windows.Controls.InkCanvas>。 一旦你更改<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>，所有将来的描边输入到<xref:System.Windows.Controls.InkCanvas>呈现所使用的新属性值。  
  
 除了修改<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>在代码隐藏文件中中,，你可以使用 XAML 语法来指定<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>属性。 下面的 XAML 代码演示如何设置<xref:System.Windows.Ink.DrawingAttributes.Color%2A>属性。 若要使用此代码，请在 Visual Studio 2005 中创建名为“HelloInkCanvas”的新 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 项目。 使用以下代码替换 Window1.xaml 文件中的代码。  
  
 [!code-xaml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]  
  
 然后，将以下按钮事件处理程序添加到 Window1 类中的代码隐藏文件。  
  
 [!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]  
  
 复制此代码后，在 Microsoft Visual Studio 2005 中按“F5”，以在调试器中运行该程序。  
  
 请注意如何<xref:System.Windows.Controls.StackPanel>放置的顶部的按钮<xref:System.Windows.Controls.InkCanvas>。 如果您尝试对墨迹上方的按钮、<xref:System.Windows.Controls.InkCanvas>收集和呈现在按钮后的墨迹。 这是因为这些按钮是同级的<xref:System.Windows.Controls.InkCanvas>而不是子级。 此外，这些按钮的 Z 顺序较高，所以墨迹呈现在其后面。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Ink.DrawingAttributes>  
 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>  
 <xref:System.Windows.Ink>
