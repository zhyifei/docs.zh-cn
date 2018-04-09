---
title: 具有值类型的引用语义
description: 了解安全地最大程度减少结构复制操作的语言功能
author: billwagner
ms.author: wiwagn
ms.date: 11/10/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 778897dc92f8a94178ebbbed7704c0dfe2397729
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="reference-semantics-with-value-types"></a>具有值类型的引用语义

使用值类型的优点之一是通常可避免堆分配。
缺点是它们按值进行复制。 由于存在这种折衷，因此难以优化针对大量数据执行的算法。 C# 7.2 中新增的语言功能可提供支持按具有值类型的引用语义传递的机制。 请恰当地使用这些功能，以最大程度地减少分配和复制操作。 本文将介绍这些新功能。

文本中的很多示例代码演示了 C# 7.2 中增加的功能。 若要使用这些功能，必须将项目配置为使用 C# 7.2 或更高版本。 可以使用 Visual Studio 进行选择。 对于每个项目，从菜单中选择“项目”，然后选择“属性”。 选择“生成”选项卡，然后单击“高级”。 在此处配置语言版本。 选择“7.2”或“最新”。  或者，可以编辑 csproj 文件，并添加以下节点：

```XML
  <PropertyGroup>
    <LangVersion>7.2</LangVersion>
  </PropertyGroup>
```

可以将“7.2”或“最新”用作值。

## <a name="passing-arguments-by-readonly-reference"></a>按只读引用传递参数

C# 7.2 新增 `in` 关键字来补充现有的 `ref` 和 `out` 关键字以按引用传递参数。 `in` 关键字指定按引用传递参数，但调用的方法不修改值。 

这一新增功能可提供完整的词汇，以表达你的设计意图。 如果未在方法签名中指定以下任一修饰符，值类型会在传递给调用的方法时进行复制。 每个修饰符指定值类型按引用传递，避免复制。 每个修饰符表达一种不同的意图：

- `out`：此方法设置用作此形参的实参的值。
- `ref`：此方法可设置用作此形参的实参的值。
- `in`：此方法不会修改用作此形参的实参的值。

添加 `in` 修饰符，按引用传递参数，并声明设计意图是为了按引用传递参数，避免不必要的复制操作。 你不打算修改用作该参数的对象。 下面的代码演示了一个方法示例，该方法用于计算三维空间中两点间的距离。 

