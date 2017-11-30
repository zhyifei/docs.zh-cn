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
ms.openlocfilehash: ce4605208be264418088399253298798205c3f9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a>如何：向三维对象的正面和背面应用 Material
下面的示例演示如何将应用<xref:System.Windows.Media.Media3D.Material>到前面和后面一个三维对象，并对要显示对象的两侧的对象进行动画处理。 <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A>属性<xref:System.Windows.Media.Media3D.GeometryModel3D>用于将应用一个红色<xref:System.Windows.Media.Brush>到对象的前端和<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>属性<xref:System.Windows.Media.Media3D.GeometryModel3D>用于应用蓝色<xref:System.Windows.Media.Brush>到后端的对象。 下面的代码显示的材料到对象的应用程序：  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a>示例  
 下面的代码演示了整个示例。  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅  
 [创建 3D 场景](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [3D 图形概述](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [在 3D 场景中为材料属性设置动画效果](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)  
 [向 3D 对象应用放射材料](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)
