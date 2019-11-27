---
title: For Each...Next 语句
ms.date: 07/20/2015
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
ms.openlocfilehash: 572f1efc0148bd8df4f13fa5651e74249caa45a7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351198"
---
# <a name="for-eachnext-statement-visual-basic"></a>For Each...Next 语句 (Visual Basic)

为集合中的每个元素重复一组语句。

## <a name="syntax"></a>语法

```vb
For Each element [ As datatype ] In group
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ element ]
```

## <a name="parts"></a>部件

|术语|Definition|
|---|---|
|`element`|在 `For Each` 语句中是必需的。 在 `Next` 语句中是可选的。 各种. 用于循环访问集合中的元素。|
|`datatype`|如果[`Option Infer`](option-infer-statement.md)为 on （默认值）或已声明 `element`，则为可选;如果 `Option Infer` 为 off，并且尚未声明 `element`，则为必需。 `element`的数据类型。|
|`group`|必需。 类型为集合类型或对象的变量。 引用要对其重复 `statements` 的集合。|
|`statements`|可选。 `For Each` 和 `Next` 之间的一个或多个语句，这些语句在 `group`中的每一项上运行。|
|`Continue For`|可选。 将控制转移到 `For Each` 循环的开头。|
|`Exit For`|可选。 将控制转移 `For Each` 循环。|
|`Next`|必需。 终止 `For Each` 循环的定义。|

## <a name="simple-example"></a>简单示例

若要为集合或数组的每个元素重复一组语句，请使用 `For Each`...`Next` 循环。

> [!TIP]
> [用于 。](../../../visual-basic/language-reference/statements/for-next-statement.md)如果可以将循环的每次迭代与控件变量相关联，并确定该变量的初始值，则下一语句会很好地运行。 但是，在处理集合时，初始值和 final 值的概念没有意义，并且您不一定知道该集合具有多少元素。 在这种情况下，`For Each``Next` 循环通常是更好的选择。

在下面的示例中，`For Each`...`Next` 语句循环访问列表集合的所有元素。

