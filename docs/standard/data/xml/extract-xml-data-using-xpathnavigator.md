---
title: 使用 XPathNavigator 提取 XML 数据
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 095b0987-ee4b-4595-a160-da1c956ad576
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d838f3d9f4c9400fbbef0fb24f5275eff2038c49
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45683159"
---
# <a name="extract-xml-data-using-xpathnavigator"></a><span data-ttu-id="a141c-102">使用 XPathNavigator 提取 XML 数据</span><span class="sxs-lookup"><span data-stu-id="a141c-102">Extract XML Data Using XPathNavigator</span></span>
<span data-ttu-id="a141c-103">可以通过多种不同的方式在 Microsoft .NET Framework 中表示 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="a141c-103">There are several different ways to represent an XML document in the Microsoft .NET Framework.</span></span> <span data-ttu-id="a141c-104">包括使用 <xref:System.String>，或通过使用 <xref:System.Xml.XmlReader>、<xref:System.Xml.XmlWriter>、<xref:System.Xml.XmlDocument> 或 <xref:System.Xml.XPath.XPathDocument> 类。</span><span class="sxs-lookup"><span data-stu-id="a141c-104">This includes using a <xref:System.String>, or by using the <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, <xref:System.Xml.XmlDocument>, or <xref:System.Xml.XPath.XPathDocument> classes.</span></span> <span data-ttu-id="a141c-105">为了便于在这些不同的 XML 文档表示形式之间切换，<xref:System.Xml.XPath.XPathNavigator> 类提供了许多方法和属性，用于将 XML 作为 <xref:System.String>, <xref:System.Xml.XmlReader> 对象或 <xref:System.Xml.XmlWriter> 对象提取。</span><span class="sxs-lookup"><span data-stu-id="a141c-105">To facilitate moving between these different representations of an XML document, the <xref:System.Xml.XPath.XPathNavigator> class provides a number of methods and properties for extracting the XML as a <xref:System.String>, <xref:System.Xml.XmlReader> object or <xref:System.Xml.XmlWriter> object.</span></span>  
  
