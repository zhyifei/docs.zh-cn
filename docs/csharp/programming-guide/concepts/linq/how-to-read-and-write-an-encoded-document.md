---
title: 如何：读取和写入编码的文档 (C#)
ms.date: 07/20/2015
ms.assetid: 84f64e71-39a6-42c6-ad68-f052bb158a03
ms.openlocfilehash: 9fc6a7beaa4a7b9de21961e1095dd41fe2e407dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317153"
---
# <a name="how-to-read-and-write-an-encoded-document-c"></a><span data-ttu-id="7506e-102">如何：读取和写入编码的文档 (C#)</span><span class="sxs-lookup"><span data-stu-id="7506e-102">How to: Read and Write an Encoded Document (C#)</span></span>
<span data-ttu-id="7506e-103">若要创建编码的 XML 文档，请向 XML 树中添加一个 <xref:System.Xml.Linq.XDeclaration>，将编码设置为需要的代码页名称。</span><span class="sxs-lookup"><span data-stu-id="7506e-103">To create an encoded XML document, you add an <xref:System.Xml.Linq.XDeclaration> to the XML tree, setting the encoding to the desired code page name.</span></span>  
  
 <span data-ttu-id="7506e-104">由 <xref:System.Text.Encoding.WebName%2A> 返回的任何值都是有效值。</span><span class="sxs-lookup"><span data-stu-id="7506e-104">Any value returned by <xref:System.Text.Encoding.WebName%2A> is a valid value.</span></span>  
  
 <span data-ttu-id="7506e-105">如果您读取编码的文档，则要将 <xref:System.Xml.Linq.XDeclaration.Encoding%2A> 属性设置为该代码页名称。</span><span class="sxs-lookup"><span data-stu-id="7506e-105">If you read an encoded document, the <xref:System.Xml.Linq.XDeclaration.Encoding%2A> property will be set to the code page name.</span></span>  
  
 <span data-ttu-id="7506e-106">如果将 <xref:System.Xml.Linq.XDeclaration.Encoding%2A> 设置为一个有效的代码页名称，则 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 将用指定的编码进行序列化。</span><span class="sxs-lookup"><span data-stu-id="7506e-106">If you set <xref:System.Xml.Linq.XDeclaration.Encoding%2A> to a valid code page name, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will serialize with the specified encoding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7506e-107">示例</span><span class="sxs-lookup"><span data-stu-id="7506e-107">Example</span></span>  
 <span data-ttu-id="7506e-108">下面的示例创建两个文档，一个文档使用 utf-8 编码，另一个使用 utf-16 编码。</span><span class="sxs-lookup"><span data-stu-id="7506e-108">The following example creates two documents, one with utf-8 encoding, and one with utf-16 encoding.</span></span> <span data-ttu-id="7506e-109">然后，该示例加载这两个文档并将编码输出到控制台。</span><span class="sxs-lookup"><span data-stu-id="7506e-109">It then loads the documents and prints the encoding to the console.</span></span>  
  
```csharp  
Console.WriteLine("Creating a document with utf-8 encoding");  
XDocument encodedDoc8 = new XDocument(  
    new XDeclaration("1.0", "utf-8", "yes"),  
    new XElement("Root", "Content")  
);  
encodedDoc8.Save("EncodedUtf8.xml");  
Console.WriteLine("Encoding is:{0}", encodedDoc8.Declaration.Encoding);  
Console.WriteLine();  
  
Console.WriteLine("Creating a document with utf-16 encoding");  
XDocument encodedDoc16 = new XDocument(  
    new XDeclaration("1.0", "utf-16", "yes"),  
    new XElement("Root", "Content")  
);  
encodedDoc16.Save("EncodedUtf16.xml");  
Console.WriteLine("Encoding is:{0}", encodedDoc16.Declaration.Encoding);  
Console.WriteLine();  
  
XDocument newDoc8 = XDocument.Load("EncodedUtf8.xml");  
Console.WriteLine("Encoded document:");  
Console.WriteLine(File.ReadAllText("EncodedUtf8.xml"));  
Console.WriteLine();  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc8.Declaration.Encoding);  
Console.WriteLine();  
  
XDocument newDoc16 = XDocument.Load("EncodedUtf16.xml");  
Console.WriteLine("Encoded document:");  
Console.WriteLine(File.ReadAllText("EncodedUtf16.xml"));  
Console.WriteLine();  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc16.Declaration.Encoding);  
```  
  
 <span data-ttu-id="7506e-110">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="7506e-110">This example produces the following output:</span></span>  
  
```  
Creating a document with utf-8 encoding  
Encoding is:utf-8  
  
Creating a document with utf-16 encoding  
Encoding is:utf-16  
  
Encoded document:  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root>Content</Root>  
  
Encoding of loaded document is:utf-8  
  
Encoded document:  
<?xml version="1.0" encoding="utf-16" standalone="yes"?>  
<Root>Content</Root>  
  
Encoding of loaded document is:utf-16  
```  
  
## <a name="see-also"></a><span data-ttu-id="7506e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="7506e-111">See Also</span></span>  
 <xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="7506e-112">高级 LINQ to XML 编程 (C#)</span><span class="sxs-lookup"><span data-stu-id="7506e-112">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
