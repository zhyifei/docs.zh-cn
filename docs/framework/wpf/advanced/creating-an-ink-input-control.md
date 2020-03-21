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
ms.openlocfilehash: 394318488b0afb8e043389e0abc3f51dce8604c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186284"
---
# <a name="creating-an-ink-input-control"></a>创建墨迹输入控件
您可以创建动态和静态渲染墨迹的自定义控件。 也就是说，在用户绘制笔画时渲染墨迹，导致墨迹从 Tablet 笔中显示为"流"，并在墨迹添加到控件后显示墨迹，通过 Tablet 笔、从剪贴板粘贴或从文件加载。 要动态渲染墨迹，控件必须使用<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>。 要静态渲染墨迹，必须重写手写笔事件方法<xref:System.Windows.UIElement.OnStylusDown%2A>（和<xref:System.Windows.UIElement.OnStylusMove%2A> <xref:System.Windows.UIElement.OnStylusUp%2A>） 以收集数据<xref:System.Windows.Input.StylusPoint>、创建描边并将它们添加到 （<xref:System.Windows.Controls.InkPresenter>该方法在控件上呈现墨迹）。  
  
 本主题包含以下小节：  
  
- [如何：收集手写笔点数据并创建墨迹描边](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
- [如何：使控件接受来自鼠标的输入](#EnablingYourControlToAcceptInputTromTheMouse)  
  
- [综合运用](#PuttingItTogether)  
  
- [使用其他插件和动态渲染器](#UsingAdditionalPluginsAndDynamicRenderers)  
  
- [结论](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>如何：收集手写笔点数据并创建墨迹描边  
 要创建收集和管理墨迹描边的控件，请执行以下操作：  
  
1. 派生来自<xref:System.Windows.Controls.Control>或 派生自<xref:System.Windows.Controls.Control>的类之一，<xref:System.Windows.Controls.Label>例如 。  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. 将<xref:System.Windows.Controls.InkPresenter>add 添加到 类<xref:System.Windows.Controls.ContentControl.Content%2A>并将 属性设置为<xref:System.Windows.Controls.InkPresenter>新 。  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. <xref:System.Windows.Controls.InkPresenter>通过调用<xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A>方法将<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer><xref:System.Windows.UIElement.StylusPlugIns%2A><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A>的 将 的<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>附加到 ，并将 添加到集合中。 这允许 在<xref:System.Windows.Controls.InkPresenter>控件收集手写笔点数据时显示墨迹。  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. 重写 <xref:System.Windows.UIElement.OnStylusDown%2A> 方法。  在此方法中，使用 调用<xref:System.Windows.Input.Stylus.Capture%2A>捕获手写笔。 通过捕获手写笔，即使手写笔离开控件的边界，您的控件仍<xref:System.Windows.UIElement.StylusMove>将继续<xref:System.Windows.UIElement.StylusUp>接收和事件。 这不是严格的强制性，但几乎总是需要良好的用户体验。 创建新数据<xref:System.Windows.Input.StylusPointCollection>以收集数据<xref:System.Windows.Input.StylusPoint>。 最后，将初始数据集<xref:System.Windows.Input.StylusPoint>添加到 。 <xref:System.Windows.Input.StylusPointCollection>  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. 重写<xref:System.Windows.UIElement.OnStylusMove%2A>方法并将<xref:System.Windows.Input.StylusPoint>数据添加到之前创建<xref:System.Windows.Input.StylusPointCollection>的对象。  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. 重写方法<xref:System.Windows.UIElement.OnStylusUp%2A>，使用<xref:System.Windows.Ink.Stroke><xref:System.Windows.Input.StylusPointCollection>数据创建新数据。 将您创建<xref:System.Windows.Ink.Stroke>的新样式添加到<xref:System.Windows.Controls.InkPresenter.Strokes%2A><xref:System.Windows.Controls.InkPresenter>和 释放手写笔捕获的集合中。  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>如何：使控件接受来自鼠标的输入  
 如果将前面的控件添加到应用程序，运行它，并将鼠标用作输入设备，您会注意到笔画不会持久化。 要在将鼠标用作输入设备时保留笔画，请执行以下操作：  
  
1. 重写<xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A>并创建新<xref:System.Windows.Input.StylusPointCollection>的"在事件发生时获取鼠标的位置"，并使用点数据创建<xref:System.Windows.Input.StylusPoint>一个 ，并将 添加到<xref:System.Windows.Input.StylusPoint>。 <xref:System.Windows.Input.StylusPointCollection>  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. 重写 <xref:System.Windows.UIElement.OnMouseMove%2A> 方法。 在事件发生时获取鼠标的位置，并使用点数据创建一个<xref:System.Windows.Input.StylusPoint>。  将<xref:System.Windows.Input.StylusPoint>添加到之前<xref:System.Windows.Input.StylusPointCollection>创建的对象。  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. 重写 <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> 方法。  <xref:System.Windows.Ink.Stroke>使用<xref:System.Windows.Input.StylusPointCollection>数据创建新数据，并将创建<xref:System.Windows.Ink.Stroke><xref:System.Windows.Controls.InkPresenter.Strokes%2A>的新添加到 集合中。 <xref:System.Windows.Controls.InkPresenter>  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>
## <a name="putting-it-together"></a>综合运用  
 下面的示例是一个自定义控件，当用户使用鼠标或笔时收集墨迹。  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>使用其他插件和动态渲染器  
 与 InkCanvas 一样，自定义控件可以<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>具有自定义<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>对象和其他对象。 将这些添加到集合中<xref:System.Windows.UIElement.StylusPlugIns%2A>。 中<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>的对象的顺序<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>会影响墨迹在渲染时的外观。 假设您有一个<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>已`dynamicRenderer`调用的自定义<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>项`translatePlugin`，该调用的自定义项会偏移 Tablet 笔中的墨迹。 如果`translatePlugin`是第一<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>个，<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>是第`dynamicRenderer`二个，则当用户移动笔时，"流动"的墨迹将被偏移。 如果`dynamicRenderer`是第一，是第`translatePlugin`二，则在用户抬起笔之前，墨迹不会偏移。  
  
<a name="AdvancedInkHandling_Conclusion"></a>
## <a name="conclusion"></a>结束语  
 您可以创建通过重写手写笔事件方法收集和呈现墨迹的控件。 通过创建自己的控件、派生自己的<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>类并将它们插入 到 中<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>，您可以实现几乎任何使用数字墨迹可以想象到的行为。 您可以在生成<xref:System.Windows.Input.StylusPoint>数据时访问数据，从而有机会自定义<xref:System.Windows.Input.Stylus>输入并在屏幕上根据需要呈现它，以适合您的应用程序。 由于您对<xref:System.Windows.Input.StylusPoint>数据具有如此低级别的访问，因此可以实现墨迹收集，并针对应用程序以最佳性能呈现它。  
  
## <a name="see-also"></a>另请参阅

- [高级墨迹处理](advanced-ink-handling.md)
- [访问和操作笔输入](https://docs.microsoft.com/previous-versions/ms818317(v=msdn.10))
