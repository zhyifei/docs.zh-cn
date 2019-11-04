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
ms.openlocfilehash: 30419200cfce785d7fcbbf59650241580a1f0ce4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454958"
---
# <a name="readonly-c-reference"></a>readonly（C# 参考）

`readonly` 关键字是一个可在四个上下文中使用的修饰符：

- 在[字段声明](#readonly-field-example)中，`readonly` 指示只能在声明期间或在同一个类的构造函数中向字段赋值。 可以在字段声明和构造函数中多次分配和重新分配只读字段。 
  
  构造函数退出后，不能分配 `readonly` 字段。 此规则对于值类型和引用类型具有不同的含义：
  
  - 由于值类型直接包含数据，因此属于 `readonly` 值类型的字段不可变。 
  - 由于引用类型包含对其数据的引用，因此属于 `readonly` 引用类型的字段必须始终引用同一对象。 该对象是可变的。 `readonly` 修饰符可防止字段替换为引用类型的其他实例。 但是，修饰符不会阻止通过只读字段修改字段的实例数据。

  > [!WARNING]
  > 包含属于可变引用类型的外部可见只读字段的外部可见类型可能存在安全漏洞，可能会触发警告 [CA2104](/visualstudio/code-quality/ca2104)：“不要声明只读可变引用类型。”

- 在 [`readonly struct` 定义](#readonly-struct-example)中，`readonly` 指示 `struct` 是不可变的。
- 在 [`readonly` 成员定义](#readonly-member-examples)中，`readonly` 表示 `struct` 的成员不会改变结构的内部状态。
- 在 [`ref readonly` 方法返回](#ref-readonly-return-example)中，`readonly` 修饰符指示该方法返回一个引用，且不允许向该引用写入内容。

在 C# 7.2 中添加了 `readonly struct` 和 `ref readonly` 上下文。 在 C# 8.0 中添加了 `readonly` 结构成员

## <a name="readonly-field-example"></a>Readonly 字段示例

在此示例中，即使在类构造函数中给字段 `year` 赋了值，也无法在方法 `ChangeYear` 中更改其值：

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

你将收到编译器错误消息：

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

## <a name="readonly-member-examples"></a>Readonly 成员示例

其他情况下，你可以创建支持可变的结构。 在这些情况下，多个实例成员可能不会修改结构的内部状态。 可以使用 `readonly` 修饰符声明那些实例成员。 编译器会强制执行你的意图。 如果该成员直接修改状态或访问未使用 `readonly` 修饰符声明的成员，则结果为编译时错误。 `readonly` 修饰符对 `struct` 成员有效，而对 `class` 或 `interface` 成员声明无效。

通过将 `readonly` 修饰符应用于适用的 `struct` 方法，可以获得两个好处。 最重要的是，编译器会强制执行你的意图。 修改状态的代码在 `readonly` 方法中无效。 编译器还可以使用 `readonly` 修饰符来实现性能优化。 大型 `struct` 类型由 `in` 引用传递时，如果该结构的状态可以进行修改，则编译器必须生成一个防御性副本。 如果仅访问 `readonly` 成员，则编译器可能不会创建防御性副本。

`readonly` 修饰符对 `struct` 的大多数成员有效，包括重写在 <xref:System.Object?displayProperty=nameWithType> 中声明的方法的方法。 但存在一些限制：

- 无法声明 `readonly` 静态成员。
- 无法声明 `readonly` 构造函数。

可将 `readonly` 修饰符添加到属性或索引器声明中：

```csharp
readonly public int Counter
{
  get { return 0; }
  set {} // not useful, but legal
}
```

还可将 `readonly` 修饰符添加到属性或索引器的单个 `get` 或 `set` 访问器中：

```csharp
public int Counter
{
  readonly get { return _counter; }
  set { _counter = value; }
}
int _counter;
```

不能同时将 `readonly` 修饰符添加到一个属性以及同一属性的一个或多个访问器中。 同样的限制也适用于索引器。

编译器隐式地将 `readonly` 修饰符应用于自动实现的属性，在这些属性中，编译器实现的代码不修改状态。 它等效于以下声明：

```csharp
public readonly int Index { get; }
// Or:
public int Number { readonly get; }
public string Message { readonly get; set; }
``` 

可以在这些位置添加 `readonly` 修饰符，但不会产生任何有意义的效果。 不能将 `readonly` 修饰符添加到自动实现的属性资源库或读/写自动实现的属性中。

## <a name="ref-readonly-return-example"></a>Ref readonly 返回示例

`ref return` 上的 `readonly` 修饰符指示返回的引用无法修改。 下面的示例返回了一个对来源的引用。 它使用 `readonly` 修饰符来指示调用方无法修改来源：

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
所返回的类型不需要为 `readonly struct`。 `ref` 能返回的任何类型都能由 `ref readonly` 返回。

## <a name="c-language-specification"></a>C# 语言规范

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

你还可查看语言规范建议：

- [readonly ref 和 readonly 结构](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [readonly 结构成员](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 关键字](index.md)
- [修饰符](index.md)
- [const](const.md)
- [字段](../../programming-guide/classes-and-structs/fields.md)
