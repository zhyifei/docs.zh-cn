---
title: 对不同形状的 XML 进行投影 (C#)
ms.date: 07/20/2015
ms.assetid: 4cb6b14a-32dc-4a2a-813e-bf9368fa8d86
ms.openlocfilehash: fe6166a333988d4b0a4550900a9307f1c4951aec
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43786975"
---
# <a name="projecting-xml-in-a-different-shape-c"></a><span data-ttu-id="1b592-102">对不同形状的 XML 进行投影 (C#)</span><span class="sxs-lookup"><span data-stu-id="1b592-102">Projecting XML in a Different Shape (C#)</span></span>
<span data-ttu-id="1b592-103">本主题演示对形状不同于源 XML 的 XML 进行投影的示例。</span><span class="sxs-lookup"><span data-stu-id="1b592-103">This topic shows an example of projecting XML that is in a different shape than the source XML.</span></span>  
  
 <span data-ttu-id="1b592-104">许多典型的 XML 转换由链接的查询组成，如本示例中所示。</span><span class="sxs-lookup"><span data-stu-id="1b592-104">Many typical XML transformations consist of chained queries, as in this example.</span></span> <span data-ttu-id="1b592-105">一种很常见的做法是从某种格式的 XML 开始，将中间结果投影为匿名类型或命名类型的集合，最后将结果投影回与源 XML 形状完全不同的 XML。</span><span class="sxs-lookup"><span data-stu-id="1b592-105">It is common to start with some form of XML, project intermediate results as collections of anonymous types or named types, and then finally to project the results back into XML that is in an entirely different shape than the source XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b592-106">示例</span><span class="sxs-lookup"><span data-stu-id="1b592-106">Example</span></span>  
 <span data-ttu-id="1b592-107">本示例处理一个 WordprocessingML 文档，它从 WordprocessingML 文档中检索段落节点。</span><span class="sxs-lookup"><span data-stu-id="1b592-107">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="1b592-108">本示例还标识每个段落的样式和文本。</span><span class="sxs-lookup"><span data-stu-id="1b592-108">It also identifies the style and text of each paragraph.</span></span> <span data-ttu-id="1b592-109">最后，本示例将以不同的形状投影 XML。</span><span class="sxs-lookup"><span data-stu-id="1b592-109">Finally, the example projects XML with a different shape.</span></span> <span data-ttu-id="1b592-110">本示例以本教程中前面的一些示例为基础构建。</span><span class="sxs-lookup"><span data-stu-id="1b592-110">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="1b592-111">下面代码中的注释标识出了执行投影操作的新语句。</span><span class="sxs-lookup"><span data-stu-id="1b592-111">The new statement that does the projection is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="1b592-112">有关创建此示例的源文档的说明，请参阅[创建源 Office Open XML 文档 (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)。</span><span class="sxs-lookup"><span data-stu-id="1b592-112">For instructions for creating the source document for this example, see [Creating the Source Office Open XML Document (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="1b592-113">本示例使用 WindowsBase 程序集中的类。</span><span class="sxs-lookup"><span data-stu-id="1b592-113">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="1b592-114">它使用 <xref:System.IO.Packaging?displayProperty=nameWithType> 命名空间中的类型。</span><span class="sxs-lookup"><span data-stu-id="1b592-114">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static string StringConcatenate(this IEnumerable<string> source)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item));  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate(this IEnumerable<string> source, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s).Append(separator);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item)).Append(separator);  
        return sb.ToString();  
    }  
}  
  
class Program  
{  
    public static string ParagraphText(XElement e)  
    {  
        XNamespace w = e.Name.Namespace;  
        return e  
               .Elements(w + "r")  
               .Elements(w + "t")  
               .StringConcatenate(element => (string)element);  
    }  
  
    static void Main(string[] args)  
    {  
        const string fileName = "SampleDoc.docx";  
  
        const string documentRelationshipType =  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
        const string stylesRelationshipType =  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
        const string wordmlNamespace =  
          "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
        XNamespace w = wordmlNamespace;  
  
        XDocument xDoc = null;  
        XDocument styleDoc = null;  
  
        using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
        {  
            PackageRelationship docPackageRelationship =  
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
            if (docPackageRelationship != null)  
            {  
                Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative),  
                  docPackageRelationship.TargetUri);  
                PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
                //  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
                //  Find the styles part. There will only be one.  
                PackageRelationship styleRelation =  
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
                if (styleRelation != null)  
                {  
                    Uri styleUri =  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
                    PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
                    //  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
                }  
            }  
        }  
  
        string defaultStyle =  
            (string)(  
                from style in styleDoc.Root.Elements(w + "style")  
                where (string)style.Attribute(w + "type") == "paragraph" &&  
                      (string)style.Attribute(w + "default") == "1"  
                select style  
            ).First().Attribute(w + "styleId");  
  
        // Find all paragraphs in the document.  
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
  
        // Retrieve the text of each paragraph.  
        var paraWithText =  
            from para in paragraphs  
            select new  
            {  
                ParagraphNode = para.ParagraphNode,  
                StyleName = para.StyleName,  
                Text = ParagraphText(para.ParagraphNode)  
            };  
  
        // The following is the new code that projects XML in a new shape.  
        XElement root = new XElement("Root",  
            from p in paraWithText  
            select new XElement("Paragraph",  
                new XElement("StyleName", p.StyleName),  
                new XElement("Text", p.Text)  
            )  
        );  
  
        Console.WriteLine(root);  
    }  
}  
```  
  
 <span data-ttu-id="1b592-115">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="1b592-115">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Paragraph>  
    <StyleName>Heading1</StyleName>  
    <Text>Parsing WordprocessingML with LINQ to XML</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text>The following example prints to the console.</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>using System;</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>class Program {</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>    public static void (string[] args) {</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>        Console.WriteLine("Hello World");</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>    }</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>}</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text>This example produces the following output:</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>Hello World</Text>  
  </Paragraph>  
</Root>  
```  
  
## <a name="next-steps"></a><span data-ttu-id="1b592-116">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1b592-116">Next Steps</span></span>  
 <span data-ttu-id="1b592-117">下面的示例通过查询查找 Word 文档中的所有文本：</span><span class="sxs-lookup"><span data-stu-id="1b592-117">In the next example, you'll query to find all the text in a Word document:</span></span>  
  
-   [<span data-ttu-id="1b592-118">查找 Word 文档中的文本 (C#)</span><span class="sxs-lookup"><span data-stu-id="1b592-118">Finding Text in Word Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/finding-text-in-word-documents.md)  
  
## <a name="see-also"></a><span data-ttu-id="1b592-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b592-119">See Also</span></span>

- [<span data-ttu-id="1b592-120">教程：操作 WordprocessingML 文档中的内容 (C#)</span><span class="sxs-lookup"><span data-stu-id="1b592-120">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
