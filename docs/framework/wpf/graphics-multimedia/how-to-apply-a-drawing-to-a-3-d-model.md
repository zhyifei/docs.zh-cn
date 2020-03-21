---
title: 如何：将绘图应用于 3D 模型
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3D models
- 3D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 5b10630ab674fa9489cdf7ad53516a680f19da08
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112175"
---
# <a name="how-to-apply-a-drawing-to-a-3d-model"></a>如何：将绘图应用于 3D 模型

此示例演示如何将<xref:System.Windows.Media.DrawingBrush><xref:System.Windows.Media.Media3D.Material>

以下代码将 定义为<xref:System.Windows.Media.DrawingGroup>的内容。 <xref:System.Windows.Media.DrawingBrush>  <xref:System.Windows.Media.DrawingBrush><xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A>设置为<xref:System.Windows.Media.Media3D.DiffuseMaterial>应用于 3D 平面的属性。

> [!NOTE]
> 通常，最好将复杂的对象和值（如下图）定义为可以重用和简化代码的资源。 有关详细信息，请参阅[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>示例

以下代码显示整个示例。

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>另请参阅

- [XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [创建 3D 场景](how-to-create-a-3-d-scene.md)
- [Drawing 对象概述](drawing-objects-overview.md)
- [3D 图形概述](3-d-graphics-overview.md)
