---
title: "在 GDI+ 中限制绘制图面"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b7834c95959972e7264e1caa2cfc21b190341b21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="restricting-the-drawing-surface-in-gdi"></a><span data-ttu-id="3e040-102">在 GDI+ 中限制绘制图面</span><span class="sxs-lookup"><span data-stu-id="3e040-102">Restricting the Drawing Surface in GDI+</span></span>
<span data-ttu-id="3e040-103">剪辑涉及将绘制限制为某些矩形或区域。</span><span class="sxs-lookup"><span data-stu-id="3e040-103">Clipping involves restricting drawing to a certain rectangle or region.</span></span> <span data-ttu-id="3e040-104">下图显示字符串"Hello"剪辑到心形区域。</span><span class="sxs-lookup"><span data-stu-id="3e040-104">The following illustration shows the string "Hello" clipped to a heart-shaped region.</span></span>  
  
 <span data-ttu-id="3e040-105">![受限绘制图面](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span><span class="sxs-lookup"><span data-stu-id="3e040-105">![Restricted Drawing Surface](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span></span>  
  
## <a name="clipping-with-regions"></a><span data-ttu-id="3e040-106">区域使用剪辑</span><span class="sxs-lookup"><span data-stu-id="3e040-106">Clipping with Regions</span></span>  
 <span data-ttu-id="3e040-107">区域可以构造从路径，并且路径可以包含的字符串，概述了，因此你可用于剪辑的轮廓包围的文本。</span><span class="sxs-lookup"><span data-stu-id="3e040-107">Regions can be constructed from paths, and paths can contain the outlines of strings, so you can use outlined text for clipping.</span></span> <span data-ttu-id="3e040-108">下图显示了一套同心省略号剪辑到的文本字符串的内部。</span><span class="sxs-lookup"><span data-stu-id="3e040-108">The following illustration shows a set of concentric ellipses clipped to the interior of a string of text.</span></span>  
  
 <span data-ttu-id="3e040-109">![受限绘制图面](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span><span class="sxs-lookup"><span data-stu-id="3e040-109">![Restricted Drawing Surface](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span></span>  
  
 <span data-ttu-id="3e040-110">若要绘制与剪辑，创建<xref:System.Drawing.Graphics>对象，设置其<xref:System.Drawing.Graphics.Clip%2A>属性，然后调用绘制方法相同<xref:System.Drawing.Graphics>对象：</span><span class="sxs-lookup"><span data-stu-id="3e040-110">To draw with clipping, create a <xref:System.Drawing.Graphics> object, set its <xref:System.Drawing.Graphics.Clip%2A> property, and then call the drawing methods of that same <xref:System.Drawing.Graphics> object:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#91](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a><span data-ttu-id="3e040-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e040-111">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [<span data-ttu-id="3e040-112">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="3e040-112">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="3e040-113">使用区域</span><span class="sxs-lookup"><span data-stu-id="3e040-113">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)
