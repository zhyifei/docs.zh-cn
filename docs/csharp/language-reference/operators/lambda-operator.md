---
title: =&gt; 运算符（C# 参考）
ms.date: 10/02/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 44cb0485aefa8b0ab10a00ae0525180020ce436d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="gt-operator-c-reference"></a>=&gt; 运算符（C# 参考）

`=>`运算符可在 C# 中的两种方式：

- 作为[lambda 运算符](#lamba-operator)中[lambda 表达式](../../lambda-expressions.md)，它将与 lambda 体分隔输入的变量。
 
- 在[表达式主体定义](#expression-body-definition)，它将成员名称与成员的实现分隔开。 

## <a name="lambda-operator"></a>Lambda 运算符

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

表达式主体定义提供高度压缩，可读的窗体中的成员的实现。 它具有以下常规语法：

```csharp
member => expression;
```
其中“expression”是有效的表达式。 请注意，*表达式*可以是*语句表达式*仅当成员的返回类型是`void`，或如果该成员是一个构造函数或终结器。

从 C# 6 支持的方法和属性 get 语句的表达式主体定义。 表达式主体定义构造函数，终结器，设置属性的语句，并且支持从 C# 7 开始的索引器。

以下是表达式主体定义`Person.ToString`方法：

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

它是以下方法定义的速记版：

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
有关更多详细信息表达式主体定义，请参阅[表达式正文成员](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)。

## <a name="see-also"></a>另请参阅  
[C# 参考](../../../csharp/language-reference/index.md)   
[C# 编程指南](../../../csharp/programming-guide/index.md)   
[Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
[表达式正文成员](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)。