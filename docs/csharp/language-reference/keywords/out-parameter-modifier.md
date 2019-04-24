---
title: out 参数修饰符 - C# 参考
ms.custom: seodec18
ms.date: 03/26/2019
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: 769d1ac0b6266c87e99605c76a25e016f15eb11c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125737"
---
# <a name="out-parameter-modifier-c-reference"></a>out 参数修饰符（C# 参考）
`out` 关键字通过引用传递参数。 它让形参成为实参的别名，这必须是变量。 换而言之，对形参执行的任何操作都是对实参执行的。 它与 [ref](ref.md) 关键字相似，只不过 `ref` 要求在传递之前初始化变量。 它也类似于 [in](in-parameter-modifier.md) 关键字，只不过 `in` 不允许通过调用方法来修改参数值。 若要使用 `out` 参数，方法定义和调用方法均必须显式使用 `out` 关键字。 例如:  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE] 
> `out` 关键字也可与泛型类型参数结合使用，以指定该类型参数是协变参数。 有关在此上下文中使用 `out` 关键字的详细信息，请参阅 [out（泛型修饰符）](out-generic-modifier.md)。
  
作为 `out` 参数传递的变量在方法调用中传递之前不必进行初始化。 但是，被调用的方法需要在返回之前赋一个值。  
  
`in`、`ref` 和 `out` 关键字不被视为用于重载决议的方法签名的一部分。 因此，如果唯一的不同是一个方法采用 `ref` 或 `in` 参数，而另一个方法采用 `out` 参数，则无法重载这两个方法。 例如，以下代码将不会编译：  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
但是，如果一个方法采用 `ref`、`in` 或 `out` 参数，而另一个方法采用其他参数，则可以完成重载，如：  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

编译器通过将调用站点上的参数修饰符与方法调用中使用的参数修饰符进行匹配，从而选择最佳重载。
 
属性不是变量，因此不能作为 `out` 参数传递。
  
不能将 `in`、`ref` 和 `out` 关键字用于以下几种方法：  
  
-   异步方法，通过使用 [async](../../../csharp/language-reference/keywords/async.md) 修饰符定义。  
  
-   迭代器方法，包括 [yield return](../../../csharp/language-reference/keywords/yield.md) 或 `yield break` 语句。  

## <a name="declaring-out-parameters"></a>声明 `out` 参数   

使用 `out` 参数声明方法是返回多个值的经典解决方法。 自 C# 7.0 起，建议在类似方案中使用[元组](../../tuples.md)。 下面的示例使用 `out` 返回具有单个方法调用的三个变量。 注意，第三个参数赋 null 值。 这使得方法可以有选择地返回值。  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

## <a name="calling-a-method-with-an-out-argument"></a>调用具有 `out` 参数的方法

在 C# 6 及更早版本中，必须先在单独的语句中声明变量，然后才能将其作为 `out` 参数传递。 下面的示例先声明了变量 `number`，然后再将它传递给将字符串转换为数字的 [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) 方法。

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

从 C# 7.0 开始，可以在方法调用的参数列表而不是单独的变量声明中声明 `out` 变量。 这使得代码更简洁可读，还能防止在方法调用之前无意中向该变量赋值。 下面的示例与上一个示例基本相同，不同之处在于它在对 [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) 方法的调用中定义了 `number` 变量。

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  
   
在上一个示例中，`number` 变量被强类型化为 `int`。 你也可以声明一个隐式类型本地变量，如以下示例所示。

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  
   
## <a name="c-language-specification"></a>C# 语言规范  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)
- [C# 编程指南](../../../csharp/programming-guide/index.md)
- [C# 关键字](../../../csharp/language-reference/keywords/index.md)
- [方法参数](../../../csharp/language-reference/keywords/method-parameters.md)
