---
title: "如何：在事件处理程序中查找源元素"
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
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d62d657b886b867481088e32fe1dd0614377e146
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a>如何：在事件处理程序中查找源元素
此示例演示如何在事件处理程序中查找源元素。  
  
## <a name="example"></a>示例  
 下面的示例演示<xref:System.Windows.Controls.Primitives.ButtonBase.Click>在代码隐藏文件中声明的事件处理程序。 当用户单击按钮处理程序附加到时，该处理程序更改的属性值。 处理程序代码使用<xref:System.Windows.RoutedEventArgs.Source%2A>属性的路由的事件数据的报告中的事件自变量更改<xref:System.Windows.FrameworkElement.Width%2A>上的属性值<xref:System.Windows.RoutedEventArgs.Source%2A>元素。  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.RoutedEventArgs>  
 [路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
