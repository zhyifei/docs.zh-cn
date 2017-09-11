---
title: "使用节点 (Visual Basic 中) 进行编程 |Microsoft 文档"
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
ms.assetid: d8422a9b-dd37-44a3-8aac-2237ed9561e0
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 967e207aa4d1a4afb21f82b7b1767a5c6dc088c6
ms.contentlocale: zh-cn
ms.lasthandoff: 05/23/2017

---
# <a name="programming-with-nodes-visual-basic"></a><span data-ttu-id="61f20-102">使用节点 (Visual Basic 中) 进行编程</span><span class="sxs-lookup"><span data-stu-id="61f20-102">Programming with Nodes (Visual Basic)</span></span>
<span data-ttu-id="61f20-103">需要编写 XML 编辑器、转换系统或报告编写器这类程序的 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 开发人员通常需要编写在比元素和属性更细的粒度下运行的程序。</span><span class="sxs-lookup"><span data-stu-id="61f20-103">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] developers who need to write programs such as an XML editor, a transform system, or a report writer often need to write programs that work at a finer level of granularity than elements and attributes.</span></span> <span data-ttu-id="61f20-104">开发人员通常需要在节点级别上工作，操作文本节点、处理指令和添加注释。</span><span class="sxs-lookup"><span data-stu-id="61f20-104">They often need to work at the node level, manipulating text nodes, processing instructions, and comments.</span></span> <span data-ttu-id="61f20-105">本主题提供有关在节点级别进行编程的一些详细信息。</span><span class="sxs-lookup"><span data-stu-id="61f20-105">This topic provides some details about programming at the node level.</span></span>  
  
## <a name="node-details"></a><span data-ttu-id="61f20-106">节点详细信息</span><span class="sxs-lookup"><span data-stu-id="61f20-106">Node Details</span></span>  
 <span data-ttu-id="61f20-107">在节点级别上工作的程序员需要了解有关编程的许多细节。</span><span class="sxs-lookup"><span data-stu-id="61f20-107">There are a number of details of programming that a programmer working at the node level should know.</span></span>  
  
### <a name="parent-property-of-children-nodes-of-xdocument-is-set-to-null"></a><span data-ttu-id="61f20-108">XDocument 的子节点的父属性设置为 Null</span><span class="sxs-lookup"><span data-stu-id="61f20-108">Parent Property of Children Nodes of XDocument is Set to Null</span></span>  
 <span data-ttu-id="61f20-109"><xref:System.Xml.Linq.XObject.Parent%2A>属性包含父<xref:System.Xml.Linq.XElement>，不是父节点。</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XObject.Parent%2A></span><span class="sxs-lookup"><span data-stu-id="61f20-109">The <xref:System.Xml.Linq.XObject.Parent%2A> property contains the parent <xref:System.Xml.Linq.XElement>, not the parent node.</span></span> <span data-ttu-id="61f20-110">子节点<xref:System.Xml.Linq.XDocument>没有父<xref:System.Xml.Linq.XElement>。</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="61f20-110">Child nodes of <xref:System.Xml.Linq.XDocument> have no parent <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="61f20-111">它们的父级是文档中，因此<xref:System.Xml.Linq.XObject.Parent%2A>对这些节点的属性设置为 null。</xref:System.Xml.Linq.XObject.Parent%2A></span><span class="sxs-lookup"><span data-stu-id="61f20-111">Their parent is the document, so the <xref:System.Xml.Linq.XObject.Parent%2A> property for those nodes is set to null.</span></span>  
  
 <span data-ttu-id="61f20-112">下面的示例演示这一操作：</span><span class="sxs-lookup"><span data-stu-id="61f20-112">The following example demonstrates this:</span></span>  
  
```vb  
Dim doc As XDocument = XDocument.Parse("<!-- a comment --><Root/>")  
Console.WriteLine(doc.Nodes().OfType(Of XComment).First().Parent Is Nothing)  
Console.WriteLine(doc.Root.Parent Is Nothing)  
```  
  
 <span data-ttu-id="61f20-113">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="61f20-113">This example produces the following output:</span></span>  
  
```  
True  
True  
```  
  
### <a name="adjacent-text-nodes-are-possible"></a><span data-ttu-id="61f20-114">可以存在相邻文本节点</span><span class="sxs-lookup"><span data-stu-id="61f20-114">Adjacent Text Nodes are Possible</span></span>  
 <span data-ttu-id="61f20-115">在许多 XML 编程模型中，相邻的文本节点始终会合并到一起。</span><span class="sxs-lookup"><span data-stu-id="61f20-115">In a number of XML programming models, adjacent text nodes are always merged.</span></span> <span data-ttu-id="61f20-116">这有时也称为文本节点的规范化。</span><span class="sxs-lookup"><span data-stu-id="61f20-116">This is sometimes called normalization of text nodes.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="61f20-117"> 不规范化文本节点。</span><span class="sxs-lookup"><span data-stu-id="61f20-117"> does not normalize text nodes.</span></span> <span data-ttu-id="61f20-118">如果向同一个元素添加两个文本节点，则会产生相邻文本节点。</span><span class="sxs-lookup"><span data-stu-id="61f20-118">If you add two text nodes to the same element, it will result in adjacent text nodes.</span></span> <span data-ttu-id="61f20-119">但是，如果您将指定为一个字符串，而不是内容添加<xref:System.Xml.Linq.XText>节点，[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]可能会将合并具有相邻的文本节点的字符串。</xref:System.Xml.Linq.XText></span><span class="sxs-lookup"><span data-stu-id="61f20-119">However, if you add content specified as a string rather than as an <xref:System.Xml.Linq.XText> node, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] might merge the string with an adjacent text node.</span></span>  
  
 <span data-ttu-id="61f20-120">下面的示例演示这一操作：</span><span class="sxs-lookup"><span data-stu-id="61f20-120">The following example demonstrates this:</span></span>  
  
