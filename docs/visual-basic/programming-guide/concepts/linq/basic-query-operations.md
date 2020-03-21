---
title: 基本查询操作
ms.date: 07/20/2015
helpviewer_keywords:
- data sources [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- ordering data [LINQ in Visual Basic]
- projections [LINQ in Visual Basic]
- LINQ [Visual Basic], query operations
- Order By clause [LINQ in Visual Basic]
- joining data [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], basic operations
- selecting data [LINQ in Visual Basic]
- Group By clause [LINQ in Visual Basic]
- grouping data [LINQ in Visual Basic]
- Select clause [LINQ in Visual Basic]
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
ms.openlocfilehash: efae72c65ad67b4a1b157b67dcc4d4d65f31f77b
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266373"
---
# <a name="basic-query-operations-visual-basic"></a>基本查询操作 (Visual Basic)
本主题简要介绍了可视化基础知识中的语言集成查询 （LINQ） 表达式，以及您在查询中执行的一些典型操作类型。 有关详情，请参阅以下主题：  
  
 [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [查询](../../../../visual-basic/language-reference/queries/index.md)  
  
 [演练：用 Visual Basic 编写查询](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>指定数据源（来自）  
 在 LINQ 查询中，第一步是指定要查询的数据源。 因此，`From`查询中的子句始终排在第一位。 查询运算符根据源的类型选择和塑造结果。  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 子`From`句指定数据源`customers`和*范围变量*。 `cust` 范围变量类似于循环迭代变量，只不过在查询表达式中，不会发生实际迭代。 执行查询时（通常通过使用`For Each`循环）时，范围变量充当 对 中每个连续元素的`customers`引用。 由于编译器可以推断 `cust` 的类型，因此无需显式指定它。 有关使用显式键入和未进行显式键入的查询的示例，请参阅[查询操作中的类型关系（可视基本）。](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)  
  
 有关如何在 Visual Basic 中使用`From`子句的详细信息，请参阅[From 子句](../../../../visual-basic/language-reference/queries/from-clause.md)。  
  
## <a name="filtering-data-where"></a>筛选数据（在哪里）  
 最常见的查询操作可能是以布尔表达式的形式应用筛选器。 然后，查询仅返回表达式为 true 的元素。 子`Where`句用于执行筛选。 筛选器指定数据源中要包含在结果序列中的元素。 在下面的示例中，仅包括在伦敦有地址的客户。  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 可以使用逻辑运算符（如 和`And``Or`）在`Where`子句中组合筛选器表达式。 例如，要仅返回来自伦敦且名称为 Devon 的客户，请使用以下代码：  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"
```  
  
 要从伦敦或巴黎返回客户，请使用以下代码：  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"
```  
  
 有关如何在 Visual Basic 中使用`Where`子句的详细信息，请参阅[子句](../../../../visual-basic/language-reference/queries/where-clause.md)的位置 。  
  
## <a name="ordering-data-order-by"></a>订购数据（按订单）  
 将返回的数据按特定顺序排序通常很方便。 子`Order By`句将导致返回序列中的元素在指定的字段或字段上进行排序。 例如，以下查询根据`Name`属性对结果进行排序。 因为`Name`是一个字符串，返回的数据将按字母顺序排序，从 A 到 Z。  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 要对结果进行从 Z 到 A 的逆序排序，请使用 `Order By...Descending` 子句。 默认值为`Ascending`既不`Ascending`指定也不`Descending`指定时。  
  
 有关如何在可视化基本版中使用`Order By`子句的详细信息，请参阅[按子句排序](../../../../visual-basic/language-reference/queries/order-by-clause.md)。  
  
## <a name="selecting-data-select"></a>选择数据（选择）  
 子`Select`句指定返回元素的形式和内容。 例如，可以指定结果是包含完整的`Customer`对象、一个`Customer`属性、属性子集、来自各种数据源的属性的组合，还是基于计算的一些新的结果类型。 当 `Select` 子句生成除源元素副本以外的内容时，该操作称为投影**。  
  
 要检索由完整`Customer`对象组成的集合，请选择范围变量本身：  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 如果`Customer`实例是具有许多字段的大型对象，并且要检索的只是名称，则可以选择`cust.Name`，如下例所示。 本地类型推理认识到，这将结果类型从`Customer`对象集合更改为字符串集合。  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 要从数据源中选择多个字段，有两种选择：  
  
- 在子`Select`句中，指定要包含在结果中的字段。 编译器将定义一个匿名类型，该类型以这些字段作为其属性。 有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。  
  
     由于以下示例中返回的元素是匿名类型的实例，因此无法按代码的其他位置引用类型。 类型的编译器指定名称包含在正常 Visual Basic 代码中无效的字符。 在下面的示例中，查询返回的集合中的元素`londonCusts4`是匿名类型的实例  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     -或-  
  
- 定义包含要包含在结果中的特定字段的命名类型，并在`Select`子句中创建和初始化该类型的实例。 仅当必须使用返回结果的集合之外的单个结果，或者您必须在方法调用中将它们作为参数传递时，才使用此选项。 以下示例中的类型`londonCusts5`为 IE无枚（NamePhone）。  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 有关如何在 Visual Basic 中使用`Select`子句的详细信息，请参阅[选择子句](../../../../visual-basic/language-reference/queries/select-clause.md)。  
  
## <a name="joining-data-join-and-group-join"></a>加入数据（加入和组加入）  
 您可以通过多种方式将`From`子句中的多个数据源合并。 例如，以下代码使用两个数据源，并在结果中隐式合并两个数据源的属性。 查询选择姓氏以元音开头的学生。  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> 您可以使用在["如何：创建项目列表](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)"中创建的学生列表运行此代码。  
  
 关键字`Join`等效于 SQL`INNER JOIN`中。 它基于两个集合中元素之间的匹配键值组合两个集合。 查询返回具有匹配键值的全部或部分集合元素。 例如，以下代码复制前一个隐式联接的操作。  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 `Group Join`将集合合并到单个分层集合中，就像`LEFT JOIN`SQL 中的集合一样。 有关详细信息，请参阅[加入子句](../../../../visual-basic/language-reference/queries/join-clause.md)和[组加入子句](../../../../visual-basic/language-reference/queries/group-join-clause.md)。  
  
## <a name="grouping-data-group-by"></a>分组数据（分组）  
 您可以根据元素的`Group By`一个或多个字段添加子句来对查询结果中的元素进行分组。 例如，以下代码按班级年份对学生进行分组。  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 如果使用"[如何创建：创建项目列表"](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)中创建的学生列表运行此代码，则语句中的`For Each`输出为：  
  
 年： 初级  
  
 塔克， 迈克尔  
  
 加西亚， 雨果  
  
 加西亚， 黛布拉  
  
 塔克， 兰斯  
  
 年份： 高级  
  
 奥梅利琴科， 斯韦特兰娜  
  
 奥萨达， 米奇科  
  
 法库里， 法迪  
  
 冯汉英  
  
 亚当斯， 特里  
  
 年份： 新生  
  
 莫滕森， 斯文  
  
 加西亚， 塞萨尔  
  
 以下代码中显示的变体对班级年数进行排序，然后按姓氏每年对学生进行订单。  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 有关 的详细信息`Group By`，请参阅[按子项分组](../../../../visual-basic/language-reference/queries/group-by-clause.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Collections.Generic.IEnumerable%601>
- [Visual Basic 中的 LINQ 入门](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [查询](../../../../visual-basic/language-reference/queries/index.md)
- [标准查询运算符概述 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Linq](../../../../visual-basic/programming-guide/language-features/linq/index.md)
