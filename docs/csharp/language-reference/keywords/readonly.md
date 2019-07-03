---
title: readonly 关键字 - C# 参考
ms.custom: seodec18
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 4a51bb0e854de127c632c28f613a7602bf09f432
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348009"
---
# <a name="readonly-c-reference"></a>readonly（C# 参考）

`readonly` 关键字是一个可在三个上下文中使用的修饰符：

- 在[字段声明](#readonly-field-example)中，`readonly` 指示只能在声明期间或在同一个类的构造函数中向字段赋值。 可以在字段声明和构造函数中多次分配和重新分配只读字段。 
  
  构造函数退出后，不能分配 `readonly` 字段。 值类型和引用类型具有不同的含义：
  
  - 由于值类型直接包含数据，因此属于 `readonly` 值类型的字段不可变。 
  - 由于引用类型包含对其数据的引用，因此属于 `readonly` 引用类型的字段必须始终引用同一对象。 该对象不是不可变的。 `readonly` 修饰符可防止字段替换为引用类型的其他实例。 但是，修饰符不会阻止通过只读字段修改字段的实例数据。

  > [!WARNING]
  > 包含属于可变引用类型的外部可见只读字段的外部可见类型可能存在安全漏洞，可能会触发警告 [CA2104](/visualstudio/code-quality/ca2104-do-not-declare-read-only-mutable-reference-types)：“不要声明只读可变引用类型。”

- 在 [`readonly struct` 定义](#readonly-struct-example)中，`readonly` 指示 `struct` 是不可变的。
- 在 [`ref readonly` 方法返回](#ref-readonly-return-example)中，`readonly` 修饰符指示该方法返回一个引用，且不允许向该引用写入内容。

C# 7.2 中添加了最后两个上下文。

## <a name="readonly-field-example"></a>Readonly 字段示例

在此示例中，即使在类构造函数中给字段 `year` 赋了值，它的值仍无法在 `ChangeYear` 方法中更改：

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

只能在下列上下文中对 `readonly` 字段进行赋值：

- 在声明中初始化变量时，例如：

  ```csharp
  public readonly int y = 5;
  ```

- 在包含实例字段声明的类的实例构造函数中。
- 在包含静态字段声明的类的静态构造函数中。

只有在这些构造函数上下文中，将 `readonly` 字段作为 [out](out-parameter-modifier.md) 或 [ref](ref.md) 参数传递才有效。

> [!NOTE]
> `readonly` 关键字不同于 [const](const.md) 关键字。 `const` 字段只能在该字段的声明中初始化。 可以在字段声明和任何构造函数中多次分配 `readonly` 字段。 因此，根据所使用的构造函数，`readonly` 字段可能具有不同的值。 另外，虽然 `const` 字段是编译时常量，但 `readonly` 字段可用于运行时常量，如下面的示例所示：
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

在前面的示例中，如果使用类似以下示例的语句：

```csharp
p2.y = 66;        // Error
```

将收到编译器错误消息：

`A readonly field cannot be assigned to (except in a constructor or a variable initializer)`

## <a name="readonly-struct-example"></a>只读结构示例

`struct` 定义上的 `readonly` 修饰符声明该结构是不可变的  。 `struct` 的每个实例字段都必须被标记为 `readonly`，如下例所示：

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

前面的示例使用[只读自动属性](../../properties.md#read-only)来声明其存储。 该操作指示编译器为这些属性创建 `readonly` 支持字段。 还可以直接声明 `readonly` 字段：

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

添加未标记 `readonly` 的字段会生成编译器错误 `CS8340`：“只读结构的实例字段必须为只读。”

## <a name="ref-readonly-return-example"></a>Ref readonly 返回示例

`ref return` 上的 `readonly` 修饰符指示返回的引用无法修改。 下面的示例返回了一个对来源的引用。 它使用 `readonly` 修饰符来指示调用方无法修改来源：

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
所返回的类型不需要为 `readonly struct`。 `ref` 能返回的任何类型都能由 `ref readonly` 返回。

## <a name="c-language-specification"></a>C# 语言规范

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 关键字](index.md)
- [修饰符](modifiers.md)
- [const](const.md)
- [字段](../../programming-guide/classes-and-structs/fields.md)
