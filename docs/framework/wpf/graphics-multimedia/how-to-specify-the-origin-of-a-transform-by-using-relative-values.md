---
title: 如何：使用相对值指定转换原点
ms.date: 03/30/2017
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
ms.openlocfilehash: 48b3b0df8dab8516873495a996074eae57ffe00f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651115"
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a><span data-ttu-id="eb170-102">如何：使用相对值指定转换原点</span><span class="sxs-lookup"><span data-stu-id="eb170-102">How to: Specify the Origin of a Transform by Using Relative Values</span></span>
<span data-ttu-id="eb170-103">此示例演示如何使用相对值来指定原点<xref:System.Windows.UIElement.RenderTransform%2A>应用于<xref:System.Windows.FrameworkElement>。</span><span class="sxs-lookup"><span data-stu-id="eb170-103">This example shows how to use relative values to specify the origin of a <xref:System.Windows.UIElement.RenderTransform%2A> that is applied to a <xref:System.Windows.FrameworkElement>.</span></span>  
  
 <span data-ttu-id="eb170-104">当旋转、 缩放或扭曲<xref:System.Windows.FrameworkElement>通过使用<xref:System.Windows.UIElement.RenderTransform%2A>属性，默认设置适用于元素的左上角的转换。</span><span class="sxs-lookup"><span data-stu-id="eb170-104">When you rotate, scale, or skew a <xref:System.Windows.FrameworkElement> by using the <xref:System.Windows.UIElement.RenderTransform%2A> property, the default setting applies the transform to the upper-left corner of the element.</span></span> <span data-ttu-id="eb170-105">如果要从元素中心进行旋转、缩放或扭曲，则可以通过将转换中心设置为元素中心来进行补偿。</span><span class="sxs-lookup"><span data-stu-id="eb170-105">If you want to rotate, scale, or skew from the center of the element, you can compensate by setting the center of the transform to the center of the element.</span></span> <span data-ttu-id="eb170-106">但是，该解决方案要求你知道元素的大小。</span><span class="sxs-lookup"><span data-stu-id="eb170-106">However, that solution requires that you know the size of the element.</span></span> <span data-ttu-id="eb170-107">将转换应用于元素的中心的更简单的方法是设置其<xref:System.Windows.UIElement.RenderTransformOrigin%2A>属性设置为 （0.5，0.5），而不是对转换本身设置中心值。</span><span class="sxs-lookup"><span data-stu-id="eb170-107">An easier way of applying a transform to the center of an element is to set its <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to (0.5, 0.5), instead of setting a center value on the transform itself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb170-108">示例</span><span class="sxs-lookup"><span data-stu-id="eb170-108">Example</span></span>  
 <span data-ttu-id="eb170-109">下面的示例使用<xref:System.Windows.Media.RotateTransform>旋转<xref:System.Windows.Controls.Button>顺时针旋转 45 度。</span><span class="sxs-lookup"><span data-stu-id="eb170-109">The following example uses a <xref:System.Windows.Media.RotateTransform> to rotate a <xref:System.Windows.Controls.Button> 45 degrees clockwise.</span></span> <span data-ttu-id="eb170-110">由于该示例未指定中心，按钮将围绕点 (0, 0)（即按钮的左上角）旋转。</span><span class="sxs-lookup"><span data-stu-id="eb170-110">Because the example does not specify a center, the button rotates about the point (0, 0), which is its upper-left corner.</span></span> <span data-ttu-id="eb170-111"><xref:System.Windows.Media.RotateTransform>应用于<xref:System.Windows.UIElement.RenderTransform%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="eb170-111">The <xref:System.Windows.Media.RotateTransform> is applied to the <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="eb170-112">下图显示了以下示例的转换结果。</span><span class="sxs-lookup"><span data-stu-id="eb170-112">The following illustration shows the transformation result for the example that follows.</span></span>  
  
 <span data-ttu-id="eb170-113">![使用 RenderTransform 转换的按钮](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")</span><span class="sxs-lookup"><span data-stu-id="eb170-113">![A button transformed using RenderTransform](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")</span></span>  
<span data-ttu-id="eb170-114">使用 RenderTransform 属性顺时针旋转 45 度</span><span class="sxs-lookup"><span data-stu-id="eb170-114">A 45 degree clockwise rotation by using the RenderTransform property</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 <span data-ttu-id="eb170-115">下面的示例也使用<xref:System.Windows.Media.RotateTransform>旋转<xref:System.Windows.Controls.Button>45 度顺时针旋转; 但是，此示例设置<xref:System.Windows.UIElement.RenderTransformOrigin%2A>到按钮的 （0.5，0.5）。</span><span class="sxs-lookup"><span data-stu-id="eb170-115">The following example also uses a <xref:System.Windows.Media.RotateTransform> to rotate a <xref:System.Windows.Controls.Button> 45 degrees clockwise; however, this example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> of the button to (0.5, 0.5).</span></span> <span data-ttu-id="eb170-116">因此，将在按钮的中心（而不是其左上角）应用旋转。</span><span class="sxs-lookup"><span data-stu-id="eb170-116">As a result, the rotation is applied to the center of the button instead of to the upper-left corner.</span></span>  
  
 <span data-ttu-id="eb170-117">下图显示了以下示例的转换结果。</span><span class="sxs-lookup"><span data-stu-id="eb170-117">The following illustration shows the transformation result for the example that follows.</span></span>  
  
 <span data-ttu-id="eb170-118">![围绕中心转换后的按钮](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")</span><span class="sxs-lookup"><span data-stu-id="eb170-118">![A button transformed about its center](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")</span></span>  
<span data-ttu-id="eb170-119">将 RenderTransform 属性与值为 (0.5, 0.5) 的 RenderTransformOrigin 结合使用以旋转 45 度</span><span class="sxs-lookup"><span data-stu-id="eb170-119">A 45 degree rotation by using the RenderTransform property with a RenderTransformOrigin of (0.5, 0.5)</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 <span data-ttu-id="eb170-120">有关转换的详细信息<xref:System.Windows.FrameworkElement>对象，请参阅[转换概述](transforms-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="eb170-120">For more information about transforming <xref:System.Windows.FrameworkElement> objects, see the [Transforms Overview](transforms-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb170-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb170-121">See also</span></span>

- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="eb170-122">转换概述</span><span class="sxs-lookup"><span data-stu-id="eb170-122">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="eb170-123">帮助主题</span><span class="sxs-lookup"><span data-stu-id="eb170-123">How-to Topics</span></span>](transformations-how-to-topics.md)
