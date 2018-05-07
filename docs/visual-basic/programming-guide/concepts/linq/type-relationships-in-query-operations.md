---
title: 查询操作中的类型关系 (Visual Basic)
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
ms.openlocfilehash: ed0072eeb44a17201ddab2af6f6a44fd14461029
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="type-relationships-in-query-operations-visual-basic"></a>查询操作中的类型关系 (Visual Basic)
在中使用变量[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]查询操作强类型和必须彼此兼容。 数据源中、 在查询本身、 和的查询执行过程中，都使用强类型。 下图列出术语用于描述[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询。 有关查询的部件的详细信息，请参阅[基本查询操作 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)。  
  
 ![具有突出显示的元素的伪代码查询。] (../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")  
LINQ 查询部分  
  
 在查询中的范围变量的类型必须与数据源中元素的类型兼容。 查询变量的类型必须与在中定义的序列元素兼容`Select`子句。 最后，序列元素的类型也必须与兼容的类型中使用的循环控制变量`For Each`执行查询的语句。 此强类型便于在编译时类型错误的标识。  
  
 Visual Basic，使强类型便捷通过也称为实现本地类型推断、*隐式类型化*。 在前面的示例中，使用功能，你将看到它使用在整个[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]示例和文档。 在 Visual Basic，局部类型推理实现只需通过使用`Dim`语句而不用`As`子句。 在下面的示例中，`city`强类型化为一个字符串。  
  
 [!code-vb[VbLINQTypeRels#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_1.vb)]  
  
> [!NOTE]
>  局部类型推理时才起作用`Option Infer`设置为`On`。 有关详细信息，请参阅[Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)。  
  
 但是，即使在查询中使用局部类型推理时，也没有数据源中的变量、 查询变量和查询执行循环相同的类型关系。 可用于具有这些类型关系的一个基本的了解，在编写时[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询或使用的示例和文档中的代码示例。  
  
 你可能需要指定从数据源返回的类型不匹配的范围变量显式类型。 你可以通过使用指定的范围变量的类型`As`子句。 但是，这会导致出现错误转换是否[收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)和`Option Strict`设置为`On`。 因此，我们建议在从数据源检索到的值上执行转换。 你可以将值转换从数据源为显式范围变量类型使用<xref:System.Linq.Enumerable.Cast%2A>方法。 此外可以强制转换中选定的值`Select`子句的显式类型的范围变量的类型不同。 这些点下面的代码所示。  
  
 [!code-vb[VbLINQTypeRels#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_2.vb)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a>查询返回的源数据的整个元素  
 下面的示例演示[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询返回的源数据中的选定元素的序列的操作。 源， `names`，包含数组的字符串，并将查询输出是一个序列包含以字母 M 开头的字符串。  
  
 [!code-vb[VbLINQTypeRels#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_3.vb)]  
  
 这等效于下面的代码，但得更短且更易于编写。 依赖于在查询中的局部类型推理是在 Visual Basic 中的首选的样式。  
  
 [!code-vb[VbLINQTypeRels#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_4.vb)]  
  
 在这两个前面的代码示例中，情况下，是否隐式或显式类型确定存在下面的关系。  
  
1.  数据源中元素的类型`names`，是一种范围变量`name`，在查询中。  
  
2.  选择后，该对象的类型`name`，确定查询变量的类型`mNames`。 此处`name`是一个字符串，因此查询变量是在 Visual Basic 中的 IEnumerable (Of 字符串）。  
  
3.  中定义的查询`mNames`中执行`For Each`循环。 循环将循环访问执行查询的结果。 因为`mNames`，它执行时，将返回一个字符串，循环迭代变量，序列`nm`，也是一个字符串。  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a>返回从所选元素的一个字段的查询  
 下面的示例演示[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]查询返回包含只有一个属于从数据源选择每个元素的序列的操作。 查询采用集合`Customer`对象，以作为其数据源，并仅投影`Name`结果中的属性。 客户名称是一个字符串，因为此查询将生成一个序列的字符串作为输出。  
  
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
  
 变量之间的关系是类似于更简单的示例中。  
  
1.  数据源中元素的类型`customers`，是一种范围变量`cust`，在查询中。 在此示例中，该类型为`Customer`。  
  
2.  `Select`语句返回`Name`每个属性`Customer`而不是整个对象的对象。 因为`Name`是一个字符串，查询变量， `custNames`，将再次 IEnumerable (Of 字符串），不能的`Customer`。  
  
3.  因为`custNames`表示一个字符串，序列`For Each`循环的迭代变量`custName`，必须是字符串。  
  
 如果没有本地类型推断、 前面的示例将比较麻烦，若要编写，若要了解，如以下示例所示。  
  
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
 下面的示例演示更复杂的情况。 在前面的示例中，已显式指定类型的所有变量很不方便。 在此示例中，不可能。 而不是选择整个`Customer`从数据源或单个字段从每个元素的元素`Select`子句在此查询将返回两个属性的原始`Customer`对象：`Name`和`City`。 以响应`Select`子句，编译器定义包含这两个属性的匿名类型。 执行的结果`nameCityQuery`中`For Each`循环是一套新的匿名类型的实例。 因为匿名类型具有没有可用的名称，则无法指定的类型`nameCityQuery`或`custInfo`显式。 这就是，使用匿名类型，具有任何类型名称来代替了`String`中`IEnumerable(Of String)`。 有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。  
  
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
  
 尽管不能在前面的示例中指定的所有变量的类型，但关系保持不变。  
  
1.  数据源中元素的类型又中查询的范围变量的类型。 在此示例中，`cust`是的一个实例`Customer`。  
  
2.  因为`Select`语句生成的匿名类型，查询变量， `nameCityQuery`，必须以匿名类型隐式键入。 匿名类型没有可用的名称，因此不能显式指定。  
  
3.  中的迭代变量的类型`For Each`循环是在步骤 2 中创建的匿名类型。 因为该类型具有没有可用的名称，则必须隐式确定循环迭代变量的类型。  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 中的 LINQ 入门](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [查询](../../../../visual-basic/language-reference/queries/queries.md)
