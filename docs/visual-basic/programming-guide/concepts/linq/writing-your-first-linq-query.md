---
title: "编写第一个 LINQ 查询 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
caps.latest.revision: "56"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c16bb28189d5525654328da2dc80d868bbe61bf5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="writing-your-first-linq-query-visual-basic"></a>编写第一个 LINQ 查询 (Visual Basic)
*查询*是一种从数据源检索数据的表达式。 专用的查询语言来表述查询。 随着时间推移，不同的语言已针对开发了不同类型的数据源，例如，用于关系数据库的 SQL 和用于 XML 的 XQuery。 这使得应用程序开发人员，若要了解每种类型的数据源或数据格式受支持的新查询语言的必要条件。  
  
 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]通过提供跨各种类型的数据源和格式处理数据的一致模型，来简化这种情况。 在 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 查询中，始终会用到对象。 使用相同的基本编码模式来查询和转换 XML 文档中的数据，SQL 数据库、 ADO.NET 数据集和实体、.NET Framework 集合和任何其他源或格式为其[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]提供程序。 本文档介绍的三个阶段的创建和使用基本[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询。  
  
## <a name="three-stages-of-a-query-operation"></a>查询操作的三个阶段  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询操作包括以下三个操作：  
  
1.  获取数据源。  
  
2.  创建查询。  
  
3.  执行查询。  
  
 在[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]，执行的查询是从查询创建不同。 不要仅通过创建一个查询中检索任何数据。 这一点将在本主题后面部分进行更详细的讨论。  
  
 下面的示例演示查询操作的三个部分。 示例出于演示目的，作为方便的数据源使用整数的数组。 但是，相同的概念也适用于其他数据源。  
  
> [!NOTE]
>  上[编译页，项目设计器 (Visual Basic 中)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)，确保**Option infer**设置为**上**。  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 输出：  
  
 `0 2 4 6`  
  
## <a name="the-data-source"></a>数据源  
 由于前面的示例中的数据源是一个数组，它隐式支持泛型<xref:System.Collections.Generic.IEnumerable%601>接口。 这一事实，使你能够作为数据源使用数组[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询。 支持 <xref:System.Collections.Generic.IEnumerable%601> 或派生接口（如泛型 <xref:System.Linq.IQueryable%601>）的类型称为可查询类型。  
  
 用作隐式可查询类型，数组需要进行任何修改或特殊处理，就可以用作[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]数据源。 同样适用于任何支持的集合类型<xref:System.Collections.Generic.IEnumerable%601>，包括泛型<xref:System.Collections.Generic.List%601>， <xref:System.Collections.Generic.Dictionary%602>，和.NET Framework 类库中的其他类。  
  
 如果源数据不实现<xref:System.Collections.Generic.IEnumerable%601>、[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]实现的功能所需的提供程序*标准查询运算符*为该数据源。 例如，[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]处理的工作的 XML 文档加载到可查询<xref:System.Xml.Linq.XElement>类型，如下面的示例中所示。 有关标准查询运算符的详细信息，请参阅[标准查询运算符概述 (Visual Basic 中)](standard-query-operators-overview.md)。  
  
 [!code-vb[VbLINQFirstQuery#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_2.vb)]  
  
 与[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]，你首先创建一个对象关系映射在设计时，手动或通过使用[LINQ to SQL Visual Studio 中的工具](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)Visual Studio 中。 针对这些对象编写查询，然后由 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 在运行时处理与数据库的通信。 在下面的示例中，`customers`表示在数据库中，特定表和<xref:System.Data.Linq.Table%601>支持泛型<xref:System.Linq.IQueryable%601>。  
  
```vb  
' Create a data source from a SQL table.  
Dim db As New DataContext("C:\Northwind\Northwnd.mdf")  
Dim customers As Table(Of Customer) = db.GetTable(Of Customer)  
```  
  
 有关如何创建特定类型的数据源的详细信息，请参阅各种 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 提供程序的文档。 (有关这些提供程序的列表，请参阅[LINQ （语言集成查询）](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)。)基本规则很简单：[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]数据源是支持泛型的任何对象<xref:System.Collections.Generic.IEnumerable%601>接口或从其继承的接口。  
  
> [!NOTE]
>  类型，如<xref:System.Collections.ArrayList>支持非泛型<xref:System.Collections.IEnumerable>接口也可以用作[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]数据源。 有关示例，使用<xref:System.Collections.ArrayList>，请参阅[如何： 查询使用 LINQ (Visual Basic 中) ArrayList](how-to-query-an-arraylist-with-linq.md)。  
  
## <a name="the-query"></a>查询  
 在查询中，你可以指定你想要从数据源或源检索哪些的信息。 此外可以指定如何应排序、 分组或结构化返回前该信息。 若要启用查询创建，Visual Basic 已合并到语言中新的查询语法。  
  
 下面的示例中的查询时执行，从整数数组，返回所有偶数`numbers`。  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 查询表达式包含三个子句： `From`， `Where`，和`Select`。 中所述的特定功能和用途的每个查询表达式子句[基本查询操作 (Visual Basic)](basic-query-operations.md)。 有关详细信息，请参阅[查询](../../../../visual-basic/language-reference/queries/queries.md)。 请注意，在[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]，查询定义通常是存储在变量和执行更高版本。 查询变量，如`evensQuery`在前面的示例中，必须是可查询的类型。 一种`evensQuery`是`IEnumerable(Of Integer)`、 分配由编译器使用局部类型推理。  
  
 请务必请记住，则查询变量本身不执行任何操作，并且不返回任何数据。 它只存储查询定义。 在前面的示例中，它是`For Each`执行查询的循环。  
  
## <a name="query-execution"></a>查询执行  
 正在从查询创建单独查询执行。 查询创建定义查询，但由不同的机制触发执行。 只要定义它，可以执行查询 (*立即执行*)，或该定义可以存储和更高版本执行查询 (*延迟执行*)。  
  
### <a name="deferred-execution"></a>延迟执行  
 典型[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询类似于在上一示例中，在其中一个`evensQuery`定义。 它创建查询，但不立即执行查询。 相反，查询定义存储在查询变量`evensQuery`。 执行查询更高版本，通常通过使用`For Each`循环，返回的序列的值，或通过应用一个标准查询运算符，如`Count`或`Max`。 此过程称为*延迟执行*。  
  
 [!code-vb[VbLINQFirstQuery#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_3.vb)]  
  
 通过使用中的迭代变量的检索到的数据访问值的序列，`For Each`循环 (`number`在前面的示例)。 因为查询变量， `evensQuery`，保存的查询定义，而不是查询结果中，你可以按你想通过使用查询变量不止一次的频率执行查询。 例如，你可能正在由单独的应用程序不断更新的应用程序有了数据库。 创建用于从该数据库中检索数据的查询后，你可以使用`For Each`循环反复执行查询，每次都检索最新数据。  
  
 下面的示例演示如何延迟的执行的工作。 后`evensQuery2`定义并的情况下执行`For Each`循环中，如下所示上述示例中，数据源中的某些元素`numbers`更改。 然后，另一个`For Each`循环运行`evensQuery2`试。 结果不一样，第二次，因为`For Each`循环执行查询同样，使用中的新值`numbers`。  
  
 [!code-vb[VbLINQFirstQuery#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_4.vb)]  
  
 输出：  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>立即执行  
 延迟执行的查询，在查询定义存储在更高版本执行的查询变量。 立即执行，而在其定义时执行查询。 应用要求对查询结果的单个元素的访问的方法时，将触发执行。 立即执行通常会强制使用返回单个值的标准查询运算符之一。 示例包括`Count`， `Max`， `Average`，和`First`。 只要它们应用才能计算并返回单一实例结果，这些标准查询运算符将执行查询。 有关返回单个值的标准查询运算符的详细信息，请参阅[聚合操作](aggregation-operations.md)，[元素操作](element-operations.md)，和[限定符操作](quantifier-operations.md)。  
  
 以下查询返回的整数数组中的偶数的计数。 未保存的查询定义，和`numEvens`是一个简单`Integer`。  
  
 [!code-vb[VbLINQFirstQuery#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_5.vb)]  
  
 你可以通过使用实现相同的结果`Aggregate`方法。  
  
 [!code-vb[VbLINQFirstQuery#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_6.vb)]  
  
 你还可以通过调用来强制执行的查询`ToList`或`ToArray`（即时） 的查询或查询变量 （延迟），如下面的代码中所示的方法。  
  
 [!code-vb[VbLINQFirstQuery#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_7.vb)]  
  
 在前面的示例中，`evensQuery3`是查询变量，而`evensList`是列表和`evensArray`是数组。  
  
 使用`ToList`或`ToArray`强制立即执行已想要立即执行查询并缓存单个集合对象中的结果的方案中尤其有用。 有关这些方法的详细信息，请参阅[转换数据类型](converting-data-types.md)。  
  
 也可能会导致查询执行使用`IEnumerable`如方法<xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A>方法。  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 中的 LINQ 入门](getting-started-with-linq.md)  
 [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [标准查询运算符概述 (Visual Basic)](standard-query-operators-overview.md)  
 [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [查询](../../../../visual-basic/language-reference/queries/queries.md)
