---
title: 查找默认段落样式 (C#)
ms.date: 07/20/2015
ms.assetid: be102177-8ab0-444a-b671-7023e555ffdb
ms.openlocfilehash: 77eb008ba6419e58541b60ac1ca7c1ef0344e316
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43800246"
---
# <a name="finding-the-default-paragraph-style-c"></a><span data-ttu-id="8ca29-102">查找默认段落样式 (C#)</span><span class="sxs-lookup"><span data-stu-id="8ca29-102">Finding the Default Paragraph Style (C#)</span></span>
<span data-ttu-id="8ca29-103">在 WordprocessingML 文档中操作信息教程中的第一项任务是在文档中查找默认段落样式。</span><span class="sxs-lookup"><span data-stu-id="8ca29-103">The first task in the Manipulating Information in a WordprocessingML Document tutorial is to find the default style of paragraphs in the document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ca29-104">示例</span><span class="sxs-lookup"><span data-stu-id="8ca29-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="8ca29-105">描述</span><span class="sxs-lookup"><span data-stu-id="8ca29-105">Description</span></span>  
 <span data-ttu-id="8ca29-106">下面的示例打开一个 Office Open XML WordprocessingML 文档，查找文档和包的样式部分，然后执行查找默认样式名称的查询。</span><span class="sxs-lookup"><span data-stu-id="8ca29-106">The following example opens an Office Open XML WordprocessingML document, finds the document and style parts of the package, and then executes a query that finds the default style name.</span></span> <span data-ttu-id="8ca29-107">有关 Office Open XML 文档包及其构成包的信息，请参阅 [Office Open XML WordprocessingML 文档的详细信息 (C#)](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="8ca29-107">For information about Office Open XML document packages, and the parts they consist of, see [Details of Office Open XML WordprocessingML Documents (C#)](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).</span></span>  
  
 <span data-ttu-id="8ca29-108">查询将查找名为 `w:style` 的节点，该节点具有值为“paragraph”的名为 `w:type` 的属性和值为“1”的名为 `w:default` 的属性。</span><span class="sxs-lookup"><span data-stu-id="8ca29-108">The query finds a node named `w:style` that has an attribute named `w:type` with a value of "paragraph", and also has an attribute named `w:default` with a value of "1".</span></span> <span data-ttu-id="8ca29-109">由于将只有一个 XML 节点具有这些属性，因此查询使用 <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> 运算符将集合转换为单一实例。</span><span class="sxs-lookup"><span data-stu-id="8ca29-109">Because there will be only one XML node with these attributes, the query uses the <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> operator to convert a collection to a singleton.</span></span> <span data-ttu-id="8ca29-110">然后，它获取名为 `w:styleId` 的属性的值。</span><span class="sxs-lookup"><span data-stu-id="8ca29-110">It then gets the value of the attribute with the name `w:styleId`.</span></span>  
  
 <span data-ttu-id="8ca29-111">本示例使用 WindowsBase 程序集中的类。</span><span class="sxs-lookup"><span data-stu-id="8ca29-111">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="8ca29-112">它使用 <xref:System.IO.Packaging?displayProperty=nameWithType> 命名空间中的类型。</span><span class="sxs-lookup"><span data-stu-id="8ca29-112">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
### <a name="code"></a><span data-ttu-id="8ca29-113">代码</span><span class="sxs-lookup"><span data-stu-id="8ca29-113">Code</span></span>  
  
```csharp  
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
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
            PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
            //  Load the style XML in the part into an XDocument instance.  
            styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
        }  
    }  
}  
  
// The following query finds all the paragraphs that have the default style.  
string defaultStyle =   
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
Console.WriteLine("The default style is: {0}", defaultStyle);  
```  
  
### <a name="comments"></a><span data-ttu-id="8ca29-114">注释</span><span class="sxs-lookup"><span data-stu-id="8ca29-114">Comments</span></span>  
 <span data-ttu-id="8ca29-115">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="8ca29-115">This example produces the following output:</span></span>  
  
```  
The default style is: Normal  
```  
  
## <a name="next-steps"></a><span data-ttu-id="8ca29-116">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8ca29-116">Next Steps</span></span>  
 <span data-ttu-id="8ca29-117">下一个示例中将创建一个类似的查询，查找文档中的所有段落及其样式：</span><span class="sxs-lookup"><span data-stu-id="8ca29-117">In the next example, you'll create a similar query that finds all the paragraphs in a document and their styles:</span></span>  
  
-   [<span data-ttu-id="8ca29-118">检索段落及其样式 (C#)</span><span class="sxs-lookup"><span data-stu-id="8ca29-118">Retrieving the Paragraphs and Their Styles (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)  
  
## <a name="see-also"></a><span data-ttu-id="8ca29-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ca29-119">See Also</span></span>

- [<span data-ttu-id="8ca29-120">教程：操作 WordprocessingML 文档中的内容</span><span class="sxs-lookup"><span data-stu-id="8ca29-120">Tutorial: Manipulating Content in a WordprocessingML Document</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
