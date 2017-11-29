---
title: "F# 类型"
description: "了解有关在 F # 和 F # 类型如何命名和描述中使用的类型。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c7272a0d-5ab6-4eae-bceb-e49af498b917
ms.openlocfilehash: 9b7235637f301f91ae2cc8fbc59adc27cdfd5bd0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="f-types"></a>F# 类型

本主题介绍在 F # 和 F # 类型如何命名和描述中使用的类型。


## <a name="summary-of-f-types"></a>F # 类型摘要
某些类型被视为*基元类型*，例如布尔类型`bool`和整型和浮点型的各种大小，包括字节和字符类型。 中介绍了这些类型[基元类型](primitive-types.md)。

其他内置于语言的类型包括元组、 列表、 数组、 序列、 记录，并可区分联合。 如果你有其他.NET 语言的经验，但学习 F #，你应阅读的主题有关上述每种类型。 有关这些类型的详细信息的链接都将纳入[相关主题](https://msdn.microsoft.com/library/#rel)本主题的部分。 这些 F # 的特定类型支持功能的编程语言通用的编程样式。 许多这些类型具有关联的 F # 库中的模块支持对这些类型的常见操作。

函数的类型包括信息的参数类型和返回类型。

.NET Framework 是对象类型、 接口类型、 委托类型和其他的源。 就像任何其他.NET 语言中，你可以定义自己的对象类型。

此外，F # 代码可以定义别名，分别名为*类型缩写，用*，都为类型的可选名称。 类型可能会在将来更改，并且你想要避免更改取决于类型的代码时，你可能使用类型缩写。 或者，可能会将类型缩写用作一种类型，可使代码易于阅读和理解的友好名称。

F # 提供有用的集合设计也考虑了函数编程记住的类型。 使用这些集合类型，可帮助你编写是样式功能更强的代码。 有关详细信息，请参阅[F # 集合类型](fsharp-collection-types.md)。


## <a name="syntax-for-types"></a>类型的语法
在 F # 代码中，通常需要写出类型的名称。 每个类型具有一个语法形式，并使用语法的窗体类型批注、 抽象方法声明、 委托声明、 签名和其他构造。 每当声明解释器中的新程序构造，解释器将打印其类型的构造和语法的名称。 此语法可能只是一个标识符为用户定义的类型或内置标识符等的`int`或`string`，但对于更复杂类型，语法是更复杂。

下表显示 F # 类型类型语法的各个方面。



|类型|类型语法|示例|
|----|-----------|--------|
|基元类型|*类型名称*|`int`<br /><br />`float`<br /><br />`string`|
|聚合类型 （类、 结构、 联合、 记录、 枚举和等等）|*类型名称*|`System.DateTime`<br /><br />`Color`|
|类型缩写|*类型缩写名称*|`bigint`|
|完全限定的类型|*namespaces.type 名称*<br /><br />或<br /><br />*modules.type 名称*<br /><br />或<br /><br />*namespaces.modules.type 名称*|`System.IO.StreamWriter`|
|array|*类型名称*[] 或<br /><br />*类型名称*数组|`int[]`<br /><br />`array<int>`<br /><br />`int array`|
|二维数组|*类型名称*[、]|`int[,]`<br /><br />`float[,]`|
|三维数组|*类型名称*[、]|`float[,,]`|
|tuple|*类型 name1* &#42;*类型 name2* ...|例如，`(1,'b',3)`具有类型`int * char * int`|
|Generic Type — 泛型类型|*类型参数**泛型类型名称*<br /><br />或<br /><br />*泛型类型名称*&lt;*类型参数列表*&gt;|`'a list`<br /><br />`list<'a>`<br /><br />`Dictionary<'key, 'value>`|
|构造类型 （具有提供的特定类型自变量的泛型类型）|*类型参数**泛型类型名称*<br /><br />或<br /><br />*泛型类型名称*&lt;*类型自变量列表*&gt;|`int option`<br /><br />`string list`<br /><br />`int ref`<br /><br />`option<int>`<br /><br />`list<string>`<br /><br />`ref<int>`<br /><br />`Dictionary<int, string>`|
|具有单个参数的函数类型|*参数 type1*  - &gt; *返回类型*|采用的函数`int`并返回`string`具有类型`int -> string`|
|具有多个参数的函数类型|*参数 type1*  - &gt; *参数 type2*  - &gt; ...-&gt; *返回类型*|采用的函数`int`和`float`并返回`string`具有类型`int -> float -> string`|
|高阶函数作为参数|(*函数类型*)|`List.map`具有类型`('a -> 'b) -> 'a list -> 'b list`|
|委托|委托的*函数类型*|`delegate of unit -> int`|
|可变类型|#*类型名称*|`#System.Windows.Forms.Control`<br /><br />`#seq<int>`|

## <a name="related-topics"></a>相关主题


|主题|描述|
|-----|-----------|
|[基元类型](primitive-types.md)|介绍如整型、 布尔值类型和字符类型的内置简单类型。|
|[Unit 类型](unit-type.md)|描述`unit`类型，该类型具有一个值，并由 （）; 等效于`void`在 C# 和`Nothing`在 Visual Basic 中。|
|[元组](tuples.md)|描述的元组类型，在对、 三元组、 四重等分组的任何类型的关联值组成的类型。|
|[选项](options.md)|描述的选项类型，可以具有一个值，或为空的类型。|
|[列表](lists.md)|描述列表，它是有序的、 不可变序列元素的所有相同的类型。|
|[阵列](arrays.md)|介绍数组，它有序集的相同类型的可变元素占用连续的内存块，并具有固定大小。|
|[序列](sequences.md)|描述序列类型，它表示逻辑的一系列值;仅在必要时计算每个值。|
|[记录](records.md)|描述记录类型，一个小型命名值的聚合。|
|[可区分联合](discriminated-unions.md)|描述可区分联合类型，其值可以是任何一种可能的类型的一组的类型。|
|[函数](functions/index.md)|说明函数值。|
|[类](classes.md)|描述的类类型，对应于一个.NET 引用类型的对象类型。 类类型可包含成员、 属性、 实现的接口和基类型。|
|[结构](structures.md)|描述`struct`类型、 对应于一个.NET 值类型的对象类型。 `struct`类型通常表示一个小型的数据聚合。|
|[接口](interfaces.md)|描述接口类型，它们是表示一组的成员提供某种功能，但不包含数据的类型。 必须由要很有用的对象类型实现的接口类型。|
|[委托](delegates.md)|描述的委托类型，它表示为对象的函数。|
|[枚举](enumerations.md)|介绍枚举类型，其值所属的一组命名的值。|
|[特性](attributes.md)|描述了属性，用于指定另一个类型的元数据。|
|[异常类型](exception-handling/exception-types.md)|描述指定错误的信息的异常。|
