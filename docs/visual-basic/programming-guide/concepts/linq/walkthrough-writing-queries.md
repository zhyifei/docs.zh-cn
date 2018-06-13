---
title: 在 Visual Basic 中编写查询
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: beb192f6b136455cb1adcb6cf2616578b63fcebf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655871"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a>演练：用 Visual Basic 编写查询
本演练演示如何使用 Visual Basic 语言功能来编写[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]查询表达式。 本演练说明如何在列表中的学生对象创建查询、 如何运行查询，以及如何对其进行修改。 查询将包括对象初始值设定项、 本地类型推断、 和匿名类型的多个功能合并。  
  
 完成此演练后，你将准备好将移到的示例和文档的特定[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]你感兴趣的提供程序。 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 提供程序包括[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]， [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)]，和[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]。  
  
## <a name="create-a-project"></a>创建项目  
  
#### <a name="to-create-a-console-application-project"></a>若要创建控制台应用程序项目  
  
1.  启动 Visual Studio。  
  
2.  在 **“文件”** 菜单上，指向 **“新建”**，然后单击 **“项目”**。  
  
3.  在**已安装的模板**列表中，单击**Visual Basic**。  
  
4.  在项目类型列表中，单击**控制台应用程序**。 在**名称**框中，为项目中，键入一个名称，然后单击**确定**。  
  
     创建一个项目。 默认情况下，它包含对 System.Core.dll 的引用。 此外，**导入命名空间**列表上[引用页上，项目设计器 (Visual Basic 中)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)包括<xref:System.Linq?displayProperty=nameWithType>命名空间。  
  
5.  上[编译页，项目设计器 (Visual Basic 中)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)，确保**Option infer**设置为**上**。  
  
## <a name="add-an-in-memory-data-source"></a>添加一个内存中数据源  
 本演练中的查询的数据源是一份`Student`对象。 每个`Student`对象包含名字、 姓氏、 类年、 和中学生正文学术级别。  
  
#### <a name="to-add-the-data-source"></a>添加数据源  
  
-   定义`Student`类，并创建的类的实例的列表。  
  
    > [!IMPORTANT]
    >  定义所需的代码`Student`类，并创建使用的列表在本演练中提供示例[如何： 创建项列表](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)。 你可以在此处复制，并将其粘贴到你的项目。 新代码将替换出现在创建项目时的代码。  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a>若要将新的学生添加到学生列表  
  
-   请按照中的模式`getStudents`方法将添加的另一个实例`Student`到列表的类。 添加学生将向你介绍对象初始值设定项。 有关详细信息，请参阅[对象初始值设定项： 命名类型和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)。  
  
