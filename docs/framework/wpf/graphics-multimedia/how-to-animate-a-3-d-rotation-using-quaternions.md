---
title: "如何：使用四元数对三维旋转进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3-D translations [WPF], with quaternions
- 3-D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4301f4ffc935c6c72509638561ffa40b7744b94a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-3-d-rotation-using-quaternions"></a><span data-ttu-id="cbc1e-102">如何：使用四元数对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="cbc1e-102">How to: Animate a 3-D Rotation Using Quaternions</span></span>
<span data-ttu-id="cbc1e-103">此示例演示如何进行动画处理的三维对象使用四元数旋转。</span><span class="sxs-lookup"><span data-stu-id="cbc1e-103">This example shows how to animate a rotation of a 3-D object using quaternions.</span></span>  
  
 <span data-ttu-id="cbc1e-104">下面的代码显示<xref:System.Windows.Media.Media3D.QuaternionRotation3D>用作的值<xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A>属性<xref:System.Windows.Media.Media3D.RotateTransform3D>。</span><span class="sxs-lookup"><span data-stu-id="cbc1e-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="cbc1e-105">这<xref:System.Windows.Media.Media3D.QuaternionRotation3D>进行动画处理<xref:System.Windows.Media.Animation.QuaternionAnimation>内<xref:System.Windows.Media.Animation.Storyboard>使用下面的代码。</span><span class="sxs-lookup"><span data-stu-id="cbc1e-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="cbc1e-106">示例</span><span class="sxs-lookup"><span data-stu-id="cbc1e-106">Example</span></span>  
 <span data-ttu-id="cbc1e-107">下面的代码演示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="cbc1e-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="cbc1e-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="cbc1e-108">See Also</span></span>  
 [<span data-ttu-id="cbc1e-109">动画概述</span><span class="sxs-lookup"><span data-stu-id="cbc1e-109">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="cbc1e-110">创建 3D 场景</span><span class="sxs-lookup"><span data-stu-id="cbc1e-110">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="cbc1e-111">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="cbc1e-111">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="cbc1e-112">转换概述</span><span class="sxs-lookup"><span data-stu-id="cbc1e-112">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="cbc1e-113">使用情节提要为 3D 旋转设置动画效果</span><span class="sxs-lookup"><span data-stu-id="cbc1e-113">Animate a 3-D Rotation Using Storyboards</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [<span data-ttu-id="cbc1e-114">使用 Rotation3DAnimation 为 3D 旋转设置动画效果</span><span class="sxs-lookup"><span data-stu-id="cbc1e-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
