---
title: 如何：沿着路径针对对象进行动画处理（偏移量进行累积的矩阵动画）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: e5e619de8b90737136559db134a131fdc1833fb9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640090"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a><span data-ttu-id="f6f1c-102">如何：沿着路径针对对象进行动画处理（偏移量进行累积的矩阵动画）</span><span class="sxs-lookup"><span data-stu-id="f6f1c-102">How to: Animate an Object Along a Path (Matrix Animation with Offset Accumulation)</span></span>
<span data-ttu-id="f6f1c-103">此示例演示如何使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>类沿着路径针对对象进行动画处理，并让该动画会累积其偏移量值重复。</span><span class="sxs-lookup"><span data-stu-id="f6f1c-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path and have that animation accumulate its offset values as it repeats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6f1c-104">示例</span><span class="sxs-lookup"><span data-stu-id="f6f1c-104">Example</span></span>  
 <span data-ttu-id="f6f1c-105">下面的示例使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>对象进行动画处理<xref:System.Windows.Media.MatrixTransform.Matrix%2A>属性的<xref:System.Windows.Media.MatrixTransform>应用于按钮。</span><span class="sxs-lookup"><span data-stu-id="f6f1c-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> applied to a button.</span></span> <span data-ttu-id="f6f1c-106">因此，按钮会沿着曲线路径移动。</span><span class="sxs-lookup"><span data-stu-id="f6f1c-106">As a result, a button moves along a curved path.</span></span>  
  
 <span data-ttu-id="f6f1c-107">此外，该示例设置<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A>属性设置为`true`，这将导致动画矩阵动画重复时累计的偏移量。</span><span class="sxs-lookup"><span data-stu-id="f6f1c-107">In addition, the example sets the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property to `true`, which causes the offset of the animated matrix to accumulate as the animation repeats.</span></span> <span data-ttu-id="f6f1c-108">由于偏移量累积，因此按钮会在动画重复时更快速地在屏幕上移动，而不是重置为起始位置。</span><span class="sxs-lookup"><span data-stu-id="f6f1c-108">Because the offset accumulates, the button moves farther across the screen when the animation repeats, rather than resetting to the starting position.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 <span data-ttu-id="f6f1c-109">请注意，尽管<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A>属性导致偏移量的值随着重复累计，但不会导致旋转值累积。</span><span class="sxs-lookup"><span data-stu-id="f6f1c-109">Note that, although the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property causes offset values to accumulate over repetitions, it doesn't cause rotation values to accumulate.</span></span> <span data-ttu-id="f6f1c-110">若要使旋转值累积，设置该动画<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A>并<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="f6f1c-110">To make rotation values accumulate, set the animation's <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> and <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> properties to `true`.</span></span>  
  
 <span data-ttu-id="f6f1c-111">有关完整示例，请参阅[路径动画示例](https://go.microsoft.com/fwlink/?LinkID=160028)。</span><span class="sxs-lookup"><span data-stu-id="f6f1c-111">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="f6f1c-112">有关演示如何进行动画处理的示例<xref:System.Windows.Media.Matrix>没有偏移量进行累积路径上的值，请参阅[沿着路径针对对象 （矩阵动画） 进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)。</span><span class="sxs-lookup"><span data-stu-id="f6f1c-112">For an example showing how to animate a <xref:System.Windows.Media.Matrix> value along a path without offset accumulation, see [Animate an Object Along a Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6f1c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6f1c-113">See also</span></span>
- [<span data-ttu-id="f6f1c-114">动画概述</span><span class="sxs-lookup"><span data-stu-id="f6f1c-114">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="f6f1c-115">路径动画操作说明主题</span><span class="sxs-lookup"><span data-stu-id="f6f1c-115">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
