---
title: 如何：声明自定义事件以避免阻止
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 8d73d9c4590afb33e7176f647069cafcb3a9d7d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345139"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>如何：声明自定义事件以避免阻止 (Visual Basic)
在某些情况下，很重要的一点是，一个事件处理程序不会阻止后续事件处理程序。 自定义事件允许事件异步调用其事件处理程序。  
  
 默认情况下，事件声明的 "备份存储" 字段为一个多播委托，该委托按顺序合并所有事件处理程序。 这意味着，如果某个处理程序需要很长时间才能完成，则会阻止其他处理程序完成。 （正常运行的事件处理程序永远不会执行冗长或可能阻塞的操作。）  
  
 您可以使用自定义事件异步执行事件处理程序，而不是使用 Visual Basic 提供的事件的默认实现。  
  
## <a name="example"></a>示例  
 在此示例中，`AddHandler` 访问器将 `Click` 事件的每个处理程序的委托添加到 `EventHandlerList` 字段中存储的 <xref:System.Collections.ArrayList>。  
  
 当代码引发 `Click` 事件时，`RaiseEvent` 访问器使用 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> 方法以异步方式调用所有事件处理程序委托。 该方法调用工作线程上的每个处理程序并立即返回，因此处理程序不能彼此阻止。  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [事件](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [如何：声明自定义事件以节省内存](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
