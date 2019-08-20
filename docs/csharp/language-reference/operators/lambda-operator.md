---
title: => 运算符 - C# 参考
ms.custom: seodec18
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 3b3a5c2e96e92271da66cbd8f1039a9ec97544fa
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971221"
---
# <a name="-operator-c-reference"></a>=> 运算符（C# 参考）

`=>` 令牌支持两种形式：作为 lambda 运算符、作为成员名称的分隔符和表达式主体定义中的成员实现。

## <a name="lambda-operator"></a>lambda 运算符

在 [lambda 表达式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)中，lambda 运算符`=>`将左侧的输入变量与右侧的 lambda 主体分开。

以下示例使用带有方法语法的 [LINQ](../../programming-guide/concepts/linq/index.md) 功能来演示 lambda 表达式的用法：

[!code-csharp-interactive[infer types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#InferredTypes)]

lambda 表达式的输入变量在编译时是强类型。 当编译器可以推断输入变量的类型时，如前面的示例所示，可以省略类型声明。 如果需要指定输入变量的类型，则必须对每个变量执行此操作，如以下示例所示：

[!code-csharp-interactive[specify types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#ExplicitTypes)]

以下示例显示如何在没有输入变量的情况下定义 lambda 表达式：

[!code-csharp-interactive[without input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#WithoutInput)]

有关详细信息，请参阅 [Lambda 表达式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)。

## <a name="expression-body-definition"></a>表达式主体定义

表达式主体定义具有下列常规语法：

```csharp
member => expression;
```

其中 `expression` 是有效的表达式。 `expression` 的返回类型必须可隐式转换为成员的返回类型。 如果成员的返回类型是 `void`，或者如果成员是构造函数、终结器或属性 `set` 访问器，则 `expression` 必须是[语句表达式](~/_csharplang/spec/statements.md#expression-statements)；可以是任意类型  。

以下示例演示了用于 `Person.ToString` 方法的表达式主体定义：

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

它是以下方法定义的简写版：

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

自 C#6 起支持方法和只读属性的表达式主体定义。 自 C# 7.0 起支持构造函数、终结器、属性访问器和索引器的表达式主体定义。

有关详细信息，请参阅 [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)（Expression-bodied 成员）。

## <a name="operator-overloadability"></a>运算符可重载性

不能重载 `=>` 运算符。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的 [匿名函数表达式](~/_csharplang/spec/expressions.md#anonymous-function-expressions)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 运算符](index.md)
- [Lambda 表达式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)
- [Expression-Bodied 成员](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)
