---
title: Widening
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: 1c9aa78549ca6e41c9fe54c12e0aaec8e7cc30cb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347834"
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)
指示转换运算符（`CType`）将类或结构转换为可以保存原始类或结构的所有可能值的类型。  
  
## <a name="converting-with-the-widening-keyword"></a>用扩大关键字转换  
 除 `Widening`之外，转换过程必须指定 `Public Shared`。  
  
 扩大转换始终会在运行时成功，不会导致数据丢失。 示例 `Single` `Double`，`Char` `String`，并将派生类型为其基类型。 由于派生类型包含基类型的所有成员，因此是最新的转换，因此是基类型的实例。  
  
 使用代码不必使用 `CType` 进行扩大转换，即使 `On``Option Strict` 也是如此。  
  
 可以在此上下文中使用 `Widening` 关键字：  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 有关扩展和收缩转换运算符的定义示例，请参阅[如何：定义转换运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)。  
  
## <a name="see-also"></a>另请参阅

- [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [扩大转换和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [如何：定义运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [如何：定义转换运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
