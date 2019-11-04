---
title: 如何：向三维模型应用绘图
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 311a3ac1d9fa219a3a365d506d9d0c3e8b6bc229
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459368"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a>如何：向三维模型应用绘图

此示例演示如何使用 <xref:System.Windows.Media.DrawingBrush> 作为 <xref:System.Windows.Media.Media3D.Material> 应用于三维模型。

下面的代码将 <xref:System.Windows.Media.DrawingGroup> 定义为 <xref:System.Windows.Media.DrawingBrush>的内容。  <xref:System.Windows.Media.DrawingBrush> 设置为应用于三维平面的 <xref:System.Windows.Media.Media3D.DiffuseMaterial> 的 <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> 属性。

> [!NOTE]
> 通常需要将复杂对象和值（如下面的绘图）定义为可重复使用的资源，并简化你的代码。 有关详细信息，请参阅[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>示例

下面的代码显示了整个示例。

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>请参阅

- [XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [创建 3D 场景](how-to-create-a-3-d-scene.md)
- [Drawing 对象概述](drawing-objects-overview.md)
- [3D 图形概述](3-d-graphics-overview.md)
