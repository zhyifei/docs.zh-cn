---
title: 针对 XPath 用户的 LINQ to XML
ms.date: 07/20/2015
ms.assetid: 0e64911c-a7cc-4c20-b927-ca99078b5656
ms.openlocfilehash: 4d5749e72acc8b051db2180b751051696ae04d57
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345466"
---
# <a name="linq-to-xml-for-xpath-users-visual-basic"></a>LINQ to XML for XPath Users (Visual Basic)

这组主题演示很多 XPath 表达式及其 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 等效表达式。  
  
 所有这些示例都使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 中的 XPath 功能，该功能是通过 <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType> 中的扩展方法实现的。 这些示例既执行 XPath 表达式也执行 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 表达式。 然后，每个示例都对这两种查询的结果进行比较，验证 XPath 表达式与 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 查询的功能等效性。 由于这两种类型的查询都从相同的 XML 树返回节点，因此查询结果的比较是使用引用标识进行的。  
  
## <a name="in-this-section"></a>本节内容  
  
|主题|描述|  
|-----------|-----------------|  
|[XPath 和 LINQ to XML 的比较](../../../../csharp/programming-guide/concepts/linq/comparison-of-xpath-and-linq-to-xml.md)|概述 XPath 和 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 的异同。|  
|[How to: Find a Child Element (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-child-element-xpath-linq-to-xml.md)|将 XPath 子元素轴与 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<xref:System.Xml.Linq.XContainer.Element%2A> 方法进行比较。<br /><br /> 关联的 XPath 表达式为：`"DeliveryNotes"`。|  
|[How to: Find a List of Child Elements (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-list-of-child-elements-xpath-linq-to-xml.md)|将 XPath 子元素轴与 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<xref:System.Xml.Linq.XContainer.Elements%2A> 轴进行比较。<br /><br /> 关联的 XPath 表达式为：`"./*"`|  
|[How to: Find the Root Element (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-root-element-xpath-linq-to-xml.md)|比较如何使用 XPath 和 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 获取根元素。<br /><br /> 关联的 XPath 表达式为：`"/PurchaseOrders"`|  
|[How to: Find Descendant Elements (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-descendant-elements-xpath-linq-to-xml.md)|比较如何使用 XPath 和 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 获取具有特定名称的子代元素。<br /><br /> 关联的 XPath 表达式为：`"//Name"`|  
|[How to: Filter on an Attribute (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-filter-on-an-attribute-xpath-linq-to-xml.md)|比较如何使用 XPath 和 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 获取子代元素，这些子代元素具有指定的名称，并具有一个带指定值的属性。<br /><br /> 关联的 XPath 表达式为：`"./Address[@Type='Shipping']"`|  
|[How to: Find Related Elements (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-related-elements-xpath-linq-to-xml.md)|比较如何使用 XPath 和 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 在由其他元素的值所引用的属性上获取元素选择。<br /><br /> 关联的 XPath 表达式为：`"./Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]"`|  
|[How to: Find Elements in a Namespace (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-elements-in-a-namespace.md)|比较 XPath <xref:System.Xml.XmlNamespaceManager> 类与 <xref:System.Xml.Linq.XName> 类的 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<xref:System.Xml.Linq.XName.Namespace%2A> 属性在处理 XML 命名空间时的用法。<br /><br /> 关联的 XPath 表达式为：`"./aw:*"`|  
|[How to: Find Preceding Siblings (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-preceding-siblings-xpath-linq-to-xml.md)|将 XPath `preceding-sibling` 轴与 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 子 <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> 轴进行比较。<br /><br /> 关联的 XPath 表达式为：`"preceding-sibling::*"`|  
|[How to: Find Descendants of a Child Element (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-descendants-of-a-child-element-xpath-linq-to-xml.md)|比较如何使用 XPath 和 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 获取具有特定名称的子元素的子代元素。<br /><br /> 关联的 XPath 表达式为：`"./Paragraph//Text/text()"`|  
|[How to: Find a Union of Two Location Paths (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-union-of-two-location-paths-xpath.md)|将 XPath 中的联合运算符 <code>&#124;</code> 与 <xref:System.Linq.Enumerable.Concat%2A> 中的 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 标准查询运算符进行比较。<br /><br /> 关联的 XPath 表达式为：<code>"//Category&#124;//Price"</code>|  
|[How to: Find Sibling Nodes (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-sibling-nodes-xpath-linq-to-xml.md)|比较如何使用 XPath 和 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 查找所有具有特定名称的节点同级。<br /><br /> 关联的 XPath 表达式为：`"../Book"`|  
|[How to: Find an Attribute of the Parent (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml.md)|比较如何使用 XPath 和 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 定位到父元素并查找关联的属性。<br /><br /> 关联的 XPath 表达式为：`"../@id"`|  
|[How to: Find Attributes of Siblings with a Specific Name (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-attributes-of-siblings-with-a-specific-name.md)|比较如何使用 XPath 和 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 查找上下文节点的同级的特定属性。<br /><br /> 关联的 XPath 表达式为：`"../Book/@id"`|  
|[How to: Find Elements with a Specific Attribute (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-elements-with-a-specific-attribute.md)|比较如何使用 XPath 和 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 查找所有包含特定属性的元素。<br /><br /> 关联的 XPath 表达式为：`"./*[@Select]"`|  
|[How to: Find Child Elements Based on Position (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-child-elements-based-on-position.md)|比较如何使用 XPath 和 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 根据元素的相对位置查找元素。<br /><br /> 关联的 XPath 表达式为：`"Test[position() >= 2 and position() <= 4]"`|  
|[How to: Find the Immediate Preceding Sibling (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml.md)|比较如何使用 XPath 和 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 查找节点前面紧邻的同级。<br /><br /> 关联的 XPath 表达式为：`"preceding-sibling::*[1]"`|  
  
## <a name="see-also"></a>请参阅

- <xref:System.Xml.XPath?displayProperty=nameWithType>
- [Querying XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
- [使用 XPath 数据模型处理 XML 数据](../../../../standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
