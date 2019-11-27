---
title: ByVal
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: a96f871c6ce119f65ebbec54fdb1471ae105d504
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351587"
---
# <a name="byval-visual-basic"></a>ByVal (Visual Basic)
指定参数[按值](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)传递，因此被调用的过程或属性无法更改调用代码中参数的基础变量的值。 如果未指定修饰符，则 ByVal 为默认值。

> [!NOTE]
> 由于这是默认值，因此不必在方法签名中显式指定 `ByVal` 关键字。 它往往会产生干扰的代码，通常会导致被忽略的非默认 `ByRef` 关键字。

## <a name="remarks"></a>备注
 `ByVal` 修饰符可用于下面的上下文中：

 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)

 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="example"></a>示例
 下面的示例演示如何将 `ByVal` 参数传递机制与引用类型参数一起使用。 在此示例中，参数 `c1`，类 `Class1`的实例。 `ByVal` 阻止过程中的代码更改 reference 参数的基础值，`c1`，但不保护 `c1`的可访问字段和属性。

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a>另请参阅

- [关键字](../../../visual-basic/language-reference/keywords/index.md)
- [按值和按引用传递自变量](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
