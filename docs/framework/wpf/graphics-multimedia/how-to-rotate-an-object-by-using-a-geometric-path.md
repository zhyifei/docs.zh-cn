---
title: 如何：使用几何路径来旋转对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: 5a73ee967be0aae7dc3f1ef82229c2bcb2f9ade2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560711"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a><span data-ttu-id="d89f9-102">如何：使用几何路径来旋转对象</span><span class="sxs-lookup"><span data-stu-id="d89f9-102">How to: Rotate an Object by Using a Geometric Path</span></span>
<span data-ttu-id="d89f9-103">此示例演示如何旋转 (pivot) 沿着由定义的几何路径对对象<xref:System.Windows.Media.PathGeometry>对象。</span><span class="sxs-lookup"><span data-stu-id="d89f9-103">This example shows how to rotate (pivot) an object along a geometric path that is defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d89f9-104">示例</span><span class="sxs-lookup"><span data-stu-id="d89f9-104">Example</span></span>  
 <span data-ttu-id="d89f9-105">下面的示例使用三个<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>对象将沿几何路径的矩形。</span><span class="sxs-lookup"><span data-stu-id="d89f9-105">The following example uses three <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path.</span></span>  
  
-   <span data-ttu-id="d89f9-106">第一个<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>进行动画处理<xref:System.Windows.Media.RotateTransform>，可应用于矩形。</span><span class="sxs-lookup"><span data-stu-id="d89f9-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates a <xref:System.Windows.Media.RotateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="d89f9-107">该动画会生成角度值。</span><span class="sxs-lookup"><span data-stu-id="d89f9-107">The animation generates angle values.</span></span> <span data-ttu-id="d89f9-108">它使矩形沿着路径的轮廓旋转（转动）。</span><span class="sxs-lookup"><span data-stu-id="d89f9-108">It makes the rectangle rotate (pivot) along the contours of the path.</span></span>  
  
-   <span data-ttu-id="d89f9-109">其他两个对象进行动画处理<xref:System.Windows.Media.TranslateTransform.X%2A>和<xref:System.Windows.Media.TranslateTransform.Y%2A>值<xref:System.Windows.Media.TranslateTransform>，可应用于矩形。</span><span class="sxs-lookup"><span data-stu-id="d89f9-109">The other two objects animate the <xref:System.Windows.Media.TranslateTransform.X%2A> and <xref:System.Windows.Media.TranslateTransform.Y%2A> values of a <xref:System.Windows.Media.TranslateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="d89f9-110">它们使矩形沿路径水平和垂直移动。</span><span class="sxs-lookup"><span data-stu-id="d89f9-110">They make the rectangle move horizontally and vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 <span data-ttu-id="d89f9-111">若要使用的几何路径来旋转对象的另一种方法是使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>对象，并将其<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="d89f9-111">Another way to rotate an object by using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object and set its <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property to `true`.</span></span> <span data-ttu-id="d89f9-112">有关详细信息及示例，请参阅[使用几何路径 （矩阵动画） 旋转对象](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md)。</span><span class="sxs-lookup"><span data-stu-id="d89f9-112">For more information and an example, see [Rotate an Object by Using a Geometric Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span></span>  
  
 <span data-ttu-id="d89f9-113">有关完整的示例，请参阅[路径动画示例](http://go.microsoft.com/fwlink/?LinkID=160028)。</span><span class="sxs-lookup"><span data-stu-id="d89f9-113">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d89f9-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d89f9-114">See Also</span></span>  
 [<span data-ttu-id="d89f9-115">动画概述</span><span class="sxs-lookup"><span data-stu-id="d89f9-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="d89f9-116">路径动画示例</span><span class="sxs-lookup"><span data-stu-id="d89f9-116">Path Animation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [<span data-ttu-id="d89f9-117">路径动画操作说明主题</span><span class="sxs-lookup"><span data-stu-id="d89f9-117">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
