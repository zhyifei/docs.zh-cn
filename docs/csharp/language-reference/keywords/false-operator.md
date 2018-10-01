---
title: false 运算符（C# 参考）
ms.date: 07/20/2015
helpviewer_keywords:
- false operator keyword [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: e73113bd37dbb68590267141ad037f78919520bc
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47193783"
---
# <a name="false-operator-c-reference"></a>false 运算符（C# 参考）

返回 [bool](bool.md) 值 `true` 以指示操作数为 `false`，否则返回 `false`。

在 C# 2.0 之前，`true` 和 `false` 运算符都用于创建用户定义的可为 null 的值类型，该类型可与 `SqlBool` 等类型兼容。 但是，现在该语言提供对可为 null 的值类型的内置支持，并且应尽可能使用这些支持而不是重载 `true` 和 `false` 运算符。 有关详细信息，请参阅[可以为 Null 的类型](../../programming-guide/nullable-types/index.md)。

对于可以为 null 的布尔值，表达式 `a != b` 不一定等同于 `!(a == b)`，因为两个值（或之一）可能为 null。 必须分别重载 `true` 和 `false` 运算符以正确处理表达式中的 null 值。 下面的示例演示如何重载和使用 `true` 和 `false` 运算符。

[!code-csharp[csrefKeywordsOperator#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#16)]

重载 `true` 和 `false` 运算符的类型可以用于 [if](if-else.md)、[do](do.md)、[while](while.md) 和 [for](for.md) 语句以及[条件表达式](../operators/conditional-operator.md)中的控制表达式。

如果某一类型定义运算符 `false`，则它还必须定义运算符 [true](true.md)。

类型不能直接重载条件逻辑运算符 [&&](../operators/conditional-and-operator.md) 和 [&#124;&#124;](../operators/conditional-or-operator.md)，但可以通过重载常规逻辑运算符及运算符 `true` 和 `false` 达到同样的效果。

## <a name="c-language-specification"></a>C# 语言规范

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)  
- [C# 编程指南](../../programming-guide/index.md)  
- [C# 关键字](index.md)  
- [C# 运算符](../operators/index.md)  
- [true](true.md)  