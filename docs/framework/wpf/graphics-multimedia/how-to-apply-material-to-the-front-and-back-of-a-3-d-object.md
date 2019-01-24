---
title: 如何：向三维对象的正面和背面应用 Material
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3-D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 16f30e3a880d7dcc943a9583ba0f04c4bd682827
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652028"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a><span data-ttu-id="a85ae-102">如何：向三维对象的正面和背面应用 Material</span><span class="sxs-lookup"><span data-stu-id="a85ae-102">How to: Apply Material to the Front and Back of a 3-D Object</span></span>
<span data-ttu-id="a85ae-103">下面的示例演示如何应用<xref:System.Windows.Media.Media3D.Material>到前面和背面三维对象，并对要显示对象的两侧的对象进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="a85ae-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3-D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="a85ae-104"><xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A>的属性<xref:System.Windows.Media.Media3D.GeometryModel3D>用于将应用一个红色<xref:System.Windows.Media.Brush>到对象的正面和<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>属性<xref:System.Windows.Media.Media3D.GeometryModel3D>用于将应用一个蓝色<xref:System.Windows.Media.Brush>到后端的对象。</span><span class="sxs-lookup"><span data-stu-id="a85ae-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="a85ae-105">下面的代码显示了应用到该对象的材料：</span><span class="sxs-lookup"><span data-stu-id="a85ae-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="a85ae-106">示例</span><span class="sxs-lookup"><span data-stu-id="a85ae-106">Example</span></span>  
 <span data-ttu-id="a85ae-107">下面的代码演示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="a85ae-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a85ae-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="a85ae-108">See also</span></span>
- [<span data-ttu-id="a85ae-109">创建 3D 场景</span><span class="sxs-lookup"><span data-stu-id="a85ae-109">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="a85ae-110">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="a85ae-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [<span data-ttu-id="a85ae-111">在 3D 场景中为材料属性设置动画效果</span><span class="sxs-lookup"><span data-stu-id="a85ae-111">Animate Material Properties in a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="a85ae-112">向 3D 对象应用放射材料</span><span class="sxs-lookup"><span data-stu-id="a85ae-112">Apply Emissive Material to a 3-D Object</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)
