---
title: "使用 XmlNameTable 的对象比较"
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
ms.assetid: 8d94e041-d340-4ddf-9a2c-d7319e3f4f86
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0cd1a3bad69499b4804299adecabad3a43b5eab1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="object-comparison-using-xmlnametable"></a>使用 XmlNameTable 的对象比较
**XmlDocuments**，创建时，有专门用于该文档创建的名称表。 当 XML 加载到文档，或创建新元素或属性时，属性和元素的名称将放入**XmlNameTable**。 你还可以创建**XmlDocument**使用现有**NameTable**从另一个文档。 当**XmlDocuments**使用采用的构造函数创建**XmlNameTable**参数，该文档具有对节点名称、 命名空间和前缀已存储在访问**XmlNameTable**。 无论如何为名称表加载名称，一旦名称存储在表中，便可以使用对象比较（而不是字符串比较）来快速比较名称。 此外可以将字符串添加到名称表使用<xref:System.Xml.NameTable.Add%2A>。 下面的代码示例显示所创建的名称表以及字符串**MyString**添加到表。 在此之后， **XmlDocument**使用该表中和中的元素和属性名称创建**Myfile.xml**添加到现有的名称表。  
  
```vb  
Dim nt As New NameTable()  
nt.Add("MyString")  
Dim doc As New XmlDocument(nt)  
doc.Load("Myfile.xml")  
```  
  
```csharp  
NameTable nt = new NameTable();  
nt.Add("MyString");  
XmlDocument doc = new XmlDocument(nt);  
doc.Load("Myfile.xml");  
```  
  
 下面的代码示例显示文档的创建，添加到该文档中的两个新元素（同时还将这两个元素添加到文档名称表中）以及针对名称进行的对象比较。  
  
```vb  
Dim doc1 As XmlDocument = imp.CreateDocument()  
Dim node1 As XmlElement = doc.CreateElement("node1")  
Dim doc2 As XmlDocument = imp.CreateDocument()  
Dim node2 As XmlElement = doc.CreateElement("node2")  
if (CType(node1.Name, object) = CType(node2.Name, object))  
```  
  
```csharp  
XmlDocument doc1 = imp.CreateDocument();  
node1 = doc1.CreateElement ("node1");  
XmlDocument doc2 = imp.CreateDocument();  
node2 = doc2.CreateElement ("node1");  
if (((object)node1.Name) == ((object)node2.Name))  
{ ...  
```  
  
 当反复处理同一类型的文档（如电子商务站点的订单文档，该文档符合 XML 架构定义语言 [即 XSD] 或文档类型定义 [即 DTD]）并重复相同的字符串时，通常使用以上在两个文档之间传递名称表的方案。 使用同一名称表可提高性能，因为同一元素名出现在多个文档中。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
