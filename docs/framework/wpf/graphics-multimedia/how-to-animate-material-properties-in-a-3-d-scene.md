---
title: 如何：在 3D 场景中设置材质属性的动画
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3D scenes
- animation [WPF], Material properties in 3D scenes
- 3D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: db59debcd7558cde52d8604cb04c8c4e68921825
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112188"
---
# <a name="how-to-animate-material-properties-in-a-3d-scene"></a>如何：在 3D 场景中设置材质属性的动画
此示例演示如何为应用于 3D<xref:System.Windows.Media.Brush.Opacity%2A>模型的属性<xref:System.Windows.Media.Media3D.Material>设置动画。  
  
 以下代码示例将<xref:System.Windows.Media.LinearGradientBrush>用作<xref:System.Windows.Media.Media3D.Material>应用于 3D 对象的定义。  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 使用<xref:System.Windows.Media.Brush.Opacity%2A><xref:System.Windows.Media.LinearGradientBrush>下面的代码示例对此的属性进行动画处理。  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a>示例  
 以下代码显示整个示例。  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- [创建 3D 场景](how-to-create-a-3-d-scene.md)
- [3D 图形概述](3-d-graphics-overview.md)
