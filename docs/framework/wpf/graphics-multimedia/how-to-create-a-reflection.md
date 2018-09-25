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
ms.openlocfilehash: 716adff5c5c41e6601e384b6669516cb6ba1041d
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47080550"
---
# <a name="how-to-create-a-reflection"></a><span data-ttu-id="4d85d-102">如何：创建反射</span><span class="sxs-lookup"><span data-stu-id="4d85d-102">How to: Create a Reflection</span></span>
<span data-ttu-id="4d85d-103">此示例演示如何使用<xref:System.Windows.Media.VisualBrush>创建反射。</span><span class="sxs-lookup"><span data-stu-id="4d85d-103">This example shows how to use a <xref:System.Windows.Media.VisualBrush> to create a reflection.</span></span> <span data-ttu-id="4d85d-104">因为<xref:System.Windows.Media.VisualBrush>可以显示现有视觉对象，可以使用此功能来生成有趣的视觉效果，例如反射和放大。</span><span class="sxs-lookup"><span data-stu-id="4d85d-104">Because a <xref:System.Windows.Media.VisualBrush> can display an existing visual, you can use this capability to produce interesting visual effects, such as reflections and magnification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d85d-105">示例</span><span class="sxs-lookup"><span data-stu-id="4d85d-105">Example</span></span>  
 <span data-ttu-id="4d85d-106">下面的示例使用<xref:System.Windows.Media.VisualBrush>若要创建的反射<xref:System.Windows.Controls.Border>包含多个元素。</span><span class="sxs-lookup"><span data-stu-id="4d85d-106">The following example uses a <xref:System.Windows.Media.VisualBrush> to create a reflection of a <xref:System.Windows.Controls.Border> that contains several elements.</span></span> <span data-ttu-id="4d85d-107">下图显示了此示例生成的输出。</span><span class="sxs-lookup"><span data-stu-id="4d85d-107">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="4d85d-108">![一个反映视觉对象](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span><span class="sxs-lookup"><span data-stu-id="4d85d-108">![A reflected Visual object](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span></span>  
<span data-ttu-id="4d85d-109">反射的 Visual 对象</span><span class="sxs-lookup"><span data-stu-id="4d85d-109">A reflected Visual object</span></span>  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 <span data-ttu-id="4d85d-110">有关完整示例，其中包括显示如何放大屏幕的部分以及如何创建反射的示例，请参阅[VisualBrush 示例](https://go.microsoft.com/fwlink/?LinkID=160049)。</span><span class="sxs-lookup"><span data-stu-id="4d85d-110">For the complete sample, which includes examples that show how to magnify parts of the screen and how to create reflections, see [VisualBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160049).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d85d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d85d-111">See Also</span></span>  
 <xref:System.Windows.Media.VisualBrush>  
 [<span data-ttu-id="4d85d-112">使用图像、绘图和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="4d85d-112">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
