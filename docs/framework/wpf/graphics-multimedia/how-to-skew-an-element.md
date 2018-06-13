---
title: 如何：使元素扭曲
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 8bd860a71253a55cb3148426dbb61cbd3477e95e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561558"
---
# <a name="how-to-skew-an-element"></a><span data-ttu-id="7630a-102">如何：使元素扭曲</span><span class="sxs-lookup"><span data-stu-id="7630a-102">How to: Skew an Element</span></span>
<span data-ttu-id="7630a-103">此示例演示如何使用<xref:System.Windows.Media.SkewTransform>扭曲元素。</span><span class="sxs-lookup"><span data-stu-id="7630a-103">This example shows how to use a <xref:System.Windows.Media.SkewTransform> to skew an element.</span></span> <span data-ttu-id="7630a-104">扭曲（也称为修剪）是一种以非均匀方式拉伸坐标空间的转换。</span><span class="sxs-lookup"><span data-stu-id="7630a-104">A skew, which is also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="7630a-105">一个典型用法<xref:System.Windows.Media.SkewTransform>是用于模拟[!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)]中的深度[!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)]对象。</span><span class="sxs-lookup"><span data-stu-id="7630a-105">One typical use of a <xref:System.Windows.Media.SkewTransform> is for simulating [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] depth in [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] objects.</span></span>  
  
 <span data-ttu-id="7630a-106">使用<xref:System.Windows.Media.SkewTransform.CenterX%2A>和<xref:System.Windows.Media.SkewTransform.CenterY%2A>属性以指定中心点的<xref:System.Windows.Media.SkewTransform>。</span><span class="sxs-lookup"><span data-stu-id="7630a-106">Use the <xref:System.Windows.Media.SkewTransform.CenterX%2A> and <xref:System.Windows.Media.SkewTransform.CenterY%2A> properties to specify the center point of the <xref:System.Windows.Media.SkewTransform>.</span></span>  
  
 <span data-ttu-id="7630a-107">使用<xref:System.Windows.Media.SkewTransform.AngleX%2A>和<xref:System.Windows.Media.SkewTransform.AngleY%2A>属性以指定的 x 轴和 y 轴的倾斜角度和倾斜沿这些轴当前坐标系统。</span><span class="sxs-lookup"><span data-stu-id="7630a-107">Use the <xref:System.Windows.Media.SkewTransform.AngleX%2A> and <xref:System.Windows.Media.SkewTransform.AngleY%2A> properties to specify the skew angle of the x-axis and y-axis, and to skew the current coordinate system along these axes.</span></span>  
  
 <span data-ttu-id="7630a-108">若要预测的倾斜转换的影响，请考虑，<xref:System.Windows.Media.SkewTransform.AngleX%2A>偏差相对于原始的坐标系统的 x 轴值。</span><span class="sxs-lookup"><span data-stu-id="7630a-108">To predict the effect of a skew transformation, consider that <xref:System.Windows.Media.SkewTransform.AngleX%2A> skews x-axis values relative to the original coordinate system.</span></span> <span data-ttu-id="7630a-109">因此，对于<xref:System.Windows.Media.SkewTransform.AngleX%2A>为 30，y 轴旋转通过原点 30 度和倾斜 x 轴旋转从该原点 30 度的值。</span><span class="sxs-lookup"><span data-stu-id="7630a-109">Therefore, for an <xref:System.Windows.Media.SkewTransform.AngleX%2A> of 30, the y-axis rotates 30 degrees through the origin and skews the values in x- by 30 degrees from that origin.</span></span> <span data-ttu-id="7630a-110">同样， <xref:System.Windows.Media.SkewTransform.AngleY%2A> 30 的偏差的形状的 y 值从原点 30 度。</span><span class="sxs-lookup"><span data-stu-id="7630a-110">Likewise, an <xref:System.Windows.Media.SkewTransform.AngleY%2A> of 30 skews the y- values of the shape by 30 degrees from the origin.</span></span> <span data-ttu-id="7630a-111">请注意，在 x 或 y 轴中将坐标系统转换（移动）30 度的效果并不相同。</span><span class="sxs-lookup"><span data-stu-id="7630a-111">Note that this is not the same effect as translating (moving) the coordinate system by 30 degrees in x- or y-.</span></span>  
  
 <span data-ttu-id="7630a-112">下面的示例应用到的 45 度的水平扭曲<xref:System.Windows.Shapes.Rectangle>要从中心点的 (0，0)。</span><span class="sxs-lookup"><span data-stu-id="7630a-112">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (0,0).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7630a-113">示例</span><span class="sxs-lookup"><span data-stu-id="7630a-113">Example</span></span>  
 [!code-xaml[transformsSample#41](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 <span data-ttu-id="7630a-114">下面的示例应用到的 45 度的水平扭曲<xref:System.Windows.Shapes.Rectangle>要从中心点 (25，25)。</span><span class="sxs-lookup"><span data-stu-id="7630a-114">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#42](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 <span data-ttu-id="7630a-115">下面的示例应用到的 45 度的垂直扭曲<xref:System.Windows.Shapes.Rectangle>要从中心点 (25，25)。</span><span class="sxs-lookup"><span data-stu-id="7630a-115">The following example applies a vertical skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#43](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 <span data-ttu-id="7630a-116">下图演示了此示例中使用的不同扭曲。</span><span class="sxs-lookup"><span data-stu-id="7630a-116">The following illustration shows the different skews that are used in this example.</span></span>  
  
 <span data-ttu-id="7630a-117">![SkewTransform 示例](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span><span class="sxs-lookup"><span data-stu-id="7630a-117">![SkewTransform examples](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span></span>  
<span data-ttu-id="7630a-118">三个 SkewTransform 示例的图示</span><span class="sxs-lookup"><span data-stu-id="7630a-118">The three SkewTransform examples illustrated</span></span>  
  
 <span data-ttu-id="7630a-119">有关完整示例，请参阅 [2D 转换示例](http://go.microsoft.com/fwlink/?LinkID=158252)。</span><span class="sxs-lookup"><span data-stu-id="7630a-119">For the complete sample, see [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7630a-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="7630a-120">See Also</span></span>  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.SkewTransform>  
 [<span data-ttu-id="7630a-121">转换概述</span><span class="sxs-lookup"><span data-stu-id="7630a-121">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="7630a-122">帮助主题</span><span class="sxs-lookup"><span data-stu-id="7630a-122">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
