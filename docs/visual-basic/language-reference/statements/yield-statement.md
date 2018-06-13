---
title: Yield 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: f938ad29df54ade6722f3de33e931c851ade8c21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604858"
---
# <a name="yield-statement-visual-basic"></a>Yield 语句 (Visual Basic)
将发送到集合的下一个元素`For Each...Next`语句。  
  
## <a name="syntax"></a>语法  
  
```  
Yield expression  
```  
  
#### <a name="parameters"></a>参数  
  
|术语|定义|  
|---|---|  
|`expression`|必须的。 隐式转换为迭代器函数的类型的表达式或`Get`访问器包含`Yield`语句。|  
  
## <a name="remarks"></a>备注  
 `Yield`语句返回一次集合的一个元素。 `Yield`语句将包括在迭代器函数或`Get`访问器，它对集合执行自定义迭代。  
  
 通过使用迭代器函数[每个...下一条语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)或 LINQ 查询。 每次迭代`For Each`循环调用迭代器函数。 当`Yield`语句访问在迭代器函数中，`expression`返回，并保留当前代码中的位置。 下次调用迭代器函数时，将从该位置重新开始执行。  
  
 必须存在从的类型的隐式转换`expression`中`Yield`到迭代器的返回类型的语句。  
  
 你可以使用`Exit Function`或`Return`语句结束迭代。  
  
 "生成"不是保留的字且仅当使用中时，它具有特殊含义`Iterator`函数或`Get`访问器。  
  
 有关迭代器函数的详细信息和`Get`访问器中，请参阅[迭代器](../../programming-guide/concepts/iterators.md)。  
  
## <a name="iterator-functions-and-get-accessors"></a>迭代器函数和 Get 访问器  
 迭代器函数的声明或`Get`访问器必须满足以下要求：  
  
-   它必须包括[迭代器](../../../visual-basic/language-reference/modifiers/iterator.md)修饰符。  
  
-   返回类型必须为 <xref:System.Collections.IEnumerable>、<xref:System.Collections.Generic.IEnumerable%601>、<xref:System.Collections.IEnumerator> 或 <xref:System.Collections.Generic.IEnumerator%601>。  
  
-   它不能含有任何`ByRef`参数。  
  
 在事件、 实例构造函数、 静态构造函数或静态析构函数不能出现迭代器函数。  
  
 迭代器函数可以是一个匿名函数。 有关更多信息，请参见 [迭代器](../../programming-guide/concepts/iterators.md)。  
  
## <a name="exception-handling"></a>异常处理  
 A`Yield`语句可以是内部`Try`块[重试...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。 A`Try`具有的块`Yield`语句可以有`Catch`阻止，并且可以`Finally`块。  
  
 A`Yield`语句不能包含在内`Catch`块或`Finally`块。  
  
 如果`For Each`（之外的迭代器函数） 的正文引发异常，`Catch`未执行迭代器函数中的块，但`Finally`执行迭代器函数中的块。 A`Catch`块中嵌套的迭代器函数捕获仅出现在迭代器函数的异常。  
  
## <a name="technical-implementation"></a>技术实现  
 下面的代码返回`IEnumerable (Of String)`从迭代器函数，然后循环访问的元素`IEnumerable (Of String)`。  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 调用`MyIteratorFunction`不执行该函数的主体。 相反，该调用会将 `IEnumerable(Of String)` 返回到 `elements` 变量中。  
  
 在 `For Each` 循环迭代时，将为 <xref:System.Collections.IEnumerator.MoveNext%2A> 调用 `elements` 方法。 此调用将执行 `MyIteratorFunction` 的主体，直至到达下一个 `Yield` 语句。 `Yield`语句返回确定不仅的值的表达式`element`循环体使用变量但还<xref:System.Collections.Generic.IEnumerator%601.Current%2A>属性的元素，它是`IEnumerable (Of String)`。  
  
 在 `For Each` 循环的每个后续迭代中，迭代器主体的执行将从它暂停的位置继续，直至到达 `Yield` 语句后才会停止。 `For Each`循环完成时的迭代器函数的末尾或`Return`或`Exit Function`达到语句。  
  
## <a name="example"></a>示例  
 下面的示例有`Yield`语句内[为...下一步](../../../visual-basic/language-reference/statements/for-next-statement.md)循环。 每次迭代[每个](../../../visual-basic/language-reference/statements/for-each-next-statement.md)语句体中的`Main`创建调用`Power`迭代器函数。 对迭代器函数的每个调用将继续到 `Yield` 语句的下一次执行（在 `For…Next` 循环的下一次迭代期间发生）。  
  
 迭代器方法的返回类型是<xref:System.Collections.Generic.IEnumerable%601>，迭代器接口类型。 当调用迭代器方法时，它将返回一个包含数字幂的可枚举对象。  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]  
  
## <a name="example"></a>示例  
 下面的示例演示一个作为迭代器的 `Get` 访问器。 属性声明中包含`Iterator`修饰符。  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]  
  
 有关其他示例，请参阅[迭代器](../../programming-guide/concepts/iterators.md)。  
  
## <a name="see-also"></a>请参阅  
 [语句](../../../visual-basic/language-reference/statements/index.md)
