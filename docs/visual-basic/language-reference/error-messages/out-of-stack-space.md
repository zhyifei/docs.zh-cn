---
title: 堆栈空间不足 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ec839d1f0ad1931ed4229e898a900c3210d813ed
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="out-of-stack-space-visual-basic"></a>堆栈空间不足 (Visual Basic)
堆栈是内存的动态与执行程序的需求的增长和缩减的工作区域。 已超出其限制。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  检查不太深嵌套过程。  
  
2.  请确保正确终止递归过程。  
  
3.  如果本地变量所需的本地变量空间大于可用空间，请尝试在模块级别声明一些变量。 你也可以声明该过程中的所有变量静态通过在前面`Property`， `Sub`，或`Function`关键字后的跟`Static`。 也可以使用`Static`语句来声明过程内的单个静态变量。  
  
4.  重新定义一些你固定长度字符串作为可变长度字符串，因为固定长度字符串使用比可变长度字符串的更多堆栈空间。 你还可以定义在模块级别，它不需要堆栈空间的字符串。  
  
5.  检查的数嵌套`DoEvents`使用函数调用，`Calls`到哪些过程是堆栈上处于活动状态的视图的对话框。  
  
6.  请确保你不会触发的事件的事件过程调用在堆栈上的已导致"事件 cascade"。 级联事件类似于未终止的递归过程调用，但是它不太明显，因为默认情况下，调用通过 Visual Basic 而不是代码中的显式调用。 使用`Calls`到哪些过程是堆栈上处于活动状态的视图的对话框。  
  
## <a name="see-also"></a>请参阅  
 [“内存”窗口](/visualstudio/debugger/memory-windows)
