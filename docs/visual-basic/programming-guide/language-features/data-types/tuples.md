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
ms.openlocfilehash: bf26b7ce58c1e20fbbe5043cbd2acfd5712837fa
ms.sourcegitcommit: d95a91d685565f4d95c8773b558752864a6a3d7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
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
```

版本号可以是任何版本的 Visual Basic 编译器开头 15.3。 而不是硬编码的特定编译器版本，你还可以指定"最新"的值作为`LangVersion`使用 Visual Basic 编译器在系统上安装的最新版本进行编译。

在某些情况下，Visual Basic 编译器无法推断元组元素名称从候选名称，并且仅可以使用其默认名称，如引用元组字段`Item1`， `Item2`，等等。这些方法包括：

- 候选名称是元组成员的名称相同如`Item3`， `Rest`，或`ToString`。

- 候选名称重复元组中。
 
当字段名称推理失败时，Visual Basic 不会生成编译器错误，也不是在运行时引发的异常。 相反，元组字段必须按名称来引用其预定义，如`Item1`和`Item2`。 
  
## <a name="tuples-versus-structures"></a>与结构的元组

Visual Basic 元组是值类型之一的实例**System.ValueTuple**泛型类型。 例如，`holiday`是的一个实例，在前面的示例中定义的元组<xref:System.ValueTuple%603>结构。 它被旨在作为数据的轻量容器。 因为此元组的目标是要更加轻松地使用多个数据项创建对象，但它缺少一些自定义结构可能具有的功能。 这些方法包括：

- 客户成员。 不能定义自己的属性、 方法或元组的事件。

- 验证。 无法验证分配给字段的数据。

- 不是可变性。 Visual Basic 元组是可变的。 与此相反，自定义结构允许你控制实例是否可变或不可变。

如果自定义成员、 属性和字段验证或不可变性很重要，则应使用 Visual Basic[结构](../../../language-reference/statements/structure-statement.md)语句以定义自定义值类型。

Visual Basic 元组未继承的成员其**ValueTuple**类型。 除了其字段，这些方法包括以下方法：

| 成员 | 描述 |
| ---|---|
| CompareTo | 比较到具有相同数量的元素的另一个元组的当前元组。 |
| Equals | 确定是否等于另一个元组或对象的当前元组。 |
| GetHashCode | 计算当前实例的哈希代码。 |
| ToString | 返回此元组，它采用的形式的字符串表示`(Item1, Item2...)`，其中`Item1`和`Item2`表示元组的字段的值。 |

此外， **ValueTuple**类型实现<xref:System.Collections.IStructuralComparable>和<xref:System.Collections.IStructuralEquatable>接口，可用于定义客户比较器。

## <a name="assignment-and-tuples"></a>赋值和元组

Visual Basic 支持具有相同数目的字段的元组类型之间的分配。 如果下列其中一项为 true，则可以转换的字段类型：

- 源和目标字段均为相同的类型。

- 扩大 （或隐式） 转换的源类型，为目标类型定义。 

- `Option Strict` 是`On`，和收缩 （或显式） 转换的源类型，为目标类型定义。 如果源值超出了目标类型的范围，此转换可以引发异常。

对于其他转换，不考虑进行赋值。 让我们看一下元组类型之间允许的赋值类型。

注意以下示例中使用的这些变量：

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

前两个变量，`unnamed`和`anonymous`，没有为字段提供的语义名称。 其字段名称就是默认`Item1`和`Item2`。 最后两个变量，`named`和`differentName`具有语义的字段的名称。 请注意，这两个元组具有不同的字段名称。

这些元组的所有四个具有相同数目的字段 （称为 arity），并且这些字段的类型相同。 因此可进行以下赋值：

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

请注意，元组的名称未赋值。 字段的赋值顺序遵循字段在元组中的顺序。

最后，请注意，我们可以将分配`named`到的元组`conversion`元组，即使的第一个字段`named`是`Integer`，和的第一个字段`conversion`是`Long`。 此分配将成功，因为转换`Integer`到`Long`的扩大转换。

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

元组具有不同数量的字段不能分配：

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
