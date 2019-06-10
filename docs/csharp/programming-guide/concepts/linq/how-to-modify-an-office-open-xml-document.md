---
title: 如何：修改 Office Open XML 文档 (C#)
ms.date: 07/20/2015
ms.assetid: 467d489c-2b1b-453b-a757-8ac180e82a96
ms.openlocfilehash: 3a6edd31ff2a22e32c979e1a6a548b212406cbf5
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486645"
---
# <a name="how-to-modify-an-office-open-xml-document-c"></a><span data-ttu-id="78634-102">如何：修改 Office Open XML 文档 (C#)</span><span class="sxs-lookup"><span data-stu-id="78634-102">How to: Modify an Office Open XML Document (C#)</span></span>
<span data-ttu-id="78634-103">本主题显演示一个打开、修改和保存 Office Open XML 文档的示例。</span><span class="sxs-lookup"><span data-stu-id="78634-103">This topic presents an example that opens an Office Open XML document, modifies it, and saves it.</span></span>  
  
 <span data-ttu-id="78634-104">若要详细了解 Office Open XML，请参阅 [Open XML SDK](https://github.com/OfficeDev/Open-XML-SDK) 和 [www.ericwhite.com](http://ericwhite.com/)。</span><span class="sxs-lookup"><span data-stu-id="78634-104">For more information on Office Open XML, see [Open XML SDK](https://github.com/OfficeDev/Open-XML-SDK) and [www.ericwhite.com](http://ericwhite.com/).</span></span>  
  
## <a name="example"></a><span data-ttu-id="78634-105">示例</span><span class="sxs-lookup"><span data-stu-id="78634-105">Example</span></span>  
 <span data-ttu-id="78634-106">本示例查找文档中的第一个段落元素。</span><span class="sxs-lookup"><span data-stu-id="78634-106">This example finds the first paragraph element in the document.</span></span> <span data-ttu-id="78634-107">示例从段落中检索文本，然后删除段落中的所有文本域。</span><span class="sxs-lookup"><span data-stu-id="78634-107">It retrieves the text from the paragraph, and then deletes all text runs in the paragraph.</span></span> <span data-ttu-id="78634-108">它创建一个由第一个段落已转换为大写的文本构成的新文本域。</span><span class="sxs-lookup"><span data-stu-id="78634-108">It creates a new text run that consists of the first paragraph text that has been converted to upper case.</span></span> <span data-ttu-id="78634-109">然后将已更改的 XML 序列化为 Open XML 包并关闭该包。</span><span class="sxs-lookup"><span data-stu-id="78634-109">It then serializes the changed XML into the Open XML package and closes it.</span></span>  
  
 <span data-ttu-id="78634-110">本示例使用 WindowsBase 程序集中的类。</span><span class="sxs-lookup"><span data-stu-id="78634-110">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="78634-111">它使用 <xref:System.IO.Packaging?displayProperty=nameWithType> 命名空间中的类型。</span><span class="sxs-lookup"><span data-stu-id="78634-111">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
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
  
        using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.ReadWrite))  
        {  
            PackageRelationship docPackageRelationship =  
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
            if (docPackageRelationship != null)  
            {  
                Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative),  
                  docPackageRelationship.TargetUri);  
                PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
                //  Load the document XML in the part into an XDocument instance.  
                XDocument xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
                //  Find the styles part. There will only be one.  
                PackageRelationship styleRelation =  
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
                PackagePart stylePart = null;  
                XDocument styleDoc = null;  
  
                if (styleRelation != null)  
                {  
                    Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
                    stylePart = wdPackage.GetPart(styleUri);  
  
                    //  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
                }  
  
                XElement paraNode = xDoc  
                                    .Root  
                                    .Element(w + "body")  
                                    .Descendants(w + "p")  
                                    .FirstOrDefault();  
  
                string paraText = ParagraphText(paraNode);  
  
                // remove all text runs  
                paraNode.Descendants(w + "r").Remove();  
  
                paraNode.Add(  
                    new XElement(w + "r",  
                        new XElement(w + "t", paraText.ToUpper())  
                    )  
                );  
  
                //  Save the XML into the package  
                using (XmlWriter xw =  
                  XmlWriter.Create(documentPart.GetStream(FileMode.Create, FileAccess.Write)))  
                {  
                    xDoc.Save(xw);  
                }  
  
                Console.WriteLine("New first paragraph: >{0}<", paraText.ToUpper());  
            }  
        }  
    }  
}  
```  
  
 <span data-ttu-id="78634-112">如果在运行此程序之后打开 `SampleDoc.docx`，则可以看到此程序已将文档中的第一个段落转换为大写。</span><span class="sxs-lookup"><span data-stu-id="78634-112">If you open `SampleDoc.docx` after running this program, you can see that this program converted the first paragraph in the document to upper case.</span></span>  
  
 <span data-ttu-id="78634-113">当针对[创建 Source Office Open XML 文档 (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md) 中说明的示例 Open XML 文档运行时，此示例生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="78634-113">When run with the sample Open XML document described in [Creating the Source Office Open XML Document (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md), this example produces the following output:</span></span>  
  
```  
New first paragraph: >PARSING WORDPROCESSINGML WITH LINQ TO XML<  
```  
  