---
title: 如何：通过 LINQ 使用联接合并数据 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
ms.openlocfilehash: f0279cc13e938b6f7853ef11fee1ef046f192316
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653450"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a>如何：通过 LINQ 使用联接合并数据 (Visual Basic)
Visual Basic 提供`Join`和`Group Join`查询子句以使您能够合并根据集合之间的常见值的多个集合的内容。 这些值称为*密钥*值。 开发人员熟悉关系数据库概念将识别`Join`作为 INNER JOIN 子句和`Group Join`作为，实际上，LEFT OUTER JOIN 子句。  
  
 本主题中的示例演示几种方法可以通过使用组合数据`Join`和`Group Join`查询子句。  
  
## <a name="create-a-project-and-add-sample-data"></a>创建项目并添加示例数据  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a>若要创建包含示例数据和类型的项目  
  
1.  若要运行本主题中的这些示例，请打开 Visual Studio，并添加新的 Visual Basic 控制台应用程序项目。 双击创建 Visual Basic 的 Module1.vb 文件。  
  
2.  在此主题使用示例`Person`和`Pet`类型和数据从下面的代码示例。 将此代码复制到默认值`Module1`由 Visual Basic 创建的模块。  
  
     [!code-vb[VbLINQHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_1.vb)]  
    [!code-vb[VbLINQHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_2.vb)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a>通过使用联接子句执行内部联接  
 INNER JOIN 将合并两个集合中的数据。 要包含指定的键值与匹配的项。 排除其他集合中没有匹配项的任一集合中的任何项。  
  
 在 Visual Basic 中，LINQ 提供执行内部联接的两个选项： 隐式联接和显式联接。  
  
 隐式联接指定要在中联接的集合`From`子句和标识中的匹配键字段`Where`子句。 Visual Basic 隐式联接两个基于指定的键字段的集合。  
  
 你可以通过使用指定显式联接`Join`子句时你想要特定有关要在联接中使用的键字段。 在这种情况下，`Where`仍可以使用子句来筛选查询结果。  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a>若要通过使用联接子句执行 Inner Join  
  
1.  以下代码添加到`Module1`项目以查看这两个隐式和显式内部联接的示例中的模块。  
  
     [!code-vb[VbLINQHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_3.vb)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a>通过使用 Group Join 子句执行左外部联接  
 LEFT OUTER JOIN 包括所有集合中的项左侧的联接和仅匹配中的联接的右侧集合的值。 从查询结果中排除任何联接的右侧集合中的项左侧集合中没有匹配项。  
  
 `Group Join`子句执行时，实际上，左外部联接。 新增功能通常称为 LEFT OUTER JOIN 和之间的差异`Group Join`子句将返回在于`Group Join`从右侧集合的每个集合中的项左侧的联接子句组结果。 在关系数据库中，左外部联接返回在其中查询中的每个项导致了未分组的结果包含在联接两个集合中的匹配项。 在这种情况下，从联接的左侧集合项的从右侧集合的每个匹配项都重复。 你将看到这种情况下一个过程完成。  
  
 你可以检索的结果`Group Join`通过扩展你的查询以返回某个项的每个分组的查询结果未分组结果的查询。 若要实现此目的，你必须确保您查询在`DefaultIfEmpty`分组的集合的方法。 这可确保到仍查询结果中包含联接的左侧集合中的项即使它们具有从右侧集合没有匹配结果。 可以将代码添加到你的查询以从联接的右侧集合没有匹配值时提供默认结果值。  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a>若要通过使用 Group Join 子句执行左外部联接  
  
1.  以下代码添加到`Module1`项目以查看分组左外部联接和未分组的左外部联接的示例中的模块。  
  
     [!code-vb[VbLINQHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_4.vb)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a>通过使用复合键执行联接  
 你可以使用`And`中的关键字`Join`或`Group Join`子句，以此标识匹配时要使用的多个键字段中被联接集合的值。 `And`关键字指定所有指定的键字段都必须匹配要联接的项。  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a>若要通过使用复合键执行联接  
  
1.  以下代码添加到`Module1`项目若要查看的一种联接，使用复合键的示例中的模块。  
  
     [!code-vb[VbLINQHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_5.vb)]  
  
## <a name="run-the-code"></a>运行代码  
  
#### <a name="to-add-code-to-run-the-examples"></a>若要添加代码以运行示例  
  
1.  替换`Sub Main`中`Module1`替换为以下代码，若要运行本主题中的示例项目中的模块。  
  
     [!code-vb[VbLINQHowTos#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_6.vb)]  
  
2.  按 f5 键以运行这些示例。  
  
## <a name="see-also"></a>请参阅  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Join 子句](../../../../visual-basic/language-reference/queries/join-clause.md)  
 [Group Join 子句](../../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [From 子句](../../../../visual-basic/language-reference/queries/from-clause.md)  
 [Where 子句](../../../../visual-basic/language-reference/queries/where-clause.md)  
 [查询](../../../../visual-basic/language-reference/queries/queries.md)  
 [使用 LINQ 进行数据转换 (C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
