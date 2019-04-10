---
title: 如何：转换三维模型的比例
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3-D objects
- 3-D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: 6d668de08201d819ce9f8752bedf6c388a6bc718
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165075"
---
# <a name="how-to-transform-the-scale-of-a-3-d-model"></a>如何：转换三维模型的比例
此示例演示如何缩放三维对象。 若要缩放三维对象，使用<xref:System.Windows.Media.Media3D.ScaleTransform3D>。 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>， <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>，和<xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A>属性调整元素大小由指定的系数。 例如，<xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>值为 1.5 会拉伸到其原始宽度的 150%的对象。 一个<xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>值为 0.5 会对象的高度缩小 50%。 下面的代码显示使用<xref:System.Windows.Media.Media3D.ScaleTransform3D>的转换为<xref:System.Windows.Media.Media3D.GeometryModel3D>。  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a>示例  
 下面的代码演示了整个示例。  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a>请参阅

- [对三维转换进行动画处理](how-to-animate-3-d-translations.md)
- [创建三维场景](how-to-create-a-3-d-scene.md)
- [三维图形概述](3-d-graphics-overview.md)
