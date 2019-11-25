---
title: 迭代器
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 9d7eaf186bae544031487ce027505e1e0d4ae0f3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351520"
---
# <a name="iterator-visual-basic"></a>迭代器 (Visual Basic)
Specifies that a function or `Get` accessor is an iterator.  
  
## <a name="remarks"></a>备注  
 An *iterator* performs a custom iteration over a collection. An iterator uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element in the collection one at a time. When a `Yield` statement is reached, the current location in code is retained. 下次调用迭代器函数时，将从该位置重新开始执行。  
  
 An iterator can be implemented as a function or as a `Get` accessor of a property definition. The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.  
  
 You call an iterator from client code by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.  
  
 An iterator cannot have any `ByRef` parameters.  
  
 不能在事件、实例构造函数、静态构造函数或静态析构函数中使用迭代器。  
  
 An iterator can be an anonymous function. 有关详细信息，请参阅[迭代器](../../programming-guide/concepts/iterators.md)。  
  
## <a name="usage"></a>用法  
 `Iterator` 修饰符可用于下面的上下文中：  
  
- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
- [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a>示例  
 The following example demonstrates an iterator function. The iterator function has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop. Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function. 对迭代器函数的每个调用将继续到 `Yield` 语句的下一次执行（在 `For…Next` 循环的下一次迭代期间发生）。  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>示例  
 下面的示例演示一个作为迭代器的 `Get` 访问器。 The `Iterator` modifier is in the property declaration.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>请参阅

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [迭代器](../../programming-guide/concepts/iterators.md)
- [Yield 语句](../../../visual-basic/language-reference/statements/yield-statement.md)
