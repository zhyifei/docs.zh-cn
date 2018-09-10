---
title: 使用 XmlSchemaCollection 进行 XML 架构 (XSD) 验证
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: ad0b5717-3d32-41ad-a4d7-072c3e492b82
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c570f812ec06c6ead0d12dc14c33fcdfd1f075c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44204872"
---
# <a name="xml-schema-xsd-validation-with-xmlschemacollection"></a><span data-ttu-id="a727a-102">使用 XmlSchemaCollection 进行 XML 架构 (XSD) 验证</span><span class="sxs-lookup"><span data-stu-id="a727a-102">XML Schema (XSD) Validation with XmlSchemaCollection</span></span>
<span data-ttu-id="a727a-103">可以使用 <xref:System.Xml.Schema.XmlSchemaCollection> 根据 XML 架构定义语言 (XSD) 架构对 XML 文档进行验证。</span><span class="sxs-lookup"><span data-stu-id="a727a-103">You can use the <xref:System.Xml.Schema.XmlSchemaCollection> to validate an XML document against XML Schema definition language (XSD) schemas.</span></span> <span data-ttu-id="a727a-104"><xref:System.Xml.Schema.XmlSchemaCollection> 在集合中存储架构，因此每当验证发生时不必将该架构加载到内存中，从而提高了性能。</span><span class="sxs-lookup"><span data-stu-id="a727a-104">The <xref:System.Xml.Schema.XmlSchemaCollection> improves performance by storing schemas in the collection so they are not loaded into memory each time validation occurs.</span></span> <span data-ttu-id="a727a-105">如果架构存在于架构集合中，则将使用 `schemaLocation` 属性在集合中查找该架构。</span><span class="sxs-lookup"><span data-stu-id="a727a-105">If the schema exists in the schema collection, the `schemaLocation` attribute is used to look up the schema in the collection.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a727a-106">现在，<xref:System.Xml.Schema.XmlSchemaCollection> 类已过时，已由 <xref:System.Xml.Schema.XmlSchemaSet> 类所取代。</span><span class="sxs-lookup"><span data-stu-id="a727a-106">The <xref:System.Xml.Schema.XmlSchemaCollection> class is now obsolete and has been replaced with the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span> <span data-ttu-id="a727a-107">若要详细了解 <xref:System.Xml.Schema.XmlSchemaSet> 类，请参阅[用于编译架构的 XmlSchemaSet](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)。</span><span class="sxs-lookup"><span data-stu-id="a727a-107">For more information about the <xref:System.Xml.Schema.XmlSchemaSet> class see, [XmlSchemaSet for Schema Compilation](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span></span>  
  
 <span data-ttu-id="a727a-108">下面的示例显示了数据文件的根元素。</span><span class="sxs-lookup"><span data-stu-id="a727a-108">The following example shows the root element of a data file.</span></span>  
  
```xml  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema"  
    xmlns="urn:bookstore-schema"  
    elementFormDefault="qualified"  
    targetNamespace="urn:bookstore-schema">  
```  
  
 <span data-ttu-id="a727a-109">对于此示例，`targetNamespace` 属性的值为 `urn:bookstore-schema`，与将架构添加到 <xref:System.Xml.Schema.XmlSchemaCollection> 时使用的命名空间相同。</span><span class="sxs-lookup"><span data-stu-id="a727a-109">For this example, the value of the `targetNamespace` attribute is `urn:bookstore-schema`, which is the same namespace that is used when adding the schema to the <xref:System.Xml.Schema.XmlSchemaCollection>.</span></span>  
  
 <span data-ttu-id="a727a-110">下面的代码示例将一个 XML 架构添加到 <xref:System.Xml.Schema.XmlSchemaCollection> 中。</span><span class="sxs-lookup"><span data-stu-id="a727a-110">The following code example adds an XML Schema to the <xref:System.Xml.Schema.XmlSchemaCollection>.</span></span>  
  
```vb  
Dim xsc As New XmlSchemaCollection()  
' XML Schema.  
xsc.Add("urn:bookstore-schema", schema)   
reader = New XmlTextReader(filename)  
vreader = New XmlValidatingReader(reader)  
vreader.Schemas.Add(xsc)  
```  
  
