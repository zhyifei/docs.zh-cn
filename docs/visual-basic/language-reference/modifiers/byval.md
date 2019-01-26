---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: 6fa87db4fbab961dd1aa526e2ac8ff15b031005b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650075"
---
# <a name="byval-visual-basic"></a>ByVal (Visual Basic)
指定的被调用的过程或属性不能更改基础调用代码中的参数的变量的值的方式来传递参数。  
  
## <a name="remarks"></a>备注  
 `ByVal` 修饰符可用于下面的上下文中：  
  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a>示例  
 下面的示例演示如何将`ByVal`参数传递机制与引用类型自变量。 在示例中，参数是`c1`，类的实例`Class1`。 `ByVal` 阻止过程中的代码进行更改的基础值的引用自变量， `c1`，但不会保护的可访问的字段和属性`c1`。  
  
 [!code-vb[VbVbalrKeywords#10](../../../visual-basic/language-reference/codesnippet/VisualBasic/byval_1.vb)]  
  
## <a name="see-also"></a>请参阅
- [关键字](../../../visual-basic/language-reference/keywords/index.md)
- [按值和按引用传递自变量](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
