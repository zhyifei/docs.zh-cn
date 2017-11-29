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
ms.openlocfilehash: e9746683ec5b7ad142591c2b419f9af21be8d69c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="e6f5d-102">如何：在事件处理程序中查找源元素</span><span class="sxs-lookup"><span data-stu-id="e6f5d-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="e6f5d-103">此示例演示如何在事件处理程序中查找源元素。</span><span class="sxs-lookup"><span data-stu-id="e6f5d-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6f5d-104">示例</span><span class="sxs-lookup"><span data-stu-id="e6f5d-104">Example</span></span>  
 <span data-ttu-id="e6f5d-105">下面的示例演示<xref:System.Windows.Controls.Primitives.ButtonBase.Click>在代码隐藏文件中声明的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e6f5d-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="e6f5d-106">当用户单击按钮处理程序附加到时，该处理程序更改的属性值。</span><span class="sxs-lookup"><span data-stu-id="e6f5d-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="e6f5d-107">处理程序代码使用<xref:System.Windows.RoutedEventArgs.Source%2A>属性的路由的事件数据的报告中的事件自变量更改<xref:System.Windows.FrameworkElement.Width%2A>上的属性值<xref:System.Windows.RoutedEventArgs.Source%2A>元素。</span><span class="sxs-lookup"><span data-stu-id="e6f5d-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="e6f5d-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6f5d-108">See Also</span></span>  
 <xref:System.Windows.RoutedEventArgs>  
 [<span data-ttu-id="e6f5d-109">路由事件概述</span><span class="sxs-lookup"><span data-stu-id="e6f5d-109">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="e6f5d-110">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="e6f5d-110">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
