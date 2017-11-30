---
title: "具有值类型的引用语义"
description: "了解最大程度减少复制结构安全地的语言功能"
author: billwagner
ms.author: wiwagn
ms.date: 11/10/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 9eeaf201c1f5a58044db62e356199b609c4c035a
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="reference-semantics-with-value-types"></a>具有值类型的引用语义

为使用值类型的一个优点是它们通常避免堆分配。
相应的缺点是通过值复制。 权衡导致难优化对大量数据进行操作的算法。 在 C# 7.2 的新语言功能提供支持与值类型的按引用传递语义的机制。 如果你使用这些功能可以最大程度减少两个分配和复制操作。 本文探讨这些新功能。

很多这篇文章中的示例代码演示了在 C# 7.2 中添加的功能。 若要使用这些功能，你必须配置您的项目以在你的项目中使用 C# 7.2 或更高版本。 可以使用 Visual Studio 以将其选中。 对于每个项目，选择**项目**的菜单，然后从**属性**。 选择**生成**选项卡，单击**高级**。 在这里，你可以配置的语言版本。 选择"7.2"最新"。  也可以在编辑*csproj*文件并添加以下节点：

```XML
  <PropertyGroup>
    <LangVersion>7.2</LangVersion>
  </PropertyGroup>
```

值，可以使用"7.2"最新"。

## <a name="specifying-in-parameters"></a>指定`in`参数

C# 7.2 添加`in`关键字来补充了现有`ref`和`out`关键字时编写的方法，通过引用传递的自变量。 `in`关键字指定您要通过引用传递参数，而调用的方法没有修改传递给它的值。 

此新增提供了完整的词汇来表示你的设计意图。 值类型时传递给调用的方法，如果不指定任何以下修饰符复制。 这些修饰符的每个指定的值类型按引用传递，避免副本。 每个修饰符表示不同的意图：

- `out`： 此方法设置为此参数中使用的参数的值。
- `ref`： 此方法可能会将设置为此参数中使用的参数的值。
- `in`： 此方法没有修改作为此参数中使用的参数的值。

当你将添加`in`修饰符来通过引用传递自变量声明你的设计意图是按引用以避免不必要复制传递自变量。 你不打算修改用作该自变量的对象。 下面的代码演示了计算在三维空间中的两个点之间的距离方法的示例。 

