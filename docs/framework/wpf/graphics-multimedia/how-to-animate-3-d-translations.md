---
title: 如何：动画 3D 翻译
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations
- 3D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 7d4fff9c74663bd220ad5d15a983bcb639621afd
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112253"
---
# <a name="how-to-animate-3d-translations"></a>如何：动画 3D 翻译
本主题演示如何在 3D 模型上为转换转换集设置动画。  
  
 下面的代码显示了<xref:System.Windows.Media.Media3D.TranslateTransform3D>对象对<xref:System.Windows.Media.Media3D.Model3D.Transform%2A>属性<xref:System.Windows.Media.Media3D.GeometryModel3D>的应用。  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 此<xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A><xref:System.Windows.Media.Media3D.TranslateTransform3D>对象的属性使用以下代码进行动画处理。  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a>示例  
 以下代码显示整个示例。  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- [动画概述](animation-overview.md)
- [创建 3D 场景](how-to-create-a-3-d-scene.md)
- [3D 图形概述](3-d-graphics-overview.md)
- [转换概述](transforms-overview.md)
