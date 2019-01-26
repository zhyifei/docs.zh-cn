---
title: '&#39;&lt;eventname&gt; &#39;是一种事件，而且不能直接调用'
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 3efd8c18497ce288e16659db4ca4693d5a3e6acc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54581980"
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a>&#39;&lt;eventname&gt; &#39;是一种事件，而且不能直接调用
<`eventname`> 是一种事件，并因此不能直接调用。 使用`RaiseEvent`语句引发事件。  
  
 过程调用指定的事件的过程名称。 事件处理程序是一个过程，但事件本身的信号的设备，必须引发并处理。  
  
 **错误 ID:** BC32022  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  使用`RaiseEvent`语句发出信号事件并调用过程或对其进行处理的过程。  
  
## <a name="see-also"></a>请参阅
- [RaiseEvent 语句](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
