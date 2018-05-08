---
title: 如何：对 Popup 进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
ms.openlocfilehash: 05b84eea7fe983340ebb8c5cdb20ff39eb2f0858
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-a-popup"></a>如何：对 Popup 进行动画处理
此示例演示两种方式进行动画处理<xref:System.Windows.Controls.Primitives.Popup>控件。  
  
## <a name="example"></a>示例  
 下面的示例设置<xref:System.Windows.Controls.Primitives.PopupAnimation>属性的值的<xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>，这将导致<xref:System.Windows.Controls.Primitives.Popup>以"滑入式"时出现。  
  
 若要旋转<xref:System.Windows.Controls.Primitives.Popup>，此示例将分配<xref:System.Windows.Media.RotateTransform>到<xref:System.Windows.UIElement.RenderTransform%2A>属性<xref:System.Windows.Controls.Canvas>，即的子元素<xref:System.Windows.Controls.Primitives.Popup>。  
  
 对于要正常工作的转换，则必须设置<xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A>属性`true`。 此外，<xref:System.Windows.FrameworkElement.Margin%2A>上<xref:System.Windows.Controls.Canvas>内容必须指定足够的空间<xref:System.Windows.Controls.Primitives.Popup>旋转。  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 下面的示例演示如何<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件发生时<xref:System.Windows.Controls.Button>单击后，触发器<xref:System.Windows.Media.Animation.Storyboard>启动动画。  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.UIElement.RenderTransform%2A>  
 <xref:System.Windows.Controls.Primitives.BulletDecorator>  
 <xref:System.Windows.Media.RotateTransform>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [帮助主题](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)  
 [Popup 概述](../../../../docs/framework/wpf/controls/popup-overview.md)
