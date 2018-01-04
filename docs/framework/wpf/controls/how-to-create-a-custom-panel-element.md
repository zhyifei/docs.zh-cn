---
title: "如何：创建自定义 Panel 元素"
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
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5eacc5435e259c20c25b64d6e82c33d07338602a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-panel-element"></a>如何：创建自定义 Panel 元素
## <a name="example"></a>示例  
 此示例演示如何重写的默认布局行为<xref:System.Windows.Controls.Panel>元素并创建自定义布局元素派生自<xref:System.Windows.Controls.Panel>。  
  
 该示例定义一个简单的自定义<xref:System.Windows.Controls.Panel>元素调用`PlotPanel`，其定位子元素根据两个硬编码 x 坐标和 y 坐标。 在此示例中，`x`和`y`都设置为`50`; 因此，所有子元素都放置在该位置上的 x 和 y 轴。  
  
 若要实现自定义<xref:System.Windows.Controls.Panel>行为，该示例使用<xref:System.Windows.FrameworkElement.MeasureOverride%2A>和<xref:System.Windows.FrameworkElement.ArrangeOverride%2A>方法。 每个方法返回<xref:System.Windows.Size>需要定位和呈现子元素的数据。  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.Panel>  
 [面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [创建自定义的内容换行面板示例](http://go.microsoft.com/fwlink/?LinkID=159979)
