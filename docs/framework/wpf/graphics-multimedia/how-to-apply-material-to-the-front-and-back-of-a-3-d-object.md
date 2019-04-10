---
title: 如何：向三维对象的正面和背面应用 Material
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3-D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 1d3f6a0622b5e0ccccf14af99782bb78dfe87ccb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168046"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a><span data-ttu-id="eab08-102">如何：向三维对象的正面和背面应用 Material</span><span class="sxs-lookup"><span data-stu-id="eab08-102">How to: Apply Material to the Front and Back of a 3-D Object</span></span>
<span data-ttu-id="eab08-103">下面的示例演示如何应用<xref:System.Windows.Media.Media3D.Material>到前面和背面三维对象，并对要显示对象的两侧的对象进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="eab08-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3-D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="eab08-104"><xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A>的属性<xref:System.Windows.Media.Media3D.GeometryModel3D>用于将应用一个红色<xref:System.Windows.Media.Brush>到对象的正面和<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>属性<xref:System.Windows.Media.Media3D.GeometryModel3D>用于将应用一个蓝色<xref:System.Windows.Media.Brush>到后端的对象。</span><span class="sxs-lookup"><span data-stu-id="eab08-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="eab08-105">下面的代码显示了应用到该对象的材料：</span><span class="sxs-lookup"><span data-stu-id="eab08-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="eab08-106">示例</span><span class="sxs-lookup"><span data-stu-id="eab08-106">Example</span></span>  
 <span data-ttu-id="eab08-107">下面的代码演示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="eab08-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="eab08-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="eab08-108">See also</span></span>

- [<span data-ttu-id="eab08-109">创建三维场景</span><span class="sxs-lookup"><span data-stu-id="eab08-109">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="eab08-110">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="eab08-110">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="eab08-111">在三维场景中对材料属性进行动画处理</span><span class="sxs-lookup"><span data-stu-id="eab08-111">Animate Material Properties in a 3-D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="eab08-112">向三维对象应用放射材料</span><span class="sxs-lookup"><span data-stu-id="eab08-112">Apply Emissive Material to a 3-D Object</span></span>](how-to-apply-emissive-material-to-a-3-d-object.md)
