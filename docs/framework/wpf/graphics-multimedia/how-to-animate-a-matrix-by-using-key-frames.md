---
title: 如何：使用关键帧对矩阵进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: 6aa3e27cdfda7597c9b6acbf2980a2774f2b667b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963027"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="04369-102">如何：使用关键帧对矩阵进行动画处理</span><span class="sxs-lookup"><span data-stu-id="04369-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="04369-103">此示例演示如何使用关键帧<xref:System.Windows.Media.MatrixTransform.Matrix%2A>对的属性<xref:System.Windows.Media.MatrixTransform>进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="04369-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04369-104">示例</span><span class="sxs-lookup"><span data-stu-id="04369-104">Example</span></span>  
 <span data-ttu-id="04369-105">下面的示例使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>类对的<xref:System.Windows.Media.MatrixTransform.Matrix%2A>属性<xref:System.Windows.Media.MatrixTransform>进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="04369-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="04369-106">该示例使用<xref:System.Windows.Media.MatrixTransform>对象来转换的外观和位置<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="04369-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="04369-107">此动画使用<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>类创建两个关键帧, 并对其执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="04369-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1. <span data-ttu-id="04369-108">在前 0.2 <xref:System.Windows.Media.Matrix>秒内对第一个进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="04369-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="04369-109">此示例更改<xref:System.Windows.Media.Matrix.M11%2A>的和<xref:System.Windows.Media.Matrix.M12%2A>属性。 <xref:System.Windows.Media.Matrix></span><span class="sxs-lookup"><span data-stu-id="04369-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="04369-110">此更改会导致按钮拉伸并变得扭曲。</span><span class="sxs-lookup"><span data-stu-id="04369-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="04369-111">该示例还更改了<xref:System.Windows.Media.Matrix.OffsetX%2A>和<xref:System.Windows.Media.Matrix.OffsetY%2A>属性, 以使按钮更改位置。</span><span class="sxs-lookup"><span data-stu-id="04369-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2. <span data-ttu-id="04369-112"><xref:System.Windows.Media.Matrix>每秒在1.0 秒进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="04369-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="04369-113">按钮移至另一个位置, 而按钮不再歪斜或拉伸。</span><span class="sxs-lookup"><span data-stu-id="04369-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3. <span data-ttu-id="04369-114">无限期地重复动画。</span><span class="sxs-lookup"><span data-stu-id="04369-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="04369-115">从<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>对象派生的关键帧会在值之间创建突然跳转, 也就是说, 动画的移动是不平稳的。</span><span class="sxs-lookup"><span data-stu-id="04369-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="04369-116">有关完整示例，请参阅[关键帧动画示例](https://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="04369-116">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04369-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="04369-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="04369-118">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="04369-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="04369-119">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="04369-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
