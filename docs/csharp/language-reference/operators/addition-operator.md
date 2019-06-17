---
title: + 和 += 运算符 - C# 参考
ms.custom: seodec18
ms.date: 05/24/2019
f1_keywords:
- +_CSharpKeyword
- +=_CSharpKeyword
helpviewer_keywords:
- addition operator [C#]
- concatenation operator [C#]
- delegate combination [C#]
- + operator [C#]
- addition assignment operator [C#]
- event subscription [C#]
- += operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: 14e62d53fca16212fae374b2627d1e96cbbca6ac
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025314"
---
# <a name="-and--operators-c-reference"></a>+ 和 += 运算符（C# 参考）

`+` 运算符受内置数字类型、[字符串](../keywords/string.md)类型和[委托](../keywords/delegate.md)类型的支持。

有关算术 `+` 运算符的信息，请参阅[一元加和减运算符](arithmetic-operators.md#unary-plus-and-minus-operators)和[算术运算符](arithmetic-operators.md)文章的[加法运算符 +](arithmetic-operators.md#addition-operator-) 部分。

## <a name="string-concatenation"></a>字符串串联

当其中的一个操作数是[字符串](../keywords/string.md)类型或两个操作数都是字符串类型时，`+` 运算符将其操作数的字符串表示形式串联在一起：

[!code-csharp-interactive[string concatenation](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddStrings)]

从 C# 6 开始，[字符串内插](../tokens/interpolated.md)提供了格式化字符串的更便捷方式：

[!code-csharp-interactive[string interpolation](~/samples/csharp/language-reference/operators/AdditionOperator.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a>委托组合

对于[委托](../keywords/delegate.md)类型相同的操作数，`+` 运算符在调用时返回新的委托实例，调用第一个操作数，然后调用第二个操作数。 如果任何操作数均为 `null`，则 `+` 运算符将返回另一个操作数（也可能是 `null`）的值。 下面的示例演示如何组合使用委托和 `+` 运算符：

[!code-csharp-interactive[delegate combination](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddDelegates)]

若要执行委托删除，请使用 [`-` 运算符](subtraction-operator.md#delegate-removal)。

有关委托类型的详细信息，请参阅[委托](../../programming-guide/delegates/index.md)。

## <a name="addition-assignment-operator-"></a>加法赋值运算符 +=

使用 `+=` 运算符的表达式，例如

```csharp
x += y
```

等效于

```csharp
x = x + y
```

不同的是 `x` 只计算一次。
  
下面的示例演示 `+=` 运算符的用法：

[!code-csharp-interactive[+= examples](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddAndAssign)]

在订阅[事件](../keywords/event.md)时，还可以使用 `+=` 运算符来指定事件处理程序方法。 有关详细信息，请参阅[如何：订阅和取消订阅事件](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)。

## <a name="operator-overloadability"></a>运算符可重载性

用户定义的类型可以[重载](../keywords/operator.md) `+` 运算符。 重载二元 `+` 运算符后，也会隐式重载 `+=` 运算符。 用户定义类型不能显式重载 `+=` 运算符。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅[C# 语言规范](~/_csharplang/spec/introduction.md)的[一元加运算符](~/_csharplang/spec/expressions.md#unary-plus-operator)和[加法运算符](~/_csharplang/spec/expressions.md#addition-operator)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 运算符](index.md)
- [字符串内插](../tokens/interpolated.md)
- [如何：连接多个字符串](../../how-to/concatenate-multiple-strings.md)
- [委托](../../programming-guide/delegates/index.md)
- [事件](../../programming-guide/events/index.md)
- [算术运算符](arithmetic-operators.md)
- [- 和 -= 运算符](subtraction-operator.md)
