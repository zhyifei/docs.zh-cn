---
title: 可以为 null 的值类型-Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
ms.openlocfilehash: 072496a560775a8f79274f1d44dd389d6ed5b40d
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "71351766"
---
# <a name="nullable-value-types-visual-basic"></a>可以为 Null 的值类型 (Visual Basic)

有时，您在某些情况下使用的值类型不具有定义的值。 例如，数据库中的字段可能必须区分分配的值是否有意义，并且没有分配值。 可以对值类型进行扩展，使其使用普通值或 null 值。 此类扩展称为*可以为 null 的类型*。

每个可以为 null 的类型都是从泛型 <xref:System.Nullable%601> 结构构造的。 考虑使用跟踪工作相关活动的数据库。 下面的示例构造一个可以为 null 的 @no__t 类型，并声明该类型的变量。 可以通过三种方式编写声明：

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

变量 `ridesBusToWork` 可以保存值 `True`、值 `False` 或根本没有值。 默认情况下，它的初始默认值为 "无" 值，在这种情况下，这可能意味着尚未获取此人的信息。 与此相反，`False` 表示已获得信息，而不会使总线工作。

可以声明具有可以为 null 的类型的变量和属性，并且可以使用可以为 null 的类型的元素声明数组。 您可以使用可以为 null 的类型作为参数来声明过程，并且可以从 @no__t 0 过程返回可为 null 的类型。

无法在引用类型（如数组、`String` 或类）上构造可以为 null 的类型。 基础类型必须为值类型。 有关更多信息，请参见 [Value Types and Reference Types](value-types-and-reference-types.md)。

## <a name="using-a-nullable-type-variable"></a>使用可以为 Null 的类型变量

可以为 null 的类型的最重要成员是其 @no__t 为0，@no__t 为-1 个属性。 对于可以为 null 的类型的变量，<xref:System.Nullable%601.HasValue%2A> 指示该变量是否包含定义的值。 如果 <xref:System.Nullable%601.HasValue%2A> @no__t 为-1，则可以从 @no__t 中读取值。 请注意，@no__t 0 和 @no__t 都是 `ReadOnly` 属性。

### <a name="default-values"></a>默认值

使用可以为 null 的类型声明变量时，其 <xref:System.Nullable%601.HasValue%2A> 属性的默认值为 `False`。 这意味着，默认情况下，该变量没有定义的值，而不是其基础值类型的默认值。 在下面的示例中，变量 `numberOfChildren` 最初没有定义的值，即使 `Integer` 类型的默认值为0。

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

空值有助于指示未定义或未知的值。 如果 `numberOfChildren` 已声明为 `Integer`，则没有任何值可指示该信息当前不可用。

### <a name="storing-values"></a>存储值

以典型方式将值存储在可以为 null 的类型的变量或属性中。 下面的示例将值赋给在上一个示例中声明的变量 `numberOfChildren`。

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

如果可为 null 的类型的变量或属性包含定义的值，则可以使其恢复到未分配值的初始状态。 为此，可将变量或属性设置为 `Nothing`，如下面的示例所示。

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> 尽管可以将 @no__t 0 赋给一个可以为 null 的类型的变量，但不能使用等号为 `Nothing` 进行测试。 使用等号 `someVar = Nothing` 的比较始终计算为 `Nothing`。 你可以测试 @no__t 的变量 <xref:System.Nullable%601.HasValue%2A> 属性，或使用 @no__t 2 或 `IsNot` 运算符测试。

### <a name="retrieving-values"></a>检索值

若要检索可为 null 的类型的变量的值，您应该首先测试其 <xref:System.Nullable%601.HasValue%2A> 属性以确认它具有值。 如果尝试在 <xref:System.Nullable%601.HasValue%2A> @no__t 时读取值-1，Visual Basic 将引发 <xref:System.InvalidOperationException> 异常。 下面的示例演示了读取前面示例的变量 `numberOfChildren` 的建议方法。

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a>比较可以为 Null 的类型

在布尔表达式中使用可以为 null 的 @no__t 变量时，结果可以是 `True`、`False` 或 `Nothing`。 下面是 `And` 和 `Or` 的事实数据表。 因为 `b1` 和 @no__t 现在有三个可能的值，所以有九个计算组合。

|b1|b2|b1 和 b2|b1 或 b2|
|--------|--------|---------------|--------------|
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|
|`Nothing`|`True`|`Nothing`|`True`|
|`Nothing`|`False`|`False`|`Nothing`|
|`True`|`Nothing`|`Nothing`|`True`|
|`True`|`True`|`True`|`True`|
|`True`|`False`|`False`|`True`|
|`False`|`Nothing`|`False`|`Nothing`|
|`False`|`True`|`False`|`True`|
|`False`|`False`|`False`|`False`|

如果布尔变量或表达式的值 `Nothing`，则不 @no__t 为-1，也不 `false`。 请看下面的示例。

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

在此示例中，`b1 And b2` 的计算结果为 `Nothing`。 因此，在每个 @no__t 语句中执行 `Else` 子句，输出如下所示：

`Expression is not true`

`Expression is not false`

> [!NOTE]
> 在第一个计算为 `Nothing` 时，@no__t 0 和 `OrElse` （使用短路计算）必须计算其第二个操作数。

## <a name="propagation"></a>传播

如果算术、比较、移位或类型运算的一个或两个操作数可以为 null，则该运算的结果也可以为 null。 如果两个操作数的值都不 `Nothing`，则对操作数的基础值执行运算，就好像这两个操作数都不是可以为 null 的类型一样。 在下面的示例中，变量 `compare1` 和 @no__t 均隐式类型化。 如果将鼠标指针停留在其上，则会看到编译器将为这两个文件推断可以为 null 的类型。

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

如果一个或两个操作数的值都为 `Nothing`，则结果将 `Nothing`。

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a>对数据使用可以为 Null 的类型

数据库是使用可以为 null 的类型的最重要的地方之一。 并非所有数据库对象当前都支持可以为 null 的类型，但设计器生成的表适配器则执行此操作。 请参阅[对可以为 null 的类型的 TableAdapter 支持](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types)。

## <a name="see-also"></a>请参阅

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [数据类型](index.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [数据类型疑难解答](troubleshooting-data-types.md)
- [使用 Tableadapter 填充数据集](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [If 运算符](../../../language-reference/operators/if-operator.md)
- [局部类型推理](../variables/local-type-inference.md)
- [Is 运算符](../../../language-reference/operators/is-operator.md)
- [IsNot 运算符](../../../language-reference/operators/isnot-operator.md)
- [使用可以为 Null 的C#值类型（）](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
