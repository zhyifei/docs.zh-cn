---
title: LINQ 介绍
ms.date: 08/28/2018
helpviewer_keywords:
- queries [LINQ in Visual Basic], about LINQ in Visual Basic queries
- query execution [LINQ in Visual Basic]
- range variables [Visual Basic]
- LINQ [Visual Basic]
- LINQ [Visual Basic], about LINQ in Visual Basic
- query expressions [LINQ in Visual Basic]
- LINQ
- deferred execution
- iteration variables [Visual Basic]
ms.assetid: 3047d86e-0d49-40e2-928b-dc02e46c7984
ms.openlocfilehash: 610f2a1020cc15f855b3ddfc0917e14aae34fb82
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344938"
---
# <a name="introduction-to-linq-in-visual-basic"></a>Visual Basic 中的 LINQ 简介
Language-Integrated Query (LINQ) adds query capabilities to Visual Basic and provides simple and powerful capabilities when you work with all kinds of data. Rather than sending a query to a database to be processed, or working with different query syntax for each type of data that you are searching, LINQ introduces queries as part of the Visual Basic language. 它使用统一语法，而不考虑数据的类型。  
  
 LINQ enables you to query data from a SQL Server database, XML, in-memory arrays and collections, ADO.NET datasets, or any other remote or local data source that supports LINQ. You can do all this with common Visual Basic language elements. Because your queries are written in the Visual Basic language, your query results are returned as strongly-typed objects. 这些对象支持 IntelliSense，这使你能够更快地编写代码，并在编译时（而不是在运行时）捕获查询中的错误。 可将 LINQ 查询用作其他查询的源，以便缩小结果的范围。 还可将它们绑定到控件，使用户能够轻松地查看和修改查询结果。  
  
 例如，下面的代码示例显示一个 LINQ 查询，它从集合返回一个客户列表并根据位置对其进行分组。  
  
 [!code-vb[VbVbalrIntroToLINQ#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#1)]  
  
## <a name="running-the-examples"></a>运行示例  
 To run the examples in the introduction and in the [Structure of a LINQ Query](#structure-of-a-linq-query) section, include the following code, which returns lists of customers and orders.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#31)]  
  
## <a name="linq-providers"></a>LINQ providers  
 A *LINQ provider* maps your Visual Basic LINQ queries to the data source being queried. 编写 LINQ 查询时，该提供程序将接受该查询，并将其转换为数据源能够执行的命令。 该提供程序还将来自源的数据转换为构成查询结果的对象。 最后，当你将更新发送至数据源时，它又将这些对象转换为数据。  
  
 Visual Basic includes the following LINQ providers.  
  
|Provider|描述|  
|---|---|  
|LINQ to Objects|通过 LINQ to Objects 提供程序，可以查询内存中集合和数组。 如果对象支持 <xref:System.Collections.IEnumerable> 或 <xref:System.Collections.Generic.IEnumerable%601> 接口，则可以通过 LINQ to Objects 提供程序对其进行查询。<br /><br /> You can enable the LINQ to Objects provider by importing the <xref:System.Linq> namespace, which is imported by default for all Visual Basic projects.<br /><br /> For more information about the LINQ to Objects provider, see [LINQ to Objects](../../concepts/linq/linq-to-objects.md).|  
|LINQ to SQL|通过 LINQ to SQL 提供程序，可以查询和修改 SQL Server 数据库中的数据。 这样就可以轻松将应用程序的对象模型映射到数据库中的表和对象。<br /><br /> Visual Basic makes it easier to work with LINQ to SQL by including the Object Relational Designer (O/R Designer). 此设计器用于在应用程序中创建映射到数据库中的对象的对象模型。 The O/R Designer also provides functionality to map stored procedures and functions to the <xref:System.Data.Linq.DataContext> object, which manages communication with the database and stores state for optimistic concurrency checks.<br /><br /> For more information about the LINQ to SQL provider, see [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md). For more information about the Object Relational Designer, see [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|通过 LINQ to XML 提供程序，可以查询和修改 XML。 可以修改内存中 XML，也可以从文件加载 XML 以及将 XML 保存到文件。<br /><br /> Additionally, the LINQ to XML provider enables XML literals and XML axis properties that enable you to write XML directly in your Visual Basic code. For more information, see [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|The LINQ to DataSet provider enables you to query and update data in an ADO.NET dataset. 可以将 LINQ 的强大功能添加到使用数据集的应用程序，以便简化和扩展查询、聚合和更新数据集中数据的功能。<br /><br /> 有关详细信息，请参阅 [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)。|  
  
## <a name="structure-of-a-linq-query"></a>Structure of a LINQ query  
 A LINQ query, often referred to as a *query expression*, consists of a combination of query clauses that identify the data sources and iteration variables for the query. 查询表达式还可以包含排序、筛选、分组和联接的说明或要对源数据应用的计算。 查询表达式语法类似于 SQL的语法；因此，你可能发现该语法大都非常熟悉。  
  
 查询表达式以 `From` 子句开头。 此子句标识查询的源数据和用于分别表示源数据中每个元素的变量。 These variables are named *range variables* or *iteration variables*. `From` 子句是查询所必需的，但 `Aggregate` 查询除外，在该查询中 `From` 子句是可选的。 在 `From` 或 `Aggregate` 子句中标识查询的范围和源后，即可包括查询子句的任意组合来优化查询。 For details about query clauses, see Visual Basic LINQ Query Operators later in this topic. 例如，下面的查询将客户数据源集合标识为 `customers` 变量和一个名为 `cust` 的迭代变量。  
  
 [!code-vb[VbVbalrIntroToLINQ#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#2)]  
  
 此示例本身是一个有效查询；但是，如果添加更多查询子句以优化结果，查询将变得更加强大。 例如，可以添加 `Where` 子句，以便按一个或多个值筛选结果。 查询表达式都是单行代码；只能将其他查询子句附加到查询的末尾。 You can break up a query across multiple lines of text to improve readability by using the underscore (\_) line-continuation character. 下面的代码示例演示了包含 `Where` 子句的查询示例。  
  
 [!code-vb[VbVbalrIntroToLINQ#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#3)]  
  
 另一个功能强大的查询子句是 `Select` 子句，它能够从数据源仅返回所选字段。 LINQ 查询返回强类型化对象的可枚举集合。 查询可以返回匿名类型或具名类型的集合。 可以使用 `Select` 子句从数据源仅返回单个字段。 执行此操作时，返回的集合类型为该单个字段的类型。 也可以使用 `Select` 子句从数据源返回多个字段。 执行此操作时，返回的集合类型为新的匿名类型。 还可以将由查询返回的字段和指定的具名类型字段进行匹配。 下面的代码示例演示了一个查询表达式，它返回一个匿名类型的集合，该集合具有使用来自数据源中所选字段的数据填充的成员。  
  
 [!code-vb[VbVbalrIntroToLINQ#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#4)]  
  
 还可使用 LINQ 查询合并多个数据源组并返回单个结果。 可以使用一个或多个 `From` 子句，或者使用 `Join` 或 `Group Join` 查询子句来完成此操作。 下面的代码示例演示了一个查询表达式，它合并客户和订单数据，并返回包含客户和订单数据的匿名类型的集合。  
  
 [!code-vb[VbVbalrIntroToLINQ#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#5)]  
  
 可以使用 `Group Join` 子句创建包含客户对象集合的分层查询结果。 每个客户对象都具有一个包含该客户所有订单的集合的属性。 下面的代码示例演示了一个查询表达式，它将客户和订单数据合并为分层结果，并返回一个匿名类型的集合。 查询返回一个包括 `CustomerOrders` 属性的类型，该属性包含客户订单数据的集合。 它还包括 `OrderTotal` 属性，该属性包含客户所有订单的总计值之和。 （此查询等效于 LEFT OUTER JOIN。）  
  
 [!code-vb[VbVbalrIntroToLINQ#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#6)]  
  
 还有几个其他 LINQ 查询运算符，可用它们创建功能强大的查询表达式。 本主题的下一部分将讨论查询表达式中可以包括的各种查询子句。 For details about Visual Basic query clauses, see [Queries](../../../../visual-basic/language-reference/queries/index.md).  
  
## <a name="visual-basic-linq-query-operators"></a>Visual Basic LINQ query operators  

你可以调用 <xref:System.Linq> 命名空间和支持 LINQ 查询的其他命名空间中的类包括的方法，以便根据应用程序的需要创建和完善查询。 Visual Basic includes keywords for the following common query clauses. For details about Visual Basic query clauses, see [Queries](../../../language-reference/queries/index.md).

### <a name="from-clause"></a>From 子句

Either a [`From` clause](../../../../visual-basic/language-reference/queries/from-clause.md) or an `Aggregate` clause is required to begin a query. `From` 子句可指定查询的源集合和迭代变量。 例如:

 [!code-vb[VbVbalrIntroToLINQ#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#7)]

### <a name="select-clause"></a>Select 子句

可选。 A [`Select` clause](../../../../visual-basic/language-reference/queries/select-clause.md) declares a set of iteration variables for a query. 例如:

 [!code-vb[VbVbalrIntroToLINQ#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#8)]

如果未指定 `Select` 子句，则该查询的迭代变量将由 `From` 或 `Aggregate` 子句指定的迭代变量组成。

### <a name="where-clause"></a>Where 子句

可选。 A [`Where` clause](../../../../visual-basic/language-reference/queries/where-clause.md) specifies a filtering condition for a query. 例如:

 [!code-vb[VbVbalrIntroToLINQ#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#9)]

### <a name="order-by-clause"></a>Order By clause]

|Optional. An [`Order By` clause](../../../../visual-basic/language-reference/queries/order-by-clause.md) specifies the sort order for columns in a query. 例如:

 [!code-vb[VbVbalrIntroToLINQ#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#10)]

### <a name="join-clause"></a>Join 子句

可选。 A [`Join` clause](../../../../visual-basic/language-reference/queries/join-clause.md) combines two collections into a single collection. 例如:

 [!code-vb[VbVbalrIntroToLINQ#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#11)]

### <a name="group-by-clause"></a>Group By 子句

可选。 A [`Group By` clause](../../../../visual-basic/language-reference/queries/group-by-clause.md) groups the elements of a query result. It can be used to apply aggregate functions to each group. 例如:

 [!code-vb[VbVbalrIntroToLINQ#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#12)]

### <a name="group-join-clause"></a>Group Join 子句

可选。 A [`Group Join` clause](../../../../visual-basic/language-reference/queries/group-join-clause.md) combines two collections into a single hierarchical collection. 例如:

 [!code-vb[VbVbalrIntroToLINQ#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#13)]

### <a name="aggregate-clause"></a>Aggregate 子句

Either an [`Aggregate` clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) or a `From` clause is required to begin a query. `Aggregate` 子句向集合应用一个或多个聚合函数。 For example, you can use the `Aggregate` clause to calculate a sum for all the elements returned by a query, as the following example does.

 [!code-vb[VbVbalrIntroToLINQ#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#14)]

还可以使用 `Aggregate` 子句来修改查询。 例如，可以使用 `Aggregate` 子句，对相关查询集合执行计算。 例如:

 [!code-vb[VbVbalrIntroToLINQ#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#15)]

### <a name="let-clause"></a>Let 子句

可选。 A [`Let` clause](../../../../visual-basic/language-reference/queries/let-clause.md) computes a value and assigns it to a new variable in the query. 例如:

 [!code-vb[VbVbalrIntroToLINQ#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#16)]

### <a name="distinct-clause"></a>Distinct 子句

可选。 A `Distinct` clause restricts the values of the current iteration variable to eliminate duplicate values in query results. 例如:

 [!code-vb[VbVbalrIntroToLINQ#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#17)]

### <a name="skip-clause"></a>Skip 子句

可选。 A [`Skip` clause](../../../../visual-basic/language-reference/queries/skip-clause.md) bypasses a specified number of elements in a collection and then returns the remaining elements. 例如:

 [!code-vb[VbVbalrIntroToLINQ#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#18)]

### <a name="skip-while-clause"></a>Skip While 子句

可选。 A [`Skip While` clause](../../../../visual-basic/language-reference/queries/skip-while-clause.md) bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements. 例如:

 [!code-vb[VbVbalrIntroToLINQ#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#19)]

### <a name="take-clause"></a>Take 子句

可选。 A [`Take` clause](../../../../visual-basic/language-reference/queries/take-clause.md) returns a specified number of contiguous elements from the start of a collection. 例如:

 [!code-vb[VbVbalrIntroToLINQ#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#20)]

### <a name="take-while-clause"></a>Take While 子句

可选。 A [`Take While` clause](../../../../visual-basic/language-reference/queries/take-while-clause.md) includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements. 例如:

 [!code-vb[VbVbalrIntroToLINQ#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#21)]
  
## <a name="use-additional-linq-query-features"></a>Use additional LINQ query features  
  
可以通过调用 LINQ 提供的可枚举类型和可查询类型的成员来使用其他 LINQ 查询功能。 可以通过对查询表达式的结果调用特定查询运算符来使用这些附加功能。 For example, the following example uses the <xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType> method to combine the results of two queries into one query result. 它使用 <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> 方法，将查询结果返回为一个泛型列表。
  
 [!code-vb[VbVbalrIntroToLINQ#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#22)]  
  
 For details about additional LINQ capabilities, see [Standard Query Operators Overview](../../concepts/linq/standard-query-operators-overview.md).  
  
## <a name="connect-to-a-database-by-using-linq-to-sql"></a>Connect to a database by using LINQ to SQL  
 In Visual Basic, you identify the SQL Server database objects, such as tables, views, and stored procedures, that you want to access by using a LINQ to SQL file. LINQ to SQL 文件具有 .dbml 扩展名。  
  
 When you have a valid connection to a SQL Server database, you can add a **LINQ to SQL Classes** item template to your project. 此操作将显示对象关系设计器（O/R 设计器）。 The O/R Designer enables you to drag the items that you want to access in your code from the **Server Explorer**/**Database Explorer** onto the designer surface. LINQ to SQL 文件可向项目添加 <xref:System.Data.Linq.DataContext> 对象。 此对象包括你希望访问的表和视图的属性和集合，以及希望调用的存储过程的方法。 保存对 LINQ to SQL (.dbml) 文件所作的更改后，即可通过引用由 O/R 设计器定义的 <xref:System.Data.Linq.DataContext> 对象，在代码中访问这些对象。 项目的 <xref:System.Data.Linq.DataContext> 对象根据 LINQ to SQL 文件的名称进行命名。 例如，名为 Northwind.dbml 的 LINQ to SQL 文件将创建名为 `NorthwindDataContext` 的 <xref:System.Data.Linq.DataContext> 对象。  
  
 For examples with step-by-step instructions, see [How to: Query a Database](how-to-query-a-database-by-using-linq.md) and [How to: Call a Stored Procedure](how-to-call-a-stored-procedure-by-using-linq.md).  
  
## <a name="visual-basic-features-that-support-linq"></a>Visual Basic features that support LINQ  
 Visual Basic includes other notable features that make the use of LINQ simple and reduce the amount of code that you must write to perform LINQ queries. 这些要求包括：  
  
- **Anonymous types**, which enable you to create a new type based on a query result.  
  
- **Implicitly typed variables**, which enable you to defer specifying a type and let the compiler infer the type based on the query result.  
  
- **Extension methods**, which enable you to extend an existing type with your own methods without modifying the type itself.  
  
 For details, see [Visual Basic Features That Support LINQ](../../concepts/linq/features-that-support-linq.md).  
  
## <a name="deferred-and-immediate-query-execution"></a>Deferred and immediate query execution

 执行查询与创建查询相互独立。 创建查询后，通过单独的机制触发其执行。 A query can be executed as soon as it is defined (*immediate execution*), or the definition can be stored and the query can be executed later (*deferred execution*).  
  
 默认情况下，创建查询后，它本身不会立即执行。 而会将查询定义存储在用于引用查询结果的变量中。 当稍后在代码中（如在 `For…Next` 循环中）访问查询结果变量时，将执行该查询。 This process is referred to as *deferred execution*.  
  
 Queries can also be executed when they are defined, which is referred to as *immediate execution*. 可以通过应用需要访问查询结果中单个元素的方法来触发立即执行。 包括聚合函数（如 `Count`、`Sum`、`Average`、`Min` 或 `Max`）可产生此结果。 For more information about aggregate functions, see [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md).  
  
 使用 `ToList` 或 `ToArray` 方法也会强制立即执行。 当你希望立即执行查询并缓存查询结果时，这将很有用。 For more information about these methods, see [Converting Data Types](../../concepts/linq/converting-data-types.md).  
  
 For more information about query execution, see [Writing Your First LINQ Query](../../concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="xml-in-visual-basic"></a>Visual Basic 中的 XML  
 The XML features in Visual Basic include XML literals and XML axis properties, which enable you easily to create, access, query, and modify XML in your code. XML 文本可用于在代码中直接编写 XML。 Visual Basic 编译器将 XML 视为第一类数据对象。  
  
 下面的代码示例演示了如何创建 XML 元素、访问其子元素和属性，以及使用 LINQ 查询该元素的内容。  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 For more information, see [XML](../xml/index.md).  
  
## <a name="related-resources"></a>相关资源  
  
|主题|描述|  
|---|---|  
|[XML](../../language-features/xml/index.md)|Describes the XML features in Visual Basic that can be queried and that enable you to include XML as first-class data objects in your Visual Basic code.|  
|[查询](../../../language-reference/queries/index.md)|Provides reference information about the query clauses that are available in Visual Basic.|  
|[LINQ（语言集成查询）](../../concepts/linq/index.md)|包括常规信息、编程指南和 LINQ 示例。|  
|[LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)|包括常规信息、编程指南和 LINQ to SQL 示例。|  
|[LINQ to Objects](../../concepts/linq/linq-to-objects.md)|包括常规信息、编程指南和 LINQ to Objects 示例。|  
|[LINQ to ADO.NET（门户网站页）](../../concepts/linq/linq-to-adonet-portal-page.md)|Includes links to general information, programming guidance, and samples for LINQ to ADO.NET.|  
|[LINQ to XML](../../concepts/linq/linq-to-xml.md)|包括常规信息、编程指南和 LINQ to XML 示例。|  
  
## <a name="how-to-and-walkthrough-topics"></a>How to and walkthrough topics
 [如何：查询数据库](how-to-query-a-database-by-using-linq.md)  
  
 [如何：调用存储过程](how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [如何：修改数据库中的数据](how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [如何：使用联接合并数据](how-to-combine-data-with-linq-by-using-joins.md)  
  
 [如何：对查询结果进行排序](how-to-sort-query-results-by-using-linq.md)  
  
 [如何：筛选查询结果](how-to-filter-query-results-by-using-linq.md)  
  
 [如何：对数据进行计数、求和与求平均值计算](how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [如何：查找查询结果中的最小值或最大值](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [如何：分配存储过程以便执行更新、插入和删除操作（O/R 设计器）](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
  
## <a name="featured-book-chapters"></a>Featured book chapters  
 [Chapter 17: LINQ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652502(v=orm.10)) in [Programming Visual Basic 2008](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652504(v=orm.10))  
  
## <a name="see-also"></a>请参阅

- [LINQ（语言集成查询）](../../concepts/linq/index.md)
- [Visual Basic 中的 LINQ to XML 概述](../../language-features/xml/overview-of-linq-to-xml.md)
- [LINQ to DataSet 概述](../../../../framework/data/adonet/linq-to-dataset-overview.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Visual Studio 中的 LINQ to SQL 工具](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [DataContext 方法（O/R 设计器）](/visualstudio/data-tools/datacontext-methods-o-r-designer)
