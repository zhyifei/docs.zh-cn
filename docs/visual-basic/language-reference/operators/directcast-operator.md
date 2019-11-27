---
title: DirectCast 运算符
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 8ea29b80cf27bbb2c21a8cebbfaa0a294e05f11d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331308"
---
# <a name="directcast-operator-visual-basic"></a>DirectCast 运算符 (Visual Basic)
引入基于继承或实现的类型转换操作。  
  
## <a name="remarks"></a>备注  
 `DirectCast` 不使用 Visual Basic 运行时帮助器例程进行转换，因此，它在与数据类型 `Object`之间来回转换时，它可以提供比 `CType` 更好的性能。  
  
 将 `DirectCast` 关键字与使用[CType 函数](../../../visual-basic/language-reference/functions/ctype-function.md)和[TryCast 运算符](../../../visual-basic/language-reference/operators/trycast-operator.md)关键字类似。 提供表达式作为第一个参数，并提供一个类型以将其转换为第二个参数。 `DirectCast` 需要这两个参数的数据类型之间的继承关系或实现关系。 这意味着一个类型必须从继承或实现另一个类型。  
  
## <a name="errors-and-failures"></a>错误和失败  
 如果 `DirectCast` 检测到不存在继承或实现关系，则会生成编译器错误。 但缺少编译器错误并不能保证成功转换。 如果所需的转换是收缩转换，则可能会在运行时失败。 如果发生这种情况，运行时会引发 <xref:System.InvalidCastException> 错误。  
  
## <a name="conversion-keywords"></a>转换关键字  
 下面是类型转换关键字的比较。  
  
|关键字|数据类型|参数关系|运行时失败|  
|---|---|---|---|  
|[CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)|任何数据类型|必须在这两种数据类型之间定义扩大转换或收缩转换|引发 <xref:System.InvalidCastException>|  
|`DirectCast`|任何数据类型|一个类型必须继承自或实现另一个类型|引发 <xref:System.InvalidCastException>|  
|[TryCast 运算符](../../../visual-basic/language-reference/operators/trycast-operator.md)|仅引用类型|一个类型必须继承自或实现另一个类型|不返回[任何内容](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>示例  
 下面的示例演示了 `DirectCast`的两个用法，一个在运行时失败，另一个则是成功的。  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 在前面的示例中，`Double``q` 的运行时类型。 `CType` 成功，因为 `Double` 可转换为 `Integer`。 但是，第一个 `DirectCast` 在运行时失败，因为 `Double` 的运行时类型与 `Integer`没有继承关系，即使存在转换也是如此。 第二个 `DirectCast` 成功，因为它从类型 <xref:System.Windows.Forms.Form> 转换为类型 <xref:System.Windows.Forms.Control>，<xref:System.Windows.Forms.Form> 将从该类型继承。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [扩大转换和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [隐式转换和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
