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
ms.openlocfilehash: 17cf42a9d6d94d6ea12399561af5647df3b4d8c2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181920"
---
# <a name="intercepting-input-from-the-stylus"></a>截获触笔输入
该<xref:System.Windows.Input.StylusPlugIns>体系结构为实现对<xref:System.Windows.Input.Stylus>输入的低级控制和创建数字墨迹<xref:System.Windows.Ink.Stroke>对象提供了一种机制。 该<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>类提供了一种机制，用于实现自定义行为并将其应用于来自手写笔设备的数据流，以实现最佳性能。  
  
 本主题包含以下小节：  
  
- [建筑](#Architecture)  
  
- [实现手写插件](#ImplementingStylusPlugins)  
  
- [将插件添加到 InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [结论](#Conclusion)  
  
<a name="Architecture"></a>
## <a name="architecture"></a>体系结构  
 是<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>[手写输入](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90))API 的演变，在[访问和操作笔输入](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))中描述。  
  
 每个<xref:System.Windows.UIElement>都有一<xref:System.Windows.UIElement.StylusPlugIns%2A>个属性是<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>。 您可以将 添加到<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>元素的属性<xref:System.Windows.UIElement.StylusPlugIns%2A>以在生成数据时操作<xref:System.Windows.Input.StylusPoint>数据。 <xref:System.Windows.Input.StylusPoint>数据由系统数字化器支持的所有属性组成，包括<xref:System.Windows.Input.StylusPoint.X%2A>和<xref:System.Windows.Input.StylusPoint.Y%2A>点数据以及<xref:System.Windows.Input.StylusPoint.PressureFactor%2A>数据。  
  
 将<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>的对象直接插入到设备<xref:System.Windows.Input.Stylus>的数据流中，当您将 添加到<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>属性时。 <xref:System.Windows.UIElement.StylusPlugIns%2A> 插件添加到<xref:System.Windows.UIElement.StylusPlugIns%2A>集合的顺序决定了它们接收<xref:System.Windows.Input.StylusPoint>数据的顺序。 例如，如果添加筛选器插件，将输入限制到特定区域，然后添加一个插件，在编写手势时识别手势，则识别手势的插件将收到筛选<xref:System.Windows.Input.StylusPoint>的数据。  
  
<a name="ImplementingStylusPlugins"></a>
## <a name="implementing-stylus-plug-ins"></a>实现手写插件  
 要实现插件，请从<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>派生类。 类应用 o 数据流，因为它来自 。 <xref:System.Windows.Input.Stylus> 在此类中，您可以修改<xref:System.Windows.Input.StylusPoint>数据的值。  
  
> [!CAUTION]
> 如果<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>引发或导致异常，应用程序将关闭。 应彻底测试使用 和<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>仅在您确定 不会引发异常时才使用控件<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>的控件。  
  
 下面的示例演示了一个插件，该<xref:System.Windows.Input.StylusPoint.X%2A>插件通过修改<xref:System.Windows.Input.StylusPoint.Y%2A><xref:System.Windows.Input.StylusPoint>数据中的 和 值来限制手写笔输入。<xref:System.Windows.Input.Stylus>因为数据来自设备。  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>将插件添加到 InkCanvas  
 使用自定义插件的最简单方法是实现从 InkCanvas 派生的类并将其添加到<xref:System.Windows.UIElement.StylusPlugIns%2A>属性。  
  
 下面的示例演示了筛选墨<xref:System.Windows.Controls.InkCanvas>迹的自定义。  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 如果向应用程序添加`FilterInkCanvas`并运行它，您会注意到，在用户完成笔画之前，墨迹不会局限于区域。 这是因为<xref:System.Windows.Controls.InkCanvas>具有 属性<xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>，该属性是<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>，并且已经是<xref:System.Windows.UIElement.StylusPlugIns%2A>集合的成员。 添加到集合<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>中的<xref:System.Windows.UIElement.StylusPlugIns%2A>自定义在接收数据后<xref:System.Windows.Input.StylusPoint><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>接收数据。 因此，<xref:System.Windows.Input.StylusPoint>在用户抬起笔以结束笔画之前，数据才会被筛选。 若要在用户绘制墨迹时筛选墨迹，必须在 之前`FilterPlugin`<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>插入 。  
  
 以下 C# 代码演示了<xref:System.Windows.Controls.InkCanvas>在绘制墨迹时筛选墨迹的自定义。  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>
## <a name="conclusion"></a>结束语  
 通过派生自己的<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>类并将其插入到集合中<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>，可以极大地增强数字墨迹的行为。 您可以在生成<xref:System.Windows.Input.StylusPoint>数据时访问数据，从而有机会自定义<xref:System.Windows.Input.Stylus>输入。 由于您对<xref:System.Windows.Input.StylusPoint>数据具有如此低级别的访问，因此可以实现墨迹收集和呈现，从而为您的应用程序提供最佳性能。  
  
## <a name="see-also"></a>另请参阅

- [高级墨迹处理](advanced-ink-handling.md)
- [访问和操作笔输入](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))
