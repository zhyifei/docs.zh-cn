---
title: 如何：使用四元数为 3D 旋转设置动画
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3D translations [WPF], with quaternions
- 3D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: 0d229b0a714cc53459943fae751ab4d4f787d7d8
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112240"
---
# <a name="how-to-animate-a-3d-rotation-using-quaternions"></a><span data-ttu-id="2df17-102">如何：使用四元数为 3D 旋转设置动画</span><span class="sxs-lookup"><span data-stu-id="2df17-102">How to: Animate a 3D Rotation Using Quaternions</span></span>
<span data-ttu-id="2df17-103">此示例演示如何使用四元数为 3D 对象的旋转设置动画。</span><span class="sxs-lookup"><span data-stu-id="2df17-103">This example shows how to animate a rotation of a 3D object using quaternions.</span></span>  
  
 <span data-ttu-id="2df17-104">下面的代码显示了用作<xref:System.Windows.Media.Media3D.QuaternionRotation3D>属性的值。 <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> <xref:System.Windows.Media.Media3D.RotateTransform3D></span><span class="sxs-lookup"><span data-stu-id="2df17-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="2df17-105">使用<xref:System.Windows.Media.Media3D.QuaternionRotation3D>下面的代码在<xref:System.Windows.Media.Animation.Storyboard><xref:System.Windows.Media.Animation.QuaternionAnimation>中使用 动画。</span><span class="sxs-lookup"><span data-stu-id="2df17-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="2df17-106">示例</span><span class="sxs-lookup"><span data-stu-id="2df17-106">Example</span></span>  
 <span data-ttu-id="2df17-107">以下代码显示整个示例。</span><span class="sxs-lookup"><span data-stu-id="2df17-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="2df17-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2df17-108">See also</span></span>

- [<span data-ttu-id="2df17-109">动画概述</span><span class="sxs-lookup"><span data-stu-id="2df17-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="2df17-110">创建 3D 场景</span><span class="sxs-lookup"><span data-stu-id="2df17-110">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="2df17-111">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="2df17-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="2df17-112">转换概述</span><span class="sxs-lookup"><span data-stu-id="2df17-112">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="2df17-113">使用情节提要为 3D 旋转设置动画</span><span class="sxs-lookup"><span data-stu-id="2df17-113">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="2df17-114">使用旋转3D动画为 3D 旋转设置动画</span><span class="sxs-lookup"><span data-stu-id="2df17-114">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
