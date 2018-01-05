---
title: "如何：创建组合的几何图形"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee77da00604b7e4965cc376748606b6bd0e92ad8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-combined-geometry"></a><span data-ttu-id="5b214-102">如何：创建组合的几何图形</span><span class="sxs-lookup"><span data-stu-id="5b214-102">How to: Create a Combined Geometry</span></span>
<span data-ttu-id="5b214-103">此示例演示如何组合几何图形。</span><span class="sxs-lookup"><span data-stu-id="5b214-103">This example shows how to combine geometries.</span></span> <span data-ttu-id="5b214-104">若要合并两个几何图形，使用<xref:System.Windows.Media.CombinedGeometry>对象。</span><span class="sxs-lookup"><span data-stu-id="5b214-104">To combine two geometries, use a <xref:System.Windows.Media.CombinedGeometry> object.</span></span> <span data-ttu-id="5b214-105">设置其<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>具有两个几何图形合并，并设置属性<xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A>属性，确定如何几何图形将组合在一起，到`Union`， `Intersect`， `Exclude`，或`Xor`.</span><span class="sxs-lookup"><span data-stu-id="5b214-105">Set its <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> properties  with the two geometries to combine, and set the <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> property, which determines how the geometries will be combined together, to `Union`, `Intersect`, `Exclude`, or `Xor`.</span></span>  
  
 <span data-ttu-id="5b214-106">若要从两个或多个几何图形中创建的复合几何图形，使用<xref:System.Windows.Media.GeometryGroup>。</span><span class="sxs-lookup"><span data-stu-id="5b214-106">To create a composite geometry from two or more geometries, use a <xref:System.Windows.Media.GeometryGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b214-107">示例</span><span class="sxs-lookup"><span data-stu-id="5b214-107">Example</span></span>  
 <span data-ttu-id="5b214-108">在下面的示例中，<xref:System.Windows.Media.CombinedGeometry>几何图形组合模式的定义`Exclude`。</span><span class="sxs-lookup"><span data-stu-id="5b214-108">In the following example, a <xref:System.Windows.Media.CombinedGeometry> is defined with a geometry combine mode of `Exclude`.</span></span>  <span data-ttu-id="5b214-109">同时<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>定义圆的半径相同，但是中心偏移量为 50。</span><span class="sxs-lookup"><span data-stu-id="5b214-109">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 <span data-ttu-id="5b214-110">![组合模式的排除结果](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span><span class="sxs-lookup"><span data-stu-id="5b214-110">![Results of the Exclude combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span></span>  
<span data-ttu-id="5b214-111">合并后的几何图形排除</span><span class="sxs-lookup"><span data-stu-id="5b214-111">Combined Geometry Exclude</span></span>  
  
 <span data-ttu-id="5b214-112">在下列标记中，<xref:System.Windows.Media.CombinedGeometry>组合模式的定义`Intersect`。</span><span class="sxs-lookup"><span data-stu-id="5b214-112">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Intersect`.</span></span>  <span data-ttu-id="5b214-113">同时<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>定义圆的半径相同，但是中心偏移量为 50。</span><span class="sxs-lookup"><span data-stu-id="5b214-113">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 <span data-ttu-id="5b214-114">![组合模式的 Intersect 结果](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span><span class="sxs-lookup"><span data-stu-id="5b214-114">![Results of the Intersect combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span></span>  
<span data-ttu-id="5b214-115">合并后的几何图形相交</span><span class="sxs-lookup"><span data-stu-id="5b214-115">Combined Geometry Intersect</span></span>  
  
 <span data-ttu-id="5b214-116">在下列标记中，<xref:System.Windows.Media.CombinedGeometry>组合模式的定义`Union`。</span><span class="sxs-lookup"><span data-stu-id="5b214-116">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Union`.</span></span>  <span data-ttu-id="5b214-117">同时<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>定义圆的半径相同，但是中心偏移量为 50。</span><span class="sxs-lookup"><span data-stu-id="5b214-117">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 <span data-ttu-id="5b214-118">![Results of the Union combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="5b214-118">![Results of the Union combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span></span>  
<span data-ttu-id="5b214-119">合并后的几何图形联合</span><span class="sxs-lookup"><span data-stu-id="5b214-119">Combined Geometry Union</span></span>  
  
 <span data-ttu-id="5b214-120">在下列标记中，<xref:System.Windows.Media.CombinedGeometry>组合模式的定义`Xor`。</span><span class="sxs-lookup"><span data-stu-id="5b214-120">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Xor`.</span></span>  <span data-ttu-id="5b214-121">同时<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>定义圆的半径相同，但是中心偏移量为 50。</span><span class="sxs-lookup"><span data-stu-id="5b214-121">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 <span data-ttu-id="5b214-122">![Results of the Xor combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span><span class="sxs-lookup"><span data-stu-id="5b214-122">![Results of the Xor combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span></span>  
<span data-ttu-id="5b214-123">合并后的几何图形 Xor</span><span class="sxs-lookup"><span data-stu-id="5b214-123">Combined Geometry Xor</span></span>
