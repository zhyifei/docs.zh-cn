---
title: 共享 WithEvents 变量的事件不能由非共享方法处理
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: f61f4cd17b1bb3088117e0a0d91b186fd40db3b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585166"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>共享 WithEvents 变量的事件不能由非共享方法处理
与声明的变量`Shared`修饰符是共享的变量。 共享的变量标识恰好一个存储位置。 与声明的变量`WithEvents`修饰符断言变量所属的类型处理一组变量引发的事件。 属性值分配给变量时，由`WithEvents`声明任何现有的事件处理程序将解除挂钩，并通过新的事件处理程序挂钩`Add`方法。  
  
 **错误 ID:** BC30594  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   声明事件处理程序`Shared`。  
  
## <a name="see-also"></a>请参阅  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
