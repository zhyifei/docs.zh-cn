---
title: "如何：使用相对值指定变换原点"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d29a572e2989ffb800434fdaab9756cb651c0816
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a>如何：使用相对值指定变换原点
此示例演示如何使用相对的值来指定的源的<xref:System.Windows.UIElement.RenderTransform%2A>，可应用于<xref:System.Windows.FrameworkElement>。  
  
 当旋转、 缩放或扭曲<xref:System.Windows.FrameworkElement>使用<xref:System.Windows.UIElement.RenderTransform%2A>属性，默认设置适用于元素左上角的转换。 如果要从元素中心进行旋转、缩放或扭曲，则可以通过将转换中心设置为元素中心来进行补偿。 但是，该解决方案要求你知道元素的大小。 将转换应用于元素的中心的更简单的方法是将设置其<xref:System.Windows.UIElement.RenderTransformOrigin%2A>属性设置为 （0.5，0.5），而不是转换本身上设置中心值。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.RotateTransform>旋转<xref:System.Windows.Controls.Button>顺时针旋转 45 度。 由于该示例未指定中心，按钮将围绕点 (0, 0)（即按钮的左上角）旋转。 <xref:System.Windows.Media.RotateTransform>应用于<xref:System.Windows.UIElement.RenderTransform%2A>属性。  
  
 下图显示了以下示例的转换结果。  
  
 ![使用 rendertransform 变换的按钮](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
使用 RenderTransform 属性顺时针旋转 45 度  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 下面的示例还使用<xref:System.Windows.Media.RotateTransform>旋转<xref:System.Windows.Controls.Button>45 度沿顺时针方向; 但是，此示例设置<xref:System.Windows.UIElement.RenderTransformOrigin%2A>的按钮为 （0.5，0.5）。 因此，将在按钮的中心（而不是其左上角）应用旋转。  
  
 下图显示了以下示例的转换结果。  
  
 ![围绕中心变换的按钮](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
将 RenderTransform 属性与值为 (0.5, 0.5) 的 RenderTransformOrigin 结合使用以旋转 45 度  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 有关转换的详细信息<xref:System.Windows.FrameworkElement>对象，请参阅[转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.Transform>  
 [转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
