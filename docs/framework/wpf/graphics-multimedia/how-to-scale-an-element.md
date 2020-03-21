---
title: 如何：缩放元素
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 34d954f68747be9eedc0ef71634e0c18b411d260
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112045"
---
# <a name="how-to-scale-an-element"></a>如何：缩放元素
此示例演示如何使用<xref:System.Windows.Media.ScaleTransform>缩放元素。  
  
 使用<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>和<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>属性按指定的因子调整元素的大小。 例如，<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>值 1.5 将元素拉伸到其原始宽度的 150%。 值<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>0.5 将元素的高度缩小 50%。  
  
 使用<xref:System.Windows.Media.ScaleTransform.CenterX%2A>和<xref:System.Windows.Media.ScaleTransform.CenterY%2A>属性指定是比例操作中心的点。 默认情况下，a<xref:System.Windows.Media.ScaleTransform>居中居于与矩形左上角相对应的点 （0，0）。 这具有移动元素的效果，并且也使元素看起来更大，因为当您应用 时<xref:System.Windows.Media.Transform>，您将更改对象所在的坐标空间。  
  
 下面的示例使用 将<xref:System.Windows.Media.ScaleTransform>50 乘 50<xref:System.Windows.Shapes.Rectangle>的大小加倍。 和<xref:System.Windows.Media.ScaleTransform>的值为 0（默认值）。 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A>  
  
## <a name="example"></a>示例  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 通常，您设置<xref:System.Windows.Media.ScaleTransform.CenterX%2A>并<xref:System.Windows.Media.ScaleTransform.CenterY%2A>设置为缩放的对象的中心：（/2，/2）。<xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A>  
  
 下面的示例显示了另一<xref:System.Windows.Shapes.Rectangle>个大小加倍的，但是，这<xref:System.Windows.Media.ScaleTransform>两个 值为<xref:System.Windows.Media.ScaleTransform.CenterX%2A>25，<xref:System.Windows.Media.ScaleTransform.CenterY%2A>对应于矩形的中心。  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 下图显示了两<xref:System.Windows.Media.ScaleTransform>个操作之间的差异。 虚线显示的是矩形在缩放之前的大小和位置。  
  
 ![以不同中心点进行的 2 倍缩放](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")  
两个具有相同 ScaleX 和 ScaleY 值但中心不同的 ScaleTransform 操作  
  
 有关完整示例，请参阅[2D 变换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [转换概述](transforms-overview.md)
- [如何使用主题](transformations-how-to-topics.md)
