---
title: '?: 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 3e45ff6eaaefa5829c3ed9415abe1a12b7a1d069
ms.sourcegitcommit: 4bca8f7e172fd019ef437a4803bf5895c6bc4781
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "50980617"
---
# <a name="-operator-c-reference"></a>?: 运算符（C# 参考）

条件运算符 (`?:`) 通常被称为三元条件运算符，根据 Boolean 表达式的值返回两个值之一。 下面是条件运算符的语法。  

```csharp
condition ? first_expression : second_expression;  
```

自 C# 7.2 起，`first_expression` 和 `second_expression` 可以是 [`ref` 表达式](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md)：

```csharp
ref condition ? ref first_expression : ref second_expression;  
```

可将结果赋给 `ref` 或 `ref readonly` 变量，也可以赋给不带任一修饰符的变量。

## <a name="remarks"></a>备注

`condition` 的计算结果必须为 `true` 或 `false`。 如果 `condition` 为 `true`，则将计算 `first_expression` 并使其成为结果。 如果 `condition` 为 `false`，则将计算 `second_expression` 并使其成为结果。 只计算两个表达式之一。 这对于结果为 `ref` 的表达式特别重要，因为以下内容有效：

```csharp
ref (storage != null) ? ref storage[3] : ref defaultValue;
```

`storage` 为空时，不会计算对 `storage` 的引用。

若结果为值，`first_expression` 和 `second_expression` 的类型必须相同，或者必须存在从一种类型到另一种类型的隐式转换。 若结果为 `ref`，`first_expression` 和 `second_expression` 的类型必须相同。

你可通过使用条件运算符表达可能更确切地要求 `if-else` 构造的计算。 例如，以下代码首先使用 `if` 语句，然后使用条件运算符将整数分类为正整数或负整数。

```csharp
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```

条件运算符为右联运算符。 表达式 `a ? b : c ? d : e` 作为 `a ? b : (c ? d : e)` 而非 `(a ? b : c) ? d : e` 进行计算。  
  
无法重载条件运算符。
  
## <a name="example"></a>示例

以下示例显示结果为值的条件运算符：

[!code-csharp[csRefOperators?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

以下备选示例显示结果为 ref 的条件运算符：

[!code-csharp[csRefOperatorsRef?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 运算符](../../../csharp/language-reference/operators/index.md)  
- [if-else](../../../csharp/language-reference/keywords/if-else.md)  
- [?. 和 ?[] 运算符](../../../csharp/language-reference/operators/null-conditional-operators.md)  
- [??运算符](../../../csharp/language-reference/operators/null-coalescing-operator.md)
