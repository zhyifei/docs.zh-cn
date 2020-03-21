---
title: 装饰器概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: b41c1f10f7e1b7c1799fd27270a3eeb9899ceeb6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111174"
---
# <a name="adorners-overview"></a>装饰器概述

装饰器是一种特殊的类型<xref:System.Windows.FrameworkElement>，用于向用户提供视觉提示。 装饰器有很多用途，可用来向元素添加功能句柄，或者提供有关某个控件的状态信息。

## <a name="about-adorners"></a>关于装饰器

是<xref:System.Windows.Documents.Adorner>绑定到<xref:System.Windows.FrameworkElement>的<xref:System.Windows.UIElement>自定义项。 装饰器以 中呈现<xref:System.Windows.Documents.AdornerLayer>，这是始终位于修饰元素或修饰元素集合之上的呈现曲面。 修饰器的渲染独立于修饰器绑定到的<xref:System.Windows.UIElement>渲染。 装饰器通常相对于绑定的元素进行定位，使用位于修饰元素左上角的标准 2D 坐标原点。

装饰器的常见应用包括：

- 将功能句柄添加到<xref:System.Windows.UIElement>，使用户能够以某种方式操作元素（调整大小、旋转、重新定位等）。
- 提供视觉反馈以指示各种状态，或者响应各种事件。
- 在 上叠加视觉装饰<xref:System.Windows.UIElement>。
- 直观地屏蔽或覆盖 部分或 全部<xref:System.Windows.UIElement>。

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供用于装饰视觉元素的基本框架。 下表列出了装饰对象时使用的主要类型及其用途。 以下几个使用示例如下：

|||
|-|-|
|<xref:System.Windows.Documents.Adorner>|一个抽象基类，从中继承所有的具体装饰器实现。|
|<xref:System.Windows.Documents.AdornerLayer>|一个类，表示一个或多个装饰元素的装饰器的呈现层。|
|<xref:System.Windows.Documents.AdornerDecorator>|一个类，使装饰器层与元素集合相关联。|

## <a name="implementing-a-custom-adorner"></a>实现自定义装饰器

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供的装饰器框架的主要用于支持创建自定义装饰器。 自定义修饰器是通过实现从抽象<xref:System.Windows.Documents.Adorner>类继承的类创建的。

> [!NOTE]
> 的父<xref:System.Windows.Documents.Adorner>级是<xref:System.Windows.Documents.AdornerLayer>呈现 的<xref:System.Windows.Documents.Adorner>， 而不是正在修饰的元素。

下面的示例展示了实现简单装饰器的类。 示例修饰器只是修饰带有圆圈的角<xref:System.Windows.UIElement>。

[!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
[!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]
  
下图显示了应用于 的<xref:System.Windows.Controls.TextBox>SimpleCircleAdorner：

![显示修饰文本框的屏幕截图。](./media/adorners-overview/simplecircleadorner-textbox.png)

## <a name="rendering-behavior-for-adorners"></a>装饰器的呈现行为

请务必注意，装饰器不包括任何继承呈现行为，确保装饰器呈现是装饰器实施者的责任。 实现呈现行为的常见方法是重写<xref:System.Windows.UIElement.OnRender%2A>该方法，并使用一个或多个<xref:System.Windows.Media.DrawingContext>对象根据需要呈现修饰器的视觉效果（如上例所示）。

> [!NOTE]
> 放置在装饰器层中的任何内容将呈现在设置的其他任何样式的顶部。 换言之，装饰器始终以可见的方式位于顶部，无法使用 z 顺序重写。

## <a name="events-and-hit-testing"></a>事件和命中测试

修饰器接收输入事件就像任何其他<xref:System.Windows.FrameworkElement>一样。  由于修饰器的 z 顺序始终高于其修饰的元素，因此修饰器接收可能用于基础修饰元素的输入事件（如<xref:System.Windows.UIElement.Drop><xref:System.Windows.UIElement.MouseMove>或 ）。  装饰器可以侦听某些输入事件，并通过重新引发这些事件将它们传递到基础装饰元素。

要启用修饰器下元素的直通命中测试，将命中测试<xref:System.Windows.UIElement.IsHitTestVisible%2A>属性设置为修饰器上的**false。**  有关命中测试的详细信息，请参阅[可视化图层中的命中测试](../graphics-multimedia/hit-testing-in-the-visual-layer.md)。

## <a name="adorning-a-single-uielement"></a>装饰单个 UIElement

要将装饰器绑定到特定<xref:System.Windows.UIElement>，请按照以下步骤操作：

1. 调用静态方法<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>获取<xref:System.Windows.Documents.AdornerLayer><xref:System.Windows.UIElement>要修饰的对象。 <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>向上走，从指定的<xref:System.Windows.UIElement>开始，然后返回它找到的第一个修饰器图层。 （如果未发现装饰器层，该方法将返回 null。）

2. 调用<xref:System.Windows.Documents.AdornerLayer.Add%2A>方法将修饰器绑定到目标<xref:System.Windows.UIElement>。

 下面的示例将 SimpleCircleAdorner（如上图所示）绑定到<xref:System.Windows.Controls.TextBox>名为*myTextBox ：*

 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]

> [!NOTE]
> 目前不支持使用 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 将装饰器绑定到另一个元素。

## <a name="adorning-the-children-of-a-panel"></a>装饰面板的子级

要将装饰器绑定到 子级<xref:System.Windows.Controls.Panel>，请按照以下步骤操作：

1. 调用`static`方法<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>查找要修饰其子元素的元素的修饰器图层。

2. 通过父元素的子元素枚举，<xref:System.Windows.Documents.AdornerLayer.Add%2A>并调用 方法将修饰器绑定到每个子元素。

下面的示例将 SimpleCircleAdorner（如上图所示）绑定到<xref:System.Windows.Controls.StackPanel>名为*myStackPanel*的子级：

[!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
[!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.AdornerHitTestResult>
- [WPF 中的形状和基本绘图概述](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [使用图像、绘图和视觉对象进行绘制](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [Drawing 对象概述](../graphics-multimedia/drawing-objects-overview.md)
- [如何使用主题](adorners-how-to-topics.md)
