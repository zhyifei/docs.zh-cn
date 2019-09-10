---
title: 如何：向三维模型应用绘图
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 14470d0adeb948ea46a0720b5713c20fb7d8e6d8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855878"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a>如何：向三维模型应用绘图

此示例演示如何使用<xref:System.Windows.Media.DrawingBrush>作为应用于三维模型的。 <xref:System.Windows.Media.Media3D.Material>

下面的代码将定义<xref:System.Windows.Media.DrawingGroup>为的内容。 <xref:System.Windows.Media.DrawingBrush>  设置为应用于三维平面的的<xref:System.Windows.Media.Media3D.DiffuseMaterial> 属性。<xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> <xref:System.Windows.Media.DrawingBrush>

> [!NOTE]
> 通常需要将复杂对象和值（如下面的绘图）定义为可重复使用的资源，并简化你的代码。 有关详细信息，请参阅[XAML 资源](../advanced/xaml-resources.md)。

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>示例

下面的代码显示了整个示例。

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>请参阅

- [XAML 资源](../advanced/xaml-resources.md)
- [创建 3D 场景](how-to-create-a-3-d-scene.md)
- [Drawing 对象概述](drawing-objects-overview.md)
- [3D 图形概述](3-d-graphics-overview.md)
