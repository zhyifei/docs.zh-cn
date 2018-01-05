---
title: "如何：使用径向渐变绘制区域"
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
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f1da933a2ee7c179a55da7d33c61539d440eabc3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a>如何：使用径向渐变绘制区域
此示例演示如何使用<xref:System.Windows.Media.RadialGradientBrush>类，以使用径向渐变绘制区域。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.RadialGradientBrush>来绘制一个具有红色以蓝色和浅绿色从黄色转换的径向渐变的矩形。  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 下图显示了前面示例中的渐变。 其中突出显示的渐变停止点。  
  
 ![径向渐变中的梯度停止点](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")  
  
> [!NOTE]
>  本主题中的示例使用默认坐标系统设置控点。 默认坐标系统是相对于边界框： 0 表示的边界框中，0%和 1 表示 100%的边界框。 你可以通过设置来更改此坐标系<xref:System.Windows.Media.GradientBrush.MappingMode%2A>属性值<xref:System.Windows.Media.BrushMappingMode.Absolute>。 绝对坐标系与范围框无关。 值直接在本地空间中解释。  
  
 有关其他<xref:System.Windows.Media.RadialGradientBrush>示例，请参阅[画笔示例](http://go.microsoft.com/fwlink/?LinkID=159973)。 有关渐变和画笔的其他类型的详细信息，请参阅[使用纯色和渐变概述绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)。
