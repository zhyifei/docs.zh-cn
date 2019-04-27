---
title: 如何：创建组合的几何图形
ms.date: 03/30/2017
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
ms.openlocfilehash: c5ebe87abd4c2cf70f8fa17f1fcc773293f3ad27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910077"
---
# <a name="how-to-create-a-combined-geometry"></a><span data-ttu-id="8689d-102">如何：创建组合的几何图形</span><span class="sxs-lookup"><span data-stu-id="8689d-102">How to: Create a Combined Geometry</span></span>
<span data-ttu-id="8689d-103">此示例演示如何合并几何图形。</span><span class="sxs-lookup"><span data-stu-id="8689d-103">This example shows how to combine geometries.</span></span> <span data-ttu-id="8689d-104">若要组合两个几何图形，使用<xref:System.Windows.Media.CombinedGeometry>对象。</span><span class="sxs-lookup"><span data-stu-id="8689d-104">To combine two geometries, use a <xref:System.Windows.Media.CombinedGeometry> object.</span></span> <span data-ttu-id="8689d-105">设置其<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>具有两个几何图形以组合和设置的属性<xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A>属性，用于确定如何将一起组合几何图形，到`Union`， `Intersect`， `Exclude`，或者`Xor`.</span><span class="sxs-lookup"><span data-stu-id="8689d-105">Set its <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> properties  with the two geometries to combine, and set the <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> property, which determines how the geometries will be combined together, to `Union`, `Intersect`, `Exclude`, or `Xor`.</span></span>  
  
 <span data-ttu-id="8689d-106">若要从两个或多个几何图形中创建的复合几何图形，请使用<xref:System.Windows.Media.GeometryGroup>。</span><span class="sxs-lookup"><span data-stu-id="8689d-106">To create a composite geometry from two or more geometries, use a <xref:System.Windows.Media.GeometryGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8689d-107">示例</span><span class="sxs-lookup"><span data-stu-id="8689d-107">Example</span></span>  
 <span data-ttu-id="8689d-108">在以下示例中，<xref:System.Windows.Media.CombinedGeometry>使用的几何图形合并模式定义`Exclude`。</span><span class="sxs-lookup"><span data-stu-id="8689d-108">In the following example, a <xref:System.Windows.Media.CombinedGeometry> is defined with a geometry combine mode of `Exclude`.</span></span>  <span data-ttu-id="8689d-109">这两<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>定义为圆的半径相同，但中心偏移 50。</span><span class="sxs-lookup"><span data-stu-id="8689d-109">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 <span data-ttu-id="8689d-110">![组合模式的排除结果](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span><span class="sxs-lookup"><span data-stu-id="8689d-110">![Results of the Exclude combine mode](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span></span>  
<span data-ttu-id="8689d-111">组合的几何图形排除</span><span class="sxs-lookup"><span data-stu-id="8689d-111">Combined Geometry Exclude</span></span>  
  
 <span data-ttu-id="8689d-112">在下列标记中，<xref:System.Windows.Media.CombinedGeometry>使用的合并模式定义`Intersect`。</span><span class="sxs-lookup"><span data-stu-id="8689d-112">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Intersect`.</span></span>  <span data-ttu-id="8689d-113">这两<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>定义为圆的半径相同，但中心偏移 50。</span><span class="sxs-lookup"><span data-stu-id="8689d-113">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 <span data-ttu-id="8689d-114">![组合模式的 Intersect 结果](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span><span class="sxs-lookup"><span data-stu-id="8689d-114">![Results of the Intersect combine mode](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span></span>  
<span data-ttu-id="8689d-115">组合的几何图形相交</span><span class="sxs-lookup"><span data-stu-id="8689d-115">Combined Geometry Intersect</span></span>  
  
 <span data-ttu-id="8689d-116">在下列标记中，<xref:System.Windows.Media.CombinedGeometry>使用的合并模式定义`Union`。</span><span class="sxs-lookup"><span data-stu-id="8689d-116">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Union`.</span></span>  <span data-ttu-id="8689d-117">这两<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>定义为圆的半径相同，但中心偏移 50。</span><span class="sxs-lookup"><span data-stu-id="8689d-117">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 <span data-ttu-id="8689d-118">![Results of the Union combine mode](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="8689d-118">![Results of the Union combine mode](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span></span>  
<span data-ttu-id="8689d-119">组合的几何图形并集</span><span class="sxs-lookup"><span data-stu-id="8689d-119">Combined Geometry Union</span></span>  
  
 <span data-ttu-id="8689d-120">在下列标记中，<xref:System.Windows.Media.CombinedGeometry>使用的合并模式定义`Xor`。</span><span class="sxs-lookup"><span data-stu-id="8689d-120">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Xor`.</span></span>  <span data-ttu-id="8689d-121">这两<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>定义为圆的半径相同，但中心偏移 50。</span><span class="sxs-lookup"><span data-stu-id="8689d-121">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 <span data-ttu-id="8689d-122">![Results of the Xor combine mode](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span><span class="sxs-lookup"><span data-stu-id="8689d-122">![Results of the Xor combine mode](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span></span>  
<span data-ttu-id="8689d-123">组合的几何图形 Xor</span><span class="sxs-lookup"><span data-stu-id="8689d-123">Combined Geometry Xor</span></span>