```vb  
Dim xmlTree As XElement = <Root>Content</Root>  
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())  
  
' This does not add a new text node.  
xmlTree.Add("new content")  
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())  
  
'// This does add a new, adjacent text node.  
xmlTree.Add(New XText("more text"))  
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())  
```  
  
 <span data-ttu-id="61f20-121">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="61f20-121">This example produces the following output:</span></span>  
  
```  
1  
1  
2  
```  
  
### <a name="empty-text-nodes-are-possible"></a><span data-ttu-id="61f20-122">可以存在空文本节点</span><span class="sxs-lookup"><span data-stu-id="61f20-122">Empty Text Nodes are Possible</span></span>  
 <span data-ttu-id="61f20-123">在某些 XML 编程模型中，文本节点保证不包含空字符串。</span><span class="sxs-lookup"><span data-stu-id="61f20-123">In some XML programming models, text nodes are guaranteed to not contain the empty string.</span></span> <span data-ttu-id="61f20-124">原因是这种文本节点对 XML 的序列化没有影响。</span><span class="sxs-lookup"><span data-stu-id="61f20-124">The reasoning is that such a text node has no impact on serialization of the XML.</span></span> <span data-ttu-id="61f20-125">但由于可以存在相邻文本节点这一相同的原因，如果您通过将文本节点的值设置为空字符串来移除文本节点中的文本，则不会删除文本节点本身。</span><span class="sxs-lookup"><span data-stu-id="61f20-125">However, for the same reason that adjacent text nodes are possible, if you remove the text from a text node by setting its value to the empty string, the text node itself will not be deleted.</span></span>  
  
```vb  
Dim xmlTree As XElement = <Root>Content</Root>  
Dim textNode As XText = xmlTree.Nodes().OfType(Of XText)().First()  
  
' The following line does not cause the removal of the text node.  
textNode.Value = ""  
  
Dim textNode2 As XText = xmlTree.Nodes().OfType(Of XText)().First()  
Console.WriteLine(">>{0}<<", textNode2)  
```  
  
 <span data-ttu-id="61f20-126">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="61f20-126">This example produces the following output:</span></span>  
  
```  
>><<  
```  
  
### <a name="an-empty-text-node-impacts-serialization"></a><span data-ttu-id="61f20-127">空文本节点影响序列化</span><span class="sxs-lookup"><span data-stu-id="61f20-127">An Empty Text Node Impacts Serialization</span></span>  
 <span data-ttu-id="61f20-128">如果一个元素仅包含一个空的子文本节点，则会用长标记语法序列化该元素：`<Child></Child>`。</span><span class="sxs-lookup"><span data-stu-id="61f20-128">If an element contains only a child text node that is empty, it is serialized with the long tag syntax: `<Child></Child>`.</span></span> <span data-ttu-id="61f20-129">如果一个元素不包含任何子节点，则会用短标记语法序列化该元素：`<Child />`。</span><span class="sxs-lookup"><span data-stu-id="61f20-129">If an element contains no child nodes whatsoever, it is serialized with the short tag syntax: `<Child />`.</span></span>  
  
```vb  
Dim child1 As XElement = New XElement("Child1", _  
    New XText("") _  
)  
Dim child2 As XElement = New XElement("Child2")  
Console.WriteLine(child1)  
Console.WriteLine(child2)  
```  
  
 <span data-ttu-id="61f20-130">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="61f20-130">This example produces the following output:</span></span>  
  
```  
<Child1></Child1>  
<Child2 />  
```  
  
### <a name="namespaces-are-attributes-in-the-linq-to-xml-tree"></a><span data-ttu-id="61f20-131">命名空间是 LINQ to XML 树中的属性</span><span class="sxs-lookup"><span data-stu-id="61f20-131">Namespaces are Attributes in the LINQ to XML Tree</span></span>  
 <span data-ttu-id="61f20-132">即使命名空间声明与特性具有完全相同的语法，在某些编程接口（如 XSLT 和 XPath）中，也不会将命名空间声明视为属性。</span><span class="sxs-lookup"><span data-stu-id="61f20-132">Even though namespace declarations have identical syntax to attributes, in some programming interfaces, such as XSLT and XPath, namespace declarations are not considered to be attributes.</span></span> <span data-ttu-id="61f20-133">但是，在[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]，命名空间存储为<xref:System.Xml.Linq.XAttribute>XML 树中的对象。</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="61f20-133">However, in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], namespaces are stored as <xref:System.Xml.Linq.XAttribute> objects in the XML tree.</span></span> <span data-ttu-id="61f20-134">如果您循环访问包含命名空间声明的元素的属性，则会在返回的集合中看到作为一项列出的命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="61f20-134">If you iterate through the attributes for an element that contains a namespace declaration, you will see the namespace declaration as one of the items in the returned collection.</span></span>  
  
 <span data-ttu-id="61f20-135"><xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A>属性指示属性是否为命名空间声明。</xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A></span><span class="sxs-lookup"><span data-stu-id="61f20-135">The <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A> property indicates whether an attribute is a namespace declaration.</span></span>  
  
