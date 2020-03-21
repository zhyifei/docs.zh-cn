---
title: 使用 DrawingVisual 对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual layer [WPF], DrawingVisual objects
- DrawingVisual objects in visual layer [WPF]
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
ms.openlocfilehash: 9d67fbc0d9716c9df3935232c6c7e579b50d55bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148317"
---
# <a name="using-drawingvisual-objects"></a>使用 DrawingVisual 对象
本主题概述了如何在<xref:System.Windows.Media.DrawingVisual>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]可视化图层中使用对象。  
  
<a name="drawingvisual_object"></a>
## <a name="drawingvisual-object"></a>DrawingVisual 对象  
 是<xref:System.Windows.Media.DrawingVisual>用于渲染形状、图像或文本的轻量级绘图类。 此类之所以为轻量类是因为它不提供布局或事件处理，从而性能得以提升。 因此，绘图非常适用于背景和剪贴画。  
  
<a name="drawingvisual_host_container"></a>
## <a name="drawingvisual-host-container"></a>DrawingVisual 宿主容器  
 为了使用<xref:System.Windows.Media.DrawingVisual>对象，您需要为对象创建一个宿主容器。 主机容器对象必须派生自<xref:System.Windows.FrameworkElement>类，该类提供类缺少的<xref:System.Windows.Media.DrawingVisual>布局和事件处理支持。 宿主容器对象不显示任何可视属性，因为它的主要用途是包含子对象。 但是，<xref:System.Windows.UIElement.Visibility%2A>主机容器的属性必须设置为<xref:System.Windows.Visibility.Visible>;否则，其子元素都不会可见。  
  
 为可视对象创建宿主容器对象时，需要在 中<xref:System.Windows.Media.VisualCollection>存储可视对象引用。 使用<xref:System.Windows.Media.VisualCollection.Add%2A>方法向宿主容器添加可视对象。 在下面的示例中，将创建一个宿主容器对象，并将三个可视对象添加到其<xref:System.Windows.Media.VisualCollection>。  
  
 [!code-csharp[DrawingVisualSample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
> 有关从中提取上述代码示例的完整代码示例，请参阅[使用 DrawingVisual 的命中测试示例](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual)。  
  
<a name="creating_drawingvisual_objects"></a>
## <a name="creating-drawingvisual-objects"></a>创建 DrawingVisual 对象  
 创建对象时<xref:System.Windows.Media.DrawingVisual>，它没有绘图内容。 您可以通过检索对象<xref:System.Windows.Media.DrawingContext>并将其绘制到其中来添加文本、图形或图像内容。 通过<xref:System.Windows.Media.DrawingContext>调用<xref:System.Windows.Media.DrawingVisual.RenderOpen%2A><xref:System.Windows.Media.DrawingVisual>对象的方法返回 。  
  
 要将矩形绘制到<xref:System.Windows.Media.DrawingContext>中，请使用<xref:System.Windows.Media.DrawingContext.DrawRectangle%2A><xref:System.Windows.Media.DrawingContext>对象的方法。 对于绘制其他类型的内容，存在类似的方法。 将内容绘制完到 中<xref:System.Windows.Media.DrawingContext>，调用<xref:System.Windows.Media.DrawingContext.Close%2A>方法以关闭<xref:System.Windows.Media.DrawingContext>并保留内容。  
  
 在下面的示例中，将创建<xref:System.Windows.Media.DrawingVisual>一个对象，并将一个矩形绘制到其<xref:System.Windows.Media.DrawingContext>中。  
  
 [!code-csharp[DrawingVisualSample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>
## <a name="creating-overrides-for-frameworkelement-members"></a>为 FrameworkElement 成员创建重写  
 宿主容器对象负责管理其视觉对象的集合。 这要求主机容器实现成员重写派生<xref:System.Windows.FrameworkElement>类。  
  
 下表介绍了必须重写的两个成员：  
  
- <xref:System.Windows.FrameworkElement.GetVisualChild%2A>：从子元素集合中返回指定索引处的子项。  
  
- <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>：获取此元素中的可视子元素的数量。  
  
 在下面的示例中，将实现两<xref:System.Windows.FrameworkElement>个成员的重写。  
  
 [!code-csharp[DrawingVisualSample#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>
## <a name="providing-hit-testing-support"></a>提供命中测试支持  
 主机容器对象可以提供事件处理，即使它不显示任何可见属性 ， 但是，其<xref:System.Windows.UIElement.Visibility%2A>属性必须设置为<xref:System.Windows.Visibility.Visible>。 这样便可以为宿主容器创建事件处理例程，此例程可以捕获鼠标事件，如松开鼠标左键。 然后，事件处理例程可以通过调用<xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>方法实现命中测试。 方法的<xref:System.Windows.Media.HitTestResultCallback>参数是指用户定义的过程，可用于确定命中测试的结果操作。  
  
 在下面的示例中，为宿主容器对象及其子级实现命中测试支持。  
  
 [!code-csharp[DrawingVisualSample#103](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.DrawingVisual>
- <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>
- [WPF 图形呈现概述](wpf-graphics-rendering-overview.md)
- [可视化层中的命中测试](hit-testing-in-the-visual-layer.md)
