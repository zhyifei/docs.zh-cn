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
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="230a2-102">如何：向三维模型应用绘图</span><span class="sxs-lookup"><span data-stu-id="230a2-102">How to: Apply a Drawing to a 3-D Model</span></span>

<span data-ttu-id="230a2-103">此示例演示如何使用 <xref:System.Windows.Media.DrawingBrush> 作为 <xref:System.Windows.Media.Media3D.Material> 应用于三维模型。</span><span class="sxs-lookup"><span data-stu-id="230a2-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3-D model.</span></span>

<span data-ttu-id="230a2-104">下面的代码将 <xref:System.Windows.Media.DrawingGroup> 定义为 <xref:System.Windows.Media.DrawingBrush>的内容。</span><span class="sxs-lookup"><span data-stu-id="230a2-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="230a2-105"><xref:System.Windows.Media.DrawingBrush> 设置为应用于三维平面的 <xref:System.Windows.Media.Media3D.DiffuseMaterial> 的 <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="230a2-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3-D plane.</span></span>

> [!NOTE]
> <span data-ttu-id="230a2-106">通常需要将复杂对象和值（如下面的绘图）定义为可重复使用的资源，并简化你的代码。</span><span class="sxs-lookup"><span data-stu-id="230a2-106">It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="230a2-107">有关详细信息，请参阅[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。</span><span class="sxs-lookup"><span data-stu-id="230a2-107">See [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) for more information.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a><span data-ttu-id="230a2-108">示例</span><span class="sxs-lookup"><span data-stu-id="230a2-108">Example</span></span>

<span data-ttu-id="230a2-109">下面的代码显示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="230a2-109">The following code shows the entire sample.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="230a2-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="230a2-110">See also</span></span>

- [<span data-ttu-id="230a2-111">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="230a2-111">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="230a2-112">创建 3D 场景</span><span class="sxs-lookup"><span data-stu-id="230a2-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="230a2-113">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="230a2-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="230a2-114">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="230a2-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