```vb  
Dim root As XElement = _   
<Root  
    xmlns='http://www.adventure-works.com'  
    xmlns:fc='www.fourthcoffee.com'  
    AnAttribute='abc'/>  
For Each att As XAttribute In root.Attributes()  
    Console.WriteLine("{0}  IsNamespaceDeclaration:{1}", att, _  
                      att.IsNamespaceDeclaration)  
Next  
```  
  
 <span data-ttu-id="61f20-136">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="61f20-136">This example produces the following output:</span></span>  
  
```  
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True  
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True  
AnAttribute="abc"  IsNamespaceDeclaration:False  
```  
  
### <a name="xpath-axis-methods-do-not-return-child-white-space-of-xdocument"></a><span data-ttu-id="61f20-137">XPath 轴方法不返回 XDocument 的子空白</span><span class="sxs-lookup"><span data-stu-id="61f20-137">XPath Axis Methods Do Not Return Child White Space of XDocument</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="61f20-138">允许的子文本节点<xref:System.Xml.Linq.XDocument>，只要文本节点只能包含空白。</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="61f20-138"> allows for child text nodes of an <xref:System.Xml.Linq.XDocument>, as long as the text nodes contain only white space.</span></span> <span data-ttu-id="61f20-139">但是，XPath 对象模型不包括空白作为子节点的一个文档，因此当遍历的子级<xref:System.Xml.Linq.XDocument>使用<xref:System.Xml.Linq.XContainer.Nodes%2A>轴，将返回空白文本节点。</xref:System.Xml.Linq.XContainer.Nodes%2A> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="61f20-139">However, the XPath object model does not include white space as child nodes of a document, so when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the <xref:System.Xml.Linq.XContainer.Nodes%2A> axis, white space text nodes will be returned.</span></span> <span data-ttu-id="61f20-140">但是，当您遍历的子级<xref:System.Xml.Linq.XDocument>使用 XPath 轴方法，空白文本节点将不会返回。</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="61f20-140">However, when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the XPath axis methods, white space text nodes will not be returned.</span></span>  
  
```vb  
' Create a document with some white space child nodes of the document.  
Dim root As XDocument = XDocument.Parse( _  
"<?xml version='1.0' encoding='utf-8' standalone='yes'?>" & _  
vbNewLine & "<Root/>" & vbNewLine & "<!--a comment-->" & vbNewLine, _  
LoadOptions.PreserveWhitespace)  
  
' Count the white space child nodes using LINQ to XML.  
Console.WriteLine(root.Nodes().OfType(Of XText)().Count())  
  
' Count the white space child nodes using XPathEvaluate.  
Dim nodes As IEnumerable = CType(root.XPathEvaluate("text()"), IEnumerable)  
Console.WriteLine(nodes.OfType(Of XText)().Count())  
```  
  
 <span data-ttu-id="61f20-141">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="61f20-141">This example produces the following output:</span></span>  
  
```  
3  
0  
```  
  
### <a name="xdeclaration-objects-are-not-nodes"></a><span data-ttu-id="61f20-142">XDeclaration 对象不是节点</span><span class="sxs-lookup"><span data-stu-id="61f20-142">XDeclaration Objects are not Nodes</span></span>  
 <span data-ttu-id="61f20-143">当您循环访问的子节点<xref:System.Xml.Linq.XDocument>，则将看不到 XML 声明对象。</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="61f20-143">When you iterate through the children nodes of an <xref:System.Xml.Linq.XDocument>, you will not see the XML declaration object.</span></span> <span data-ttu-id="61f20-144">它是文档的属性，不是文档的子节点。</span><span class="sxs-lookup"><span data-stu-id="61f20-144">It is a property of the document, not a child node of it.</span></span>  
  
```vb  
Dim doc As XDocument = _  
<?xml version='1.0' encoding='utf-8' standalone='yes'?>  
<Root/>  
  
doc.Save("Temp.xml")  
Console.WriteLine(File.ReadAllText("Temp.xml"))  
  
' This shows that there is only one child node of the document.  
Console.WriteLine(doc.Nodes().Count())  
```  
  
 <span data-ttu-id="61f20-145">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="61f20-145">This example produces the following output:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root />  
1  
```  
  
## <a name="see-also"></a><span data-ttu-id="61f20-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61f20-146">See Also</span></span>  
 [<span data-ttu-id="61f20-147">高级的 LINQ to XML 编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61f20-147">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)

