---
title: "LINQ to XML 类概述 (Visual Basic) |Microsoft 文档"
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
ms.assetid: f11b62b5-d522-4c23-92ae-23186dc16447
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
ms.openlocfilehash: 8c999860ed04c754855792d814cd3801f5f92c90
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="linq-to-xml-classes-overview-visual-basic"></a><span data-ttu-id="5afda-102">LINQ to XML 类概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5afda-102">LINQ to XML Classes Overview (Visual Basic)</span></span>
<span data-ttu-id="5afda-103">本主题提供了一份[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]中的类<xref:System.Xml.Linq>命名空间，以及每个简短说明。</xref:System.Xml.Linq></span><span class="sxs-lookup"><span data-stu-id="5afda-103">This topic provides a list of the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] classes in the <xref:System.Xml.Linq> namespace, and a short description of each.</span></span>  
  
## <a name="linq-to-xml-classes"></a><span data-ttu-id="5afda-104">LINQ to XML 类</span><span class="sxs-lookup"><span data-stu-id="5afda-104">LINQ to XML Classes</span></span>  
  
### <a name="xattribute-class"></a><span data-ttu-id="5afda-105">XAttribute 类</span><span class="sxs-lookup"><span data-stu-id="5afda-105">XAttribute Class</span></span>  
 <span data-ttu-id="5afda-106"><xref:System.Xml.Linq.XAttribute>表示一个 XML 属性。</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="5afda-106"><xref:System.Xml.Linq.XAttribute> represents an XML attribute.</span></span> <span data-ttu-id="5afda-107">有关详细的信息和示例，请参阅[XAttribute 类概述 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/xattribute-class-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5afda-107">For detailed information and examples, see [XAttribute Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xattribute-class-overview.md).</span></span>  
  
### <a name="xcdata-class"></a><span data-ttu-id="5afda-108">XCData 类</span><span class="sxs-lookup"><span data-stu-id="5afda-108">XCData Class</span></span>  
 <span data-ttu-id="5afda-109"><xref:System.Xml.Linq.XCData>表示一个 CDATA 文本节点。</xref:System.Xml.Linq.XCData></span><span class="sxs-lookup"><span data-stu-id="5afda-109"><xref:System.Xml.Linq.XCData> represents a CDATA text node.</span></span>  
  
### <a name="xcomment-class"></a><span data-ttu-id="5afda-110">XComment 类</span><span class="sxs-lookup"><span data-stu-id="5afda-110">XComment Class</span></span>  
 <span data-ttu-id="5afda-111"><xref:System.Xml.Linq.XComment>表示一个 XML 注释。</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="5afda-111"><xref:System.Xml.Linq.XComment> represents an XML comment.</span></span>  
  
### <a name="xcontainer-class"></a><span data-ttu-id="5afda-112">XContainer 类</span><span class="sxs-lookup"><span data-stu-id="5afda-112">XContainer Class</span></span>  
 <span data-ttu-id="5afda-113"><xref:System.Xml.Linq.XContainer>是可以有子节点的所有节点的抽象基类。</xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="5afda-113"><xref:System.Xml.Linq.XContainer> is an abstract base class for all nodes that can have child nodes.</span></span> <span data-ttu-id="5afda-114">下面的类派生自<xref:System.Xml.Linq.XContainer>类︰</xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="5afda-114">The following classes derive from the <xref:System.Xml.Linq.XContainer> class:</span></span>  
  
-   <span data-ttu-id="5afda-115"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="5afda-115"><xref:System.Xml.Linq.XElement></span></span>  
  
-   <span data-ttu-id="5afda-116"><xref:System.Xml.Linq.XDocument></xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="5afda-116"><xref:System.Xml.Linq.XDocument></span></span>  
  
### <a name="xdeclaration-class"></a><span data-ttu-id="5afda-117">XDeclaration 类</span><span class="sxs-lookup"><span data-stu-id="5afda-117">XDeclaration Class</span></span>  
 <span data-ttu-id="5afda-118"><xref:System.Xml.Linq.XDeclaration>表示一个 XML 声明。</xref:System.Xml.Linq.XDeclaration></span><span class="sxs-lookup"><span data-stu-id="5afda-118"><xref:System.Xml.Linq.XDeclaration> represents an XML declaration.</span></span> <span data-ttu-id="5afda-119">XML 声明用于声明 XML 版本和文档的编码。</span><span class="sxs-lookup"><span data-stu-id="5afda-119">An XML declaration is used to declare the XML version and the encoding of a document.</span></span> <span data-ttu-id="5afda-120">此外，XML 声明还指定 XML 文档是否为独立文档。</span><span class="sxs-lookup"><span data-stu-id="5afda-120">In addition, an XML declaration specifies whether the XML document is stand-alone.</span></span> <span data-ttu-id="5afda-121">如果文档是独立文档，则在外部 DTD 或从内部子集引用的外部参数实体中不存在外部标记声明。</span><span class="sxs-lookup"><span data-stu-id="5afda-121">If a document is stand-alone, there are no external markup declarations, either in an external DTD, or in an external parameter entity referenced from the internal subset.</span></span>  
  
### <a name="xdocument-class"></a><span data-ttu-id="5afda-122">XDocument 类</span><span class="sxs-lookup"><span data-stu-id="5afda-122">XDocument Class</span></span>  
 <span data-ttu-id="5afda-123"><xref:System.Xml.Linq.XDocument>表示 XML 文档。</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="5afda-123"><xref:System.Xml.Linq.XDocument> represents an XML document.</span></span> <span data-ttu-id="5afda-124">有关详细的信息和示例，请参阅[XDocument 类概述 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5afda-124">For detailed information and examples, see [XDocument Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).</span></span>  
  
### <a name="xdocumenttype-class"></a><span data-ttu-id="5afda-125">XDocumentType 类</span><span class="sxs-lookup"><span data-stu-id="5afda-125">XDocumentType Class</span></span>  
 <span data-ttu-id="5afda-126"><xref:System.Xml.Linq.XDocumentType>表示 XML 文档类型定义 (DTD)。</xref:System.Xml.Linq.XDocumentType></span><span class="sxs-lookup"><span data-stu-id="5afda-126"><xref:System.Xml.Linq.XDocumentType> represents an XML Document Type Definition (DTD).</span></span>  
  
### <a name="xelement-class"></a><span data-ttu-id="5afda-127">XElement 类</span><span class="sxs-lookup"><span data-stu-id="5afda-127">XElement Class</span></span>  
 <span data-ttu-id="5afda-128"><xref:System.Xml.Linq.XElement>表示一个 XML 元素。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="5afda-128"><xref:System.Xml.Linq.XElement> represents an XML element.</span></span> <span data-ttu-id="5afda-129">有关详细的信息和示例，请参阅[XElement 类概述 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/xelement-class-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5afda-129">For detailed information and examples, see [XElement Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xelement-class-overview.md).</span></span>  
  
### <a name="xname-class"></a><span data-ttu-id="5afda-130">XName 类</span><span class="sxs-lookup"><span data-stu-id="5afda-130">XName Class</span></span>  
 <span data-ttu-id="5afda-131"><xref:System.Xml.Linq.XName>表示元素的名称 (<xref:System.Xml.Linq.XElement>) 和属性 (<xref:System.Xml.Linq.XAttribute>)。</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="5afda-131"><xref:System.Xml.Linq.XName> represents names of elements (<xref:System.Xml.Linq.XElement>) and attributes (<xref:System.Xml.Linq.XAttribute>).</span></span> <span data-ttu-id="5afda-132">有关详细的信息和示例，请参阅[XDocument 类概述 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5afda-132">For detailed information and examples, see [XDocument Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="5afda-133"> 旨在使 XML 名称尽可能简单。</span><span class="sxs-lookup"><span data-stu-id="5afda-133"> is designed to make XML names as straightforward as possible.</span></span> <span data-ttu-id="5afda-134">XML 名称由于复杂而通常被视为 XML 中的高级主题。</span><span class="sxs-lookup"><span data-stu-id="5afda-134">Due to their complexity, XML names are often considered to be an advanced topic in XML.</span></span> <span data-ttu-id="5afda-135">有证据证明，这种复杂性不是由开发人员编程时通常使用的命名空间造成的，而是由命名空间前缀造成的。</span><span class="sxs-lookup"><span data-stu-id="5afda-135">Arguably, this complexity comes not from namespaces, which developers use regularly in programming, but from namespace prefixes.</span></span> <span data-ttu-id="5afda-136">使用命名空间前缀可以减少输入 XML 时需要的击键数或使 XML 更具可读性。</span><span class="sxs-lookup"><span data-stu-id="5afda-136">Namespace prefixes can be useful to reduce the keystrokes required when you input XML, or to make XML easier to read.</span></span> <span data-ttu-id="5afda-137">但是，前缀通常是只需使用的快捷方式的完整 XML 命名空间，并且不要求在大多数情况下。</span><span class="sxs-lookup"><span data-stu-id="5afda-137">However, prefixes are often just a shortcut for using the full XML namespace, and are not required in most cases.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="5afda-138">通过将所有前缀都解析为其对应的 XML 命名空间，简化了 XML 名称。</span><span class="sxs-lookup"><span data-stu-id="5afda-138"> simplifies XML names by resolving all prefixes to their corresponding XML namespace.</span></span> <span data-ttu-id="5afda-139">前缀是可用的如果需要，通过这些<xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A>方法。</xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="5afda-139">Prefixes are available, if they are required, through the <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A> method.</span></span>  
  
 <span data-ttu-id="5afda-140">如果有必要，可以控制命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="5afda-140">It is possible, if necessary, to control namespace prefixes.</span></span> <span data-ttu-id="5afda-141">在某些情况下，如果使用的是其他 XML 系统（如 XSLT 或 XAML），则需要控制命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="5afda-141">In some circumstances, if you are working with other XML systems, such as XSLT or XAML, you need to control namespace prefixes.</span></span> <span data-ttu-id="5afda-142">例如，如果 XPath 表达式使用命名空间前缀且嵌入在 XSLT 样式表中，则将必须确保使用与 XPath 表达式中使用的前缀相匹配的命名空间前缀来序列化 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="5afda-142">For example, if you have an XPath expression that uses namespace prefixes and is embedded in an XSLT stylesheet, you must make sure that your XML document is serialized with namespace prefixes that match those used in the XPath expression.</span></span>  
  
### <a name="xnamespace-class"></a><span data-ttu-id="5afda-143">XNamespace 类</span><span class="sxs-lookup"><span data-stu-id="5afda-143">XNamespace Class</span></span>  
 <span data-ttu-id="5afda-144"><xref:System.Xml.Linq.XNamespace>表示一个命名空间<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="5afda-144"><xref:System.Xml.Linq.XNamespace> represents a namespace for an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="5afda-145">命名空间是<xref:System.Xml.Linq.XName>。</xref:System.Xml.Linq.XName>的组件</span><span class="sxs-lookup"><span data-stu-id="5afda-145">Namespaces are a component of an <xref:System.Xml.Linq.XName>.</span></span>  
  
### <a name="xnode-class"></a><span data-ttu-id="5afda-146">XNode 类</span><span class="sxs-lookup"><span data-stu-id="5afda-146">XNode Class</span></span>  
 <span data-ttu-id="5afda-147"><xref:System.Xml.Linq.XNode>是一个抽象类表示 XML 树的节点。</xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="5afda-147"><xref:System.Xml.Linq.XNode> is an abstract class that represents the nodes of an XML tree.</span></span> <span data-ttu-id="5afda-148">下面的类派生自<xref:System.Xml.Linq.XNode>类︰</xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="5afda-148">The following classes derive from the <xref:System.Xml.Linq.XNode> class:</span></span>  
  
-   <span data-ttu-id="5afda-149"><xref:System.Xml.Linq.XText></xref:System.Xml.Linq.XText></span><span class="sxs-lookup"><span data-stu-id="5afda-149"><xref:System.Xml.Linq.XText></span></span>  
  
-   <span data-ttu-id="5afda-150"><xref:System.Xml.Linq.XContainer></xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="5afda-150"><xref:System.Xml.Linq.XContainer></span></span>  
  
-   <span data-ttu-id="5afda-151"><xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="5afda-151"><xref:System.Xml.Linq.XComment></span></span>  
  
-   <span data-ttu-id="5afda-152"><xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="5afda-152"><xref:System.Xml.Linq.XProcessingInstruction></span></span>  
  
-   <span data-ttu-id="5afda-153"><xref:System.Xml.Linq.XDocumentType></xref:System.Xml.Linq.XDocumentType></span><span class="sxs-lookup"><span data-stu-id="5afda-153"><xref:System.Xml.Linq.XDocumentType></span></span>  
  
### <a name="xnodedocumentordercomparer-class"></a><span data-ttu-id="5afda-154">XNodeDocumentOrderComparer 类</span><span class="sxs-lookup"><span data-stu-id="5afda-154">XNodeDocumentOrderComparer Class</span></span>  
 <span data-ttu-id="5afda-155"><xref:System.Xml.Linq.XNodeDocumentOrderComparer>提供用于比较节点文档顺序的功能。</xref:System.Xml.Linq.XNodeDocumentOrderComparer></span><span class="sxs-lookup"><span data-stu-id="5afda-155"><xref:System.Xml.Linq.XNodeDocumentOrderComparer> provides functionality to compare nodes for their document order.</span></span>  
  
### <a name="xnodeequalitycomparer-class"></a><span data-ttu-id="5afda-156">XNodeEqualityComparer 类</span><span class="sxs-lookup"><span data-stu-id="5afda-156">XNodeEqualityComparer Class</span></span>  
 <span data-ttu-id="5afda-157"><xref:System.Xml.Linq.XNodeEqualityComparer>提供用于比较节点值相等的功能。</xref:System.Xml.Linq.XNodeEqualityComparer></span><span class="sxs-lookup"><span data-stu-id="5afda-157"><xref:System.Xml.Linq.XNodeEqualityComparer> provides functionality to compare nodes for value equality.</span></span>  
  
### <a name="xobject-class"></a><span data-ttu-id="5afda-158">XObject 类</span><span class="sxs-lookup"><span data-stu-id="5afda-158">XObject Class</span></span>  
 <span data-ttu-id="5afda-159"><xref:System.Xml.Linq.XObject>是一个抽象基类和<xref:System.Xml.Linq.XNode><xref:System.Xml.Linq.XAttribute>。</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode></xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="5afda-159"><xref:System.Xml.Linq.XObject> is an abstract base class of <xref:System.Xml.Linq.XNode> and <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="5afda-160">它提供批注和事件功能。</span><span class="sxs-lookup"><span data-stu-id="5afda-160">It provides annotation and event functionality.</span></span>  
  
### <a name="xobjectchange-class"></a><span data-ttu-id="5afda-161">XObjectChange 类</span><span class="sxs-lookup"><span data-stu-id="5afda-161">XObjectChange Class</span></span>  
 <span data-ttu-id="5afda-162"><xref:System.Xml.Linq.XObjectChange>以团队<xref:System.Xml.Linq.XObject>。</xref:System.Xml.Linq.XObject>引发事件时指定的事件类型</xref:System.Xml.Linq.XObjectChange></span><span class="sxs-lookup"><span data-stu-id="5afda-162"><xref:System.Xml.Linq.XObjectChange> specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>  
  
### <a name="xobjectchangeeventargs-class"></a><span data-ttu-id="5afda-163">XObjectChangeEventArgs 类</span><span class="sxs-lookup"><span data-stu-id="5afda-163">XObjectChangeEventArgs Class</span></span>  
 <span data-ttu-id="5afda-164"><xref:System.Xml.Linq.XObjectChangeEventArgs>将提供数据供<xref:System.Xml.Linq.XObject.Changing>和<xref:System.Xml.Linq.XObject.Changed>事件。</xref:System.Xml.Linq.XObject.Changed> </xref:System.Xml.Linq.XObject.Changing></xref:System.Xml.Linq.XObjectChangeEventArgs></span><span class="sxs-lookup"><span data-stu-id="5afda-164"><xref:System.Xml.Linq.XObjectChangeEventArgs> provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>  
  
### <a name="xprocessinginstruction-class"></a><span data-ttu-id="5afda-165">XProcessingInstruction 类</span><span class="sxs-lookup"><span data-stu-id="5afda-165">XProcessingInstruction Class</span></span>  
 <span data-ttu-id="5afda-166"><xref:System.Xml.Linq.XProcessingInstruction>表示一个 XML 处理指令。</xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="5afda-166"><xref:System.Xml.Linq.XProcessingInstruction> represents an XML processing instruction.</span></span> <span data-ttu-id="5afda-167">处理指令将信息传递给处理 XML 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5afda-167">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
### <a name="xtext-class"></a><span data-ttu-id="5afda-168">XText 类</span><span class="sxs-lookup"><span data-stu-id="5afda-168">XText Class</span></span>  
 <span data-ttu-id="5afda-169"><xref:System.Xml.Linq.XText>表示一个文本节点。</xref:System.Xml.Linq.XText></span><span class="sxs-lookup"><span data-stu-id="5afda-169"><xref:System.Xml.Linq.XText> represents a text node.</span></span> <span data-ttu-id="5afda-170">多数情况下都不必使用此类。</span><span class="sxs-lookup"><span data-stu-id="5afda-170">In most cases, you do not have to use this class.</span></span> <span data-ttu-id="5afda-171">此类主要用于混合内容。</span><span class="sxs-lookup"><span data-stu-id="5afda-171">This class is primarily used for mixed content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5afda-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5afda-172">See Also</span></span>  
 [<span data-ttu-id="5afda-173">LINQ to XML 编程概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5afda-173">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
