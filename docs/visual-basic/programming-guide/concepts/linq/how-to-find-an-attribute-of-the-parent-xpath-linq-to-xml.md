---
title: 如何：查找父级的特性 (XPath-LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 9d2572fd-27d4-426c-b079-16854cb9ec7d
ms.openlocfilehash: c4cb2f2e52aeaa42fd69b83c19c47fd205d48cbc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352960"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-visual-basic"></a>如何：查找父级的特性（LINQ to XML）（Visual Basic）
本主题演示如何定位到父元素并查找其属性。  
  
 XPath 表达式为：  
  
 `../@id`  
  
## <a name="example"></a>示例  
 此示例首先查找 `Author` 元素。 然后，查找父元素的 `id` 属性。  
  
 本示例使用以下 XML 文档：[示例 XML 文件：图书 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)。  
  
```vb  
Dim books As XDocument = XDocument.Load("Books.xml")  
Dim author As XElement = books.Root.<Book>.<Author>.FirstOrDefault()  
  
' LINQ to XML query  
Dim att1 As XAttribute = author.Parent.Attribute("id")  
  
' XPath expression  
Dim att2 As XAttribute = DirectCast(author.XPathEvaluate("../@id"),  _  
    IEnumerable).Cast(Of XAttribute)().First()  
  
If att1 Is att2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(att1)  
```  
  
 该示例产生下面的输出：  
  
```console  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a>另请参阅

- [XPath 用户的 LINQ to XML （Visual Basic）](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
