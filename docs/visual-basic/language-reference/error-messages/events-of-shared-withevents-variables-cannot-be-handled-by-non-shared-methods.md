---
title: 共享 WithEvents 变量的事件不能由非共享方法处理
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: 09f56d340322ee88afc54e7e8a53716777782d47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505757"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>共享 WithEvents 变量的事件不能由非共享方法处理
与声明的变量`Shared`修饰符是共享的变量。 共享的变量标识恰好一个存储位置。 与声明的变量`WithEvents`修饰符声明该变量所属的类型处理一组变量引发的事件。 该属性值分配给变量时，创建的`WithEvents`声明卸载任何现有的事件处理程序，并通过新的事件处理程序挂钩`Add`方法。  
  
 **错误 ID:** BC30594  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   声明事件处理程序`Shared`。  
  
## <a name="see-also"></a>请参阅
- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
