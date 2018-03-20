---
title: "in 参数修饰符（C# 参考）"
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 035aac3e6b902f607e533b709713eb1d07c9774a
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="in-parameter-modifier-c-reference"></a>in 参数修饰符（C# 参考）

`in` 关键字通过引用传递参数。 它类似于 [ref](ref.md) 或 [out](out-parameter-modifier.md) 关键字，只是通过调用的方法不能修改 `in` 参数，而可以修改 `ref` 参数，同时 `out` 参数必须由调用方修改，并且在调用上下文中可观测这些修改。

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

前面的示例说明调用站点处不需要 `in` 修饰符。 仅在方法声明中需要它。

> [!NOTE] 
> `in` 关键字还作为 `foreach` 语句的一部分，或作为 LINQ 查询中 `join` 子句的一部分，与泛型类型参数一起使用来指定该类型参数为逆变。 有关在这些上下文使用 `in` 关键字的详细信息，请参阅 [in](in.md)，其中提供了所有这些用法的链接。
  
 作为 `in` 参数传递的变量在方法调用中传递之前必须进行初始化。 但是，所调用的方法可能不会分配值或修改参数。  
  
 尽管 `in`、`ref` 和 `out` 关键字会导致不同的运行时行为，它们并不被视为编译时方法签名的一部分。 因此，如果唯一的不同是一个方法采用 `ref` 或 `in` 参数，而另一个方法采用 `out` 参数，则无法重载这两个方法。 例如，以下代码将不会编译：  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
允许基于 `in` 的存在进行重载，但会生成编译器警告：  
  
```csharp
class InOverloads
{
    // Discouraged. Calling SampleMethod(value) is ambiguous.
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

属性或常量可能以 `in` 参数传递，因为调用的方法可能不会修改其值。
  
不能将 `in`、`ref` 和 `out` 关键字用于以下几种方法：  
  
- 异步方法，通过使用 [async](../../../csharp/language-reference/keywords/async.md) 修饰符定义。  
  
- 迭代器方法，包括 [yield return](../../../csharp/language-reference/keywords/yield.md) 或 `yield break` 语句。  

通常可声明 `in` 参数以避免按值传递参数所需的复制操作。 参数为结构或结构数组时，这非常有用。

## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [方法参数](../../../csharp/language-reference/keywords/method-parameters.md)
