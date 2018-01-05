---
title: "如何：变换画笔"
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
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ee517eb76877bb4e02c021061055b328597c517
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-transform-a-brush"></a>如何：变换画笔
此示例演示如何将转换<xref:System.Windows.Media.Brush>通过使用其两个转换属性的对象：<xref:System.Windows.Media.Brush.RelativeTransform%2A>和<xref:System.Windows.Media.Brush.Transform%2A>。  
  
 下面的示例使用<xref:System.Windows.Media.RotateTransform>要旋转的内容<xref:System.Windows.Media.ImageBrush>旋转 45 度。  
  
 下图显示<xref:System.Windows.Media.ImageBrush>而无需<xref:System.Windows.Media.RotateTransform>，与<xref:System.Windows.Media.RotateTransform>应用于<xref:System.Windows.Media.Brush.RelativeTransform%2A>属性，且<xref:System.Windows.Media.RotateTransform>应用于<xref:System.Windows.Media.Brush.Transform%2A>属性。  
  
 ![画笔 RelativeTransform 和 Transform 设置](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
## <a name="example"></a>示例  
 第一个示例适用<xref:System.Windows.Media.RotateTransform>到<xref:System.Windows.Media.Brush.RelativeTransform%2A>属性<xref:System.Windows.Media.ImageBrush>。 <xref:System.Windows.Media.RotateTransform.CenterX%2A>和<xref:System.Windows.Media.RotateTransform.CenterY%2A>属性<xref:System.Windows.Media.RotateTransform>对象都设置为 0.5，这是此内容的中心点的相对坐标。 因此，<xref:System.Windows.Media.ImageBrush>内容围绕其中心。  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 第二个示例也适用<xref:System.Windows.Media.RotateTransform>到<xref:System.Windows.Media.ImageBrush>; 但是，此示例使用<xref:System.Windows.Media.Brush.Transform%2A>属性而不是<xref:System.Windows.Media.Brush.RelativeTransform%2A>属性。  
  
 若要将围绕其中心画笔，该示例设置<xref:System.Windows.Media.RotateTransform.CenterX%2A>和<xref:System.Windows.Media.RotateTransform.CenterY%2A>属性<xref:System.Windows.Media.RotateTransform>为绝对坐标的对象。 因为画笔绘制了一个 175x90 像素的矩形，所以该矩形的中心点为 (87.5, 45)。  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 有关如何说明<xref:System.Windows.Media.Brush.RelativeTransform%2A>和<xref:System.Windows.Media.Brush.Transform%2A>属性工作，请参见[画笔转换概述](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)。  
  
 有关完整示例，请参阅[画笔示例](http://go.microsoft.com/fwlink/?LinkID=159973)。 有关画笔的详细信息，请参阅[使用纯色和渐变进行绘制概述](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)。  
  
## <a name="see-also"></a>请参阅  
 [画笔转换概述](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)  
 [使用纯色和渐变进行绘制概述](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