```csharp  
XmlSchemaCollection xsc = new XmlSchemaCollection();  
// XML Schema.  
xsc.Add("urn:bookstore-schema", schema);  
reader = new XmlTextReader (filename);  
vreader = new XmlValidatingReader (reader);  
vreader.Schemas.Add(xsc);  
```  
  
 <span data-ttu-id="a727a-111">在 `targetNamespace` 的 `namespaceURI` 方法中添加 <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A> 属性时，通常使用 <xref:System.Xml.Schema.XmlSchemaCollection> 属性。</span><span class="sxs-lookup"><span data-stu-id="a727a-111">The `targetNamespace` attribute is generally used when you add the `namespaceURI` property in the <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A> method for the <xref:System.Xml.Schema.XmlSchemaCollection>.</span></span> <span data-ttu-id="a727a-112">将架构添加到 <xref:System.Xml.Schema.XmlSchemaCollection> 之前，可以指定空引用。</span><span class="sxs-lookup"><span data-stu-id="a727a-112">You can specify a null reference before adding the schema to the <xref:System.Xml.Schema.XmlSchemaCollection>.</span></span> <span data-ttu-id="a727a-113">对于没有命名空间的架构，应该使用空字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="a727a-113">An empty string ("") should be used for schemas without a namespace.</span></span> <span data-ttu-id="a727a-114"><xref:System.Xml.Schema.XmlSchemaCollection> 只能有一个没有命名空间的架构。</span><span class="sxs-lookup"><span data-stu-id="a727a-114">The <xref:System.Xml.Schema.XmlSchemaCollection> can have only one schema without a namespace.</span></span>  
  
 <span data-ttu-id="a727a-115">下面的代码示例将一个 XML 架构 HeadCount.xsd 添加到 <xref:System.Xml.Schema.XmlSchemaCollection> 中并对 HeadCount.xml 进行验证。</span><span class="sxs-lookup"><span data-stu-id="a727a-115">The following code example adds an XML Schema, HeadCount.xsd, to the <xref:System.Xml.Schema.XmlSchemaCollection> and validates HeadCount.xml.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Schema  
  
Namespace ValidationSample  
  
   Class Sample  
  
      Public Shared Sub Main()  
         Dim tr As New XmlTextReader("HeadCount.xml")  
         Dim vr As New XmlValidatingReader(tr)  
  
         vr.Schemas.Add("xsdHeadCount", "HeadCount.xsd")  
         vr.ValidationType = ValidationType.Schema  
         AddHandler vr.ValidationEventHandler, AddressOf ValidationHandler  
  
         While vr.Read()  
         End While  
         Console.WriteLine("Validation finished")  
      End Sub  
      ' Main  
  
      Public Shared Sub ValidationHandler(sender As Object, args As ValidationEventArgs)  
         Console.WriteLine("***Validation error")  
         Console.WriteLine("Severity:{0}", args.Severity)  
         Console.WriteLine("Message:{0}", args.Message)  
      End Sub  
      ' ValidationHandler  
   End Class  
   ' Sample  
End Namespace  
' ValidationSample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Schema;  
  
namespace ValidationSample  
{  
   class Sample  
   {  
      public static void Main()  
      {  
         XmlTextReader tr = new XmlTextReader("HeadCount.xml");  
         XmlValidatingReader vr = new XmlValidatingReader(tr);  
  
         vr.Schemas.Add("xsdHeadCount", "HeadCount.xsd");  
         vr.ValidationType = ValidationType.Schema;  
         vr.ValidationEventHandler += new ValidationEventHandler (ValidationHandler);  
  
         while(vr.Read());  
         Console.WriteLine("Validation finished");  
      }  
  
      public static void ValidationHandler(object sender, ValidationEventArgs args)  
      {  
         Console.WriteLine("***Validation error");  
         Console.WriteLine("\tSeverity:{0}", args.Severity);  
         Console.WriteLine("\tMessage  :{0}", args.Message);  
      }  
   }  
}  
```  
  
 <span data-ttu-id="a727a-116">下面概括了要验证的输入文件 HeadCount.xml 的内容。</span><span class="sxs-lookup"><span data-stu-id="a727a-116">The following outlines the contents of the input file, HeadCount.xml, to be validated.</span></span>  
  
```xml  
<!--Load HeadCount.xsd in SchemaCollection for Validation-->  
<hc:HeadCount xmlns:hc='xsdHeadCount'>  
   <Name>Waldo Pepper</Name>  
   <Name>Red Pepper</Name>  
