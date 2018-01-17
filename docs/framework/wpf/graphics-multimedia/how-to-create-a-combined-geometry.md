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
# <a name="how-to-create-a-combined-geometry"></a>如何：创建组合的几何图形
此示例演示如何组合几何图形。 若要合并两个几何图形，使用<xref:System.Windows.Media.CombinedGeometry>对象。 设置其<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>具有两个几何图形合并，并设置属性<xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A>属性，确定如何几何图形将组合在一起，到`Union`， `Intersect`， `Exclude`，或`Xor`.  
  
 若要从两个或多个几何图形中创建的复合几何图形，使用<xref:System.Windows.Media.GeometryGroup>。  
  
## <a name="example"></a>示例  
 在下面的示例中，<xref:System.Windows.Media.CombinedGeometry>几何图形组合模式的定义`Exclude`。  同时<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>定义圆的半径相同，但是中心偏移量为 50。  
  
 [!code-xaml[GeometrySample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 ![组合模式的排除结果](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")  
合并后的几何图形排除  
  
 在下列标记中，<xref:System.Windows.Media.CombinedGeometry>组合模式的定义`Intersect`。  同时<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>定义圆的半径相同，但是中心偏移量为 50。  
  
 [!code-xaml[GeometrySample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 ![组合模式的 Intersect 结果](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")  
合并后的几何图形相交  
  
 在下列标记中，<xref:System.Windows.Media.CombinedGeometry>组合模式的定义`Union`。  同时<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>定义圆的半径相同，但是中心偏移量为 50。  
  
 [!code-xaml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Results of the Union combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
合并后的几何图形联合  
  
 在下列标记中，<xref:System.Windows.Media.CombinedGeometry>组合模式的定义`Xor`。  同时<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>定义圆的半径相同，但是中心偏移量为 50。  
  
 [!code-xaml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Results of the Xor combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
合并后的几何图形 Xor
