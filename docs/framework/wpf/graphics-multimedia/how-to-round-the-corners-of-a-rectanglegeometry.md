---
title: "如何：圆化 RectangleGeometry 的角"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cd857f7ce886095bcbe92ae57c350ce83bb5c7d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a><span data-ttu-id="3a697-102">如何：圆化 RectangleGeometry 的角</span><span class="sxs-lookup"><span data-stu-id="3a697-102">How to: Round the Corners of a RectangleGeometry</span></span>
<span data-ttu-id="3a697-103">改为圆角的<xref:System.Windows.Media.RectangleGeometry>，将其<xref:System.Windows.Media.RectangleGeometry.RadiusX%2A>和<xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>属性设置为大于零的值。</span><span class="sxs-lookup"><span data-stu-id="3a697-103">To round the corners of a <xref:System.Windows.Media.RectangleGeometry>, set its <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> properties to a value greater than zero.</span></span> <span data-ttu-id="3a697-104">值越大，1 之间的矩形的角。</span><span class="sxs-lookup"><span data-stu-id="3a697-104">The larger the values, the rounder the rectangle's corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a697-105">示例</span><span class="sxs-lookup"><span data-stu-id="3a697-105">Example</span></span>  
 <span data-ttu-id="3a697-106">下面的示例显示了几个<xref:System.Windows.Media.RectangleGeometry>具有不同的对象<xref:System.Windows.Media.RectangleGeometry.RadiusX%2A>和<xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>设置。</span><span class="sxs-lookup"><span data-stu-id="3a697-106">The following example shows several <xref:System.Windows.Media.RectangleGeometry> objects with different <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> settings.</span></span> <span data-ttu-id="3a697-107"><xref:System.Windows.Media.RectangleGeometry>对象将显示使用<xref:System.Windows.Shapes.Path>元素。</span><span class="sxs-lookup"><span data-stu-id="3a697-107">The <xref:System.Windows.Media.RectangleGeometry> objects are displayed using <xref:System.Windows.Shapes.Path> elements.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 <span data-ttu-id="3a697-108">![使用不同的 RadiusX &#47; 的矩形RadiusY 设置](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")</span><span class="sxs-lookup"><span data-stu-id="3a697-108">![Rectangles with different RadiusX&#47;RadiusY settings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")</span></span>  
<span data-ttu-id="3a697-109">圆角矩形</span><span class="sxs-lookup"><span data-stu-id="3a697-109">Rectangles with Rounded Corners</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a697-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a697-110">See Also</span></span>  
 [<span data-ttu-id="3a697-111">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="3a697-111">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="3a697-112">创建复合形状</span><span class="sxs-lookup"><span data-stu-id="3a697-112">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="3a697-113">使用 PathGeometry 创建形状</span><span class="sxs-lookup"><span data-stu-id="3a697-113">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
