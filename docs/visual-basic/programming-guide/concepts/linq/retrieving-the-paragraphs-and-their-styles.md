---
title: "检索段落及其样式 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9ed2238-d38e-4ad4-b88b-db7859df9bde
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 95c85b4731a9ada0a6af1a9d825bef9b873e89ee
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="retrieving-the-paragraphs-and-their-styles-visual-basic"></a><span data-ttu-id="7451b-102">检索段落及其样式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7451b-102">Retrieving the Paragraphs and Their Styles (Visual Basic)</span></span>
<span data-ttu-id="7451b-103">在本示例中，我们编写一个从 WordprocessingML 文档检索段落节点的查询。</span><span class="sxs-lookup"><span data-stu-id="7451b-103">In this example, we write a query that retrieves the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="7451b-104">它还标识每个段落的样式。</span><span class="sxs-lookup"><span data-stu-id="7451b-104">It also identifies the style of each paragraph.</span></span>  
  
 <span data-ttu-id="7451b-105">此查询基于在前面的示例中，查询[查找默认段落样式 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md)，从列表中的样式检索默认样式。</span><span class="sxs-lookup"><span data-stu-id="7451b-105">This query builds on the query in the previous example, [Finding the Default Paragraph Style (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md), which retrieves the default style from the list of styles.</span></span> <span data-ttu-id="7451b-106">这些信息是必需的，以便查询能标识未显式设置样式的段落样式。</span><span class="sxs-lookup"><span data-stu-id="7451b-106">This information is required so that the query can identify the style of paragraphs that do not have a style explicitly set.</span></span> <span data-ttu-id="7451b-107">段落样式通过 `w:pPr` 元素来设置；如果段落未包含此元素，则它会使用默认样式的格式。</span><span class="sxs-lookup"><span data-stu-id="7451b-107">Paragraph styles are set through the `w:pPr` element; if a paragraph does not contain this element, it is formatted with the default style.</span></span>  
  
 <span data-ttu-id="7451b-108">本主题解释某些查询的意义，然后作为一个完整工作示例的一部分来显示查询。</span><span class="sxs-lookup"><span data-stu-id="7451b-108">This topic explains the significance of some pieces of the query, then shows the query as part of a complete, working example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7451b-109">示例</span><span class="sxs-lookup"><span data-stu-id="7451b-109">Example</span></span>  
 <span data-ttu-id="7451b-110">检索文档中所有段落及其样式的查询的源如下所示：</span><span class="sxs-lookup"><span data-stu-id="7451b-110">The source of the query to retrieve all the paragraphs in a document and their styles is as follows:</span></span>  
  
```vb  
xDoc.Root.<w:body>...<w:p>  
```  
  
 <span data-ttu-id="7451b-111">此表达式是类似于在上一示例中，查询的源[查找默认段落样式 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md)。</span><span class="sxs-lookup"><span data-stu-id="7451b-111">This expression is similar to the source of the query in the previous example, [Finding the Default Paragraph Style (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md).</span></span> <span data-ttu-id="7451b-112">主要区别是它使用 <xref:System.Xml.Linq.XContainer.Descendants%2A> 轴，而不是 <xref:System.Xml.Linq.XContainer.Elements%2A> 轴。</span><span class="sxs-lookup"><span data-stu-id="7451b-112">The main difference is that it uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis instead of the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span> <span data-ttu-id="7451b-113">该查询使用 <xref:System.Xml.Linq.XContainer.Descendants%2A> 轴，因为在包含节的文档中，段落将不是正文元素的直接子元素；而是在层次结构中的两个级别之下。</span><span class="sxs-lookup"><span data-stu-id="7451b-113">The query uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis because in documents that have sections, the paragraphs will not be the direct children of the body element; rather, the paragraphs will be two levels down in the hierarchy.</span></span> <span data-ttu-id="7451b-114">通过使用 <xref:System.Xml.Linq.XContainer.Descendants%2A> 轴，无论文档是否使用节，代码都能运行。</span><span class="sxs-lookup"><span data-stu-id="7451b-114">By using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis, the code will work of whether or not the document uses sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7451b-115">示例</span><span class="sxs-lookup"><span data-stu-id="7451b-115">Example</span></span>  
 <span data-ttu-id="7451b-116">该查询使用 `Let` 子句来确定包含样式节点的元素。</span><span class="sxs-lookup"><span data-stu-id="7451b-116">The query uses a `Let` clause to determine the element that contains the style node.</span></span> <span data-ttu-id="7451b-117">如果没有任何元素，则将 `styleNode` 设置为 `Nothing`：</span><span class="sxs-lookup"><span data-stu-id="7451b-117">If there is no element, then `styleNode` is set to `Nothing`:</span></span>  
  
```vb  
Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault()  
```  
  
 <span data-ttu-id="7451b-118">`Let` 子句首先使用 <xref:System.Xml.Linq.XContainer.Elements%2A> 轴，查找所有名为 `pPr` 的元素，然后使用 <xref:System.Xml.Linq.Extensions.Elements%2A> 扩展方法，查找所有名为 `pStyle` 的子元素，最后使用 <xref:System.Linq.Enumerable.FirstOrDefault%2A> 标准查询运算符，将集合转换为单一实例。</span><span class="sxs-lookup"><span data-stu-id="7451b-118">The `Let` clause first uses the <xref:System.Xml.Linq.XContainer.Elements%2A> axis to find all elements named `pPr`, then uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method to find all child elements named `pStyle`, and finally uses the <xref:System.Linq.Enumerable.FirstOrDefault%2A> standard query operator to convert the collection to a singleton.</span></span> <span data-ttu-id="7451b-119">如果集合为空，则将 `styleNode` 设置为 `Nothing`。</span><span class="sxs-lookup"><span data-stu-id="7451b-119">If the collection is empty, `styleNode` is set to `Nothing`.</span></span> <span data-ttu-id="7451b-120">这是一个用于查找 `pStyle` 子代节点的有用方法。</span><span class="sxs-lookup"><span data-stu-id="7451b-120">This is a useful idiom to look for the `pStyle` descendant node.</span></span> <span data-ttu-id="7451b-121">请注意，如果 `pPr` 子节点不存在，代码不会通过引发异常而运行失败；相反，它会将 `styleNode` 设置为 `Nothing`，这是此 `Let` 子句的期望行为。</span><span class="sxs-lookup"><span data-stu-id="7451b-121">Note that if the `pPr` child node does not exist, the code does nor fail by throwing an exception; instead, `styleNode` is set to `Nothing`, which is the desired behavior of this `Let` clause.</span></span>  
  
 <span data-ttu-id="7451b-122">该查询投影一个具有两个成员 `StyleName` 和 `ParagraphNode` 的匿名类型的集合。</span><span class="sxs-lookup"><span data-stu-id="7451b-122">The query projects a collection of an anonymous type with two members, `StyleName` and `ParagraphNode`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7451b-123">示例</span><span class="sxs-lookup"><span data-stu-id="7451b-123">Example</span></span>  
 <span data-ttu-id="7451b-124">本示例处理一个 WordprocessingML 文档，它从 WordprocessingML 文档中检索段落节点。</span><span class="sxs-lookup"><span data-stu-id="7451b-124">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="7451b-125">它还标识每个段落的样式。</span><span class="sxs-lookup"><span data-stu-id="7451b-125">It also identifies the style of each paragraph.</span></span> <span data-ttu-id="7451b-126">本示例以本教程中前面的一些示例为基础构建。</span><span class="sxs-lookup"><span data-stu-id="7451b-126">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="7451b-127">下面代码中的注释标识出了这个新查询。</span><span class="sxs-lookup"><span data-stu-id="7451b-127">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="7451b-128">你可以找到用于创建此示例中的源文档的说明[创建源 Office Open XML 文档 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)。</span><span class="sxs-lookup"><span data-stu-id="7451b-128">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="7451b-129">本示例使用 WindowsBase 程序集中的类。</span><span class="sxs-lookup"><span data-stu-id="7451b-129">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="7451b-130">它使用 <xref:System.IO.Packaging?displayProperty=nameWithType> 命名空间中的类型。</span><span class="sxs-lookup"><span data-stu-id="7451b-130">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, ByVal defaultStyle As String) As String  
        If (styleNode Is Nothing) Then  
            Return defaultStyle  
        Else  
            Return styleNode.@w:val  
        End If  
    End Function  
  
    Sub Main()  
        Dim fileName = "SampleDoc.docx"  
  
        Dim documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Dim stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
        Dim wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                '  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                '  Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If (styleRelation IsNot Nothing) Then  
                    Dim styleUri As Uri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    '  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        Dim defaultStyle As String = _  
            ( _  
                From style In styleDoc.Root.<w:style> _  
                Where style.@w:type = "paragraph" And _  
                      style.@w:default = "1" _  
                Select style _  
            ).First().@w:styleId  
  
        ' Following is the new query that finds all paragraphs in the  
        ' document and their styles.  
        Dim paragraphs = _  
            From para In xDoc.Root.<w:body>...<w:p> _  
        Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault() _  
        Select New With { _  
            .ParagraphNode = para, _  
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _  
        }  
  
        For Each p In paragraphs  
            Console.WriteLine("StyleName:{0}", p.StyleName)  
        Next  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="7451b-131">该示例产生以下输出时应用于文档中所述[创建源 Office Open XML 文档 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)。</span><span class="sxs-lookup"><span data-stu-id="7451b-131">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
```  
StyleName:Heading1  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
```  
  
## <a name="next-steps"></a><span data-ttu-id="7451b-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7451b-132">Next Steps</span></span>  
 <span data-ttu-id="7451b-133">在下一步的主题中，[检索段落 (Visual Basic 中) 的文本](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md)，你将创建查询来检索段落的文本。</span><span class="sxs-lookup"><span data-stu-id="7451b-133">In the next topic, [Retrieving the Text of the Paragraphs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), you'll create a query to retrieve the text of paragraphs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7451b-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7451b-134">See Also</span></span>  
 [<span data-ttu-id="7451b-135">教程： 操作 WordprocessingML 文档 (Visual Basic 中) 中的内容</span><span class="sxs-lookup"><span data-stu-id="7451b-135">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
