---
title: 如何：创建反射
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: c791dbbe02faaba790c650d482db092702730fa6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560571"
---
# <a name="how-to-create-a-reflection"></a>如何：创建反射
此示例演示如何使用<xref:System.Windows.Media.VisualBrush>创建反射。 因为<xref:System.Windows.Media.VisualBrush>可以显示现有的视觉对象，可以使用此功能来生成有趣的视觉效果，例如反射和放大倍数。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.VisualBrush>若要创建的反射<xref:System.Windows.Controls.Border>，其中包含几个元素。 下图显示了此示例生成的输出。  
  
 ![A 反映视觉对象](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
反射的 Visual 对象  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 有关完整的示例，其中包括演示如何放大屏幕的部分以及如何创建反射的示例，请参阅[VisualBrush 示例](http://go.microsoft.com/fwlink/?LinkID=160049)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.VisualBrush>  
 [使用图像、绘图和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
