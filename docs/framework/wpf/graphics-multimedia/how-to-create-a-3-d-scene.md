---
title: 如何：创建三维场景
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: e3c2ea803961ca57606f8ea8bec21d50a38dbe1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559521"
---
# <a name="how-to-create-a-3-d-scene"></a>如何：创建三维场景
此示例演示如何创建看起来像平面纸已转动的一个三维对象。 A<xref:System.Windows.Controls.Viewport3D>以下组件以及用于创建此简单的三维场景：  
  
-   使用创建相机<xref:System.Windows.Media.Media3D.PerspectiveCamera>。 照相机指定三维场景的哪个部分可查看。  
  
-   创建一个网格，以指定的三维对象 （张纸） 使用形状<xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A>属性<xref:System.Windows.Media.Media3D.GeometryModel3D>。  
  
-   材料指定要显示在对象 （线性渐变在此示例中） 使用的图面上<xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A>属性<xref:System.Windows.Media.Media3D.GeometryModel3D>。  
  
-   Light 创建对象使用表现<xref:System.Windows.Media.Media3D.DirectionalLight>。  
  
## <a name="example"></a>示例  
 下面的代码演示如何在 XAML 中创建三维场景。  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a>示例  
 下面的代码演示如何在程序代码中创建相同的三维场景。  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a>请参阅  
 [3D 图形概述](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
