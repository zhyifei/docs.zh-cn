---
title: 装饰器概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: d8e6e53edc92a2847c001377706d313cf97cced5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956095"
---
# <a name="adorners-overview"></a>装饰器概述
装饰器是一种特殊<xref:System.Windows.FrameworkElement>类型的, 用于向用户提供视觉提示。 装饰器有很多用途，可用来向元素添加功能句柄，或者提供有关某个控件的状态信息。  

<a name="about_Adorners"></a>   
## <a name="about-adorners"></a>关于装饰器  
 是绑定到的<xref:System.Windows.FrameworkElement> <xref:System.Windows.UIElement>自定义。 <xref:System.Windows.Documents.Adorner> 装饰器呈现在<xref:System.Windows.Documents.AdornerLayer>中, 后者是始终位于装饰元素或装饰元素集合之上的呈现图面。 装饰器的呈现独立于呈现装饰器所<xref:System.Windows.UIElement>绑定到的。 装饰器通常使用位于装饰元素左上部的标准 2D 坐标原点，相对于其绑定到的元素进行定位。  
  
 装饰器的常见应用包括：  
  
- 将函数句柄添加<xref:System.Windows.UIElement>到, 使用户能够以某种方式 (调整大小、旋转、重定位等) 操作元素。  
  
- 提供视觉反馈以指示各种状态，或者响应各种事件。  
  
- 覆盖上的<xref:System.Windows.UIElement>视觉修饰。  
  
- 直观屏蔽或重写的<xref:System.Windows.UIElement>部分或全部。  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供用于装饰视觉元素的基本框架。 下表列出了装饰对象时使用的主要类型及其用途。 下面是几个用法示例。  
  
|||  
|-|-|  
|<xref:System.Windows.Documents.Adorner>|一个抽象基类，从中继承所有的具体装饰器实现。|  
|<xref:System.Windows.Documents.AdornerLayer>|一个类，表示一个或多个装饰元素的装饰器的呈现层。|  
|<xref:System.Windows.Documents.AdornerDecorator>|一个类，使装饰器层与元素集合相关联。|  
  
<a name="implement_custom_Adorner"></a>   
## <a name="implementing-a-custom-adorner"></a>实现自定义装饰器  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供的装饰器框架的主要用于支持创建自定义装饰器。 通过实现继承自抽象<xref:System.Windows.Documents.Adorner>类的类来创建自定义装饰器。  
  
> [!NOTE]
> 的父级<xref:System.Windows.Documents.Adorner> <xref:System.Windows.Documents.AdornerLayer>是呈现<xref:System.Windows.Documents.Adorner>的, 而不是要装饰的元素。  
  
 下面的示例展示了实现简单装饰器的类。 示例装饰器只是<xref:System.Windows.UIElement>使用圆圈装饰的角。  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
 下图显示了应用于的<xref:System.Windows.Controls.TextBox>SimpleCircleAdorner。  
  
 ![显示所装饰文本框的屏幕截图。](./media/adorners-overview/simplecircleadorner-textbox.png)  
  
<a name="rendering_behavior_for_Adorners"></a>   
## <a name="rendering-behavior-for-adorners"></a>装饰器的呈现行为  
 请务必注意，装饰器不包括任何继承呈现行为，确保装饰器呈现是装饰器实施者的责任。   实现呈现行为的常见方法是重写<xref:System.Windows.UIElement.OnRender%2A>方法, 并使用一个或多个<xref:System.Windows.Media.DrawingContext>对象根据需要呈现装饰器的视觉对象 (如上面的示例所示)。  
  
> [!NOTE]
> 放置在装饰器层中的任何内容将呈现在设置的其他任何样式的顶部。 换言之，装饰器始终以可见的方式位于顶部，无法使用 z 顺序重写。  
  
<a name="adorner_events_hittest"></a>   
## <a name="events-and-hit-testing"></a>事件和命中测试  
 装饰器接收输入事件的方式与<xref:System.Windows.FrameworkElement>任何其他的一样。  因为装饰器的 z 顺序始终高于它装饰的元素, 所以装饰器会接收可能适用于基础装饰元素<xref:System.Windows.UIElement.Drop>的<xref:System.Windows.UIElement.MouseMove>输入事件 (如或)。  装饰器可以侦听某些输入事件，并通过重新引发这些事件将它们传递到基础装饰元素。  
  
 若要启用装饰器下元素的传递命中测试, 请在装饰器上<xref:System.Windows.UIElement.IsHitTestVisible%2A>将 "命中测试" 属性设置为**false** 。  有关命中测试的详细信息，请参阅  
  
 [可视化层中的命中测试](../graphics-multimedia/hit-testing-in-the-visual-layer.md)。  
  
<a name="adorn_single_element"></a>   
## <a name="adorning-a-single-uielement"></a>装饰单个 UIElement  
 若要将装饰器绑定到<xref:System.Windows.UIElement>特定的, 请执行以下步骤:  
  
1. 调用静态方法<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> , 以<xref:System.Windows.Documents.AdornerLayer>获取要装饰的的<xref:System.Windows.UIElement>对象。 <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>从指定<xref:System.Windows.UIElement>的开始向上遍历可视化树, 并返回它找到的第一个装饰器层。 （如果未发现装饰器层，该方法将返回 null。）  
  
2. 调用方法以将装饰器绑定到目标<xref:System.Windows.UIElement>。 <xref:System.Windows.Documents.AdornerLayer.Add%2A>  
  
 下面的示例将 SimpleCircleAdorner (如上所示) 绑定到<xref:System.Windows.Controls.TextBox>命名的*myTextBox*。  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
> 目前不支持使用 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 将装饰器绑定到另一个元素。  
  
<a name="adorn_children_panel"></a>   
## <a name="adorning-the-children-of-a-panel"></a>装饰面板的子级  
 若要将装饰器绑定到的子<xref:System.Windows.Controls.Panel>节点, 请执行以下步骤:  
  
1. `static`调用方法<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> , 为要装饰其子级的元素查找装饰器层。  
  
2. 枚举父元素的子级并调用<xref:System.Windows.Documents.AdornerLayer.Add%2A>方法, 将装饰器绑定到每个子元素。  
  
 下面的示例将 SimpleCircleAdorner (如上所示) 绑定到<xref:System.Windows.Controls.StackPanel>名为*myStackPanel*的子项。  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.AdornerHitTestResult>
- [WPF 中的形状和基本绘图概述](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [使用图像、绘图和视觉对象进行绘制](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [Drawing 对象概述](../graphics-multimedia/drawing-objects-overview.md)
- [帮助主题](adorners-how-to-topics.md)
