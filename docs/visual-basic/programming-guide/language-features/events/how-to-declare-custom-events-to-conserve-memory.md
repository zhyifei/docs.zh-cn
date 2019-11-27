---
title: 如何：声明自定义事件以节省内存
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: 3cc2d3ea57f1a8daf704c2c929baf3f2acf78c17
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345134"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>如何：声明自定义事件以节省内存 (Visual Basic)
在以下几种情况下，应用程序很重要的是应用程序保持其内存使用率较低。 自定义事件允许应用程序仅对它处理的事件使用内存。  
  
 默认情况下，当类声明事件时，编译器会为字段分配内存以存储事件信息。 如果某个类有许多未使用的事件，则它们将不必要地占用内存。  
  
 您可以使用自定义事件来更仔细地管理内存使用情况，而不是使用 Visual Basic 提供的事件的默认实现。  
  
## <a name="example"></a>示例  
 在此示例中，类使用 <xref:System.ComponentModel.EventHandlerList> 类的一个实例，该实例存储在 `Events` 字段中，用于存储有关正在使用的事件的信息。 <xref:System.ComponentModel.EventHandlerList> 类是一种旨在容纳委托的优化列表类。  
  
 类中的所有事件都使用 "`Events`" 字段来跟踪处理每个事件的方法。  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.ComponentModel.EventHandlerList>
- [事件](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [如何：声明自定义事件以避免阻止](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
