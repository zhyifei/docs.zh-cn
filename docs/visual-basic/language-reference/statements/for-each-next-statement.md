---
title: For Each...Next 语句 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ForEach
- vb.ForEachNext
- vb.Each
- ForEachNext
helpviewer_keywords:
- infinite loops
- Next statement [Visual Basic], For Each...Next
- endless loops
- loop structures [Visual Basic], For Each...Next
- loops, endless
- Each keyword [Visual Basic]
- instructions, repeating
- For Each statement [Visual Basic]
- collections, instruction repetition
- loops, infinite
- For Each...Next statements
- For keyword [Visual Basic], For Each...Next statements
- Exit statement [Visual Basic], For Each...Next statements
- iteration
ms.assetid: ebce3120-95c3-42b1-b70b-fa7da40c75e2
caps.latest.revision: 56
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b1593d279d4338ebadca803fe757a201cbcd654b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="for-eachnext-statement-visual-basic"></a>For Each...Next 语句 (Visual Basic)
集合中每个元素重复一的组语句。  
  
## <a name="syntax"></a>语法  
  
```  
For Each element [ As datatype ] In group  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ element ]  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`element`|中所需`For Each`语句。 参数是可选的`Next`语句。 变量。 用于循环访问集合的元素。|  
|`datatype`|如果存在`element`不已声明。 数据类型的`element`。|  
|`group`|必须的。 具有集合类型或对象的类型的变量。 对其引用集合`statements`要重复。|  
|`statements`|可选。 一个或多个语句之间`For Each`和`Next`运行中的每个项`group`。|  
|`Continue For`|可选。 将控制转移到开始`For Each`循环。|  
|`Exit For`|可选。 将扩展的控制转移`For Each`循环。|  
|`Next`|必须的。 终止的定义`For Each`循环。|  
  
## <a name="simple-example"></a>简单的示例  
 使用`For Each`...`Next`循环时要重复的集合或数组每个元素的一组语句。  
  
> [!TIP]
>  A[为...下一条语句](../../../visual-basic/language-reference/statements/for-next-statement.md)适用时，你可以将每个迭代的循环控制变量与相关联，并确定该变量的初始和最终值。 但是，当你处理的集合，初始和最终值的概念不是有意义，并且不必知道集合具有的元素数量。 在这种情况下， `For Each`...`Next`循环通常是更好的选择。  
  
 在下面的示例中， `For Each`...`Next` 语句循环访问列表集合的所有元素。  
  
 [!code-vb[VbVbalrStatements#121](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_1.vb)]  
  
 有关更多示例，请参阅[集合](../../../standard/collections/index.md)和[数组](../../../visual-basic/programming-guide/language-features/arrays/index.md)。  
  
## <a name="nested-loops"></a>嵌套的循环  
 可以嵌套`For Each`置于另一个循环内的循环。  
  
 下面的示例演示嵌套`For Each`...`Next` 结构。  
  
 [!code-vb[VbVbalrStatements#122](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_2.vb)]  
  
 每个循环时，则此嵌套循环必须具有唯一`element`变量。  
  
 此外可以嵌套不同类型的每个其他控件结构。 有关详细信息，请参阅[嵌套控制结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)。  
  
## <a name="exit-for-and-continue-for"></a>退出的针对并继续  
 [Exit For](../../../visual-basic/language-reference/statements/exit-statement.md)语句会导致执行退出`For`...`Next` 到后面的语句的循环，并将控制权`Next`语句。  
  
 `Continue For`语句将控制权立即到循环的下一个迭代。 有关详细信息，请参阅[继续语句](../../../visual-basic/language-reference/statements/continue-statement.md)。  
  
 下面的示例演示如何使用`Continue For`和`Exit For`语句。  
  
 [!code-vb[VbVbalrStatements#123](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_3.vb)]  
  
 你可以放置任意数量的`Exit For`中的语句`For Each`循环。 当使用内嵌套`For Each`循环，`Exit For`会导致执行到下一步较高级别的嵌套退出最内部的循环，并将控制权。  
  
 `Exit For` 通常使用某种条件; 评估之后例如，在`If`...`Then`...`Else`结构。 你可能想要使用`Exit For`在以下情况：  
  
-   继续循环是不必要或无法完成。 这可能引起错误的值或终止请求。  
  
-   在捕获了一个异常`Try`...`Catch`...`Finally`.你可以使用`Exit For`末尾`Finally`块。  
  
-   存在无限循环，即无法运行大型或甚至无限数量的次数的循环。 如果检测到此类条件，则可以使用`Exit For`来退出循环。 有关详细信息，请参阅[执行...循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)。  
  
## <a name="iterators"></a>Iterators  
 你使用*迭代器*来对集合执行自定义迭代。 迭代器可以是函数或`Get`访问器。 它使用`Yield`语句以返回一次的集合的每个元素。  
  
 通过调用迭代器`For Each...Next`语句。 `For Each` 循环的每次迭代都会调用迭代器。 当`Yield`语句达到迭代器中的表达式中`Yield`语句会返回，并保留当前代码中的位置。 下次调用迭代器时，将从该位置重新开始执行。  
  
 下面的示例使用迭代器函数。 迭代器函数具有`Yield`语句内[为...下一步](../../../visual-basic/language-reference/statements/for-next-statement.md)循环。 在`ListEvenNumbers`方法时，每次迭代`For Each`语句体创建对迭代器函数，并将继续到下一步的调用`Yield`语句。  
  
 [!code-vb[VbVbalrStatements#127](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_4.vb)]  
  
 有关详细信息，请参阅[迭代器](../../programming-guide/concepts/iterators.md)， [Yield 语句](../../../visual-basic/language-reference/statements/yield-statement.md)，和[迭代器](../../../visual-basic/language-reference/modifiers/iterator.md)。  
  
## <a name="technical-implementation"></a>技术实现  
 当`For Each`...`Next` 语句在运行时，Visual Basic 对集合仅一次，循环启动之前进行评估。 如果语句块更改`element`或`group`，这些更改不会影响循环的迭代。  
  
 当集合中的所有元素已依次都分配给`element`、`For Each`循环停止并将控制权传递到后面的语句`Next`语句。  
  
 如果`element`尚未已之外声明该循环中，你必须将其声明中`For Each`语句。 你可以声明的类型`element`通过使用显式`As`语句，或者你可以依赖于分配类型的类型推理。 在任一情况下的作用域`element`是循环的正文。 但是，您無法宣告`element`循环内外。  
  
 你可以选择指定`element`中`Next`语句。 这可以改善你程序的可读性，尤其是在具有嵌套`For Each`循环。 你必须指定相同的变量为显示在相应的一个`For Each`语句。  
  
 你可能想要避免更改的值`element`循环内。 执行此操作可以导致更难读取和调试你的代码。 更改的值`group`不会影响集合或其元素，用于确定第一次键入循环。  
  
 当要嵌套循环，如果`Next`外部的嵌套级别的语句遇到过`Next`的一个内部级别，编译器将引发错误。 但是，编译器可以检测到这只有在指定重叠错误`element`中每个`Next`语句。  
  
 如果你的代码依赖于遍历以特定的顺序集合`For Each`...`Next`循环不是最佳选择，除非你知道的枚举器对象的特征，否则该集合公开。 遍历的顺序不确定的 Visual Basic 中，但通过<xref:System.Collections.IEnumerator.MoveNext%2A>的枚举器对象的方法。 因此，你可能无法预测哪些集合的元素是在中返回的第一个`element`，或者其中的下一个要返回给定元素之后。 您可能会获得更可靠的结果，如使用不同的循环结构， `For`...`Next`或`Do`...`Loop`.  
  
 数据类型`element`必须是这样，数据类型的元素的`group`可以转换为它。  
  
 数据类型`group`必须指的是集合或数组，它是可枚举是引用类型。 通常这意味着，`group`实现的对象是指<xref:System.Collections.IEnumerable>界面`System.Collections`命名空间或<xref:System.Collections.Generic.IEnumerable%601>界面`System.Collections.Generic`命名空间。 `System.Collections.IEnumerable` 定义<xref:System.Collections.IEnumerable.GetEnumerator%2A>方法，返回集合的枚举器对象。 枚举器对象实现`System.Collections.IEnumerator`界面`System.Collections`命名空间，并公开<xref:System.Collections.IEnumerator.Current%2A>属性和<xref:System.Collections.IEnumerator.Reset%2A>和<xref:System.Collections.IEnumerator.MoveNext%2A>方法。 Visual Basic 使用这些遍历该集合。  
  
### <a name="narrowing-conversions"></a>收缩转换  
 当`Option Strict`设置为`On`，收缩转换通常会导致编译器错误。 在`For Each`语句，但是，从中的元素的转换`group`到`element`进行求值和执行在运行时，编译器错误引起的收缩转换将被抑制。  
  
 在下面的示例中，分配`m`作为初始值为`n`时将不会编译`Option Strict`打开，因为转换`Long`到`Integer`都是收缩转换。 在`For Each`语句，但是，任何编译器错误是报告，即使分配给的`number`需要从相同的转换`Long`到`Integer`。 在`For Each`包含大量的语句，运行时错误发生时<xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A>应用于数量很大。  
  
 [!code-vb[VbVbalrStatements#89](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_5.vb)]  
  
### <a name="ienumerator-calls"></a>IEnumerator 调用  
 当执行`For Each`...`Next`循环启动时，Visual Basic 验证`group`引用有效的集合对象。 如果没有，则会引发异常。 否则，它会调用<xref:System.Collections.IEnumerator.MoveNext%2A>方法和<xref:System.Collections.IEnumerator.Current%2A>要返回的第一个元素的枚举器对象的属性。 如果`MoveNext`指示是否有没有下一个元素，即，如果该集合为空，`For Each`循环停止并将控制权传递到后面的语句`Next`语句。 否则，Visual Basic 会将设置`element`到第一个元素和运行此语句块。  
  
 每次 Visual Basic 遇到`Next`语句，它返回到`For Each`语句。 它将再次调用`MoveNext`和`Current`以返回下一个元素，并再次运行块，也不停止根据结果循环。 此过程将继续，直至`MoveNext`指示没有下一个元素或`Exit For`遇到语句。  
  
 **修改集合。** 返回的枚举器对象<xref:System.Collections.IEnumerable.GetEnumerator%2A>通常不允许您更改通过添加、 删除、 替换或重新排序的任何元素的集合。 如果你更改的集合，您已经启动后`For Each`...`Next`循环的枚举器对象将变为无效，和下一步尝试访问的元素会导致<xref:System.InvalidOperationException>异常。  
  
 但是，修改此阻止不取决于通过 Visual Basic 中，而是由的实现<xref:System.Collections.IEnumerable>接口。 就能实现`IEnumerable`以允许进行迭代过程修改一种。 如果你正在考虑进行这种动态修改，请确保你了解的特征`IEnumerable`你使用的集合上实现。  
  
 **修改集合元素。** <xref:System.Collections.IEnumerator.Current%2A>的枚举器对象的属性是[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)，并返回每个集合元素的本地副本。 这意味着，你不能修改元素本身中`For Each`...`Next`循环。 你所做的任何修改会影响仅从本地复制`Current`并不反映回基础集合。 但是，如果元素是引用类型，则可以修改它所指向的实例的成员。 下面的示例修改`BackColor`的每个成员`thisControl`元素。 但是，不能修改`thisControl`本身。  
  
```vb  
Sub lightBlueBackground(ByVal thisForm As System.Windows.Forms.Form)  
    For Each thisControl As System.Windows.Forms.Control In thisForm.Controls  
        thisControl.BackColor = System.Drawing.Color.LightBlue  
    Next thisControl  
