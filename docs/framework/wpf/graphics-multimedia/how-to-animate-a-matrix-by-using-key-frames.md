---
title: "如何：使用关键帧对 Matrix 进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 862e1afdcd823181dff0948fab43b1656b85f721
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="07746-102">如何：使用关键帧对 Matrix 进行动画处理</span><span class="sxs-lookup"><span data-stu-id="07746-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="07746-103">此示例演示如何进行动画处理<xref:System.Windows.Media.MatrixTransform.Matrix%2A>属性<xref:System.Windows.Media.MatrixTransform>使用关键帧。</span><span class="sxs-lookup"><span data-stu-id="07746-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07746-104">示例</span><span class="sxs-lookup"><span data-stu-id="07746-104">Example</span></span>  
 <span data-ttu-id="07746-105">下面的示例使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.MatrixTransform.Matrix%2A>属性<xref:System.Windows.Media.MatrixTransform>。</span><span class="sxs-lookup"><span data-stu-id="07746-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="07746-106">该示例使用<xref:System.Windows.Media.MatrixTransform>要转换的外观和位置对象<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="07746-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="07746-107">此动画使用<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>类来创建两个关键帧，并执行以下命令，并它们：</span><span class="sxs-lookup"><span data-stu-id="07746-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1.  <span data-ttu-id="07746-108">进行动画处理第一个<xref:System.Windows.Media.Matrix>的第一个 0.2 秒数内。</span><span class="sxs-lookup"><span data-stu-id="07746-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="07746-109">此示例更改<xref:System.Windows.Media.Matrix.M11%2A>和<xref:System.Windows.Media.Matrix.M12%2A>属性<xref:System.Windows.Media.Matrix>。</span><span class="sxs-lookup"><span data-stu-id="07746-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="07746-110">此更改会导致按钮拉伸并不正确。</span><span class="sxs-lookup"><span data-stu-id="07746-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="07746-111">此示例还更改<xref:System.Windows.Media.Matrix.OffsetX%2A>和<xref:System.Windows.Media.Matrix.OffsetY%2A>属性，以便该按钮将更改位置。</span><span class="sxs-lookup"><span data-stu-id="07746-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2.  <span data-ttu-id="07746-112">进行动画处理第二个<xref:System.Windows.Media.Matrix>1.0 秒时。</span><span class="sxs-lookup"><span data-stu-id="07746-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="07746-113">按钮不再扭曲或拉伸时，此按钮将移到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="07746-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3.  <span data-ttu-id="07746-114">无限期地重复动画。</span><span class="sxs-lookup"><span data-stu-id="07746-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07746-115">关键帧派生自<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>对象突变值，也就是说，移动动画效果。</span><span class="sxs-lookup"><span data-stu-id="07746-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="07746-116">有关完整示例，请参阅[关键帧动画示例](http://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="07746-116">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07746-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="07746-117">See Also</span></span>  
 <xref:System.Windows.Media.MatrixTransform.Matrix%2A>  
 <xref:System.Windows.Media.MatrixTransform>  
 [<span data-ttu-id="07746-118">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="07746-118">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="07746-119">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="07746-119">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
