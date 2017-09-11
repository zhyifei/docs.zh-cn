---
title: "XDocument 类概述 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 45cb7e71-196a-47da-bfe9-7a5589db1eed
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3f51808a64d51fb354159df1a7323ad2fc26eedc
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="xdocument-class-overview-visual-basic"></a><span data-ttu-id="83883-102">XDocument 类概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83883-102">XDocument Class Overview (Visual Basic)</span></span>
<span data-ttu-id="83883-103">本主题介绍了<xref:System.Xml.Linq.XDocument>类。</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="83883-103">This topic introduces the <xref:System.Xml.Linq.XDocument> class.</span></span>  
  
## <a name="overview-of-the-xdocument-class"></a><span data-ttu-id="83883-104">XDocument 类概述</span><span class="sxs-lookup"><span data-stu-id="83883-104">Overview of the XDocument class</span></span>  
 <span data-ttu-id="83883-105"><xref:System.Xml.Linq.XDocument>类包含有效的 XML 文档所需的信息。</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="83883-105">The <xref:System.Xml.Linq.XDocument> class contains the information necessary for a valid XML document.</span></span> <span data-ttu-id="83883-106">其中包括 XML 声明、处理指令和注释。</span><span class="sxs-lookup"><span data-stu-id="83883-106">This includes an XML declaration, processing instructions, and comments.</span></span>  
  
 <span data-ttu-id="83883-107">请注意，您只需创建<xref:System.Xml.Linq.XDocument>对象，如果您需要的特定功能，提供的<xref:System.Xml.Linq.XDocument>类。</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="83883-107">Note that you only have to create <xref:System.Xml.Linq.XDocument> objects if you require the specific functionality provided by the <xref:System.Xml.Linq.XDocument> class.</span></span> <span data-ttu-id="83883-108">在许多情况下，您可以直接使用<xref:System.Xml.Linq.XElement>。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="83883-108">In many circumstances, you can work directly with <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="83883-109">直接使用<xref:System.Xml.Linq.XElement>是更简单的编程模型。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="83883-109">Working directly with <xref:System.Xml.Linq.XElement> is a simpler programming model.</span></span>  
  
 <span data-ttu-id="83883-110"><xref:System.Xml.Linq.XDocument>派生自<xref:System.Xml.Linq.XContainer>。</xref:System.Xml.Linq.XContainer></xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="83883-110"><xref:System.Xml.Linq.XDocument> derives from <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="83883-111">因此，它可以包含子节点。</span><span class="sxs-lookup"><span data-stu-id="83883-111">Therefore, it can contain child nodes.</span></span> <span data-ttu-id="83883-112">但是，<xref:System.Xml.Linq.XDocument>对象只能有一个子<xref:System.Xml.Linq.XElement>节点。</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="83883-112">However, <xref:System.Xml.Linq.XDocument> objects can have only one child <xref:System.Xml.Linq.XElement> node.</span></span> <span data-ttu-id="83883-113">这反映了 XML 标准，即在 XML 文档中只能有一个根元素。</span><span class="sxs-lookup"><span data-stu-id="83883-113">This reflects the XML standard that there can be only one root element in an XML document.</span></span>  
  
## <a name="components-of-xdocument"></a><span data-ttu-id="83883-114">Xdocument 的组件</span><span class="sxs-lookup"><span data-stu-id="83883-114">Components of XDocument</span></span>  
 <span data-ttu-id="83883-115"><xref:System.Xml.Linq.XDocument>可以包含下列元素︰</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="83883-115">An <xref:System.Xml.Linq.XDocument> can contain the following elements:</span></span>  
  
-   <span data-ttu-id="83883-116">一个<xref:System.Xml.Linq.XDeclaration>对象。</xref:System.Xml.Linq.XDeclaration></span><span class="sxs-lookup"><span data-stu-id="83883-116">One <xref:System.Xml.Linq.XDeclaration> object.</span></span> <span data-ttu-id="83883-117"><xref:System.Xml.Linq.XDeclaration>使您能够指定 XML 声明的相关部分︰ XML 版本、 文档的编码和 XML 文档是否是独立。</xref:System.Xml.Linq.XDeclaration></span><span class="sxs-lookup"><span data-stu-id="83883-117"><xref:System.Xml.Linq.XDeclaration> enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is stand-alone.</span></span>  
  
-   <span data-ttu-id="83883-118">一个<xref:System.Xml.Linq.XElement>对象。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="83883-118">One <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="83883-119">这是 XML 文档的根节点。</span><span class="sxs-lookup"><span data-stu-id="83883-119">This is the root node of the XML document.</span></span>  
  
