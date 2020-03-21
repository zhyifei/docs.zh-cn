---
title: 如何：变换 3D 模型的比例
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3D objects
- 3D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: be41a0e10929912c1b54bf7140d743d9453199bf
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111980"
---
# <a name="how-to-transform-the-scale-of-a-3d-model"></a>如何：变换 3D 模型的比例
此示例演示如何缩放 3D 对象。 要缩放 3D 对象，请使用<xref:System.Windows.Media.Media3D.ScaleTransform3D>。 和<xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A><xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A><xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A>属性按指定的因子调整元素的大小。 例如，<xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>值 1.5 将对象拉伸到其原始宽度的 150%。 值<xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>0.5 将对象的高度缩小 50%。 下面的代码显示使用 作为<xref:System.Windows.Media.Media3D.ScaleTransform3D>转换。 <xref:System.Windows.Media.Media3D.GeometryModel3D>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a>示例  
 以下代码显示整个示例。  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- [动画 3D 翻译](how-to-animate-3-d-translations.md)
- [创建 3D 场景](how-to-create-a-3-d-scene.md)
- [3D 图形概述](3-d-graphics-overview.md)
