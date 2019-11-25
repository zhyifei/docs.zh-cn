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
Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.  
  
## <a name="converting-with-the-widening-keyword"></a>Converting with the Widening Keyword  
 The conversion procedure must specify `Public Shared` in addition to `Widening`.  
  
 Widening conversions always succeed at run time and never incur data loss. Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type. This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.  
  
 The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.  
  
 The `Widening` keyword can be used in this context:  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="see-also"></a>请参阅

- [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [扩大转换和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [如何：定义运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType 函数](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [如何：定义转换运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
