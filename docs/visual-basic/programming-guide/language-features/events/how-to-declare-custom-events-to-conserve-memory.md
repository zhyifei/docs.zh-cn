---
title: "如何：声明自定义事件以节省内存 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: eec9a2fc687f481ab40313e35cbde81c25b81ae8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>如何：声明自定义事件以节省内存 (Visual Basic)
重要应用程序保持其内存使用率较低时，有几种情况。 自定义事件允许应用程序内存仅用于其处理的事件。  
  
 默认情况下，当一个类声明事件时，编译器将内存分配的字段来存储事件信息。 如果类具有许多未使用的事件，它们将不必要地占用内存。  
  
 而不是使用 Visual Basic 提供的事件的默认实现，你可以使用自定义事件来更仔细管理内存使用情况。  
  
## <a name="example"></a>示例  
 在此示例中，类使用的一个实例<xref:System.ComponentModel.EventHandlerList>类，存储在`Events`字段中，在使用存储有关的事件的信息。 <xref:System.ComponentModel.EventHandlerList>类是一个经过优化的列表类，用于保存委托。  
  
 类使用中的所有事件`Events`字段来跟踪哪些方法正处理每个事件。  
  
 [!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ComponentModel.EventHandlerList>  
 [事件](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [如何：声明自定义事件以避免阻止](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
