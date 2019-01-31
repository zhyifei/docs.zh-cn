---
title: 如何：从 XmlReader 创建树 (C#)
ms.date: 07/20/2015
ms.assetid: 60951c9c-7087-406c-b5bb-c60e58609b21
ms.openlocfilehash: fb65c7b74bf3bd006fd4f545e4587efe9a392131
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496174"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-c"></a><span data-ttu-id="d0611-102">如何：从 XmlReader 创建树 (C#)</span><span class="sxs-lookup"><span data-stu-id="d0611-102">How to: Create a Tree from an XmlReader (C#)</span></span>
<span data-ttu-id="d0611-103">本主题演示如何直接从 <xref:System.Xml.XmlReader> 创建 XML 树。</span><span class="sxs-lookup"><span data-stu-id="d0611-103">This topic shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="d0611-104">若要从 <xref:System.Xml.Linq.XElement> 创建 <xref:System.Xml.XmlReader>，必须将 <xref:System.Xml.XmlReader> 定位在元素节点上。</span><span class="sxs-lookup"><span data-stu-id="d0611-104">To create an <xref:System.Xml.Linq.XElement> from an <xref:System.Xml.XmlReader>, you must position the <xref:System.Xml.XmlReader> on an element node.</span></span> <span data-ttu-id="d0611-105"><xref:System.Xml.XmlReader> 将跳过注释和处理指令，但如果 <xref:System.Xml.XmlReader> 定位在文本节点上，则将引发错误。</span><span class="sxs-lookup"><span data-stu-id="d0611-105">The <xref:System.Xml.XmlReader> will skip comments and processing instructions, but if the <xref:System.Xml.XmlReader> is positioned on a text node, an error will be thrown.</span></span> <span data-ttu-id="d0611-106">若要避免这类错误，请在从 <xref:System.Xml.XmlReader> 创建 XML 树之前，始终将 <xref:System.Xml.XmlReader> 定位在元素上。</span><span class="sxs-lookup"><span data-stu-id="d0611-106">To avoid such errors, always position the <xref:System.Xml.XmlReader> on an element before you create an XML tree from the <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0611-107">示例</span><span class="sxs-lookup"><span data-stu-id="d0611-107">Example</span></span>  
 <span data-ttu-id="d0611-108">本示例使用下面的 XML 文档：[示例 XML 文件：图书 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="d0611-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="d0611-109">下面的代码创建一个 `T:System.Xml.XmlReader` 对象，然后读取节点，直到找到第一个元素节点。</span><span class="sxs-lookup"><span data-stu-id="d0611-109">The following code creates an `T:System.Xml.XmlReader` object, and then reads nodes until it finds the first element node.</span></span> <span data-ttu-id="d0611-110">然后加载 <xref:System.Xml.Linq.XElement> 对象。</span><span class="sxs-lookup"><span data-stu-id="d0611-110">It then loads the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```csharp  
XmlReader r = XmlReader.Create("books.xml");  
while (r.NodeType != XmlNodeType.Element)  
    r.Read();  
XElement e = XElement.Load(r);  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="d0611-111">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="d0611-111">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d0611-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0611-112">See also</span></span>

- [<span data-ttu-id="d0611-113">分析 XML (C#)</span><span class="sxs-lookup"><span data-stu-id="d0611-113">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
