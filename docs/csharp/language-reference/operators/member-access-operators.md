---
title: 成员访问运算符 - C# 参考
description: 了解可用于访问类型成员的 C# 运算符。
ms.date: 05/09/2019
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
helpviewer_keywords:
- member access operators [C#]
- member access operator [C#]
- dot operator [C#]
- . operator [C#]
- subscript operator [C#]
- square brackets [] operator [C#]
- indexer operator [C#]
- '[] operator [C#]'
- null-conditional operators [C#]
- Elvis operator [C#]
- ?. operator [C#]
- ?[] operator [C#]
- invocation operator [C#]
- method call [C#]
- method invocation [C#]
- delegate invocation [C#]
- () operator [C#]
ms.openlocfilehash: eec70f5446eec11fa4e241b86eed4ed8d6146f85
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66195781"
---
# <a name="member-access-operators-c-reference"></a>成员访问运算符（C# 参考）

访问类型成员时，可能会使用以下运算符：

- [`.`（成员访问）](#member-access-operator-)：用于访问命名空间或类型的成员
- [`[]`（数组元素或索引器访问）](#indexer-operator-)：用于访问数组元素或类型索引器
- [`?.` 和 `?[]`（null 条件运算符）](#null-conditional-operators--and-)：仅当操作数为非 null 时才用于执行成员或元素访问运算
- [`()`（调用）](#invocation-operator-)：用于调用被访问的方法或调用委托

## <a name="member-access-operator-"></a>成员访问运算符 .

可以使用 `.` 标记来访问命名空间或类型的成员，如以下示例所示：

- 使用 `.` 访问命名空间内的嵌套命名空间，如以下 [`using` directive](../keywords/using-directive.md) 的示例所示：

  [!code-csharp[nested namespaces](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#NestedNamespace)]

- 使用 `.` 构成限定名称以访问命名空间中的类型，如下面的代码所示：

  [!code-csharp[qualified name](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#QualifiedName)]

  使用 [`using` 指令](../keywords/using-directive.md)来使用可选的限定名称。

- 使用 `.` 访问[类型成员](../../programming-guide/classes-and-structs/index.md#members)（静态和非静态），如下面的代码所示：

  [!code-csharp-interactive[type members](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#TypeMemberAccess)]

还可以使用 `.` 访问[扩展方法](../../programming-guide/classes-and-structs/extension-methods.md)。

## <a name="indexer-operator-"></a>索引器运算符 []

方括号 `[]` 通常用于数组、索引器或指针元素访问。

### <a name="array-access"></a>数组访问

下面的示例演示如何访问数组元素：

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Arrays)]

如果数组索引超出数组相应维度的边界，将引发 <xref:System.IndexOutOfRangeException>。

如上述示例所示，在声明数组类型或实例化数组实例时，还会使用方括号。

有关数组的详细信息，请参阅[数组](../../programming-guide/arrays/index.md)。

### <a name="indexer-access"></a>索引器访问

下面的示例使用 .NET <xref:System.Collections.Generic.Dictionary%602>类型来演示索引器访问：

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Indexers)]

使用索引器，可通过类似于编制数组索引的方式对用户定义类型的实例编制索引。 与必须是整数的数组索引不同，可以将索引器参数声明为任何类型。

有关索引器的详细信息，请参阅[索引器](../../programming-guide/indexers/index.md)。

### <a name="other-usages-of-"></a>[] 的其他用法

要了解指针元素访问，请参阅[与指针相关的运算符](pointer-related-operators.md)一文的[指针元素访问运算符 []](pointer-related-operators.md#pointer-element-access-operator-) 部分。

方括号还用于指定[属性](../../programming-guide/concepts/attributes/index.md)：

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a>Null 条件运算符 ?. 和 ?[]

Null 条件运算符在 C# 6 及更高版本中可用，仅当操作数的计算结果为非 null 时，null 条件运算符才会将成员访问 `?.` 或元素访问 `?[]` 运算应用于其操作数。 如果操作数的计算结果为 `null`，则应用运算符的结果为 `null`。 Null 条件成员访问运算符 `?.` 也称为 Elvis 运算符。

NULL 条件运算符采用最小化求值策略。 也就是说，如果条件成员或元素访问运算链中的一个运算返回 `null`，则链的其余部分不会执行。 在以下示例中，如果 `A` 的计算结果为 `null`，则不会计算 `B`；如果 `A` 或 `B` 的计算结果为 `null`，则不会计算 `C`：

```csharp
A?.B?.Do(C);
A?.B?[C];
```

以下示例演示了 `?.` 和 `?[]` 运算符的用法：

[!code-csharp-interactive[null-conditional operators](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#NullConditional)]

上述示例还展示了 [null 合并运算符](null-coalescing-operator.md)的用法。 可能会使用 null 合并运算符来提供替代表达式，以便在 null 条件运算的结果为 `null` 时用于计算。

### <a name="thread-safe-delegate-invocation"></a>线程安全的委托调用

使用 `?.` 运算符来检查委托是否非 null 并以线程安全的方式调用它（例如，[引发事件](../../../standard/events/how-to-raise-and-consume-events.md)时），如下面的代码所示：

```csharp
PropertyChanged?.Invoke(…)
```

该代码等同于将在 C# 5 或更低版本中使用的以下代码：

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-operator-"></a>调用运算符 ()

使用括号 `()` 调用[方法](../../programming-guide/classes-and-structs/methods.md)或调用[委托](../../programming-guide/delegates/index.md)。

以下示例演示如何在使用或不使用参数的情况下调用方法，以及调用委托：

[!code-csharp-interactive[invocation with ()](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Invocation)]

在调用带 [`new`](../keywords/new-operator.md) 运算符的[构造函数](../../programming-guide/classes-and-structs/constructors.md)时，还可以使用括号。

### <a name="other-usages-of-"></a>() 的其他用法

此外可以使用括号来指定表达式中计算操作的顺序。 有关详细信息，请参阅[运算符](../../programming-guide/statements-expressions-operators/operators.md)一文中的[添加括号](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses)部分。 对于按优先级排序的运算符列表，请参阅 [C# 运算符](index.md)。

[强制转换表达式](invocation-operator.md#cast-expression)，调用转换运算符，还使用括号。

## <a name="operator-overloadability"></a>运算符可重载性

`.` 和 `()` 运算符不能重载。 `[]` 运算符也被视为非可重载运算符。 使用[索引器](../../programming-guide/indexers/index.md)以支持对用户定义的类型编制索引。

## <a name="c-language-specification"></a>C# 语言规范

有关更多信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的以下部分：

- [成员访问](~/_csharplang/spec/expressions.md#member-access)
- [元素访问](~/_csharplang/spec/expressions.md#element-access)
- [Null 条件运算符](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [调用表达式](~/_csharplang/spec/expressions.md#invocation-expressions)

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)
- [??（空合运算符）](null-coalescing-operator.md)
