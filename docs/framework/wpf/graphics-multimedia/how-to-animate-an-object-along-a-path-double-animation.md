---
title: 如何：沿着路径针对对象进行动画处理（双精度动画）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
ms.openlocfilehash: 34fde285cad794c01a509c4a79a7fa3baf61d2c8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651480"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a><span data-ttu-id="ef63b-102">如何：沿着路径针对对象进行动画处理（双精度动画）</span><span class="sxs-lookup"><span data-stu-id="ef63b-102">How to: Animate an Object Along a Path (Double Animation)</span></span>
<span data-ttu-id="ef63b-103">此示例演示如何使用<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>类来沿着由定义的路径移动对象<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="ef63b-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> class to move an object along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef63b-104">示例</span><span class="sxs-lookup"><span data-stu-id="ef63b-104">Example</span></span>  
 <span data-ttu-id="ef63b-105">下面的示例使用两个<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>对象沿几何路径移动一个矩形：</span><span class="sxs-lookup"><span data-stu-id="ef63b-105">The following example uses two <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path:</span></span>  
  
- <span data-ttu-id="ef63b-106">第一个<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>之间进行动画处理<xref:System.Windows.Media.TranslateTransform.X%2A>的<xref:System.Windows.Media.TranslateTransform>应用于该矩形。</span><span class="sxs-lookup"><span data-stu-id="ef63b-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.X%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="ef63b-107">这使矩形沿路径水平移动。</span><span class="sxs-lookup"><span data-stu-id="ef63b-107">It makes the rectangle move horizontally along the path.</span></span>  
  
- <span data-ttu-id="ef63b-108">第二个<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>之间进行动画处理<xref:System.Windows.Media.TranslateTransform.Y%2A>的<xref:System.Windows.Media.TranslateTransform>应用于该矩形。</span><span class="sxs-lookup"><span data-stu-id="ef63b-108">The second <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.Y%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="ef63b-109">这使矩形沿路径垂直移动。</span><span class="sxs-lookup"><span data-stu-id="ef63b-109">It makes the rectangle move vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 <span data-ttu-id="ef63b-110">有关完整示例，请参阅[路径动画示例](https://go.microsoft.com/fwlink/?LinkID=160028)。</span><span class="sxs-lookup"><span data-stu-id="ef63b-110">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="ef63b-111">使用几何路径移动对象的另一个方法是使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>对象。</span><span class="sxs-lookup"><span data-stu-id="ef63b-111">Another way to move an object using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object.</span></span> <span data-ttu-id="ef63b-112">有关示例，请参阅[沿着路径针对对象 （矩阵动画） 进行动画处理](how-to-animate-an-object-along-a-path-matrix-animation.md)。</span><span class="sxs-lookup"><span data-stu-id="ef63b-112">For an example, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef63b-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef63b-113">See also</span></span>

- [<span data-ttu-id="ef63b-114">动画概述</span><span class="sxs-lookup"><span data-stu-id="ef63b-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="ef63b-115">路径动画操作说明主题</span><span class="sxs-lookup"><span data-stu-id="ef63b-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
