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
ms.openlocfilehash: 98b2abf813a232e36b80683254174b12b97659bb
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095211"
---
# <a name="creating-an-ink-input-control"></a>创建墨迹输入控件
可以创建动态和静态呈现墨迹的自定义控件。 也就是说，当用户绘制笔划时呈现墨迹，使墨迹显示为触笔的 "流"，并在将墨迹添加到控件后通过 tablet 笔从剪贴板中粘贴或从文件加载墨迹来显示墨迹。 若要动态呈现墨迹，控件必须使用 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>。 若要以静态方式呈现墨迹，必须重写触笔事件方法（<xref:System.Windows.UIElement.OnStylusDown%2A>、<xref:System.Windows.UIElement.OnStylusMove%2A>和 <xref:System.Windows.UIElement.OnStylusUp%2A>）以收集 <xref:System.Windows.Input.StylusPoint> 数据、创建笔画，并将其添加到 <xref:System.Windows.Controls.InkPresenter> （这会在控件上呈现墨迹）。  
  
 本主题包含下列子部分：  
  
- [如何：收集触笔接触点数据和创建墨迹笔划](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
- [如何：使控件接受鼠标输入](#EnablingYourControlToAcceptInputTromTheMouse)  
  
- [将其放在一起](#PuttingItTogether)  
  
- [使用其他插件和 DynamicRenderers](#UsingAdditionalPluginsAndDynamicRenderers)  
  
- [结语](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>如何：收集触笔接触点数据和创建墨迹笔划  
 若要创建用于收集和管理墨迹笔划的控件，请执行以下操作：  
  
1. 从 <xref:System.Windows.Controls.Control> 或从 <xref:System.Windows.Controls.Control>派生的类中派生一个类，如 <xref:System.Windows.Controls.Label>。  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. 将 <xref:System.Windows.Controls.InkPresenter> 添加到类，并将 <xref:System.Windows.Controls.ContentControl.Content%2A> 属性设置为新的 <xref:System.Windows.Controls.InkPresenter>。  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. 通过调用 <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> 方法将 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 的 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> 附加到 <xref:System.Windows.Controls.InkPresenter>，并将 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 添加到 <xref:System.Windows.UIElement.StylusPlugIns%2A> 集合。 这允许 <xref:System.Windows.Controls.InkPresenter> 在控件收集触笔数据时显示墨迹。  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. 重写 <xref:System.Windows.UIElement.OnStylusDown%2A> 方法。  在此方法中，通过调用 <xref:System.Windows.Input.Stylus.Capture%2A>捕获触笔。 捕获触笔后，即使触笔离开控件边界，控件仍将继续接收 <xref:System.Windows.UIElement.StylusMove> 和 <xref:System.Windows.UIElement.StylusUp> 事件。 这并不是绝对必需的，但几乎总是希望获得良好的用户体验。 创建新 <xref:System.Windows.Input.StylusPointCollection> 以收集 <xref:System.Windows.Input.StylusPoint> 数据。 最后，将 <xref:System.Windows.Input.StylusPoint> 的初始数据集添加到 <xref:System.Windows.Input.StylusPointCollection>中。  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. 重写 <xref:System.Windows.UIElement.OnStylusMove%2A> 方法，并将 <xref:System.Windows.Input.StylusPoint> 数据添加到之前创建的 <xref:System.Windows.Input.StylusPointCollection> 对象。  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. 重写 <xref:System.Windows.UIElement.OnStylusUp%2A> 方法，并使用 <xref:System.Windows.Input.StylusPointCollection> 数据创建新的 <xref:System.Windows.Ink.Stroke>。 将创建的新 <xref:System.Windows.Ink.Stroke> 添加到 <xref:System.Windows.Controls.InkPresenter> 的 <xref:System.Windows.Controls.InkPresenter.Strokes%2A> 集合，并释放触笔捕获。  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>如何：使控件接受鼠标输入  
 如果将前面的控件添加到应用程序，运行它，并使用鼠标作为输入设备，你会注意到这些笔划不会保留。 若要在鼠标作为输入设备使用时保持笔画，请执行以下操作：  
  
1. 重写 <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> 并创建一个新的 <xref:System.Windows.Input.StylusPointCollection> 获取发生事件时的鼠标位置，并使用点数据创建 <xref:System.Windows.Input.StylusPoint>，并将 <xref:System.Windows.Input.StylusPoint> 添加到 <xref:System.Windows.Input.StylusPointCollection>。  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. 重写 <xref:System.Windows.UIElement.OnMouseMove%2A> 方法。 在事件发生时获取鼠标位置，并使用点数据创建 <xref:System.Windows.Input.StylusPoint>。  将 <xref:System.Windows.Input.StylusPoint> 添加到之前创建的 <xref:System.Windows.Input.StylusPointCollection> 对象中。  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. 重写 <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> 方法。  使用 <xref:System.Windows.Input.StylusPointCollection> 数据创建新 <xref:System.Windows.Ink.Stroke>，并将创建的新 <xref:System.Windows.Ink.Stroke> 添加到 <xref:System.Windows.Controls.InkPresenter>的 <xref:System.Windows.Controls.InkPresenter.Strokes%2A> 集合。  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## <a name="putting-it-together"></a>将其放在一起  
 下面的示例是在用户使用鼠标或笔时收集墨迹的自定义控件。  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>使用其他插件和 DynamicRenderers  
 与 InkCanvas 一样，自定义控件可以具有自定义 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 和其他 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 对象。 将它们添加到 <xref:System.Windows.UIElement.StylusPlugIns%2A> 集合。 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 中的 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 对象的顺序会影响呈现墨迹时的外观。 假设你有一个名为 `dynamicRenderer` 的 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>，以及一个名为 "`translatePlugin`" 的自定义 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>，它将墨迹从 tablet 笔偏移。 如果 `translatePlugin` 是 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>中的第一个 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>，而 `dynamicRenderer` 为第二个，则在用户移动笔时，"流" 的墨迹将偏移。 如果 `dynamicRenderer` 是第一个，`translatePlugin` 为第二个，则在用户提起笔之前，墨迹不会偏移。  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## <a name="conclusion"></a>结束语  
 可以通过重写触笔事件方法来创建一个用于收集和呈现墨迹的控件。 通过创建自己的控件，派生你自己的 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 类，并将其插入 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>，你可以使用数字墨迹实现几乎所有的行为想象。 你可以在生成 <xref:System.Windows.Input.StylusPoint> 数据时对其进行访问，使你有机会自定义 <xref:System.Windows.Input.Stylus> 输入，并根据应用程序将其呈现在屏幕上。 由于你对 <xref:System.Windows.Input.StylusPoint> 的数据具有这种低级别访问权限，因此你可以实现墨迹收集，并为应用程序提供最佳性能。  
  
## <a name="see-also"></a>另请参阅

- [高级墨迹处理](advanced-ink-handling.md)
- [访问和操作笔输入](https://docs.microsoft.com/previous-versions/ms818317(v=msdn.10))
