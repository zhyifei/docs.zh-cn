---
title: "创建 XML 文档"
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
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a0806e34cfbf7c8e0b5ba995ca4876b8d10405e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-creation"></a>创建 XML 文档
有两种创建 XML 文档的方法。 一种方法是创建**XmlDocument**不带任何参数。 另一种方法是创建**XmlDocument**并将其作为参数传递 XmlNameTable。 下面的示例演示如何创建新的空**XmlDocument**不使用任何参数。  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 创建文档后，你可以加载数据从字符串、 流、 URL、 文本读取器，或**XmlReader**派生类使用**加载**方法。 还有另一种负载方法， **LoadXML**方法，从字符串读取 XML。 有关详细信息的各种**负载**方法，请参阅[XML 文档读入 DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md)。  
  
 没有名为的类**XmlNameTable**。 此类是原子化字符串对象的表。 该表使 XML 分析器可以高效地对 XML 文档中所有重复的元素和属性的名称使用相同的字符串对象。 **XmlNameTable**如上所示创建并加载文档时，具有属性和元素名称加载文档时将自动创建。 如果你已有的文档包含名称表，并且这些名称可用于另一个文档，则可以创建新的文档使用**负载**采用的方法**XmlNameTable**作为参数。 当使用此方法创建文档时，它会使用现有**XmlNameTable**包含所有属性和元素已从其他文档加载到它。 它可用于有效地比较元素和属性的名称。 有关详细信息**XmlNameTable**，请参阅[使用 XmlNameTable 比较对象](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md)。 有关参考，请参阅<xref:System.Xml.XmlNameTable>。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