End Sub  
```  
  
 前面的示例可以修改`BackColor`的每个成员`thisControl`元素，但是不能修改`thisControl`本身。  
  
 **通过遍历数组。** 因为<xref:System.Array>类实现<xref:System.Collections.IEnumerable>接口，所有数组都公开<xref:System.Array.GetEnumerator%2A>方法。 这意味着你可以循环访问数组与`For Each`...`Next`循环。 但是，你只能读取数组元素。 你不能更改它们。  
  
## <a name="example"></a>示例  
 下面的示例通过使用列出的 C:\ 目录中的所有文件夹<xref:System.IO.DirectoryInfo>类。  
  
 [!code-vb[VbVbalrStatements#124](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_6.vb)]  
  
## <a name="example"></a>示例  
 以下示例阐释了对集合排序的过程。 该示例实例进行排序`Car`存储中的类<xref:System.Collections.Generic.List%601>。 `Car` 类实现 <xref:System.IComparable%601> 接口，此操作需要实现 <xref:System.IComparable%601.CompareTo%2A> 方法。  
  
 每次调用<xref:System.IComparable%601.CompareTo%2A>方法可用于排序的单一比较。 `CompareTo` 方法中用户编写的代码针对当前对象与另一个对象的每个比较返回一个值。 如果当前对象小于另一个对象，则返回的值小于零；如果当前对象大于另一个对象，则返回的值大于零；如果当前对象等于另一个对象，则返回的值等于零。 这使你可以在代码中定义大于、小于和等于条件。  
  
 在 `ListCars` 方法中，`cars.Sort()` 语句对列表进行排序。 对 <xref:System.Collections.Generic.List%601> 的 <xref:System.Collections.Generic.List%601.Sort%2A> 方法的此调用将导致为 `List` 中的 `Car` 对象自动调用 `CompareTo` 方法。  
  
 [!code-vb[VbVbalrStatements#125](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_7.vb)]  
  
## <a name="see-also"></a>请参阅  
 [集合](../../../standard/collections/index.md)  
 [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [循环结构](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [While...End While 语句](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Do...Loop 语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [扩大转换和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [对象初始值设定项：命名类型和匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [集合初始值设定项](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [数组](../../../visual-basic/programming-guide/language-features/arrays/index.md)
