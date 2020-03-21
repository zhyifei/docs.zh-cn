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
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3d-object"></a>如何：将材质应用于 3D 对象的正面和背面
下面的示例演示如何将 应用于<xref:System.Windows.Media.Media3D.Material>3D 对象的正面和背面，并为对象设置动画以显示对象的两侧。 的属性<xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A><xref:System.Windows.Media.Media3D.GeometryModel3D><xref:System.Windows.Media.Brush>用于将红色应用于对象的正面，<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>而 属性<xref:System.Windows.Media.Media3D.GeometryModel3D>用于将蓝色<xref:System.Windows.Media.Brush>应用于对象的背面。 下面的代码显示了材料在对象中的应用：  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a>示例  
 以下代码显示整个示例。  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- [创建 3D 场景](how-to-create-a-3-d-scene.md)
- [3D 图形概述](3-d-graphics-overview.md)
- [在 3D 场景中设置材质属性的动画](how-to-animate-material-properties-in-a-3-d-scene.md)
- [将透射材料应用于 3D 对象](how-to-apply-emissive-material-to-a-3-d-object.md)
