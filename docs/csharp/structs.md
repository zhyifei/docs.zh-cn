---
title: 结构 - C# 指南
description: 了解结构类型及其创建方式
ms.date: 10/12/2016
ms.technology: csharp-fundamentals
ms.assetid: a7094b8c-7229-4b6f-82fc-824d0ea0ec40
ms.openlocfilehash: cdfe2a763058b8f568ede2ff93c918c2dae874f7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346906"
---
# <a name="structs"></a>结构

结构  是一个值类型。 创建结构时，分配给结构的变量保留结构的实际数据。 将结构分配给新变量时，会复制结构。 因此，新变量和原始变量包含相同数据的副本（共两个）。 对一个副本所做的更改不会影响另一个副本。

值类型变量直接包含它们的值，这意味着在声明变量的任何上下文中内联分配内存。 对于值类型变量，没有单独的堆分配或垃圾回收开销。

值类型分为两类：[结构](language-reference/keywords/struct.md)和[枚举](language-reference/builtin-types/enum.md)。

内置数值类型是结构，包含可以访问的属性和方法：

[!code-csharp[Static Method](../../samples/snippets/csharp/concepts/structs/static-method.cs)]

不过，可以声明数值类型并向其赋值，就像它们是简单的非聚合类型一样：

[!code-csharp[Assign Values](../../samples/snippets/csharp/concepts/structs/assign-value.cs)]

例如，值类型为“密封”  ，这意味着不能从 <xref:System.Int32> 派生类型，并且不能将结构定义为从任何用户定义的类或结构继承，因为结构只能从 <xref:System.ValueType> 继承。 但是，一个结构可以实现一个或多个接口。 可将结构类型强制转换为接口类型；这将导致“装箱”  操作，以将结构包装在托管堆上的引用类型对象内。 当将值类型传递到接受 <xref:System.Object> 作为输入参数的方法时，将发生装箱操作。 有关详细信息，请参阅[装箱和取消装箱](./programming-guide/types/boxing-and-unboxing.md )。

使用 [struct](./language-reference/keywords/struct.md) 关键字可以创建你自己的自定义值类型。 结构通常用作一小组相关变量的容器，如以下示例所示：

[!code-csharp[Struct Keyword](../../samples/snippets/csharp/concepts/structs/struct-keyword.cs)]

有关 .NET Framework 中的值类型的详细信息，请参阅[通用类型系统](../standard/common-type-system.md)。

结构与类具有许多相同的语法，但结构比类受到的限制更多：

- 在结构声明中，除非将字段声明为 `const` 或 `static`，否则无法初始化。

- 结构不能声明无参数构造函数（没有参数的构造函数）或终结器。

- 结构在分配时进行复制。 将结构分配给新变量时，将复制所有数据，并且对新副本所做的任何修改不会更改原始副本的数据。 使用值类型的集合（如 Dictionary<string, myStruct>）时，请务必记住这一点。

- 结构是值类型，而类是引用类型。

- 与类不同，无需使用 `new` 运算符即可对结构进行实例化。

   > [!NOTE]
   > 在 .NET Core 2.1 及更高版本中，必须使用 [new 运算符](language-reference/operators/new-operator.md)或[默认文本](language-reference/operators/default.md#default-literal)，或者通过初始化每个私有字段来实例化结构类型。 有关详细信息，请参阅[从版本 2.0 迁移到 2.1 的中断性变更](../core/compatibility/2.0-2.1.md#corefx)。

- 结构可以声明具有参数的构造函数。

- 一个结构无法继承自另一个结构或类，并且它不能为类的基类。 所有结构都直接继承自 <xref:System.ValueType>，后者继承自 <xref:System.Object>。

- 和类一样，结构可以实现接口。

## <a name="nullable-value-types"></a>可以为 null 的值类型

普通值类型不能具有 [null](language-reference/keywords/null.md) 值。 不过，可以在类型后面附加 `?`，创建可以为 null 的值类型。 例如，`int?` 是还可以包含值 [null](./language-reference/keywords/null.md) 的 `int` 类型。 可以为 null 的值类型是泛型结构类型 <xref:System.Nullable%601> 的实例。 在将数据传入和传出数据库（数值可能为 NULL 或未定义）时，可为空的值类型特别有用。 有关详细信息，请参阅[可以为 null 的值类型](language-reference/builtin-types/nullable-value-types.md)。

## <a name="see-also"></a>请参阅

- [类](programming-guide/classes-and-structs/classes.md)
- [基本类型](basic-types.md)
