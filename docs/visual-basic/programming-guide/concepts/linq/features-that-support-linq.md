---
title: "支持 LINQ 的 Visual Basic 功能"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
caps.latest.revision: "51"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 42465dbb168b7961792aec6b3c2bb7ae8f0a3355
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="visual-basic-features-that-support-linq"></a>支持 LINQ 的 Visual Basic 功能
名称[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]指在 Visual Basic 支持查询语法和其他语言构造直接在语言中的技术。 与[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]，则不需要了解对外部数据源执行查询的新语言。 可以使用 Visual Basic 查询针对关系数据库、 XML 存储区或对象中的数据。 查询功能语言编程到此集成使编译时检查语法错误和类型安全。 此集成还可确保你已经知道你需要知道要在 Visual Basic 中编写丰富、 不同的查询的大部分。  
  
 以下各节描述了足够的详细信息，以便你开始读取的介绍性文档、 代码示例和示例应用程序中支持 LINQ 的语言构造。 您也可以单击链接，以了解如何的语言功能结合使用才能启用语言集成查询的更详细的解释。 启动的好时机是[演练： 在 Visual Basic 中编写查询](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)。  
  
## <a name="query-expressions"></a>查询表达式  
 在 Visual Basic 中的查询表达式可以表示类似于 SQL 或 XQuery 的声明性语法。 在编译时，查询语法将转换为对标准查询运算符扩展方法的 LINQ 提供程序实现的方法调用。 应用程序控件的标准查询运算符在作用域中通过指定适当的命名空间与`Imports`语句。 Visual Basic 查询表达式的语法如下所示：  
  
 [!code-vb[VbLINQVbFeatures#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_1.vb)]  
  
 有关详细信息，请参阅[Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)。  
  
## <a name="implicitly-typed-variables"></a>隐式类型化的变量  
 而不是显式指定类型声明和初始化变量时，你可以启用编译器推导出，分配类型。 这称为*局部类型推理*。  
  
 变量的类型推断强类型，就像你显式指定其类型的变量一样。 局部类型推理仅适用于你正在定义方法主体内的本地变量。 有关详细信息，请参阅[Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)和[本地类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。  
  
 下面的示例阐释了局部类型推理。 若要使用此示例，必须设置`Option Infer`到`On`。  
  
 [!code-vb[VbLINQVbFeatures#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_2.vb)]  
  
 局部类型推理还使可以创建匿名类型，也不能在本部分稍后介绍 LINQ 查询所必需的。  
  
 在以下 LINQ 示例中，会发生类型推理如果`Option Infer`是`On`或`Off`。 如果，则会发生编译时错误`Option Infer`是`Off`和`Option Strict`是`On`。  
  
 [!code-vb[VbLINQVbFeatures#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_3.vb)]  
  
## <a name="object-initializers"></a>对象初始值设定项  
 当您必须创建一个匿名类型来保存查询的结果时，将在查询表达式中使用对象初始值设定项。 它们还可以用于初始化命名外部的类型的查询的对象。 通过使用对象初始值设定项，可以无需显式调用构造函数初始化单个行中的对象。 假设你有一个名为类`Customer`该类具有公共`Name`和`Phone`属性，以及其他属性，可以按照此方式使用对象初始值设定项：  
  
 [!code-vb[VbLINQVbFeatures#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_4.vb)]  
  
 有关详细信息，请参阅[对象初始值设定项： 命名类型和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)。  
  
## <a name="anonymous-types"></a>匿名类型  
 匿名类型提供一种简便方式暂时到你想要在查询结果中包含的元素进行分组的一组属性。 这使你可以在查询中，按任何顺序中，选择可用字段的任意组合，但不定义元素的已命名的数据类型。  
  
 *匿名类型*由编译器动态构造。 类型的名称分配由编译器，并且它可能会更改与每个新的编译。 因此，不能直接使用的名称。 按以下方式初始化匿名类型：  
  
 [!code-vb[VbLINQVbFeatures#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_5.vb)]  
  
 有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。  
  
## <a name="extension-methods"></a>扩展方法  
 扩展方法，可以将方法添加到的数据类型或从定义之外的接口。 此功能使您能够，实际上，将新方法添加到现有类型而实际修改该类型。 标准查询运算符本身就是扩展方法，它们提供一组[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询实现任何类型的功能<xref:System.Collections.Generic.IEnumerable%601>。 到其他扩展<xref:System.Collections.Generic.IEnumerable%601>包括<xref:System.Linq.Enumerable.Count%2A>， <xref:System.Linq.Enumerable.Union%2A>，和<xref:System.Linq.Enumerable.Intersect%2A>。  
  
 下面的扩展方法将添加到打印方法<xref:System.String>类。  
  
 [!code-vb[VbLINQVbFeatures#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_6.vb)]  
  
 默认情况下，调用类似于普通的实例方法的<xref:System.String>:  
  
 [!code-vb[VbLINQVbFeatures#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_7.vb)]  
  
 有关详细信息，请参阅[扩展方法](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
  
## <a name="lambda-expressions"></a>Lambda 表达式  
 Lambda 表达式是没有名称，用于计算并返回单个值的函数。 不同于命名的函数，可以定义并在同一时间执行 lambda 表达式。 下面的示例显示 4。  
  
 [!code-vb[VbLINQVbFeatures#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_8.vb)]  
  
 你可以将 lambda 表达式定义分配给变量的名称，然后使用名称调用该函数。 下面的示例还显示 4。  
  
 [!code-vb[VbLINQVbFeatures#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_9.vb)]  
  
 在[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]，lambda 表达式生成许多标准查询运算符。 编译器创建 lambda 表达式捕获的计算，如基本查询方法中定义`Where`， `Select`， `Order By`， `Take While`，和其他人。  
  
 例如，下面的代码定义学生列表中返回所有高年级学生的查询。  
  
 [!code-vb[VbLINQVbFeatures#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_10.vb)]  
  
 查询定义编译为类似于下面的示例使用两个 lambda 表达式来指定的自变量的代码`Where`和`Select`。  
  
 [!code-vb[VbLINQVbFeatures#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_11.vb)]  
  
 可以使用运行任一版本`For Each`循环：  
  
 [!code-vb[VbLINQVbFeatures#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_12.vb)]  
  
 有关详细信息，请参阅 [Lambda 表达式](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。  
  
## <a name="see-also"></a>另请参阅  
 [语言集成查询 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 [Visual Basic 中的 LINQ 入门](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [LINQ 和字符串 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 [Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
