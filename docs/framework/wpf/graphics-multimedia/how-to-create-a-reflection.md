---
title: "如何：创建反射"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 157bc01e23c304531f04b0a1cc7a66bad4bb3934
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-reflection"></a><span data-ttu-id="4f416-102">如何：创建反射</span><span class="sxs-lookup"><span data-stu-id="4f416-102">How to: Create a Reflection</span></span>
<span data-ttu-id="4f416-103">此示例演示如何使用<xref:System.Windows.Media.VisualBrush>创建反射。</span><span class="sxs-lookup"><span data-stu-id="4f416-103">This example shows how to use a <xref:System.Windows.Media.VisualBrush> to create a reflection.</span></span> <span data-ttu-id="4f416-104">因为<xref:System.Windows.Media.VisualBrush>可以显示现有的视觉对象，可以使用此功能来生成有趣的视觉效果，例如反射和放大倍数。</span><span class="sxs-lookup"><span data-stu-id="4f416-104">Because a <xref:System.Windows.Media.VisualBrush> can display an existing visual, you can use this capability to produce interesting visual effects, such as reflections and magnification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f416-105">示例</span><span class="sxs-lookup"><span data-stu-id="4f416-105">Example</span></span>  
 <span data-ttu-id="4f416-106">下面的示例使用<xref:System.Windows.Media.VisualBrush>若要创建的反射<xref:System.Windows.Controls.Border>，其中包含几个元素。</span><span class="sxs-lookup"><span data-stu-id="4f416-106">The following example uses a <xref:System.Windows.Media.VisualBrush> to create a reflection of a <xref:System.Windows.Controls.Border> that contains several elements.</span></span> <span data-ttu-id="4f416-107">下图显示了此示例生成的输出。</span><span class="sxs-lookup"><span data-stu-id="4f416-107">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="4f416-108">![A 反映视觉对象](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span><span class="sxs-lookup"><span data-stu-id="4f416-108">![A reflected Visual object](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span></span>  
<span data-ttu-id="4f416-109">反射的 Visual 对象</span><span class="sxs-lookup"><span data-stu-id="4f416-109">A reflected Visual object</span></span>  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 <span data-ttu-id="4f416-110">有关完整的示例，其中包括演示如何放大屏幕的部分以及如何创建反射的示例，请参阅[VisualBrush 示例](http://go.microsoft.com/fwlink/?LinkID=160049)。</span><span class="sxs-lookup"><span data-stu-id="4f416-110">For the complete sample, which includes examples that show how to magnify parts of the screen and how to create reflections, see [VisualBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160049).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f416-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f416-111">See Also</span></span>  
 <xref:System.Windows.Media.VisualBrush>  
 [<span data-ttu-id="4f416-112">使用图像、绘图和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="4f416-112">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
