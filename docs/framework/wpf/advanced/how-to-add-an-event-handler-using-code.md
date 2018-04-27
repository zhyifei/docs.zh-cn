---
title: 如何：使用代码添加事件处理程序
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4e7627589ff7e422c4ad3cd7a37fdc14c8a9c9f4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-an-event-handler-using-code"></a>如何：使用代码添加事件处理程序
此示例演示如何使用代码将事件处理程序添加到元素。  
  
 如果你想要添加到事件处理程序[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]在已加载元素，并包含的元素的标记页面，则必须添加使用代码处理程序。 或者，如果您正在生成应用程序完全使用代码而不声明使用任何元素的元素树[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，你可以调用特定方法，以将事件处理程序添加到构造的元素树。  
  
## <a name="example"></a>示例  
 下面的示例添加一个新<xref:System.Windows.Controls.Button>向最初中定义的现有页面[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。 代码隐藏文件实现事件处理程序方法，然后将该方法上添加一个新的事件处理程序为<xref:System.Windows.Controls.Button>。  
  
 C# 示例使用`+=`运算符将处理程序分配到的事件。 这是用于分配中的处理程序的相同运算符[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]事件处理模型。 作为一种添加事件处理程序，Microsoft Visual Basic 不支持此运算符。 相反，它要求两种方法之一：  
  
-   使用<xref:System.Windows.UIElement.AddHandler%2A>方法，与一起`AddressOf`运算符，以引用的事件处理程序实现。  
  
-   使用`Handles`关键字作为事件处理程序定义的一部分。 此技术未在此处; 显示请参阅[Visual Basic 和 WPF 的事件处理](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md)。  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  添加事件处理程序在最初分析[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]页是要简单得多。 在对象元素中你想要添加事件处理程序，将添加匹配你想要处理事件的名称的属性。 然后该属性的值指定为你的代码隐藏文件中定义的事件处理程序方法的名称[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]页。 有关详细信息，请参阅[XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)或[路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)。  
  
## <a name="see-also"></a>请参阅  
 [路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
