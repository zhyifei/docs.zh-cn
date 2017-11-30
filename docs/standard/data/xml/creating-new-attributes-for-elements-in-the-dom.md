---
title: "为 DOM 中的元素创建新属性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6970ffc38e900c9b47c58c8ae4b81b9551f5589b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a>为 DOM 中的元素创建新属性
创建新属性是不同于创建其他节点类型，因为属性不是节点，但是元素节点的属性和中包含**XmlAttributeCollection**与元素关联。 有多种方法可创建属性并将其附加到元素：  
  
-   获取元素节点并使用**SetAttribute**将属性添加到该元素的属性集合。  
  
-   创建**XmlAttribute**节点使用**CreateAttribute**方法，获取元素节点，然后使用**SetAttributeNode**将节点添加到属性集合的元素。  
  
 下面的示例演示如何将属性添加到元素使用**SetAttribute**方法。  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
public class Sample  
  
  public shared sub Main()  
  
  Dim doc as XmlDocument = new XmlDocument()  
  doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" & _  
              "<title>Pride And Prejudice</title>" & _  
              "</book>")  
  Dim root as XmlElement = doc.DocumentElement  
  
  'Add a new attribute.  
  root.SetAttribute("genre", "urn:samples", "novel")  
  
  Console.WriteLine("Display the modified XML...")  
  Console.WriteLine(doc.InnerXml)  
  
  end sub  
end class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
  public static void Main()  
  {  
    XmlDocument doc = new XmlDocument();  
    doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" +  
                "<title>Pride And Prejudice</title>" +  
                "</book>");  
    XmlElement root = doc.DocumentElement;  
  
    // Add a new attribute.  
    root.SetAttribute("genre", "urn:samples", "novel");  
  
    Console.WriteLine("Display the modified XML...");  
    Console.WriteLine(doc.InnerXml);  
  }  
```  
  
 下面的示例演示一个新属性正在创建使用**CreateAttribute**方法。 然后，它演示添加到的属性集合的属性**簿**元素使用**SetAttributeNode**方法。  
  
 已知下列 XML：  
  
```xml  
<book genre='novel' ISBN='1-861001-57-5'>  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 创建一个新属性并为其提供值：  
  
```vb  
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")  
   attr.Value = "WorldWide Publishing"  
```  
  
```csharp  
XmlAttribute attr = doc.CreateAttribute("publisher");  
attr.Value = "WorldWide Publishing";  
```  
  
 将其附加到此元素：  
  
```vb  
doc.DocumentElement.SetAttributeNode(attr)  
```  
  
```csharp  
doc.DocumentElement.SetAttributeNode(attr);  
```  
  
 **输出**  
  
```xml  
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 完整代码示例，请参阅<xref:System.Xml.XmlDocument.CreateAttribute%2A>。  
  
 你还可以创建**XmlAttribute**节点并使用**InsertBefore**或**InsertAfter**方法将其放在集合中的适当位置。 如果具有相同名称的属性已在现有的属性集合中存在**XmlAttribute**节点删除从集合中的新**XmlAttribute**插入节点。 这将进行相同的方式**SetAttribute**方法。 这些方法作为参数，将现有节点作为执行操作的参考点执行**InsertBefore**和**InsertAfter**。 如果未提供指示插入新节点的默认位置的参考节点**InsertAfter**方法是在集合开头插入新节点。 默认位置**InsertBefore**，如果未不提供任何参考节点，是在集合末尾。  
  
 如果你创建**XmlNamedNodeMap**属性，您可以添加的属性名称使用<xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>。 有关详细信息，请参阅[Namednodemap 和 Nodelist 中的节点集合](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md)。  
  
## <a name="default-attributes"></a>默认属性  
 如果创建一个声明为具有默认属性的元素，则 XML 文档对象模型 (DOM) 创建一个带默认值的新默认属性并将其附加到该元素。 此时还创建默认属性的子节点。  
  
## <a name="attribute-child-nodes"></a>属性子节点  
 属性节点的值成为它的子节点。 有只有两种类型的有效子节点： **XmlText**节点，和**XmlEntityReference**节点。 这些是子节点，也就是说，该方法**FirstChild**和**LastChild**处理它们作为子节点。 当试图移除属性或属性子节点时，属性这种具有子节点的特性很重要。 有关详细信息，请参阅[移除 DOM 中元素节点的属性](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md)。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
