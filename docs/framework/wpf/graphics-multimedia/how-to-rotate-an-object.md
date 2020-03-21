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
ms.openlocfilehash: e17d3b7b9986b477df198480129edaf4c139c6bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112058"
---
# <a name="how-to-rotate-an-object"></a><span data-ttu-id="d5988-102">如何：旋转对象</span><span class="sxs-lookup"><span data-stu-id="d5988-102">How to: Rotate an Object</span></span>
<span data-ttu-id="d5988-103">此示例演示如何旋转对象。</span><span class="sxs-lookup"><span data-stu-id="d5988-103">This example shows how to rotate an object.</span></span> <span data-ttu-id="d5988-104">该示例首先创建<xref:System.Windows.Media.RotateTransform>a，然后指定<xref:System.Windows.Media.RotateTransform.Angle%2A>其以度表示。</span><span class="sxs-lookup"><span data-stu-id="d5988-104">The example first creates a <xref:System.Windows.Media.RotateTransform> and then specifies its <xref:System.Windows.Media.RotateTransform.Angle%2A> in degrees.</span></span>  
  
 <span data-ttu-id="d5988-105">下面的示例围绕<xref:System.Windows.Shapes.Polyline>其左上角旋转对象 45 度。</span><span class="sxs-lookup"><span data-stu-id="d5988-105">The following example rotates a <xref:System.Windows.Shapes.Polyline> object 45 degrees about its upper-left corner.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5988-106">示例</span><span class="sxs-lookup"><span data-stu-id="d5988-106">Example</span></span>  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <span data-ttu-id="d5988-107">的<xref:System.Windows.Media.RotateTransform.CenterX%2A><xref:System.Windows.Media.RotateTransform.CenterY%2A>和 属性<xref:System.Windows.Media.RotateTransform>指定对象旋转的点。</span><span class="sxs-lookup"><span data-stu-id="d5988-107">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> specify the point about which the object is rotated.</span></span> <span data-ttu-id="d5988-108">此中心点以要转换的元素的坐标空间表示。</span><span class="sxs-lookup"><span data-stu-id="d5988-108">This center point is expressed in the coordinate space of the element that is transformed.</span></span> <span data-ttu-id="d5988-109">默认情况下，将围绕着要转换的对象的左上角 (0,0) 进行旋转。</span><span class="sxs-lookup"><span data-stu-id="d5988-109">By default, the rotation is applied to (0,0), which is the upper-left corner of the object to transform.</span></span>  
  
 <span data-ttu-id="d5988-110">下一<xref:System.Windows.Shapes.Polyline>个示例沿点 （25，50） 顺时针旋转对象 45 度。</span><span class="sxs-lookup"><span data-stu-id="d5988-110">The next example rotates a <xref:System.Windows.Shapes.Polyline> object clockwise 45 degrees about the point (25,50).</span></span>  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 <span data-ttu-id="d5988-111">下图显示了对两个对象应用 的结果<xref:System.Windows.Media.Transform>。</span><span class="sxs-lookup"><span data-stu-id="d5988-111">The following illustration shows the results of applying a <xref:System.Windows.Media.Transform> to the two objects.</span></span>  
  
 <span data-ttu-id="d5988-112">![以不同中心点进行的 45 度旋转](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="d5988-112">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
<span data-ttu-id="d5988-113">两个对象以不同的旋转中心旋转 45 度</span><span class="sxs-lookup"><span data-stu-id="d5988-113">Two objects that rotate 45 degrees from different rotational centers</span></span>  
  
 <span data-ttu-id="d5988-114">前面的<xref:System.Windows.Shapes.Polyline>示例中是 。 <xref:System.Windows.UIElement></span><span class="sxs-lookup"><span data-stu-id="d5988-114">The <xref:System.Windows.Shapes.Polyline> in the previous examples is a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="d5988-115">将 应用<xref:System.Windows.Media.Transform>到<xref:System.Windows.UIElement.RenderTransform%2A>的属性时<xref:System.Windows.UIElement>，可以使用 属性<xref:System.Windows.UIElement.RenderTransformOrigin%2A>为应用于元素的每个<xref:System.Windows.Media.Transform>属性指定原点。</span><span class="sxs-lookup"><span data-stu-id="d5988-115">When you apply a <xref:System.Windows.Media.Transform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a <xref:System.Windows.UIElement>, you can use the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to specify an origin for every <xref:System.Windows.Media.Transform> that you apply to the element.</span></span> <span data-ttu-id="d5988-116">由于属性<xref:System.Windows.UIElement.RenderTransformOrigin%2A>使用相对坐标，因此即使不知道元素的大小，也可以对元素的中心应用变换。</span><span class="sxs-lookup"><span data-stu-id="d5988-116">Because the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property uses relative coordinates, you can apply a transformation to the center of the element even if you do not know its size.</span></span> <span data-ttu-id="d5988-117">有关详细信息，请参阅[使用相对值指定变换的原点](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md)。</span><span class="sxs-lookup"><span data-stu-id="d5988-117">For more information and for an example, see [Specify the Origin of a Transform by Using Relative Values](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span></span>  
  
 <span data-ttu-id="d5988-118">有关完整示例，请参阅[2D 变换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。</span><span class="sxs-lookup"><span data-stu-id="d5988-118">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5988-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5988-119">See also</span></span>

- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="d5988-120">转换概述</span><span class="sxs-lookup"><span data-stu-id="d5988-120">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="d5988-121">如何使用主题</span><span class="sxs-lookup"><span data-stu-id="d5988-121">How-to Topics</span></span>](transformations-how-to-topics.md)