[!code-vb[VbVbalrStatements#121](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#121)]

有关更多示例，请参阅[集合](../../../standard/collections/index.md)和[数组](../../../visual-basic/programming-guide/language-features/arrays/index.md)。

## <a name="nested-loops"></a>嵌套循环

可以通过在另一个循环中放置一个循环来嵌套 `For Each` 循环。

下面的示例演示了嵌套 `For Each`...`Next` 构造.

[!code-vb[VbVbalrStatements#122](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#122)]

嵌套循环时，每个循环必须具有唯一的 `element` 变量。

您还可以在彼此之间嵌套不同种类的控制结构。 有关详细信息，请参阅[嵌套控制结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)。

## <a name="exit-for-and-continue-for"></a>退出并继续进行

[Exit For](../../../visual-basic/language-reference/statements/exit-statement.md)语句导致执行退出 `For`...`Next` 循环并将控制转移到 `Next` 语句后面的语句。

`Continue For` 语句将控制立即传输到循环的下一次迭代。 有关详细信息，请参阅[Continue 语句](../../../visual-basic/language-reference/statements/continue-statement.md)。

下面的示例演示如何使用 `Continue For` 和 `Exit For` 语句。

[!code-vb[VbVbalrStatements#123](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#123)]

可以将任意数量的 `Exit For` 语句置于 `For Each` 循环中。 在嵌套的 `For Each` 循环中使用时，`Exit For` 会导致执行退出最内层的循环，并将控制转移到下一个更高的嵌套级别。

在对某些条件进行计算后（例如，在 `If`...`Then`...`Else` 结构中），通常使用 `Exit For`。 你可能想要在以下条件下使用 `Exit For`：

- 不需要继续循环访问。 这可能是由错误值或终止请求引起的。

- `Try`...`Catch`...`Finally`中捕获到了异常。您可以在 `Finally` 块的末尾使用 `Exit For`。

- 有一个无限循环，该循环是一种循环，它可以运行很大甚至无限次。 如果检测到这种情况，则可以使用 `Exit For` 来转义循环。 有关详细信息，请参阅[Do 。循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)。

## <a name="iterators"></a>迭代器

使用*迭代器*对集合执行自定义迭代。 迭代器可以是函数或 `Get` 访问器。 它使用 `Yield` 语句一次返回一个集合的每个元素。

使用 `For Each...Next` 语句调用迭代器。 `For Each` 循环的每次迭代都会调用迭代器。 在迭代器中到达 `Yield` 语句时，将返回 `Yield` 语句中的表达式，并保留代码中的当前位置。 下次调用迭代器时，将从该位置重新开始执行。

下面的示例使用迭代器函数。 迭代器函数的 `Yield` 语句位于[For 。下一个](../../../visual-basic/language-reference/statements/for-next-statement.md)循环。 在 `ListEvenNumbers` 方法中，`For Each` 语句体的每次迭代都会创建对迭代器函数的调用，该函数将继续执行下一 `Yield` 语句。

[!code-vb[VbVbalrStatements#127](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#127)]

有关详细信息，请参阅[迭代](../../programming-guide/concepts/iterators.md)器、 [Yield 语句](../../../visual-basic/language-reference/statements/yield-statement.md)和[迭代器](../../../visual-basic/language-reference/modifiers/iterator.md)。

## <a name="technical-implementation"></a>技术实现

当 `For Each`...`Next` 语句运行时，Visual Basic 在循环开始之前仅计算一次集合。 如果语句块 `element` 或 `group`发生更改，则这些更改不会影响循环的迭代。

当集合中的所有元素连续分配到 `element`时，`For Each` 循环停止，并控制传递到 `Next` 语句后面的语句。

如果[选项推断](option-infer-statement.md)为 on （其默认设置），则 Visual Basic 编译器可以推断 `element`的数据类型。 如果它处于关闭状态，并且 `element` 未在循环外声明，则必须在 `For Each` 语句中声明它。 若要显式声明 `element` 的数据类型，请使用 `As` 子句。 除非在 `For Each`...`Next` 构造之外定义元素的数据类型，否则其作用域为循环的主体。 请注意，不能在循环的外部和内部声明 `element`。

您可以选择在 `Next` 语句中指定 `element`。 这会提高程序的可读性，尤其是在嵌套 `For Each` 循环的情况下。 您必须指定与相应的 `For Each` 语句中显示的变量相同的变量。

你可能希望避免在循环内更改 `element` 的值。 这样做可以更难读取和调试代码。 更改 `group` 的值不会影响集合或其元素，这是在第一次进入循环时确定的。

嵌套循环时，如果在内部级别 `Next` 之前遇到外部嵌套级别的 `Next` 语句，则编译器会发出错误消息。 但是，只有在每个 `Next` 语句中指定 `element` 时，编译器才能检测到此重叠错误。

如果你的代码依赖于遍历特定顺序的集合，则 `For Each`...`Next` 循环并不是最佳选择，除非你知道该集合公开的枚举器对象的特征。 遍历的顺序并不由 Visual Basic 确定，而是由枚举器对象的 <xref:System.Collections.IEnumerator.MoveNext%2A> 方法决定。 因此，你可能无法预测 `element`中返回的第一个元素，或者在给定元素后返回的下一个元素。 你可能会使用不同的循环结构（如 `For``Next` 或 `Do`...`Loop`来实现更可靠的结果。

运行时必须能够将 `group` 中的元素转换为 `element`。 [`Option Strict`] 语句控制是否允许扩大转换和收缩转换（`Option Strict` 为 off、其默认值），或者是否只允许扩大转换（`Option Strict` 为 on）。 有关详细信息，请参阅[收缩转换](#narrowing-conversions)。

`group` 的数据类型必须为引用类型，该引用类型引用可枚举的集合或数组。 最常见的情况是，这意味着 `group` 引用实现了 `System.Collections` 命名空间的 <xref:System.Collections.IEnumerable> 接口或 `System.Collections.Generic` 命名空间的 <xref:System.Collections.Generic.IEnumerable%601> 接口的对象。 `System.Collections.IEnumerable` 定义 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 方法，该方法返回集合的枚举器对象。 枚举器对象实现 `System.Collections` 命名空间的 `System.Collections.IEnumerator` 接口，并公开 <xref:System.Collections.IEnumerator.Current%2A> 属性和 <xref:System.Collections.IEnumerator.Reset%2A> 和 <xref:System.Collections.IEnumerator.MoveNext%2A> 方法。 Visual Basic 使用它们遍历集合。

### <a name="narrowing-conversions"></a>收缩转换

将 `Option Strict` 设置为 `On`时，收缩转换通常会导致编译器错误。 但是，在 `For Each` 语句中，将在运行时计算和执行从 `group` 中的元素到 `element` 的转换，并取消收缩转换导致的编译器错误。

在下面的示例中，当 `Option Strict` 为 on 时，将 `m` 的赋值 `n` 不会进行编译，因为 `Long` 到 `Integer` 的转换是收缩转换。 但在 `For Each` 语句中，不会报告任何编译器错误，即使向 `number` 赋值也需要从 `Long` 到 `Integer`相同的转换。 在包含大量的 `For Each` 语句中，当 <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> 应用于大数字时，将发生运行时错误。

[!code-vb[VbVbalrStatements#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class3.vb#89)]

### <a name="ienumerator-calls"></a>IEnumerator 调用

当执行 `For Each`...`Next` 循环开始时，Visual Basic 将验证 `group` 是否引用了有效的集合对象。 如果不是，则会引发异常。 否则，它将调用 <xref:System.Collections.IEnumerator.MoveNext%2A> 方法和枚举器对象的 <xref:System.Collections.IEnumerator.Current%2A> 属性以返回第一个元素。 如果 `MoveNext` 指示没有下一个元素（即，如果集合为空），则 `For Each` 循环停止，并控制传递到 `Next` 语句后面的语句。 否则，Visual Basic 将 `element` 设置为第一个元素，并运行语句块。

每次 Visual Basic 遇到 `Next` 语句时，它都会返回到 `For Each` 语句。 再次调用 `MoveNext` 和 `Current`，返回下一个元素，并再次运行该块或停止循环，具体取决于结果。 此过程将继续，直至 `MoveNext` 指示没有下一个元素或 `Exit For` 语句时。

**修改集合。** <xref:System.Collections.IEnumerable.GetEnumerator%2A> 通常返回的枚举器对象不允许通过添加、删除、替换或重新排序任何元素来更改集合。 如果你在启动 `For Each`...`Next` 循环后更改集合，则枚举器对象将变为无效，并且下一次尝试访问元素时将导致 <xref:System.InvalidOperationException> 异常。

但是，这种修改阻塞不是由 Visual Basic 确定的，而是由实现 <xref:System.Collections.IEnumerable> 接口。 可以通过允许在迭代期间进行修改的方式来实现 `IEnumerable`。 如果考虑执行此类动态修改，请确保了解所使用的集合的 `IEnumerable` 实现的特征。

**修改集合元素。** 枚举器对象的 <xref:System.Collections.IEnumerator.Current%2A> 属性是[只读](../../../visual-basic/language-reference/modifiers/readonly.md)的，它返回每个集合元素的本地副本。 这意味着不能在 `For Each`...`Next` 循环中修改元素本身。 您所做的任何修改只会影响 `Current` 的本地副本，并且不会反映回基础集合中。 但是，如果元素是引用类型，则可以修改它所指向的实例的成员。 下面的示例修改每个 `thisControl` 元素的 `BackColor` 成员。 但不能修改 `thisControl` 本身。

```vb
Sub LightBlueBackground(thisForm As System.Windows.Forms.Form)
    For Each thisControl In thisForm.Controls
        thisControl.BackColor = System.Drawing.Color.LightBlue
    Next thisControl
End Sub
```

前面的示例可以修改每个 `thisControl` 元素的 `BackColor` 成员，不过它不能修改 `thisControl` 本身。

**遍历数组。** 由于 <xref:System.Array> 类实现 <xref:System.Collections.IEnumerable> 接口，因此所有数组都公开了 <xref:System.Array.GetEnumerator%2A> 方法。 这意味着，可以使用 `For Each`...`Next` 循环来循环访问数组。 但是，只能读取数组元素。 不能更改它们。

## <a name="example"></a>示例

下面的示例列出了 C：\ 中的所有文件夹使用 <xref:System.IO.DirectoryInfo> 类的目录。

[!code-vb[VbVbalrStatements#124](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#124)]

## <a name="example"></a>示例

以下示例阐释了对集合排序的过程。 该示例对存储在 <xref:System.Collections.Generic.List%601>中的 `Car` 类的实例进行排序。 `Car` 类实现 <xref:System.IComparable%601> 接口，此操作需要实现 <xref:System.IComparable%601.CompareTo%2A> 方法。

每次调用 <xref:System.IComparable%601.CompareTo%2A> 方法都会产生用于排序的单个比较。 `CompareTo` 方法中用户编写的代码针对当前对象与另一个对象的每个比较返回一个值。 如果当前对象小于另一个对象，则返回的值小于零；如果当前对象大于另一个对象，则返回的值大于零；如果当前对象等于另一个对象，则返回的值等于零。 这使你可以在代码中定义大于、小于和等于条件。

在 `ListCars` 方法中，`cars.Sort()` 语句对列表进行排序。 对 <xref:System.Collections.Generic.List%601.Sort%2A> 的 <xref:System.Collections.Generic.List%601> 方法的此调用将导致为 `CompareTo` 中的 `Car` 对象自动调用 `List` 方法。

[!code-vb[VbVbalrStatements#125](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#125)]

## <a name="see-also"></a>另请参阅

- [集合](../../../standard/collections/index.md)
- [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [循环结构](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [While...End While 语句](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Do...Loop 语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [扩大转换和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [对象初始值设定项：命名类型和匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [集合初始值设定项](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [数组](../../../visual-basic/programming-guide/language-features/arrays/index.md)
