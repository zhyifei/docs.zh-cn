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
# <a name="how-to-load-xml-from-a-file-visual-basic"></a>如何：从文件 (Visual Basic) 加载 XML
本主题演示如何通过使用 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> 方法从 URI 加载 XML。  
  
## <a name="example"></a>示例  
 下面的示例演示如何从文件加载 XML 文档。 下面的示例加载 books.xml 并将 XML 树输出到控制台。  
  
 本示例使用下面的 XML 文档：[示例 XML 文件：书籍 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)。  
  
```vb  
Dim booksFromFile As XElement = XElement.Load("books.xml")  
Console.WriteLine(booksFromFile)  
```  
  
 此代码生成以下输出：  
  
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
  
## <a name="see-also"></a>请参阅
- [分析 XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
