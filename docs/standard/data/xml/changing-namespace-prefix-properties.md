---
title: "更改命名空间前缀属性"
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
ms.assetid: d5c87cbe-4d69-429f-aad5-3103c2ca2770
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7ce6e4b705188b9c1d0949703991633e3f450689
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="changing-namespace-prefix-properties"></a>更改命名空间前缀属性
**XmlNode**类允许您更改与给定的节点关联的命名空间前缀。 例如，下面的代码显示所更改元素的前缀。  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "b"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "b";  
Console.WriteLine(doc.InnerXml);  
```  
  
 **输出**  
  
```xml  
<b:test xmlns:a="123" xmlns:b="456" />  
```  
  
 更改节点的前缀不会更改节点的命名空间。 命名空间只能在创建节点时设置。 当保持树时，可能需要在外部保存新的命名空间属性，以满足所设置的前缀的需要。 如果无法创建新的命名空间，则更改此前缀以使节点保留其本地名称和命名空间。 下面的示例显示所添加的命名空间属性。  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<test xmlns='123'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "a"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<test xmlns='123'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "a";  
Console.WriteLine(doc.InnerXml);  
```  
  
 **输出**  
  
```xml  
<a:test xmlns="123" xmlns:a="123" />  
```  
  
 当树已保存到为调用的结果字符串**文档。InnerXml**、`xmlns:a='123'`属性已添加保留的命名空间`test`元素。 以前为 `'123'`，并保持为 `'123'`。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
