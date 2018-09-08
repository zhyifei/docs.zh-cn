---
title: 如何：使用几何路径来旋转对象（矩阵动画）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
ms.openlocfilehash: 3a35f6dda05cfe65811de16d76b288c8fbd618a7
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44199227"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a><span data-ttu-id="7cc0b-102">如何：使用几何路径来旋转对象（矩阵动画）</span><span class="sxs-lookup"><span data-stu-id="7cc0b-102">How to: Rotate an Object by Using a Geometric Path (Matrix Animation)</span></span>
<span data-ttu-id="7cc0b-103">此示例演示如何使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>和一个<xref:System.Windows.Media.MatrixTransform>旋转 （转动） 某个对象沿几何路径由定义<xref:System.Windows.Media.PathGeometry>对象。</span><span class="sxs-lookup"><span data-stu-id="7cc0b-103">This example shows how to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and a <xref:System.Windows.Media.MatrixTransform> to rotate (pivot) an object along a geometric path defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cc0b-104">示例</span><span class="sxs-lookup"><span data-stu-id="7cc0b-104">Example</span></span>  
 <span data-ttu-id="7cc0b-105">下面的示例使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>对象进行动画处理<xref:System.Windows.Media.MatrixTransform.Matrix%2A>属性的<xref:System.Windows.Media.MatrixTransform>。</span><span class="sxs-lookup"><span data-stu-id="7cc0b-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="7cc0b-106"><xref:System.Windows.Media.MatrixTransform>应用于按钮，并使其沿着曲线路径移动。</span><span class="sxs-lookup"><span data-stu-id="7cc0b-106">The <xref:System.Windows.Media.MatrixTransform> is applied to a button and causes it to move along a curved path.</span></span> <span data-ttu-id="7cc0b-107">因为<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A>属性设置为`true`，矩形将沿着路径的切线旋转。</span><span class="sxs-lookup"><span data-stu-id="7cc0b-107">Because the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property is set to `true`, the rectangle rotates along the tangent of the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 <span data-ttu-id="7cc0b-108">有关完整示例，请参阅[路径动画示例](https://go.microsoft.com/fwlink/?LinkID=160028)。</span><span class="sxs-lookup"><span data-stu-id="7cc0b-108">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="7cc0b-109">使用前面示例的代码版本<xref:System.Windows.Media.Animation.Storyboard>进行动画处理<xref:System.Windows.Media.EllipseGeometry>，即使只有一个动画已应用。</span><span class="sxs-lookup"><span data-stu-id="7cc0b-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="7cc0b-110">将一个动画应用到代码中的属性的更简单方法是使用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="7cc0b-110">An easier way to apply a single animation to a property in code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="7cc0b-111">有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="7cc0b-111">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cc0b-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="7cc0b-112">See Also</span></span>  
 [<span data-ttu-id="7cc0b-113">动画概述</span><span class="sxs-lookup"><span data-stu-id="7cc0b-113">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="7cc0b-114">路径动画操作说明主题</span><span class="sxs-lookup"><span data-stu-id="7cc0b-114">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [<span data-ttu-id="7cc0b-115">路径动画示例</span><span class="sxs-lookup"><span data-stu-id="7cc0b-115">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)
