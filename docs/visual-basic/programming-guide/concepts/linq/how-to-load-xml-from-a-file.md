---
title: "如何： 从文件 (Visual Basic) 加载 XML"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2d337ad-8ac8-4671-b694-30e5ca1413b7
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7babad6b08b2aa486c2ae92e7ad2485d62ac5d47
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-load-xml-from-a-file-visual-basic"></a><span data-ttu-id="00267-102">如何： 从文件 (Visual Basic) 加载 XML</span><span class="sxs-lookup"><span data-stu-id="00267-102">How to: Load XML from a File (Visual Basic)</span></span>
<span data-ttu-id="00267-103">本主题演示如何通过使用 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> 方法从 URI 加载 XML。</span><span class="sxs-lookup"><span data-stu-id="00267-103">This topic shows how to load XML from a URI by using the <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00267-104">示例</span><span class="sxs-lookup"><span data-stu-id="00267-104">Example</span></span>  
 <span data-ttu-id="00267-105">下面的示例演示如何从文件加载 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="00267-105">The following example shows how to load an XML document from a file.</span></span> <span data-ttu-id="00267-106">下面的示例加载 books.xml 并将 XML 树输出到控制台。</span><span class="sxs-lookup"><span data-stu-id="00267-106">The following example loads books.xml and outputs the XML tree to the console.</span></span>  
  
 <span data-ttu-id="00267-107">本示例使用以下 XML 文档：[示例 XML 文件：图书 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="00267-107">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```vb  
Dim booksFromFile As XElement = XElement.Load("books.xml")  
Console.WriteLine(booksFromFile)  
```  
  
 <span data-ttu-id="00267-108">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="00267-108">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="00267-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00267-109">See Also</span></span>  
 [<span data-ttu-id="00267-110">分析 XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00267-110">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