## <a name="convert-an-xpathnavigator-to-a-string"></a><span data-ttu-id="a141c-106">将 XPathNavigator 转换为字符串</span><span class="sxs-lookup"><span data-stu-id="a141c-106">Convert an XPathNavigator to a String</span></span>  
 <span data-ttu-id="a141c-107"><xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> 类的 <xref:System.Xml.XPath.XPathNavigator> 属性用于获取整个 XML 文档的标记或只获取单个节点及其子节点的标记。</span><span class="sxs-lookup"><span data-stu-id="a141c-107">The <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class is used to get the markup of the entire XML document or just the markup of a single node and its child nodes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a141c-108"><xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> 属性只获取节点的子节点的标记。</span><span class="sxs-lookup"><span data-stu-id="a141c-108">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property gets the markup of just the child nodes of a node.</span></span>  
  
 <span data-ttu-id="a141c-109">以下代码示例显示如何将 <xref:System.Xml.XPath.XPathNavigator> 对象中包含的整个 XML 文档以及单个节点及其子节点保存为 <xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="a141c-109">The following code example shows how to save an entire XML document contained in an <xref:System.Xml.XPath.XPathNavigator> object as a <xref:System.String>, as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("input.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Save the entire input.xml document to a string.  
Dim xml As String = navigator.OuterXml  
  
' Now save the Root element and its child nodes to a string.  
navigator.MoveToChild(XPathNodeType.Element)  
Dim root As String = navigator.OuterXml  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Save the entire input.xml document to a string.  
string xml = navigator.OuterXml;  
  
// Now save the Root element and its child nodes to a string.  
navigator.MoveToChild(XPathNodeType.Element);  
string root = navigator.OuterXml;  
```  
  
## <a name="convert-an-xpathnavigator-to-an-xmlreader"></a><span data-ttu-id="a141c-110">将 XPathNavigator 转换为 XmlReader</span><span class="sxs-lookup"><span data-stu-id="a141c-110">Convert an XPathNavigator to an XmlReader</span></span>  
 <span data-ttu-id="a141c-111"><xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> 方法用于将 XML 文档的全部内容或只是单个节点及其子节点流处理到 <xref:System.Xml.XmlReader> 对象。</span><span class="sxs-lookup"><span data-stu-id="a141c-111">The <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> method is used to stream the entire contents of an XML document or just a single node and its child nodes to an <xref:System.Xml.XmlReader> object.</span></span>  
  
 <span data-ttu-id="a141c-112">为当前节点及其子节点创建 <xref:System.Xml.XmlReader> 对象时，<xref:System.Xml.XmlReader> 对象的 <xref:System.Xml.XmlReader.ReadState%2A> 属性设置为 <xref:System.Xml.ReadState.Initial>。</span><span class="sxs-lookup"><span data-stu-id="a141c-112">When the <xref:System.Xml.XmlReader> object is created with the current node and its child nodes, the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.ReadState%2A> property is set to <xref:System.Xml.ReadState.Initial>.</span></span> <span data-ttu-id="a141c-113">当首次调用 <xref:System.Xml.XmlReader> 对象的 <xref:System.Xml.XmlReader.Read%2A> 方法时，<xref:System.Xml.XmlReader> 移动到 <xref:System.Xml.XPath.XPathNavigator> 的当前节点上。</span><span class="sxs-lookup"><span data-stu-id="a141c-113">When the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.Read%2A> method is called for the first time, the <xref:System.Xml.XmlReader> is moved to the current node of the <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="a141c-114">新的 <xref:System.Xml.XmlReader> 对象继续执行读取操作，直到到达 XML 树的结尾为止。</span><span class="sxs-lookup"><span data-stu-id="a141c-114">The new <xref:System.Xml.XmlReader> object continues to read until the end of the XML tree is reached.</span></span> <span data-ttu-id="a141c-115">此时，<xref:System.Xml.XmlReader.Read%2A> 方法返回 `false`，<xref:System.Xml.XmlReader> 对象的 <xref:System.Xml.XmlReader.ReadState%2A> 属性设置为 <xref:System.Xml.ReadState.EndOfFile>。</span><span class="sxs-lookup"><span data-stu-id="a141c-115">At this point, the <xref:System.Xml.XmlReader.Read%2A> method returns `false` and the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.ReadState%2A> property is set to <xref:System.Xml.ReadState.EndOfFile>.</span></span>  
  
 <span data-ttu-id="a141c-116">创建或移动 <xref:System.Xml.XPath.XPathNavigator> 对象时不会更改 <xref:System.Xml.XmlReader> 对象的位置。</span><span class="sxs-lookup"><span data-stu-id="a141c-116">The <xref:System.Xml.XPath.XPathNavigator> object's position is unchanged by the creation or movement of the <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="a141c-117"><xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> 方法只有在位于元素或根节点上时才有效。</span><span class="sxs-lookup"><span data-stu-id="a141c-117">The <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> method is only valid when positioned on an element or root node.</span></span>  
  
 <span data-ttu-id="a141c-118">以下示例显示如何获取包含 <xref:System.Xml.XmlReader> 对象中的整个 XML 文档以及单个节点及其子节点的 <xref:System.Xml.XPath.XPathDocument> 对象。</span><span class="sxs-lookup"><span data-stu-id="a141c-118">The following example shows how to get an <xref:System.Xml.XmlReader> object containing the entire XML document in an <xref:System.Xml.XPath.XPathDocument> object as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Stream the entire XML document to the XmlReader.  
Dim xml As XmlReader = navigator.ReadSubtree()  
  
While xml.Read()  
    Console.WriteLine(xml.ReadInnerXml())  
End While  
  
xml.Close()  
  
' Stream the book element and its child nodes to the XmlReader.  
navigator.MoveToChild("bookstore", "")  
navigator.MoveToChild("book", "")  
  
Dim book As XmlReader = navigator.ReadSubtree()  
  
While book.Read()  
    Console.WriteLine(book.ReadInnerXml())  
End While  
  
book.Close()  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Stream the entire XML document to the XmlReader.  
XmlReader xml = navigator.ReadSubtree();  
  
while (xml.Read())  
{  
    Console.WriteLine(xml.ReadInnerXml());  
}  
  
xml.Close();  
  
// Stream the book element and its child nodes to the XmlReader.  
navigator.MoveToChild("bookstore", "");  
navigator.MoveToChild("book", "");  
  
XmlReader book = navigator.ReadSubtree();  
  
while (book.Read())  
{  
    Console.WriteLine(book.ReadInnerXml());  
}  
  
book.Close();  
```  
  
 <span data-ttu-id="a141c-119">该示例使用 `books.xml` 文件作为输入。</span><span class="sxs-lookup"><span data-stu-id="a141c-119">The example takes the `books.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
## <a name="converting-an-xpathnavigator-to-an-xmlwriter"></a><span data-ttu-id="a141c-120">将 XPathNavigator 转换为 XmlWriter</span><span class="sxs-lookup"><span data-stu-id="a141c-120">Converting an XPathNavigator to an XmlWriter</span></span>  
 <span data-ttu-id="a141c-121"><xref:System.Xml.XPath.XPathNavigator.WriteSubtree%2A> 方法用于将 XML 文档的全部内容或只是单个节点及其子节点流处理到 <xref:System.Xml.XmlWriter> 对象。</span><span class="sxs-lookup"><span data-stu-id="a141c-121">The <xref:System.Xml.XPath.XPathNavigator.WriteSubtree%2A> method is used to stream the entire contents of an XML document or just a single node and its child nodes to an <xref:System.Xml.XmlWriter> object.</span></span>  
  
 <span data-ttu-id="a141c-122">创建 <xref:System.Xml.XPath.XPathNavigator> 对象时不会更改 <xref:System.Xml.XmlWriter> 对象的位置。</span><span class="sxs-lookup"><span data-stu-id="a141c-122">The <xref:System.Xml.XPath.XPathNavigator> object's position is unchanged by the creation of the <xref:System.Xml.XmlWriter> object.</span></span>  
  
 <span data-ttu-id="a141c-123">以下示例显示如何获取包含 <xref:System.Xml.XmlWriter> 对象中的整个 XML 文档以及单个节点及其子节点的 <xref:System.Xml.XPath.XPathDocument> 对象。</span><span class="sxs-lookup"><span data-stu-id="a141c-123">The following example shows how to get an <xref:System.Xml.XmlWriter> object containing the entire XML document in an <xref:System.Xml.XPath.XPathDocument> object as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Stream the entire XML document to the XmlWriter.  
Dim xml As XmlWriter = XmlWriter.Create("newbooks.xml")  
navigator.WriteSubtree(xml)  
xml.Close()  
  
' Stream the book element and its child nodes to the XmlWriter.  
navigator.MoveToChild("bookstore", "")  
navigator.MoveToChild("book", "")  
  
Dim book As XmlWriter = XmlWriter.Create("book.xml")  
navigator.WriteSubtree(book)  
book.Close()  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Stream the entire XML document to the XmlWriter.  
XmlWriter xml = XmlWriter.Create("newbooks.xml");  
navigator.WriteSubtree(xml);  
xml.Close();  
  
// Stream the book element and its child nodes to the XmlWriter.  
navigator.MoveToChild("bookstore", "");  
navigator.MoveToChild("book", "");  
  
XmlWriter book = XmlWriter.Create("book.xml");  
navigator.WriteSubtree(book);  
book.Close();  
```  
  
 <span data-ttu-id="a141c-124">该示例使用本主题前面所示的 `books.xml` 文件作为输入。</span><span class="sxs-lookup"><span data-stu-id="a141c-124">The example takes the `books.xml` file found earlier in this topic as input.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a141c-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="a141c-125">See also</span></span>

- <xref:System.Xml.XmlDocument>  
- <xref:System.Xml.XPath.XPathDocument>  
- <xref:System.Xml.XPath.XPathNavigator>  
- [<span data-ttu-id="a141c-126">使用 XPath 数据模型处理 XML 数据</span><span class="sxs-lookup"><span data-stu-id="a141c-126">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
- [<span data-ttu-id="a141c-127">使用 XPathNavigator 的节点集定位</span><span class="sxs-lookup"><span data-stu-id="a141c-127">Node Set Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)  
- [<span data-ttu-id="a141c-128">使用 XPathNavigator 的属性和命名空间节点定位</span><span class="sxs-lookup"><span data-stu-id="a141c-128">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)  
- [<span data-ttu-id="a141c-129">使用 XPathNavigator 访问强类型 XML 数据</span><span class="sxs-lookup"><span data-stu-id="a141c-129">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
