---
title: 如何：使动画加速或减速
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: b4bea64dbc88ce32c908289b9465b058c558a932
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555668"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a>如何：使动画加速或减速
此示例演示如何进行加速和随着时间的推移减速的动画。 在下面的示例中，多个矩形进行动画处理具有不同的动画<xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A>和<xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>设置。  
  
## <a name="example"></a>示例  
 [!code-xaml[timingbehaviors_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 此示例中，代码已被省略。 有关完整的代码，请参阅[动画计时行为示例](http://go.microsoft.com/fwlink/?LinkID=159970)。
