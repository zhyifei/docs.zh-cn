---
title: 如何：声明自定义事件以避免阻止 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 3cb66aed71195d2fd2335fbd59cc499b3dbf808e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>如何：声明自定义事件以避免阻止 (Visual Basic)
有几种情况下很重要的一个事件处理程序不会阻止后续的事件处理程序。 自定义事件允许事件以异步方式调用其事件处理程序。  
  
 默认情况下，事件声明的后备存储字段是按顺序将合并所有事件处理程序的多路广播的委托。 这意味着，如果一个处理程序采用较长时间才能完成，它将阻止其他处理程序直到它完成。 （功能良好的事件处理程序应永远不会执行时间较长或可能起阻止作用的操作。）  
  
 而不是使用 Visual Basic 提供的事件的默认实现，你可以使用自定义事件以异步方式执行的事件处理程序。  
  
## <a name="example"></a>示例  
 在此示例中，`AddHandler`访问器将添加的每个处理程序委托`Click`事件<xref:System.Collections.ArrayList>存储在`EventHandlerList`字段。  
  
 在代码引发`Click`事件，`RaiseEvent`访问器时，将调用以异步方式使用的所有事件处理程序委托<xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>方法。 该方法调用每个工作线程上的处理程序并立即返回，因此处理程序无法阻止另一个。  
  
 [!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Collections.ArrayList>  
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>  
 [事件](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [如何：声明自定义事件以节省内存](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
