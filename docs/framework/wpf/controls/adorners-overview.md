---
title: "装饰器概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 47b43b1b9848f91e77448d41609d8be5d60ecda5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="adorners-overview"></a>装饰器概述
装饰器是一种特殊类型的<xref:System.Windows.FrameworkElement>，可用来向用户提供可视提示。 装饰器有很多用途，可用来向元素添加功能句柄，或者提供有关某个控件的状态信息。  
  
  
  
<a name="about_Adorners"></a>   
## <a name="about-adorners"></a>关于装饰器  
 <xref:System.Windows.Documents.Adorner>是一个自定义<xref:System.Windows.FrameworkElement>，它绑定到<xref:System.Windows.UIElement>。 在中呈现装饰器<xref:System.Windows.Documents.AdornerLayer>，这是基于经过装饰的元素或经过装饰的元素的集合始终是一个呈现图面。 呈现装饰器无关的呈现<xref:System.Windows.UIElement>装饰器绑定到。 装饰器通常使用位于装饰元素左上部的标准 2D 坐标原点，相对于其绑定到的元素进行定位。  
  
 装饰器的常见应用包括：  
  
-   添加功能的句柄<xref:System.Windows.UIElement>，使用户能够操作以某种方式 （调整大小、 旋转、 重新定位等） 的元素。  
  
-   提供视觉反馈以指示各种状态，或者响应各种事件。  
  
-   上叠加视觉效果<xref:System.Windows.UIElement>。  
  
-   直观地进行掩码或重写部分或全部<xref:System.Windows.UIElement>。  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供用于装饰视觉元素的基本框架。 下表列出了装饰对象时使用的主要类型及其用途。 下面是几个用法示例。  
  
|||  
|-|-|  
|<xref:System.Windows.Documents.Adorner>|一个抽象基类，从中继承所有的具体装饰器实现。|  
|<xref:System.Windows.Documents.AdornerLayer>|一个类，表示一个或多个装饰元素的装饰器的呈现层。|  
|<xref:System.Windows.Documents.AdornerDecorator>|一个类，使装饰器层与元素集合相关联。|  
  
<a name="implement_custom_Adorner"></a>   
## <a name="implementing-a-custom-adorner"></a>实现自定义装饰器  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供的装饰器框架的主要用于支持创建自定义装饰器。 通过实现从抽象继承的类创建一个自定义的装饰器<xref:System.Windows.Documents.Adorner>类。  
  
> [!NOTE]
>  父级<xref:System.Windows.Documents.Adorner>是<xref:System.Windows.Documents.AdornerLayer>呈现<xref:System.Windows.Documents.Adorner>，不被修饰元素。  
  
 下面的示例展示了实现简单装饰器的类。 本示例装饰器简单地装饰的角<xref:System.Windows.UIElement>使用圆圈。  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
 下图显示应用于 SimpleCircleAdorner <xref:System.Windows.Controls.TextBox>。  
  
 ![装饰器示例：经过装饰的文本框](../../../../docs/framework/wpf/controls/media/adornedtextbox.png "AdornedTextBox")  
  
<a name="rendering_behavior_for_Adorners"></a>   
## <a name="rendering-behavior-for-adorners"></a>装饰器的呈现行为  
 请务必注意，装饰器不包括任何继承呈现行为，确保装饰器呈现是装饰器实施者的责任。   实现呈现行为的常用方法是重写<xref:System.Windows.UIElement.OnRender%2A>方法并使用一个或多个<xref:System.Windows.Media.DrawingContext>对象来呈现装饰器的视觉对象根据需要 （如上面的示例中所示）。  
  
> [!NOTE]
>  放置在装饰器层中的任何内容将呈现在设置的其他任何样式的顶部。 换言之，装饰器始终以可见的方式位于顶部，无法使用 z 顺序重写。  
  
<a name="adorner_events_hittest"></a>   
## <a name="events-and-hit-testing"></a>事件和命中测试  
 装饰器接收输入的事件，就像任何其他<xref:System.Windows.FrameworkElement>。  由于装饰器始终具有更高版本 z 顺序比其装饰的元素，该装饰器接收输入的事件 (如<xref:System.Windows.UIElement.Drop>或<xref:System.Windows.UIElement.MouseMove>) 可能适用于基础装饰元素。  装饰器可以侦听某些输入事件，并通过重新引发这些事件将它们传递到基础装饰元素。  
  
 若要启用下装饰器元素传递命中测试，设置命中的测试<xref:System.Windows.UIElement.IsHitTestVisible%2A>属性**false**装饰器上。  有关命中测试的详细信息，请参阅  
  
 [可视化层中的命中测试](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)。  
  
<a name="adorn_single_element"></a>   
## <a name="adorning-a-single-uielement"></a>装饰单个 UIElement  
 若要将装饰器绑定到特定<xref:System.Windows.UIElement>，请按照下列步骤：  
  
1.  调用静态方法<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>获取<xref:System.Windows.Documents.AdornerLayer>对象<xref:System.Windows.UIElement>装饰。 <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>上移到可视化树，开始指定<xref:System.Windows.UIElement>，并返回它找到的第一个装饰器层。 （如果未发现装饰器层，该方法将返回 null。）  
  
2.  调用<xref:System.Windows.Documents.AdornerLayer.Add%2A>方法将装饰器绑定到目标<xref:System.Windows.UIElement>。  
  
 下面的示例将绑定 （上面所述） 到 SimpleCircleAdorner<xref:System.Windows.Controls.TextBox>名为*myTextBox*。  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  目前不支持使用 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 将装饰器绑定到另一个元素。  
  
<a name="adorn_children_panel"></a>   
## <a name="adorning-the-children-of-a-panel"></a>装饰面板的子级  
 若要将装饰器绑定到的子级<xref:System.Windows.Controls.Panel>，请按照下列步骤：  
  
1.  调用`static`方法<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>查找装饰的子级的元素的装饰器层。  
  
2.  枚举的子级的父元素和调用<xref:System.Windows.Documents.AdornerLayer.Add%2A>方法将装饰器绑定到每个子元素。  
  
 下面的示例将绑定 （上面所述） 的子级 SimpleCircleAdorner<xref:System.Windows.Controls.StackPanel>名为*myStackPanel*。  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.AdornerHitTestResult>  
 [WPF 中的形状和基本绘图概述](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [使用图像、绘图和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Drawing 对象概述](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/controls/adorners-how-to-topics.md)
