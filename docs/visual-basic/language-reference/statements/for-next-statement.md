---
title: For...Next 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: a60293fc837b6d12810a211892c391f24a46d4e6
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582960"
---
# <a name="fornext-statement-visual-basic"></a>For...Next 语句 (Visual Basic)

按指定次数重复一组语句。

## <a name="syntax"></a>语法

```vb
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a>部件

|部件|描述|
|----------|-----------------|
|`counter`|在 `For` 语句中是必需的。 数值变量。 循环的控制变量。 有关详细信息，请参阅本主题后面的[计数器参数](#BKMK_Counter)。|
|`datatype`|可选。 @No__t_0 的数据类型。 有关详细信息，请参阅本主题后面的[计数器参数](#BKMK_Counter)。|
|`start`|必须的。 数值表达式。 `counter` 的初始值。|
|`end`|必须的。 数值表达式。 @No__t_0 的最终值。|
|`step`|可选。 数值表达式。 每次通过循环 `counter` 递增的量。|
|`statements`|可选。 @No__t_0 和 `Next` 之间的一个或多个语句运行指定的次数。|
|`Continue For`|可选。 将控制转移到下一个循环迭代。|
|`Exit For`|可选。 将控制转移 `For` 循环。|
|`Next`|必须的。 终止 `For` 循环的定义。|

> [!NOTE]
> 此语句中使用 `To` 关键字来指定计数器的范围。 你还可以在[Select .。。Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)和数组声明。 有关数组声明的详细信息，请参阅[Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)。

## <a name="simple-examples"></a>简单示例

使用 `For` .。。当您想要重复一组语句时，`Next` 结构。

在下面的示例中，`index` 变量以值1开始，并随循环的每次迭代递增，并在 `index` 的值达到5之后结束。

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

在下面的示例中，`number` 变量从2开始，在循环的每次迭代后减0.25，并在 `number` 的值达到0后结束。 @No__t_1 的 `Step` 参数会在循环的每次迭代时减少0.25 的值。

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> ... [End While 语句](../../../visual-basic/language-reference/statements/while-end-while-statement.md)或[Do .。。](../../../visual-basic/language-reference/statements/do-loop-statement.md)当您事先不知道在循环中运行语句的次数时，Loop 语句可以正常工作。 但是，当你希望将循环运行特定次数时，`For` .。。`Next` 循环是更好的选择。 您在第一次进入循环时确定迭代次数。

## <a name="nesting-loops"></a>嵌套循环

可以通过在另一个循环中放置一个循环来嵌套 `For` 循环。 下面的示例演示了嵌套 `For` .。。`Next` 具有不同步骤值的结构。 外部循环为循环的每次迭代创建字符串。 内部循环为循环的每次迭代递减循环计数器变量。

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

嵌套循环时，每个循环必须具有唯一的 `counter` 变量。

你还可以在彼此之间嵌套不同种类的控制结构。 有关详细信息，请参阅[嵌套控制结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)。

## <a name="exit-for-and-continue-for"></a>退出并继续进行

@No__t_0 语句立即退出 `For` ... `Next` 循环并将控制转移到 `Next` 语句后面的语句。

@No__t_0 语句将控制立即传输到循环的下一次迭代。 有关详细信息，请参阅[Continue 语句](../../../visual-basic/language-reference/statements/continue-statement.md)。

下面的示例阐释了 `Continue For` 和 `Exit For` 语句的用法。

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

可以将任意数量的 `Exit For` 语句放入 `For` ... `Next` 圈. 在嵌套 `For` 中使用 ... `Next` 循环，`Exit For` 退出最内层循环，并将控制转移到下一个更高的嵌套级别。

`Exit For` 在你计算某个条件（例如，在 `If` ... `Then` ... `Else` 结构中）后经常使用。 你可能想要在以下条件下使用 `Exit For`：

- 不需要继续循环访问。 错误的值或终止请求可能会创建此条件。

- @No__t_0 .。。`Catch` .。。`Finally` 语句捕获异常。 您可以在 `Finally` 块的末尾使用 `Exit For`。

- 您有一个无限循环，该循环是一种循环，它可以运行很大甚至无限次。 如果检测到这种情况，则可以使用 `Exit For` 来转义循环。 有关详细信息，请参阅[Do .。。循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)。

## <a name="technical-implementation"></a>技术实现

当 `For` .。。`Next` 循环开始，Visual Basic 计算 `start`、`end` 和 `step`。 Visual Basic 此时仅计算这些值，然后将 `start` 分配给 `counter`。 在语句块运行之前，Visual Basic 将 `counter` 与 `end` 进行比较。 如果 `counter` 已大于 `end` 值（如果 `step` 为负，则为较小的值），则 `For` 循环结束，并控制将传递到位于 `Next` 语句后面的语句。 否则，语句块将运行。

每次 Visual Basic 遇到 `Next` 语句时，它会递增 `counter` `step` 并返回到 `For` 语句。 再次将 `counter` 与 `end` 进行比较，并再次运行该块或退出循环，具体取决于结果。 此过程将继续，直至 `counter` 传递 `end` 或遇到 `Exit For` 语句为止。

在 `counter` 通过 `end` 之前，循环不会停止。 如果 `counter` 等于 `end`，则循环将继续。 确定是否运行块的比较 `counter`  <=  `end` 如果 `step` 为正值，`counter` 为负数  >=  `end` `step`。

如果在循环中更改 `counter` 的值，则可能会更难读取和调试代码。 更改 `start`、`end` 或 `step` 的值不会影响在第一次输入循环时确定的迭代值。

如果嵌套循环，当编译器在内部级别的 `Next` 语句前面遇到外部嵌套级别的 `Next` 语句时，编译器会发出错误信号。 但是，只有在每个 `Next` 语句中指定 `counter` 时，编译器才能检测到此重叠错误。

### <a name="step-argument"></a>步骤参数

@No__t_0 的值可以是正数也可以是负数。 此参数根据下表确定循环处理：

|**步骤值**|**如果**|
|--------------------|--------------------------|
|正或零|`counter` <= `end`|
|负数|`counter` >= `end`|

@No__t_0 的默认值为1。

### <a name="BKMK_Counter"></a>计数器参数

下表指示 `counter` 是否定义了作用域为整个 `For…Next` 循环的新局部变量。 这一决定取决于 `datatype` 是否存在以及 `counter` 是否已定义。

|@No__t_0 存在吗？|@No__t_0 是否已定义？|Result （`counter` 是否定义了作用域为整个 `For...Next` 循环的新局部变量）|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|No|是|不能，因为已定义 `counter`。 如果 `counter` 的作用域不是过程所本地的，则会发生编译时警告。|
|No|No|可以。 数据类型从 `start`、`end` 和 `step` 表达式中推断。 有关类型推理的信息，请参阅[选项推断语句](../../../visual-basic/language-reference/statements/option-infer-statement.md)和[局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。|
|是|是|是，但仅当现有 `counter` 变量在过程外定义时才存在。 该变量保持独立。 如果现有 `counter` 变量的作用域是过程的本地值，则会发生编译时错误。|
|是|No|可以。|

@No__t_0 的数据类型决定迭代的类型，该类型必须是以下类型之一：

- @No__t_0、`SByte`、`UShort`、`Short`、`UInteger`、`Integer`、`ULong`、`Long`、`Decimal`、`Single` 或 0。

- 使用[Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)声明的枚举。

- 一个 `Object`。

- 具有以下运算符的类型 `T`，其中 `B` 是可在 `Boolean` 表达式中使用的类型。

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

您可以选择在 `Next` 语句中指定 `counter` 变量。 此语法可提高程序的可读性，尤其是在嵌套 `For` 循环的情况下。 您必须指定在相应的 `For` 语句中显示的变量。

@No__t_0、`end` 和 `step` 表达式的计算结果可以为扩大到 `counter` 类型的任何数据类型。 如果对 `counter` 使用用户定义的类型，则可能需要定义 `CType` 转换运算符，以将 `start`、`end` 或 `step` 的类型转换为 `counter` 的类型。

## <a name="example"></a>示例

下面的示例从泛型列表中移除所有元素。 而不是[为每个 .。。下一条语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)，示例演示了 `For` .。。`Next` 按降序循环访问的语句。 该示例使用此方法，因为 `removeAt` 方法导致删除的元素后的元素具有更低的索引值。

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a>示例

下面的示例循环访问通过使用[Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)声明的枚举。

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a>示例

在下面的示例中，语句参数使用类，该类具有用于 `+`、`-`、`>=` 和 `<=` 运算符的运算符重载。

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a>请参阅

- <xref:System.Collections.Generic.List%601>
- [循环结构](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [While...End While 语句](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Do...Loop 语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [嵌套的控件结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)
- [集合](../../programming-guide/concepts/collections.md)
