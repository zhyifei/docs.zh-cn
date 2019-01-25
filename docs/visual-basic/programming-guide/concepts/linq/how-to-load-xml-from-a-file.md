---
title: 如何：从文件 (Visual Basic) 加载 XML
ms.date: 07/20/2015
ms.assetid: e2d337ad-8ac8-4671-b694-30e5ca1413b7
ms.openlocfilehash: 9ca19868629c89c10a8aca8f88860115a9efe7bc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494660"
---
# <a name="how-to-load-xml-from-a-file-visual-basic"></a><span data-ttu-id="831fb-102">如何：从文件 (Visual Basic) 加载 XML</span><span class="sxs-lookup"><span data-stu-id="831fb-102">How to: Load XML from a File (Visual Basic)</span></span>
<span data-ttu-id="831fb-103">本主题演示如何通过使用 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> 方法从 URI 加载 XML。</span><span class="sxs-lookup"><span data-stu-id="831fb-103">This topic shows how to load XML from a URI by using the <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="831fb-104">示例</span><span class="sxs-lookup"><span data-stu-id="831fb-104">Example</span></span>  
 <span data-ttu-id="831fb-105">下面的示例演示如何从文件加载 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="831fb-105">The following example shows how to load an XML document from a file.</span></span> <span data-ttu-id="831fb-106">下面的示例加载 books.xml 并将 XML 树输出到控制台。</span><span class="sxs-lookup"><span data-stu-id="831fb-106">The following example loads books.xml and outputs the XML tree to the console.</span></span>  
  
 <span data-ttu-id="831fb-107">本示例使用下面的 XML 文档：[示例 XML 文件：书籍 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="831fb-107">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```vb  
Dim booksFromFile As XElement = XElement.Load("books.xml")  
Console.WriteLine(booksFromFile)  
```  
  
 <span data-ttu-id="831fb-108">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="831fb-108">This code produces the following output:</span></span>  
  
```xml  
<Catalog>  
  <Book id="bk101">  
    <Author>Garghentini, Davide</Author>  
    <Title>XML Developer's Guide</Title>  
    <Genre>Computer</Genre>  
    <Price>44.95</Price>  
    <PublishDate>2000-10-01</PublishDate>  
    <Description>An in-depth look at creating applications   
      with XML.</Description>  
  </Book>  
  <Book id="bk102">  
    <Author>Garcia, Debra</Author>  
    <Title>Midnight Rain</Title>  
    <Genre>Fantasy</Genre>  
    <Price>5.95</Price>  
    <PublishDate>2000-12-16</PublishDate>  
    <Description>A former architect battles corporate zombies,   
      an evil sorceress, and her own childhood to become queen   
      of the world.</Description>  
  </Book>  
</Catalog>  
```  
  
## <a name="see-also"></a><span data-ttu-id="831fb-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="831fb-109">See also</span></span>
- [<span data-ttu-id="831fb-110">分析 XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="831fb-110">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
