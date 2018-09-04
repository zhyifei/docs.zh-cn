---
title: 如何：使用径向渐变绘制区域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: 75c28cd19ec0423589b6485884842468b89b5e8c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526786"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a>如何：使用径向渐变绘制区域
此示例演示如何使用<xref:System.Windows.Media.RadialGradientBrush>类，以使用径向渐变绘制区域。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.RadialGradientBrush>绘制一个矩形使用径向渐变的黄色从过渡到红色变为蓝色变为浅绿色。  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 下图显示了前面的示例中的渐变。 其中突出显示的渐变停止点。  
  
 ![径向渐变中的梯度停止点](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")  
  
> [!NOTE]
>  本主题中的示例使用默认坐标系来设置控制点。 默认坐标系与边界框是： 0 指示边界框的 0 %1 指示边界框的 100%。 您可以通过设置更改此坐标系<xref:System.Windows.Media.GradientBrush.MappingMode%2A>属性的值<xref:System.Windows.Media.BrushMappingMode.Absolute>。 绝对坐标系与范围框无关。 值直接在本地空间中解释。  
  
 有关更多<xref:System.Windows.Media.RadialGradientBrush>示例，请参阅[画笔示例](https://go.microsoft.com/fwlink/?LinkID=159973)。 渐变和画笔的其他类型的详细信息，请参阅[使用纯色和渐变概述进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)。
