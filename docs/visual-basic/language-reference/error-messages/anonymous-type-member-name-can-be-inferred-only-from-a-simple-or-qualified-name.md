---
title: 只能从不带自变量的简单名或限定名中推断匿名类型成员名称
ms.date: 07/20/2015
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
ms.openlocfilehash: 38f669fe183ac79ebed6e5a122bc70aedc9bb753
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701218"
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>只能从不带自变量的简单名或限定名中推断匿名类型成员名称
不能从复杂的表达式中推断匿名类型成员名称。  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 有关匿名类型可以和不能推断成员名称和类型的源的详细信息，请参阅 [How to：在匿名类型声明 @ no__t 中推断属性名称和类型。  
  
 **错误 ID：** BC36556  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 将表达式分配到成员名称，如下面的代码所示：  
  
    ```vb  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a>请参阅

- [匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [如何：在匿名类型声明中推断属性名和类型 @ no__t-0
