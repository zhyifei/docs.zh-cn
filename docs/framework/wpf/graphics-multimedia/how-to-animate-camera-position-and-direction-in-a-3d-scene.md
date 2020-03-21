---
title: 如何：在三维场景中对照相机位置和方向进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera position in 3D scenes
- camera direction [WPF], animating in 3D scenes
- 3D scenes [WPF], animating camera position
- 3D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3D scenes
- animation [WPF], camera direction in 3D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
ms.openlocfilehash: 5ce94e154cd5aa29b59260f893ec2b63a08db0fc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112202"
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a><span data-ttu-id="afcf7-102">如何：在三维场景中对照相机位置和方向进行动画处理</span><span class="sxs-lookup"><span data-stu-id="afcf7-102">How to: Animate Camera Position and Direction in a 3D Scene</span></span>
<span data-ttu-id="afcf7-103">下面的示例演示如何为摄像机的位置设置动画，并为它在 3D 场景中指向的方向设置动画。</span><span class="sxs-lookup"><span data-stu-id="afcf7-103">The following example shows how to animate the position of a camera and animate the direction it is pointing in a 3D scene.</span></span> <span data-ttu-id="afcf7-104">这是通过使用<xref:System.Windows.Media.Animation.Point3DAnimation>和<xref:System.Windows.Media.Animation.Vector3DAnimation>分别为<xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A>和<xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A>属性设置动画来完成<xref:System.Windows.Media.Media3D.PerspectiveCamera>的。</span><span class="sxs-lookup"><span data-stu-id="afcf7-104">This is done by using <xref:System.Windows.Media.Animation.Point3DAnimation> and <xref:System.Windows.Media.Animation.Vector3DAnimation> to animate the <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> and <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> properties respectively of the <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="afcf7-105">您可以使用这样的动画来更改旁观者对场景的视图，以响应事件。</span><span class="sxs-lookup"><span data-stu-id="afcf7-105">You might use an animation like this to change the onlooker's view of a scene in response to an event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afcf7-106">示例</span><span class="sxs-lookup"><span data-stu-id="afcf7-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="afcf7-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="afcf7-107">See also</span></span>

- <xref:System.Windows.Media.Animation.Vector3DAnimation>
- <xref:System.Windows.Media.Animation.Point3DAnimation>
- [<span data-ttu-id="afcf7-108">使用关键帧为照相机位置和方向设置动画效果</span><span class="sxs-lookup"><span data-stu-id="afcf7-108">Animate Camera Position and Direction Using Key Frames</span></span>](how-to-animate-camera-position-and-direction-using-key-frames.md)
- [<span data-ttu-id="afcf7-109">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="afcf7-109">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
