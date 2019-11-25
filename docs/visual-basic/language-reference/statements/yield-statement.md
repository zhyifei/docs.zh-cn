---
title: Yield 语句
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: 72a8dafdc5aa834a644e1e70a309cfc0827b5fdf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352724"
---
# <a name="yield-statement-visual-basic"></a>Yield 语句 (Visual Basic)
Sends the next element of a collection to a `For Each...Next` statement.  
  
## <a name="syntax"></a>语法  
  
```vb  
Yield expression  
```  
  
## <a name="parameters"></a>参数  
  
|术语|定义|  
|---|---|  
|`expression`|必须的。 An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.|  
  
## <a name="remarks"></a>备注  
 The `Yield` statement returns one element of a collection at a time. The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.  
  
 You consume an iterator function by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) or a LINQ query. Each iteration of the `For Each` loop calls the iterator function. When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained. 下次调用迭代器函数时，将从该位置重新开始执行。  
  
 An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.  
  
 You can use an `Exit Function` or `Return` statement to end the iteration.  
  
 "Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.  
  
 For more information about iterator functions and `Get` accessors, see [Iterators](../../programming-guide/concepts/iterators.md).  
  
## <a name="iterator-functions-and-get-accessors"></a>Iterator Functions and Get Accessors  
 The declaration of an iterator function or `Get` accessor must meet the following requirements:  
  
- It must include an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.  
  
- 返回类型必须为 <xref:System.Collections.IEnumerable>、<xref:System.Collections.Generic.IEnumerable%601>、<xref:System.Collections.IEnumerator> 或 <xref:System.Collections.Generic.IEnumerator%601>。  
  
- It cannot have any `ByRef` parameters.  
  
 An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.  
  
 An iterator function can be an anonymous function. 有关详细信息，请参阅[迭代器](../../programming-guide/concepts/iterators.md)。  
  
## <a name="exception-handling"></a>异常处理  
 A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.  
  
 A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.  
  
 If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed. A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.  
  
## <a name="technical-implementation"></a>技术实现  
 The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 The call to `MyIteratorFunction` doesn't execute the body of the function. 相反，该调用会将 `IEnumerable(Of String)` 返回到 `elements` 变量中。  
  
 在 `For Each` 循环迭代时，将为 <xref:System.Collections.IEnumerator.MoveNext%2A> 调用 `elements` 方法。 此调用将执行 `MyIteratorFunction` 的主体，直至到达下一个 `Yield` 语句。 The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.  
  
 在 `For Each` 循环的每个后续迭代中，迭代器主体的执行将从它暂停的位置继续，直至到达 `Yield` 语句后才会停止。 The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.  
  
## <a name="example"></a>示例  
 The following example has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop. Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function. 对迭代器函数的每个调用将继续到 `Yield` 语句的下一次执行（在 `For…Next` 循环的下一次迭代期间发生）。  
  
 The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type. 当调用迭代器方法时，它将返回一个包含数字幂的可枚举对象。  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>示例  
 下面的示例演示一个作为迭代器的 `Get` 访问器。 The property declaration includes an `Iterator` modifier.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>请参阅

- [语句](../../../visual-basic/language-reference/statements/index.md)