## <a name="create-a-query"></a>创建查询  
 在执行时，此部分中添加此查询将生成其学术级别将它们放入前 10 个学生的列表。 因为查询选择完整`Student`对象每次查询结果的类型是`IEnumerable(Of Student)`。 但是，查询的类型通常是未指定查询定义中。 相反，编译器使用局部类型推理来确定类型。 有关详细信息，请参阅[本地类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。 查询的范围变量`currentStudent`，用作参考，给每个`Student`源中的实例`students`，提供对中每个对象的属性访问`students`。  
  
#### <a name="to-create-a-simple-query"></a>创建简单查询  
  
1.  查找中的位置`Main`标记，如下所示的项目的方法：  
  
     [!code-vb[VbLINQWalkthrough#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_1.vb)]  
  
     复制下面的代码并将其粘贴中。  
  
     [!code-vb[VbLINQWalkthrough#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_2.vb)]  
  
2.  将鼠标指针停留在`studentQuery`代码来验证编译器分配类型是否为`IEnumerable(Of Student)`。  
  
## <a name="run-the-query"></a>运行查询  
 变量`studentQuery`包含定义的查询，不运行查询的结果。 用于运行查询的典型机制是`For Each`循环。 返回序列中的每个元素进行访问通过循环迭代变量。 有关执行查询的详细信息，请参阅[编写你的第一个 LINQ 查询](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)。  
  
#### <a name="to-run-the-query"></a>若要运行查询  
  
1.  添加以下`For Each`下面你的项目中的查询的循环。  
  
     [!code-vb[VbLINQWalkthrough#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_3.vb)]  
  
2.  将鼠标指针停留在循环控制变量`studentRecord`以查看其数据类型。 一种`studentRecord`将被推断`Student`，这是因为`studentQuery`返回的集合`Student`实例。  
  
3.  生成并通过按 CTRL + F5 运行应用程序。 请注意控制台窗口中的结果。  
  
## <a name="modify-the-query"></a>修改查询  
 很容易地扫描查询结果，如果它们在指定的顺序。 可以对返回基于任何可用字段的序列进行排序。  
  
#### <a name="to-order-the-results"></a>对结果进行排序  
  
1.  添加以下`Order By`之间子句`Where`语句和`Select`语句的查询。 `Order By`子句将字母顺序对结果从 A 到 Z、 到最后一个根据每个学生的名字。  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2.  若要通过最后一个名称，然后按名字排序，请向查询添加这两个字段：  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     你还可以指定`Descending`到顺序从 Z 到 a。  
  
3.  生成并通过按 CTRL + F5 运行应用程序。 请注意控制台窗口中的结果。  
  
#### <a name="to-introduce-a-local-identifier"></a>若要将本地标识符引入  
  
1.  在查询表达式将本地标识符引入此部分中添加代码。 本地标识符将保留中间结果。 在下面的示例中，`name`是保存学生的串联的标识符的名字和姓氏。 为方便起见，可以使用的本地标识符或也可以通过将存储否则可计算多次表达式的结果来提高性能。  
  
     [!code-vb[VbLINQWalkthrough#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_4.vb)]  
  
2.  生成并通过按 CTRL + F5 运行应用程序。 请注意控制台窗口中的结果。  
  
#### <a name="to-project-one-field-in-the-select-clause"></a>投影 Select 子句中的一个字段  
  
1.  将查询添加和`For Each`从此部分以创建一个查询，生成一个序列，其元素与不同的源中的元素的循环。 在以下示例中，源是一套`Student`返回对象，但只有一个成员的每个对象： 其姓氏为 Garcia 学生的名字。 因为`currentStudent.First`是一个字符串，返回的序列的数据类型`studentQuery3`是`IEnumerable(Of String)`，一个字符串序列。 如前面的示例所示的数据分配键入`studentQuery3`留给编译器使用局部类型推理来确定。  
  
     [!code-vb[VbLINQWalkthrough#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_5.vb)]  
  
2.  将鼠标指针停留在`studentQuery3`代码来验证分配的类型是否为`IEnumerable(Of String)`。  
  
3.  生成并通过按 CTRL + F5 运行应用程序。 请注意控制台窗口中的结果。  
  
#### <a name="to-create-an-anonymous-type-in-the-select-clause"></a>若要在 Select 子句中创建一个匿名类型  
  
1.  添加查询中使用的该部分以查看如何匿名类型中的代码。 如果您使用它们在查询中你想要从数据源而不是完整记录返回多个字段 (`currentStudent`前面的示例中的记录) 或单个字段 (`First`在上一部分中)。 而不是定义新命名的类型，包含你想要在结果中包含的字段，指定中的字段`Select`子句和编译器创建一个匿名类型以这些字段作为其属性。 有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。  
  
     下面的示例创建查询返回的名称和其学术级别是介于 1 和 10，顺序学术级别之间的高年级学生的秩。 在此示例中的一种`studentQuery4`必须无法推断，因为`Select`子句将返回一个匿名类型的实例和一个匿名类型有没有可用的名称。  
  
     [!code-vb[VbLINQWalkthrough#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_6.vb)]  
  
2.  生成并通过按 CTRL + F5 运行应用程序。 请注意控制台窗口中的结果。  
  
## <a name="additional-examples"></a>其他示例  
 现在，你已了解基础知识，下面是其他示例来演示灵活的列表以及的幂[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询。 每个示例被前面其用途的简短说明。 鼠标指针停留在每个查询，以查看推断出的类型的查询结果变量。 使用`For Each`循环以产生的结果。  
  
 [!code-vb[VbLINQWalkthrough#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_7.vb)]  
  
## <a name="additional-information"></a>其他信息  
 你熟悉使用查询的基本概念后，你就可以读取的特定类型的文档和示例[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]你感兴趣的提供程序：  
  
 [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)  
  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
  
 [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)  
  
 [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)  
  
## <a name="see-also"></a>请参阅  
 [语言集成查询 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 [Visual Basic 中的 LINQ 入门](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [对象初始值设定项：命名类型和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [查询](../../../../visual-basic/language-reference/queries/queries.md)
