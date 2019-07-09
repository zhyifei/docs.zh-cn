---
title: 运算符重载 - C# 引用
description: 了解如何重载 C# 运算符以及哪些运算符可重载。
ms.date: 07/05/2019
f1_keywords:
- operator_CSharpKeyword
helpviewer_keywords:
- operator keyword [C#]
- operator overloading [C#]
ms.openlocfilehash: f9085f2a550dfacc670857a70f5b22de9e028107
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610590"
---
# <a name="operator-overloading-c-reference"></a>运算符重载（C# 引用）

用户定义的类型可重载预定义的 C# 运算符。 也就是说，当一个或两个运算符都是某类型时，此类型可提供操作的自定义实现。 [可重载运算符](#overloadable-operators)部分介绍了哪些 C# 运算符可重载。

使用 `operator` 关键字来声明运算符。 运算符声明必须符合以下规则：

- 同时包含 `public` 和 `static` 修饰符。
- 一元运算符采用一个参数。 二元运算符采用两个参数。 在每种情况下，都至少有一个参数必须具有类型 `T` 或 `T?`，其中 `T` 是包含运算符声明的类型。

下面的示例定义了一个表示有理数的简单结构。 该结构会重载一些[算术运算符](arithmetic-operators.md)：

[!code-csharp[fraction example](~/samples/csharp/language-reference/operators/OperatorOverloading.cs)]

## <a name="overloadable-operators"></a>可重载运算符

下表提供了 C# 运算符可重载性的相关信息：

| 运算符 | 可重载性 |
| --------- | --------------- |
|[+](arithmetic-operators.md#unary-plus-and-minus-operators)、[-](arithmetic-operators.md#unary-plus-and-minus-operators)、[!](boolean-logical-operators.md#logical-negation-operator-)、[~](bitwise-and-shift-operators.md#bitwise-complement-operator-)、[++](arithmetic-operators.md#increment-operator-)、[--](arithmetic-operators.md#decrement-operator---)、[true](true-false-operators.md)、[false](true-false-operators.md)|这些一元运算符可以进行重载。|
|[+](addition-operator.md)、[-](subtraction-operator.md)、[\*](arithmetic-operators.md#multiplication-operator-)、[/](arithmetic-operators.md#division-operator-)、[%](arithmetic-operators.md#remainder-operator-)、[&](boolean-logical-operators.md#logical-and-operator-)、[&#124;](boolean-logical-operators.md#logical-or-operator-)、[^](boolean-logical-operators.md#logical-exclusive-or-operator-)、[\<\<](bitwise-and-shift-operators.md#left-shift-operator-)、[>>](bitwise-and-shift-operators.md#right-shift-operator-)、[==](equality-operators.md#equality-operator-)、[!=](equality-operators.md#inequality-operator-)、[\<](comparison-operators.md#less-than-operator-)、[>](comparison-operators.md#greater-than-operator-)、[\<=](comparison-operators.md#less-than-or-equal-operator-)、[>=](comparison-operators.md#greater-than-or-equal-operator-)|这些二元运算符可以进行重载。 某些运算符必须成对重载；有关详细信息，请查看此表后面的备注。|
|[&&](boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124;](boolean-logical-operators.md#conditional-logical-or-operator-)|无法重载条件逻辑运算符。 但是，如果具有已重载的 [`true` 和 `false` 运算符](true-false-operators.md)的类型还以某种方式重载了 `&` 或 <code>&#124;</code> 运算符，则可针对此类型的操作数分别计算 `&&` 或 <code>&#124;&#124;</code> 运算符。 有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的[用户定义条件逻辑运算符](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators)部分。|
|[&#91;&#93;](member-access-operators.md#indexer-operator-)|元素访问不被视为可重载运算符，但你可定义[索引器](../../programming-guide/indexers/index.md)。|
|[(T)x](type-testing-and-conversion-operators.md#cast-operator-)|强制转换运算符无法进行重载，但是可以定义新转换运算符（请参阅 [explicit](../keywords/explicit.md) 和 [implicit](../keywords/implicit.md)）。|
|[+=](arithmetic-operators.md#compound-assignment), [-=](arithmetic-operators.md#compound-assignment), [\*=](arithmetic-operators.md#compound-assignment), [/=](arithmetic-operators.md#compound-assignment), [%=](arithmetic-operators.md#compound-assignment), [&=](boolean-logical-operators.md#compound-assignment), [&#124;=](boolean-logical-operators.md#compound-assignment), [^=](boolean-logical-operators.md#compound-assignment), [\<\<=](bitwise-and-shift-operators.md#compound-assignment), [>>=](bitwise-and-shift-operators.md#compound-assignment)|复合赋值运算符不能显式重载。 但在重载二元运算符时，也会隐式重载相应的复合赋值运算符（若有）。 例如，使用 `+`（可以进行重载）计算 `+=`。|
|[=](assignment-operator.md)、[.](member-access-operators.md#member-access-operator-)、[?:](conditional-operator.md)、[??](null-coalescing-operator.md)、[->](pointer-related-operators.md#pointer-member-access-operator--)、[=>](lambda-operator.md)、[f(x)](member-access-operators.md#invocation-operator-)、[as](type-testing-and-conversion-operators.md#as-operator)、[checked](../keywords/checked.md)、[unchecked](../keywords/unchecked.md)、[default](../../programming-guide/statements-expressions-operators/default-value-expressions.md)、[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md)、[is](type-testing-and-conversion-operators.md#is-operator)、[nameof](../keywords/nameof.md)、[new](new-operator.md)、[sizeof](../keywords/sizeof.md)、[typeof](type-testing-and-conversion-operators.md#typeof-operator)|这些运算符无法进行重载。|

> [!NOTE]
> 比较运算符必须成对重载。 也就是说，如果重载一对运算符中的任一一个，则另一个运算符也必须重载。 此类配对如下所示：
>
> - `==` 和 `!=` 运算符
> - `<` 和 `>` 运算符
> - `<=` 和 `>=` 运算符

## <a name="c-language-specification"></a>C# 语言规范

有关更多信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的以下部分：

- [运算符重载](~/_csharplang/spec/expressions.md#operator-overloading)
- [运算符](~/_csharplang/spec/classes.md#operators)

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 运算符](index.md)
- [重载运算符为何在 C# 中始终是静态的？](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/)
