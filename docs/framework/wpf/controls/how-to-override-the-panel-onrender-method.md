---
title: 如何：重写面板的 OnRender 方法
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
ms.openlocfilehash: 23c3353e130585ed83726816a467ca73f6aa9152
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666705"
---
# <a name="how-to-override-the-panel-onrender-method"></a>如何：重写面板的 OnRender 方法
此示例演示如何重写<xref:System.Windows.Controls.Panel.OnRender%2A>的<xref:System.Windows.Controls.Panel>方法, 以便将自定义图形效果添加到布局元素。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.Panel.OnRender%2A>使用方法可向呈现的面板元素添加图形效果。 例如, 您可以使用此方法来添加自定义边框或背景效果。 <xref:System.Windows.Media.DrawingContext>对象作为参数传递, 该参数提供用于绘制形状、文本、图像或视频的方法。 因此, 此方法对 panel 对象的自定义很有用。  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.Panel>
- [面板概述](panels-overview.md)
- [帮助主题](panel-how-to-topics.md)
