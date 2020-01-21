---
title: default 运算符 - C# 参考
description: 使用 default 运算符生成类型的默认值
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 651c4698514aee8cf4dab75ea32c98493e19a30b
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964623"
---
# <a name="default-operator-c-reference"></a>default 运算符（C# 参考）

`default` 运算符生成类型的[默认值](../builtin-types/default-values.md)。 `default` 运算符的实参必须是类型或类型形参的名称。

下面的示例演示 `default` 运算符的用法：

[!code-csharp-interactive[default of T](~/samples/csharp/language-reference/operators/DefaultOperator.cs#WithOperand)]

你还可以将 `default` 关键字用作 [`switch` 语句](../keywords/switch.md)中的默认用例标签。

## <a name="default-literal"></a>default 文本

从 C# 7.1 开始，当编译器可以推断表达式类型时，可以使用 `default` 文本生成类型的默认值。 `default` 文本表达式生成与 `default(T)` 表达式（其中，`T` 是推断的类型）相同的值。 可以在以下任一情况下使用 `default` 文本：

- 对变量进行赋值或初始化时。
- 在声明[可选方法参数](../../methods.md#optional-parameters-and-arguments)的默认值时。
- 在方法调用中提供参数值时。
- 在 [`return` 语句](../keywords/return.md)中或作为[表达式主体成员](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)中的表达式时。

下面的示例演示 `default` 文本的用法：

[!code-csharp-interactive[default literal](~/samples/csharp/language-reference/operators/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的 [默认值表达式](~/_csharplang/spec/expressions.md#default-value-expressions)部分。

有关 `default` 文本的详细信息，请参阅[功能建议说明](~/_csharplang/proposals/csharp-7.1/target-typed-default.md)。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 运算符](index.md)
- [C# 类型的默认值](../builtin-types/default-values.md)
- [.NET 中的泛型](../../../standard/generics/index.md)