[!code-csharp[InArgument](../../samples/csharp/reference-semantics/Program.cs#InArgument "Specifying an In argument")]

该参数具有两个结构，每个结构包含三个双精度值。 一个双精度值有 8 个字节，所以每个参数有 24 个字节。 通过指定 `in` 修饰符，可向这些参数传递 4 字节或 8 字节引用，具体取决于计算机的体系结构。 大小的差异很小，但是当应用程序使用许多不同的值在一个紧凑的循环中调用此方法时，这些差异可迅速累积。
 
`in` 修饰符还可以通过其他方式补充 `out` 和 `ref`。 无法创建差异仅为是否具有 `in`、`out` 或 `ref` 的方法的重载。 这些新规则可扩展始终为 `out` 和 `ref` 参数定义的相同行为。

`in` 修饰符可能适用于采用以下参数的任何成员：methods、delegates、lambdas、local functions、indexers 和 operators。

与 `ref` 和 `out` 实参不同，可对 `in` 形参的实参使用文本值或常数。 此外，与 `ref` 或 `out` 参数不同，无需在调用站点应用 `in` 修饰符。 下面的代码演示调用 `CalculateDistance` 方法的两个示例。 第一个示例使用按引用传递的两个本地变量。 第二个示例包含方法调用过程中创建的临时变量。 

[!code-csharp[UseInArgument](../../samples/csharp/reference-semantics/Program.cs#UseInArgument "Specifying an In argument")]

有多种方法可让编译器确保强制执行 `in` 参数的只读性质。  首先，调用的方法不能直接分配给 `in` 参数。 当值类型为 `struct` 时，不能直接分配给 `in` 参数的任何字段。 此外，不能向使用 `ref` 或 `out` 修饰符的任何方法传递 `in` 参数。
如果字段为 `struct` 类型且该参数也为 `struct` 类型，则这些规则适用于 `in` 参数的任何字段。 事实上，如果所有级别的成员访问类型都是 `structs`，则这些规则适用于多层成员访问。 编译器强制将 `struct` 类型作为 `in` 参数传递，它们的 `struct` 成员用作其他方法的参数时，为只读变量。

使用 `in` 参数可避免产生复制操作可能产生的性能成本。 这不会改变任何方法调用的语义。 所以不需要在调用站点指定 `in` 修饰符。 但在调用站点省略 `in` 修饰符就会通知编译器你允许它出于以下原因复制参数：

- 存在从实参类型到形参类型的隐式转换，但不是标识转换。
- 该参数是一个表达式，但是没有已知的存储变量。
- 存在的重载因 `in` 是否存在而有所不同。 在这种情况下，按值重载的匹配度会更高。

在更新现有代码以使用只读引用参数时，这些规则会很有用。 在调用的方法中，可以调用任何使用按值参数的实例方法。 在这些方法中，将创建 `in` 参数的副本。 由于编译器可为任何 `in` 参数创建临时变量，因此还可指定任何 `in` 参数的默认值。 以下代码指定原点（点 0,0）为第二个点的默认值：

[!code-csharp[InArgumentDefault](../../samples/csharp/reference-semantics/Program.cs#InArgumentDefault "Specifying defaults for an in parameter")]

要强制编译器按引用传递只读参数，请在调用站点的参数上指定 `in` 修饰符，如下列代码所示：

[!code-csharp[UseInArgument](../../samples/csharp/reference-semantics/Program.cs#ExplicitInArgument "Specifying an In argument")]

这样可以更轻松地在大型代码库中采用一段时间的 `in` 参数，从而实现性能提升。 首先，将 `in` 修饰符添加到方法签名。 然后，可以在调用站点添加 `in` 修饰符，并创建 `readonly struct` 类型，让编译器避免在更多位置创建 `in` 参数的防御性副本。

`in` 参数指定还可用于引用类型或数值。 但是，这两种情况下获得的好处都是最少的（如果有）。

## <a name="ref-readonly-returns"></a>`ref readonly` 返回

可能还需要按引用返回值类型，但不允许调用方修改该值。 使用 `ref readonly` 修饰符来表达该设计意图。 它将通知读者，即将返回对现有数据的引用，但不允许修改。 

编译器可强制调用方不能修改引用。 直接分配给该值的尝试会生成编译时错误。 但是，编译器无法得知某一成员方法是否修改该结构的状态。
若要确保未修改该对象，编译器将创建副本并使用该副本调用成员引用。 任何修改均针对该防御性副本。 

使用 `Point3D` 的库通常很可能在代码中使用原点。 每个实例将在堆栈上创建一个新对象。 最好创建一个常数并按引用返回它。 但是，如果返回对内部存储的引用，可能需要强制该调用方不能修改引用的存储。 以下代码定义只读属性，该属性向指定原点的 `Point3D` 返回 `readonly ref`。

[!code-csharp[OriginReference](../../samples/csharp/reference-semantics/Point3D.cs#OriginReference "Creating a readonly Origin reference")]

创建 ref readonly return 的副本很容易：只需将其分配给未使用 `ref readonly` 修饰符声明的变量即可。 编译器将生成代码，用于在分配过程中复制对象。 

当向 `ref readonly return` 分配变量时，可指定 `ref readonly` 变量或只读引用的按值副本：

[!code-csharp[AssignRefReadonly](../../samples/csharp/reference-semantics/Program.cs#AssignRefReadonly "Assigning a ref readonly")]

前面的代码中的第一个分配将创建 `Origin` 常数的副本，并分配该副本。 第二个将分配引用。 注意，`readonly` 修饰符必须包含在变量声明中。 无法修改该修饰符引用对象的引用。 尝试执行该操作将导致编译时错误。

## <a name="readonly-struct-type"></a>`readonly struct` 类型

向结构的高流量使用应用 `ref readonly` 可能已足够。
其他情况下，可能需要创建不可变的结构。 然后便可以按只读引用传递。 该做法将删除防御性副本，该副本创建于访问用作 `in` 参数的结构的方法时。

可通过创建 `readonly struct` 类型执行该操作。 可向结构声明添加 `readonly` 修饰符。 编译器可强制结构的所有实例成员为 `readonly`；`struct` 必须是不可变的。

存在针对 `readonly struct` 的其他优化。 可在 `readonly struct` 为参数的每个位置使用 `in` 修饰符。 此外，如果要返回其生存期超出返回对象的方法的作用域的对象，可返回 `readonly struct` 作为 `ref return`。

最后，调用 `readonly struct` 的成员时，编译器将生成更高效的代码：`this` 引用，而不是接收方的副本，是始终通过对成员方法的引用进行传递的 `in` 参数。 这种优化在你使用 `readonly struct` 时可减少更多复制操作。 `Point3D` 是这项更改的理想候选项。 下面的代码显示更新后的 `ReadonlyPoint3D` 结构：

[!code-csharp[ReadonlyOnlyPoint3D](../../samples/csharp/reference-semantics/Point3D.cs#ReadonlyOnlyPoint3D "Defining an immutable structure")]

## <a name="ref-struct-type"></a>`ref struct` 类型

另一相关语言功能是声明值类型必须为堆栈分配。 换言之，永远不能在作为另一类的成员的堆上创建这些类型。 此功能的主要动机是 <xref:System.Span%601> 和相关结构。 <xref:System.Span%601> 可能包含托管的指针，作为成员之一，而另一个作为范围的长度。 它的实现方式稍微有些不同，因为 C# 不支持指向不安全上下文之外的托管内存的指针。 更改指针和长度的任何写入都不是原子的。 这意味着如果 <xref:System.Span%601> 不限于单个堆栈帧，它将发生超出范围错误或其他类型安全冲突。 此外，将托管指针置于 GC 堆上通常会在 JIT 时出现故障。

在使用通过 [`stackalloc`](language-reference/keywords/stackalloc.md) 创建的内存或使用互操作 API 中的内存时，可能具有类似要求。 可针对这些需求定义自己的 `ref struct` 类型。 在本文中，请参阅使用 `Span<T>` 的简化示例。

`ref struct` 声明会声明此类型的结构必须位于堆栈上。 语言规则可确保安全使用这些类型。 声明为 `ref struct` 的其他类型包括 <xref:System.ReadOnlySpan%601>。 

保持 `ref struct` 类型作为堆栈分配的变量的目标引入了几条编译器针对所有 `ref struct` 类型强制执行的规则。

- 不能对 `ref struct` 装箱。 无法向属于 `object`、`dynamic` 或任何接口类型的变量分配 `ref struct` 类型。
- 不能将 `ref struct` 声明为类或常规结构的成员。
- 不能声明异步方法中属于 `ref struct` 类型的本地变量。 不能在返回 `Task`、`Task<T>` 或类似 Task 类型的同步方法中声明它们。
- 无法在迭代器中声明 `ref struct` 本地变量。
- 无法捕获 Lambda 表达式或本地函数中的 `ref struct` 变量。

这些限制可确保不会以可提升至托管堆的方式意外地使用 `ref struct`。

## <a name="readonly-ref-struct-type"></a>`readonly ref struct` 类型

将结构声明为 `readonly ref` 兼具 `ref struct` 和 `readonly struct` 声明的优点和限制。 

以下示例演示 `readonly ref struct` 的声明。

```csharp
readonly ref struct ReadOnlyRefPoint2D
{
    public int X { get; }
    public int Y { get; }
    
    public ReadOnlyRefPoint2D(int x, int y) => (X, Y) = (x, y);
}
```

## <a name="conclusions"></a>结论

C# 语言的这些增强功能专为性能关键型算法设计，在这些算法中，内存分配可能对实现必需的性能至关重要。 你可能会发现，编写代码时不经常使用这些功能。 但是，.NET Framework 中的许多位置已采用这些增强功能。 随着越来越多的 API 使用这些功能，你会发现应用程序的性能得到提升。
