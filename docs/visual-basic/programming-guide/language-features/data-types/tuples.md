---
title: "在 Visual Basic 中的元组"
ms.custom: 
ms.date: 04/23/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2653b9dc8a6ecbcb718c20be8bd6275edf4cfb6e
ms.sourcegitcommit: be1fb5d9447ad459bef22b91a91c72e3e0b2d916
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="tuples-visual-basic"></a>元组 (Visual Basic)

从 Visual Basic 自 2017 年开始，Visual Basic 语言提供内置支持的元组，可创建元组和访问元组更容易的元素。 元组是具有特定的数量和值序列的轻量数据结构。 当实例化此元组时，你定义的数量以及每个值 （或元素） 的数据类型。 例如的 2 元组 （或对） 有两个元素。 第一个可能`Boolean`值，而第二个是`String`。 元组建立方便地将多个值存储在单个对象，因为它们是通常用作一个简便的方法来从方法返回多个值。

> [!IMPORTANT]
> 元组的支持，需要<xref:System.ValueTuple>类型。 如果未安装.NET Framework 4.7，必须先添加 NuGet 包`System.ValueTuple`，即在 NuGet 库上可用。 而无需此包，你可能会收到编译错误类似于"预定义类型未定义或导入 ValueTuple(Of,,,)。

## <a name="instantiating-and-using-a-tuple"></a>实例化并使用一个元组

通过将其以逗号分隔值 im 括号实例元组。 每个这些值随后将成为此元组的字段。 例如，下面的代码定义三次 （或 3 元组），其中有`Date`作为其第一个值，`String`作为第二个操作数，和一个`Boolean`作为其第三个。

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

默认情况下，元组中每个字段的名称包含字符串`Item`以及字段的元组中的基于 1 的位置。 有关此 3 元组，`Date`字段是`Item1`、`String`字段是`Item2`，和`Boolean`字段是`Item3`。 下面的示例显示在之前的代码行中实例化此元组的字段的值

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

Visual Basic 元组的字段是读写;已实例化元组后，你可以修改其值。 下面的示例修改两个元组在前面的示例中创建的三个字段，并显示结果。

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a>实例化和使用命名的元组

而不是使用一个元组的字段的默认名称，可以实例化*名为元组*通过将您自己的名称分配给此元组的元素。 此元组的字段然后可由其分配名称访问*或*通过默认名称。 下面的示例实例化相同 3 元组作为以前，只不过它进行显式命名的第一个字段`EventDate`，第二个`Name`，第三个`IsHoliday`。 然后显示字段值，修改它们，并再次显示字段值。

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a>推断元组元素名称

从 Visual Basic 15.3 开始，Visual Basic 可以推导出的元组元素; 的名称不需要显式将它们分配。 初始化从一组变量，一个元组，并且你想要的变量的名称相同的元组元素名称时，推断元组名称很有用。 

下面的示例创建`stateInfo`元组显式包含三个名为元素， `state`， `stateName`，和`capital`。 请注意，在命名元素中，元组的初始化语句只需将分配已命名的元素具有相同名称的变量的值。

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
元素和变量具有相同的名称，因为 Visual Basic 编译器可以推断的字段的名称，如以下示例所示。

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

若要启用 interred 元组元素名称，必须定义要在 Visual Basic 项目中使用的 Visual Basic 编译器的版本 (\*.vbproj) 文件： 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 

The version number can be any version of the Visual Basic compiler starting with 15.3. Rather than hard-coding a specific compiler version, you can also specify "Latest" as the value of `LangVersion` to compile with the most recent version of the Visual Basic compiler installed on your system.

In some cases, the Visual Basic compiler cannot infer the tuple element name from the candidate name, and the tuple field can only be referenced using its default name, such as `Item1`, `Item2`, etc. These include:

- The candidate name is the same as the name of a tuple member, such as `Item3`, `Rest`, or `ToString`.

- The candidate name is duplicated in the tuple.
 
When field name inference fails, Visual Basic does not generate a compiler error, nor is an exception thrown at runtime. Instead, tuple fields must be referenced by their predefined names, such as `Item1` and `Item2`. 
  
## Tuples versus structures

A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types. For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure. It is designed to be a lightweight container for data. Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have. These include:

- Customer members. You cannot define your own properties, methods, or events for a tuple.

