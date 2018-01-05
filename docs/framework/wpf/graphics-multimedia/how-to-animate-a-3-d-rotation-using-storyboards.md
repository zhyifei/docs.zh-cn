---
title: "如何：使用演示图板对三维旋转进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aa67db777ee04edcafa6ca3a53a37a638992fe29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a><span data-ttu-id="cacba-102">如何：使用演示图板对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="cacba-102">How to: Animate a 3-D Rotation Using Storyboards</span></span>
<span data-ttu-id="cacba-103">下面的示例演示如何使旋转时它"松动"通过进行动画处理的三维对象<xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A>和<xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A>属性<xref:System.Windows.Media.Media3D.AxisAngleRotation3D>对象。</span><span class="sxs-lookup"><span data-stu-id="cacba-103">The following example shows how to make a 3D object rotate while it "wobbles" by animating the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> and <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> properties of an <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object.</span></span> <span data-ttu-id="cacba-104">这<xref:System.Windows.Media.Media3D.AxisAngleRotation3D>对象指定旋转转换三维对象，并因此对其属性进行动画处理创建所需旋转效果。</span><span class="sxs-lookup"><span data-stu-id="cacba-104">This <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object specifies the rotation transform of the 3D object and so animating its properties creates the desire rotation effect.</span></span> <span data-ttu-id="cacba-105">在情节提要，<xref:System.Windows.Media.Animation.DoubleAnimation>用于进行动画处理<xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A>属性中的，而<xref:System.Windows.Media.Animation.Vector3DAnimation>用于进行动画处理<xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="cacba-105">Within the Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> property while <xref:System.Windows.Media.Animation.Vector3DAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cacba-106">示例</span><span class="sxs-lookup"><span data-stu-id="cacba-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="cacba-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="cacba-107">See Also</span></span>  
 [<span data-ttu-id="cacba-108">使用 Rotation3DAnimation 为 3D 旋转设置动画效果</span><span class="sxs-lookup"><span data-stu-id="cacba-108">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [<span data-ttu-id="cacba-109">使用关键帧为 3D 旋转设置动画效果 (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="cacba-109">Animate a 3-D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)  
 [<span data-ttu-id="cacba-110">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="cacba-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="cacba-111">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="cacba-111">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
