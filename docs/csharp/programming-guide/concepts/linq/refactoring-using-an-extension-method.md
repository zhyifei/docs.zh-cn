---
title: 使用扩展方法重构 (C#)
ms.date: 07/20/2015
ms.assetid: c5fc123d-af10-4a2f-b8e4-db921efb2639
ms.openlocfilehash: 0f41c4b4357125b6c92b17d8c818a0cfcf9822e7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64596186"
---
# <a name="refactoring-using-an-extension-method-c"></a><span data-ttu-id="d0135-102">使用扩展方法重构 (C#)</span><span class="sxs-lookup"><span data-stu-id="d0135-102">Refactoring Using an Extension Method (C#)</span></span>
<span data-ttu-id="d0135-103">本示例建立在前面示例（[检索段落的文本 (C#)](../../../../csharp/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md)）的基础之上，具体方法是使用作为扩展方法实现的一个纯函数来重构字符串的串联。</span><span class="sxs-lookup"><span data-stu-id="d0135-103">This example builds on the previous example, [Retrieving the Text of the Paragraphs (C#)](../../../../csharp/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), by refactoring the concatenation of strings using a pure function that is implemented as an extension method.</span></span>  
  
 <span data-ttu-id="d0135-104">前面的示例使用 <xref:System.Linq.Enumerable.Aggregate%2A> 标准查询运算符将多个字符串串联为一个字符串。</span><span class="sxs-lookup"><span data-stu-id="d0135-104">The previous example used the <xref:System.Linq.Enumerable.Aggregate%2A> standard query operator to concatenate multiple strings into one string.</span></span> <span data-ttu-id="d0135-105">不过，编写一个扩展方法来执行此操作会更方便，因为这样实现的查询会更小、更简单。</span><span class="sxs-lookup"><span data-stu-id="d0135-105">However, it is more convenient to write an extension method to do this, because the resulting query smaller and more simple.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0135-106">示例</span><span class="sxs-lookup"><span data-stu-id="d0135-106">Example</span></span>  
 <span data-ttu-id="d0135-107">本示例处理一个 WordprocessingML 文档，检索段落、每个段落的样式以及每个段落的文本。</span><span class="sxs-lookup"><span data-stu-id="d0135-107">This example processes a WordprocessingML document, retrieving the paragraphs, the style of each paragraph, and the text of each paragraph.</span></span> <span data-ttu-id="d0135-108">本示例以本教程中前面的一些示例为基础构建。</span><span class="sxs-lookup"><span data-stu-id="d0135-108">This example builds on the previous examples in this tutorial.</span></span>  
  
 <span data-ttu-id="d0135-109">本示例包含 `StringConcatenate` 方法的多个重载。</span><span class="sxs-lookup"><span data-stu-id="d0135-109">The example contains multiple overloads of the `StringConcatenate` method.</span></span>  
  
 <span data-ttu-id="d0135-110">若要查找用于创建此示例的源文档的说明，请参阅[创建源 Office Open XML 文档 (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)。</span><span class="sxs-lookup"><span data-stu-id="d0135-110">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="d0135-111">本示例使用 WindowsBase 程序集中的类。</span><span class="sxs-lookup"><span data-stu-id="d0135-111">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="d0135-112">它使用 <xref:System.IO.Packaging?displayProperty=nameWithType> 命名空间中的类型。</span><span class="sxs-lookup"><span data-stu-id="d0135-112">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
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
```  
  
## <a name="example"></a><span data-ttu-id="d0135-113">示例</span><span class="sxs-lookup"><span data-stu-id="d0135-113">Example</span></span>  
 <span data-ttu-id="d0135-114">`StringConcatenate` 方法有四个重载。</span><span class="sxs-lookup"><span data-stu-id="d0135-114">There are four overloads of the `StringConcatenate` method.</span></span> <span data-ttu-id="d0135-115">其中一个重载仅接受字符串集合并返回单个字符串。</span><span class="sxs-lookup"><span data-stu-id="d0135-115">One overload simply takes a collection of strings and returns a single string.</span></span> <span data-ttu-id="d0135-116">另一个重载可以接受任何类型的集合，以及从该集合的单一实例映射到字符串的委托。</span><span class="sxs-lookup"><span data-stu-id="d0135-116">Another overload can take a collection of any type, and a delegate that projects from a singleton of the collection to a string.</span></span> <span data-ttu-id="d0135-117">使用其余两个重载可以指定分隔符字符串。</span><span class="sxs-lookup"><span data-stu-id="d0135-117">There are two more overloads that allow you to specify a separator string.</span></span>  
  
 <span data-ttu-id="d0135-118">下面的代码使用所有四个重载。</span><span class="sxs-lookup"><span data-stu-id="d0135-118">The following code uses all four overloads.</span></span>  
  
```csharp  
string[] numbers = { "one", "two", "three" };  
  
Console.WriteLine("{0}", numbers.StringConcatenate());  
Console.WriteLine("{0}", numbers.StringConcatenate(":"));  
  
int[] intNumbers = { 1, 2, 3 };  
Console.WriteLine("{0}", intNumbers.StringConcatenate(i => i.ToString()));  
Console.WriteLine("{0}", intNumbers.StringConcatenate(i => i.ToString(), ":"));  
```  
  
 <span data-ttu-id="d0135-119">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="d0135-119">This example produces the following output:</span></span>  
  
```  
onetwothree  
one:two:three:  
123  
1:2:3:  
```  
  
## <a name="example"></a><span data-ttu-id="d0135-120">示例</span><span class="sxs-lookup"><span data-stu-id="d0135-120">Example</span></span>  
 <span data-ttu-id="d0135-121">现在，可以对示例进行修改，从而利用新扩展方法。</span><span class="sxs-lookup"><span data-stu-id="d0135-121">Now, the example can be modified to take advantage of the new extension method:</span></span>  
  
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
                Text = para  
                       .ParagraphNode  
                       .Elements(w + "r")  
                       .Elements(w + "t")  
                       .StringConcatenate(e => (string)e)  
            };  
  
        foreach (var p in paraWithText)  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text);  
    }  
}  
```  
  
 <span data-ttu-id="d0135-122">当此示例应用于[创建源 Office Open XML 文档 (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md) 中说明的文档时，会生成以下输出。</span><span class="sxs-lookup"><span data-stu-id="d0135-122">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
```  
StyleName:Heading1 >Parsing WordprocessingML with LINQ to XML<  
StyleName:Normal ><  
StyleName:Normal >The following example prints to the console.<  
StyleName:Normal ><  
StyleName:Code >using System;<  
StyleName:Code ><  
StyleName:Code >class Program {<  
StyleName:Code >    public static void (string[] args) {<  
StyleName:Code >        Console.WriteLine("Hello World");<  
StyleName:Code >    }<  
StyleName:Code >}<  
StyleName:Normal ><  
StyleName:Normal >This example produces the following output:<  
StyleName:Normal ><  
StyleName:Code >Hello World<  
```  
  
 <span data-ttu-id="d0135-123">请注意，此重构是重构到纯函数的一种变体。</span><span class="sxs-lookup"><span data-stu-id="d0135-123">Note that this refactoring is a variant of refactoring into a pure function.</span></span> <span data-ttu-id="d0135-124">下一主题将更详细地介绍重构到纯函数的概念。</span><span class="sxs-lookup"><span data-stu-id="d0135-124">The next topic will introduce the idea of factoring into pure functions in more detail.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d0135-125">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d0135-125">Next Steps</span></span>  
 <span data-ttu-id="d0135-126">下一示例演示如何使用纯函数以其他方式重构此代码：</span><span class="sxs-lookup"><span data-stu-id="d0135-126">The next example shows how to refactor this code in another way, by using pure functions:</span></span>  
  
- [<span data-ttu-id="d0135-127">使用纯函数重构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0135-127">Refactoring Using a Pure Function (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-a-pure-function.md)  
  
## <a name="see-also"></a><span data-ttu-id="d0135-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0135-128">See also</span></span>

- [<span data-ttu-id="d0135-129">教程：操作 WordprocessingML 文档中的内容 (C#)</span><span class="sxs-lookup"><span data-stu-id="d0135-129">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
- [<span data-ttu-id="d0135-130">重构为纯函数 (C#)</span><span class="sxs-lookup"><span data-stu-id="d0135-130">Refactoring Into Pure Functions (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md)
