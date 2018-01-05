---
title: "如何：定义钢笔"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [WPF], defining
- creating [WPF], pens
ms.assetid: 7a4f2900-cdf9-49de-84e0-ba5d0ded4d33
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02a3bef369f5bdd70588f3934e4199d7d4c703f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-pen"></a><span data-ttu-id="35cdf-102">如何：定义钢笔</span><span class="sxs-lookup"><span data-stu-id="35cdf-102">How to: Define a Pen</span></span>
<span data-ttu-id="35cdf-103">此示例演示如何使用<xref:System.Windows.Media.Pen>概述一种形状。</span><span class="sxs-lookup"><span data-stu-id="35cdf-103">This example shows how use a <xref:System.Windows.Media.Pen> to outline a shape.</span></span> <span data-ttu-id="35cdf-104">若要创建一个简单<xref:System.Windows.Media.Pen>，只需指定其<xref:System.Windows.Media.Pen.Thickness%2A>和<xref:System.Windows.Media.Pen.Brush%2A>。</span><span class="sxs-lookup"><span data-stu-id="35cdf-104">To create a simple <xref:System.Windows.Media.Pen>, you need only specify its <xref:System.Windows.Media.Pen.Thickness%2A> and <xref:System.Windows.Media.Pen.Brush%2A>.</span></span> <span data-ttu-id="35cdf-105">你可以通过指定创建更复杂的钢笔<xref:System.Windows.Media.Pen.DashStyle%2A>， <xref:System.Windows.Media.Pen.DashCap%2A>， <xref:System.Windows.Media.Pen.LineJoin%2A>， <xref:System.Windows.Media.Pen.StartLineCap%2A>，和<xref:System.Windows.Media.Pen.EndLineCap%2A>。</span><span class="sxs-lookup"><span data-stu-id="35cdf-105">You can create more complex pen's by specifying a <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A>, and <xref:System.Windows.Media.Pen.EndLineCap%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35cdf-106">示例</span><span class="sxs-lookup"><span data-stu-id="35cdf-106">Example</span></span>  
 <span data-ttu-id="35cdf-107">下面的示例使用<xref:System.Windows.Media.Pen>概述一个形状定义<xref:System.Windows.Media.GeometryDrawing>。</span><span class="sxs-lookup"><span data-stu-id="35cdf-107">The following example uses a <xref:System.Windows.Media.Pen> to outline a shape defined by a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 [!code-csharp[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PenExamples_snip/CSharp/PenExample.cs#penexamplewholepage)]
 [!code-vb[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PenExamples_snip/VisualBasic/PenExample.vb#penexamplewholepage)]  
  
 <span data-ttu-id="35cdf-108">![概述了通过 Pen 产生的](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")</span><span class="sxs-lookup"><span data-stu-id="35cdf-108">![Outlines produces by a Pen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")</span></span>  
<span data-ttu-id="35cdf-109">一个 GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="35cdf-109">A GeometryDrawing</span></span>
