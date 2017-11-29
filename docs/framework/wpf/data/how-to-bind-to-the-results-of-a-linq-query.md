---
title: "如何：绑定到 LINQ 查询的结果"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e77a0c698dae0330877c54422c15e14c82376891
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a>如何：绑定到 LINQ 查询的结果
此示例演示如何运行 LINQ 查询，然后将绑定到结果。  
  
## <a name="example"></a>示例  
 下面的示例创建两个列表框。 第一个列表框中包含三个列表项。  
  
 [!code-xaml[LinqExample#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 从第一个列表框中选择一项时，将调用以下事件处理程序。 在此示例中，`Tasks`是一套`Task`对象。 `Task`类有一个名为`Priority`。 此事件处理程序运行返回的集合的 LINQ 查询`Task`对象具有所选的优先级值，然后将设置为<xref:System.Windows.FrameworkElement.DataContext%2A>:  
  
 [!code-csharp[LinqExample#Using](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 第二个列表框中将绑定到该集合，因为其<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>值设置为`{Binding}`。 因此，它将显示返回的集合 (基于`myTaskTemplate` <xref:System.Windows.DataTemplate>)。  
  
## <a name="see-also"></a>另请参阅  
 [让数据可供 XAML 中的绑定使用](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)  
 [绑定到集合并根据选择的内容显示信息](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [WPF 版本 4.5 中的新增功能](../../../../docs/framework/wpf/getting-started/whats-new.md)  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [操作说明主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
