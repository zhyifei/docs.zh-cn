---
title: XML 的功能转换
ms.date: 07/20/2015
ms.assetid: fdbe5b91-f457-4b4e-a11b-def4bdd77bab
ms.openlocfilehash: 7e029fd562ae3f221a8aaef40f332a1e3fa896eb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353421"
---
# <a name="functional-transformation-of-xml-visual-basic"></a>Functional Transformation of XML (Visual Basic)
本主题讨论用于修改 XML 文档的纯函数转换方法，并将该方法与过程方法进行比较。  
  
## <a name="modifying-an-xml-document"></a>修改 XML 文档  
 对 XML 程序员来说，最常见的任务之一就是将 XML 从一种形状转换为另一种形状。 XML 文档的形状就是文档的结构，包括下列内容：  
  
- 文档所表达的层次结构。  
  
- 元素和属性的名称。  
  
- 元素和属性的数据类型。  
  
 通常，将 XML 从一种形状转换为另一种形状的最有效方法是纯函数转换方法。 在这种方法中，程序员的主要任务是创建一个转换，该转换将应用到整个 XML 文档（或应用到一个或多个严格定义的节点）。 可以说，函数转换最容易进行编码（如果程序员熟悉这种方法），生成的代码最容易维护，并且相比其他方法通常更加简洁。  
  
### <a name="xml-functional-transformational-technologies"></a>XML 函数转换技术  
 Microsoft 提供了两种函数转换技术用于 XML 文档：XSLT 和 LINQ to XML。 在 <xref:System.Xml.Xsl> 托管命名空间和 MSXML 的本机 COM 实现中都支持 XSLT。 尽管 XSLT 是操作 XML 文档的可靠技术，但它要求专门领域的专业知识，即 XSLT 语言和支持它的 API。  
  
 LINQ to XML 提供了必要的工具，使用这些工具可以在 C# 或 Visual Basic 代码中以富于表现力而又强有力的方式编写纯函数转换。 例如，LINQ to XML 文档中的很多示例都使用纯函数方法。 Also, in the [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial, we use LINQ to XML in a functional approach to manipulate information in a Microsoft Word document.  
  
 For a more complete comparison of LINQ to XML with other Microsoft XML technologies, see [LINQ to XML vs. Other XML Technologies](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md).  
  
 如果源文档具有不规则的结构，则推荐使用 XSLT 工具进行以文档为中心的转换。 但是 LINQ to XML 也可以执行以文档为中心的转换。 For more information, see [How to: Use Annotations to Transform LINQ to XML Trees in an XSLT Style (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-use-annotation-trees-to-transform-linq-to-xml-trees-in-an-xslt-style.md).  
  
## <a name="see-also"></a>请参阅

- [Introduction to Pure Functional Transformations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
- [LINQ to XML vs. Other XML Technologies](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md)
