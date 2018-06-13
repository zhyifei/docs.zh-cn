---
title: 如何：创建和使用画布
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
ms.openlocfilehash: c3ddb5171ca8ded053d56fde26ab86ebc4ae5cb2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552839"
---
# <a name="how-to-create-and-use-a-canvas"></a>如何：创建和使用画布
此示例演示如何创建和使用的实例<xref:System.Windows.Controls.Canvas>。  
  
## <a name="example"></a>示例  
 下面的示例显式定位两<xref:System.Windows.Controls.TextBlock>元素通过使用<xref:System.Windows.Controls.Canvas.SetTop%2A>和<xref:System.Windows.Controls.Canvas.SetLeft%2A>方法<xref:System.Windows.Controls.Canvas>。 该示例还将指定<xref:System.Windows.Controls.Control.Background%2A>颜色`LightSteelBlue`到<xref:System.Windows.Controls.Canvas>。  
  
> [!NOTE]
>  当你使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]到位置<xref:System.Windows.Controls.TextBlock>元素时，使用<xref:System.Windows.Controls.Canvas.Top%2A>和<xref:System.Windows.Controls.Canvas.Left%2A>属性。  
  
 [!code-csharp[CanvasCode#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.TextBlock>  
 <xref:System.Windows.Controls.Canvas.SetTop%2A>  
 <xref:System.Windows.Controls.Canvas.SetLeft%2A>  
 <xref:System.Windows.Controls.Canvas.Top%2A>  
 <xref:System.Windows.Controls.Canvas.Left%2A>  
 [面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)
