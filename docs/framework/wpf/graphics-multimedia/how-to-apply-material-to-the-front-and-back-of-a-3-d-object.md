---
title: "如何：向三维对象的正面和背面应用 Material"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 3-D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3-D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c5ead8805c3d16bc16e259bdf90a19f05500563c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a><span data-ttu-id="a51c5-102">如何：向三维对象的正面和背面应用 Material</span><span class="sxs-lookup"><span data-stu-id="a51c5-102">How to: Apply Material to the Front and Back of a 3-D Object</span></span>
<span data-ttu-id="a51c5-103">下面的示例演示如何将应用<xref:System.Windows.Media.Media3D.Material>到前面和后面一个三维对象，并对要显示对象的两侧的对象进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="a51c5-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3-D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="a51c5-104"><xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A>属性<xref:System.Windows.Media.Media3D.GeometryModel3D>用于将应用一个红色<xref:System.Windows.Media.Brush>到对象的前端和<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>属性<xref:System.Windows.Media.Media3D.GeometryModel3D>用于应用蓝色<xref:System.Windows.Media.Brush>到后端的对象。</span><span class="sxs-lookup"><span data-stu-id="a51c5-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="a51c5-105">下面的代码显示的材料到对象的应用程序：</span><span class="sxs-lookup"><span data-stu-id="a51c5-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="a51c5-106">示例</span><span class="sxs-lookup"><span data-stu-id="a51c5-106">Example</span></span>  
 <span data-ttu-id="a51c5-107">下面的代码演示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="a51c5-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a51c5-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="a51c5-108">See Also</span></span>  
 [<span data-ttu-id="a51c5-109">创建 3D 场景</span><span class="sxs-lookup"><span data-stu-id="a51c5-109">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="a51c5-110">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="a51c5-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="a51c5-111">在 3D 场景中为材料属性设置动画效果</span><span class="sxs-lookup"><span data-stu-id="a51c5-111">Animate Material Properties in a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)  
 [<span data-ttu-id="a51c5-112">向 3D 对象应用放射材料</span><span class="sxs-lookup"><span data-stu-id="a51c5-112">Apply Emissive Material to a 3-D Object</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)
