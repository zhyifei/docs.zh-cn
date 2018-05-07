---
title: 用作可选参数类型的泛型参数必须受类约束
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 7e2b59f758ef236717a912694576b514e2ae8a60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a>用作可选参数类型的泛型参数必须受类约束
使用不约束为引用类型的类型参数的可选参数声明的过程。  
  
 你必须始终提供每个可选参数的默认值。 如果参数是引用类型，则可选值必须为`Nothing`，是一个有效的值，对于任何引用类型。 但是，如果参数的值类型，则该类型必须由 Visual Basic 预定义的基本数据类型。 这是因为复合值类型，如用户定义的结构，不具有任何有效的默认值。  
  
 当你使用的类型参数为可选参数时，必须保证它属于引用类型以避免任何有效的默认值的值类型的可能性。 这意味着必须与约束类型参数`Class`关键字或特定类的名称。  
  
 **错误 ID:** BC32124  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   将仅接受一个引用类型，类型参数约束，或者不使用它为可选参数。  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 中的泛型类型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [类型列表](../../../visual-basic/language-reference/statements/type-list.md)  
 [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)  
 [可选参数](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [结构](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Nothing](../../../visual-basic/language-reference/nothing.md)
