---
title: "XElement 类概述 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 52331fcd-6023-4d19-b423-7b24f2d86ded
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
ms.openlocfilehash: 78a72effa021408943b9248546106c6fd655ac0b
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="xelement-class-overview-visual-basic"></a><span data-ttu-id="f488b-102">XElement 类概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f488b-102">XElement Class Overview (Visual Basic)</span></span>
<span data-ttu-id="f488b-103"><xref:System.Xml.Linq.XElement>类是中的基础类之一[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="f488b-103">The <xref:System.Xml.Linq.XElement> class is one of the fundamental classes in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span> <span data-ttu-id="f488b-104">它表示一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="f488b-104">It represents an XML element.</span></span> <span data-ttu-id="f488b-105">可以使用该类创建元素；更改元素内容；添加、更改或删除子元素；向元素中添加属性；或以文本格式序列化元素内容。</span><span class="sxs-lookup"><span data-stu-id="f488b-105">You can use this class to create elements; change the content of the element; add, change, or delete child elements; add attributes to an element; or serialize the contents of an element in text form.</span></span> <span data-ttu-id="f488b-106">您还可兼容的其他类<xref:System.Xml?displayProperty=fullName>，如<xref:System.Xml.XmlReader>， <xref:System.Xml.XmlWriter>，和<xref:System.Xml.Xsl.XslCompiledTransform>。</xref:System.Xml.Xsl.XslCompiledTransform> </xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> </xref:System.Xml?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f488b-106">You can also interoperate with other classes in <xref:System.Xml?displayProperty=fullName>, such as <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="xelement-functionality"></a><span data-ttu-id="f488b-107">XElement 功能</span><span class="sxs-lookup"><span data-stu-id="f488b-107">XElement Functionality</span></span>  
 <span data-ttu-id="f488b-108">本主题介绍<xref:System.Xml.Linq.XElement>类</xref:System.Xml.Linq.XElement>提供的功能</span><span class="sxs-lookup"><span data-stu-id="f488b-108">This topic describes the functionality provided by the <xref:System.Xml.Linq.XElement> class.</span></span>  
  
### <a name="constructing-xml-trees"></a><span data-ttu-id="f488b-109">构造 XML 树</span><span class="sxs-lookup"><span data-stu-id="f488b-109">Constructing XML Trees</span></span>  
 <span data-ttu-id="f488b-110">可以使用各种方式构造 XML 树，包括以下方式：</span><span class="sxs-lookup"><span data-stu-id="f488b-110">You can construct XML trees in a variety of ways, including the following:</span></span>  
  
-   <span data-ttu-id="f488b-111">可以在代码中构造 XML 树。</span><span class="sxs-lookup"><span data-stu-id="f488b-111">You can construct an XML tree in code.</span></span> <span data-ttu-id="f488b-112">有关详细信息，请参阅[创建 XML 树 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)。</span><span class="sxs-lookup"><span data-stu-id="f488b-112">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
-   <span data-ttu-id="f488b-113">您可以分析来自各种源，包括 XML <xref:System.IO.TextReader>，文本文件或 Web 地址 (URL)。</xref:System.IO.TextReader></span><span class="sxs-lookup"><span data-stu-id="f488b-113">You can parse XML from various sources, including a <xref:System.IO.TextReader>, text files, or a Web address (URL).</span></span> <span data-ttu-id="f488b-114">有关详细信息，请参阅[分析 XML (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="f488b-114">For more information, see [Parsing XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).</span></span>  
  
-   <span data-ttu-id="f488b-115">您可以使用<xref:System.Xml.XmlReader>来填充树。</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="f488b-115">You can use an <xref:System.Xml.XmlReader> to populate the tree.</span></span> <span data-ttu-id="f488b-116">有关详细信息，请参阅<xref:System.Xml.Linq.XNode.ReadFrom%2A>。</xref:System.Xml.Linq.XNode.ReadFrom%2A></span><span class="sxs-lookup"><span data-stu-id="f488b-116">For more information, see <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span></span>  
  
-   <span data-ttu-id="f488b-117">如果您具有一个模块，可以将内容写入<xref:System.Xml.XmlWriter>，您可以使用<xref:System.Xml.Linq.XContainer.CreateWriter%2A>方法来创建编写器，将编写器传递到该模块，然后使用写入到的内容<xref:System.Xml.XmlWriter>来填充 XML 树。</xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XContainer.CreateWriter%2A> </xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="f488b-117">If you have a module that can write content to an <xref:System.Xml.XmlWriter>, you can use the <xref:System.Xml.Linq.XContainer.CreateWriter%2A> method to create a writer, pass the writer to the module, and then use the content that is written to the <xref:System.Xml.XmlWriter> to populate the XML tree.</span></span>  
  
 <span data-ttu-id="f488b-118">但是，创建 XML 树的最常见的方法如下：</span><span class="sxs-lookup"><span data-stu-id="f488b-118">However, the most common way to create an XML tree is as follows:</span></span>  
  
```vb  
Dim contacts As XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone>206-555-0144</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
 <span data-ttu-id="f488b-119">另一个创建 XML 树的十分常用的方法是使用 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 查询的结果来填充 XML 树，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="f488b-119">Another very common technique for creating an XML tree involves using the results of a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query to populate an XML tree, as shown in the following example:</span></span>  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where el.Value > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 <span data-ttu-id="f488b-120">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="f488b-120">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
### <a name="serializing-xml-trees"></a><span data-ttu-id="f488b-121">序列化 XML 树</span><span class="sxs-lookup"><span data-stu-id="f488b-121">Serializing XML Trees</span></span>  
 <span data-ttu-id="f488b-122">XML 树序列化为<xref:System.IO.File>、 <xref:System.IO.TextWriter>，或<xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="f488b-122">You can serialize the XML tree to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="f488b-123">有关详细信息，请参阅[序列化 XML 树 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)。</span><span class="sxs-lookup"><span data-stu-id="f488b-123">For more information, see [Serializing XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).</span></span>  
  
### <a name="retrieving-xml-data-via-axis-methods"></a><span data-ttu-id="f488b-124">通过轴方法检索 XML 数据</span><span class="sxs-lookup"><span data-stu-id="f488b-124">Retrieving XML Data via Axis Methods</span></span>  
 <span data-ttu-id="f488b-125">可以使用轴方法检索属性、子元素、子代元素和上级元素。</span><span class="sxs-lookup"><span data-stu-id="f488b-125">You can use axis methods to retrieve attributes, child elements, descendant elements, and ancestor elements.</span></span> [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]<span data-ttu-id="f488b-126"> 查询对轴方法进行操作，并提供了多种灵活而有效的方法导航和处理 XML 树。</span><span class="sxs-lookup"><span data-stu-id="f488b-126"> queries operate on axis methods, and provide several flexible and powerful ways to navigate through and process an XML tree.</span></span>  
  
 <span data-ttu-id="f488b-127">有关详细信息，请参阅[LINQ to XML 轴 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)。</span><span class="sxs-lookup"><span data-stu-id="f488b-127">For more information, see [LINQ to XML Axes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).</span></span>  
  
### <a name="querying-xml-trees"></a><span data-ttu-id="f488b-128">查询 XML 树</span><span class="sxs-lookup"><span data-stu-id="f488b-128">Querying XML Trees</span></span>  
 <span data-ttu-id="f488b-129">可以编写从 XML 树提取数据的 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 查询。</span><span class="sxs-lookup"><span data-stu-id="f488b-129">You can write [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] queries that extract data from an XML tree.</span></span>  
  
 <span data-ttu-id="f488b-130">有关详细信息，请参阅[查询 XML 树 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)。</span><span class="sxs-lookup"><span data-stu-id="f488b-130">For more information, see [Querying XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).</span></span>  
  
### <a name="modifying-xml-trees"></a><span data-ttu-id="f488b-131">修改 XML 树</span><span class="sxs-lookup"><span data-stu-id="f488b-131">Modifying XML Trees</span></span>  
 <span data-ttu-id="f488b-132">可以通过各种方式修改元素，例如更改元素的内容或属性。</span><span class="sxs-lookup"><span data-stu-id="f488b-132">You can modify an element in a variety of ways, including changing its content or attributes.</span></span> <span data-ttu-id="f488b-133">还可以从元素的父级移除元素。</span><span class="sxs-lookup"><span data-stu-id="f488b-133">You can also remove an element from its parent.</span></span>  
  
 <span data-ttu-id="f488b-134">有关详细信息，请参阅[修改 XML 树 (LINQ to XML) (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="f488b-134">For more information, see [Modifying XML Trees (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f488b-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f488b-135">See Also</span></span>  
 [<span data-ttu-id="f488b-136">LINQ to XML 编程概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f488b-136">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
