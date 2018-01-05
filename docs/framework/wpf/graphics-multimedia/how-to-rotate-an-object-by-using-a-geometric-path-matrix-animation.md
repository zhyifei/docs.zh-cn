---
title: "如何：使用几何路径来旋转对象（矩阵动画）"
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
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c001c0969e42c1eaadad6c029ae86009176b9eb7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a><span data-ttu-id="5e597-102">如何：使用几何路径来旋转对象（矩阵动画）</span><span class="sxs-lookup"><span data-stu-id="5e597-102">How to: Rotate an Object by Using a Geometric Path (Matrix Animation)</span></span>
<span data-ttu-id="5e597-103">此示例演示如何使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>和<xref:System.Windows.Media.MatrixTransform>旋转 (pivot) 的对象定义的几何路径沿<xref:System.Windows.Media.PathGeometry>对象。</span><span class="sxs-lookup"><span data-stu-id="5e597-103">This example shows how to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and a <xref:System.Windows.Media.MatrixTransform> to rotate (pivot) an object along a geometric path defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e597-104">示例</span><span class="sxs-lookup"><span data-stu-id="5e597-104">Example</span></span>  
 <span data-ttu-id="5e597-105">下面的示例使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>对象要进行动画处理<xref:System.Windows.Media.MatrixTransform.Matrix%2A>属性<xref:System.Windows.Media.MatrixTransform>。</span><span class="sxs-lookup"><span data-stu-id="5e597-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="5e597-106"><xref:System.Windows.Media.MatrixTransform>应用于一个按钮并使其将沿曲线的路径。</span><span class="sxs-lookup"><span data-stu-id="5e597-106">The <xref:System.Windows.Media.MatrixTransform> is applied to a button and causes it to move along a curved path.</span></span> <span data-ttu-id="5e597-107">因为<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A>属性设置为`true`，矩形沿该路径的切线旋转。</span><span class="sxs-lookup"><span data-stu-id="5e597-107">Because the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property is set to `true`, the rectangle rotates along the tangent of the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 <span data-ttu-id="5e597-108">有关完整的示例，请参阅[路径动画示例](http://go.microsoft.com/fwlink/?LinkID=160028)。</span><span class="sxs-lookup"><span data-stu-id="5e597-108">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="5e597-109">上面的示例使用的代码版本<xref:System.Windows.Media.Animation.Storyboard>要进行动画处理<xref:System.Windows.Media.EllipseGeometry>，即使只有一个动画已应用。</span><span class="sxs-lookup"><span data-stu-id="5e597-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="5e597-110">将单个动画应用到代码中的属性的简单方法是使用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="5e597-110">An easier way to apply a single animation to a property in code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="5e597-111">有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="5e597-111">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e597-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e597-112">See Also</span></span>  
 [<span data-ttu-id="5e597-113">动画概述</span><span class="sxs-lookup"><span data-stu-id="5e597-113">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="5e597-114">路径动画操作说明主题</span><span class="sxs-lookup"><span data-stu-id="5e597-114">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [<span data-ttu-id="5e597-115">路径动画示例</span><span class="sxs-lookup"><span data-stu-id="5e597-115">Path Animation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160028)
