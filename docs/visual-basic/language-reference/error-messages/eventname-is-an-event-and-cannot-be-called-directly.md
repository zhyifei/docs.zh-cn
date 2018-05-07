---
title: '&#39;&lt;eventname&gt; &#39;是一种事件，并且不能直接调用'
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 4d8a7d716d2b7c52d1d027a1e7959d981bb0857e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a>&#39;&lt;eventname&gt; &#39;是一种事件，并且不能直接调用
<`eventname`> 是一种事件，并因此不能直接调用。 使用`RaiseEvent`语句以引发一个事件。  
  
 过程调用指定过程名称的事件。 事件处理程序是一个过程，但事件本身的信号的设备，必须引发事件并处理。  
  
 **错误 ID:** BC32022  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  使用`RaiseEvent`语句发出信号事件并调用或多个处理它的过程。  
  
## <a name="see-also"></a>请参阅  
 [RaiseEvent 语句](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
