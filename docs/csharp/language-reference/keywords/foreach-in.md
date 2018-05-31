---
title: foreach，in（C# 参考）
ms.date: 05/24/2018
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: b6b7dc0a4d3970ddfbbb6635ccebbbd5b75671e4
ms.sourcegitcommit: 54231aa56fca059e9297888a96fbca1d4cf3746c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2018
ms.locfileid: "34549370"
---
# <a name="foreach-in-c-reference"></a>foreach，in（C# 参考）

`foreach` 语句为类型实例中实现 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 或 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 接口的每个元素执行语句或语句块。 `foreach` 语句不局限于这些类型，它可应用于满足以下条件的任何类型的实例：

- 具有公共无参数 `GetEnumerator` 方法，其返回类型为类、结构或接口类型。
- `GetEnumerator` 方法的返回类型具有公共 `Current` 属性和公共无参数 `MoveNext` 方法（其返回类型为 <xref:System.Boolean>）。

在 `foreach` 语句块中的任何点上，可以使用 [break](break.md) 关键字中断循环，或者可以使用 [continue](continue.md) 关键字继续执行到循环中的下一次迭代。 还可以使用 [goto](goto.md)、[return](return.md) 或 [throw](throw.md) 语句退出 `foreach` 循环。

## <a name="examples"></a>示例

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

以下示例介绍 `foreach` 语句的使用，其中包含实现 <xref:System.Collections.Generic.IEnumerable%601> 接口的 <xref:System.Collections.Generic.List%601> 类型的实例：

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

下一个示例使用 `foreach` 语句，其中包含 <xref:System.Span%601?displayProperty=nameWithType> 类型的实例，该实例不实现任何接口：

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

## <a name="c-language-specification"></a>C# 语言规范

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>请参阅

[foreach 语句（C# 语言规范）](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement)  
[对数组使用 foreach](../../programming-guide/arrays/using-foreach-with-arrays.md)  
[for](for.md)  
[迭代语句](iteration-statements.md)  
[C# 关键字](index.md)  
[C# 参考](../index.md)  
[C# 编程指南](../../programming-guide/index.md)  