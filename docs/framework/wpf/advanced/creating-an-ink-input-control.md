---
title: 创建墨迹输入控件
ms.date: 03/30/2017
helpviewer_keywords:
- ink strokes [WPF], managing
- managing ink strokes [WPF]
- ink input control [WPF]
- input from mouse [WPF], accepting
- mouse input [WPF], accepting
- ink [WPF], rendering
- ink strokes [WPF], collecting
- rendering ink [WPF]
- collecting ink strokes [WPF]
- DynamicRenderer objects [WPF]
- StylusPlugIn objects [WPF]
ms.assetid: c31f3a67-cb3f-4ded-af9e-ed21f6575b26
ms.openlocfilehash: b3dc71182b7553a429bb17e1888a4108ceb3e286
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541052"
---
# <a name="creating-an-ink-input-control"></a>创建墨迹输入控件
你可以创建自定义控件的动态和静态呈现墨迹。 也就是说，呈现墨迹，为用户绘制笔画，导致墨迹以显示"流"从触笔和之后显示墨迹添加到该控件，是指通过触笔从剪贴板、 粘贴或从文件加载的方式。 若要动态呈现墨迹，控件必须使用<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>。 若要以静态方式呈现墨迹，必须重写触笔事件方法 (<xref:System.Windows.UIElement.OnStylusDown%2A>， <xref:System.Windows.UIElement.OnStylusMove%2A>，和<xref:System.Windows.UIElement.OnStylusUp%2A>) 来收集<xref:System.Windows.Input.StylusPoint>数据，创建描边，并将其添加到<xref:System.Windows.Controls.InkPresenter>（呈现在控件上的墨迹）。  
  
 本主题包含以下小节：  
  
-   [如何： 收集触笔点数据和创建墨迹笔画](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
-   [如何： 使控件能够接受从鼠标输入](#EnablingYourControlToAcceptInputTromTheMouse)  
  
-   [整合在一起](#PuttingItTogether)  
  
-   [使用其他插件和 DynamicRenderers](#UsingAdditionalPluginsAndDynamicRenderers)  
  
-   [结束语](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>如何： 收集触笔点数据和创建墨迹笔画  
 若要创建的控件，收集和管理墨迹描边，请执行以下操作：  
  
1.  从派生类<xref:System.Windows.Controls.Control>或类之一派生自<xref:System.Windows.Controls.Control>，如<xref:System.Windows.Controls.Label>。  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2.  添加<xref:System.Windows.Controls.InkPresenter>到类和集<xref:System.Windows.Controls.ContentControl.Content%2A>属性设置为新<xref:System.Windows.Controls.InkPresenter>。  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3.  附加<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A>的<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>到<xref:System.Windows.Controls.InkPresenter>通过调用<xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A>方法，并添加<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>到<xref:System.Windows.UIElement.StylusPlugIns%2A>集合。 这允许<xref:System.Windows.Controls.InkPresenter>触笔接触点数据收集由控件显示墨迹。  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4.  重写 <xref:System.Windows.UIElement.OnStylusDown%2A> 方法。  在此方法，来获取调用触笔<xref:System.Windows.Input.Stylus.Capture%2A>。 通过捕获触笔，控件将以继续接收<xref:System.Windows.UIElement.StylusMove>和<xref:System.Windows.UIElement.StylusUp>事件，即使触笔离开控件的边界。 这不是绝对必需的但几乎总是需要进行良好的用户体验。 创建一个新<xref:System.Windows.Input.StylusPointCollection>收集<xref:System.Windows.Input.StylusPoint>数据。 最后，添加的初始集<xref:System.Windows.Input.StylusPoint>数据到<xref:System.Windows.Input.StylusPointCollection>。  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5.  重写<xref:System.Windows.UIElement.OnStylusMove%2A>方法并添加<xref:System.Windows.Input.StylusPoint>数据到<xref:System.Windows.Input.StylusPointCollection>前面创建的对象。  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6.  重写<xref:System.Windows.UIElement.OnStylusUp%2A>方法并创建新<xref:System.Windows.Ink.Stroke>与<xref:System.Windows.Input.StylusPointCollection>数据。 添加新<xref:System.Windows.Ink.Stroke>您创建到<xref:System.Windows.Controls.InkPresenter.Strokes%2A>集合<xref:System.Windows.Controls.InkPresenter>并释放触笔捕获。  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>如何： 使控件能够接受从鼠标输入  
 如果将前面的控件添加到你的应用程序，运行它，并使用作为输入设备的鼠标你将注意到笔画不持久。 若要保留的笔画鼠标用作输入的设备时执行以下操作：  
  
1.  重写<xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A>并创建新<xref:System.Windows.Input.StylusPointCollection>在事件发生时获取的鼠标位置并创建<xref:System.Windows.Input.StylusPoint>使用点数据，并添加<xref:System.Windows.Input.StylusPoint>到<xref:System.Windows.Input.StylusPointCollection>。  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2.  重写 <xref:System.Windows.UIElement.OnMouseMove%2A> 方法。 在事件发生时获取的鼠标位置并创建<xref:System.Windows.Input.StylusPoint>使用点数据。  添加<xref:System.Windows.Input.StylusPoint>到<xref:System.Windows.Input.StylusPointCollection>前面创建的对象。  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3.  重写 <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> 方法。  创建一个新<xref:System.Windows.Ink.Stroke>与<xref:System.Windows.Input.StylusPointCollection>数据，并添加新<xref:System.Windows.Ink.Stroke>您创建到<xref:System.Windows.Controls.InkPresenter.Strokes%2A>集合<xref:System.Windows.Controls.InkPresenter>。  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## <a name="putting-it-together"></a>整合在一起  
 下面的示例是当用户使用鼠标或笔时，收集墨迹的自定义控件。  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>使用其他插件和 DynamicRenderers  
 如 InkCanvas，自定义控件可以有自定义<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>和其他<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>对象。 将它们添加到<xref:System.Windows.UIElement.StylusPlugIns%2A>集合。 顺序<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>中的对象<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>呈现时影响墨迹的外观。 假设你有<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>调用`dynamicRenderer`和自定义<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>调用`translatePlugin`的偏移量从触笔墨迹。 如果`translatePlugin`是第一个<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>中<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>，和`dynamicRenderer`是第二个"流"墨迹将偏移量，当用户移动笔。 如果`dynamicRenderer`是第一个，和`translatePlugin`是第二个，用户提起笔之前，将不会偏移墨迹。  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## <a name="conclusion"></a>结束语  
 你可以创建能够收集和呈现墨迹通过重写触笔事件方法的控件。 通过创建您自己的控件，派生你自己<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>类，并将它们插入到<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>，可以实现数字墨迹想像几乎任何行为。 你有权<xref:System.Windows.Input.StylusPoint>作为它的数据生成，为你提供机会自定义<xref:System.Windows.Input.Stylus>输入，并根据你的应用程序屏幕上呈现其。 由于这种低级别访问<xref:System.Windows.Input.StylusPoint>数据，可以实现墨迹集合并使其以最佳性能为应用程序。  
  
## <a name="see-also"></a>请参阅  
 [高级墨迹处理](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)  
 [访问和操作笔输入](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
