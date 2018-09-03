---
title: 如何：使用关键帧对 Matrix 进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: 8f58b43a870f2c85ae4349965f586a33e2f75a2a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485845"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="f1535-102">如何：使用关键帧对 Matrix 进行动画处理</span><span class="sxs-lookup"><span data-stu-id="f1535-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="f1535-103">此示例演示如何进行动画处理<xref:System.Windows.Media.MatrixTransform.Matrix%2A>属性的<xref:System.Windows.Media.MatrixTransform>使用关键帧。</span><span class="sxs-lookup"><span data-stu-id="f1535-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1535-104">示例</span><span class="sxs-lookup"><span data-stu-id="f1535-104">Example</span></span>  
 <span data-ttu-id="f1535-105">下面的示例使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.MatrixTransform.Matrix%2A>属性的<xref:System.Windows.Media.MatrixTransform>。</span><span class="sxs-lookup"><span data-stu-id="f1535-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="f1535-106">该示例使用<xref:System.Windows.Media.MatrixTransform>要转换的外观和位置对象<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="f1535-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="f1535-107">此动画使用<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>类来创建两个关键帧，然后执行以下与它们：</span><span class="sxs-lookup"><span data-stu-id="f1535-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1.  <span data-ttu-id="f1535-108">进行动画处理的第一个<xref:System.Windows.Media.Matrix>0.2 的第一个秒数内。</span><span class="sxs-lookup"><span data-stu-id="f1535-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="f1535-109">此示例更改<xref:System.Windows.Media.Matrix.M11%2A>并<xref:System.Windows.Media.Matrix.M12%2A>的属性<xref:System.Windows.Media.Matrix>。</span><span class="sxs-lookup"><span data-stu-id="f1535-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="f1535-110">此更改会导致该按钮拉伸和扭曲。</span><span class="sxs-lookup"><span data-stu-id="f1535-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="f1535-111">此示例还更改<xref:System.Windows.Media.Matrix.OffsetX%2A>和<xref:System.Windows.Media.Matrix.OffsetY%2A>属性，以便该按钮将更改位置。</span><span class="sxs-lookup"><span data-stu-id="f1535-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2.  <span data-ttu-id="f1535-112">进行动画处理第二个<xref:System.Windows.Media.Matrix>1.0 秒时。</span><span class="sxs-lookup"><span data-stu-id="f1535-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="f1535-113">该按钮将会移到另一个位置，而不再倾斜或拉伸按钮。</span><span class="sxs-lookup"><span data-stu-id="f1535-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3.  <span data-ttu-id="f1535-114">无限期地重复动画。</span><span class="sxs-lookup"><span data-stu-id="f1535-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1535-115">关键帧派生<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>对象之间创建突然跳跃值，也就是说，移动动画显得很不稳定。</span><span class="sxs-lookup"><span data-stu-id="f1535-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="f1535-116">有关完整示例，请参阅[关键帧动画示例](https://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="f1535-116">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1535-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1535-117">See Also</span></span>  
 <xref:System.Windows.Media.MatrixTransform.Matrix%2A>  
 <xref:System.Windows.Media.MatrixTransform>  
 [<span data-ttu-id="f1535-118">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="f1535-118">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="f1535-119">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="f1535-119">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
