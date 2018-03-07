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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 99e2f66a1aedafe316ab65ae302113ea553146ed
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="xml-schema-xsd-validation-with-xmlschemaset"></a><span data-ttu-id="fdbc2-102">使用 XmlSchemaSet 进行 XML 架构 (XSD) 验证</span><span class="sxs-lookup"><span data-stu-id="fdbc2-102">XML Schema (XSD) Validation with XmlSchemaSet</span></span>
<span data-ttu-id="fdbc2-103">XML 文档可以根据 <xref:System.Xml.Schema.XmlSchemaSet> 中的 XML 架构定义语言 (XSD) 架构进行验证。</span><span class="sxs-lookup"><span data-stu-id="fdbc2-103">XML documents can be validated against an XML schema definition language (XSD) schema in an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
## <a name="validating-xml-documents"></a><span data-ttu-id="fdbc2-104">验证 XML 文档</span><span class="sxs-lookup"><span data-stu-id="fdbc2-104">Validating XML Documents</span></span>  
 <span data-ttu-id="fdbc2-105">XML 文档通过 <xref:System.Xml.XmlReader.Create%2A> 类的 <xref:System.Xml.XmlReader> 方法进行验证。</span><span class="sxs-lookup"><span data-stu-id="fdbc2-105">XML documents are validated by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class.</span></span> <span data-ttu-id="fdbc2-106">若要验证 XML 文档，请构造一个 <xref:System.Xml.XmlReaderSettings> 对象，其中包含用于验证 XML 文档的 XML 架构定义语言 (XSD) 架构。</span><span class="sxs-lookup"><span data-stu-id="fdbc2-106">To validate an XML document, construct an <xref:System.Xml.XmlReaderSettings> object that contains an XML schema definition language (XSD) schema with which to validate the XML document.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fdbc2-107"><xref:System.Xml.Schema> 命名空间包含扩展方法，以便于在使用 [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) 时轻松针对 XSD 文件验证 XML 树。</span><span class="sxs-lookup"><span data-stu-id="fdbc2-107">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XSD file when using [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span> <span data-ttu-id="fdbc2-108">若要详细了解如何在使用 LINQ to XML 时验证 XML 文档，请参阅[如何：使用 XSD 进行验证](http://msdn.microsoft.com/library/481a97fa-6e96-46f2-8c9a-415555fac33b)。</span><span class="sxs-lookup"><span data-stu-id="fdbc2-108">For more information on validating XML documents with LINQ to XML, see [How to: Validate Using XSD](http://msdn.microsoft.com/library/481a97fa-6e96-46f2-8c9a-415555fac33b).</span></span>  
  
 <span data-ttu-id="fdbc2-109">通过将架构作为参数传递给 <xref:System.Xml.Schema.XmlSchemaSet> 的 <xref:System.Xml.Schema.XmlSchemaSet> 方法，可以将单个架构或一组架构（作为 <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>）添加到 <xref:System.Xml.Schema.XmlSchemaSet>。</span><span class="sxs-lookup"><span data-stu-id="fdbc2-109">An individual schema or a set of schemas (as an <xref:System.Xml.Schema.XmlSchemaSet>) can be added to an <xref:System.Xml.Schema.XmlSchemaSet> by passing either one as a parameter to the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="fdbc2-110">请注意，在验证文档时，文档的目标命名空间必须匹配架构集中架构的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="fdbc2-110">Note that when validating a document the target namespace of the document must match the target namespace of the schema in the schema set.</span></span>  
  
 <span data-ttu-id="fdbc2-111">下面是示例 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="fdbc2-111">The following is an example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples#5](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xml#5)]  
  
 <span data-ttu-id="fdbc2-112">下面是验证示例 XML 文档的架构。</span><span class="sxs-lookup"><span data-stu-id="fdbc2-112">The following is the schema that validates the example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples#6](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xsd#6)]  
  
 <span data-ttu-id="fdbc2-113">在下面的代码示例中，上面的架构添加到 <xref:System.Xml.Schema.XmlSchemaSet> 对象的 <xref:System.Xml.XmlReaderSettings.Schemas%2A><xref:System.Xml.XmlReaderSettings> 属性中。</span><span class="sxs-lookup"><span data-stu-id="fdbc2-113">In the code example that follows, the schema above is added to the <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A> property of the <xref:System.Xml.XmlReaderSettings> object.</span></span> <span data-ttu-id="fdbc2-114"><xref:System.Xml.XmlReaderSettings> 对象作为参数传递给验证上述 XML 文档的 <xref:System.Xml.XmlReader.Create%2A> 对象的 <xref:System.Xml.XmlReader> 方法。</span><span class="sxs-lookup"><span data-stu-id="fdbc2-114">The <xref:System.Xml.XmlReaderSettings> object is passed as a parameter to the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object, which validates the XML document above.</span></span>  
  
 <span data-ttu-id="fdbc2-115"><xref:System.Xml.XmlReaderSettings.ValidationType%2A> 对象的 <xref:System.Xml.XmlReaderSettings> 属性设置为 `Schema`，强制通过 <xref:System.Xml.XmlReader.Create%2A> 对象的 <xref:System.Xml.XmlReader> 方法验证 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="fdbc2-115">The <xref:System.Xml.XmlReaderSettings.ValidationType%2A> property of the <xref:System.Xml.XmlReaderSettings> object is set to `Schema` to enforce validation of the XML document by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="fdbc2-116">将 <xref:System.Xml.Schema.ValidationEventHandler> 添加到 <xref:System.Xml.XmlReaderSettings> 对象以处理 XML 文档和架构验证过程中发现的错误所引发的任何 <xref:System.Xml.Schema.XmlSeverityType.Warning> 或 <xref:System.Xml.Schema.XmlSeverityType.Error> 事件。</span><span class="sxs-lookup"><span data-stu-id="fdbc2-116">A <xref:System.Xml.Schema.ValidationEventHandler> is added to the <xref:System.Xml.XmlReaderSettings> object to handle any <xref:System.Xml.Schema.XmlSeverityType.Warning> or <xref:System.Xml.Schema.XmlSeverityType.Error> events raised by errors found during the validation process of both the XML document and the schema.</span></span>  
  
 [!code-cpp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaSetOverall Example/CPP/xmlschemasetexample.cpp#1)]
 [!code-csharp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaSetOverall Example/CS/xmlschemasetexample.cs#1)]
 [!code-vb[XmlSchemaSetOverall Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaSetOverall Example/VB/xmlschemasetexample.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fdbc2-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdbc2-117">See Also</span></span>  
 [<span data-ttu-id="fdbc2-118">用于编译架构的 XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="fdbc2-118">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 [<span data-ttu-id="fdbc2-119">使用 XML 架构</span><span class="sxs-lookup"><span data-stu-id="fdbc2-119">Working with XML Schemas</span></span>](../../../../docs/standard/data/xml/working-with-xml-schemas.md)
