---
title: 如何：为 TileBrush 设置平铺大小
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: af7bab59a292549b29dad9b6a7417f22b1b84e48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186840"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>如何：为 TileBrush 设置平铺大小

此示例演示如何设置 的<xref:System.Windows.Media.TileBrush>磁贴大小。 默认情况下，生成<xref:System.Windows.Media.TileBrush>一个完全填充要绘制的区域的磁贴。 可以通过设置 和<xref:System.Windows.Media.TileBrush.Viewport%2A><xref:System.Windows.Media.TileBrush.ViewportUnits%2A>属性来重写此行为。

属性<xref:System.Windows.Media.TileBrush.Viewport%2A>指定 的<xref:System.Windows.Media.TileBrush>磁贴大小。 默认情况下，<xref:System.Windows.Media.TileBrush.Viewport%2A>属性的值与要绘制的区域的大小相关。 要使<xref:System.Windows.Media.TileBrush.Viewport%2A>属性指定绝对磁贴大小，请将<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>属性设置为<xref:System.Windows.Media.BrushMappingMode.Absolute>。

## <a name="example"></a>示例

下面的示例使用<xref:System.Windows.Media.ImageBrush>、 的类型<xref:System.Windows.Media.TileBrush>，使用切片绘制矩形。 该示例将每个磁贴按输出区域（矩形）的 50% 设置为 50%。 因此，将用四个投影图像绘制该矩形。

下图显示了示例生成的输出：

![一个矩形，有四个樱桃，用图像画笔演示平铺。](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

下一个示例创建<xref:System.Windows.Media.ImageBrush>一个<xref:System.Windows.Media.TileBrush.Viewport%2A> `0,0,25,25` ，设置<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>其<xref:System.Windows.Media.BrushMappingMode.Absolute>和 其 到 ，并使用它来绘制另一个矩形。 因此，画笔会生成一个宽度为 25 像素、高度为 25 像素的平铺。

下图显示了示例生成的输出：

![一个长方形，有四十八个樱桃，展示一个瓷砖刷与视口。](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

以上几个示例摘自一个更大的示例。 有关完整示例，请参阅[图像画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)。

尽管此示例使用 类<xref:System.Windows.Media.ImageBrush>，<xref:System.Windows.Media.TileBrush.Viewport%2A>但 和<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>属性对于其他<xref:System.Windows.Media.TileBrush>对象（即 和<xref:System.Windows.Media.DrawingBrush>） 的行为相同。 <xref:System.Windows.Media.VisualBrush> 有关<xref:System.Windows.Media.ImageBrush>和其他<xref:System.Windows.Media.TileBrush>对象的详细信息，请参阅[使用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.TileBrush>
- [使用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
- [使用 TileBrush 创建不同的平铺图案](how-to-create-different-tile-patterns-with-a-tilebrush.md)
