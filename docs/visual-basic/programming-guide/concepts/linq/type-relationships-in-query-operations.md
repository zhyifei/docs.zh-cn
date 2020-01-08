---
title: 查询操作中的类型关系
ms.date: 07/20/2015
helpviewer_keywords:
- variable relationships [LINQ in Visual Basic]
- type information inferred [LINQ in Visual Basic]
- type relationships [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], type relationships
- data sources [LINQ in Visual Basic], type relationships
- LINQ [Visual Basic], type relationships
- inferring type information [LINQ in Visual Basic]
- relationships [LINQ in Visual Basic]
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
ms.openlocfilehash: e839271ac254a5e96f8c99f59397016fb99540aa
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636908"
---
# <a name="type-relationships-in-query-operations-visual-basic"></a>查询操作中的类型关系 (Visual Basic)

在语言集成查询（LINQ）查询操作中使用的变量是强类型化的，并且必须彼此兼容。 强类型化在数据源、查询本身和查询执行中使用。 下图标识用于描述 LINQ 查询的术语。 有关查询各个部分的详细信息，请参阅[基本查询操作（Visual Basic）](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)。

![显示突出显示了元素的伪代码查询的屏幕截图。](./media/type-relationships-in-query-operations/linq-query-description-terms.png)

查询中范围变量的类型必须与数据源中的元素类型兼容。 查询变量的类型必须与 `Select` 子句中定义的序列元素兼容。 最后，序列元素的类型还必须与用于执行查询的 `For Each` 语句中使用的循环控制变量的类型兼容。 这种强类型化有助于在编译时标识错误的类型。

通过实现局部类型推理（也称为*隐式*类型），Visual Basic 使强类型化变得非常方便。 上一示例中使用了该功能，您将看到它在整个 LINQ 示例和文档中使用。 在 Visual Basic 中，仅通过使用不带 `As` 子句的 `Dim` 语句来完成本地类型推断。 在下面的示例中，`city` 强类型化为字符串。

