---
title: 如何：在 3D 场景中设置材质属性的动画
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3D scenes
- animation [WPF], Material properties in 3D scenes
- 3D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: db59debcd7558cde52d8604cb04c8c4e68921825
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112188"
---
# <a name="how-to-animate-material-properties-in-a-3d-scene"></a><span data-ttu-id="08796-102">如何：在 3D 场景中设置材质属性的动画</span><span class="sxs-lookup"><span data-stu-id="08796-102">How to: Animate Material Properties in a 3D Scene</span></span>
<span data-ttu-id="08796-103">此示例演示如何为应用于 3D<xref:System.Windows.Media.Brush.Opacity%2A>模型的属性<xref:System.Windows.Media.Media3D.Material>设置动画。</span><span class="sxs-lookup"><span data-stu-id="08796-103">This example shows how to animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Media3D.Material> applied to a 3D model.</span></span>  
  
 <span data-ttu-id="08796-104">以下代码示例将<xref:System.Windows.Media.LinearGradientBrush>用作<xref:System.Windows.Media.Media3D.Material>应用于 3D 对象的定义。</span><span class="sxs-lookup"><span data-stu-id="08796-104">The following code example defines the <xref:System.Windows.Media.LinearGradientBrush> used as the <xref:System.Windows.Media.Media3D.Material> applied to the 3D object.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 <span data-ttu-id="08796-105">使用<xref:System.Windows.Media.Brush.Opacity%2A><xref:System.Windows.Media.LinearGradientBrush>下面的代码示例对此的属性进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="08796-105">The <xref:System.Windows.Media.Brush.Opacity%2A> property of this <xref:System.Windows.Media.LinearGradientBrush> is animated using the code example below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="08796-106">示例</span><span class="sxs-lookup"><span data-stu-id="08796-106">Example</span></span>  
 <span data-ttu-id="08796-107">以下代码显示整个示例。</span><span class="sxs-lookup"><span data-stu-id="08796-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="08796-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08796-108">See also</span></span>

- [<span data-ttu-id="08796-109">创建 3D 场景</span><span class="sxs-lookup"><span data-stu-id="08796-109">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="08796-110">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="08796-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