[!code-csharp[InArgument](../../samples/csharp/reference-semantics/Program.cs#InArgument "Specifying an In argument")]

这些参数是，每个包含三个双精度型值的两个结构。 双精度值是 8 个字节，因此每个自变量为 24 字节。 通过指定`in`修饰符，4 字节或 8 字节引用传递到这些自变量，具体取决于计算机的体系结构。 大小的差异很少，但当你的应用程序使用许多不同的值出现紧凑循环中调用此方法可以快速添加。
 
`in`修饰符补充`out`和`ref`用其他方式。 无法创建与不同，仅存在的方法的重载`in`，`out`或`ref`。 这些新的规则扩展必须始终为已定义的行为相同`out`和`ref`参数。

`in`修饰符可应用于任何采用参数的成员： 方法、 委托、 lambda、 本地函数、 索引器、 运算符。

与不同`ref`和`out`自变量，你可以使用文本值或常量的自变量为`in`参数。 此外，与不同`ref`或`out`参数，你不需要将应用`in`调用站点的修饰符。 下面的代码演示调用的两个示例`CalculateDistance`方法。 第一个命令使用通过引用传递的两个本地变量。 第二个包含方法调用的一部分创建的临时变量。 

[!code-csharp[UseInArgument](../../samples/csharp/reference-semantics/Program.cs#UseInArgument "Specifying an In argument")]

有几种方法在其中编译器可确保的只读的性质`in`强制执行自变量。  首先，调用的方法不能将直接分配到`in`参数。 它不能将直接分配到的任何字段`in`参数。 此外，不能将传递`in`参数到任何方法要求严苛`ref`或`out`修饰符。
编译器强制实施的`in`自变量是只读变量。 你可以调用使用按值传递语义的任何实例方法。 在这些情况下，一份`in`创建参数。 因为编译器可以为任何创建的临时变量`in`参数，你还可以为任何指定默认值`in`参数。 以下代码使用该值来指定为第二个点的默认值的来源 （点 0，0）：

[!code-csharp[InArgumentDefault](../../samples/csharp/reference-semantics/Program.cs#InArgumentDefault "Specifying defaults for an in parameter")]

`in`参数代码也可以用于引用类型或内置的数字值。 但是，这两种情况的好处是最小，如果有的话。

## <a name="ref-readonly-returns"></a>`ref readonly`返回

你可能还想要通过引用，返回值类型，但不允许调用方修改该值。 使用`ref readonly`修饰符来表示该设计意图。 它将返回的引用现有数据，但不是允许修改通知读取器。 

编译器强制实施，调用方不能修改引用。 尝试将直接分配给值会生成编译时错误。 但是，编译器无法知道是否任何成员方法会修改该结构的状态。
若要确保不修改该对象，编译器将创建副本，并调用使用该副本的引用的成员。 任何修改都是到该防御性的副本。 

很可能，库使用`Point3D`通常将使用在整个代码的来源。 每个实例在堆栈上创建一个新对象。 它可能会创建一个常数，并通过引用返回它更有利。 但是，如果返回到内部存储的引用，你可能需要强制，调用方不能修改引用的存储。 下面的代码定义一个只读属性，返回`readonly ref`到`Point3D`指定的来源。

[!code-csharp[OriginReference](../../samples/csharp/reference-semantics/Point3D.cs#OriginReference "Creating a readonly Origin reference")]

创建一份 ref readonly 返回很容易： 只需将其分配给具有未声明的变量`ref readonly`修饰符。 编译器将生成代码以将对象复制到分配的一部分。 

将分配到的变量时`ref readonly return`，你可以指定`ref readonly`变量或按值副本的 readonly 引用：

[!code-csharp[AssignRefReadonly](../../samples/csharp/reference-semantics/Program.cs#AssignRefReadonly "Assigning a ref readonly")]

在前面的代码的第一个分配创建的副本`Origin`常量和复制的分配。 第二个指定的引用。 请注意，`readonly`修饰符必须是变量的声明的一部分。 不能修改它所引用的引用。 尝试这样做将导致编译时错误。

## <a name="readonly-struct-type"></a>`readonly struct` 类型

应用`ref readonly`到高流量使用的结构可能已足够。
其他情况下，你可能想要创建不可变的结构。 然后你可以始终传递 readonly 引用。 当访问用作一个结构的方法时，做法删除被动复制发生`in`参数。

你可以通过创建执行的操作`readonly struct`类型。 你可以添加`readonly`修饰符添加到结构声明构造。 编译器强制实施该结构的所有成员都是`readonly`;`struct`必须是不可变。

有的其他优化`readonly struct`。 你可以使用`in`在每个位置的修饰符其中`readonly struct`是的自变量。 此外，你可以返回`readonly struct`作为`ref return`当您在返回其生存期超出返回对象的方法的作用域的对象。

最后，编译器将生成更高效的代码调用的成员时`readonly struct`:`this`引用，而不是一份接收方，始终是`in`参数通过引用传递给成员方法。 此优化将保存多个复制，当你使用`readonly struct`。 `Point3D`是使此更改的理想。 下面的代码显示了已更新`ReadonlyPoint3D`结构：

[!code-csharp[ReadonlyOnlyPoint3D](../../samples/csharp/reference-semantics/Point3D.cs#ReadonlyOnlyPoint3D "Defining an immutable structure")]

## <a name="ref-struct-type"></a>`ref struct` 类型

另一个相关的语言功能是能够声明必须是堆栈中分配的值类型。 换而言之，这些类型可以永远不会创建在堆上作为另一个类的成员。 此功能的主要动机是<xref:System.Span%601>和相关的结构。 <xref:System.Span%601>可能包含托管的指针作为其成员之一的另一个执行范围的长度。 因为 C# 不支持在不安全的上下文之外的托管内存指针，则它是实际稍有不同实现。 更改指针和长度的任何写入不是原子的。 这意味着<xref:System.Span%601>将受制于超出范围错误或其他类型安全冲突是它不限于单个堆栈帧。 此外，通常在 GC 堆上放置的托管的指针崩溃 JIT 时。

你可能有类似要求使用内存使用创建[ `stackalloc` ](language-reference/keywords/stackalloc.md)或者使用互操作 Api 中的内存时。 你可以定义自己`ref struct`为了满足这些需求的类型。 在本文中，请参阅示例使用`Span<T>`为简单起见。

`ref struct`声明会声明这种类型的结构，必须在堆栈上。 使用语言规则确保这些类型的安全使用。 其他类型声明为`ref struct`包括<xref:System.ReadOnlySpan%601>。 

若要保持的目标`ref struct`类型作为堆栈分配变量引入了几条规则，则编译器强制执行所有`ref struct`类型。

- 不能装箱`ref struct`。 不能将分配`ref struct`类型设置为变量的类型`object`， `dynamic`，或任何接口类型。
- 不能声明`ref struct`作为一个类或正常结构的成员。
- 你不能声明本地变量`ref struct`在异步方法中的类型。 您可以在返回的同步方法中声明它们`Task`，`Task<T>`或类似任务的类型。
- 不能声明`ref struct`迭代器中的本地变量。
- 无法捕获`ref struct`在 lambda 表达式或本地函数中的变量。

这些限制确保是你不会意外地使用`ref struct`无法将其提升为托管堆的方式。

## <a name="conclusions"></a>结论

为 C# 语言的这些增强功能旨在用于内存分配可在其中实现必要的性能关键的性能关键算法。 你可能会发现，通常不在你编写的代码中使用这些功能。 但是，这些增强功能已在.NET Framework 中的许多位置已采用。 随着越来越多的 Api 进行使用这些功能，你将看到自己的应用程序的性能改进。
