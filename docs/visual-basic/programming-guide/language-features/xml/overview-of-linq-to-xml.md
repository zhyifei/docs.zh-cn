---
title: LINQ to XML 概述
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: 0481a140541a7f45c682c5150bc1c3d647de90bd
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266893"
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Visual Basic 中的 LINQ to XML 概述
Visual Basic[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]通过 XML 文本和 XML 轴属性提供支持。 这使您能够使用熟悉、方便的语法在 Visual Basic 代码中使用 XML。 *XML 文本*使您能够直接在代码中包括 XML。 *XML 轴属性*使您能够访问 XML 文本的子节点、子节点和属性。 有关详细信息，请参阅可视化基础 中的[XML 文本概述](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)和[访问 XML。](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]是一个内存中的XML编程API，专门用于利用语言集成查询 （LINQ）。 尽管可以直接调用 LINQ API，但只有 Visual Basic 才能声明 XML 文本并直接访问 XML 轴属性。  
  
> [!NOTE]
> ASP.NET页中的声明性代码不支持 XML 文本和 XML 轴属性。 要使用 Visual Basic XML 功能，请将代码放在ASP.NET应用程序中的代码背后页中。  
  
 [播放按钮](./media/overview-of-linq-to-xml/play-video-icon-example.gif)有关相关的视频演示，请参阅[如何开始使用 LINQ 到 XML？](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-get-started-with-linq-to-xml)以及如何[使用 LINQ 创建 Excel 电子表格？](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-create-excel-spreadsheets-using-linq-to-xml)
  
## <a name="creating-xml"></a>创建 XML  
 在 Visual Basic 中创建 XML 树有两种方法。 可以直接在代码中声明 XML 文本，也可以使用 LINQ API 创建树。 这两个进程使代码能够反映 XML 树的最终结构。 例如，以下代码示例创建一个 XML 元素：  
  
 [!code-vb[VbXmlSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 有关详细信息，请参阅[在可视化基本 中创建 XML。](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
  
## <a name="accessing-and-navigating-xml"></a>访问和导航 XML  
 Visual Basic 提供了用于访问和导航 XML 结构的 XML 轴属性。 这些属性使您能够通过指定 XML 子元素名称来访问 XML 元素和属性。 或者，您可以显式调用 LINQ 方法来导航和定位元素和属性。 例如，以下代码示例使用 XML 轴属性来引用 XML 元素的属性和子元素。 代码示例使用 LINQ 查询检索子元素并将其输出为 XML 元素，从而有效地执行转换。  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 有关详细信息，请参阅[在可视化基本 中访问 XML。](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
  
## <a name="xml-namespaces"></a>XML 命名空间  
 Visual Basic 使您能够通过使用`Imports`语句将别名指定为全局 XML 命名空间。 下面的示例演示如何使用 语句`Imports`导入 XML 命名空间：  
  
 [!code-vb[VbXMLSamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#1)]  
  
 访问 XML 轴属性并为 XML 文档和元素声明 XML 文本时，可以使用 XML 命名空间别名。  
  
 可以使用<xref:System.Xml.Linq.XNamespace>[GetXml 命名空间运算符](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)检索特定命名空间前缀的对象。  
  
 有关详细信息，请参阅[导入语句 （XML 命名空间）](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)。  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>在 XML 文本中使用 XML 命名空间  
 下面的示例演示如何创建<xref:System.Xml.Linq.XElement>使用全局命名空间`ns`的对象：  
  
 [!code-vb[VbXMLSamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#2)]  
  
 Visual Basic 编译器将包含 XML 命名空间别名的 XML 文本转换为等效代码，这些代码使用 XML 表示法使用 XML`xmlns`命名空间，以及属性。 编译后，上一节示例中的代码生成与以下示例基本相同的可执行代码：  
  
 [!code-vb[VbXMLSamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#3)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>在 XML 轴属性中使用 XML 命名空间  
 在 XML 文本中声明的 XML 命名空间不适用于 XML 轴属性。 但是，全局命名空间可以与 XML 轴属性一起使用。 使用冒号将 XML 命名空间前缀与本地元素名称分开。 下面是一个示例：  
  
 [!code-vb[VbXMLSamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#4)]  
  
## <a name="see-also"></a>另请参阅

- [Xml](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [在 Visual Basic 中创建 XML](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [在 Visual Basic 中访问 XML](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [在 Visual Basic 中操作 XML](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
