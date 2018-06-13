---
title: 如何：对三维场景中的材质属性进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3-D scenes
- animation [WPF], Material properties in 3-D scenes
- 3-D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: ed4bbb3b22b09c24ed40b72a483db38b35038759
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559046"
---
# <a name="how-to-animate-material-properties-in-a-3-d-scene"></a><span data-ttu-id="c4c34-102">如何：对三维场景中的材质属性进行动画处理</span><span class="sxs-lookup"><span data-stu-id="c4c34-102">How to: Animate Material Properties in a 3-D Scene</span></span>
<span data-ttu-id="c4c34-103">此示例演示如何进行动画处理<xref:System.Windows.Media.Brush.Opacity%2A>属性<xref:System.Windows.Media.Media3D.Material>应用于[!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)]模型。</span><span class="sxs-lookup"><span data-stu-id="c4c34-103">This example shows how to animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Media3D.Material> applied to a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="c4c34-104">下面的代码示例定义<xref:System.Windows.Media.LinearGradientBrush>用作<xref:System.Windows.Media.Media3D.Material>应用于三维对象。</span><span class="sxs-lookup"><span data-stu-id="c4c34-104">The following code example defines the <xref:System.Windows.Media.LinearGradientBrush> used as the <xref:System.Windows.Media.Media3D.Material> applied to the 3D object.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 <span data-ttu-id="c4c34-105"><xref:System.Windows.Media.Brush.Opacity%2A>此属性<xref:System.Windows.Media.LinearGradientBrush>使用下面的代码示例动态显示。</span><span class="sxs-lookup"><span data-stu-id="c4c34-105">The <xref:System.Windows.Media.Brush.Opacity%2A> property of this <xref:System.Windows.Media.LinearGradientBrush> is animated using the code example below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="c4c34-106">示例</span><span class="sxs-lookup"><span data-stu-id="c4c34-106">Example</span></span>  
 <span data-ttu-id="c4c34-107">下面的代码演示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="c4c34-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c4c34-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4c34-108">See Also</span></span>  
 [<span data-ttu-id="c4c34-109">创建 3D 场景</span><span class="sxs-lookup"><span data-stu-id="c4c34-109">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="c4c34-110">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="c4c34-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
