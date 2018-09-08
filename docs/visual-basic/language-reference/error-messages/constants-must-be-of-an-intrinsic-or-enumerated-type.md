---
title: 常量必须是内部类型或者枚举类型，不能是类、结构、类型参数或数组类型
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: 4d635d289ed99aed48c296c278bc546971af51da
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083917"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a>常量必须是内部类型或者枚举类型，不能是类、结构、类型参数或数组类型
已尝试声明为类、 结构或数组类型，或由包含泛型类型定义的类型参数的常量。  
  
 常量必须是内部类型 (`Boolean`， `Byte`， `Date`， `Decimal`， `Double`， `Integer`， `Long`， `Object`， `SByte`， `Short`， `Single`， `String`， `UInteger`， `ULong`，或`UShort`)，或`Enum`类型基于整型类型之一。  
  
 **错误 ID:** BC30424  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  声明常量用作内部函数或`Enum`类型。  
  
2.  一个常数，也可以是特殊值，如`True`， `False`，或`Nothing`。 编译器会考虑这些预定义的值为相应的内部类型。  
  
## <a name="see-also"></a>请参阅  
 [常量和枚举](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [数据类型](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [数据类型](../../../visual-basic/language-reference/data-types/index.md)
