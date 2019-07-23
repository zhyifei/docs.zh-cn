---
title: 委托运算符 - C# 参考
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 1fe281776bd75d8fa869065cd24e85f04fec849d
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331826"
---
# <a name="delegate-operator-c-reference"></a>委托运算符 -（C# 参考）

`delegate` 运算符创建一个可以转换为委托类型的匿名方法：

[!code-csharp-interactive[anonymous method](~/samples/csharp/language-reference/operators/DelegateOperator.cs#AnonymousMethod)]

从 C# 3 开始，[lambda表达式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)提供了一种更简洁和富有表现力的方式来创建匿名函数。 使用 [=> 运算符](lambda-operator.md)构造 lambda 表达式：

[!code-csharp-interactive[lambda expression](~/samples/csharp/language-reference/operators/DelegateOperator.cs#Lambda)]

使用 `delegate` 运算符时，可以省略参数列表。 如果这样做，可以将创建的匿名方法转换为具有任何参数列表的委托类型，如以下示例所示：

[!code-csharp-interactive[no parameter list](~/samples/csharp/language-reference/operators/DelegateOperator.cs#WithoutParameterList)]

这是 lambda 表达式不支持的匿名方法的唯一功能。 在所有其他情况下，lambda 表达式是编写内联代码的首选方法。 有关 lambda 表达式功能的更多信息（例如，如何捕获外部变量），请参阅 [lambda 表达式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)。

还可以使用 `delegate` 关键字声明[委托类型](../builtin-types/reference-types.md#the-delegate-type)。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的 [匿名函数表达式](~/_csharplang/spec/expressions.md#anonymous-function-expressions)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 运算符](index.md)
