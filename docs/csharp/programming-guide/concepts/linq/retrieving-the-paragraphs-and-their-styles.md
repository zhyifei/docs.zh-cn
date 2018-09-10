---
title: 检索段落及其样式 (C#)
ms.date: 07/20/2015
ms.assetid: c2f767f8-57b1-4b4b-af04-89ffb1f7067d
ms.openlocfilehash: 46ffc13c9808b6186efa402bd46b75c6c1a9bbda
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510769"
---
# <a name="retrieving-the-paragraphs-and-their-styles-c"></a><span data-ttu-id="c048a-102">检索段落及其样式 (C#)</span><span class="sxs-lookup"><span data-stu-id="c048a-102">Retrieving the Paragraphs and Their Styles (C#)</span></span>
<span data-ttu-id="c048a-103">在本示例中，我们编写一个从 WordprocessingML 文档检索段落节点的查询。</span><span class="sxs-lookup"><span data-stu-id="c048a-103">In this example, we write a query that retrieves the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="c048a-104">它还标识每个段落的样式。</span><span class="sxs-lookup"><span data-stu-id="c048a-104">It also identifies the style of each paragraph.</span></span>  
  
 <span data-ttu-id="c048a-105">此查询建立在前一示例[查找默认段落样式 (C#)](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md) 中的查询的基础之上，该查询从样式列表中检索默认样式。</span><span class="sxs-lookup"><span data-stu-id="c048a-105">This query builds on the query in the previous example, [Finding the Default Paragraph Style (C#)](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md), which retrieves the default style from the list of styles.</span></span> <span data-ttu-id="c048a-106">这些信息是必需的，以便查询能标识未显式设置样式的段落样式。</span><span class="sxs-lookup"><span data-stu-id="c048a-106">This information is required so that the query can identify the style of paragraphs that do not have a style explicitly set.</span></span> <span data-ttu-id="c048a-107">段落样式通过 `w:pPr` 元素来设置；如果段落未包含此元素，则它会使用默认样式的格式。</span><span class="sxs-lookup"><span data-stu-id="c048a-107">Paragraph styles are set through the `w:pPr` element; if a paragraph does not contain this element, it is formatted with the default style.</span></span>  
  
 <span data-ttu-id="c048a-108">本主题解释某些查询的意义，然后作为一个完整工作示例的一部分来显示查询。</span><span class="sxs-lookup"><span data-stu-id="c048a-108">This topic explains the significance of some pieces of the query, then shows the query as part of a complete, working example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c048a-109">示例</span><span class="sxs-lookup"><span data-stu-id="c048a-109">Example</span></span>  
 <span data-ttu-id="c048a-110">检索文档中所有段落及其样式的查询的源如下所示：</span><span class="sxs-lookup"><span data-stu-id="c048a-110">The source of the query to retrieve all the paragraphs in a document and their styles is as follows:</span></span>  
  
```csharp  
xDoc.Root.Element(w + "body").Descendants(w + "p")  
```  
  
 <span data-ttu-id="c048a-111">此表达式与前一示例[查找默认段落样式 (C#)](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md) 中的查询的源相似。</span><span class="sxs-lookup"><span data-stu-id="c048a-111">This expression is similar to the source of the query in the previous example, [Finding the Default Paragraph Style (C#)](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md).</span></span> <span data-ttu-id="c048a-112">主要区别是它使用 <xref:System.Xml.Linq.XContainer.Descendants%2A> 轴，而不是 <xref:System.Xml.Linq.XContainer.Elements%2A> 轴。</span><span class="sxs-lookup"><span data-stu-id="c048a-112">The main difference is that it uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis instead of the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span> <span data-ttu-id="c048a-113">该查询使用 <xref:System.Xml.Linq.XContainer.Descendants%2A> 轴，因为在包含节的文档中，段落将不是正文元素的直接子元素；而是在层次结构中的两个级别之下。</span><span class="sxs-lookup"><span data-stu-id="c048a-113">The query uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis because in documents that have sections, the paragraphs will not be the direct children of the body element; rather, the paragraphs will be two levels down in the hierarchy.</span></span> <span data-ttu-id="c048a-114">通过使用 <xref:System.Xml.Linq.XContainer.Descendants%2A> 轴，无论文档是否使用节，代码都能运行。</span><span class="sxs-lookup"><span data-stu-id="c048a-114">By using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis, the code will work of whether or not the document uses sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c048a-115">示例</span><span class="sxs-lookup"><span data-stu-id="c048a-115">Example</span></span>  
 <span data-ttu-id="c048a-116">该查询使用 `let` 子句来确定包含样式节点的元素。</span><span class="sxs-lookup"><span data-stu-id="c048a-116">The query uses a `let` clause to determine the element that contains the style node.</span></span> <span data-ttu-id="c048a-117">如果没有任何元素，则将 `styleNode` 设置为 `null`：</span><span class="sxs-lookup"><span data-stu-id="c048a-117">If there is no element, then `styleNode` is set to `null`:</span></span>  
  
```csharp  
let styleNode = para.Elements(w + "pPr").Elements(w + "pStyle").FirstOrDefault()  
```  
  
 <span data-ttu-id="c048a-118">`let` 子句首先使用 <xref:System.Xml.Linq.XContainer.Elements%2A> 轴，查找所有名为 `pPr` 的元素，然后使用 <xref:System.Xml.Linq.Extensions.Elements%2A> 扩展方法，查找所有名为 `pStyle` 的子元素，最后使用 <xref:System.Linq.Enumerable.FirstOrDefault%2A> 标准查询运算符，将集合转换为单一实例。</span><span class="sxs-lookup"><span data-stu-id="c048a-118">The `let` clause first uses the <xref:System.Xml.Linq.XContainer.Elements%2A> axis to find all elements named `pPr`, then uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method to find all child elements named `pStyle`, and finally uses the <xref:System.Linq.Enumerable.FirstOrDefault%2A> standard query operator to convert the collection to a singleton.</span></span> <span data-ttu-id="c048a-119">如果集合为空，则将 `styleNode` 设置为 `null`。</span><span class="sxs-lookup"><span data-stu-id="c048a-119">If the collection is empty, `styleNode` is set to `null`.</span></span> <span data-ttu-id="c048a-120">这是一个用于查找 `pStyle` 子代节点的有用方法。</span><span class="sxs-lookup"><span data-stu-id="c048a-120">This is a useful idiom to look for the `pStyle` descendant node.</span></span> <span data-ttu-id="c048a-121">请注意，如果 `pPr` 子节点不存在，代码不会通过引发异常而运行失败；相反，它会将 `styleNode` 设置为 `null`，这是此 `let` 子句的期望行为。</span><span class="sxs-lookup"><span data-stu-id="c048a-121">Note that if the `pPr` child node does not exist, the code does nor fail by throwing an exception; instead, `styleNode` is set to `null`, which is the desired behavior of this `let` clause.</span></span>  
  
 <span data-ttu-id="c048a-122">该查询投影一个具有两个成员 `StyleName` 和 `ParagraphNode` 的匿名类型的集合。</span><span class="sxs-lookup"><span data-stu-id="c048a-122">The query projects a collection of an anonymous type with two members, `StyleName` and `ParagraphNode`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c048a-123">示例</span><span class="sxs-lookup"><span data-stu-id="c048a-123">Example</span></span>  
 <span data-ttu-id="c048a-124">本示例处理一个 WordprocessingML 文档，它从 WordprocessingML 文档中检索段落节点。</span><span class="sxs-lookup"><span data-stu-id="c048a-124">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="c048a-125">它还标识每个段落的样式。</span><span class="sxs-lookup"><span data-stu-id="c048a-125">It also identifies the style of each paragraph.</span></span> <span data-ttu-id="c048a-126">本示例以本教程中前面的一些示例为基础构建。</span><span class="sxs-lookup"><span data-stu-id="c048a-126">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="c048a-127">下面代码中的注释标识出了这个新查询。</span><span class="sxs-lookup"><span data-stu-id="c048a-127">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="c048a-128">若要查找用于创建此示例的源文档的说明，请参阅[创建源 Office Open XML 文档 (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)。</span><span class="sxs-lookup"><span data-stu-id="c048a-128">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="c048a-129">本示例使用 WindowsBase 程序集中的类。</span><span class="sxs-lookup"><span data-stu-id="c048a-129">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="c048a-130">它使用 <xref:System.IO.Packaging?displayProperty=nameWithType> 命名空间中的类型。</span><span class="sxs-lookup"><span data-stu-id="c048a-130">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative), docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
        if (styleRelation != null)  
        {  
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
            PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
            //  Load the style XML in the part into an XDocument instance.  
            styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
        }  
    }  
}  
  
string defaultStyle =   
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
// Following is the new query that finds all paragraphs in the  
// document and their styles.  
var paragraphs =  
    from para in xDoc  
                 .Root  
                 .Element(w + "body")  
                 .Descendants(w + "p")  
    let styleNode = para  
                    .Elements(w + "pPr")  
                    .Elements(w + "pStyle")  
                    .FirstOrDefault()  
    select new  
    {  
        ParagraphNode = para,  
        StyleName = styleNode != null ?  
            (string)styleNode.Attribute(w + "val") :  
            defaultStyle  
    };  
  
foreach (var p in paragraphs)  
    Console.WriteLine("StyleName:{0}", p.StyleName);  
```  
  
 <span data-ttu-id="c048a-131">当此示例应用于[创建源 Office Open XML 文档 (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md) 中说明的文档时，会生成以下输出。</span><span class="sxs-lookup"><span data-stu-id="c048a-131">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
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
  
## <a name="next-steps"></a><span data-ttu-id="c048a-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c048a-132">Next Steps</span></span>  
 <span data-ttu-id="c048a-133">在下一主题[检索段落的文本 (C#)](../../../../csharp/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md) 中，将创建一个查询来检索段落的文本。</span><span class="sxs-lookup"><span data-stu-id="c048a-133">In the next topic, [Retrieving the Text of the Paragraphs (C#)](../../../../csharp/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), you'll create a query to retrieve the text of paragraphs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c048a-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="c048a-134">See Also</span></span>

- [<span data-ttu-id="c048a-135">教程：操作 WordprocessingML 文档中的内容 (C#)</span><span class="sxs-lookup"><span data-stu-id="c048a-135">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
