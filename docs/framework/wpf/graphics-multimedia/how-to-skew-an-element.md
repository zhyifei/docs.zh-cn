---
title: 如何：使元素扭曲
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 10b00044c1c518641281e2e72cdb5a68474b5170
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112019"
---
# <a name="how-to-skew-an-element"></a><span data-ttu-id="00e4a-102">如何：使元素扭曲</span><span class="sxs-lookup"><span data-stu-id="00e4a-102">How to: Skew an Element</span></span>
<span data-ttu-id="00e4a-103">此示例演示如何使用<xref:System.Windows.Media.SkewTransform>倾斜元素。</span><span class="sxs-lookup"><span data-stu-id="00e4a-103">This example shows how to use a <xref:System.Windows.Media.SkewTransform> to skew an element.</span></span> <span data-ttu-id="00e4a-104">扭曲（也称为修剪）是一种以非均匀方式拉伸坐标空间的转换。</span><span class="sxs-lookup"><span data-stu-id="00e4a-104">A skew, which is also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="00e4a-105">一<xref:System.Windows.Media.SkewTransform>个典型的用途是模拟 2D 对象中的 3D 深度。</span><span class="sxs-lookup"><span data-stu-id="00e4a-105">One typical use of a <xref:System.Windows.Media.SkewTransform> is for simulating 3D depth in 2D objects.</span></span>  
  
 <span data-ttu-id="00e4a-106">使用<xref:System.Windows.Media.SkewTransform.CenterX%2A>和<xref:System.Windows.Media.SkewTransform.CenterY%2A>属性指定 的中心<xref:System.Windows.Media.SkewTransform>点。</span><span class="sxs-lookup"><span data-stu-id="00e4a-106">Use the <xref:System.Windows.Media.SkewTransform.CenterX%2A> and <xref:System.Windows.Media.SkewTransform.CenterY%2A> properties to specify the center point of the <xref:System.Windows.Media.SkewTransform>.</span></span>  
  
 <span data-ttu-id="00e4a-107">使用<xref:System.Windows.Media.SkewTransform.AngleX%2A>和<xref:System.Windows.Media.SkewTransform.AngleY%2A>属性指定 x 轴和 y 轴的倾斜角度，并沿这些轴倾斜当前坐标系。</span><span class="sxs-lookup"><span data-stu-id="00e4a-107">Use the <xref:System.Windows.Media.SkewTransform.AngleX%2A> and <xref:System.Windows.Media.SkewTransform.AngleY%2A> properties to specify the skew angle of the x-axis and y-axis, and to skew the current coordinate system along these axes.</span></span>  
  
 <span data-ttu-id="00e4a-108">要预测偏斜变换的效果，请考虑倾斜<xref:System.Windows.Media.SkewTransform.AngleX%2A>x 轴值相对于原始坐标系。</span><span class="sxs-lookup"><span data-stu-id="00e4a-108">To predict the effect of a skew transformation, consider that <xref:System.Windows.Media.SkewTransform.AngleX%2A> skews x-axis values relative to the original coordinate system.</span></span> <span data-ttu-id="00e4a-109">因此，对于<xref:System.Windows.Media.SkewTransform.AngleX%2A>30，y 轴通过原点旋转 30 度，并将该原点以 x- 30 度表示值。</span><span class="sxs-lookup"><span data-stu-id="00e4a-109">Therefore, for an <xref:System.Windows.Media.SkewTransform.AngleX%2A> of 30, the y-axis rotates 30 degrees through the origin and skews the values in x- by 30 degrees from that origin.</span></span> <span data-ttu-id="00e4a-110">同样，30 的 y<xref:System.Windows.Media.SkewTransform.AngleY%2A>值从原点偏斜 30 度。</span><span class="sxs-lookup"><span data-stu-id="00e4a-110">Likewise, an <xref:System.Windows.Media.SkewTransform.AngleY%2A> of 30 skews the y- values of the shape by 30 degrees from the origin.</span></span> <span data-ttu-id="00e4a-111">请注意，在 x 或 y 轴中将坐标系统转换（移动）30 度的效果并不相同。</span><span class="sxs-lookup"><span data-stu-id="00e4a-111">Note that this is not the same effect as translating (moving) the coordinate system by 30 degrees in x- or y-.</span></span>  
  
 <span data-ttu-id="00e4a-112">下面的示例将 45 度的水平偏斜从中心<xref:System.Windows.Shapes.Rectangle>点 （0，0） 应用于 a。</span><span class="sxs-lookup"><span data-stu-id="00e4a-112">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (0,0).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00e4a-113">示例</span><span class="sxs-lookup"><span data-stu-id="00e4a-113">Example</span></span>  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 <span data-ttu-id="00e4a-114">下面的示例将 45 度的水平偏斜从中心<xref:System.Windows.Shapes.Rectangle>点 （25，25） 应用于 a。</span><span class="sxs-lookup"><span data-stu-id="00e4a-114">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 <span data-ttu-id="00e4a-115">下面的示例将 45 度的垂直倾斜从中心点<xref:System.Windows.Shapes.Rectangle>（25，25） 应用于 a。</span><span class="sxs-lookup"><span data-stu-id="00e4a-115">The following example applies a vertical skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 <span data-ttu-id="00e4a-116">下图演示了此示例中使用的不同扭曲。</span><span class="sxs-lookup"><span data-stu-id="00e4a-116">The following illustration shows the different skews that are used in this example.</span></span>  
  
 <span data-ttu-id="00e4a-117">![SkewTransform 示例](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span><span class="sxs-lookup"><span data-stu-id="00e4a-117">![SkewTransform examples](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span></span>  
<span data-ttu-id="00e4a-118">三个 SkewTransform 示例的图示</span><span class="sxs-lookup"><span data-stu-id="00e4a-118">The three SkewTransform examples illustrated</span></span>  
  
 <span data-ttu-id="00e4a-119">有关完整示例，请参阅[2D 变换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。</span><span class="sxs-lookup"><span data-stu-id="00e4a-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e4a-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00e4a-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [<span data-ttu-id="00e4a-121">转换概述</span><span class="sxs-lookup"><span data-stu-id="00e4a-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="00e4a-122">如何使用主题</span><span class="sxs-lookup"><span data-stu-id="00e4a-122">How-to Topics</span></span>](transformations-how-to-topics.md)
