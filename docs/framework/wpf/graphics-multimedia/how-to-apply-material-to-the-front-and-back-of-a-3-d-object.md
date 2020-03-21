---
title: 如何：将材质应用于 3D 对象的正面和背面
ms.date: 03/30/2017
helpviewer_keywords:
- 3D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 5c24879d97e7857fb07fcef4a9ba8efa901e4a39
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112136"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3d-object"></a><span data-ttu-id="b44ef-102">如何：将材质应用于 3D 对象的正面和背面</span><span class="sxs-lookup"><span data-stu-id="b44ef-102">How to: Apply Material to the Front and Back of a 3D Object</span></span>
<span data-ttu-id="b44ef-103">下面的示例演示如何将 应用于<xref:System.Windows.Media.Media3D.Material>3D 对象的正面和背面，并为对象设置动画以显示对象的两侧。</span><span class="sxs-lookup"><span data-stu-id="b44ef-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="b44ef-104">的属性<xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A><xref:System.Windows.Media.Media3D.GeometryModel3D><xref:System.Windows.Media.Brush>用于将红色应用于对象的正面，<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>而 属性<xref:System.Windows.Media.Media3D.GeometryModel3D>用于将蓝色<xref:System.Windows.Media.Brush>应用于对象的背面。</span><span class="sxs-lookup"><span data-stu-id="b44ef-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="b44ef-105">下面的代码显示了材料在对象中的应用：</span><span class="sxs-lookup"><span data-stu-id="b44ef-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="b44ef-106">示例</span><span class="sxs-lookup"><span data-stu-id="b44ef-106">Example</span></span>  
 <span data-ttu-id="b44ef-107">以下代码显示整个示例。</span><span class="sxs-lookup"><span data-stu-id="b44ef-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b44ef-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b44ef-108">See also</span></span>

- [<span data-ttu-id="b44ef-109">创建 3D 场景</span><span class="sxs-lookup"><span data-stu-id="b44ef-109">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="b44ef-110">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="b44ef-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="b44ef-111">在 3D 场景中设置材质属性的动画</span><span class="sxs-lookup"><span data-stu-id="b44ef-111">Animate Material Properties in a 3D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="b44ef-112">将透射材料应用于 3D 对象</span><span class="sxs-lookup"><span data-stu-id="b44ef-112">Apply Emissive Material to a 3D Object</span></span>](how-to-apply-emissive-material-to-a-3-d-object.md)
