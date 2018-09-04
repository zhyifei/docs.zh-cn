---
title: 如何：旋转对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: b5a954158388e8b85589042e9d1f3b82c1747e30
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43563684"
---
# <a name="how-to-rotate-an-object"></a><span data-ttu-id="5aa95-102">如何：旋转对象</span><span class="sxs-lookup"><span data-stu-id="5aa95-102">How to: Rotate an Object</span></span>
<span data-ttu-id="5aa95-103">此示例演示如何旋转对象。</span><span class="sxs-lookup"><span data-stu-id="5aa95-103">This example shows how to rotate an object.</span></span> <span data-ttu-id="5aa95-104">该示例首先创建<xref:System.Windows.Media.RotateTransform>，然后指定其<xref:System.Windows.Media.RotateTransform.Angle%2A>以度为单位。</span><span class="sxs-lookup"><span data-stu-id="5aa95-104">The example first creates a <xref:System.Windows.Media.RotateTransform> and then specifies its <xref:System.Windows.Media.RotateTransform.Angle%2A> in degrees.</span></span>  
  
 <span data-ttu-id="5aa95-105">下面的示例将旋转<xref:System.Windows.Shapes.Polyline>对象围绕其左上角的 45 度。</span><span class="sxs-lookup"><span data-stu-id="5aa95-105">The following example rotates a <xref:System.Windows.Shapes.Polyline> object 45 degrees about its upper-left corner.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5aa95-106">示例</span><span class="sxs-lookup"><span data-stu-id="5aa95-106">Example</span></span>  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <span data-ttu-id="5aa95-107"><xref:System.Windows.Media.RotateTransform.CenterX%2A>并<xref:System.Windows.Media.RotateTransform.CenterY%2A>的属性<xref:System.Windows.Media.RotateTransform>指定哪些对象的旋转的点。</span><span class="sxs-lookup"><span data-stu-id="5aa95-107">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> specify the point about which the object is rotated.</span></span> <span data-ttu-id="5aa95-108">此中心点以要转换的元素的坐标空间表示。</span><span class="sxs-lookup"><span data-stu-id="5aa95-108">This center point is expressed in the coordinate space of the element that is transformed.</span></span> <span data-ttu-id="5aa95-109">默认情况下，将围绕着要转换的对象的左上角 (0,0) 进行旋转。</span><span class="sxs-lookup"><span data-stu-id="5aa95-109">By default, the rotation is applied to (0,0), which is the upper-left corner of the object to transform.</span></span>  
  
 <span data-ttu-id="5aa95-110">下一个示例旋转<xref:System.Windows.Shapes.Polyline>对象围绕点 (25，50) 顺时针旋转 45 度。</span><span class="sxs-lookup"><span data-stu-id="5aa95-110">The next example rotates a <xref:System.Windows.Shapes.Polyline> object clockwise 45 degrees about the point (25,50).</span></span>  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 <span data-ttu-id="5aa95-111">下图显示了应用的结果<xref:System.Windows.Media.Transform>到两个对象。</span><span class="sxs-lookup"><span data-stu-id="5aa95-111">The following illustration shows the results of applying a <xref:System.Windows.Media.Transform> to the two objects.</span></span>  
  
 <span data-ttu-id="5aa95-112">![围绕不同中心点旋转 45 度](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="5aa95-112">![45 degree rotations with different center points](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
<span data-ttu-id="5aa95-113">两个对象以不同的旋转中心旋转 45 度</span><span class="sxs-lookup"><span data-stu-id="5aa95-113">Two objects that rotate 45 degrees from different rotational centers</span></span>  
  
 <span data-ttu-id="5aa95-114"><xref:System.Windows.Shapes.Polyline>前面的示例中是<xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="5aa95-114">The <xref:System.Windows.Shapes.Polyline> in the previous examples is a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="5aa95-115">当应用<xref:System.Windows.Media.Transform>到<xref:System.Windows.UIElement.RenderTransform%2A>的属性<xref:System.Windows.UIElement>，可以使用<xref:System.Windows.UIElement.RenderTransformOrigin%2A>属性指定的 origin 每个<xref:System.Windows.Media.Transform>适用于元素。</span><span class="sxs-lookup"><span data-stu-id="5aa95-115">When you apply a <xref:System.Windows.Media.Transform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a <xref:System.Windows.UIElement>, you can use the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to specify an origin for every <xref:System.Windows.Media.Transform> that you apply to the element.</span></span> <span data-ttu-id="5aa95-116">因为<xref:System.Windows.UIElement.RenderTransformOrigin%2A>属性使用相对坐标，你可以将转换应用到元素的中心，即使您不知道其大小。</span><span class="sxs-lookup"><span data-stu-id="5aa95-116">Because the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property uses relative coordinates, you can apply a transformation to the center of the element even if you do not know its size.</span></span> <span data-ttu-id="5aa95-117">有关详细信息和示例，请参阅[指定使用相对值转换原点](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-the-origin-of-a-transform-by-using-relative-values.md)。</span><span class="sxs-lookup"><span data-stu-id="5aa95-117">For more information and for an example, see [Specify the Origin of a Transform by Using Relative Values](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span></span>  
  
 <span data-ttu-id="5aa95-118">有关完整示例，请参阅 [2D 转换示例](https://go.microsoft.com/fwlink/?LinkID=158252)。</span><span class="sxs-lookup"><span data-stu-id="5aa95-118">For the complete sample, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aa95-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="5aa95-119">See Also</span></span>  
 <xref:System.Windows.Media.Transform>  
 [<span data-ttu-id="5aa95-120">转换概述</span><span class="sxs-lookup"><span data-stu-id="5aa95-120">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="5aa95-121">帮助主题</span><span class="sxs-lookup"><span data-stu-id="5aa95-121">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
