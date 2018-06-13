---
title: 如何：向三维对象应用放射材质
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3-D objects
- 3-D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: da2c8c5d488afd02b50cfeee70048e6fa619248c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559412"
---
# <a name="how-to-apply-emissive-material-to-a-3-d-object"></a>如何：向三维对象应用放射材质
下面的示例演示如何使用<xref:System.Windows.Media.Media3D.EmissiveMaterial>将颜色添加到现有材料等于 EmissiveMaterial 的画笔的颜色。 下面的代码显示<xref:System.Windows.Media.Media3D.DiffuseMaterial>和<xref:System.Windows.Media.Media3D.EmissiveMaterial>应用中进行组合，以将蓝色添加到 DiffuseMaterial 的外观。  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 在过程代码中：  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a>示例  
 下面的代码演示了整个示例在 XAML 中。  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a>示例  
 下面是在程序代码中的整个示例。  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a>请参阅  
 [创建 3D 场景](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [3D 图形概述](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [在 3D 场景中为材料属性设置动画效果](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)  
 [向 3D 对象的正面和背面应用材料](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
