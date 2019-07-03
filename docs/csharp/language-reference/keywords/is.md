---
title: is - C# 参考
ms.custom: seodec18
ms.date: 06/21/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: 45e37dcb15e178fe37907e00cc14ef48c1bf230d
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306594"
---
# <a name="is-c-reference"></a>is（C# 参考）

`is` 运算符检查表达式的结果是否与给定类型兼容，或（从 C# 7.0 开始）针对某个模式测试表达式。 有关类型测试 `is` 运算符的信息，请参阅文章[类型测试和转换运算符](../operators/type-testing-and-conversion-operators.md)的 [is 运算符](../operators/type-testing-and-conversion-operators.md#is-operator)部分。

## <a name="pattern-matching-with-is"></a>利用 `is` 的模式匹配

从 C# 7.0 开始，`is` 和 [switch](switch.md) 语句支持模式匹配。 `is` 关键字支持以下模式：

- [类型模式](#type-pattern)，用于测试表达式是否可转换为指定类型，如果可以，则将其转换为该类型的一个变量。

- [常量模式](#constant-pattern)，用于测试表达式计算结果是否为指定的常数值。

- [var 模式](#var-pattern)，始终成功的匹配，可将表达式的值绑定到新局部变量。

### <a name="type-pattern"></a>类型模式

使用类型模式执行模式匹配时，`is` 会测试表达式是否可转换为指定类型，如果可以，则将其转换为该类型的一个变量。 它是 `is` 语句的直接扩展，可执行简单的类型计算和转换。 `is` 类型模式的一般形式为：

```csharp
   expr is type varname
```

其中 *expr* 是计算结果为某个类型的实例的表达式，*type* 是 *expr* 结果要转换到的类型的名称，*varname* 是 *expr* 结果要转换到的对象（如果 `is` 测试为 `true`）。 

如果 expr  不为 `null` 且以下任意内容为 true，那么 `is` 表达式为 `true`：

- *expr* 是与 *type* 具有相同类型的一个实例。

- *expr* 是派生自 *type* 的类型的一个实例。 换言之，*expr* 结果可以向上转换为 *type* 的一个实例。

- *expr* 具有属于 *type* 的一个基类的编译时类型，*expr* 还具有属于 *type* 或派生自 *type* 的运行时类型。 变量的编译时类型  是其声明中定义的变量类型。 变量的运行时类型  是分配给该变量的实例类型。

- *expr* 是实现 *type* 接口的类型的一个实例。

自 C# 7.1 起，expr  可能有泛型类型参数及其约束定义的编译时类型。

如果 *expr* 为 `true` 且 `is` 与 `if` 语句配合使用，则仅在 `if` 语句内分配 *varname*。 *varname* 的使用范围：从 `is` 表达式到封闭 `if` 语句的块的末尾。 在任何其他位置使用 *varname* 都会因使用尚未分配的变量而生成编译时错误。

下列示例使用 `is` 类型模式为类型的 <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> 方法提供实现。

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

如果没有模式匹配，则可能按以下方式编写此代码。 使用类型模式匹配无需测试转换结果是否为 `null`，从而生成更紧凑易读的代码。  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

确定值类型的类型时，`is` 类型模式也会生成更紧凑的代码。 下例在显示相应属性的值之前使用 `is` 类型模式来确定对象是 `Person` 还是 `Dog` 实例。

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

对于无模式匹配的等效代码，需要为其单独分配显式转换。

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="constant-pattern"></a>常量模式

使用常量模式执行模式匹配时，`is` 会测试表达式结果是否等于指定常量。 在 C# 6 和更低版本中，[switch](switch.md) 语句支持常量模式。 自 C# 7.0 起，`is` 语句也支持它。 语法为：

```csharp
   expr is constant
```

其中 *expr* 是要计算的表达式，*constant* 是要测试的值。 *constant* 可以是以下任何常数表达式：

- 一个文本值。

- 已声明 `const` 变量的名称。

- 一个枚举常量。

常数表达式的计算方式如下：

- 如果 *expr* 和 *constant* 均为整型类型，则 C# 相等运算符确定表示式是否返回 `true`（即，是否为 `expr == constant`）。

- 否则，由对静态 [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) 方法的调用来确定表达式的值。  

下例同时使用了类型模式和常量模式来测试对象是否为 `Dice` 实例，如果是，则确定骰子的值是否为 6。

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

可以使用常量模式执行 `null` 检查。 `is` 语句支持 `null` 关键字。 语法为：

```csharp
   expr is null
```

下面的示例显示 `null` 检查的比较：

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]

### <a name="var-pattern"></a>var 模式

`var` 模式对于任何类型或值均为 catch-all。 expr  值始终分配给与 expr  的编译时类型相同的本地变量。 `is` 表达式的结果始终为 `true`。 语法为：

```csharp
   expr is var varname
```

下例使用 var 模式向名为 `obj` 的变量分配表达式。 然后，显示 `obj` 的值和类型。

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

## <a name="c-language-specification"></a>C# 语言规范
  
有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的 [is 运算符](~/_csharplang/spec/expressions.md#the-is-operator)部分以及下面的 C# 语言建议：

- [模式匹配](~/_csharplang/proposals/csharp-7.0/pattern-matching.md)
- [使用泛型的模式匹配](~/_csharplang/proposals/csharp-7.1/generics-pattern-match.md)
  
## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 关键字](index.md)
- [类型测试和转换运算符](../operators/type-testing-and-conversion-operators.md)
