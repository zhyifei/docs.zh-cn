---
title: 截获触笔输入
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
ms.openlocfilehash: 7629843730a82584e94448ceac1ea574906876c9
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095133"
---
# <a name="intercepting-input-from-the-stylus"></a>截获触笔输入
<xref:System.Windows.Input.StylusPlugIns> 体系结构提供了一种机制，用于实现对 <xref:System.Windows.Input.Stylus> 输入和数字墨迹 <xref:System.Windows.Ink.Stroke> 对象创建的低级别控制。 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 类提供一种机制，用于实现自定义行为，并将其应用于来自触笔设备的数据流，以获得最佳性能。  
  
 本主题包含下列子部分：  
  
- [体系结构](#Architecture)  
  
- [实现触笔插件](#ImplementingStylusPlugins)  
  
- [将插件添加到 InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [结语](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>体系结构  
 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 是[StylusInput](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) api 的演变，如[访问和操作笔输入](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))中所述。  
  
 每个 <xref:System.Windows.UIElement> 都具有 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>的 <xref:System.Windows.UIElement.StylusPlugIns%2A> 属性。 可以将 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 添加到元素的 <xref:System.Windows.UIElement.StylusPlugIns%2A> 属性，以便在生成数据时操作 <xref:System.Windows.Input.StylusPoint> 数据。 <xref:System.Windows.Input.StylusPoint> 数据由系统数字化器支持的所有属性组成，其中包括 <xref:System.Windows.Input.StylusPoint.X%2A> 和 <xref:System.Windows.Input.StylusPoint.Y%2A> 点数据以及 <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> 数据。  
  
 将 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 添加到 <xref:System.Windows.UIElement.StylusPlugIns%2A> 属性时，<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 对象将直接插入来自 <xref:System.Windows.Input.Stylus> 设备的数据流。 插件添加到 <xref:System.Windows.UIElement.StylusPlugIns%2A> 集合中的顺序指示它们将接收 <xref:System.Windows.Input.StylusPoint> 数据的顺序。 例如，如果添加一个筛选器插件，该插件将输入限制为特定区域，然后在写入时添加可识别手势的插件，则识别手势的插件将接收筛选的 <xref:System.Windows.Input.StylusPoint> 数据。  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>实现触笔插件  
 若要实现插件，请从 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>派生类。 此类应用于从 <xref:System.Windows.Input.Stylus>传入的数据流。 在此类中，您可以修改 <xref:System.Windows.Input.StylusPoint> 数据的值。  
  
> [!CAUTION]
> 如果 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 引发或导致异常，应用程序将关闭。 你应全面测试使用 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 的控件，并且仅当你确定 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 不会引发异常时，才使用控件。  
  
 下面的示例演示一个插件，该插件通过在 <xref:System.Windows.Input.StylusPoint> 数据中修改 <xref:System.Windows.Input.StylusPoint.X%2A> 和 <xref:System.Windows.Input.StylusPoint.Y%2A> 值来限制触笔输入，因为该插件来自 <xref:System.Windows.Input.Stylus> 设备。  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>将插件添加到 InkCanvas  
 使用自定义插件的最简单方法是实现从 InkCanvas 派生的类并将其添加到 <xref:System.Windows.UIElement.StylusPlugIns%2A> 属性中。  
  
 下面的示例演示用于筛选墨迹的自定义 <xref:System.Windows.Controls.InkCanvas>。  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 如果将 `FilterInkCanvas` 添加到应用程序并运行该应用程序，则会注意到，在用户完成笔划之前，墨迹并不限于区域。 这是因为 <xref:System.Windows.Controls.InkCanvas> 具有 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 属性，该属性是一个 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>，并且已经是 <xref:System.Windows.UIElement.StylusPlugIns%2A> 集合的成员。 添加到 <xref:System.Windows.UIElement.StylusPlugIns%2A> 集合中的自定义 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 在 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 接收数据后接收 <xref:System.Windows.Input.StylusPoint> 数据。 因此，在用户将笔抬起到结束笔划之前，将不会筛选 <xref:System.Windows.Input.StylusPoint> 的数据。 若要在用户绘制墨迹时筛选墨迹，必须在 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>之前插入 `FilterPlugin`。  
  
 下面C#的代码演示了一个自定义 <xref:System.Windows.Controls.InkCanvas>，可在绘制时对墨迹进行筛选。  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>结束语  
 通过派生你自己的 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 类并将它们插入 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 集合中，你可以极大地提高数字墨迹的行为。 您可以在生成 <xref:System.Windows.Input.StylusPoint> 数据时对其进行访问，从而使您有机会自定义 <xref:System.Windows.Input.Stylus> 输入。 由于你对 <xref:System.Windows.Input.StylusPoint> 的数据具有这种低级别访问权限，因此你可以实现墨迹收集并使用应用程序的最佳性能进行呈现。  
  
## <a name="see-also"></a>另请参阅

- [高级墨迹处理](advanced-ink-handling.md)
- [访问和操作笔输入](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))
