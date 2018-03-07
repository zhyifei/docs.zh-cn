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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c891736534741d1d3d3edb93d75d9f191c2dd573
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="xmlschemacollection-schema-compilation"></a><span data-ttu-id="6f1a6-102">XmlSchemaCollection 架构编译</span><span class="sxs-lookup"><span data-stu-id="6f1a6-102">XmlSchemaCollection Schema Compilation</span></span>
<span data-ttu-id="6f1a6-103">XmlSchemaCollection 是可用于存储和验证 XML 数据缩减 (XDR) 和 XML 架构定义语言 (XSD) 架构的缓存或库。</span><span class="sxs-lookup"><span data-stu-id="6f1a6-103">The **XmlSchemaCollection** is a cache or library where XML-Data Reduced (XDR) and XML Schema definition language (XSD) schemas can be stored and validated.</span></span> <span data-ttu-id="6f1a6-104">XmlSchemaCollection 在内存中缓存架构，而不是通过文件或 URL 访问架构，从而提升了性能。</span><span class="sxs-lookup"><span data-stu-id="6f1a6-104">**XmlSchemaCollection** improves performance by caching schemas in memory instead of accessing them from a file or URL.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f1a6-105">尽管 XmlSchemaCollection 类存储 XDR 架构和 XML 架构，但任何需要使用或返回 XmlSchema 对象的方法和属性都只支持 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="6f1a6-105">Although the **XmlSchemaCollection** class stores both XDR schemas and XML Schemas, any method and property that takes or returns an **XmlSchema** object supports XML Schemas only.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6f1a6-106">现在，<xref:System.Xml.Schema.XmlSchemaCollection> 类已过时，已由 <xref:System.Xml.Schema.XmlSchemaSet> 类所取代。</span><span class="sxs-lookup"><span data-stu-id="6f1a6-106">The <xref:System.Xml.Schema.XmlSchemaCollection> class is now obsolete and has been replaced with the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span> <span data-ttu-id="6f1a6-107">若要详细了解 <xref:System.Xml.Schema.XmlSchemaSet> 类，请参阅[用于编译架构的 XmlSchemaSet](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)。</span><span class="sxs-lookup"><span data-stu-id="6f1a6-107">For more information about the <xref:System.Xml.Schema.XmlSchemaSet> class see, [XmlSchemaSet for Schema Compilation](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span></span>  
  
## <a name="add-schemas-to-the-collection"></a><span data-ttu-id="6f1a6-108">向集合中添加架构</span><span class="sxs-lookup"><span data-stu-id="6f1a6-108">Add Schemas to the Collection</span></span>  
 <span data-ttu-id="6f1a6-109">架构是使用 XmlSchemaCollection 的 Add 方法在集合中加载，此时架构与命名空间 URI 相关联。</span><span class="sxs-lookup"><span data-stu-id="6f1a6-109">Schemas are loaded to the collection using the **Add** method of **XmlSchemaCollection**, at which time the schema is associated with a namespace URI.</span></span> <span data-ttu-id="6f1a6-110">对于 XML 架构，命名空间 URI 通常是该架构的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="6f1a6-110">For XML Schemas, the namespace URI will typically be the target namespace for the schema.</span></span> <span data-ttu-id="6f1a6-111">对于 XDR 架构，命名空间 URI 是在将架构添加到集合时指定的命名空间。</span><span class="sxs-lookup"><span data-stu-id="6f1a6-111">For XDR schemas, the namespace URI is the namespace specified when the schema was added to the collection.</span></span>  
  
## <a name="check-for-a-schema-in-the-collection"></a><span data-ttu-id="6f1a6-112">检查集合中是否存在架构</span><span class="sxs-lookup"><span data-stu-id="6f1a6-112">Check for a Schema in the Collection</span></span>  
 <span data-ttu-id="6f1a6-113">通过使用 Contains 方法，可以检查架构是否位于集合中。</span><span class="sxs-lookup"><span data-stu-id="6f1a6-113">You can check to see if a schema is in the collection by using the **Contains** method.</span></span> <span data-ttu-id="6f1a6-114">Contains 方法需要使用 XmlSchema 对象（仅对于 XML 架构），或表示与架构关联的命名空间 URI 的字符串（对于 XML 架构和 XDR 架构）。</span><span class="sxs-lookup"><span data-stu-id="6f1a6-114">The **Contains** method takes either an **XmlSchema** object (for XML Schemas only) or a string representing the namespace URI associated with the schema (for XML Schemas and XDR schemas).</span></span>  
  
## <a name="retrieve-a-schema-from-the-collection"></a><span data-ttu-id="6f1a6-115">从集合中检索架构</span><span class="sxs-lookup"><span data-stu-id="6f1a6-115">Retrieve a Schema from the Collection</span></span>  
 <span data-ttu-id="6f1a6-116">通过使用 Item 属性，可以从集合中检索架构。</span><span class="sxs-lookup"><span data-stu-id="6f1a6-116">You can retrieve a schema from the collection by using the **Item** property.</span></span> <span data-ttu-id="6f1a6-117">Item 属性需要使用表示与架构关联的命名空间 URI 的字符串（通常是它的目标命名空间），并返回 XmlSchema 对象。</span><span class="sxs-lookup"><span data-stu-id="6f1a6-117">The **Item** property takes a string representing the namespace URI associated with the schema, typically its target namespace, and returns an **XmlSchema** object.</span></span> <span data-ttu-id="6f1a6-118">Item 属性仅适用于 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="6f1a6-118">The **Item** property applies to XML Schemas only.</span></span> <span data-ttu-id="6f1a6-119">对于 XDR 架构，返回值总是空引用，因为它们没有可用的对象模型。</span><span class="sxs-lookup"><span data-stu-id="6f1a6-119">The return value is always a null reference for XDR schemas because they do not have an object model available.</span></span>  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a><span data-ttu-id="6f1a6-120">使用 XmlSchemaCollection 验证 XML 文档</span><span class="sxs-lookup"><span data-stu-id="6f1a6-120">Validate XML Documents Using XmlSchemaCollection</span></span>  
 <span data-ttu-id="6f1a6-121">可以使用 XmlSchemaCollection 验证 XML 实例文档，具体操作是创建 XmlSchemaCollection 对象，将架构添加到集合中，再设置 XmlValidatingReader 的 Schemas 属性，以将创建的 XmlSchemaCollection 分配给 XmlValidatingReader。</span><span class="sxs-lookup"><span data-stu-id="6f1a6-121">You can validate an XML instance document using an **XmlSchemaCollection** by creating the **XmlSchemaCollection** object, adding your schemas to the collection, and setting the **Schemas** property on the **XmlValidatingReader** to assign the created **XmlSchemaCollection** to the **XmlValidatingReader**.</span></span>  
  
### <a name="improved-performance"></a><span data-ttu-id="6f1a6-122">提高的性能</span><span class="sxs-lookup"><span data-stu-id="6f1a6-122">Improved Performance</span></span>  
 <span data-ttu-id="6f1a6-123">若要针对相同架构验证多个文档，建议使用 XmlSchemaCollection，因为它在内存中缓存架构，从而提升了性能。</span><span class="sxs-lookup"><span data-stu-id="6f1a6-123">It is recommended, if you are validating more than one document against the same schema, that you use the **XmlSchemaCollection** because it provides better performance by caching schemas in memory.</span></span>  
  
 <span data-ttu-id="6f1a6-124">下面的代码示例创建 XmlSchemaCollection 对象，将架构添加到集合中，并设置 Schemas 属性。</span><span class="sxs-lookup"><span data-stu-id="6f1a6-124">The following code example creates the **XmlSchemaCollection** object, adds schemas to the collection, and sets the **Schemas** property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6f1a6-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f1a6-125">See Also</span></span>  
 [<span data-ttu-id="6f1a6-126">使用 XmlSchemaCollection 进行 XDR 验证</span><span class="sxs-lookup"><span data-stu-id="6f1a6-126">XDR Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)  
 [<span data-ttu-id="6f1a6-127">使用 XmlSchemaCollection 进行 XML 架构 (XSD) 验证</span><span class="sxs-lookup"><span data-stu-id="6f1a6-127">XML Schema (XSD) Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
