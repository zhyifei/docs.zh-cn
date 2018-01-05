---
title: "如何：沿着路径针对对象进行动画处理（矩阵动画）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eb1bbe43c7e1797d5943bf3da6b4aca22a11c3a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a><span data-ttu-id="6b85c-102">如何：沿着路径针对对象进行动画处理（矩阵动画）</span><span class="sxs-lookup"><span data-stu-id="6b85c-102">How to: Animate an Object Along a Path (Matrix Animation)</span></span>
<span data-ttu-id="6b85c-103">此示例演示如何使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>沿路径定义的对象进行动画处理的类<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="6b85c-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path that is defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b85c-104">示例</span><span class="sxs-lookup"><span data-stu-id="6b85c-104">Example</span></span>  
 <span data-ttu-id="6b85c-105">下面的示例通过执行以下操作沿着路径针对对象进行动画处理：</span><span class="sxs-lookup"><span data-stu-id="6b85c-105">The following example animates an object along a path by doing the following:</span></span>  
  
-   <span data-ttu-id="6b85c-106">适用<xref:System.Windows.Media.MatrixTransform>对象以便将其移到。</span><span class="sxs-lookup"><span data-stu-id="6b85c-106">Applies a <xref:System.Windows.Media.MatrixTransform> to the object in order to move it.</span></span>  
  
-   <span data-ttu-id="6b85c-107">通过使用定义的路径<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="6b85c-107">Defines the path by using a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
-   <span data-ttu-id="6b85c-108">创建<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>并使用它来进行动画处理<xref:System.Windows.Media.Matrix>属性<xref:System.Windows.Media.MatrixTransform>。</span><span class="sxs-lookup"><span data-stu-id="6b85c-108">Creates a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and uses it to animate the <xref:System.Windows.Media.Matrix> property of the <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="6b85c-109"><xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>采用<xref:System.Windows.Media.PathGeometry>并使用它来生成<xref:System.Windows.Media.Matrix>值。</span><span class="sxs-lookup"><span data-stu-id="6b85c-109">The <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> takes the <xref:System.Windows.Media.PathGeometry> and uses it to generate <xref:System.Windows.Media.Matrix> values.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 <span data-ttu-id="6b85c-110">有关完整的示例，请参阅[路径动画示例](http://go.microsoft.com/fwlink/?LinkID=160028)。</span><span class="sxs-lookup"><span data-stu-id="6b85c-110">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="6b85c-111">有关几何路径的详细信息，请参阅[几何图形概述](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="6b85c-111">For more information about geometric paths, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b85c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b85c-112">See Also</span></span>  
 [<span data-ttu-id="6b85c-113">动画概述</span><span class="sxs-lookup"><span data-stu-id="6b85c-113">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="6b85c-114">路径动画示例</span><span class="sxs-lookup"><span data-stu-id="6b85c-114">Path Animation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [<span data-ttu-id="6b85c-115">路径动画操作说明主题</span><span class="sxs-lookup"><span data-stu-id="6b85c-115">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
