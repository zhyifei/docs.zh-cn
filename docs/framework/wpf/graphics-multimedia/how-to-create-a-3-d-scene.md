---
title: 如何：创建 3D 场景
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3D
- 3D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 36453894e06e7b59f339c21713449140c17f6851
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112097"
---
# <a name="how-to-create-a-3d-scene"></a>如何：创建 3D 场景
此示例演示如何创建看起来像已旋转的平面纸张的 3D 对象。 A<xref:System.Windows.Controls.Viewport3D>与以下组件一起用于创建这个简单的 3D 场景：  
  
- 使用 创建摄像机<xref:System.Windows.Media.Media3D.PerspectiveCamera>。 摄像机指定 3D 场景的哪些部分是可查看的。  
  
- 创建网格是为了使用<xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A>的属性指定 3D 对象（纸张）的形状。 <xref:System.Windows.Media.Media3D.GeometryModel3D>  
  
- 指定材质用于使用<xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A><xref:System.Windows.Media.Media3D.GeometryModel3D>的属性显示在对象表面（此示例中的线性渐变）。  
  
- 创建一个光来使用<xref:System.Windows.Media.Media3D.DirectionalLight>在对象上发光。  
  
## <a name="example"></a>示例  
 下面的代码显示了如何在 XAML 中创建 3D 场景。  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a>示例  
 下面的代码演示如何在过程代码中创建相同的 3D 场景。  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- [3D 图形概述](3-d-graphics-overview.md)
