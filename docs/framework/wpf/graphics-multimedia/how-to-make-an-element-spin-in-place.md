---
title: 如何：使元素就地旋转
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: 56385d7c31465e25f19486ea5cdaa8876cdb30ff
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43784440"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="ec5aa-102">如何：使元素就地旋转</span><span class="sxs-lookup"><span data-stu-id="ec5aa-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="ec5aa-103">此示例演示如何使某个元素通过使用旋转<xref:System.Windows.Media.RotateTransform>和一个<xref:System.Windows.Media.Animation.DoubleAnimation>。</span><span class="sxs-lookup"><span data-stu-id="ec5aa-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="ec5aa-104">下面的示例应用<xref:System.Windows.Media.RotateTransform>到<xref:System.Windows.UIElement.RenderTransform%2A>元素的属性。</span><span class="sxs-lookup"><span data-stu-id="ec5aa-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="ec5aa-105">该示例使用<xref:System.Windows.Media.Animation.DoubleAnimation>进行动画处理<xref:System.Windows.Media.RotateTransform.Angle%2A>的<xref:System.Windows.Media.RotateTransform>。</span><span class="sxs-lookup"><span data-stu-id="ec5aa-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="ec5aa-106">若要使元素就地旋转，该示例设置<xref:System.Windows.UIElement.RenderTransformOrigin%2A>到点 （0.5，0.5） 元素的属性。</span><span class="sxs-lookup"><span data-stu-id="ec5aa-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec5aa-107">示例</span><span class="sxs-lookup"><span data-stu-id="ec5aa-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="ec5aa-108">有关完整示例，其中包括转换的更多示例，请参阅[2d 转换示例](https://go.microsoft.com/fwlink/?LinkID=158252)。</span><span class="sxs-lookup"><span data-stu-id="ec5aa-108">For the complete sample, which includes more transformation examples, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec5aa-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec5aa-109">See Also</span></span>  
 [<span data-ttu-id="ec5aa-110">动画概述</span><span class="sxs-lookup"><span data-stu-id="ec5aa-110">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="ec5aa-111">转换概述</span><span class="sxs-lookup"><span data-stu-id="ec5aa-111">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
