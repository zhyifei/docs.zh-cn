---
title: 基本查询操作 (Visual Basic)
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
ms.openlocfilehash: 5587a60e97464324659b325e38a18ac25488d30d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644116"
---
# <a name="basic-query-operations-visual-basic"></a>基本查询操作 (Visual Basic)
本主题提供了的简要介绍[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]表达式在 Visual Basic 中，并以一些典型的一种在查询中执行的操作。 有关详细信息，请参阅下列主题：  
  
 [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [查询](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [演练： 在 Visual Basic 中编写查询](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>指定数据源 （从）  
 在[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询，第一步是指定你想要查询的数据源。 因此，`From`在查询中的子句始终最先。 查询运算符选择和调整基于的源的类型的结果。  
  
 [!code-vb[VbLINQBasicOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]  
  
 `From`子句指定数据源， `customers`，和一个*范围变量*， `cust`。 范围变量类似，循环迭代变量，但在查询表达式中，实际上不发生迭代。 执行查询时，通常通过使用`For Each`循环，用作对中的每个后续元素的引用的范围变量`customers`。 由于编译器可以推断 `cust` 的类型，因此无需显式指定它。 有关编写显式超时和没有显式类型的查询的示例，请参阅[查询操作 (Visual Basic 中) 中的类型关系](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)。  
  
 有关如何使用`From`子句在 Visual Basic 中，请参阅[From 子句](../../../../visual-basic/language-reference/queries/from-clause.md)。  
  
## <a name="filtering-data-where"></a>筛选数据 （位置）  
 可能的最常见的查询操作正将应用筛选器的布尔表达式的形式。 该查询然后返回仅对表达式为 true 的元素。 A`Where`子句用于执行筛选。 筛选器指定要生成序列中包含的数据源中的哪些元素。 中的以下示例中，只有这些地址位于伦敦的客户不包括。  
  
 [!code-vb[VbLINQBasicOps#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]  
  
 你可以使用逻辑运算符，如`And`和`Or`组合中的筛选器表达式`Where`子句。 例如，若要返回的客户，只有那些从伦敦，并姓名为 Devon，使用下面的代码：  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 若要返回客户位于伦敦或巴黎，请使用下面的代码：  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 有关如何使用`Where`子句在 Visual Basic 中，请参阅[Where 子句](../../../../visual-basic/language-reference/queries/where-clause.md)。  
  
## <a name="ordering-data-order-by"></a>对数据 (Order By) 进行排序  
 它通常会带来方便返回的数据排序到特定的顺序。 `Order By`子句将使元素中返回的序列上指定的字段或字段排序。 例如，以下查询对基于对结果进行排序`Name`属性。 因为`Name`是一个字符串，返回的数据将从 A 到 Z 的字母顺序，排序。  
  
 [!code-vb[VbLINQBasicOps#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]  
  
 要对结果进行从 Z 到 A 的逆序排序，请使用 `Order By...Descending` 子句。 默认值是`Ascending`时都不`Ascending`也不`Descending`指定。  
  
 有关如何使用`Order By`子句在 Visual Basic 中，请参阅[Order By 子句](../../../../visual-basic/language-reference/queries/order-by-clause.md)。  
  
## <a name="selecting-data-select"></a>选择数据 （选择）  
 `Select`子句可指定窗体和返回元素的内容。 例如，可以指定你的结果将包含的是整个`Customer`对象、 仅一个`Customer`根据计算的属性，属性的子集、 从各种数据源或某些新的结果类型的属性的组合。 当 `Select` 子句生成除源元素副本以外的内容时，该操作称为投影。  
  
 若要检索的集合组成的完整`Customer`对象，选择的范围变量本身：  
  
 [!code-vb[VbLINQBasicOps#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]  
  
 如果`Customer`实例是具有许多字段，大型对象和所有你想要检索是的名称，你可以选择`cust.Name`，下面的示例中所示。 局部类型推理知道这会从集合中更改的结果类型`Customer`对象与字符串的集合。  
  
 [!code-vb[VbLINQBasicOps#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]  
  
 若要从数据源选择多个字段，你有两个选择：  
  
-   在`Select`子句中，指定你想要在结果中包含的字段。 编译器将定义这些字段作为其属性的匿名类型。 有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。  
  
     在下面的示例返回的元素是匿名类型的实例，因为你不能为类型根据名称引用在其他位置中你的代码。 类型的编译器指定名称包含在正常的 Visual Basic 代码中无效的字符。 在下面的示例中中的查询返回的集合中的元素`londonCusts4`是匿名类型的实例  
  
     [!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]  
  
     -或-  
  
-   定义包含你想要包括在结果中，以及创建和初始化中的类型的实例的特定字段的命名的类型`Select`子句。 仅当你需要使用外部顺序返回它们，集合的单个结果，或者是否可以将它们传递作为方法调用中的参数，请使用此选项。 一种`londonCusts5`在下面的示例是 IEnumerable (Of NamePhone)。  
  
     [!code-vb[VbLINQBasicOps#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]  
  
     [!code-vb[VbLINQBasicOps#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]  
  
 有关如何使用`Select`子句在 Visual Basic 中，请参阅[Select 子句](../../../../visual-basic/language-reference/queries/select-clause.md)。  
  
## <a name="joining-data-join-and-group-join"></a>联接数据 （联接和组联接）  
 你可以组合中的多个数据源`From`有几个方面的子句。 例如，下面的代码使用两个数据源，并且隐式将合并来自这两个结果中的属性。 查询选择的学生以元音开头的姓氏和名字。  
  
 [!code-vb[VbLINQBasicOps#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]  
  
> [!NOTE]
>  你可以运行此代码中创建的学生列表[如何： 创建项列表](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)。  
  
 `Join`关键字等效于`INNER JOIN`SQL 中。 它整合了基于匹配键的两个集合中元素之间的两个集合。 该查询返回所有或部分具有匹配键的值的集合元素。 例如，下面的代码复制以前的隐式联接的操作。  
  
 [!code-vb[VbLINQBasicOps#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]  
  
 `Group Join` 将集合合并为单个分层集合，就像`LEFT JOIN`SQL 中。 有关详细信息，请参阅[Join 子句](../../../../visual-basic/language-reference/queries/join-clause.md)和[Group Join 子句](../../../../visual-basic/language-reference/queries/group-join-clause.md)。  
  
## <a name="grouping-data-group-by"></a>对数据进行分组 （通过组）  
 你可以添加`Group By`子句进行分组的元素的一个或多个字段根据查询结果中的元素。 例如，下面的代码按类年分组学生。  
  
 [!code-vb[VbLINQBasicOps#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]  
  
 如果你运行此代码使用在中创建的学生列表[如何： 创建项列表](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)，从输出`For Each`语句是：  
  
 年： 初级  
  
 Tucker Michael  
  
 Garcia Hugo  
  
 Garcia 徐  
  
 Tucker Lance  
  
 年： 高级  
  
 Omelchenko Svetlana  
  
 Osada Michiko  
  
 Fakhouri Fadi  
  
 Feng 汉英  
  
 Terry Adams  
  
 年： 新生  
  
 Mortensen Sven  
  
 Garcia Cesar  
  
 以下代码所示的变体订单类年，而然后按姓氏排序每个年级学生。  
  
 [!code-vb[VbLINQBasicOps#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]  
  
 有关详细信息`Group By`，请参阅[组 By 子句](../../../../visual-basic/language-reference/queries/group-by-clause.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [Visual Basic 中的 LINQ 入门](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [查询](../../../../visual-basic/language-reference/queries/queries.md)  
 [标准查询运算符概述 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
