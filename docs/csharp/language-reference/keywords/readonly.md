---
title: readonly（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: d2f8a2f192dc319ad806aeef4bfbaeecc44b07a3
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172628"
---
# <a name="readonly-c-reference"></a>readonly（C# 参考）
`readonly` 关键字是一个可在字段上使用的修饰符。 当字段声明包括 `readonly` 修饰符时，该声明引入的字段赋值只能作为声明的一部分出现，或者出现在同一类的构造函数中。  
  
## <a name="readonly-field-example"></a>Readonly 字段示例  
 在此示例中，即使在类构造函数中给字段 `year` 赋了值，它的值仍无法在 `ChangeYear` 方法中更改：  
  
 [!code-csharp[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 只能在下列上下文中对 `readonly` 字段进行赋值：  
  
-   在声明中初始化变量时，例如：  
  
    ```csharp  
    public readonly int y = 5;  
    ```  
  
-   对于实例字段，在包含字段声明的类的实例构造函数中；或者，对于静态字段，在包含字段声明的类的静态构造函数中。 也只有在这些上下文中，将 `readonly` 字段作为 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 或 [ref](../../../csharp/language-reference/keywords/ref.md) 参数传递才有效。  
  
> [!NOTE]
>  `readonly` 关键字不同于 [const](../../../csharp/language-reference/keywords/const.md) 关键字。 `const` 字段只能在该字段的声明中初始化。 
          
          
          `readonly` 字段可以在声明或构造函数中初始化。 因此，根据所使用的构造函数，`readonly` 字段可能具有不同的值。 另外，虽然 `const` 字段是编译时常量，但 `readonly` 字段可用于运行时常量，如下面的示例所示：   
  
```csharp  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="comparing-readonly-and-non-readonly-instance-fields"></a>比较 readonly 和非 readonly 实例字段  
 [!code-csharp[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
 在前面的示例中，如果使用如下的语句：  
  
 `p2.y = 66;        // Error`  
  
 将收到编译器错误消息：  
  
 `The left-hand side of an assignment must be an l-value`  
  
 这与尝试给常数赋值时收到的错误相同。  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [修饰符](../../../csharp/language-reference/keywords/modifiers.md)  
 [const](../../../csharp/language-reference/keywords/const.md)  
 [字段](../../../csharp/programming-guide/classes-and-structs/fields.md)