[!code-vb[VbLINQTypeRels#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#1)]

> [!NOTE]
> 仅当 `Option Infer` 设置为 `On`时，本地类型推理才有效。 有关详细信息，请参阅[Option 推理语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)。

但是，即使在查询中使用局部类型推理，数据源、查询变量和查询执行循环中的变量也存在相同的类型关系。 编写 LINQ 查询或使用文档中的示例和代码示例时，基本了解这些类型关系非常有用。

对于与从数据源返回的类型不匹配的范围变量，可能需要指定显式类型。 您可以使用 `As` 子句指定范围变量的类型。 但是，如果转换是[收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)并且 `Option Strict` 设置为 `On`，这会导致错误。 因此，建议您对从数据源检索的值执行转换。 您可以使用 <xref:System.Linq.Enumerable.Cast%2A> 方法将数据源中的值转换为显式范围变量类型。 还可以将 `Select` 子句中选择的值强制转换为与范围变量的类型不同的显式类型。 下面的代码演示了这些要点。

[!code-vb[VbLINQTypeRels#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#4)]

## <a name="queries-that-return-entire-elements-of-the-source-data"></a>返回源数据的整个元素的查询

下面的示例演示一个 LINQ 查询操作，该操作返回从源数据中选择的一系列元素。 `names`源包含一个字符串数组，并且查询输出是一个序列，其中包含以字母 M 开头的字符串。

[!code-vb[VbLINQTypeRels#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#2)]

这等效于以下代码，但更短且更易于编写。 在查询中，依赖于本地类型推理是 Visual Basic 中的首选样式。

[!code-vb[VbLINQTypeRels#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#3)]

上述两个代码示例都存在以下关系，无论类型是隐式还是显式确定的。

1. 数据源中元素的类型（`names`）是查询中范围变量的类型 `name`。

2. `name`选择的对象的类型决定查询变量的类型，`mNames`。 此处 `name` 是一个字符串，因此查询变量在 Visual Basic 中是 IEnumerable （的字符串）。

3. `mNames` 中定义的查询是在 `For Each` 循环中执行的。 循环将循环访问执行查询的结果。 因为 `mNames`在执行时将返回一个字符串序列，所以循环迭代变量 `nm`，也是一个字符串。

## <a name="queries-that-return-one-field-from-selected-elements"></a>从选定元素返回一个字段的查询

下面的示例演示一个 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 查询操作，该操作返回一个序列，该序列仅包含从数据源中选择的每个元素的一个部分。 查询采用 `Customer` 对象的集合作为其数据源，并仅在结果中的 `Name` 属性中进行投影。 因为客户名称是字符串，所以查询生成一个字符串序列作为输出。

```vb
' Method GetTable returns a table of Customer objects.
Dim customers = db.GetTable(Of Customer)()
Dim custNames = From cust In customers
                Where cust.City = "London"
                Select cust.Name

For Each custName In custNames
    Console.WriteLine(custName)
Next
```

变量之间的关系类似于简单示例中的关系。

1. 数据源中元素的类型（`customers`）是查询中范围变量的类型 `cust`。 在此示例中，该类型为 `Customer`。

2. `Select` 语句返回每个 `Customer` 对象（而非整个对象）的 `Name` 属性。 由于 `Name` 是字符串，因此查询变量 `custNames`将再次为 IEnumerable （字符串），而不是 `Customer`。

3. 由于 `custNames` 表示字符串序列，因此 `For Each` 循环的迭代变量 `custName`必须是字符串。

如果没有局部类型推理，则上一个示例将更难编写和理解，如下面的示例所示。

```vb
' Method GetTable returns a table of Customer objects.
 Dim customers As Table(Of Customer) = db.GetTable(Of Customer)()
 Dim custNames As IEnumerable(Of String) =
     From cust As Customer In customers
     Where cust.City = "London"
     Select cust.Name

 For Each custName As String In custNames
     Console.WriteLine(custName)
 Next
```

## <a name="queries-that-require-anonymous-types"></a>需要匿名类型的查询

下面的示例演示一个更复杂的情况。 在上面的示例中，显式指定所有变量的类型是不方便的。 在此示例中，这是不可能的。 此查询中的 `Select` 子句不会从数据源中选择整个 `Customer` 元素，也不是从每个元素中选择单个字段，而是返回原始 `Customer` 对象的两个属性： `Name` 和 `City`。 在响应 `Select` 子句时，编译器将定义包含这两个属性的匿名类型。 在 `For Each` 循环中执行 `nameCityQuery` 的结果是新匿名类型的实例的集合。 由于匿名类型没有可使用的名称，因此不能显式指定 `nameCityQuery` 类型或 `custInfo`。 也就是说，使用匿名类型时，没有用于替代 `IEnumerable(Of String)`中的 `String` 的类型名称。 有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。

```vb
' Method GetTable returns a table of Customer objects.
Dim customers = db.GetTable(Of Customer)()
Dim nameCityQuery = From cust In customers
                    Where cust.City = "London"
                    Select cust.Name, cust.City

For Each custInfo In nameCityQuery
    Console.WriteLine(custInfo.Name)
Next
```

尽管不能为上一示例中的所有变量指定类型，但关系仍保持不变。

1. 数据源中元素的类型再次为查询中范围变量的类型。 在此示例中，`cust` 是 `Customer`的实例。

2. 由于 `Select` 语句生成匿名类型，因此必须以匿名类型的形式隐式类型化查询变量 `nameCityQuery`。 匿名类型没有可使用的名称，因此不能显式指定。

3. `For Each` 循环中迭代变量的类型是在步骤2中创建的匿名类型。 因为类型没有可用名称，所以必须隐式确定循环迭代变量的类型。

## <a name="see-also"></a>另请参阅

- [Visual Basic 中的 LINQ 入门](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [查询](../../../../visual-basic/language-reference/queries/index.md)
