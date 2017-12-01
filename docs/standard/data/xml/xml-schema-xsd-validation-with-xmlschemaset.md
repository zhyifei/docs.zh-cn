---
title: "使用 XmlSchemaSet 进行 XML 架构 (XSD) 验证"
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
- cpp
ms.assetid: 359b10eb-ec05-4cc6-ac96-c2b060afc4de
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a6cf857ccecbdac88453fd1fba6e93d609196b1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xml-schema-xsd-validation-with-xmlschemaset"></a>使用 XmlSchemaSet 进行 XML 架构 (XSD) 验证
XML 文档可以根据 <xref:System.Xml.Schema.XmlSchemaSet> 中的 XML 架构定义语言 (XSD) 架构进行验证。  
  
## <a name="validating-xml-documents"></a>验证 XML 文档  
 XML 文档通过 <xref:System.Xml.XmlReader.Create%2A> 类的 <xref:System.Xml.XmlReader> 方法进行验证。 若要验证 XML 文档，请构造一个 <xref:System.Xml.XmlReaderSettings> 对象，其中包含用于验证 XML 文档的 XML 架构定义语言 (XSD) 架构。  
  
> [!NOTE]
>  <xref:System.Xml.Schema>命名空间包含扩展方法，可以轻松验证针对 XSD 文件的 XML 树时使用[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)。 验证使用 LINQ to XML 的 XML 文档的详细信息，请参阅[如何： 验证使用 XSD](http://msdn.microsoft.com/library/481a97fa-6e96-46f2-8c9a-415555fac33b)。  
  
 通过将架构作为参数传递给 <xref:System.Xml.Schema.XmlSchemaSet> 的 <xref:System.Xml.Schema.XmlSchemaSet> 方法，可以将单个架构或一组架构（作为 <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>）添加到 <xref:System.Xml.Schema.XmlSchemaSet>。 请注意，在验证文档时，文档的目标命名空间必须匹配架构集中架构的目标命名空间。  
  
 下面是示例 XML 文档。  
  
 [!code-xml[XSDInference Examples#5](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xml#5)]  
  
 下面是验证示例 XML 文档的架构。  
  
 [!code-xml[XSDInference Examples#6](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xsd#6)]  
  
 在下面的代码示例中，上面的架构添加到 <xref:System.Xml.Schema.XmlSchemaSet> 对象的 <xref:System.Xml.XmlReaderSettings.Schemas%2A><xref:System.Xml.XmlReaderSettings> 属性中。 <xref:System.Xml.XmlReaderSettings> 对象作为参数传递给验证上述 XML 文档的 <xref:System.Xml.XmlReader.Create%2A> 对象的 <xref:System.Xml.XmlReader> 方法。  
  
 <xref:System.Xml.XmlReaderSettings.ValidationType%2A> 对象的 <xref:System.Xml.XmlReaderSettings> 属性设置为 `Schema`，强制通过 <xref:System.Xml.XmlReader.Create%2A> 对象的 <xref:System.Xml.XmlReader> 方法验证 XML 文档。 将 <xref:System.Xml.Schema.ValidationEventHandler> 添加到 <xref:System.Xml.XmlReaderSettings> 对象以处理 XML 文档和架构验证过程中发现的错误所引发的任何 <xref:System.Xml.Schema.XmlSeverityType.Warning> 或 <xref:System.Xml.Schema.XmlSeverityType.Error> 事件。  
  
 [!code-cpp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaSetOverall Example/CPP/xmlschemasetexample.cpp#1)]
 [!code-csharp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaSetOverall Example/CS/xmlschemasetexample.cs#1)]
 [!code-vb[XmlSchemaSetOverall Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaSetOverall Example/VB/xmlschemasetexample.vb#1)]  
  
## <a name="see-also"></a>另请参阅  
 [编译架构的 XmlSchemaSet](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 [使用 XML 架构](../../../../docs/standard/data/xml/working-with-xml-schemas.md)
