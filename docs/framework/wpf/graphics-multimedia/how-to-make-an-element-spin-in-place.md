---
title: 如何：使元素就地旋转
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: 2e72389a11e48629c2763fcbd9f7b1945ffff5dd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452787"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="7e0e6-102">如何：使元素就地旋转</span><span class="sxs-lookup"><span data-stu-id="7e0e6-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="7e0e6-103">此示例演示如何使用 <xref:System.Windows.Media.RotateTransform> 和 <xref:System.Windows.Media.Animation.DoubleAnimation>使元素旋转。</span><span class="sxs-lookup"><span data-stu-id="7e0e6-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="7e0e6-104">下面的示例将 <xref:System.Windows.Media.RotateTransform> 应用到元素的 <xref:System.Windows.UIElement.RenderTransform%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="7e0e6-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="7e0e6-105">该示例使用 <xref:System.Windows.Media.Animation.DoubleAnimation> 对 <xref:System.Windows.Media.RotateTransform>的 <xref:System.Windows.Media.RotateTransform.Angle%2A> 进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="7e0e6-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="7e0e6-106">为了使元素就地旋转，此示例将元素的 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 属性设置为点（0.5，0.5）。</span><span class="sxs-lookup"><span data-stu-id="7e0e6-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e0e6-107">示例</span><span class="sxs-lookup"><span data-stu-id="7e0e6-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="7e0e6-108">有关包含更多转换示例的完整示例，请参阅二维[转换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。</span><span class="sxs-lookup"><span data-stu-id="7e0e6-108">For the complete sample, which includes more transformation examples, see [2-D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e0e6-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e0e6-109">See also</span></span>

- [<span data-ttu-id="7e0e6-110">动画概述</span><span class="sxs-lookup"><span data-stu-id="7e0e6-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="7e0e6-111">转换概述</span><span class="sxs-lookup"><span data-stu-id="7e0e6-111">Transforms Overview</span></span>](transforms-overview.md)
