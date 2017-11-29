---
title: "如何：限定 XML 元素和 XML 属性名"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- qualifying XML names
- qualifying XML elements
- XML namespaces, qualifying elements and names in
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 22ec3703331c43cd3b244ee3a5ce2e48d30314e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-qualify-xml-element-and-xml-attribute-names"></a><span data-ttu-id="e9fb3-102">如何：限定 XML 元素和 XML 属性名</span><span class="sxs-lookup"><span data-stu-id="e9fb3-102">How to: Qualify XML Element and XML Attribute Names</span></span>
[<span data-ttu-id="e9fb3-103">代码示例</span><span class="sxs-lookup"><span data-stu-id="e9fb3-103">Code Example</span></span>](#cpconworkingwithxmlnamespacesanchor1)  
  
 <span data-ttu-id="e9fb3-104"><xref:System.Xml.Serialization.XmlSerializerNamespaces> 类的实例所包含的 XML 命名空间必须符合万维网联合会 (www.w3.org) 规范“XML 中的命名空间”(Namespaces in XML)。</span><span class="sxs-lookup"><span data-stu-id="e9fb3-104">XML namespaces contained by instances of the <xref:System.Xml.Serialization.XmlSerializerNamespaces> class must conform to the World Wide Web Consortium (www.w3.org) specification called "Namespaces in XML."</span></span>  
  
 <span data-ttu-id="e9fb3-105">XML 命名空间提供了一种方法，用来限定 XML 文档中 XML 元素和 XML 特性的名称。</span><span class="sxs-lookup"><span data-stu-id="e9fb3-105">XML namespaces provide a method for qualifying the names of XML elements and XML attributes in XML documents.</span></span> <span data-ttu-id="e9fb3-106">限定名由前缀和本地名称组成，两者之间用冒号分隔。</span><span class="sxs-lookup"><span data-stu-id="e9fb3-106">A qualified name consists of a prefix and a local name, separated by a colon.</span></span> <span data-ttu-id="e9fb3-107">前缀仅用作占位符；它将映射到用于指定命名空间的 URI。</span><span class="sxs-lookup"><span data-stu-id="e9fb3-107">The prefix functions only as a placeholder; it is mapped to a URI that specifies a namespace.</span></span> <span data-ttu-id="e9fb3-108">统一管理的 URI 命名空间和本地名称的组合能够产生保证为全局唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="e9fb3-108">The combination of the universally managed URI namespace and the local name produces a name that is guaranteed to be universally unique.</span></span>  
  
 <span data-ttu-id="e9fb3-109">通过创建 `XmlSerializerNamespaces` 的实例，并向对象中添加命名空间对，可以指定在 XML 文档中使用的前缀。</span><span class="sxs-lookup"><span data-stu-id="e9fb3-109">By creating an instance of `XmlSerializerNamespaces` and adding the namespace pairs to the object, you can specify the prefixes used in an XML document.</span></span>  
  
### <a name="to-create-qualified-names-in-an-xml-document"></a><span data-ttu-id="e9fb3-110">在 XML 文档中创建限定名称</span><span class="sxs-lookup"><span data-stu-id="e9fb3-110">To create qualified names in an XML document</span></span>  
  
1.  <span data-ttu-id="e9fb3-111">创建 `XmlSerializerNamespaces` 类的一个实例。</span><span class="sxs-lookup"><span data-stu-id="e9fb3-111">Create an instance of the `XmlSerializerNamespaces` class.</span></span>  
  
2.  <span data-ttu-id="e9fb3-112">将所有的前缀和命名空间对添加至 `XmlSerializerNamespaces`。</span><span class="sxs-lookup"><span data-stu-id="e9fb3-112">Add all prefixes and namespace pairs to the `XmlSerializerNamespaces`.</span></span>  
  
3.  <span data-ttu-id="e9fb3-113">对每个由 `System.Xml.Serialization` 序列化为 XML 文档的成员或类应用相应的 <xref:System.Xml.Serialization.XmlSerializer> 特性。</span><span class="sxs-lookup"><span data-stu-id="e9fb3-113">Apply the appropriate `System.Xml.Serialization` attribute to each member or class that the <xref:System.Xml.Serialization.XmlSerializer> is to serialize into an XML document.</span></span>  
  
     <span data-ttu-id="e9fb3-114">可用的特性包括：<xref:System.Xml.Serialization.XmlAnyElementAttribute>、<xref:System.Xml.Serialization.XmlArrayAttribute>、<xref:System.Xml.Serialization.XmlArrayItemAttribute>、<xref:System.Xml.Serialization.XmlAttributeAttribute>、<xref:System.Xml.Serialization.XmlElementAttribute>、<xref:System.Xml.Serialization.XmlRootAttribute> 和 <xref:System.Xml.Serialization.XmlTypeAttribute>。</span><span class="sxs-lookup"><span data-stu-id="e9fb3-114">The available attributes are: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute>, and <xref:System.Xml.Serialization.XmlTypeAttribute>.</span></span>  
  
4.  <span data-ttu-id="e9fb3-115">将每个属性 (Attribute) 的 `Namespace` 属性 (Property) 设置为 `XmlSerializerNamespaces` 的命名空间值之一。</span><span class="sxs-lookup"><span data-stu-id="e9fb3-115">Set the `Namespace` property of each attribute to one of the namespace values from the `XmlSerializerNamespaces`.</span></span>  
  
5.  <span data-ttu-id="e9fb3-116">将 `XmlSerializerNamespaces` 传递到 `Serialize` 的 `XmlSerializer` 方法。</span><span class="sxs-lookup"><span data-stu-id="e9fb3-116">Pass the `XmlSerializerNamespaces` to the `Serialize` method of the `XmlSerializer`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9fb3-117">示例</span><span class="sxs-lookup"><span data-stu-id="e9fb3-117">Example</span></span>  
 <span data-ttu-id="e9fb3-118">下面的示例创建一个 `XmlSerializerNamespaces`，并向对象添加两个前缀和命名空间对。</span><span class="sxs-lookup"><span data-stu-id="e9fb3-118">The following example creates an `XmlSerializerNamespaces`, and adds two prefix and namespace pairs to the object.</span></span> <span data-ttu-id="e9fb3-119">该代码创建了用来序列化 `XmlSerializer` 类实例的 `Books`，</span><span class="sxs-lookup"><span data-stu-id="e9fb3-119">The code creates an `XmlSerializer` that is used to serialize an instance of the `Books` class.</span></span> <span data-ttu-id="e9fb3-120">并通过 `Serialize` 调用 `XmlSerializerNamespaces` 方法，使 XML 可以包含带前缀的命名空间。</span><span class="sxs-lookup"><span data-stu-id="e9fb3-120">The code calls the `Serialize` method with the `XmlSerializerNamespaces`, allowing the XML to contain prefixed namespaces.</span></span>  
  
```vb  
Option Explicit   
public class Price  
{  
    [XmlAttribute(Namespace = "http://www.cpandl.com")]  
    public string currency;  
    [XmlElement(Namespace = "http://www.cohowinery.com")]  
    public decimal price;  
}  
  
Option Strict  
  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Serialization  
  
Public Class Run  
  
    Public Shared Sub Main()  
        Dim test As New Run()  
        test.SerializeObject("XmlNamespaces.xml")  
    End Sub 'Main  
  
    Public Sub SerializeObject(filename As String)  
        Dim mySerializer As New XmlSerializer(GetType(Books))  
        ' Writing a file requires a TextWriter.  
        Dim myWriter As New StreamWriter(filename)  
  
        ' Creates an XmlSerializerNamespaces and adds two  
        ' prefix-namespace pairs.   
        Dim myNamespaces As New XmlSerializerNamespaces()  
        myNamespaces.Add("books", "http://www.cpandl.com")  
        myNamespaces.Add("money", "http://www.cohowinery.com")  
  
        ' Creates a Book.  
        Dim myBook As New Book()  
        myBook.TITLE = "A Book Title"  
        Dim myPrice As New Price()  
        myPrice.price = CDec(9.95)  
        myPrice.currency = "US Dollar"  
        myBook.PRICE = myPrice  
        Dim myBooks As New Books()  
        myBooks.Book = myBook  
        mySerializer.Serialize(myWriter, myBooks, myNamespaces)  
        myWriter.Close()  
    End Sub  
End Class  
  
Public Class Books  
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _  
    Public Book As Book  
End Class 'Books  
  
<XmlType([Namespace] := "http://www.cpandl.com")> _  
Public Class Book  
  
    <XmlElement([Namespace] := "http://www.cpandl.com")> _  
    Public TITLE As String  
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _  
    Public PRICE As Price  
End Class  
  
Public Class Price  
    <XmlAttribute([Namespace] := "http://www.cpandl.com")> _  
    Public currency As String  
    Public <XmlElement([Namespace] := "http://www.cohowinery.com")> _  
        price As Decimal  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Serialization;  
  
public class Run  
{  
    public static void Main()  
    {  
        Run test = new Run();  
        test.SerializeObject("XmlNamespaces.xml");  
    }  
    public void SerializeObject(string filename)  
    {  
        XmlSerializer mySerializer = new XmlSerializer(typeof(Books));  
        // Writing a file requires a TextWriter.  
        TextWriter myWriter = new StreamWriter(filename);  
  
        // Creates an XmlSerializerNamespaces and adds two  
        // prefix-namespace pairs.  
        XmlSerializerNamespaces myNamespaces =   
        new XmlSerializerNamespaces();  
        myNamespaces.Add("books", "http://www.cpandl.com");  
        myNamespaces.Add("money", "http://www.cohowinery.com");  
  
        // Creates a Book.  
        Book myBook = new Book();  
        myBook.TITLE = "A Book Title";  
        Price myPrice = new Price();  
        myPrice.price = (decimal) 9.95;  
        myPrice.currency = "US Dollar";  
        myBook.PRICE = myPrice;  
        Books myBooks = new Books();  
        myBooks.Book = myBook;  
        mySerializer.Serialize(myWriter,myBooks,myNamespaces);  
        myWriter.Close();  
    }  
}  
  
public class Books  
{  
    [XmlElement(Namespace = "http://www.cohowinery.com")]  
    public Book Book;  
}  
  
[XmlType(Namespace ="http://www.cpandl.com")]  
public class Book  
{  
    [XmlElement(Namespace = "http://www.cpandl.com")]  
    public string TITLE;  
    [XmlElement(Namespace ="http://www.cohowinery.com")]  
    public Price PRICE;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9fb3-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9fb3-121">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSerializer>  
 [<span data-ttu-id="e9fb3-122">XML 架构定义工具和 XML 序列化</span><span class="sxs-lookup"><span data-stu-id="e9fb3-122">The XML Schema Definition Tool and XML Serialization</span></span>](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)  
 [<span data-ttu-id="e9fb3-123">XML 序列化简介</span><span class="sxs-lookup"><span data-stu-id="e9fb3-123">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="e9fb3-124">XmlSerializer 类</span><span class="sxs-lookup"><span data-stu-id="e9fb3-124">XmlSerializer Class</span></span>](xref:System.Xml.Serialization.XmlSerializer)  
 [<span data-ttu-id="e9fb3-125">用来控制 XML 序列化的属性</span><span class="sxs-lookup"><span data-stu-id="e9fb3-125">Attributes That Control XML Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-xml-serialization.md)  
 [<span data-ttu-id="e9fb3-126">如何：指定 XML 流的替代元素名称</span><span class="sxs-lookup"><span data-stu-id="e9fb3-126">How to: Specify an Alternate Element Name for an XML Stream</span></span>](../../../docs/standard/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
 [<span data-ttu-id="e9fb3-127">如何：序列化对象</span><span class="sxs-lookup"><span data-stu-id="e9fb3-127">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 [<span data-ttu-id="e9fb3-128">如何：反序列化对象</span><span class="sxs-lookup"><span data-stu-id="e9fb3-128">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
