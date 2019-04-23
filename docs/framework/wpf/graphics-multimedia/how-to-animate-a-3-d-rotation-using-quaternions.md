---
title: 如何：使用四元数对三维旋转进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3-D translations [WPF], with quaternions
- 3-D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: d994ac2ae67fd366f27f123d5bd15f14d5ac7abe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183217"
---
# <a name="how-to-animate-a-3-d-rotation-using-quaternions"></a><span data-ttu-id="90844-102">如何：使用四元数对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="90844-102">How to: Animate a 3-D Rotation Using Quaternions</span></span>
<span data-ttu-id="90844-103">此示例演示如何使用四元数对三维对象的旋转进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="90844-103">This example shows how to animate a rotation of a 3-D object using quaternions.</span></span>  
  
 <span data-ttu-id="90844-104">下面的代码显示<xref:System.Windows.Media.Media3D.QuaternionRotation3D>的值作为<xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A>属性的<xref:System.Windows.Media.Media3D.RotateTransform3D>。</span><span class="sxs-lookup"><span data-stu-id="90844-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="90844-105">这<xref:System.Windows.Media.Media3D.QuaternionRotation3D>进行动画处理<xref:System.Windows.Media.Animation.QuaternionAnimation>内<xref:System.Windows.Media.Animation.Storyboard>使用下面的代码。</span><span class="sxs-lookup"><span data-stu-id="90844-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="90844-106">示例</span><span class="sxs-lookup"><span data-stu-id="90844-106">Example</span></span>  
 <span data-ttu-id="90844-107">下面的代码演示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="90844-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="90844-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="90844-108">See also</span></span>

- [<span data-ttu-id="90844-109">动画概述</span><span class="sxs-lookup"><span data-stu-id="90844-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="90844-110">创建 3D 场景</span><span class="sxs-lookup"><span data-stu-id="90844-110">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="90844-111">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="90844-111">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="90844-112">转换概述</span><span class="sxs-lookup"><span data-stu-id="90844-112">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="90844-113">使用情节提要为 3D 旋转设置动画效果</span><span class="sxs-lookup"><span data-stu-id="90844-113">Animate a 3-D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="90844-114">使用 Rotation3DAnimation 为 3D 旋转设置动画效果</span><span class="sxs-lookup"><span data-stu-id="90844-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
