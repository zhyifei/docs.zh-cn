---
title: =&gt; 运算符 - C# 参考
ms.custom: seodec18
ms.date: 10/02/2017
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 8641757d9252c88cf30595cec06d27b964e4d95c
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415281"
---
# <a name="gt-operator-c-reference"></a>=&gt; 运算符（C# 参考）

在 C# 中，`=>` 运算符有两种用法：

- 作为 [Lambda 表达式](../../lambda-expressions.md)中的 [lambda 运算符](#lambda-operator)，它可将输入变量从 lambda 体中隔离出来。
 
- 在[表达式主体定义](#expression-body-definition)中，它可将成员名称从成员实现中隔离出来。 

## <a name="lambda-operator"></a>lambda 运算符

`=>` 标记称作 lambda 运算符。 该标记在 Lambda 表达式中用来将左侧的输入变量与右侧的 lambda 体分离。 Lambda 表达式是类似于匿名方法的内联表达式，但更加灵活；在以方法语法表示的 LINQ 查询中广泛使用了 Lambda 表达式。 有关详细信息，请参阅 [Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)。  
  
 以下示例演示了 2 种在字符串数组中查找并显示最短字符串长度的方法。 本示例的第一部分将 Lambda 表达式 (`w => w.Length`) 应用于 `words` 数组的每个元素中，然后使用 <xref:System.Linq.Enumerable.Min%2A> 方法查找最小长度。 为了进行比较，本示例的第二部分演示了使用查询语法执行相同操作的较长解决方案。  
  
```csharp  
string[] words = { "cherry", "apple", "blueberry" };  
  
// Use method syntax to apply a lambda expression to each element  
// of the words array.   
int shortestWordLength = words.Min(w => w.Length);  
Console.WriteLine(shortestWordLength);  
  
// Compare the following code that uses query syntax.  
// Get the lengths of each word in the words array.  
var query = from w in words  
            select w.Length;  
// Apply the Min method to execute the query and get the shortest length.  
int shortestWordLength2 = query.Min();  
Console.WriteLine(shortestWordLength2);  
  
// Output:   
// 5  
// 5  
```  
  
### <a name="remarks"></a>备注  
 `=>` 运算符具有与赋值运算符 (`=`) 相同的优先级，并且是右结合运算符。  
  
 可以显式指定输入变量的类型或让编译器推断类型；无论何种情况，该变量在编译时均为强类型。 指定类型时，必须用括号括住类型名称和变量名称，如下例所示。  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
### <a name="example"></a>示例  
 以下示例演示如何为使用 2 个参数的标准查询运算符 <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> 的重载编写一个 Lambda 表达式。 由于 Lambda 表达式具有多个参数，因此参数必须括在括号中。 第 2 个参数 `index` 表示集合中当前元素的索引。 `Where` 表达式返回长度小于其数组中索引位置的所有字符串。  
  
```csharp  
static void Main(string[] args)  
{  
    string[] digits = { "zero", "one", "two", "three", "four", "five",   
            "six", "seven", "eight", "nine" };  
  
    Console.WriteLine("Example that uses a lambda expression:");  
    var shortDigits = digits.Where((digit, index) => digit.Length < index);  
    foreach (var sD in shortDigits)  
    {  
        Console.WriteLine(sD);  
    }  
  
    // Output:  
    // Example that uses a lambda expression:  
    // five  
    // six  
    // seven  
    // eight  
    // nine  
}  
```  
## <a name="expression-body-definition"></a>表达式主体定义

表达式主体定义可采用非常简洁的可读形式提供成员的实现。 它具有以下常规语法：

```csharp
member => expression;
```
其中“expression”是有效的表达式。 请注意，仅当成员的返回类型是 `void` 时，或者成员是构造函数或终结器时，表达式才可能是语句表达式。

自 C# 6 起支持方法和属性 Get 语句的表达式主体定义。 自 C# 7 起支持构造函数、终结器、属性 Set 语句和索引器的表达式主体定义。

以下是用于 `Person.ToString` 方法的表达式主体定义：

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
有关表达式主体定义的详细信息，请参阅 [Expression-Bodied 成员](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)。

## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)   
- [C# 编程指南](../../../csharp/programming-guide/index.md)   
- [Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
- [Expression-bodied 成员](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).