</hc:HeadCount>  
```  
  
 <span data-ttu-id="a727a-117">下面概括了要作为验证依据的 XML 架构文件 HeadCount.xsd 的内容。</span><span class="sxs-lookup"><span data-stu-id="a727a-117">The following outlines the contents of the XML Schema file, HeadCount.xsd, to be validated against.</span></span>  
  
```xml  
<xs:schema xmlns="xsdHeadCount" targetNamespace="xsdHeadCount" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
   <xs:element name='HeadCount' type="HEADCOUNT"/>  
   <xs:complexType name="HEADCOUNT">  
      <xs:sequence>  
         <xs:element name='Name' type='xs:string' maxOccurs='unbounded'/>  
      </xs:sequence>  
      <xs:attribute name='division' type='xs:int' use='optional' default='8'/>  
   </xs:complexType>  
</xs:schema>  
```  
  
 <span data-ttu-id="a727a-118">下面的代码示例创建一个接受 <xref:System.Xml.XmlValidatingReader> 的 <xref:System.Xml.XmlTextReader>。</span><span class="sxs-lookup"><span data-stu-id="a727a-118">The following code example creates an <xref:System.Xml.XmlValidatingReader> that takes an <xref:System.Xml.XmlTextReader>.</span></span> <span data-ttu-id="a727a-119">根据 XML 架构 sample4.xsd 对输入文件 sample4.xml 进行验证。</span><span class="sxs-lookup"><span data-stu-id="a727a-119">The input file, sample4.xml, is validated against the XML Schema, sample4.xsd.</span></span>  
  
```vb  
Dim tr As New XmlTextReader("sample4.xml")  
Dim vr As New XmlValidatingReader(tr)  
vr.ValidationType = ValidationType.Schema  
vr.Schemas.Add("datatypesTest", "sample4.xsd")  
AddHandler vr.ValidationEventHandler, AddressOf ValidationCallBack  
While vr.Read()  
   Console.WriteLine("NodeType: {0} NodeName: {1}", vr.NodeType, vr.Name)  
End While  
```  
  
```csharp  
XmlTextReader tr = new XmlTextReader("sample4.xml");  
XmlValidatingReader vr = new XmlValidatingReader(tr);  
vr.ValidationType = ValidationType.Schema;  
        vr.Schemas.Add("datatypesTest", "sample4.xsd");  
vr.ValidationEventHandler += new ValidationEventHandler(ValidationCallBack);  
while(vr.Read()) {  
    Console.WriteLine("NodeType: {0} NodeName: {1}", vr.NodeType, vr.Name);  
    }  
```  
  
 <span data-ttu-id="a727a-120">下面概括了要验证的输入文件 sample4.xml 的内容。</span><span class="sxs-lookup"><span data-stu-id="a727a-120">The following outlines the contents of the input file, sample4.xml, to be validated.</span></span>  
  
```xml  
<datatypes xmlns="datatypesTest">  
    <number>  
        <number_1>123</number_1>  
    </number>  
</datatypes>  
```  
  
 <span data-ttu-id="a727a-121">下面概括了作为验证依据的 XML 架构文件 sample4.xsd 的内容。</span><span class="sxs-lookup"><span data-stu-id="a727a-121">The following outlines the contents of the XML Schema file, sample4.xsd, to be validated against.</span></span>  
  
```xml  
<xs:schema   
    xmlns:xs="http://www.w3.org/2001/XMLSchema"   
    xmlns:tns="datatypesTest"   
    targetNamespace="datatypesTest"  
    elementFormDefault="qualified">  
  
<xs:element name = "datatypes">  
  <xs:complexType>  
    <xs:all>  
        <xs:element name="number">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="number_1" type="xs:decimal" maxOccurs="unbounded"/>  
                </xs:sequence>  
            </xs:complexType>  
        </xs:element>  
    </xs:all>  
  </xs:complexType>  
</xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a727a-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="a727a-122">See also</span></span>

- <xref:System.Xml.XmlParserContext>  
- <xref:System.Xml.XmlValidatingReader.ValidationEventHandler?displayProperty=nameWithType>  
- <xref:System.Xml.XmlValidatingReader.Schemas%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="a727a-123">XmlSchemaCollection 架构编译</span><span class="sxs-lookup"><span data-stu-id="a727a-123">XmlSchemaCollection Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemacollection-schema-compilation.md)
