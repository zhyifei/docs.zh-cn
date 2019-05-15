---
title: XDocument 类概述 (C#)
ms.date: 07/20/2015
ms.assetid: 63305603-ab54-49fc-84e4-f76eecc59549
ms.openlocfilehash: 9a2b2e7490116cfd7ff3cff783a4a3a985a39d0a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64595340"
---
# <a name="xdocument-class-overview-c"></a><span data-ttu-id="e6452-102">XDocument 类概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="e6452-102">XDocument Class Overview (C#)</span></span>
<span data-ttu-id="e6452-103">本主题介绍 <xref:System.Xml.Linq.XDocument> 类。</span><span class="sxs-lookup"><span data-stu-id="e6452-103">This topic introduces the <xref:System.Xml.Linq.XDocument> class.</span></span>  
  
## <a name="overview-of-the-xdocument-class"></a><span data-ttu-id="e6452-104">XDocument 类概述</span><span class="sxs-lookup"><span data-stu-id="e6452-104">Overview of the XDocument class</span></span>  
 <span data-ttu-id="e6452-105"><xref:System.Xml.Linq.XDocument> 类包含有效的 XML 文档所需的信息。</span><span class="sxs-lookup"><span data-stu-id="e6452-105">The <xref:System.Xml.Linq.XDocument> class contains the information necessary for a valid XML document.</span></span> <span data-ttu-id="e6452-106">其中包括 XML 声明、处理指令和注释。</span><span class="sxs-lookup"><span data-stu-id="e6452-106">This includes an XML declaration, processing instructions, and comments.</span></span>  
  
 <span data-ttu-id="e6452-107">请注意，如果需要 <xref:System.Xml.Linq.XDocument> 类提供的特定功能，您只需创建 <xref:System.Xml.Linq.XDocument> 对象。</span><span class="sxs-lookup"><span data-stu-id="e6452-107">Note that you only have to create <xref:System.Xml.Linq.XDocument> objects if you require the specific functionality provided by the <xref:System.Xml.Linq.XDocument> class.</span></span> <span data-ttu-id="e6452-108">在很多情况下，可以直接使用 <xref:System.Xml.Linq.XElement>。</span><span class="sxs-lookup"><span data-stu-id="e6452-108">In many circumstances, you can work directly with <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="e6452-109">直接使用 <xref:System.Xml.Linq.XElement> 是一种比较简单的编程模型。</span><span class="sxs-lookup"><span data-stu-id="e6452-109">Working directly with <xref:System.Xml.Linq.XElement> is a simpler programming model.</span></span>  
  
 <span data-ttu-id="e6452-110"><xref:System.Xml.Linq.XDocument> 派生自 <xref:System.Xml.Linq.XContainer>。</span><span class="sxs-lookup"><span data-stu-id="e6452-110"><xref:System.Xml.Linq.XDocument> derives from <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="e6452-111">因此，它可以包含子节点。</span><span class="sxs-lookup"><span data-stu-id="e6452-111">Therefore, it can contain child nodes.</span></span> <span data-ttu-id="e6452-112">但是，<xref:System.Xml.Linq.XDocument> 对象只能有一个子 <xref:System.Xml.Linq.XElement> 节点。</span><span class="sxs-lookup"><span data-stu-id="e6452-112">However, <xref:System.Xml.Linq.XDocument> objects can have only one child <xref:System.Xml.Linq.XElement> node.</span></span> <span data-ttu-id="e6452-113">这反映了 XML 标准，即在 XML 文档中只能有一个根元素。</span><span class="sxs-lookup"><span data-stu-id="e6452-113">This reflects the XML standard that there can be only one root element in an XML document.</span></span>  
  
## <a name="components-of-xdocument"></a><span data-ttu-id="e6452-114">Xdocument 的组件</span><span class="sxs-lookup"><span data-stu-id="e6452-114">Components of XDocument</span></span>  
 <span data-ttu-id="e6452-115"><xref:System.Xml.Linq.XDocument> 可以包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="e6452-115">An <xref:System.Xml.Linq.XDocument> can contain the following elements:</span></span>  
  
- <span data-ttu-id="e6452-116">一个 <xref:System.Xml.Linq.XDeclaration> 对象。</span><span class="sxs-lookup"><span data-stu-id="e6452-116">One <xref:System.Xml.Linq.XDeclaration> object.</span></span> <span data-ttu-id="e6452-117"><xref:System.Xml.Linq.XDeclaration> 使您能够指定 XML 声明的相关部分：XML 版本、文档的编码以及 XML 文档是否是独立的。</span><span class="sxs-lookup"><span data-stu-id="e6452-117"><xref:System.Xml.Linq.XDeclaration> enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is stand-alone.</span></span>  
  
- <span data-ttu-id="e6452-118">一个 <xref:System.Xml.Linq.XElement> 对象。</span><span class="sxs-lookup"><span data-stu-id="e6452-118">One <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="e6452-119">这是 XML 文档的根节点。</span><span class="sxs-lookup"><span data-stu-id="e6452-119">This is the root node of the XML document.</span></span>  
  
- <span data-ttu-id="e6452-120">任意数目的 <xref:System.Xml.Linq.XProcessingInstruction> 对象。</span><span class="sxs-lookup"><span data-stu-id="e6452-120">Any number of <xref:System.Xml.Linq.XProcessingInstruction> objects.</span></span> <span data-ttu-id="e6452-121">处理指令将信息传递给处理 XML 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e6452-121">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
- <span data-ttu-id="e6452-122">任意数目的 <xref:System.Xml.Linq.XComment> 对象。</span><span class="sxs-lookup"><span data-stu-id="e6452-122">Any number of <xref:System.Xml.Linq.XComment> objects.</span></span> <span data-ttu-id="e6452-123">注释将与根元素同级。</span><span class="sxs-lookup"><span data-stu-id="e6452-123">The comments will be siblings to the root element.</span></span> <span data-ttu-id="e6452-124"><xref:System.Xml.Linq.XComment> 对象不能是列表中的第一个参数，因为 XML 文档以注释开头无效。</span><span class="sxs-lookup"><span data-stu-id="e6452-124">The <xref:System.Xml.Linq.XComment> object cannot be the first argument in the list, because it is not valid for an XML document to start with a comment.</span></span>  
  
- <span data-ttu-id="e6452-125">一个用于 DTD 的 <xref:System.Xml.Linq.XDocumentType>。</span><span class="sxs-lookup"><span data-stu-id="e6452-125">One <xref:System.Xml.Linq.XDocumentType> for the DTD.</span></span>  
  
 <span data-ttu-id="e6452-126">序列化 <xref:System.Xml.Linq.XDocument> 时，即使 `XDocument.Declaration` 为 `null`，输出也将具有 XML 声明，前提是编写器已经将 `Writer.Settings.OmitXmlDeclaration` 设置为 `false`（默认值）。</span><span class="sxs-lookup"><span data-stu-id="e6452-126">When you serialize an <xref:System.Xml.Linq.XDocument>, even if `XDocument.Declaration` is `null`, the output will have an XML declaration if the writer has `Writer.Settings.OmitXmlDeclaration` set to `false` (the default).</span></span>  
  
 <span data-ttu-id="e6452-127">默认情况下，[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 将版本设置为“1.0”，将编码设置为“utf-8”。</span><span class="sxs-lookup"><span data-stu-id="e6452-127">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sets the version to "1.0", and sets the encoding to "utf-8".</span></span>  
  
## <a name="using-xelement-without-xdocument"></a><span data-ttu-id="e6452-128">在没有 Xdocument 的情况下使用 XElement</span><span class="sxs-lookup"><span data-stu-id="e6452-128">Using XElement without XDocument</span></span>  
 <span data-ttu-id="e6452-129">如上所述，<xref:System.Xml.Linq.XElement> 类是 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 编程接口中的主类。</span><span class="sxs-lookup"><span data-stu-id="e6452-129">As previously mentioned, the <xref:System.Xml.Linq.XElement> class is the main class in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface.</span></span> <span data-ttu-id="e6452-130">在很多情况下，您的应用程序不需要您创建文档。</span><span class="sxs-lookup"><span data-stu-id="e6452-130">In many cases, your application will not require that you create a document.</span></span> <span data-ttu-id="e6452-131">通过使用 <xref:System.Xml.Linq.XElement> 类，可以创建 XML 树，向它添加其他 XML 树，修改 XML 树并进行保存。</span><span class="sxs-lookup"><span data-stu-id="e6452-131">By using the <xref:System.Xml.Linq.XElement> class, you can create an XML tree, add other XML trees to it, modify the XML tree, and save it.</span></span>  
  
## <a name="using-xdocument"></a><span data-ttu-id="e6452-132">使用 XDocument</span><span class="sxs-lookup"><span data-stu-id="e6452-132">Using XDocument</span></span>  
 <span data-ttu-id="e6452-133">若要构造一个 <xref:System.Xml.Linq.XDocument>，可使用函数构造，正如您构造 <xref:System.Xml.Linq.XElement> 对象那样。</span><span class="sxs-lookup"><span data-stu-id="e6452-133">To construct an <xref:System.Xml.Linq.XDocument>, use functional construction, just like you do to construct <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="e6452-134">下面的代码创建一个 <xref:System.Xml.Linq.XDocument> 对象及其关联的包含对象。</span><span class="sxs-lookup"><span data-stu-id="e6452-134">The following code creates an <xref:System.Xml.Linq.XDocument> object and its associated contained objects.</span></span>  
  
```csharp  
XDocument d = new XDocument(  
    new XComment("This is a comment."),  
    new XProcessingInstruction("xml-stylesheet",  
        "href='mystyle.css' title='Compact' type='text/css'"),  
    new XElement("Pubs",  
        new XElement("Book",  
            new XElement("Title", "Artifacts of Roman Civilization"),  
            new XElement("Author", "Moreno, Jordao")  
        ),  
        new XElement("Book",  
            new XElement("Title", "Midieval Tools and Implements"),  
            new XElement("Author", "Gazit, Inbar")  
        )  
    ),  
    new XComment("This is another comment.")  
);  
d.Declaration = new XDeclaration("1.0", "utf-8", "true");  
Console.WriteLine(d);  
  
d.Save("test.xml");  
```  
  
 <span data-ttu-id="e6452-135">当你检查文件 test.xml 时, 会得到以下输出：</span><span class="sxs-lookup"><span data-stu-id="e6452-135">When you examine the file test.xml, you get the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<!--This is a comment.-->  
<?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>  
<Pubs>  
  <Book>  
    <Title>Artifacts of Roman Civilization</Title>  
    <Author>Moreno, Jordao</Author>  
  </Book>  
  <Book>  
    <Title>Midieval Tools and Implements</Title>  
    <Author>Gazit, Inbar</Author>  
  </Book>  
</Pubs>  
<!--This is another comment.-->  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6452-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6452-136">See also</span></span>

- [<span data-ttu-id="e6452-137">LINQ to XML 编程概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="e6452-137">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
