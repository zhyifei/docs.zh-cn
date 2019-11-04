---
title: 如何：使用代码添加事件处理程序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 457b8cf5c68096b20df7fe39f1cc3f40358f34d0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460437"
---
# <a name="how-to-add-an-event-handler-using-code"></a>如何：使用代码添加事件处理程序
此示例演示如何使用代码将事件处理程序添加到元素。  
  
 如果要将事件处理程序添加到 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 元素，并且已加载包含该元素的标记页，则必须使用代码添加该处理程序。 或者，如果您正在完全使用代码构建应用程序的元素树，而没有使用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]声明任何元素，则可以调用特定的方法将事件处理程序添加到构造的元素树中。  
  
## <a name="example"></a>示例  
 下面的示例将新 <xref:System.Windows.Controls.Button> 添加到 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中最初定义的现有页面。 代码隐藏文件实现事件处理程序方法，然后将该方法作为新的事件处理程序添加到 <xref:System.Windows.Controls.Button>上。  
  
 该C#示例使用 `+=` 运算符为事件分配处理程序。 这是用于在公共语言运行时（CLR）事件处理模型中分配处理程序的同一运算符。 Microsoft Visual Basic 不支持将此运算符作为添加事件处理程序的方法。 而是需要以下两种方法之一：  
  
- 将 <xref:System.Windows.UIElement.AddHandler%2A> 方法与 `AddressOf` 运算符一起使用以引用事件处理程序实现。  
  
- 使用 `Handles` 关键字作为事件处理程序定义的一部分。 此处未显示此方法;请参阅[Visual Basic 和 WPF 事件处理](visual-basic-and-wpf-event-handling.md)。  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> 在最初分析的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页中添加事件处理程序要简单得多。 在要添加事件处理程序的对象元素中，添加一个与你要处理的事件的名称相匹配的属性。 然后，将该属性的值指定为在 "[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]" 页的代码隐藏文件中定义的事件处理程序方法的名称。 有关详细信息，请参阅[XAML 概述（WPF）](../../../desktop-wpf/fundamentals/xaml.md)或[路由事件概述](routed-events-overview.md)。  
  
## <a name="see-also"></a>请参阅

- [路由事件概述](routed-events-overview.md)
- [帮助主题](events-how-to-topics.md)
