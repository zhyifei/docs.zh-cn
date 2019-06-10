---
title: 运算符 - C# 编程指南
ms.custom: seodec18
ms.date: 04/30/2019
helpviewer_keywords:
- operators [C#]
- C# language, operators
- operators [C#], about operators
ms.assetid: 214e7b83-1a41-4f7c-9867-64e9c0bab39f
ms.openlocfilehash: 60e7f7c25b525c6db856731bd16c1c0e60efe6d6
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422924"
---
# <a name="operators-c-programming-guide"></a>运算符（C# 编程指南）

在 C# 中，运算符  是应用于表达式或语句中的一个或多个操作数  的程序元素。 接受一个操作数的运算符称为`++`一元 `new`运算符，例如递增运算符 ( *) 或* 。 接受两个操作数的运算符称为`+`二元`-`运算符，例如算术运算符（`*`、`/`、 *、* ）。 条件运算符`?:`接受三个操作数，是 C# 中唯一的三元运算符。  
  
 下面的 C# 语句包含一个一元运算符和一个操作数。 递增运算符 `++`修改操作数 `y`的值。  
  
 [!code-csharp[csProgGuideStatements#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#5)]  
  
 下面的 C# 语句包含两个二元运算符，它们分别有两个操作数。 赋值运算符 `=` 将一个整数变量 `y` 和一个表达式 `2 + 3` 作为操作数。 表达式 `2 + 3` 本身由加法运算符和两个操作数 `2` 和 `3` 组成。  
  
 [!code-csharp[csProgGuideStatements#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#6)]  
  
操作数可以是由任何长度的代码组成的有效表达式，且可包含任意数量的子表达式。 在包含多个运算符的表达式中，运算符的应用顺序由运算符优先级  、关联性  和括号确定。  

## <a name="operator-precedence"></a>运算符优先级
  
每个运算符都具有已定义的优先级。 在包含具有不同优先级级别的多个运算符的表达式中，运算符的优先级确定运算符的计算顺序。 例如，下列语句将 3 赋给 `n1`：

```csharp
n1 = 11 - 2 * 4;
```

因为乘法的优先级高于减法，所以首先执行乘法。

要了解按优先级排序的完整 C# 运算符列表，请参阅 [C# 运算符](../../language-reference/operators/index.md)。
  
## <a name="associativity"></a>结合性

 当表达式中出现两个或两个以上具有相同优先级的运算符时，将根据结合性计算它们。 左结合运算符按从左到右的顺序计算。 例如，`x * y / z` 将计算为 `(x * y) / z`。 右结合运算符按从右到左的顺序计算。 例如，赋值运算符是右关联的。 如果不是，下面的代码将导致错误。  
  
```csharp  
int a, b, c;  
c = 1;  
// The following two lines are equivalent.  
a = b = c;  
a = (b = c);  
  
// The following line, which forces left associativity, causes an error.  
//(a = b) = c;  
```  
  
 再举一个例子，三元运算符 ([?:](../../../csharp/language-reference/operators/conditional-operator.md)) 是右结合运算符。 大多数的二元运算符是左结合运算符。  
  
 无论表达式中的运算符是左结合运算符还是右结合运算符，都将先从左至右评估各表达式的操作数。 以下示例显示运算符和操作数的计算顺序。  
  
|语句|计算顺序|  
|---------------|-------------------------|  
|`a = b`|a、b、=|  
|`a = b + c`|a、b、c、+、=|  
|`a = b + c * d`|a、b、c、d、*、+、=|  
|`a = b * c + d`|a、b、c、*、d、+、=|  
|`a = b - c + d`|a、b、c、-、d、+、=|  
|`a += b -= c`|a、b、c、-=、+=|  
  
## <a name="adding-parentheses"></a>添加括号

 可通过使用圆括号更改运算符优先级和相关性。 例如，`2 + 3 * 2` 通常计算结果为 8，因为乘法运算符的优先级高于加法运算符。 但是，如果你将表达式编写为 `(2 + 3) * 2`，则先计算加法，再计算乘法，且结果为 10。 以下示例显示括号表达式中的计算顺序。 如前面的示例中所示，计算操作数之前会应用运算符。  
  
|语句|计算顺序|  
|---------------|-------------------------|  
|`a = (b + c) * d`|a、b、c、+、d、*、=|  
|`a = b - (c + d)`|a、b、c、d、+、-、=|  
|`a = (b + c) * (d - e)`|a、b、c、+、d、e、-、*、=|  
  
## <a name="operator-overloading"></a>运算符重载

可以为自定义类和结构定义特定运算符的行为。 此过程称为“运算符重载”  。 有关详细信息，请参阅[可重载运算符](overloadable-operators.md)和[运算符](../../language-reference/keywords/operator.md)关键字文章。
  
## <a name="see-also"></a>请参阅

- [C# 编程指南](../index.md)
- [语句、表达式和运算符](index.md)
- [C# 运算符](../../language-reference/operators/index.md)
