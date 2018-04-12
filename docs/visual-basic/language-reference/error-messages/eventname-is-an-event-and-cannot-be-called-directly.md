---
title: '&#39;&lt;eventname&gt;&#39; 是一种事件，并且不能直接调用'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb987c957a28aa37c40ad975b945c20da4690f6e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a>&#39;&lt;eventname&gt;&#39; 是一种事件，并且不能直接调用
<`eventname`> 是一种事件，并因此不能直接调用。 使用`RaiseEvent`语句以引发一个事件。  
  
 过程调用指定过程名称的事件。 事件处理程序是一个过程，但事件本身的信号的设备，必须引发事件并处理。  
  
 **错误 ID:** BC32022  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  使用`RaiseEvent`语句发出信号事件并调用或多个处理它的过程。  
  
## <a name="see-also"></a>另请参阅  
 [RaiseEvent 语句](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
