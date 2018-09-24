---
title: 读写 XML 架构
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: b5757c4a-ea59-467e-ac62-be2bfe24eb77
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 241ff40448c3dca2846f9e420dc7df41427dc79d
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2018
ms.locfileid: "46698983"
---
# <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="bd30f-102">读写 XML 架构</span><span class="sxs-lookup"><span data-stu-id="bd30f-102">Reading and Writing XML Schemas</span></span>
<span data-ttu-id="bd30f-103">架构对象模型 (SOM) API 可以用于从文件或其他源读取和写入 XML 架构定义语言 (XSD) 架构并使用 <xref:System.Xml.Schema?displayProperty=nameWithType> 命名空间中的类生成内存中 XML 架构，这些架构映射到万维网联合会 (W3C) XML 架构建议中定义的结构。</span><span class="sxs-lookup"><span data-stu-id="bd30f-103">The Schema Object Model (SOM) API can be used to read and write XML Schema definition language (XSD) schemas from files or other sources and build XML schemas in-memory using the classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that map to the structures defined in the World Wide Web Consortium (W3C) XML Schema Recommendation.</span></span>  
  
## <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="bd30f-104">读写 XML 架构</span><span class="sxs-lookup"><span data-stu-id="bd30f-104">Reading and Writing XML Schemas</span></span>  
 <span data-ttu-id="bd30f-105"><xref:System.Xml.Schema.XmlSchema> 类提供 <xref:System.Xml.Schema.XmlSchema.Read%2A> 和 <xref:System.Xml.Schema.XmlSchema.Write%2A> 方法来读取和写入 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="bd30f-105">The <xref:System.Xml.Schema.XmlSchema> class provides the <xref:System.Xml.Schema.XmlSchema.Read%2A> and <xref:System.Xml.Schema.XmlSchema.Write%2A> methods to read and write XML schemas.</span></span> <span data-ttu-id="bd30f-106"><xref:System.Xml.Schema.XmlSchema.Read%2A> 方法返回表示 XML 架构的 <xref:System.Xml.Schema.XmlSchema> 对象并使用可选的 <xref:System.Xml.Schema.ValidationEventHandler> 作为参数，以处理在读取 XML 架构时遇到的架构验证警告和错误。</span><span class="sxs-lookup"><span data-stu-id="bd30f-106">The <xref:System.Xml.Schema.XmlSchema.Read%2A> method returns an <xref:System.Xml.Schema.XmlSchema> object representing the XML schema and takes an optional <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to handle schema validation warnings and errors encountered while reading an XML schema.</span></span>  
  
 <span data-ttu-id="bd30f-107"><xref:System.Xml.Schema.XmlSchema.Write%2A> 方法将 XML 架构写入 <xref:System.IO.Stream>、<xref:System.IO.TextWriter> 和 <xref:System.Xml.XmlWriter> 对象，并且可以使用可选的 <xref:System.Xml.XmlNamespaceManager> 对象作为参数。</span><span class="sxs-lookup"><span data-stu-id="bd30f-107">The <xref:System.Xml.Schema.XmlSchema.Write%2A> method writes XML schemas to <xref:System.IO.Stream>, <xref:System.IO.TextWriter> and <xref:System.Xml.XmlWriter> objects and can take an optional <xref:System.Xml.XmlNamespaceManager> object as a parameter.</span></span> <span data-ttu-id="bd30f-108"><xref:System.Xml.XmlNamespaceManager> 用于处理在 XML 架构中遇到的命名空间。</span><span class="sxs-lookup"><span data-stu-id="bd30f-108">An <xref:System.Xml.XmlNamespaceManager> is used to handle namespaces encountered in an XML schema.</span></span> <span data-ttu-id="bd30f-109">若要详细了解 <xref:System.Xml.XmlNamespaceManager> 类，请参阅[管理 XML 文档中的命名空间](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md)。</span><span class="sxs-lookup"><span data-stu-id="bd30f-109">For more information about the <xref:System.Xml.XmlNamespaceManager> class, see [Managing Namespaces in an XML Document](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md).</span></span>  
  
 <span data-ttu-id="bd30f-110">以下代码示例说明如何在文件中读取和写入 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="bd30f-110">The following code example illustrates reading and writing XML schemas from and to a file.</span></span> <span data-ttu-id="bd30f-111">代码示例使用 `example.xsd` 文件，使用 <xref:System.Xml.Schema.XmlSchema>`static` 方法将其读入 <xref:System.Xml.Schema.XmlSchema.Read%2A> 对象，然后将文件写入控制台和新的 `new.xsd` 文件。</span><span class="sxs-lookup"><span data-stu-id="bd30f-111">The code example takes the `example.xsd` file, reads it into an <xref:System.Xml.Schema.XmlSchema> object using the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method, and then writes the file to the console and a new `new.xsd` file.</span></span> <span data-ttu-id="bd30f-112">代码示例还将 <xref:System.Xml.Schema.ValidationEventHandler> 作为参数传递给 `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> 方法，以处理在读取 XML 架构时遇到的任何架构验证警告或错误。</span><span class="sxs-lookup"><span data-stu-id="bd30f-112">The code example also provides a <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method to handle any schema validation warnings or errors encountered while reading the XML schema.</span></span> <span data-ttu-id="bd30f-113">如果未指定 <xref:System.Xml.Schema.ValidationEventHandler> (`null`)，则不会报告任何警告或错误。</span><span class="sxs-lookup"><span data-stu-id="bd30f-113">If the <xref:System.Xml.Schema.ValidationEventHandler> is not specified (`null`), no warnings or errors are reported.</span></span>  
  
 [!code-cpp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaReadWriteExample/CPP/XmlSchemaReadWriteExample.cpp#1)]
 [!code-csharp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaReadWriteExample/CS/XmlSchemaReadWriteExample.cs#1)]
 [!code-vb[XmlSchemaReadWriteExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaReadWriteExample/VB/XmlSchemaReadWriteExample.vb#1)]  
  
 <span data-ttu-id="bd30f-114">该示例使用 `example.xsd` 作为输入。</span><span class="sxs-lookup"><span data-stu-id="bd30f-114">The example takes the `example.xsd` as input.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<xs:schema id="play" targetNamespace="http://tempuri.org/play.xsd" elementFormDefault="qualified" xmlns="http://tempuri.org/play.xsd" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name='myShoeSize'>  
        <xs:complexType>  
            <xs:simpleContent>  
                <xs:extension base='xs:decimal'>  
                    <xs:attribute name='sizing' type='xs:string' />  
                </xs:extension>  
            </xs:simpleContent>  
        </xs:complexType>  
    </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bd30f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd30f-115">See also</span></span>

- [<span data-ttu-id="bd30f-116">XML 架构对象模型概述</span><span class="sxs-lookup"><span data-stu-id="bd30f-116">XML Schema Object Model Overview</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)  
- [<span data-ttu-id="bd30f-117">生成 XML 架构</span><span class="sxs-lookup"><span data-stu-id="bd30f-117">Building XML Schemas</span></span>](../../../../docs/standard/data/xml/building-xml-schemas.md)  
- [<span data-ttu-id="bd30f-118">遍历 XML 架构</span><span class="sxs-lookup"><span data-stu-id="bd30f-118">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)  
- [<span data-ttu-id="bd30f-119">编辑 XML 架构</span><span class="sxs-lookup"><span data-stu-id="bd30f-119">Editing XML Schemas</span></span>](../../../../docs/standard/data/xml/editing-xml-schemas.md)  
- [<span data-ttu-id="bd30f-120">包含或导入 XML 架构</span><span class="sxs-lookup"><span data-stu-id="bd30f-120">Including or Importing XML Schemas</span></span>](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)  
- [<span data-ttu-id="bd30f-121">用于编译架构的 XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="bd30f-121">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
- [<span data-ttu-id="bd30f-122">后架构编译信息集</span><span class="sxs-lookup"><span data-stu-id="bd30f-122">Post-Schema Compilation Infoset</span></span>](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)  
- [<span data-ttu-id="bd30f-123">管理 XML 文档中的命名空间</span><span class="sxs-lookup"><span data-stu-id="bd30f-123">Managing Namespaces in an XML Document</span></span>](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md)