-   <span data-ttu-id="83883-120">任意数量的<xref:System.Xml.Linq.XProcessingInstruction>对象。</xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="83883-120">Any number of <xref:System.Xml.Linq.XProcessingInstruction> objects.</span></span> <span data-ttu-id="83883-121">处理指令将信息传递给处理 XML 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="83883-121">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
-   <span data-ttu-id="83883-122">任意数量的<xref:System.Xml.Linq.XComment>对象。</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="83883-122">Any number of <xref:System.Xml.Linq.XComment> objects.</span></span> <span data-ttu-id="83883-123">注释将与根元素同级。</span><span class="sxs-lookup"><span data-stu-id="83883-123">The comments will be siblings to the root element.</span></span> <span data-ttu-id="83883-124"><xref:System.Xml.Linq.XComment>对象不能为在列表中，第一个参数，因为它与 XML 文档以注释开头无效。</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="83883-124">The <xref:System.Xml.Linq.XComment> object cannot be the first argument in the list, because it is not valid for an XML document to start with a comment.</span></span>  
  
-   <span data-ttu-id="83883-125">一个<xref:System.Xml.Linq.XDocumentType>的 dtd。</xref:System.Xml.Linq.XDocumentType></span><span class="sxs-lookup"><span data-stu-id="83883-125">One <xref:System.Xml.Linq.XDocumentType> for the DTD.</span></span>  
  
 <span data-ttu-id="83883-126">当序列化<xref:System.Xml.Linq.XDocument>，即使`XDocument.Declaration`是`null`，输出将具有 XML 声明，前提是编写器已经`Writer.Settings.OmitXmlDeclaration`设置为`false`（默认值）。</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="83883-126">When you serialize an <xref:System.Xml.Linq.XDocument>, even if `XDocument.Declaration` is `null`, the output will have an XML declaration if the writer has `Writer.Settings.OmitXmlDeclaration` set to `false` (the default).</span></span>  
  
 <span data-ttu-id="83883-127">默认情况下，[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 将版本设置为“1.0”，将编码设置为“utf-8”。</span><span class="sxs-lookup"><span data-stu-id="83883-127">By default, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] sets the version to "1.0", and sets the encoding to "utf-8".</span></span>  
  
## <a name="using-xelement-without-xdocument"></a><span data-ttu-id="83883-128">在没有 Xdocument 的情况下使用 XElement</span><span class="sxs-lookup"><span data-stu-id="83883-128">Using XElement without XDocument</span></span>  
 <span data-ttu-id="83883-129">正如前面提到，<xref:System.Xml.Linq.XElement>类是中的主类[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]编程接口。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="83883-129">As previously mentioned, the <xref:System.Xml.Linq.XElement> class is the main class in the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] programming interface.</span></span> <span data-ttu-id="83883-130">在很多情况下，您的应用程序不需要您创建文档。</span><span class="sxs-lookup"><span data-stu-id="83883-130">In many cases, your application will not require that you create a document.</span></span> <span data-ttu-id="83883-131">通过使用<xref:System.Xml.Linq.XElement>类，可以创建 XML 树、 向其中添加其他 XML 树，修改 XML 树中，和保存它。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="83883-131">By using the <xref:System.Xml.Linq.XElement> class, you can create an XML tree, add other XML trees to it, modify the XML tree, and save it.</span></span>  
  
## <a name="using-xdocument"></a><span data-ttu-id="83883-132">使用 XDocument</span><span class="sxs-lookup"><span data-stu-id="83883-132">Using XDocument</span></span>  
 <span data-ttu-id="83883-133">若要构造<xref:System.Xml.Linq.XDocument>，使用函数构造，像您那样来构造<xref:System.Xml.Linq.XElement>对象。</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="83883-133">To construct an <xref:System.Xml.Linq.XDocument>, use functional construction, just like you do to construct <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="83883-134">下面的代码创建<xref:System.Xml.Linq.XDocument>对象及其关联的包含对象。</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="83883-134">The following code creates an <xref:System.Xml.Linq.XDocument> object and its associated contained objects.</span></span>  
  
```vb  
Dim doc As XDocument = <?xml version="1.0" encoding="utf-8"?>  
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
doc.Save("test.xml")  
```  
  
 <span data-ttu-id="83883-135">当你检查文件 test.xml 时, 会得到以下输出：</span><span class="sxs-lookup"><span data-stu-id="83883-135">When you examine the file test.xml, you get the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="83883-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83883-136">See Also</span></span>  
 [<span data-ttu-id="83883-137">LINQ to XML 编程概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83883-137">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
