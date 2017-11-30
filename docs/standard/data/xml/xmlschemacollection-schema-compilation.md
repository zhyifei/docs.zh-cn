---
title: "XmlSchemaCollection 架构编译"
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
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 901c3fdc8fdc80cc7c3bf13170646de857a5e009
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xmlschemacollection-schema-compilation"></a>XmlSchemaCollection 架构编译
**XmlSchemaCollection**是一个缓存或库可以存储和验证 XML 数据简化 (XDR) 和 XML 架构定义语言 (XSD) 架构。 **XmlSchemaCollection**通过缓存内存而不是从文件或 URL 访问中的架构来提高性能。  
  
> [!NOTE]
>  尽管**XmlSchemaCollection**类存储 XDR 架构和 XML 架构，所有方法和属性，可接受或返回**XmlSchema**对象只支持 XML 架构。  
  
> [!IMPORTANT]
>  现在，<xref:System.Xml.Schema.XmlSchemaCollection> 类已过时，已由 <xref:System.Xml.Schema.XmlSchemaSet> 类所取代。 有关详细信息<xref:System.Xml.Schema.XmlSchemaSet>类，请参阅[编译架构的 XmlSchemaSet](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)。  
  
## <a name="add-schemas-to-the-collection"></a>向集合中添加架构  
 架构加载到集合使用**添加**方法**XmlSchemaCollection**，这时架构将与命名空间 URI 相关联。 对于 XML 架构，命名空间 URI 通常是该架构的目标命名空间。 对于 XDR 架构，命名空间 URI 是在将架构添加到集合时指定的命名空间。  
  
## <a name="check-for-a-schema-in-the-collection"></a>检查集合中是否存在架构  
 你可以检查以查看架构是否在集合中使用**Contains**方法。 **Contains**方法接受**XmlSchema** （仅对于 XML 架构） 的对象或一个字符串，表示命名空间 URI （对于 XML 架构和 XDR 架构） 的架构与相关联。  
  
## <a name="retrieve-a-schema-from-the-collection"></a>从集合中检索架构  
 可以通过使用从集合中检索架构**项**属性。 **项**属性采用一个表示命名空间的架构，通常其目标命名空间，与关联的 URI 的字符串并返回**XmlSchema**对象。 **项**属性仅适用于 XML 架构。 对于 XDR 架构，返回值总是空引用，因为它们没有可用的对象模型。  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a>使用 XmlSchemaCollection 验证 XML 文档  
 你可以验证 XML 实例文档使用**XmlSchemaCollection**通过创建**XmlSchemaCollection**对象，将架构添加到集合，然后设置**架构**属性**XmlValidatingReader**分配创建**XmlSchemaCollection**到**XmlValidatingReader**。  
  
### <a name="improved-performance"></a>提高的性能  
 建议，如果您要验证多个文档针对相同的架构，你使用**XmlSchemaCollection**因为它通过缓存在内存中的架构提供更好的性能。  
  
 下面的代码示例创建**XmlSchemaCollection**对象，将架构添加到集合，并设置**架构**属性。  
  
```vb  
Dim tr as XmlTextReader = new XmlTextReader("Books.xml")  
Dim vr as XmlValidatingReader = new XmlValidatingReader(tr)  
Dim xsc as XmlSchemaCollection = new XmlSchemaCollection  
xsc.Add("urn:bookstore-schema", "Books.xsd")  
vr.Schemas.Add(xsc)  
```  
  
```csharp  
XmlTextReader tr = new XmlTextReader("Books.xml");  
XmlValidatingReader vr = new XmlValidatingReader(tr);  
XmlSchemaCollection xsc = new XmlSchemaCollection();  
xsc.Add("urn:bookstore-schema", "Books.xsd");    
vr.Schemas.Add(xsc);  
```  
  
## <a name="see-also"></a>另请参阅  
 [使用 xmlschemacollection 进行 XDR 验证](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)  
 [使用 xmlschemacollection 进行 XML 架构 (XSD) 验证](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