- Validation. You cannot validate the data assigned to fields.

- Immutability. Visual Basic tuples are mutable. In contrast, a custom structure allows you to control whether an instance is mutable or immutable.

If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.

A Visual Basic tuple does inherit the members of its **ValueTuple** type. In addition to its fields, these include the following methods:

| Member | Description |
| ---|---|
| CompareTo | Compares the current tuple to another tuple with the same number of elements. |
| Equals | Determines whether the current tuple is equal to another tuple or object. |
| GetHashCode | Calculates the hash code for the current instance. |
| ToString | Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields. |

In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.

## Assignment and tuples

Visual Basic supports assignment between tuple types that have the same number of fields. The field types can be converted if one of the following is true:

- The source and target field are of the same type.

- A widening (or implicit) conversion of the source type to the target type is defined. 

- `Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined. This conversion can throw an exception if the source value is outside the range of the target type.

Other conversions are not considered for assignments. Let's look at the kinds of assignments that are allowed between tuple types.

Consider these variables used in the following examples:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields. Their field names are the default `Item1` and `Item2`. The last two variables, `named` and `differentName` have semantic field names. Note that these two tuples have different names for the fields.

All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical. Therefore, all of these assignments work:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Notice that the names of the tuples are not assigned. The values of the fields are assigned following the order of the fields in the tuple.

Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`. This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Tuples with different numbers of fields are not assignable:

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a>作为方法返回值的元组

方法可以返回单个值。 通常情况下，不过，你想要的方法调用返回多个值。 有多种，若要解决此限制：

- 你可以创建自定义类或结构，其属性或字段表示由该方法返回的值。 因此是一种 heavyweight 解决方案;它需要定义其唯一目的是从方法调用中检索值的自定义类型。

- 你可以从方法返回单个值，并通过将它们传递通过对该方法的引用返回剩下的值。 这涉及到的实例化变量和风险无意中重写的变量通过引用传递的值的开销。

- 你可以使用一个元组，它提供一种轻量型解决方案检索多个返回值。

例如， **TryParse** .NET 返回中的方法`Boolean`值，该值指示是否在分析操作成功。 在分析操作的结果在变量通过引用传递给该方法返回。 通常情况下，调用分析方法如<xref:System.Int32.TryParse%2A?displayProperty=nameWithType>如下所示：

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

我们可以从在分析操作返回一个元组，如果我们包装对调用<xref:System.Int32.TryParse%2A?displayProperty=nameWithType>在我们自己的方法的方法。 在下面的示例中，`NumericLibrary.ParseInteger`调用<xref:System.Int32.TryParse%2A?displayProperty=nameWithType>方法并返回具有两个元素的命名元组。 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

然后，可以调用此方法的代码如下所示：

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a>Visual Basic 元组和.NET Framework 中的元组

Visual Basic 元组是之一的实例**System.ValueTuple**在.NET Framework 4.7 中引入的泛型类型。 .NET Framework 还包括一套泛型**System.Tuple**类。 这些类，但是，不同于 Visual Basic 元组和**System.ValueTuple**通过多种方式中的泛型类型：

- 元素**元组**类是属性名为`Item1`， `Item2`，依次类推。 在 Visual Basic 元组和**ValueTuple**类型，对元组元素是字段。

- 不能将有意义的名称分配到的元素**元组**实例或**ValueTuple**实例。 Visual Basic，可分配传达的含义的字段的名称。

- 属性**元组**实例是只读的; 元组是不可变。 在 Visual Basic 元组和**ValueTuple**类型，元组字段是可读写; 元组是可变的。

- 泛型**元组**类型是引用类型。 使用这些**元组**类型分配对象的方式。 在热路径中，这可能会对应用程序性能产生明显的影响。 Visual Basic 元组和**ValueTuple**类型是值类型。

中的扩展方法<xref:System.TupleExtensions>类，更易于 Visual Basic 元组和.NET 之间转换**元组**对象。 **ToTuple**方法将 Visual Basic 元组转换为.NET**元组**对象，与**ToValueTuple**方法将转换.NET**元组**Visual Basic 元组对象。

下面的示例中创建元组，将其转换为.NET**元组**对象，并将转换回 Visual Basic 元组。 然后，示例进行比较以确保它们相等替换为原始此元组。

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a>请参阅

[Visual Basic 语言参考](index.md)  
