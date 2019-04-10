---
title: 委托类“<classname>”没有 Invoke 方法，所以此类型的表达式不能作为方法调用的目标
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 3fe164d868ee7bde0e687e1d592f4d5a17565aea
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321297"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>委托类的\<类名 > 有没有 Invoke 方法，所以此类型的表达式不能作为方法调用的目标
调用`Invoke`通过委托失败，因为`Invoke`上委托类未实现。  
  
 **错误 ID:** BC30220  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 确保委托类的实例已经用`Dim`语句和到委托实例获得了一个过程`AddressOf`运算符。  
  
2. 找到实现委托类的代码并确保它实现了`Invoke`过程。  
  
## <a name="see-also"></a>请参阅

- [委托](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Delegate 语句](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [AddressOf 运算符](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)
