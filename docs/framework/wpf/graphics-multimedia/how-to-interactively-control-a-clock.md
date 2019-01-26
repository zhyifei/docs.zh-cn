---
title: 如何：以交互方式控制时钟
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 93c2d754ec899c96a50fef3dcef680434f564276
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657536"
---
# <a name="how-to-interactively-control-a-clock"></a>如何：以交互方式控制时钟
一个<xref:System.Windows.Media.Animation.Clock>对象的<xref:System.Windows.Media.Animation.ClockController>属性使您能够以交互方式启动、 暂停、 恢复、 查找，请转到其填充期，时钟和停止时钟。 可以以交互方式控制仅一个计时树的根时钟。  
  
> [!NOTE]
>  还有其他方法为以交互方式控制动画的不需要您要直接使用时钟： 你还可以使用情节提要。 情节提要支持标记和代码中。 有关示例，请参阅[使用情节提要对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)或[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。  
  
 在以下示例中，几个按钮，用于以交互方式控制的动画时钟。  
  
## <a name="example"></a>示例  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a>请参阅
- [使用情节提要对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)
- [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
