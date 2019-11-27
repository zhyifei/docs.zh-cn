---
title: Narrowing
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: b252f7939e812f31103d4bd98ffd50953679f042
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351478"
---
# <a name="narrowing-visual-basic"></a>Narrowing (Visual Basic)
指示转换运算符（`CType`）将类或结构转换为可能无法保存原始类或结构的某些可能值的类型。  
  
## <a name="converting-with-the-narrowing-keyword"></a>用收缩关键字转换  
 除 `Narrowing`之外，转换过程必须指定 `Public Shared`。  
  
 收缩转换在运行时并不总是成功，可能会失败或导致数据丢失。 示例 `Long` `Integer`，`String` `Date`，并将基类型为派生类型。 此上一转换是收缩的，因为基类型可能不包含派生类型的所有成员，因此不是派生类型的实例。  
  
 如果 `On``Option Strict`，则使用代码必须使用 `CType` 进行所有收缩转换。  
  
 可以在此上下文中使用 `Narrowing` 关键字：  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a>另请参阅

- [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Widening](../../../visual-basic/language-reference/modifiers/widening.md)
- [扩大转换和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [如何：定义运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)
