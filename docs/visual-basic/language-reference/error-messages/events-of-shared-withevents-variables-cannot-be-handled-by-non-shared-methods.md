---
title: 共享 WithEvents 变量的事件不能由非共享方法处理
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 53372927b88df3946583564492df42170f302739
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>共享 WithEvents 变量的事件不能由非共享方法处理
与声明的变量`Shared`修饰符是共享的变量。 共享的变量标识恰好一个存储位置。 与声明的变量`WithEvents`修饰符断言变量所属的类型处理一组变量引发的事件。 属性值分配给变量时，由`WithEvents`声明任何现有的事件处理程序将解除挂钩，并通过新的事件处理程序挂钩`Add`方法。  
  
 **错误 ID:** BC30594  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   声明事件处理程序`Shared`。  
  
## <a name="see-also"></a>另请参阅  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
