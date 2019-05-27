---
title: C# foreach 语句
ms.date: 05/17/2019
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 7a1508db23f60cac487e0171c3db7756bc228fd2
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880539"
---
# <a name="foreach-in-c-reference"></a>foreach，in（C# 参考）

`foreach` 语句为类型实例中实现 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 或 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 接口的每个元素执行语句或语句块。 `foreach` 语句不局限于这些类型，它可应用于满足以下条件的任何类型的实例：

- 具有公共无参数 `GetEnumerator` 方法，其返回类型为类、结构或接口类型。
- `GetEnumerator` 方法的返回类型具有公共 `Current` 属性和公共无参数 `MoveNext` 方法（其返回类型为 <xref:System.Boolean>）。

从 C# 7.3 开始，如果枚举器的 `Current` 属性返回 [引用返回值](ref.md#reference-return-values)（`ref T`，其中 `T` 为集合元素类型），就可以使用 `ref` 或 `ref readonly` 修饰符来声明迭代变量。

在 `foreach` 语句块中的任何点上，可以使用 [break](break.md) 语句中断循环，或者可以使用 [continue](continue.md) 语句继续执行到循环中的下一次迭代。 还可以使用 [goto](goto.md)、[return](return.md) 或 [throw](throw.md) 语句退出 `foreach` 循环。

如果 `foreach` 语句应用为 `null`，则会引发 <xref:System.NullReferenceException>。 如果 `foreach` 语句的源集合为空，则 `foreach` 循环的正文不会被执行，而是被跳过。

## <a name="examples"></a>示例

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

以下示例介绍 `foreach` 语句的使用，其中包含实现 <xref:System.Collections.Generic.IEnumerable%601> 接口的 <xref:System.Collections.Generic.List%601> 类型的实例：

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

下一个示例使用 `foreach` 语句，其中包含 <xref:System.Span%601?displayProperty=nameWithType> 类型的实例，该实例不实现任何接口：

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

下面的示例使用 `ref` 迭代变量来设置 stackalloc 数组中每个项的值。 `ref readonly` 版本循环访问该集合以打印所有值。 `readonly` 声明使用隐式局部变量声明。 隐式变量声明可与 `ref` 或 `ref readonly` 声明配合使用，显式类型化变量声明也一样。

[!code-csharp-interactive[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的 [foreach 语句](~/_csharplang/spec/statements.md#the-foreach-statement)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 关键字](index.md)
- [迭代语句](iteration-statements.md)
- [对数组使用 foreach](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [for 语句](for.md)
