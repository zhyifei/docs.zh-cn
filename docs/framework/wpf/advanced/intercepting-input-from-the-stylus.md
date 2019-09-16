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
ms.openlocfilehash: 2547c0aa2f3a14080868c2760fa8999eb99d3d16
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046333"
---
# <a name="intercepting-input-from-the-stylus"></a>截获触笔输入
该<xref:System.Windows.Input.StylusPlugIns>体系结构提供了一种机制，用于实现对<xref:System.Windows.Input.Stylus>输入和数字墨迹<xref:System.Windows.Ink.Stroke>对象创建的低级别控制。 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>类提供一种机制，用于实现自定义行为，并将其应用于来自触笔设备的数据流，以获得最佳性能。  
  
 本主题包含以下小节：  
  
- [体系结构](#Architecture)  
  
- [实现触笔插件](#ImplementingStylusPlugins)  
  
- [将插件添加到 InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [结束语](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>体系结构  
 在 Microsoft [Windows XP Tablet PC Edition 软件开发工具包 1.7](https://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409)中，在[访问和操作笔输入](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)中介绍了 [StylusInput api](https://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) 的发展 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>。  
  
 每<xref:System.Windows.UIElement>个都有<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>一个的属性。<xref:System.Windows.UIElement.StylusPlugIns%2A> 可以向元素的<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.UIElement.StylusPlugIns%2A>属性添加，以便在生成数据<xref:System.Windows.Input.StylusPoint>时对数据进行操作。 <xref:System.Windows.Input.StylusPoint>数据包含系统数字化器支持的所有属性，包括<xref:System.Windows.Input.StylusPoint.X%2A>和<xref:System.Windows.Input.StylusPoint.Y%2A>点<xref:System.Windows.Input.StylusPoint.PressureFactor%2A>数据以及数据。  
  
 当<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.Input.Stylus> 你将<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>添加到属性中时，你的对象将直接插入来自设备的数据流。<xref:System.Windows.UIElement.StylusPlugIns%2A> 插件添加到<xref:System.Windows.UIElement.StylusPlugIns%2A>集合中的顺序指示它们将接收<xref:System.Windows.Input.StylusPoint>数据的顺序。 例如，如果添加一个筛选器插件，该插件将输入限制为特定区域，然后添加一个可在写入时识别手势的插件，则识别手势的插件将接收筛选<xref:System.Windows.Input.StylusPoint>的数据。  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>实现触笔插件  
 若要实现某个插件，请从<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>派生一个类。 此类应用于从<xref:System.Windows.Input.Stylus>传入的数据流的输出。 在此类中，您可以修改<xref:System.Windows.Input.StylusPoint>数据的值。  
  
> [!CAUTION]
> <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>如果引发或导致异常，应用程序将关闭。 你应全面测试使用的<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>控件，并且仅当你<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>确定不会引发异常时，才使用控件。  
  
 下面的示例演示一个插件，该插件<xref:System.Windows.Input.StylusPoint.X%2A>通过修改<xref:System.Windows.Input.StylusPoint>数据<xref:System.Windows.Input.Stylus>中来自设备的和<xref:System.Windows.Input.StylusPoint.Y%2A>值来限制触笔输入。  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>将插件添加到 InkCanvas  
 使用自定义插件的最简单方法是实现从 InkCanvas 派生的类并将其添加到<xref:System.Windows.UIElement.StylusPlugIns%2A>属性。  
  
 下面的示例演示用于筛选<xref:System.Windows.Controls.InkCanvas>墨迹的自定义。  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 如果你将添加`FilterInkCanvas`到应用程序并运行它，你会注意到，在用户完成笔划之前，不会将墨迹限制在某个区域。 这<xref:System.Windows.Controls.InkCanvas>是因为<xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>具有一个<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>属性，该属性是，并且已经是<xref:System.Windows.UIElement.StylusPlugIns%2A>集合的成员。 添加<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.Input.StylusPoint>到集合中的自定义接收数据后<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>接收数据。 <xref:System.Windows.UIElement.StylusPlugIns%2A> 因此，在用户将<xref:System.Windows.Input.StylusPoint>笔提起到结束笔划之前，将不会对数据进行筛选。 若要在用户绘制墨迹时筛选墨迹，必须在`FilterPlugin` <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>之前插入。  
  
 下面C#的代码演示了一个<xref:System.Windows.Controls.InkCanvas>自定义，它在绘制时对墨迹进行筛选。  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>结束语  
 通过派生你自己<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>的类并将它们<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>插入到集合中，你可以极大地增强数字墨迹的行为。 您可以在生成<xref:System.Windows.Input.StylusPoint>数据时对其进行访问，从而为您提供<xref:System.Windows.Input.Stylus>自定义输入的机会。 由于你对<xref:System.Windows.Input.StylusPoint>数据具有这样的低级别访问权限，因此你可以实现墨迹收集并使用应用程序的最佳性能进行呈现。  
  
## <a name="see-also"></a>请参阅

- [高级墨迹处理](advanced-ink-handling.md)
- [访问和操作笔输入](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
