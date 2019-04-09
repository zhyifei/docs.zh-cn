---
title: 如何：向三维模型应用绘图
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: a20b89a7359fc85d9790ac02dd2b173452df8c22
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125029"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="28b32-102">如何：向三维模型应用绘图</span><span class="sxs-lookup"><span data-stu-id="28b32-102">How to: Apply a Drawing to a 3-D Model</span></span>
<span data-ttu-id="28b32-103">此示例演示如何使用<xref:System.Windows.Media.DrawingBrush>作为<xref:System.Windows.Media.Media3D.Material>应用于[!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)]模型。</span><span class="sxs-lookup"><span data-stu-id="28b32-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="28b32-104">下面的代码定义<xref:System.Windows.Media.DrawingGroup>的内容作为<xref:System.Windows.Media.DrawingBrush>。</span><span class="sxs-lookup"><span data-stu-id="28b32-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="28b32-105"><xref:System.Windows.Media.DrawingBrush>设置为<xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A>的属性<xref:System.Windows.Media.Media3D.DiffuseMaterial>应用于[!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]平面。</span><span class="sxs-lookup"><span data-stu-id="28b32-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] plane.</span></span>  
  
 <span data-ttu-id="28b32-106">**注意：** 通常是需要复杂的对象和值，如下面的绘图定义为资源可以重复使用并简化你的代码。</span><span class="sxs-lookup"><span data-stu-id="28b32-106">**Note:** It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="28b32-107">请参阅[XAML 资源](../advanced/xaml-resources.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="28b32-107">See [XAML Resources](../advanced/xaml-resources.md) for more information.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## <a name="example"></a><span data-ttu-id="28b32-108">示例</span><span class="sxs-lookup"><span data-stu-id="28b32-108">Example</span></span>  
 <span data-ttu-id="28b32-109">下面的代码演示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="28b32-109">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="28b32-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="28b32-110">See also</span></span>

- [<span data-ttu-id="28b32-111">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="28b32-111">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="28b32-112">创建三维场景</span><span class="sxs-lookup"><span data-stu-id="28b32-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="28b32-113">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="28b32-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="28b32-114">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="28b32-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
