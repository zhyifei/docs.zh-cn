---
title: "如何：重写面板的 OnRender 方法"
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
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 958595cdfa521b372270d6283c7134ef0ba0ef79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-override-the-panel-onrender-method"></a>如何：重写面板的 OnRender 方法
此示例演示如何重写<xref:System.Windows.Controls.Panel.OnRender%2A>方法<xref:System.Windows.Controls.Panel>以便将自定义图形效果添加到布局元素。  
  
## <a name="example"></a>示例  
 使用<xref:System.Windows.Controls.Panel.OnRender%2A>方法，以将图形效果添加到呈现的面板元素。 例如，此方法可用于添加自定义边框或背景效果。 A<xref:System.Windows.Media.DrawingContext>对象作为参数，它提供绘制形状、 文本、 图像或视频方法传递。 因此，此方法很有用的面板对象自定义项。  
  
 [!code-csharp[LightWeightCustomPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.Panel>  
 [面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [自定义径向面板示例](http://go.microsoft.com/fwlink/?LinkID=159982)  
 [帮助主题](../../../../docs/framework/wpf/controls/panel-how-to-topics.md)
