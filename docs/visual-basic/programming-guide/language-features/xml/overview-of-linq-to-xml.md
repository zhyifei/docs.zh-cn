---
title: Visual Basic 中的 LINQ to XML 概述
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: 1ac9c7749cb054857715fd670f1510697c18f0e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Visual Basic 中的 LINQ to XML 概述
Visual Basic 支持[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]通过 XML 文本和 XML 轴属性。 这使你可以为 Visual Basic 代码中使用的 XML 中使用熟悉的、 方便的语法。 *XML 文本*使您能够在你的代码中直接包含 XML。 *XML 轴属性*使您能够访问子节点、 子代节点和属性的 XML 文本。 有关详细信息，请参阅[XML 文本概述](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)和[访问 Visual Basic 中的 XML](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)。  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 内存中 XML 编程 API 专门用于充分利用[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]。 尽管你可以调用[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]Api 直接，但仅 Visual Basic，可声明 XML 文本和直接访问 XML 轴属性。  
  
> [!NOTE]
>  在 ASP.NET 页中的声明性代码中不支持 XML 文本和 XML 轴属性。 若要使用 Visual Basic XML 功能，请将代码放在 ASP.NET 应用程序中的代码隐藏页。  
  
 ![视频链接](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo")相关视频演示，请参阅[如何开始使用 LINQ to XML？](http://go.microsoft.com/fwlink/?LinkId=143034)和[如何创建 Excel 电子表格使用 LINQ to XML？](http://go.microsoft.com/fwlink/?LinkId=143536)。  
  
## <a name="creating-xml"></a>创建 XML  
 有两种方法可以在 Visual Basic 中创建 XML 树。 您可以声明 XML 文本直接在代码中，也可以使用[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]Api 来创建树。 这两个进程都使代码能够反映最终 XML 树的结构。 例如，下面的代码示例创建一个 XML 元素：  
  
 [!code-vb[VbXmlSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]  
  
 有关详细信息，请参阅[在 Visual Basic 中创建 XML](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)。  
  
## <a name="accessing-and-navigating-xml"></a>访问和导航 XML  
 Visual Basic 提供 XML 轴属性，用于访问和导航 XML 结构。 这些属性，可以通过指定的 XML 子元素名称来访问 XML 元素和属性。 或者，你可以明确地调用[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]来导航和查找元素和属性的方法。 例如，下面的代码示例使用 XML 轴属性的属性和子元素的 XML 元素引用。 此代码示例使用[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询以检索子元素，并输出为 XML 元素，从而有效地执行转换。  
  
 [!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]  
  
 有关详细信息，请参阅[访问 Visual Basic 中的 XML](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)。  
  
## <a name="xml-namespaces"></a>XML 命名空间  
 Visual Basic，可通过使用指定为全局 XML 命名空间别名`Imports`语句。 下面的示例演示如何使用`Imports`要导入的 XML 命名空间声明：  
  
 [!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]  
  
 访问 XML 轴属性和声明的 XML 文档和元素的 XML 文本时，你可以使用 XML 命名空间别名。  
  
 你可以检索<xref:System.Xml.Linq.XNamespace>对象使用的特定命名空间前缀[GetXmlNamespace 运算符](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)。  
  
 有关详细信息，请参阅[Imports 语句 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)。  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>在 XML 文本中使用 XML 命名空间  
 下面的示例演示如何创建<xref:System.Xml.Linq.XElement>使用全局命名空间的对象`ns`:  
  
 [!code-vb[VbXMLSamples#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]  
  
 Visual Basic 编译器会将转换到 XML 命名空间中使用的使用的 XML 表示法的等效代码包含 XML 命名空间别名的 XML 文本`xmlns`属性。 在编译时上, 一节的示例中的代码将产生与下面的示例实质上是相同的可执行代码：  
  
 [!code-vb[VbXMLSamples#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>在 XML 轴属性中使用 XML 命名空间  
 XML 文本声明的 XML 命名空间不在 XML 轴属性中使用。 但是，可以与 XML 轴属性一起使用全局命名空间。 使用冒号分隔的 XML 命名空间前缀和本地元素名称。 下面是一个示例：  
  
 [!code-vb[VbXMLSamples#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]  
  
## <a name="see-also"></a>请参阅  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [在 Visual Basic 中创建 XML](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [在 Visual Basic 中访问 XML](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [在 Visual Basic 中操控 XML](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
